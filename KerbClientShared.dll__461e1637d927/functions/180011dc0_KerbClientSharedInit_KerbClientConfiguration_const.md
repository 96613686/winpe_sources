# KerbClientSharedInit(_KerbClientConfiguration const *)

- ea: `0x180011dc0`
- end: `0x180011e7c`
- name: `?KerbClientSharedInit@@YAJPEBU_KerbClientConfiguration@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(const struct _KerbClientConfiguration *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180011dc0`
- `0x1800147b8`
- `0x180017e08`
- `0x180028000`
- `0x1800281fc`
- `0x180029010`

## import_xrefs

- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x180011e40`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x180011e40`

## pseudocode

```c
__int64 __fastcall KerbClientSharedInit(const struct _KerbClientConfiguration *a1)
{
  __int64 LocalCipherPolicy; // rax

  SafeAllocaInitialize();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  qword_1800333D8 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_KerbClientSharedTraceControlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_1800333E0 = 1;
  WppInitUm();
  GlobalConfig = *(_DWORD *)a1;
  *(_OWORD *)&dword_18003349C = *(_OWORD *)((char *)a1 + 4);
  *(_OWORD *)((char *)&qword_1800334A8 + 4) = *(_OWORD *)((char *)a1 + 20);
  HIDWORD(qword_1800334B8) = *((_DWORD *)a1 + 9);
  if ( GlobalConfig )
  {
    LocalCipherPolicy = GetLocalCipherPolicy();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)LocalCipherPolicy + 48LL))(LocalCipherPolicy);
    KerberosCryptoPolicy::isolatedMode = 1;
    if ( !(unsigned __int8)KerberosCryptoPolicy::InitializeCiphers() )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      __fastfail(0x29Cu);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011dc0  push    rbx
0x180011dc2  sub     rsp, 20h
0x180011dc6  mov     rbx, rcx
0x180011dc9  call    SafeAllocaInitialize
0x180011dce  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180011dd3  lea     rax, WPP_ThisDir_CTLGUID_KerbClientSharedTraceControlGuid
0x180011dda  mov     cs:qword_1800333D8, 0
0x180011de5  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180011dec  lea     rax, WPP_MAIN_CB
0x180011df3  mov     cs:WPP_GLOBAL_Control, rax
0x180011dfa  mov     cs:WPP_MAIN_CB, 0
0x180011e05  mov     cs:qword_1800333E0, 1
0x180011e10  call    WppInitUm
0x180011e15  mov     ecx, [rbx]
0x180011e17  mov     cs:?GlobalConfig@@3U_KerbClientConfiguration@@A, ecx; _KerbClientConfiguration GlobalConfig
0x180011e1d  movups  xmm0, xmmword ptr [rbx+4]
0x180011e21  movups  xmmword ptr cs:dword_18003349C, xmm0
0x180011e28  movups  xmm1, xmmword ptr [rbx+14h]
0x180011e2c  movups  xmmword ptr cs:qword_1800334A8+4, xmm1
0x180011e33  mov     eax, [rbx+24h]
0x180011e36  mov     dword ptr cs:qword_1800334B8+4, eax
0x180011e3c  test    ecx, ecx
0x180011e3e  jz      short loc_180011E74
0x180011e40  call    cs:__imp_GetLocalCipherPolicy
0x180011e46  mov     rdx, rax
0x180011e49  mov     rcx, [rax]
0x180011e4c  mov     rax, [rcx+30h]
0x180011e50  mov     rcx, rdx
0x180011e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e58  mov     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 1; bool KerberosCryptoPolicy::isolatedMode
0x180011e5f  call    ?InitializeCiphers@KerberosCryptoPolicy@@SA_NW4Kerb3961PolicyType@@PEAUHKEY__@@@Z; KerberosCryptoPolicy::InitializeCiphers(Kerb3961PolicyType,HKEY__ *)
0x180011e64  test    al, al
0x180011e66  jnz     short loc_180011E74
0x180011e68  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011e6d  mov     ecx, 29Ch
0x180011e72  int     29h; Win8: RtlFailFast(ecx)
0x180011e74  xor     eax, eax
0x180011e76  add     rsp, 20h
0x180011e7a  pop     rbx
0x180011e7b  retn
```
