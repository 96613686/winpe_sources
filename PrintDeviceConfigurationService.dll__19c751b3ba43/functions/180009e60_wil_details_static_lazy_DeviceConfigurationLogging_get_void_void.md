# wil::details::static_lazy<DeviceConfigurationLogging>::get(void (*)(void))

- ea: `0x180009e60`
- end: `0x180009f1a`
- name: `?get@?$static_lazy@VDeviceConfigurationLogging@@@details@wil@@QEAAPEAVDeviceConfigurationLogging@@P6AXXZ@Z`
- size: `186`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b70`
- `0x18000ad98`

## callees

- `0x180002470`
- `0x180004f40`
- `0x180009e60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e96`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e96`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<DeviceConfigurationLogging>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  WINBOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`DeviceConfigurationLogging::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`DeviceConfigurationLogging::Instance'::`2'::wrapper;
    v8 = &qword_1800245D0;
    qword_1800245D0 = (__int64)&DeviceConfigurationLogging::`vftable';
    qword_1800245D8 = 0;
    byte_1800245E0 = 0;
    dword_1800245E4 = 0;
    qword_1800245E8 = (__int64)&`DeviceConfigurationLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<DeviceConfigurationLogging>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x180009e60  mov     rax, rsp
0x180009e63  mov     [rax+10h], rbx
0x180009e67  mov     [rax+8], rcx
0x180009e6b  push    rsi
0x180009e6c  sub     rsp, 30h
0x180009e70  mov     rbx, rdx
0x180009e73  mov     qword ptr [rax+18h], 0
0x180009e7b  lea     rsi, ?wrapper@?1??Instance@DeviceConfigurationLogging@@KAPEAV2@XZ@4V?$static_lazy@VDeviceConfigurationLogging@@@details@wil@@A; wil::details::static_lazy<DeviceConfigurationLogging> `DeviceConfigurationLogging::Instance(void)'::`2'::wrapper
0x180009e82  mov     dword ptr [rax+8], 0
0x180009e89  mov     rcx, rsi; lpInitOnce
0x180009e8c  lea     r9, [rax+18h]; lpContext
0x180009e90  lea     r8, [rax+8]; fPending
0x180009e94  xor     edx, edx; dwFlags
0x180009e96  call    cs:__imp_InitOnceBeginInitialize
0x180009e9c  test    eax, eax
0x180009e9e  jz      short loc_180009F0A
0x180009ea0  cmp     [rsp+38h+arg_0], 0
0x180009ea5  jz      short loc_180009F0A
0x180009ea7  lea     rax, qword_1800245D0
0x180009eae  mov     [rsp+38h+var_18], rsi
0x180009eb3  mov     [rsp+38h+arg_10], rax
0x180009eb8  lea     rax, ??_7DeviceConfigurationLogging@@6B@; const DeviceConfigurationLogging::`vftable'
0x180009ebf  mov     cs:qword_1800245D0, rax
0x180009ec6  mov     cs:qword_1800245D8, 0
0x180009ed1  mov     cs:byte_1800245E0, 0
0x180009ed8  mov     cs:dword_1800245E4, 0
0x180009ee2  lea     rax, ?__hInner@?1???0StaticHandle@DeviceConfigurationLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DeviceConfigurationLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009ee9  mov     rcx, rbx; void (__cdecl *)()
0x180009eec  mov     cs:qword_1800245E8, rax
0x180009ef3  call    atexit
0x180009ef8  lea     rcx, [rsp+38h+var_18]
0x180009efd  mov     [rsp+38h+var_10], 0
0x180009f05  call    ??1Completer@?$static_lazy@VDeviceConfigurationLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<DeviceConfigurationLogging>::Completer::~Completer(void)
0x180009f0a  mov     rax, [rsp+38h+arg_10]
0x180009f0f  mov     rbx, [rsp+38h+arg_8]
0x180009f14  add     rsp, 30h
0x180009f18  pop     rsi
0x180009f19  retn
```
