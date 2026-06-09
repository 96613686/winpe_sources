# OpenThreadWaitChainSession

- ea: `0x18005f340`
- end: `0x18005f4b2`
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
- `0x18005ec8c`
- `0x18005f340`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f454`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f43e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f41f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f41f`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_4c32fa7a72a13340317baef891270170_Traceguids, LastError);
  v10 = 0;
  utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(&v10);
  return v6;
}

```

## disassembly

```asm
0x18005f340  push    rbx
0x18005f342  push    rsi
0x18005f343  push    rdi
0x18005f344  push    r14
0x18005f346  sub     rsp, 28h
0x18005f34a  mov     rsi, rdx
0x18005f34d  mov     ebx, ecx
0x18005f34f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f356  lea     r14, WPP_GLOBAL_Control
0x18005f35d  cmp     rcx, r14
0x18005f360  jz      short loc_18005F37D
0x18005f362  test    byte ptr [rcx+1Ch], 4
0x18005f366  jz      short loc_18005F37D
0x18005f368  mov     rcx, [rcx+10h]
0x18005f36c  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005f373  mov     edx, 3Dh ; '='
0x18005f378  call    WPP_SF_
0x18005f37d  test    ebx, 0FFFFFFFEh
0x18005f383  jz      short loc_18005F38F
0x18005f385  mov     ebx, 57h ; 'W'
0x18005f38a  jmp     loc_18005F452
0x18005f38f  test    bl, 1
0x18005f392  jz      short loc_18005F399
0x18005f394  test    rsi, rsi
0x18005f397  jz      short loc_18005F385
0x18005f399  call    ?WctInitPackage@@YAHXZ; WctInitPackage(void)
0x18005f39e  test    eax, eax
0x18005f3a0  jnz     short loc_18005F3AC
0x18005f3a2  mov     ebx, 54Fh
0x18005f3a7  jmp     loc_18005F452
0x18005f3ac  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005f3b3  xor     edx, edx; dwFlags
0x18005f3b5  lea     r8d, [rdx+30h]; dwBytes
0x18005f3b9  call    cs:__imp_HeapAlloc
0x18005f3bf  mov     rdi, rax
0x18005f3c2  test    rax, rax
0x18005f3c5  jz      short loc_18005F3EF
0x18005f3c7  mov     qword ptr [rax+18h], 0
0x18005f3cf  xorps   xmm0, xmm0
0x18005f3d2  movups  xmmword ptr [rax], xmm0
0x18005f3d5  mov     qword ptr [rax+10h], 0
0x18005f3dd  mov     qword ptr [rax+20h], 0
0x18005f3e5  mov     qword ptr [rax+28h], 0
0x18005f3ed  jmp     short loc_18005F3F1
0x18005f3ef  xor     edi, edi
0x18005f3f1  lea     rcx, [rsp+48h+arg_10]
0x18005f3f6  mov     [rsp+48h+arg_10], 0
0x18005f3ff  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x18005f404  test    rdi, rdi
0x18005f407  jnz     short loc_18005F40E
0x18005f409  lea     ebx, [rdi+8]
0x18005f40c  jmp     short loc_18005F452
0x18005f40e  mov     [rdi+18h], ebx
0x18005f411  xor     r9d, r9d; lpName
0x18005f414  xor     r8d, r8d; bInitialState
0x18005f417  mov     [rdi+20h], rsi
0x18005f41b  xor     edx, edx; bManualReset
0x18005f41d  xor     ecx, ecx; lpEventAttributes
0x18005f41f  call    cs:__imp_CreateEventW
0x18005f425  mov     rdx, rax
0x18005f428  lea     rcx, [rdi+28h]
0x18005f42c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f431  mov     rax, [rdi+28h]
0x18005f435  inc     rax
0x18005f438  cmp     rax, 1
0x18005f43c  ja      short loc_18005F45E
0x18005f43e  call    cs:__imp_GetLastError
0x18005f444  mov     ebx, eax
0x18005f446  test    eax, eax
0x18005f448  jz      short loc_18005F468
0x18005f44a  mov     rdx, rdi
0x18005f44d  call    ??R?$default_delete@UWCT_ENTRY@@@utl@@QEBAXPEAUWCT_ENTRY@@@Z; utl::default_delete<WCT_ENTRY>::operator()(WCT_ENTRY *)
0x18005f452  mov     ecx, ebx; dwErrCode
0x18005f454  call    cs:__imp_SetLastError
0x18005f45a  xor     edi, edi
0x18005f45c  jmp     short loc_18005F468
0x18005f45e  xor     ebx, ebx
0x18005f460  mov     rcx, rdi; struct WCT_ENTRY *
0x18005f463  call    ?WctAddEntry@@YAXPEAUWCT_ENTRY@@@Z; WctAddEntry(WCT_ENTRY *)
0x18005f468  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f46f  cmp     rcx, r14
0x18005f472  jz      short loc_18005F492
0x18005f474  test    byte ptr [rcx+1Ch], 4
0x18005f478  jz      short loc_18005F492
0x18005f47a  mov     rcx, [rcx+10h]
0x18005f47e  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005f485  mov     edx, 3Eh ; '>'
0x18005f48a  mov     r9d, ebx
0x18005f48d  call    WPP_SF_d
0x18005f492  lea     rcx, [rsp+48h+arg_10]
0x18005f497  mov     [rsp+48h+arg_10], 0
0x18005f4a0  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x18005f4a5  mov     rax, rdi
0x18005f4a8  add     rsp, 28h
0x18005f4ac  pop     r14
0x18005f4ae  pop     rdi
0x18005f4af  pop     rsi
0x18005f4b0  pop     rbx
0x18005f4b1  retn
```
