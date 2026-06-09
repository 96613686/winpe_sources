# ConfigSet::RegisterChangeCallback(void (*)(void *,uchar),void *,void * *)

- ea: `0x18002f30c`
- end: `0x18002f60c`
- name: `?RegisterChangeCallback@ConfigSet@@QEAAJP6AXPEAXE@Z0PEAPEAX@Z`
- size: `768`
- prototype: `int(ConfigSet *__hidden this, void (*)(void *, unsigned __int8), void *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b120`

## callees

- `0x180005660`
- `0x180005c54`
- `0x18001db40`
- `0x18002c580`
- `0x18002f30c`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f339`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f339`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5e9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f3ef`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f4c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f54d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f5b0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f3ef`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f4c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f54d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002f5b0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002f3ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002f3ac`

## string_xrefs

- `0x18002f362`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f3d1`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f415`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f4ef`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f50c`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f577`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f58f`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18002f5d6`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::RegisterChangeCallback(
        ConfigSet *this,
        void (*a2)(void *, unsigned __int8),
        void *a3,
        void **a4)
{
  HANDLE EventW; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  void **v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  bool v14; // sf
  _QWORD *v15; // rbx
  HANDLE v16; // rdx
  HANDLE v17; // rbp
  _QWORD *v18; // rax
  _QWORD *v19; // rdx
  HANDLE v20; // rcx
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  bool v24; // sf
  signed int v25; // eax
  bool v26; // sf
  HANDLE WaitHandle; // [rsp+30h] [rbp-38h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent_7(v9, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1138);
    return v9;
  }
  WaitHandle = 0;
  v11 = tlx::replace<void *,unsigned long (*)(void *),&private: static unsigned long ConfigSet::UnregisterWaitAndBlock(void *),0>(&WaitHandle);
  if ( !RegisterWaitForSingleObject(v11, EventW, PhoneController::_AccessibilityChangeCallback, a3, 0xFFFFFFFF, 0) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    Log_HREvent_7(v9, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1142);
    if ( WaitHandle && !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v13 = GetLastError();
      v14 = v13 < 0;
      if ( v13 > 0 )
      {
        v13 = (unsigned __int16)v13 | 0x80070000;
        v14 = v13 < 0;
      }
      if ( v14 )
        Log_HREvent_7((unsigned int)v13, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1218);
    }
    CloseHandle(EventW);
    return v9;
  }
  v15 = operator new(0x18u);
  if ( !v15 )
  {
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1146);
    if ( WaitHandle && !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v25 = GetLastError();
      v26 = v25 < 0;
      if ( v25 > 0 )
      {
        v25 = (unsigned __int16)v25 | 0x80070000;
        v26 = v25 < 0;
      }
      if ( v26 )
        Log_HREvent_7((unsigned int)v25, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1218);
    }
    CloseHandle(EventW);
    return 2147942414LL;
  }
  v16 = WaitHandle;
  v15[2] = EventW;
  *v15 = &ConfigSet::ConfigSetListener::`vftable';
  v15[1] = v16;
  v17 = WaitHandle;
  WaitHandle = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v18 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v18 )
  {
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1156);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
    if ( WaitHandle && !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v23 = GetLastError();
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 )
        Log_HREvent_7((unsigned int)v23, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1218);
    }
    return 2147942414LL;
  }
  v18[2] = v15;
  v19 = (_QWORD *)*((_QWORD *)this + 7);
  v18[1] = v19;
  *v18 = (char *)this + 48;
  *v19 = v18;
  *((_QWORD *)this + 7) = v18;
  ++*((_QWORD *)this + 8);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v20 = WaitHandle;
  *a4 = v17;
  if ( v20 && !UnregisterWaitEx(v20, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    v21 = GetLastError();
    v22 = v21 < 0;
    if ( v21 > 0 )
    {
      v21 = (unsigned __int16)v21 | 0x80070000;
      v22 = v21 < 0;
    }
    if ( v22 )
      Log_HREvent_7((unsigned int)v21, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1218);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f30c  push    rbx
0x18002f30e  push    rbp
0x18002f30f  push    rsi
0x18002f310  push    rdi
0x18002f311  push    r14
0x18002f313  sub     rsp, 40h
0x18002f317  mov     rax, cs:__security_cookie
0x18002f31e  xor     rax, rsp
0x18002f321  mov     [rsp+68h+var_30], rax
0x18002f326  mov     r14, r9
0x18002f329  mov     rbx, r8
0x18002f32c  mov     rsi, rcx
0x18002f32f  xor     r9d, r9d; lpName
0x18002f332  xor     r8d, r8d; bInitialState
0x18002f335  xor     ecx, ecx; lpEventAttributes
0x18002f337  xor     edx, edx; bManualReset
0x18002f339  call    cs:__imp_CreateEventW
0x18002f33f  mov     rdi, rax
0x18002f342  test    rax, rax
0x18002f345  jnz     short loc_18002F379
0x18002f347  call    cs:__imp_GetLastError
0x18002f34d  mov     ebx, eax
0x18002f34f  test    eax, eax
0x18002f351  jle     short loc_18002F35C
0x18002f353  movzx   ebx, ax
0x18002f356  or      ebx, 80070000h
0x18002f35c  mov     r9d, 472h
0x18002f362  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f369  xor     edx, edx
0x18002f36b  mov     ecx, ebx
0x18002f36d  call    Log_HREvent_7
0x18002f372  mov     eax, ebx
0x18002f374  jmp     loc_18002F5F4
0x18002f379  lea     rcx, [rsp+68h+WaitHandle]
0x18002f37e  mov     [rsp+68h+WaitHandle], 0
0x18002f387  call    ??$replace@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@0@@Z; tlx::replace<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0>(tlx::auto_xxx<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0> &)
0x18002f38c  mov     r9, rbx; Context
0x18002f38f  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18002f397  lea     r8, ?_AccessibilityChangeCallback@PhoneController@@KAXPEAXE@Z; Callback
0x18002f39e  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18002f3a6  mov     rdx, rdi; hObject
0x18002f3a9  mov     rcx, rax; phNewWaitObject
0x18002f3ac  call    cs:__imp_RegisterWaitForSingleObject
0x18002f3b2  test    eax, eax
0x18002f3b4  jnz     short loc_18002F433
0x18002f3b6  call    cs:__imp_GetLastError
0x18002f3bc  mov     ebx, eax
0x18002f3be  test    eax, eax
0x18002f3c0  jle     short loc_18002F3CB
0x18002f3c2  movzx   ebx, ax
0x18002f3c5  or      ebx, 80070000h
0x18002f3cb  mov     r9d, 476h
0x18002f3d1  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f3d8  xor     edx, edx
0x18002f3da  mov     ecx, ebx
0x18002f3dc  call    Log_HREvent_7
0x18002f3e1  mov     rcx, [rsp+68h+WaitHandle]; WaitHandle
0x18002f3e6  test    rcx, rcx
0x18002f3e9  jz      short loc_18002F425
0x18002f3eb  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002f3ef  call    cs:__imp_UnregisterWaitEx
0x18002f3f5  test    eax, eax
0x18002f3f7  jnz     short loc_18002F425
0x18002f3f9  call    cs:__imp_GetLastError
0x18002f3ff  test    eax, eax
0x18002f401  jle     short loc_18002F40D
0x18002f403  movzx   eax, ax
0x18002f406  or      eax, 80070000h
0x18002f40b  test    eax, eax
0x18002f40d  jns     short loc_18002F425
0x18002f40f  mov     r9d, 4C2h
0x18002f415  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f41c  xor     edx, edx
0x18002f41e  mov     ecx, eax
0x18002f420  call    Log_HREvent_7
0x18002f425  mov     rcx, rdi; hObject
0x18002f428  call    cs:__imp_CloseHandle
0x18002f42e  jmp     loc_18002F372
0x18002f433  mov     ecx, 18h; Size
0x18002f438  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f43d  mov     rbx, rax
0x18002f440  test    rax, rax
0x18002f443  jz      loc_18002F589
0x18002f449  mov     rdx, [rsp+68h+WaitHandle]
0x18002f44e  lea     rax, ??_7ConfigSetListener@ConfigSet@@6B@; const ConfigSet::ConfigSetListener::`vftable'
0x18002f455  mov     [rbx+10h], rdi
0x18002f459  lea     rdi, [rsi+8]
0x18002f45d  mov     [rbx], rax
0x18002f460  mov     rcx, rdi; lpCriticalSection
0x18002f463  mov     [rbx+8], rdx
0x18002f467  mov     rbp, [rsp+68h+WaitHandle]
0x18002f46c  mov     [rsp+68h+WaitHandle], 0
0x18002f475  call    cs:__imp_EnterCriticalSection
0x18002f47b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f482  mov     ecx, 18h; unsigned __int64
0x18002f487  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f48c  test    rax, rax
0x18002f48f  jz      short loc_18002F506
0x18002f491  mov     [rax+10h], rbx
0x18002f495  lea     r8, [rsi+30h]
0x18002f499  mov     rdx, [r8+8]
0x18002f49d  mov     rcx, rdi; lpCriticalSection
0x18002f4a0  mov     [rax+8], rdx
0x18002f4a4  mov     [rax], r8
0x18002f4a7  mov     [rdx], rax
0x18002f4aa  mov     [r8+8], rax
0x18002f4ae  inc     qword ptr [r8+10h]
0x18002f4b2  call    cs:__imp_LeaveCriticalSection
0x18002f4b8  mov     rcx, [rsp+68h+WaitHandle]; WaitHandle
0x18002f4bd  mov     [r14], rbp
0x18002f4c0  test    rcx, rcx
0x18002f4c3  jz      short loc_18002F4FF
0x18002f4c5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002f4c9  call    cs:__imp_UnregisterWaitEx
0x18002f4cf  test    eax, eax
0x18002f4d1  jnz     short loc_18002F4FF
0x18002f4d3  call    cs:__imp_GetLastError
0x18002f4d9  test    eax, eax
0x18002f4db  jle     short loc_18002F4E7
0x18002f4dd  movzx   eax, ax
0x18002f4e0  or      eax, 80070000h
0x18002f4e5  test    eax, eax
0x18002f4e7  jns     short loc_18002F4FF
0x18002f4e9  mov     r9d, 4C2h
0x18002f4ef  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f4f6  xor     edx, edx
0x18002f4f8  mov     ecx, eax
0x18002f4fa  call    Log_HREvent_7
0x18002f4ff  xor     eax, eax
0x18002f501  jmp     loc_18002F5F4
0x18002f506  mov     r9d, 484h
0x18002f50c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f513  xor     edx, edx
0x18002f515  mov     ecx, 8007000Eh
0x18002f51a  call    Log_HREvent_7
0x18002f51f  mov     rcx, rdi; lpCriticalSection
0x18002f522  call    cs:__imp_LeaveCriticalSection
0x18002f528  mov     rax, [rbx]
0x18002f52b  mov     edx, 1
0x18002f530  mov     rcx, rbx
0x18002f533  mov     rax, [rax]
0x18002f536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f53b  mov     rcx, [rsp+68h+WaitHandle]; WaitHandle
0x18002f540  test    rcx, rcx
0x18002f543  jz      loc_18002F5EF
0x18002f549  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002f54d  call    cs:__imp_UnregisterWaitEx
0x18002f553  test    eax, eax
0x18002f555  jnz     loc_18002F5EF
0x18002f55b  call    cs:__imp_GetLastError
0x18002f561  test    eax, eax
0x18002f563  jle     short loc_18002F56F
0x18002f565  movzx   eax, ax
0x18002f568  or      eax, 80070000h
0x18002f56d  test    eax, eax
0x18002f56f  jns     short loc_18002F5EF
0x18002f571  mov     r9d, 4C2h
0x18002f577  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f57e  xor     edx, edx
0x18002f580  mov     ecx, eax
0x18002f582  call    Log_HREvent_7
0x18002f587  jmp     short loc_18002F5EF
0x18002f589  mov     r9d, 47Ah
0x18002f58f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f596  xor     edx, edx
0x18002f598  mov     ecx, 8007000Eh
0x18002f59d  call    Log_HREvent_7
0x18002f5a2  mov     rcx, [rsp+68h+WaitHandle]; WaitHandle
0x18002f5a7  test    rcx, rcx
0x18002f5aa  jz      short loc_18002F5E6
0x18002f5ac  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002f5b0  call    cs:__imp_UnregisterWaitEx
0x18002f5b6  test    eax, eax
0x18002f5b8  jnz     short loc_18002F5E6
0x18002f5ba  call    cs:__imp_GetLastError
0x18002f5c0  test    eax, eax
0x18002f5c2  jle     short loc_18002F5CE
0x18002f5c4  movzx   eax, ax
0x18002f5c7  or      eax, 80070000h
0x18002f5cc  test    eax, eax
0x18002f5ce  jns     short loc_18002F5E6
0x18002f5d0  mov     r9d, 4C2h
0x18002f5d6  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002f5dd  xor     edx, edx
0x18002f5df  mov     ecx, eax
0x18002f5e1  call    Log_HREvent_7
0x18002f5e6  mov     rcx, rdi; hObject
0x18002f5e9  call    cs:__imp_CloseHandle
0x18002f5ef  mov     eax, 8007000Eh
0x18002f5f4  mov     rcx, [rsp+68h+var_30]
0x18002f5f9  xor     rcx, rsp; StackCookie
0x18002f5fc  call    __security_check_cookie
0x18002f601  add     rsp, 40h
0x18002f605  pop     r14
0x18002f607  pop     rdi
0x18002f608  pop     rsi
0x18002f609  pop     rbp
0x18002f60a  pop     rbx
0x18002f60b  retn
```
