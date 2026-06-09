# CmDebuggerApi::StartActivity(void *,ulong,void * *)

- ea: `0x18000a660`
- end: `0x18000a989`
- name: `?StartActivity@CmDebuggerApi@@UEAAJPEAXKPEAPEAX@Z`
- size: `809`
- prototype: `int(CmDebuggerApi *__hidden this, void *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x1800048a0`
- `0x180004ef8`
- `0x1800066e4`
- `0x18000672c`
- `0x18000700c`
- `0x180007044`
- `0x180007100`
- `0x180007490`
- `0x180009270`
- `0x1800095a0`
- `0x18000a660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a812`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a812`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a6ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a702`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a744`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a84b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a744`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a84b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8bc`

## string_xrefs

- `0x18000a8dd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a8f3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a909`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a91f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a935`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a94b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a961`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a977`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a68f`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`

## pseudocode

```c
__int64 __fastcall CmDebuggerApi::StartActivity(CmDebuggerApi *this, __int64 a2, DWORD a3, void **a4)
{
  int v7; // eax
  wil::details *v8; // rcx
  HANDLE Event; // rdi
  DWORD LastError; // esi
  const char *v11; // r9
  int v12; // eax
  unsigned int started; // ebx
  const char *v14; // r9
  int LastErrorFailHr; // eax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  const char *v19; // r9
  DWORD v20; // eax
  const char *v21; // r9
  const char *v22; // r9
  HANDLE v23; // rcx
  const char *v24; // r9
  int v26; // eax
  const char *v27; // r9
  void *v28; // [rsp+20h] [rbp-28h] BYREF
  HANDLE hObject[2]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v7 = CmsRegisterForContainerNotifications(
         a2,
         utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::_CallDeleter,
         0);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)(unsigned int)v7,
      (int)v28);
  v28 = 0;
  *(_OWORD *)hObject = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    if ( hObject[1] )
    {
      LastError = GetLastError();
      if ( !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v11);
      SetLastError(LastError);
    }
    hObject[1] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
    started = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        (int)v28);
      if ( hObject[1] && !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v16);
      return started;
    }
  }
  v12 = CmsCreateActivity(a2, 12000, &v28);
  started = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)(unsigned int)v12,
      (int)v28);
    if ( hObject[1] )
    {
      if ( !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v14);
    }
    return started;
  }
  v17 = v28;
  started = CmsStartActivityAsync(v28, ActivityNotificationCallback, hObject);
  if ( (started & 0x80000000) != 0 )
  {
    v18 = CmsCloseActivity(&v28);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)(unsigned int)v18,
        (int)v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)started,
      (int)v28);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v19);
    return started;
  }
  v20 = WaitForSingleObjectEx(hObject[1], a3, 0);
  if ( v20 == 258 )
  {
    v26 = CmsCloseActivity(&v28);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)(unsigned int)v26,
        (int)v28);
    started = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xE7,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
                (const char *)0x5B4,
                (unsigned int)v28);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v27);
    return started;
  }
  if ( v20 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  started = (unsigned int)hObject[0];
  if ( SLODWORD(hObject[0]) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)LODWORD(hObject[0]),
      (int)v28);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    return started;
  }
  v23 = hObject[1];
  *a4 = v17;
  if ( v23 && !CloseHandle(v23) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v24);
  return 0;
}

```

## disassembly

```asm
0x18000a660  push    rbp
0x18000a662  push    rbx
0x18000a663  push    rsi
0x18000a664  push    rdi
0x18000a665  push    r12
0x18000a667  push    r13
0x18000a669  push    r14
0x18000a66b  push    r15
0x18000a66d  mov     rbp, rsp
0x18000a670  sub     rsp, 48h
0x18000a674  mov     r14, rdx
0x18000a677  mov     r12d, r8d
0x18000a67a  mov     rcx, r14
0x18000a67d  lea     rdx, ?_CallDeleter@?$_RefCountVtable@V?$_RefCountStored@UNotificationDeliveryThreadState@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::_CallDeleter(void)
0x18000a684  xor     r8d, r8d
0x18000a687  mov     r15, r9
0x18000a68a  call    CmsRegisterForContainerNotifications
0x18000a68f  lea     r13, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a696  test    eax, eax
0x18000a698  jns     short loc_18000A6AE
0x18000a69a  mov     rcx, [rbp+40h]; this
0x18000a69e  mov     r9d, eax; char *
0x18000a6a1  mov     r8, r13; unsigned int
0x18000a6a4  mov     edx, 0CEh; void *
0x18000a6a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a6ae  xorps   xmm0, xmm0
0x18000a6b1  mov     [rbp+var_28], 0
0x18000a6b9  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a6bf  xor     r8d, r8d; dwFlags
0x18000a6c2  xor     edx, edx; lpName
0x18000a6c4  xor     ecx, ecx; lpEventAttributes
0x18000a6c6  movups  xmmword ptr [rbp+hObject], xmm0
0x18000a6ca  call    cs:__imp_CreateEventExW
0x18000a6d0  mov     rdi, rax
0x18000a6d3  test    rax, rax
0x18000a6d6  jz      short loc_18000A757
0x18000a6d8  call    cs:__imp_GetLastError
0x18000a6de  mov     rbx, [rbp+hObject+8]
0x18000a6e2  test    rbx, rbx
0x18000a6e5  jz      short loc_18000A708
0x18000a6e7  call    cs:__imp_GetLastError
0x18000a6ed  mov     rcx, rbx; hObject
0x18000a6f0  mov     esi, eax
0x18000a6f2  call    cs:__imp_CloseHandle
0x18000a6f8  test    eax, eax
0x18000a6fa  jz      loc_18000A947
0x18000a700  mov     ecx, esi; dwErrCode
0x18000a702  call    cs:__imp_SetLastError
0x18000a708  mov     [rbp+hObject+8], rdi
0x18000a70c  lea     r8, [rbp+var_28]
0x18000a710  mov     edx, 2EE0h
0x18000a715  mov     rcx, r14
0x18000a718  call    CmsCreateActivity
0x18000a71d  mov     ebx, eax
0x18000a71f  test    eax, eax
0x18000a721  jns     short loc_18000A796
0x18000a723  mov     rcx, [rbp+40h]; this
0x18000a727  mov     r9d, eax; char *
0x18000a72a  mov     r8, r13; unsigned int
0x18000a72d  mov     edx, 0D7h; void *
0x18000a732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a737  mov     rcx, [rbp+hObject+8]; hObject
0x18000a73b  test    rcx, rcx
0x18000a73e  jz      loc_18000A8C6
0x18000a744  call    cs:__imp_CloseHandle
0x18000a74a  test    eax, eax
0x18000a74c  jz      loc_18000A8EF
0x18000a752  jmp     loc_18000A8C6
0x18000a757  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a75c  mov     ebx, eax
0x18000a75e  test    eax, eax
0x18000a760  jns     short loc_18000A70C
0x18000a762  mov     rcx, [rbp+40h]; this
0x18000a766  mov     r9d, eax; char *
0x18000a769  mov     r8, r13; unsigned int
0x18000a76c  mov     edx, 0D3h; void *
0x18000a771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a776  mov     rcx, [rbp+hObject+8]; hObject
0x18000a77a  test    rcx, rcx
0x18000a77d  jz      loc_18000A8C6
0x18000a783  call    cs:__imp_CloseHandle
0x18000a789  test    eax, eax
0x18000a78b  jz      loc_18000A905
0x18000a791  jmp     loc_18000A8C6
0x18000a796  mov     rdi, [rbp+var_28]
0x18000a79a  lea     r8, [rbp+hObject]
0x18000a79e  mov     rcx, rdi
0x18000a7a1  lea     rdx, ActivityNotificationCallback
0x18000a7a8  call    CmsStartActivityAsync
0x18000a7ad  mov     ebx, eax
0x18000a7af  test    eax, eax
0x18000a7b1  jns     short loc_18000A808
0x18000a7b3  lea     rcx, [rbp+var_28]
0x18000a7b7  call    CmsCloseActivity
0x18000a7bc  test    eax, eax
0x18000a7be  jns     short loc_18000A7D4
0x18000a7c0  mov     rcx, [rbp+40h]; this
0x18000a7c4  mov     r9d, eax; char *
0x18000a7c7  mov     r8, r13; unsigned int
0x18000a7ca  mov     edx, 0DFh; void *
0x18000a7cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a7d4  mov     rcx, [rbp+40h]; this
0x18000a7d8  mov     r9d, ebx; char *
0x18000a7db  mov     r8, r13; unsigned int
0x18000a7de  mov     edx, 0E0h; void *
0x18000a7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7e8  mov     rcx, [rbp+hObject+8]; hObject
0x18000a7ec  test    rcx, rcx
0x18000a7ef  jz      loc_18000A8C6
0x18000a7f5  call    cs:__imp_CloseHandle
0x18000a7fb  test    eax, eax
0x18000a7fd  jz      loc_18000A91B
0x18000a803  jmp     loc_18000A8C6
0x18000a808  mov     rcx, [rbp+hObject+8]; hHandle
0x18000a80c  xor     r8d, r8d; bAlertable
0x18000a80f  mov     edx, r12d; dwMilliseconds
0x18000a812  call    cs:__imp_WaitForSingleObjectEx
0x18000a818  cmp     eax, 102h
0x18000a81d  jz      short loc_18000A879
0x18000a81f  test    eax, eax
0x18000a821  jnz     loc_18000A95D
0x18000a827  mov     ebx, dword ptr [rbp+hObject]
0x18000a82a  test    ebx, ebx
0x18000a82c  jns     short loc_18000A85B
0x18000a82e  mov     rcx, [rbp+40h]; this
0x18000a832  mov     r9d, ebx; char *
0x18000a835  mov     r8, r13; unsigned int
0x18000a838  mov     edx, 0EAh; void *
0x18000a83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a842  mov     rcx, [rbp+hObject+8]; hObject
0x18000a846  test    rcx, rcx
0x18000a849  jz      short loc_18000A8C6
0x18000a84b  call    cs:__imp_CloseHandle
0x18000a851  test    eax, eax
0x18000a853  jz      loc_18000A931
0x18000a859  jmp     short loc_18000A8C6
0x18000a85b  mov     rcx, [rbp+hObject+8]; hObject
0x18000a85f  mov     [r15], rdi
0x18000a862  test    rcx, rcx
0x18000a865  jz      short loc_18000A875
0x18000a867  call    cs:__imp_CloseHandle
0x18000a86d  test    eax, eax
0x18000a86f  jz      loc_18000A973
0x18000a875  xor     eax, eax
0x18000a877  jmp     short loc_18000A8C8
0x18000a879  lea     rcx, [rbp+var_28]
0x18000a87d  call    CmsCloseActivity
0x18000a882  test    eax, eax
0x18000a884  jns     short loc_18000A89A
0x18000a886  mov     rcx, [rbp+40h]; this
0x18000a88a  mov     r9d, eax; char *
0x18000a88d  mov     r8, r13; unsigned int
0x18000a890  mov     edx, 0E6h; void *
0x18000a895  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a89a  mov     rcx, [rbp+40h]; this
0x18000a89e  mov     r9d, 5B4h; char *
0x18000a8a4  mov     r8, r13; unsigned int
0x18000a8a7  mov     edx, 0E7h; void *
0x18000a8ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a8b1  mov     rcx, [rbp+hObject+8]; hObject
0x18000a8b5  mov     ebx, eax
0x18000a8b7  test    rcx, rcx
0x18000a8ba  jz      short loc_18000A8C6
0x18000a8bc  call    cs:__imp_CloseHandle
0x18000a8c2  test    eax, eax
0x18000a8c4  jz      short loc_18000A8D9
0x18000a8c6  mov     eax, ebx
0x18000a8c8  add     rsp, 48h
0x18000a8cc  pop     r15
0x18000a8ce  pop     r14
0x18000a8d0  pop     r13
0x18000a8d2  pop     r12
0x18000a8d4  pop     rdi
0x18000a8d5  pop     rsi
0x18000a8d6  pop     rbx
0x18000a8d7  pop     rbp
0x18000a8d8  retn
0x18000a8d9  mov     rcx, [rbp+40h]; this
0x18000a8dd  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a8e4  mov     edx, 0A0Bh; void *
0x18000a8e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a8ef  mov     rcx, [rbp+40h]; this
0x18000a8f3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a8fa  mov     edx, 0A0Bh; void *
0x18000a8ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a905  mov     rcx, [rbp+40h]; this
0x18000a909  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a910  mov     edx, 0A0Bh; void *
0x18000a915  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a91b  mov     rcx, [rbp+40h]; this
0x18000a91f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a926  mov     edx, 0A0Bh; void *
0x18000a92b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a931  mov     rcx, [rbp+40h]; this
0x18000a935  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a93c  mov     edx, 0A0Bh; void *
0x18000a941  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a947  mov     rcx, [rbp+40h]; this
0x18000a94b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a952  mov     edx, 0A0Bh; void *
0x18000a957  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a95d  mov     rcx, [rbp+40h]; this
0x18000a961  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a968  mov     edx, 0B0Fh; void *
0x18000a96d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a973  mov     rcx, [rbp+40h]; this
0x18000a977  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a97e  mov     edx, 0A0Bh; void *
0x18000a983  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
