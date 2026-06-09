# wil::details::static_lazy<MBSettingUXLogging>::get(void (*)(void))

- ea: `0x180010aa0`
- end: `0x180010b8b`
- name: `?get@?$static_lazy@VMBSettingUXLogging@@@details@wil@@QEAAPEAVMBSettingUXLogging@@P6AXXZ@Z`
- size: `235`
- prototype: `__int64(void)`
- caller_count: `15`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008c84`
- `0x180022ac0`
- `0x1800258b0`
- `0x18003237c`
- `0x18003a1c4`
- `0x18003a220`
- `0x18003a27c`
- `0x18003a2d8`
- `0x18003ced0`
- `0x180042130`
- `0x1800421d8`
- `0x1800422d8`
- `0x180042380`
- `0x1800485a4`
- `0x180049794`

## callees

- `0x180010aa0`
- `0x180010b94`
- `0x18002d1ac`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010acd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010acd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010b75`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010b75`

## pseudocode

```c
LPVOID __fastcall wil::details::static_lazy<MBSettingUXLogging>::get(__int64 a1, __int64 a2)
{
  LPVOID Context; // [rsp+30h] [rbp+8h] BYREF
  WINBOOL fPending; // [rsp+38h] [rbp+10h] BYREF
  int v5; // [rsp+3Ch] [rbp+14h]

  v5 = HIDWORD(a2);
  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18007EE30 = 0;
    Context = &qword_18007EE28;
    byte_18007EE38 = 0;
    dword_18007EE3C = 0;
    qword_18007EE28 = (__int64)&MBSettingUXLogging::`vftable';
    CallbackContext = &`MBSettingUXLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MBSettingUXLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    qword_18007EE30 = (__int64)CallbackContext;
    byte_18007EE38 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18007EE3C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18007EE28 + 8))(&qword_18007EE28);
    InitOnceComplete(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &qword_18007EE28);
  }
  return Context;
}

```

## disassembly

```asm
0x180010aa0  mov     qword ptr [rsp+fPending], rdx
0x180010aa5  mov     [rsp+Context], rcx
0x180010aaa  push    rdi
0x180010aab  sub     rsp, 20h
0x180010aaf  xor     edi, edi
0x180010ab1  lea     r9, [rsp+28h+Context]; lpContext
0x180010ab6  lea     r8, [rsp+28h+fPending]; fPending
0x180010abb  mov     [rsp+28h+Context], rdi
0x180010ac0  xor     edx, edx; dwFlags
0x180010ac2  mov     [rsp+28h+fPending], edi
0x180010ac6  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x180010acd  call    cs:__imp_InitOnceBeginInitialize
0x180010ad3  test    eax, eax
0x180010ad5  jz      loc_180010B80
0x180010adb  cmp     [rsp+28h+fPending], edi
0x180010adf  jz      loc_180010B80
0x180010ae5  mov     [rsp+28h+arg_10], rbx
0x180010aea  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x180010af1  lea     rbx, qword_18007EE28
0x180010af8  mov     cs:qword_18007EE30, rdi
0x180010aff  mov     [rsp+28h+Context], rbx
0x180010b04  mov     cs:byte_18007EE38, dil
0x180010b0b  mov     cs:dword_18007EE3C, edi
0x180010b11  mov     cs:qword_18007EE28, rax
0x180010b18  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180010b1f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180010b26  mov     cs:CallbackContext, rax
0x180010b2d  call    atexit
0x180010b32  mov     rcx, cs:CallbackContext; CallbackContext
0x180010b39  mov     cs:qword_18007EE30, rcx
0x180010b40  mov     cs:byte_18007EE38, 1
0x180010b47  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180010b4c  mov     rax, cs:qword_18007EE28
0x180010b53  mov     rcx, rbx
0x180010b56  mov     cs:dword_18007EE3C, 1
0x180010b60  mov     rax, [rax+8]
0x180010b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b69  mov     r8, rbx; lpContext
0x180010b6c  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x180010b73  xor     edx, edx; dwFlags
0x180010b75  call    cs:__imp_InitOnceComplete
0x180010b7b  mov     rbx, [rsp+28h+arg_10]
0x180010b80  mov     rax, [rsp+28h+Context]
0x180010b85  add     rsp, 20h
0x180010b89  pop     rdi
0x180010b8a  retn
```
