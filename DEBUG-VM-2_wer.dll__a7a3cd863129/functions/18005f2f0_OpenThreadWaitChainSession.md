# OpenThreadWaitChainSession

- ea: `0x18005f2f0`
- end: `0x18005f462`
- name: `OpenThreadWaitChainSession`
- size: `370`
- prototype: `HWCT __stdcall(DWORD Flags, PWAITCHAINCALLBACK callback)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004bb4`
- `0x180007e34`
- `0x18001fe24`
- `0x18004ecf8`
- `0x18005c7b4`
- `0x18005c868`
- `0x18005ec3c`
- `0x18005f2f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f369`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f404`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f3cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f3cf`

## pseudocode

```c
HWCT __stdcall OpenThreadWaitChainSession(DWORD Flags, PWAITCHAINCALLBACK callback)
{
  DWORD LastError; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  HANDLE EventW; // rax
  __int64 v8; // rcx
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( (Flags & 0xFFFFFFFE) != 0 || (Flags & 1) != 0 && !callback )
  {
    LastError = 87;
LABEL_18:
    SetLastError(LastError);
    v6 = 0;
    goto LABEL_20;
  }
  if ( !(unsigned int)WctInitPackage() )
  {
    LastError = 1359;
    goto LABEL_18;
  }
  v5 = HeapAlloc(g_hWerheap, 0, 0x30u);
  v6 = v5;
  if ( v5 )
  {
    v5[3] = 0;
    *(_OWORD *)v5 = 0;
    v5[2] = 0;
    v5[4] = 0;
    v5[5] = 0;
  }
  else
  {
    v6 = 0;
  }
  v10 = 0;
  utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(&v10);
  if ( !v6 )
  {
    LastError = 8;
    goto LABEL_18;
  }
  *((_DWORD *)v6 + 6) = Flags;
  v6[4] = callback;
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(v6 + 5, EventW);
  if ( v6[5] != -1 && v6[5] != 0 )
  {
    LastError = 0;
    WctAddEntry((struct WCT_ENTRY *)v6);
    goto LABEL_20;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    utl::default_delete<WCT_ENTRY>::operator()(v8, v6);
    goto LABEL_18;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  v10 = 0;
  utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(&v10);
  return v6;
}

```

## disassembly

```asm
0x18005f2f0  push    rbx
0x18005f2f2  push    rsi
0x18005f2f3  push    rdi
0x18005f2f4  push    r14
0x18005f2f6  sub     rsp, 28h
0x18005f2fa  mov     rsi, rdx
0x18005f2fd  mov     ebx, ecx
0x18005f2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f306  lea     r14, WPP_GLOBAL_Control
0x18005f30d  cmp     rcx, r14
0x18005f310  jz      short loc_18005F32D
0x18005f312  test    byte ptr [rcx+1Ch], 4
0x18005f316  jz      short loc_18005F32D
0x18005f318  mov     rcx, [rcx+10h]
0x18005f31c  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f323  mov     edx, 3Dh ; '='
0x18005f328  call    WPP_SF_
0x18005f32d  test    ebx, 0FFFFFFFEh
0x18005f333  jz      short loc_18005F33F
0x18005f335  mov     ebx, 57h ; 'W'
0x18005f33a  jmp     loc_18005F402
0x18005f33f  test    bl, 1
0x18005f342  jz      short loc_18005F349
0x18005f344  test    rsi, rsi
0x18005f347  jz      short loc_18005F335
0x18005f349  call    ?WctInitPackage@@YAHXZ; WctInitPackage(void)
0x18005f34e  test    eax, eax
0x18005f350  jnz     short loc_18005F35C
0x18005f352  mov     ebx, 54Fh
0x18005f357  jmp     loc_18005F402
0x18005f35c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005f363  xor     edx, edx; dwFlags
0x18005f365  lea     r8d, [rdx+30h]; dwBytes
0x18005f369  call    cs:__imp_HeapAlloc
0x18005f36f  mov     rdi, rax
0x18005f372  test    rax, rax
0x18005f375  jz      short loc_18005F39F
0x18005f377  mov     qword ptr [rax+18h], 0
0x18005f37f  xorps   xmm0, xmm0
0x18005f382  movups  xmmword ptr [rax], xmm0
0x18005f385  mov     qword ptr [rax+10h], 0
0x18005f38d  mov     qword ptr [rax+20h], 0
0x18005f395  mov     qword ptr [rax+28h], 0
0x18005f39d  jmp     short loc_18005F3A1
0x18005f39f  xor     edi, edi
0x18005f3a1  lea     rcx, [rsp+48h+arg_10]
0x18005f3a6  mov     [rsp+48h+arg_10], 0
0x18005f3af  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x18005f3b4  test    rdi, rdi
0x18005f3b7  jnz     short loc_18005F3BE
0x18005f3b9  lea     ebx, [rdi+8]
0x18005f3bc  jmp     short loc_18005F402
0x18005f3be  mov     [rdi+18h], ebx
0x18005f3c1  xor     r9d, r9d; lpName
0x18005f3c4  xor     r8d, r8d; bInitialState
0x18005f3c7  mov     [rdi+20h], rsi
0x18005f3cb  xor     edx, edx; bManualReset
0x18005f3cd  xor     ecx, ecx; lpEventAttributes
0x18005f3cf  call    cs:__imp_CreateEventW
0x18005f3d5  mov     rdx, rax
0x18005f3d8  lea     rcx, [rdi+28h]
0x18005f3dc  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f3e1  mov     rax, [rdi+28h]
0x18005f3e5  inc     rax
0x18005f3e8  cmp     rax, 1
0x18005f3ec  ja      short loc_18005F40E
0x18005f3ee  call    cs:__imp_GetLastError
0x18005f3f4  mov     ebx, eax
0x18005f3f6  test    eax, eax
0x18005f3f8  jz      short loc_18005F418
0x18005f3fa  mov     rdx, rdi
0x18005f3fd  call    ??R?$default_delete@UWCT_ENTRY@@@utl@@QEBAXPEAUWCT_ENTRY@@@Z; utl::default_delete<WCT_ENTRY>::operator()(WCT_ENTRY *)
0x18005f402  mov     ecx, ebx; dwErrCode
0x18005f404  call    cs:__imp_SetLastError
0x18005f40a  xor     edi, edi
0x18005f40c  jmp     short loc_18005F418
0x18005f40e  xor     ebx, ebx
0x18005f410  mov     rcx, rdi; struct WCT_ENTRY *
0x18005f413  call    ?WctAddEntry@@YAXPEAUWCT_ENTRY@@@Z; WctAddEntry(WCT_ENTRY *)
0x18005f418  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f41f  cmp     rcx, r14
0x18005f422  jz      short loc_18005F442
0x18005f424  test    byte ptr [rcx+1Ch], 4
0x18005f428  jz      short loc_18005F442
0x18005f42a  mov     rcx, [rcx+10h]
0x18005f42e  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f435  mov     edx, 3Eh ; '>'
0x18005f43a  mov     r9d, ebx
0x18005f43d  call    WPP_SF_d
0x18005f442  lea     rcx, [rsp+48h+arg_10]
0x18005f447  mov     [rsp+48h+arg_10], 0
0x18005f450  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x18005f455  mov     rax, rdi
0x18005f458  add     rsp, 28h
0x18005f45c  pop     r14
0x18005f45e  pop     rdi
0x18005f45f  pop     rsi
0x18005f460  pop     rbx
0x18005f461  retn
```
