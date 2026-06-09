# AccessibilitySettingsTelemetry::ColorFilterWithOptions<ulong &,ulong &,ulong &>(ulong &,ulong &,ulong &)

- ea: `0x140012cbc`
- end: `0x140012e83`
- name: `??$ColorFilterWithOptions@AEAKAEAKAEAK@AccessibilitySettingsTelemetry@@SAXAEAK00@Z`
- size: `455`
- prototype: `__int64 __fastcall(_DWORD *, int *, WINBOOL *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400143ac`

## callees

- `0x140001950`
- `0x140001a8c`
- `0x1400023e4`
- `0x140012cbc`
- `0x140015b00`
- `0x140017010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x140012db0`
- `KERNEL32!InitOnceComplete` at `0x140012db0`
- `KERNEL32!InitOnceBeginInitialize` at `0x140012d06`
- `KERNEL32!InitOnceBeginInitialize` at `0x140012d06`

## pseudocode

```c
__int64 __fastcall AccessibilitySettingsTelemetry::ColorFilterWithOptions<unsigned long &,unsigned long &,unsigned long &>(
        _DWORD *a1,
        int *a2,
        WINBOOL *a3)
{
  unsigned int *v6; // rcx
  __int64 result; // rax
  __int64 v8; // rdx
  WINBOOL fPending; // [rsp+30h] [rbp-59h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-51h] BYREF
  int v11; // [rsp+40h] [rbp-49h] BYREF
  __int64 v12; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-39h] BYREF
  LPVOID *p_Context; // [rsp+70h] [rbp-19h]
  __int64 v15; // [rsp+78h] [rbp-11h]
  int *v16; // [rsp+80h] [rbp-9h]
  __int64 v17; // [rsp+88h] [rbp-1h]
  WINBOOL *p_fPending; // [rsp+90h] [rbp+7h]
  __int64 v19; // [rsp+98h] [rbp+Fh]
  __int64 *v20; // [rsp+A0h] [rbp+17h]
  __int64 v21; // [rsp+A8h] [rbp+1Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`AccessibilitySettingsTraceLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_1400213B8 = 0;
    Context = &qword_1400213B0;
    qword_1400213B0 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1400213C0 = 0;
    dword_1400213C4 = 0;
    qword_1400213C8 = &`AccessibilitySettingsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_91053f1c33a8d60f5c719a7612d63ba1_::_lambda_invoker_cdecl_);
    qword_1400213B8 = (__int64)qword_1400213C8;
    byte_1400213C0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1400213C8);
    dword_1400213C4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1400213B0 + 8))(&qword_1400213B0);
    InitOnceComplete(&`AccessibilitySettingsTraceLogging::Instance'::`2'::wrapper, 0, &qword_1400213B0);
  }
  v6 = (unsigned int *)*((_QWORD *)Context + 1);
  result = *v6;
  if ( (unsigned int)result > 5 )
  {
    v8 = *((_QWORD *)v6 + 3);
    result = *((_QWORD *)v6 + 2);
    if ( (result & 0x400000000000LL) != 0 )
    {
      result = v8 & 0x400000000000LL;
      if ( (v8 & 0x400000000000LL) == v8 )
      {
        fPending = *a3;
        v11 = *a2;
        LODWORD(Context) = *a1;
        v20 = &v12;
        p_fPending = &fPending;
        v16 = &v11;
        p_Context = &Context;
        v12 = 0x2000000;
        v21 = 8;
        v19 = 4;
        v17 = 4;
        v15 = 4;
        return tlgWriteTransfer_EventWriteTransfer(v6, byte_14001BEC3, 0, 0, 6, v13);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012cbc  push    rbp
0x140012cbe  push    rbx
0x140012cbf  push    rsi
0x140012cc0  push    rdi
0x140012cc1  push    r14
0x140012cc3  lea     rbp, [rsp-37h]
0x140012cc8  sub     rsp, 0C0h
0x140012ccf  mov     rax, cs:__security_cookie
0x140012cd6  xor     rax, rsp
0x140012cd9  mov     [rbp+57h+var_30], rax
0x140012cdd  mov     rbx, r8
0x140012ce0  mov     [rbp+57h+Context], 0
0x140012ce8  mov     rdi, rdx
0x140012ceb  mov     [rbp+57h+fPending], 0
0x140012cf2  mov     rsi, rcx
0x140012cf5  lea     r8, [rbp+57h+fPending]; fPending
0x140012cf9  xor     edx, edx; dwFlags
0x140012cfb  lea     rcx, ?wrapper@?1??Instance@AccessibilitySettingsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@A; lpInitOnce
0x140012d02  lea     r9, [rbp+57h+Context]; lpContext
0x140012d06  call    cs:__imp_InitOnceBeginInitialize
0x140012d0c  test    eax, eax
0x140012d0e  jz      loc_140012DB6
0x140012d14  cmp     [rbp+57h+fPending], 0
0x140012d18  jz      loc_140012DB6
0x140012d1e  lea     r14, qword_1400213B0
0x140012d25  mov     cs:qword_1400213B8, 0
0x140012d30  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x140012d37  mov     [rbp+57h+Context], r14
0x140012d3b  mov     cs:qword_1400213B0, rax
0x140012d42  mov     cs:byte_1400213C0, 0
0x140012d49  mov     cs:dword_1400213C4, 0
0x140012d53  lea     rax, ?__hInner@?1???0StaticHandle@AccessibilitySettingsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AccessibilitySettingsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140012d5a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_91053f1c33a8d60f5c719a7612d63ba1_@@CA@XZ; void (__cdecl *)()
0x140012d61  mov     cs:qword_1400213C8, rax
0x140012d68  call    atexit
0x140012d6d  mov     rcx, cs:qword_1400213C8; CallbackContext
0x140012d74  mov     cs:qword_1400213B8, rcx
0x140012d7b  mov     cs:byte_1400213C0, 1
0x140012d82  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140012d87  mov     rax, cs:qword_1400213B0
0x140012d8e  mov     rcx, r14
0x140012d91  mov     cs:dword_1400213C4, 1
0x140012d9b  mov     rax, [rax+8]
0x140012d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012da4  mov     r8, r14; lpContext
0x140012da7  lea     rcx, ?wrapper@?1??Instance@AccessibilitySettingsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@A; lpInitOnce
0x140012dae  xor     edx, edx; dwFlags
0x140012db0  call    cs:__imp_InitOnceComplete
0x140012db6  mov     rax, [rbp+57h+Context]
0x140012dba  mov     rcx, [rax+8]
0x140012dbe  mov     eax, [rcx]
0x140012dc0  cmp     eax, 5
0x140012dc3  jbe     loc_140012E69
0x140012dc9  mov     rdx, [rcx+18h]
0x140012dcd  mov     r8, 400000000000h
0x140012dd7  mov     rax, [rcx+10h]
0x140012ddb  test    r8, rax
0x140012dde  jz      loc_140012E69
0x140012de4  mov     rax, rdx
0x140012de7  and     rax, r8
0x140012dea  cmp     rax, rdx
0x140012ded  jnz     short loc_140012E69
0x140012def  mov     eax, [rbx]
0x140012df1  lea     rdx, byte_14001BEC3
0x140012df8  mov     [rbp+57h+fPending], eax
0x140012dfb  xor     r9d, r9d
0x140012dfe  mov     eax, [rdi]
0x140012e00  xor     r8d, r8d
0x140012e03  mov     [rbp+57h+var_A0], eax
0x140012e06  mov     eax, [rsi]
0x140012e08  mov     dword ptr [rbp+57h+Context], eax
0x140012e0b  lea     rax, [rbp+57h+var_98]
0x140012e0f  mov     [rbp+57h+var_40], rax
0x140012e13  lea     rax, [rbp+57h+fPending]
0x140012e17  mov     [rbp+57h+var_50], rax
0x140012e1b  lea     rax, [rbp+57h+var_A0]
0x140012e1f  mov     [rbp+57h+var_60], rax
0x140012e23  lea     rax, [rbp+57h+Context]
0x140012e27  mov     [rbp+57h+var_70], rax
0x140012e2b  lea     rax, [rbp+57h+var_90]
0x140012e2f  mov     [rsp+0E0h+var_B8], rax
0x140012e34  mov     [rsp+0E0h+var_C0], 6
0x140012e3c  mov     [rbp+57h+var_98], 2000000h
0x140012e44  mov     [rbp+57h+var_38], 8
0x140012e4c  mov     [rbp+57h+var_48], 4
0x140012e54  mov     [rbp+57h+var_58], 4
0x140012e5c  mov     [rbp+57h+var_68], 4
0x140012e64  call    _tlgWriteTransfer_EventWriteTransfer
0x140012e69  mov     rcx, [rbp+57h+var_30]
0x140012e6d  xor     rcx, rsp; StackCookie
0x140012e70  call    __security_check_cookie
0x140012e75  add     rsp, 0C0h
0x140012e7c  pop     r14
0x140012e7e  pop     rdi
0x140012e7f  pop     rsi
0x140012e80  pop     rbx
0x140012e81  pop     rbp
0x140012e82  retn
```
