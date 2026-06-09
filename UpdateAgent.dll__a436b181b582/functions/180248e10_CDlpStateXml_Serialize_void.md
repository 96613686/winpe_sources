# CDlpStateXml::Serialize(void)

- ea: `0x180248e10`
- end: `0x1802491cd`
- name: `?Serialize@CDlpStateXml@@QEAAJXZ`
- size: `957`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18024a9d8`

## callees

- `0x1800061d4`
- `0x180039f90`
- `0x180077664`
- `0x180248e10`
- `0x180288c98`
- `0x18028a2f0`
- `0x18028aaa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180249166`
- `ntdll!RtlFreeHeap` at `0x180249166`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180249020`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802490e0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180249020`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802490e0`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180249049`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180249109`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180249049`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180249109`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180248fe7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1802490a3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180248fe7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1802490a3`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180248f92`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18024907a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180248f92`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18024907a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180248eee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18024919b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180248eee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18024919b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180248f02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802491af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180248f02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802491af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180248fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180248fa2`

## pseudocode

```c
__int64 __fastcall CDlpStateXml::Serialize(CDlpStateXml *this, __int64 a2)
{
  Unattend **v2; // r15
  void *v3; // rdi
  __int64 v4; // r12
  Unattend *v6; // r14
  signed int RootNode; // ebx
  signed int v8; // eax
  __int64 *v9; // rax
  PVOID v10; // r15
  __int64 v11; // rcx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  Unattend **v14; // r14
  Unattend *v15; // r14
  signed int v16; // eax
  signed int LastError; // eax
  __int64 v18; // rcx
  PVOID *v19; // rax
  HANDLE v20; // rax
  __int128 v22; // [rsp+30h] [rbp-40h] BYREF
  PVOID P[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v24; // [rsp+50h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-10h]
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp+40h] BYREF
  LPCVOID lpBuffer; // [rsp+B8h] [rbp+48h] BYREF
  __int64 nNumberOfBytesToWrite; // [rsp+C0h] [rbp+50h] BYREF

  v2 = (Unattend **)*((_QWORD *)this + 16);
  v3 = 0;
  v4 = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v25 = 0;
  *(_OWORD *)P = 0;
  v24 = 0;
  if ( !v2 || (v6 = *v2) == 0 )
  {
    RootNode = -2147024809;
LABEL_33:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)RootNode, a2);
    v10 = P[0];
    goto LABEL_34;
  }
  RootNode = Unattend::GetRootNode(*v2, (struct UnattendNode *)&v22);
  if ( RootNode >= 0 )
  {
    v8 = PopulateNode(v6, v2, &v22, P);
    v4 = v25;
    RootNode = v8;
  }
  if ( RootNode < 0 )
    goto LABEL_33;
  v9 = (__int64 *)*((_QWORD *)this + 16);
  v10 = P[0];
  if ( !v9
    || (v11 = *v9) == 0
    || !P[0]
    || (v22 = *(_OWORD *)P[0],
        v12 = Unattend::SerializeToBuffer(v11, &v22, &lpBuffer, &nNumberOfBytesToWrite, 1),
        v3 = (void *)lpBuffer,
        RootNode = v12,
        v12 < 0) )
  {
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      v3 = 0;
      lpBuffer = 0;
    }
    v14 = (Unattend **)*((_QWORD *)this + 16);
    if ( !v14 || (v15 = *v14) == 0 )
    {
      RootNode = -2147024809;
LABEL_31:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)RootNode, a2);
      goto LABEL_34;
    }
    RootNode = Unattend::GetRootNode(v15, (struct UnattendNode *)&v22);
    if ( RootNode >= 0 )
    {
      v16 = Unattend::SerializeToBuffer(v15, &v22, &lpBuffer, &nNumberOfBytesToWrite, 0);
      v3 = (void *)lpBuffer;
      RootNode = v16;
    }
    if ( RootNode < 0 )
      goto LABEL_31;
  }
  if ( !SetFilePointerEx(
          (HANDLE)(*((_QWORD *)this + 13) & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          0,
          0,
          0)
    || !SetEndOfFile((HANDLE)(*((_QWORD *)this + 13)
                            & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !WriteFile(
          (HANDLE)(*((_QWORD *)this + 13) & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          v3,
          nNumberOfBytesToWrite,
          &NumberOfBytesWritten,
          0)
    || !FlushFileBuffers((HANDLE)(*((_QWORD *)this + 13)
                                & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !SetFilePointerEx(
          (HANDLE)(*((_QWORD *)this + 14) & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          0,
          0,
          0)
    || !SetEndOfFile((HANDLE)(*((_QWORD *)this + 14)
                            & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !WriteFile(
          (HANDLE)(*((_QWORD *)this + 14) & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          v3,
          nNumberOfBytesToWrite,
          &NumberOfBytesWritten,
          0)
    || !FlushFileBuffers((HANDLE)(*((_QWORD *)this + 14)
                                & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0))) )
  {
    LastError = GetLastError();
    RootNode = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        RootNode = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      RootNode = -2147467259;
    }
    goto LABEL_31;
  }
LABEL_34:
  if ( v10 )
  {
    if ( *(_QWORD *)v4 )
      --*(_QWORD *)(*(_QWORD *)v4 + 24LL);
    if ( P[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    operator delete(v10);
    v18 = 40;
    v19 = P;
    do
    {
      *(_BYTE *)v19 = 0;
      v19 = (PVOID *)((char *)v19 + 1);
      --v18;
    }
    while ( v18 );
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)RootNode);
  if ( v3 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v3);
  }
  return (unsigned int)RootNode;
}

```

## disassembly

```asm
0x180248e10  push    rbp
0x180248e12  push    rbx
0x180248e13  push    rsi
0x180248e14  push    rdi
0x180248e15  push    r12
0x180248e17  push    r14
0x180248e19  push    r15
0x180248e1b  mov     rbp, rsp
0x180248e1e  sub     rsp, 70h
0x180248e22  mov     r15, [rcx+80h]
0x180248e29  xor     edi, edi
0x180248e2b  xor     r12d, r12d
0x180248e2e  mov     [rbp+lpBuffer], rdi
0x180248e32  mov     [rbp+nNumberOfBytesToWrite], rdi
0x180248e36  xorps   xmm0, xmm0
0x180248e39  mov     [rbp+NumberOfBytesWritten], edi
0x180248e3c  mov     rsi, rcx
0x180248e3f  mov     [rbp+var_10], r12
0x180248e43  movups  xmmword ptr [rbp+P], xmm0
0x180248e47  movups  [rbp+var_20], xmm0
0x180248e4b  test    r15, r15
0x180248e4e  jz      loc_18024912C
0x180248e54  mov     r14, [r15]
0x180248e57  test    r14, r14
0x180248e5a  jz      loc_18024912C
0x180248e60  lea     rdx, [rbp+var_40]; struct UnattendNode *
0x180248e64  mov     rcx, r14; this
0x180248e67  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x180248e6c  mov     ebx, eax
0x180248e6e  test    eax, eax
0x180248e70  js      short loc_180248E94
0x180248e72  movaps  xmm0, [rbp+var_40]
0x180248e76  lea     r9, [rbp+P]
0x180248e7a  lea     r8, [rbp+var_40]
0x180248e7e  movdqa  [rbp+var_40], xmm0
0x180248e83  mov     rdx, r15
0x180248e86  mov     rcx, r14
0x180248e89  call    ?PopulateNode@@YAJAEAVUnattend@@PEBU_UNATTEND_CONTEXT@@VUnattendNode@@PEAU_UNATTEND_NODE@@@Z; PopulateNode(Unattend &,_UNATTEND_CONTEXT const *,UnattendNode,_UNATTEND_NODE *)
0x180248e8e  mov     r12, [rbp+var_10]
0x180248e92  mov     ebx, eax
0x180248e94  test    ebx, ebx
0x180248e96  js      loc_180249131
0x180248e9c  mov     rax, [rsi+80h]
0x180248ea3  mov     r15, [rbp+P]
0x180248ea7  test    rax, rax
0x180248eaa  jz      short loc_180248EE9
0x180248eac  mov     rcx, [rax]
0x180248eaf  test    rcx, rcx
0x180248eb2  jz      short loc_180248EE9
0x180248eb4  test    r15, r15
0x180248eb7  jz      short loc_180248EE9
0x180248eb9  movups  xmm0, xmmword ptr [r15]
0x180248ebd  lea     r9, [rbp+nNumberOfBytesToWrite]
0x180248ec1  mov     dword ptr [rsp+70h+lpOverlapped], 1
0x180248ec9  lea     r8, [rbp+lpBuffer]
0x180248ecd  lea     rdx, [rbp+var_40]
0x180248ed1  movdqu  [rbp+var_40], xmm0
0x180248ed6  call    ?SerializeToBuffer@Unattend@@QEAAJVUnattendNode@@PEAPEAGPEA_KH@Z; Unattend::SerializeToBuffer(UnattendNode,ushort * *,unsigned __int64 *,int)
0x180248edb  mov     rdi, [rbp+lpBuffer]
0x180248edf  mov     ebx, eax
0x180248ee1  test    eax, eax
0x180248ee3  jns     loc_180248F75
0x180248ee9  test    rdi, rdi
0x180248eec  jz      short loc_180248F14
0x180248eee  call    cs:__imp_GetProcessHeap
0x180248ef5  nop     dword ptr [rax+rax+00h]
0x180248efa  mov     r8, rdi; lpMem
0x180248efd  xor     edx, edx; dwFlags
0x180248eff  mov     rcx, rax; hHeap
0x180248f02  call    cs:__imp_HeapFree
0x180248f09  nop     dword ptr [rax+rax+00h]
0x180248f0e  xor     edi, edi
0x180248f10  mov     [rbp+lpBuffer], rdi
0x180248f14  mov     r14, [rsi+80h]
0x180248f1b  test    r14, r14
0x180248f1e  jz      loc_18024911E
0x180248f24  mov     r14, [r14]
0x180248f27  test    r14, r14
0x180248f2a  jz      loc_18024911E
0x180248f30  lea     rdx, [rbp+var_40]; struct UnattendNode *
0x180248f34  mov     rcx, r14; this
0x180248f37  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x180248f3c  mov     ebx, eax
0x180248f3e  test    eax, eax
0x180248f40  js      short loc_180248F6D
0x180248f42  movaps  xmm0, [rbp+var_40]
0x180248f46  lea     r9, [rbp+nNumberOfBytesToWrite]
0x180248f4a  lea     r8, [rbp+lpBuffer]
0x180248f4e  movdqa  [rbp+var_40], xmm0
0x180248f53  lea     rdx, [rbp+var_40]
0x180248f57  mov     dword ptr [rsp+70h+lpOverlapped], 0
0x180248f5f  mov     rcx, r14
0x180248f62  call    ?SerializeToBuffer@Unattend@@QEAAJVUnattendNode@@PEAPEAGPEA_KH@Z; Unattend::SerializeToBuffer(UnattendNode,ushort * *,unsigned __int64 *,int)
0x180248f67  mov     rdi, [rbp+lpBuffer]
0x180248f6b  mov     ebx, eax
0x180248f6d  test    ebx, ebx
0x180248f6f  js      loc_180249123
0x180248f75  mov     r8, [rsi+68h]
0x180248f79  xor     edx, edx; liDistanceToMove
0x180248f7b  lea     rax, [r8+1]
0x180248f7f  and     rax, 0FFFFFFFFFFFFFFFEh
0x180248f83  neg     rax
0x180248f86  sbb     rcx, rcx
0x180248f89  xor     r9d, r9d; dwMoveMethod
0x180248f8c  and     rcx, r8; hFile
0x180248f8f  xor     r8d, r8d; lpNewFilePointer
0x180248f92  call    cs:__imp_SetFilePointerEx
0x180248f99  nop     dword ptr [rax+rax+00h]
0x180248f9e  test    eax, eax
0x180248fa0  jnz     short loc_180248FD2
0x180248fa2  call    cs:__imp_GetLastError
0x180248fa9  nop     dword ptr [rax+rax+00h]
0x180248fae  mov     ebx, eax
0x180248fb0  test    eax, eax
0x180248fb2  jnz     short loc_180248FBE
0x180248fb4  mov     ebx, 80004005h
0x180248fb9  jmp     loc_180249123
0x180248fbe  jle     loc_180249123
0x180248fc4  movzx   ebx, ax
0x180248fc7  or      ebx, 80070000h
0x180248fcd  jmp     loc_180249123
0x180248fd2  mov     rdx, [rsi+68h]
0x180248fd6  lea     rax, [rdx+1]
0x180248fda  and     rax, 0FFFFFFFFFFFFFFFEh
0x180248fde  neg     rax
0x180248fe1  sbb     rcx, rcx
0x180248fe4  and     rcx, rdx; hFile
0x180248fe7  call    cs:__imp_SetEndOfFile
0x180248fee  nop     dword ptr [rax+rax+00h]
0x180248ff3  test    eax, eax
0x180248ff5  jz      short loc_180248FA2
0x180248ff7  mov     rdx, [rsi+68h]
0x180248ffb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180248fff  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180249003  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18024900c  lea     rax, [rdx+1]
0x180249010  and     rax, 0FFFFFFFFFFFFFFFEh
0x180249014  neg     rax
0x180249017  sbb     rcx, rcx
0x18024901a  and     rcx, rdx; hFile
0x18024901d  mov     rdx, rdi; lpBuffer
0x180249020  call    cs:__imp_WriteFile
0x180249027  nop     dword ptr [rax+rax+00h]
0x18024902c  test    eax, eax
0x18024902e  jz      loc_180248FA2
0x180249034  mov     rdx, [rsi+68h]
0x180249038  lea     rax, [rdx+1]
0x18024903c  and     rax, 0FFFFFFFFFFFFFFFEh
0x180249040  neg     rax
0x180249043  sbb     rcx, rcx
0x180249046  and     rcx, rdx; hFile
0x180249049  call    cs:__imp_FlushFileBuffers
0x180249050  nop     dword ptr [rax+rax+00h]
0x180249055  test    eax, eax
0x180249057  jz      loc_180248FA2
0x18024905d  mov     r8, [rsi+70h]
0x180249061  xor     edx, edx; liDistanceToMove
0x180249063  lea     rax, [r8+1]
0x180249067  and     rax, 0FFFFFFFFFFFFFFFEh
0x18024906b  neg     rax
0x18024906e  sbb     rcx, rcx
0x180249071  xor     r9d, r9d; dwMoveMethod
0x180249074  and     rcx, r8; hFile
0x180249077  xor     r8d, r8d; lpNewFilePointer
0x18024907a  call    cs:__imp_SetFilePointerEx
0x180249081  nop     dword ptr [rax+rax+00h]
0x180249086  test    eax, eax
0x180249088  jz      loc_180248FA2
0x18024908e  mov     rdx, [rsi+70h]
0x180249092  lea     rax, [rdx+1]
0x180249096  and     rax, 0FFFFFFFFFFFFFFFEh
0x18024909a  neg     rax
0x18024909d  sbb     rcx, rcx
0x1802490a0  and     rcx, rdx; hFile
0x1802490a3  call    cs:__imp_SetEndOfFile
0x1802490aa  nop     dword ptr [rax+rax+00h]
0x1802490af  test    eax, eax
0x1802490b1  jz      loc_180248FA2
0x1802490b7  mov     rdx, [rsi+70h]
0x1802490bb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802490bf  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1802490c3  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1802490cc  lea     rax, [rdx+1]
0x1802490d0  and     rax, 0FFFFFFFFFFFFFFFEh
0x1802490d4  neg     rax
0x1802490d7  sbb     rcx, rcx
0x1802490da  and     rcx, rdx; hFile
0x1802490dd  mov     rdx, rdi; lpBuffer
0x1802490e0  call    cs:__imp_WriteFile
0x1802490e7  nop     dword ptr [rax+rax+00h]
0x1802490ec  test    eax, eax
0x1802490ee  jz      loc_180248FA2
0x1802490f4  mov     rdx, [rsi+70h]
0x1802490f8  lea     rax, [rdx+1]
0x1802490fc  and     rax, 0FFFFFFFFFFFFFFFEh
0x180249100  neg     rax
0x180249103  sbb     rcx, rcx
0x180249106  and     rcx, rdx; hFile
0x180249109  call    cs:__imp_FlushFileBuffers
0x180249110  nop     dword ptr [rax+rax+00h]
0x180249115  test    eax, eax
0x180249117  jnz     short loc_18024913C
0x180249119  jmp     loc_180248FA2
0x18024911e  mov     ebx, 80070057h
0x180249123  mov     ecx, ebx
0x180249125  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18024912a  jmp     short loc_18024913C
0x18024912c  mov     ebx, 80070057h
0x180249131  mov     ecx, ebx
0x180249133  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180249138  mov     r15, [rbp+P]
0x18024913c  test    r15, r15
0x18024913f  jz      short loc_18024918F
0x180249141  mov     rax, [r12]
0x180249145  test    rax, rax
0x180249148  jz      short loc_18024914E
0x18024914a  dec     qword ptr [rax+18h]
0x18024914e  mov     r8, [rbp+P+8]; P
0x180249152  test    r8, r8
0x180249155  jz      short loc_180249172
0x180249157  mov     rcx, gs:60h
0x180249160  xor     edx, edx; Flags
0x180249162  mov     rcx, [rcx+30h]; HeapHandle
0x180249166  call    cs:__imp_RtlFreeHeap
0x18024916d  nop     dword ptr [rax+rax+00h]
0x180249172  mov     rcx, r15; Block
0x180249175  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18024917a  mov     ecx, 28h ; '('
0x18024917f  lea     rax, [rbp+P]
0x180249183  mov     byte ptr [rax], 0
0x180249186  inc     rax
0x180249189  sub     rcx, 1
0x18024918d  jnz     short loc_180249183
0x18024918f  mov     ecx, ebx
0x180249191  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180249196  test    rdi, rdi
0x180249199  jz      short loc_1802491BB
0x18024919b  call    cs:__imp_GetProcessHeap
0x1802491a2  nop     dword ptr [rax+rax+00h]
0x1802491a7  mov     r8, rdi; lpMem
0x1802491aa  xor     edx, edx; dwFlags
0x1802491ac  mov     rcx, rax; hHeap
0x1802491af  call    cs:__imp_HeapFree
0x1802491b6  nop     dword ptr [rax+rax+00h]
0x1802491bb  mov     eax, ebx
0x1802491bd  add     rsp, 70h
0x1802491c1  pop     r15
0x1802491c3  pop     r14
0x1802491c5  pop     r12
0x1802491c7  pop     rdi
0x1802491c8  pop     rsi
0x1802491c9  pop     rbx
0x1802491ca  pop     rbp
0x1802491cb  retn
```
