# XinputHid::XinputHidInterface::~XinputHidInterface(void)

- ea: `0x18000efec`
- end: `0x18000f19c`
- name: `??1XinputHidInterface@XinputHid@@QEAA@XZ`
- size: `432`
- prototype: `void __fastcall(XinputHid::XinputHidInterface *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000cbe0`
- `0x18000df30`

## callees

- `0x180009260`
- `0x18000ed1c`
- `0x18000ee70`
- `0x18000efec`
- `0x180010ed4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f04a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f0a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f04a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f0a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f00f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f00f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f035`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f035`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f0f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0c0`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000f08a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000f08a`

## pseudocode

```c
void __fastcall XinputHid::XinputHidInterface::~XinputHidInterface(XinputHid::XinputHidInterface *this)
{
  const char *v2; // r9
  __int64 v3; // rdi
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !XinputHid::finalCallbackEvent )
  {
    XinputHid::finalCallbackEvent = CreateEventW(0, 1, 0, 0);
    if ( !XinputHid::finalCallbackEvent )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
        v2);
  }
  v3 = _InterlockedExchange64(&XinputHid::callbackState, 2);
  if ( !SetEvent(*((HANDLE *)this + 5)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v4);
  WaitForSingleObject(*((HANDLE *)this + 4), 0xFFFFFFFF);
  if ( !CloseHandle(*((HANDLE *)this + 4)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v5);
  if ( !CloseHandle(*((HANDLE *)this + 6)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v6);
  if ( !CloseHandle(*((HANDLE *)this + 5)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v7);
  if ( (unsigned int)CM_Unregister_Notification(*((_QWORD *)this + 3)) )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0xE2, v8, (const char *)0x8000FFFFLL, v10);
  if ( v3 == 4 )
    WaitForSingleObject(XinputHid::finalCallbackEvent, 0xFFFFFFFF);
  XinputHid::callbackState = 3;
  if ( !CloseHandle(XinputHid::finalCallbackEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v9);
  XinputHid::finalCallbackEvent = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>((char *)this + 120);
  std::list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>::~list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>((void **)this + 13);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x18000efec  mov     [rsp+arg_0], rbx
0x18000eff1  push    rdi; int
0x18000eff2  sub     rsp, 20h
0x18000eff6  cmp     cs:?finalCallbackEvent@XinputHid@@3PEAXEA, 0; void * XinputHid::finalCallbackEvent
0x18000effe  mov     rbx, rcx
0x18000f001  jnz     short loc_18000F025
0x18000f003  xor     r9d, r9d; lpName
0x18000f006  xor     r8d, r8d; bInitialState
0x18000f009  xor     ecx, ecx; lpEventAttributes
0x18000f00b  lea     edx, [r9+1]; bManualReset
0x18000f00f  call    cs:__imp_CreateEventW
0x18000f015  mov     cs:?finalCallbackEvent@XinputHid@@3PEAXEA, rax; void * XinputHid::finalCallbackEvent
0x18000f01c  test    rax, rax
0x18000f01f  jz      loc_18000F113
0x18000f025  mov     edi, 2
0x18000f02a  xchg    rdi, cs:?callbackState@XinputHid@@3_JC; __int64 volatile XinputHid::callbackState
0x18000f031  mov     rcx, [rbx+28h]; hEvent
0x18000f035  call    cs:__imp_SetEvent
0x18000f03b  test    eax, eax
0x18000f03d  jz      loc_18000F12A
0x18000f043  mov     rcx, [rbx+20h]; hHandle
0x18000f047  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f04a  call    cs:__imp_WaitForSingleObject
0x18000f050  mov     rcx, [rbx+20h]; hObject
0x18000f054  call    cs:__imp_CloseHandle
0x18000f05a  test    eax, eax
0x18000f05c  jz      loc_18000F141
0x18000f062  mov     rcx, [rbx+30h]; hObject
0x18000f066  call    cs:__imp_CloseHandle
0x18000f06c  test    eax, eax
0x18000f06e  jz      loc_18000F158
0x18000f074  mov     rcx, [rbx+28h]; hObject
0x18000f078  call    cs:__imp_CloseHandle
0x18000f07e  test    eax, eax
0x18000f080  jz      loc_18000F16F
0x18000f086  mov     rcx, [rbx+18h]
0x18000f08a  call    cs:__imp_CM_Unregister_Notification
0x18000f090  test    eax, eax
0x18000f092  jnz     loc_18000F186
0x18000f098  cmp     rdi, 4
0x18000f09c  jnz     short loc_18000F0AE
0x18000f09e  mov     rcx, cs:?finalCallbackEvent@XinputHid@@3PEAXEA; hHandle
0x18000f0a5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f0a8  call    cs:__imp_WaitForSingleObject
0x18000f0ae  mov     rcx, cs:?finalCallbackEvent@XinputHid@@3PEAXEA; hObject
0x18000f0b5  mov     cs:?callbackState@XinputHid@@3_JC, 3; __int64 volatile XinputHid::callbackState
0x18000f0c0  call    cs:__imp_CloseHandle
0x18000f0c6  test    eax, eax
0x18000f0c8  jz      short loc_18000F0FC
0x18000f0ca  lea     rcx, [rbx+78h]
0x18000f0ce  mov     cs:?finalCallbackEvent@XinputHid@@3PEAXEA, 0; void * XinputHid::finalCallbackEvent
0x18000f0d9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>(void)
0x18000f0de  lea     rcx, [rbx+68h]
0x18000f0e2  call    ??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>::~list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>(void)
0x18000f0e7  lea     rcx, [rbx+38h]
0x18000f0eb  mov     rbx, [rsp+28h+arg_0]
0x18000f0f0  add     rsp, 20h
0x18000f0f4  pop     rdi
0x18000f0f5  jmp     cs:__imp_DeleteCriticalSection
0x18000f0fc  mov     rcx, [rsp+28h]; this
0x18000f101  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f108  mov     edx, 0EBh; void *
0x18000f10d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f113  mov     rcx, [rsp+28h]; this
0x18000f118  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f11f  mov     edx, 0D5h; void *
0x18000f124  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f12a  mov     rcx, [rsp+28h]; this
0x18000f12f  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f136  mov     edx, 0DAh; void *
0x18000f13b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f141  mov     rcx, [rsp+28h]; this
0x18000f146  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f14d  mov     edx, 0DEh; void *
0x18000f152  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f158  mov     rcx, [rsp+28h]; this
0x18000f15d  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f164  mov     edx, 0DFh; void *
0x18000f169  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f16f  mov     rcx, [rsp+28h]; this
0x18000f174  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000f17b  mov     edx, 0E0h; void *
0x18000f180  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f186  mov     rcx, [rsp+28h]; this
0x18000f18b  mov     edx, 0E2h; void *
0x18000f190  mov     r9d, 8000FFFFh; char *
0x18000f196  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
