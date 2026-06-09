# SipcClient::Create(_GUID const &,SIPC_SERVICE_BOUNDARY,uchar,uchar,void *,ISIPCClient * *)

- ea: `0x180026848`
- end: `0x180026a43`
- name: `?Create@SipcClient@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@EEPEAXPEAPEAUISIPCClient@@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180026848`
- `0x180029a74`
- `0x18002aca0`
- `0x18004c881`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180026950`
- `ntdll!RtlAllocateHeap` at `0x180026950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026903`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800268f3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800268f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026890`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026890`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800268b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800268b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268d3`

## pseudocode

```c
__int64 __fastcall SipcClient::Create(__int64 a1, __int64 a2, __int64 a3, char a4, PSID pSid, _QWORD *a6)
{
  void *v7; // rbx
  DWORD LengthSid; // eax
  DWORD v9; // esi
  HLOCAL v11; // rax
  signed int LastError; // eax
  unsigned int v13; // edi
  char *Heap; // rax
  char *v15; // rdi
  int v16; // ebx

  *a6 = 0;
  if ( !memcmp_0(&GameInputClient::c_serviceGuid, qword_1800554E8, 0x10u) || pSid && !IsValidSid(pSid) )
    return 2147942487LL;
  v7 = 0;
  if ( !pSid )
    goto LABEL_14;
  LengthSid = GetLengthSid(pSid);
  v9 = LengthSid;
  if ( !LengthSid )
    return 2147549183LL;
  v11 = LocalAlloc(0, LengthSid);
  v7 = v11;
  if ( !v11 )
    return 2147942414LL;
  if ( CopySid(v9, v11, pSid) )
  {
LABEL_14:
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
    v15 = Heap;
    if ( Heap )
    {
      *(_QWORD *)Heap = &SipcObjectBase<ISIPCClient>::`vftable';
      *((_QWORD *)Heap + 1) = 2;
      *((_QWORD *)Heap + 2) = &SipcEndpointOwner::`vftable';
      *((_DWORD *)Heap + 10) = 1;
      Heap[44] = 5;
      *(GUID *)(Heap + 24) = GameInputClient::c_serviceGuid;
      *((_QWORD *)Heap + 6) = v7;
      Heap[45] = a4;
      *(_QWORD *)Heap = &SipcClient::`vftable'{for `SipcObjectBase<ISIPCClient>'};
      *((_QWORD *)Heap + 2) = &SipcClient::`vftable'{for `SipcEndpointOwner'};
      *((_DWORD *)Heap + 24) = 0;
      *((_QWORD *)Heap + 11) = Heap + 80;
      *((_QWORD *)Heap + 10) = Heap + 80;
      *((_DWORD *)Heap + 30) = 0;
      *((_QWORD *)Heap + 14) = Heap + 104;
      *((_QWORD *)Heap + 13) = Heap + 104;
      *((_QWORD *)Heap + 7) = 0;
      *((_QWORD *)Heap + 8) = 0;
      *((_QWORD *)Heap + 9) = 0;
      v16 = AggregateWaitHandle::Initialize((AggregateWaitHandle *)(Heap + 56));
      if ( v16 < 0 )
      {
        SipcObjectBase<ISIPCClient>::Release(v15);
        return (unsigned int)v16;
      }
      else
      {
        *a6 = v15;
        return 0;
      }
    }
    if ( v7 )
      LocalFree(v7);
    return 2147942414LL;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v13 = -2147418113;
  if ( LastError < 0 )
    v13 = LastError;
  LocalFree(v7);
  return v13;
}

```

## disassembly

```asm
0x180026848  push    rbx
0x18002684a  push    rbp
0x18002684b  push    rsi
0x18002684c  push    rdi
0x18002684d  push    r14
0x18002684f  sub     rsp, 20h
0x180026853  mov     r14, [rsp+48h+arg_28]
0x180026858  lea     rdx, qword_1800554E8; Buf2
0x18002685f  mov     r8d, 10h; Size
0x180026865  lea     rcx, ?c_serviceGuid@GameInputClient@@0U_GUID@@B; Buf1
0x18002686c  mov     bpl, r9b
0x18002686f  mov     qword ptr [r14], 0
0x180026876  call    memcmp_0
0x18002687b  test    eax, eax
0x18002687d  jz      loc_180026A32
0x180026883  mov     rdi, [rsp+48h+pSid]
0x180026888  test    rdi, rdi
0x18002688b  jz      short loc_1800268A4
0x18002688d  mov     rcx, rdi; pSid
0x180026890  call    cs:__imp_IsValidSid
0x180026897  nop     dword ptr [rax+rax+00h]
0x18002689c  test    eax, eax
0x18002689e  jz      loc_180026A32
0x1800268a4  xor     ebx, ebx
0x1800268a6  test    rdi, rdi
0x1800268a9  jz      loc_18002693B
0x1800268af  mov     rcx, rdi; pSid
0x1800268b2  call    cs:__imp_GetLengthSid
0x1800268b9  nop     dword ptr [rax+rax+00h]
0x1800268be  mov     esi, eax
0x1800268c0  test    eax, eax
0x1800268c2  jnz     short loc_1800268CE
0x1800268c4  mov     eax, 8000FFFFh
0x1800268c9  jmp     loc_180026A37
0x1800268ce  mov     rdx, rsi; uBytes
0x1800268d1  xor     ecx, ecx; uFlags
0x1800268d3  call    cs:__imp_LocalAlloc
0x1800268da  nop     dword ptr [rax+rax+00h]
0x1800268df  mov     rbx, rax
0x1800268e2  test    rax, rax
0x1800268e5  jz      loc_180026A2B
0x1800268eb  mov     r8, rdi; pSourceSid
0x1800268ee  mov     rdx, rax; pDestinationSid
0x1800268f1  mov     ecx, esi; nDestinationSidLength
0x1800268f3  call    cs:__imp_CopySid
0x1800268fa  nop     dword ptr [rax+rax+00h]
0x1800268ff  test    eax, eax
0x180026901  jnz     short loc_18002693B
0x180026903  call    cs:__imp_GetLastError
0x18002690a  nop     dword ptr [rax+rax+00h]
0x18002690f  test    eax, eax
0x180026911  jle     short loc_18002691B
0x180026913  movzx   eax, ax
0x180026916  or      eax, 80070000h
0x18002691b  test    eax, eax
0x18002691d  mov     edi, 8000FFFFh
0x180026922  mov     rcx, rbx; hMem
0x180026925  cmovs   edi, eax
0x180026928  call    cs:__imp_LocalFree
0x18002692f  nop     dword ptr [rax+rax+00h]
0x180026934  mov     eax, edi
0x180026936  jmp     loc_180026A37
0x18002693b  mov     rcx, gs:60h
0x180026944  xor     edx, edx; Flags
0x180026946  mov     r8d, 80h; Size
0x18002694c  mov     rcx, [rcx+30h]; HeapHandle
0x180026950  call    cs:__imp_RtlAllocateHeap
0x180026957  nop     dword ptr [rax+rax+00h]
0x18002695c  mov     rdi, rax
0x18002695f  test    rax, rax
0x180026962  jz      loc_180026A17
0x180026968  lea     rax, ??_7?$SipcObjectBase@UISIPCClient@@@@6B@; const SipcObjectBase<ISIPCClient>::`vftable'
0x18002696f  mov     [rdi], rax
0x180026972  lea     rcx, [rdi+38h]; this
0x180026976  mov     qword ptr [rdi+8], 2
0x18002697e  lea     rax, ??_7SipcEndpointOwner@@6B@; const SipcEndpointOwner::`vftable'
0x180026985  mov     [rdi+10h], rax
0x180026989  lea     rax, ??_7SipcClient@@6B?$SipcObjectBase@UISIPCClient@@@@@; const SipcClient::`vftable'{for `SipcObjectBase<ISIPCClient>'}
0x180026990  movups  xmm0, xmmword ptr cs:?c_serviceGuid@GameInputClient@@0U_GUID@@B.Data1; _GUID const GameInputClient::c_serviceGuid ...
0x180026997  mov     dword ptr [rdi+28h], 1
0x18002699e  mov     byte ptr [rdi+2Ch], 5
0x1800269a2  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800269a7  mov     [rdi+30h], rbx
0x1800269ab  mov     [rdi+2Dh], bpl
0x1800269af  mov     [rdi], rax
0x1800269b2  lea     rax, ??_7SipcClient@@6BSipcEndpointOwner@@@; const SipcClient::`vftable'{for `SipcEndpointOwner'}
0x1800269b9  mov     [rdi+10h], rax
0x1800269bd  lea     rax, [rdi+50h]
0x1800269c1  mov     dword ptr [rax+10h], 0
0x1800269c8  mov     [rax+8], rax
0x1800269cc  mov     [rax], rax
0x1800269cf  lea     rax, [rdi+68h]
0x1800269d3  mov     dword ptr [rax+10h], 0
0x1800269da  mov     [rax+8], rax
0x1800269de  mov     [rax], rax
0x1800269e1  mov     qword ptr [rdi+38h], 0
0x1800269e9  mov     qword ptr [rdi+40h], 0
0x1800269f1  mov     qword ptr [rdi+48h], 0
0x1800269f9  call    ?Initialize@AggregateWaitHandle@@QEAAJXZ; AggregateWaitHandle::Initialize(void)
0x1800269fe  mov     ebx, eax
0x180026a00  test    eax, eax
0x180026a02  js      short loc_180026A0B
0x180026a04  mov     [r14], rdi
0x180026a07  xor     eax, eax
0x180026a09  jmp     short loc_180026A37
0x180026a0b  mov     rcx, rdi
0x180026a0e  call    ?Release@?$SipcObjectBase@UISIPCClient@@@@UEAAKXZ; SipcObjectBase<ISIPCClient>::Release(void)
0x180026a13  mov     eax, ebx
0x180026a15  jmp     short loc_180026A37
0x180026a17  test    rbx, rbx
0x180026a1a  jz      short loc_180026A2B
0x180026a1c  mov     rcx, rbx; hMem
0x180026a1f  call    cs:__imp_LocalFree
0x180026a26  nop     dword ptr [rax+rax+00h]
0x180026a2b  mov     eax, 8007000Eh
0x180026a30  jmp     short loc_180026A37
0x180026a32  mov     eax, 80070057h
0x180026a37  add     rsp, 20h
0x180026a3b  pop     r14
0x180026a3d  pop     rdi
0x180026a3e  pop     rsi
0x180026a3f  pop     rbp
0x180026a40  pop     rbx
0x180026a41  retn
```
