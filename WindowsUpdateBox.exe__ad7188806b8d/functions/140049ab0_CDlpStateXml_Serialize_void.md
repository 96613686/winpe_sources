# CDlpStateXml::Serialize(void)

- ea: `0x140049ab0`
- end: `0x140049e7e`
- name: `?Serialize@CDlpStateXml@@QEAAJXZ`
- size: `974`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14004ae2c`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140049ab0`
- `0x14005eecc`
- `0x140060734`
- `0x140060f00`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140049c41`
- `KERNEL32!SetFilePointerEx` at `0x140049d19`
- `KERNEL32!SetFilePointerEx` at `0x140049c41`
- `KERNEL32!SetFilePointerEx` at `0x140049d19`
- `KERNEL32!FlushFileBuffers` at `0x140049cec`
- `KERNEL32!FlushFileBuffers` at `0x140049d9c`
- `KERNEL32!FlushFileBuffers` at `0x140049cec`
- `KERNEL32!FlushFileBuffers` at `0x140049d9c`
- `KERNEL32!HeapFree` at `0x140049bb2`
- `KERNEL32!HeapFree` at `0x140049e19`
- `KERNEL32!HeapFree` at `0x140049e5b`
- `KERNEL32!HeapFree` at `0x140049bb2`
- `KERNEL32!HeapFree` at `0x140049e19`
- `KERNEL32!HeapFree` at `0x140049e5b`
- `KERNEL32!GetProcessHeap` at `0x140049b9e`
- `KERNEL32!GetProcessHeap` at `0x140049e05`
- `KERNEL32!GetProcessHeap` at `0x140049e47`
- `KERNEL32!GetProcessHeap` at `0x140049b9e`
- `KERNEL32!GetProcessHeap` at `0x140049e05`
- `KERNEL32!GetProcessHeap` at `0x140049e47`
- `KERNEL32!GetLastError` at `0x140049c51`
- `KERNEL32!GetLastError` at `0x140049c51`
- `KERNEL32!SetEndOfFile` at `0x140049c92`
- `KERNEL32!SetEndOfFile` at `0x140049d3e`
- `KERNEL32!SetEndOfFile` at `0x140049c92`
- `KERNEL32!SetEndOfFile` at `0x140049d3e`
- `KERNEL32!WriteFile` at `0x140049cc7`
- `KERNEL32!WriteFile` at `0x140049d77`
- `KERNEL32!WriteFile` at `0x140049cc7`
- `KERNEL32!WriteFile` at `0x140049d77`
- `ntdll!RtlFreeHeap` at `0x140049df9`
- `ntdll!RtlFreeHeap` at `0x140049df9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpStateXml::Serialize(CDlpStateXml *this)
{
  void *v2; // r12
  __int64 v3; // r13
  Unattend **v4; // r15
  Unattend *v5; // r14
  signed int RootNode; // edi
  int v7; // ecx
  __int64 *v8; // rax
  PVOID v9; // r15
  __int64 v10; // rcx
  HANDLE ProcessHeap; // rax
  Unattend **v12; // r14
  Unattend *v13; // r14
  int v14; // ecx
  void *v15; // rcx
  signed int LastError; // eax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  HANDLE v24; // rax
  __int64 v25; // rcx
  PVOID *v26; // rax
  HANDLE v27; // rax
  __int128 v29; // [rsp+40h] [rbp-40h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v31; // [rsp+60h] [rbp-20h]
  __int64 v32; // [rsp+70h] [rbp-10h]
  DWORD NumberOfBytesWritten; // [rsp+C0h] [rbp+40h] BYREF
  LPCVOID lpBuffer; // [rsp+C8h] [rbp+48h] BYREF
  __int64 nNumberOfBytesToWrite; // [rsp+D0h] [rbp+50h] BYREF

  v2 = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v3 = 0;
  *(_OWORD *)P = 0;
  v31 = 0;
  v32 = 0;
  v4 = (Unattend **)*((_QWORD *)this + 16);
  if ( !v4 || (v5 = *v4) == 0 )
  {
    RootNode = -2147024809;
    v7 = -2147024809;
LABEL_58:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    v9 = P[0];
    goto LABEL_59;
  }
  RootNode = Unattend::GetRootNode(*v4, (struct UnattendNode *)&v29);
  if ( RootNode >= 0 )
  {
    RootNode = PopulateNode(v5, v4, &v29, P);
    v3 = v32;
  }
  v7 = RootNode;
  if ( RootNode < 0 )
    goto LABEL_58;
  v8 = (__int64 *)*((_QWORD *)this + 16);
  v9 = P[0];
  if ( !v8
    || (v10 = *v8) == 0
    || !P[0]
    || (v29 = *(_OWORD *)P[0],
        RootNode = Unattend::SerializeToBuffer(v10, &v29, &lpBuffer, &nNumberOfBytesToWrite, 1),
        v2 = (void *)lpBuffer,
        RootNode < 0) )
  {
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
      v2 = 0;
      lpBuffer = 0;
    }
    v12 = (Unattend **)*((_QWORD *)this + 16);
    if ( !v12 || (v13 = *v12) == 0 )
    {
      RootNode = -2147024809;
LABEL_55:
      v14 = RootNode;
LABEL_56:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
      goto LABEL_59;
    }
    RootNode = Unattend::GetRootNode(v13, (struct UnattendNode *)&v29);
    if ( RootNode >= 0 )
    {
      RootNode = Unattend::SerializeToBuffer(v13, &v29, &lpBuffer, &nNumberOfBytesToWrite, 0);
      v2 = (void *)lpBuffer;
    }
    v14 = RootNode;
    if ( RootNode < 0 )
      goto LABEL_56;
  }
  v15 = (void *)*((_QWORD *)this + 13);
  if ( !v15 || v15 == (void *)-1LL )
    v15 = 0;
  if ( !SetFilePointerEx(v15, 0, 0, 0) )
    goto LABEL_21;
  v17 = (void *)*((_QWORD *)this + 13);
  if ( !v17 || v17 == (void *)-1LL )
    v17 = 0;
  if ( !SetEndOfFile(v17) )
    goto LABEL_21;
  v18 = (void *)*((_QWORD *)this + 13);
  if ( !v18 || v18 == (void *)-1LL )
    v18 = 0;
  if ( !WriteFile(v18, v2, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    goto LABEL_21;
  v19 = (void *)*((_QWORD *)this + 13);
  if ( !v19 || v19 == (void *)-1LL )
    v19 = 0;
  if ( !FlushFileBuffers(v19) )
    goto LABEL_21;
  v20 = (void *)*((_QWORD *)this + 14);
  if ( !v20 || v20 == (void *)-1LL )
    v20 = 0;
  if ( !SetFilePointerEx(v20, 0, 0, 0) )
    goto LABEL_21;
  v21 = (void *)*((_QWORD *)this + 14);
  if ( !v21 || v21 == (void *)-1LL )
    v21 = 0;
  if ( !SetEndOfFile(v21) )
    goto LABEL_21;
  v22 = (void *)*((_QWORD *)this + 14);
  if ( !v22 || v22 == (void *)-1LL )
    v22 = 0;
  if ( !WriteFile(v22, v2, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    goto LABEL_21;
  v23 = (void *)*((_QWORD *)this + 14);
  if ( !v23 || v23 == (void *)-1LL )
    v23 = 0;
  if ( !FlushFileBuffers(v23) )
  {
LABEL_21:
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
    goto LABEL_55;
  }
LABEL_59:
  if ( v9 )
  {
    if ( *(_QWORD *)v3 )
      --*(_QWORD *)(*(_QWORD *)v3 + 24LL);
    if ( P[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v9);
    v25 = 40;
    v26 = P;
    do
    {
      *(_BYTE *)v26 = 0;
      v26 = (PVOID *)((char *)v26 + 1);
      --v25;
    }
    while ( v25 );
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)RootNode);
  if ( v2 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v2);
  }
  return (unsigned int)RootNode;
}

```

## disassembly

```asm
0x140049ab0  push    rbp
0x140049ab2  push    rsi
0x140049ab3  push    rdi
0x140049ab4  push    r12
0x140049ab6  push    r13
0x140049ab8  push    r14
0x140049aba  push    r15
0x140049abc  mov     rbp, rsp
0x140049abf  sub     rsp, 80h
0x140049ac6  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x140049ace  mov     rsi, rcx
0x140049ad1  xor     r12d, r12d
0x140049ad4  mov     [rbp+lpBuffer], r12
0x140049ad8  mov     [rbp+nNumberOfBytesToWrite], r12
0x140049adc  mov     [rbp+NumberOfBytesWritten], r12d
0x140049ae0  xorps   xmm0, xmm0
0x140049ae3  xor     r13d, r13d
0x140049ae6  movups  xmmword ptr [rbp+P], xmm0
0x140049aea  movups  [rbp+var_20], xmm0
0x140049aee  mov     [rbp+var_10], r13
0x140049af2  mov     r15, [rcx+80h]
0x140049af9  test    r15, r15
0x140049afc  jz      loc_140049DBF
0x140049b02  mov     r14, [r15]
0x140049b05  test    r14, r14
0x140049b08  jz      loc_140049DBF
0x140049b0e  lea     rdx, [rbp+var_40]; struct UnattendNode *
0x140049b12  mov     rcx, r14; this
0x140049b15  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x140049b1a  mov     edi, eax
0x140049b1c  test    eax, eax
0x140049b1e  js      short loc_140049B42
0x140049b20  movaps  xmm0, [rbp+var_40]
0x140049b24  movdqa  [rbp+var_40], xmm0
0x140049b29  lea     r9, [rbp+P]
0x140049b2d  lea     r8, [rbp+var_40]
0x140049b31  mov     rdx, r15
0x140049b34  mov     rcx, r14
0x140049b37  call    ?PopulateNode@@YAJAEAVUnattend@@PEBU_UNATTEND_CONTEXT@@VUnattendNode@@PEAU_UNATTEND_NODE@@@Z; PopulateNode(Unattend &,_UNATTEND_CONTEXT const *,UnattendNode,_UNATTEND_NODE *)
0x140049b3c  mov     edi, eax
0x140049b3e  mov     r13, [rbp+var_10]
0x140049b42  mov     ecx, edi
0x140049b44  test    edi, edi
0x140049b46  js      loc_140049DC6
0x140049b4c  mov     rax, [rsi+80h]
0x140049b53  mov     r15, [rbp+P]
0x140049b57  test    rax, rax
0x140049b5a  jz      short loc_140049B99
0x140049b5c  mov     rcx, [rax]
0x140049b5f  test    rcx, rcx
0x140049b62  jz      short loc_140049B99
0x140049b64  test    r15, r15
0x140049b67  jz      short loc_140049B99
0x140049b69  movups  xmm0, xmmword ptr [r15]
0x140049b6d  movdqu  [rbp+var_40], xmm0
0x140049b72  mov     dword ptr [rsp+80h+lpOverlapped], 1
0x140049b7a  lea     r9, [rbp+nNumberOfBytesToWrite]
0x140049b7e  lea     r8, [rbp+lpBuffer]
0x140049b82  lea     rdx, [rbp+var_40]
0x140049b86  call    ?SerializeToBuffer@Unattend@@QEAAJVUnattendNode@@PEAPEAGPEA_KH@Z; Unattend::SerializeToBuffer(UnattendNode,ushort * *,unsigned __int64 *,int)
0x140049b8b  mov     edi, eax
0x140049b8d  mov     r12, [rbp+lpBuffer]
0x140049b91  test    eax, eax
0x140049b93  jns     loc_140049C28
0x140049b99  test    r12, r12
0x140049b9c  jz      short loc_140049BC5
0x140049b9e  call    cs:__imp_GetProcessHeap
0x140049ba5  nop     dword ptr [rax+rax+00h]
0x140049baa  mov     rcx, rax; hHeap
0x140049bad  mov     r8, r12; lpMem
0x140049bb0  xor     edx, edx; dwFlags
0x140049bb2  call    cs:__imp_HeapFree
0x140049bb9  nop     dword ptr [rax+rax+00h]
0x140049bbe  xor     r12d, r12d
0x140049bc1  mov     [rbp+lpBuffer], r12
0x140049bc5  mov     r14, [rsi+80h]
0x140049bcc  test    r14, r14
0x140049bcf  jz      loc_140049DB1
0x140049bd5  mov     r14, [r14]
0x140049bd8  test    r14, r14
0x140049bdb  jz      loc_140049DB1
0x140049be1  lea     rdx, [rbp+var_40]; struct UnattendNode *
0x140049be5  mov     rcx, r14; this
0x140049be8  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x140049bed  mov     edi, eax
0x140049bef  test    eax, eax
0x140049bf1  js      short loc_140049C1E
0x140049bf3  movaps  xmm0, [rbp+var_40]
0x140049bf7  movdqa  [rbp+var_40], xmm0
0x140049bfc  mov     dword ptr [rsp+80h+lpOverlapped], 0
0x140049c04  lea     r9, [rbp+nNumberOfBytesToWrite]
0x140049c08  lea     r8, [rbp+lpBuffer]
0x140049c0c  lea     rdx, [rbp+var_40]
0x140049c10  mov     rcx, r14
0x140049c13  call    ?SerializeToBuffer@Unattend@@QEAAJVUnattendNode@@PEAPEAGPEA_KH@Z; Unattend::SerializeToBuffer(UnattendNode,ushort * *,unsigned __int64 *,int)
0x140049c18  mov     edi, eax
0x140049c1a  mov     r12, [rbp+lpBuffer]
0x140049c1e  mov     ecx, edi
0x140049c20  test    edi, edi
0x140049c22  js      loc_140049DB8
0x140049c28  mov     rcx, [rsi+68h]
0x140049c2c  test    rcx, rcx
0x140049c2f  jz      short loc_140049C37
0x140049c31  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049c35  jnz     short loc_140049C39
0x140049c37  xor     ecx, ecx; hFile
0x140049c39  xor     r9d, r9d; dwMoveMethod
0x140049c3c  xor     r8d, r8d; lpNewFilePointer
0x140049c3f  xor     edx, edx; liDistanceToMove
0x140049c41  call    cs:__imp_SetFilePointerEx
0x140049c48  nop     dword ptr [rax+rax+00h]
0x140049c4d  test    eax, eax
0x140049c4f  jnz     short loc_140049C81
0x140049c51  call    cs:__imp_GetLastError
0x140049c58  nop     dword ptr [rax+rax+00h]
0x140049c5d  test    eax, eax
0x140049c5f  mov     edi, eax
0x140049c61  jnz     short loc_140049C6D
0x140049c63  mov     edi, 80004005h
0x140049c68  jmp     loc_140049DB6
0x140049c6d  jle     loc_140049DB6
0x140049c73  movzx   edi, ax
0x140049c76  or      edi, 80070000h
0x140049c7c  jmp     loc_140049DB6
0x140049c81  mov     rcx, [rsi+68h]
0x140049c85  test    rcx, rcx
0x140049c88  jz      short loc_140049C90
0x140049c8a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049c8e  jnz     short loc_140049C92
0x140049c90  xor     ecx, ecx; hFile
0x140049c92  call    cs:__imp_SetEndOfFile
0x140049c99  nop     dword ptr [rax+rax+00h]
0x140049c9e  test    eax, eax
0x140049ca0  jz      short loc_140049C51
0x140049ca2  mov     rcx, [rsi+68h]
0x140049ca6  test    rcx, rcx
0x140049ca9  jz      short loc_140049CB1
0x140049cab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049caf  jnz     short loc_140049CB3
0x140049cb1  xor     ecx, ecx; hFile
0x140049cb3  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x140049cbc  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140049cc0  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140049cc4  mov     rdx, r12; lpBuffer
0x140049cc7  call    cs:__imp_WriteFile
0x140049cce  nop     dword ptr [rax+rax+00h]
0x140049cd3  test    eax, eax
0x140049cd5  jz      loc_140049C51
0x140049cdb  mov     rcx, [rsi+68h]
0x140049cdf  test    rcx, rcx
0x140049ce2  jz      short loc_140049CEA
0x140049ce4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049ce8  jnz     short loc_140049CEC
0x140049cea  xor     ecx, ecx; hFile
0x140049cec  call    cs:__imp_FlushFileBuffers
0x140049cf3  nop     dword ptr [rax+rax+00h]
0x140049cf8  test    eax, eax
0x140049cfa  jz      loc_140049C51
0x140049d00  mov     rcx, [rsi+70h]
0x140049d04  test    rcx, rcx
0x140049d07  jz      short loc_140049D0F
0x140049d09  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049d0d  jnz     short loc_140049D11
0x140049d0f  xor     ecx, ecx; hFile
0x140049d11  xor     r9d, r9d; dwMoveMethod
0x140049d14  xor     r8d, r8d; lpNewFilePointer
0x140049d17  xor     edx, edx; liDistanceToMove
0x140049d19  call    cs:__imp_SetFilePointerEx
0x140049d20  nop     dword ptr [rax+rax+00h]
0x140049d25  test    eax, eax
0x140049d27  jz      loc_140049C51
0x140049d2d  mov     rcx, [rsi+70h]
0x140049d31  test    rcx, rcx
0x140049d34  jz      short loc_140049D3C
0x140049d36  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049d3a  jnz     short loc_140049D3E
0x140049d3c  xor     ecx, ecx; hFile
0x140049d3e  call    cs:__imp_SetEndOfFile
0x140049d45  nop     dword ptr [rax+rax+00h]
0x140049d4a  test    eax, eax
0x140049d4c  jz      loc_140049C51
0x140049d52  mov     rcx, [rsi+70h]
0x140049d56  test    rcx, rcx
0x140049d59  jz      short loc_140049D61
0x140049d5b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049d5f  jnz     short loc_140049D63
0x140049d61  xor     ecx, ecx; hFile
0x140049d63  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x140049d6c  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140049d70  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140049d74  mov     rdx, r12; lpBuffer
0x140049d77  call    cs:__imp_WriteFile
0x140049d7e  nop     dword ptr [rax+rax+00h]
0x140049d83  test    eax, eax
0x140049d85  jz      loc_140049C51
0x140049d8b  mov     rcx, [rsi+70h]
0x140049d8f  test    rcx, rcx
0x140049d92  jz      short loc_140049D9A
0x140049d94  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049d98  jnz     short loc_140049D9C
0x140049d9a  xor     ecx, ecx; hFile
0x140049d9c  call    cs:__imp_FlushFileBuffers
0x140049da3  nop     dword ptr [rax+rax+00h]
0x140049da8  test    eax, eax
0x140049daa  jnz     short loc_140049DCF
0x140049dac  jmp     loc_140049C51
0x140049db1  mov     edi, 80070057h
0x140049db6  mov     ecx, edi
0x140049db8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140049dbd  jmp     short loc_140049DCF
0x140049dbf  mov     edi, 80070057h
0x140049dc4  mov     ecx, edi
0x140049dc6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140049dcb  mov     r15, [rbp+P]
0x140049dcf  test    r15, r15
0x140049dd2  jz      short loc_140049E3A
0x140049dd4  mov     rax, [r13+0]
0x140049dd8  test    rax, rax
0x140049ddb  jz      short loc_140049DE1
0x140049ddd  dec     qword ptr [rax+18h]
0x140049de1  mov     r8, [rbp+P+8]; P
0x140049de5  test    r8, r8
0x140049de8  jz      short loc_140049E05
0x140049dea  mov     rcx, gs:60h
0x140049df3  xor     edx, edx; Flags
0x140049df5  mov     rcx, [rcx+30h]; HeapHandle
0x140049df9  call    cs:__imp_RtlFreeHeap
0x140049e00  nop     dword ptr [rax+rax+00h]
0x140049e05  call    cs:__imp_GetProcessHeap
0x140049e0c  nop     dword ptr [rax+rax+00h]
0x140049e11  mov     rcx, rax; hHeap
0x140049e14  mov     r8, r15; lpMem
0x140049e17  xor     edx, edx; dwFlags
0x140049e19  call    cs:__imp_HeapFree
0x140049e20  nop     dword ptr [rax+rax+00h]
0x140049e25  mov     ecx, 28h ; '('
0x140049e2a  lea     rax, [rbp+P]
0x140049e2e  mov     byte ptr [rax], 0
0x140049e31  inc     rax
0x140049e34  sub     rcx, 1
0x140049e38  jnz     short loc_140049E2E
0x140049e3a  mov     ecx, edi
0x140049e3c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140049e41  nop
0x140049e42  test    r12, r12
0x140049e45  jz      short loc_140049E68
0x140049e47  call    cs:__imp_GetProcessHeap
0x140049e4e  nop     dword ptr [rax+rax+00h]
0x140049e53  mov     rcx, rax; hHeap
0x140049e56  mov     r8, r12; lpMem
0x140049e59  xor     edx, edx; dwFlags
0x140049e5b  call    cs:__imp_HeapFree
0x140049e62  nop     dword ptr [rax+rax+00h]
0x140049e67  nop
0x140049e68  mov     eax, edi
0x140049e6a  add     rsp, 80h
0x140049e71  pop     r15
0x140049e73  pop     r14
0x140049e75  pop     r13
0x140049e77  pop     r12
0x140049e79  pop     rdi
0x140049e7a  pop     rsi
0x140049e7b  pop     rbp
0x140049e7c  retn
```
