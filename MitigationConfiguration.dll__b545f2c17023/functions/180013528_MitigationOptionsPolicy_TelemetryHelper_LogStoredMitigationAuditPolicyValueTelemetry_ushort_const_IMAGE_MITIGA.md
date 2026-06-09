# MitigationOptionsPolicy::TelemetryHelper::LogStoredMitigationAuditPolicyValueTelemetry(ushort const *,_IMAGE_MITIGATION_POLICY,void *,ulong,void *,ulong)

- ea: `0x180013528`
- end: `0x180013717`
- name: `?LogStoredMitigationAuditPolicyValueTelemetry@TelemetryHelper@MitigationOptionsPolicy@@SAXPEBGW4_IMAGE_MITIGATION_POLICY@@PEAXK2K@Z`
- size: `495`
- prototype: `__int64 __fastcall(const wchar_t *, int, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001086c`
- `0x180010b3c`

## callees

- `0x1800012bc`
- `0x1800013d8`
- `0x180001c00`
- `0x1800076b4`
- `0x180013068`
- `0x180013528`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800135a0`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800135a0`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::TelemetryHelper::LogStoredMitigationAuditPolicyValueTelemetry(
        const wchar_t *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6)
{
  const wchar_t *v8; // rbx
  const wchar_t *v9; // rdi
  __int64 result; // rax
  _QWORD *v11; // rax
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  const wchar_t *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const wchar_t *v20; // [rsp+40h] [rbp-49h] BYREF
  const wchar_t *v21; // [rsp+48h] [rbp-41h] BYREF
  const wchar_t *v22; // [rsp+50h] [rbp-39h] BYREF
  _QWORD *v23; // [rsp+58h] [rbp-31h] BYREF
  char *v24[4]; // [rsp+60h] [rbp-29h] BYREF
  char *v25[4]; // [rsp+80h] [rbp-9h] BYREF

  if ( a2 < 19 )
    v8 = (const wchar_t *)(&MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames)[a2];
  else
    v8 = L"Unknown";
  v9 = L"*System Defaults*";
  if ( a1 )
    v9 = a1;
  RtlRunOnceExecuteOnce(
    &MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce,
    MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce,
    0,
    0);
  result = (unsigned int)dword_18001C038;
  if ( a4 )
  {
    if ( (unsigned int)dword_18001C038 > 5 )
    {
      result = qword_18001C048;
      if ( (qword_18001C048 & 0x400000000000LL) != 0 )
      {
        result = qword_18001C050 & 0x400000000000LL;
        if ( (qword_18001C050 & 0x400000000000LL) == qword_18001C050 )
        {
          v11 = (_QWORD *)MitigationOptionsPolicy::TelemetryHelper::Base64Encode(v24, a5, a6);
          if ( v11[3] > 7u )
            v11 = (_QWORD *)*v11;
          v23 = v11;
          v12 = (const wchar_t *)MitigationOptionsPolicy::TelemetryHelper::Base64Encode(v25, a3, a4);
          if ( *((_QWORD *)v12 + 3) > 7u )
            v12 = *(const wchar_t **)v12;
          v20 = v12;
          v21 = v8;
          v22 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v13,
            (__int64)word_180018E42,
            v14,
            v15,
            &v22,
            &v21,
            &v20,
            &v23);
          std::wstring::~wstring(v25);
          return std::wstring::~wstring(v24);
        }
      }
    }
  }
  else if ( (unsigned int)dword_18001C038 > 5 )
  {
    result = qword_18001C048;
    if ( (qword_18001C048 & 0x200000000000LL) != 0 )
    {
      result = qword_18001C050 & 0x200000000000LL;
      if ( (qword_18001C050 & 0x200000000000LL) == qword_18001C050 )
      {
        v16 = (const wchar_t *)MitigationOptionsPolicy::TelemetryHelper::Base64Encode(v24, a5, a6);
        if ( *((_QWORD *)v16 + 3) > 7u )
          v16 = *(const wchar_t **)v16;
        v22 = v16;
        v21 = v8;
        v20 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v17,
          (__int64)&byte_180018CEF,
          v18,
          v19,
          &v20,
          &v21,
          &v22);
        return std::wstring::~wstring(v24);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013528  mov     [rsp-8+arg_0], rbx
0x18001352d  mov     [rsp-8+arg_8], rsi
0x180013532  push    rbp
0x180013533  push    rdi
0x180013534  push    r12
0x180013536  push    r14
0x180013538  push    r15
0x18001353a  lea     rbp, [rsp-27h]
0x18001353f  sub     rsp, 0B0h
0x180013546  mov     rax, cs:__security_cookie
0x18001354d  xor     rax, rsp
0x180013550  mov     [rbp+47h+var_30], rax
0x180013554  mov     r15d, r9d
0x180013557  mov     r12, r8
0x18001355a  mov     rsi, [rbp+47h+arg_20]
0x18001355e  mov     r14d, [rbp+47h+arg_28]
0x180013562  cmp     edx, 13h
0x180013565  jl      short loc_180013570
0x180013567  lea     rbx, aUnknown; "Unknown"
0x18001356e  jmp     short loc_18001357E
0x180013570  movsxd  rax, edx
0x180013573  lea     rbx, ?s_mitigationNames@TelemetryHelper@MitigationOptionsPolicy@@0PAPEBGA; ushort const * near * MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames
0x18001357a  mov     rbx, [rbx+rax*8]
0x18001357e  lea     rdi, aSystemDefaults; "*System Defaults*"
0x180013585  test    rcx, rcx
0x180013588  cmovnz  rdi, rcx
0x18001358c  xor     r9d, r9d
0x18001358f  xor     r8d, r8d
0x180013592  lea     rdx, ?ImageMitigationPolicyTelemetryInitOnce@MitigationOptionsPolicy@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce(_RTL_RUN_ONCE *,void *,void * *)
0x180013599  lea     rcx, ?ImageMitigationPolicyTelemetryInitRunOnce@MitigationOptionsPolicy@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce
0x1800135a0  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800135a6  mov     eax, cs:dword_18001C038
0x1800135ac  test    r15d, r15d
0x1800135af  jz      loc_18001366D
0x1800135b5  cmp     eax, 5
0x1800135b8  jbe     loc_1800136EF
0x1800135be  mov     rcx, cs:qword_18001C050
0x1800135c5  mov     rax, cs:qword_18001C048
0x1800135cc  mov     rdx, 400000000000h
0x1800135d6  test    rdx, rax
0x1800135d9  jz      loc_1800136EF
0x1800135df  mov     rax, rcx
0x1800135e2  and     rax, rdx
0x1800135e5  cmp     rax, rcx
0x1800135e8  jnz     loc_1800136EF
0x1800135ee  mov     r8d, r14d
0x1800135f1  mov     rdx, rsi
0x1800135f4  lea     rcx, [rbp+47h+var_70]
0x1800135f8  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x1800135fd  nop
0x1800135fe  cmp     qword ptr [rax+18h], 7
0x180013603  jbe     short loc_180013608
0x180013605  mov     rax, [rax]
0x180013608  mov     [rbp+47h+var_78], rax
0x18001360c  mov     r8d, r15d
0x18001360f  mov     rdx, r12
0x180013612  lea     rcx, [rbp+47h+var_50]
0x180013616  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x18001361b  cmp     qword ptr [rax+18h], 7
0x180013620  jbe     short loc_180013625
0x180013622  mov     rax, [rax]
0x180013625  mov     [rbp+47h+var_90], rax
0x180013629  mov     [rbp+47h+var_88], rbx
0x18001362d  mov     [rbp+47h+var_80], rdi
0x180013631  lea     rax, [rbp+47h+var_78]
0x180013635  mov     [rsp+0D0h+var_98], rax
0x18001363a  lea     rax, [rbp+47h+var_90]
0x18001363e  mov     [rsp+0D0h+var_A0], rax
0x180013643  lea     rax, [rbp+47h+var_88]
0x180013647  mov     [rsp+0D0h+var_A8], rax
0x18001364c  lea     rax, [rbp+47h+var_80]
0x180013650  mov     [rsp+0D0h+var_B0], rax
0x180013655  lea     rdx, word_180018E42
0x18001365c  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180013661  lea     rcx, [rbp+47h+var_50]
0x180013665  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001366a  nop
0x18001366b  jmp     short loc_1800136E6
0x18001366d  cmp     eax, 5
0x180013670  jbe     short loc_1800136EF
0x180013672  mov     rcx, cs:qword_18001C050
0x180013679  mov     rax, cs:qword_18001C048
0x180013680  mov     rdx, 200000000000h
0x18001368a  test    rdx, rax
0x18001368d  jz      short loc_1800136EF
0x18001368f  mov     rax, rcx
0x180013692  and     rax, rdx
0x180013695  cmp     rax, rcx
0x180013698  jnz     short loc_1800136EF
0x18001369a  mov     r8d, r14d
0x18001369d  mov     rdx, rsi
0x1800136a0  lea     rcx, [rbp+47h+var_70]
0x1800136a4  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x1800136a9  cmp     qword ptr [rax+18h], 7
0x1800136ae  jbe     short loc_1800136B3
0x1800136b0  mov     rax, [rax]
0x1800136b3  mov     [rbp+47h+var_80], rax
0x1800136b7  mov     [rbp+47h+var_88], rbx
0x1800136bb  mov     [rbp+47h+var_90], rdi
0x1800136bf  lea     rax, [rbp+47h+var_80]
0x1800136c3  mov     [rsp+0D0h+var_A0], rax
0x1800136c8  lea     rax, [rbp+47h+var_88]
0x1800136cc  mov     [rsp+0D0h+var_A8], rax
0x1800136d1  lea     rax, [rbp+47h+var_90]
0x1800136d5  mov     [rsp+0D0h+var_B0], rax
0x1800136da  lea     rdx, byte_180018CEF
0x1800136e1  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800136e6  lea     rcx, [rbp+47h+var_70]
0x1800136ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800136ef  mov     rcx, [rbp+47h+var_30]
0x1800136f3  xor     rcx, rsp; StackCookie
0x1800136f6  call    __security_check_cookie
0x1800136fb  lea     r11, [rsp+0D0h+var_20]
0x180013703  mov     rbx, [r11+30h]
0x180013707  mov     rsi, [r11+38h]
0x18001370b  mov     rsp, r11
0x18001370e  pop     r15
0x180013710  pop     r14
0x180013712  pop     r12
0x180013714  pop     rdi
0x180013715  pop     rbp
0x180013716  retn
```
