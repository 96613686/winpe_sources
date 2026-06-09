# MitigationOptionsPolicy::TelemetryHelper::LogImageMitigationAuditPolicyFailureTelemetry(MitigationOptionsPolicy::_POLICY_ACTION,ushort const *,_IMAGE_MITIGATION_POLICY,long)

- ea: `0x180013128`
- end: `0x1800132c2`
- name: `?LogImageMitigationAuditPolicyFailureTelemetry@TelemetryHelper@MitigationOptionsPolicy@@SAXW4_POLICY_ACTION@2@PEBGW4_IMAGE_MITIGATION_POLICY@@J@Z`
- size: `410`
- prototype: `__int64 __fastcall(int, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001086c`
- `0x180010e10`

## callees

- `0x180001514`
- `0x18000160c`
- `0x180013128`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180013181`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180013181`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::TelemetryHelper::LogImageMitigationAuditPolicyFailureTelemetry(
        int a1,
        const wchar_t *a2,
        int a3)
{
  const wchar_t *v4; // rsi
  const wchar_t *v5; // rdi
  __int64 result; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  char *v10; // rdx
  const wchar_t *v11; // [rsp+40h] [rbp-10h] BYREF
  const wchar_t *v12; // [rsp+78h] [rbp+28h] BYREF

  if ( a3 < 19 )
    v4 = (const wchar_t *)(&MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames)[a3];
  else
    v4 = L"Unknown";
  v5 = L"*System Defaults*";
  if ( a2 )
    v5 = a2;
  result = RtlRunOnceExecuteOnce(
             &MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce,
             MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce,
             0,
             0);
  if ( !a1 )
  {
    result = (unsigned int)dword_18001C038;
    if ( (unsigned int)dword_18001C038 <= 5 )
      return result;
    result = qword_18001C048;
    if ( (qword_18001C048 & 0x400000000000LL) == 0 )
      return result;
    result = qword_18001C050 & 0x400000000000LL;
    if ( (qword_18001C050 & 0x400000000000LL) != qword_18001C050 )
      return result;
    v10 = (char *)&unk_180018DE8;
LABEL_21:
    v12 = v4;
    v11 = v5;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
             0x400000000000LL,
             (__int64)v10,
             v7,
             v8,
             &v11,
             &v12);
  }
  v9 = a1 - 1;
  if ( !v9 )
  {
    result = (unsigned int)dword_18001C038;
    if ( (unsigned int)dword_18001C038 <= 5 )
      return result;
    result = qword_18001C048;
    if ( (qword_18001C048 & 0x400000000000LL) == 0 )
      return result;
    result = qword_18001C050 & 0x400000000000LL;
    if ( (qword_18001C050 & 0x400000000000LL) != qword_18001C050 )
      return result;
    v10 = &byte_180018C57;
    goto LABEL_21;
  }
  if ( v9 == 1 )
  {
    result = (unsigned int)dword_18001C038;
    if ( (unsigned int)dword_18001C038 > 5 )
    {
      result = qword_18001C048;
      if ( (qword_18001C048 & 0x400000000000LL) != 0 )
      {
        result = qword_18001C050 & 0x400000000000LL;
        if ( (qword_18001C050 & 0x400000000000LL) == qword_18001C050 )
        {
          v12 = v5;
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                   0x400000000000LL,
                   (__int64)&dword_180018C04,
                   v7,
                   v8,
                   &v12);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013128  mov     [rsp-18h+arg_10], rbx
0x18001312d  mov     [rsp-18h+arg_18], rsi
0x180013132  push    rbp
0x180013133  push    rdi
0x180013134  push    r14
0x180013136  mov     rbp, rsp
0x180013139  sub     rsp, 50h
0x18001313d  mov     r14d, r9d
0x180013140  mov     ebx, ecx
0x180013142  cmp     r8d, 13h
0x180013146  jl      short loc_180013151
0x180013148  lea     rsi, aUnknown; "Unknown"
0x18001314f  jmp     short loc_18001315F
0x180013151  movsxd  rax, r8d
0x180013154  lea     rsi, ?s_mitigationNames@TelemetryHelper@MitigationOptionsPolicy@@0PAPEBGA; ushort const * near * MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames
0x18001315b  mov     rsi, [rsi+rax*8]
0x18001315f  test    rdx, rdx
0x180013162  lea     rdi, aSystemDefaults; "*System Defaults*"
0x180013169  lea     rcx, ?ImageMitigationPolicyTelemetryInitRunOnce@MitigationOptionsPolicy@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce
0x180013170  cmovnz  rdi, rdx
0x180013174  xor     r9d, r9d
0x180013177  xor     r8d, r8d
0x18001317a  lea     rdx, ?ImageMitigationPolicyTelemetryInitOnce@MitigationOptionsPolicy@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce(_RTL_RUN_ONCE *,void *,void * *)
0x180013181  call    cs:__imp_RtlRunOnceExecuteOnce
0x180013187  test    ebx, ebx
0x180013189  jz      loc_180013247
0x18001318f  sub     ebx, 1
0x180013192  jz      short loc_180013207
0x180013194  cmp     ebx, 1
0x180013197  jnz     loc_1800132AD
0x18001319d  mov     eax, cs:dword_18001C038
0x1800131a3  cmp     eax, 5
0x1800131a6  jbe     loc_1800132AD
0x1800131ac  mov     rdx, cs:qword_18001C050
0x1800131b3  mov     rcx, 400000000000h
0x1800131bd  mov     rax, cs:qword_18001C048
0x1800131c4  test    rcx, rax
0x1800131c7  jz      loc_1800132AD
0x1800131cd  mov     rax, rdx
0x1800131d0  and     rax, rcx
0x1800131d3  cmp     rax, rdx
0x1800131d6  jnz     loc_1800132AD
0x1800131dc  lea     rax, [rbp+arg_0]
0x1800131e0  mov     [rbp+arg_0], r14d
0x1800131e4  mov     [rsp+50h+var_28], rax
0x1800131e9  lea     rdx, dword_180018C04
0x1800131f0  lea     rax, [rbp+arg_8]
0x1800131f4  mov     [rbp+arg_8], rdi
0x1800131f8  mov     [rsp+50h+var_30], rax
0x1800131fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013202  jmp     loc_1800132AD
0x180013207  mov     eax, cs:dword_18001C038
0x18001320d  cmp     eax, 5
0x180013210  jbe     loc_1800132AD
0x180013216  mov     rdx, cs:qword_18001C050
0x18001321d  mov     rcx, 400000000000h
0x180013227  mov     rax, cs:qword_18001C048
0x18001322e  test    rcx, rax
0x180013231  jz      short loc_1800132AD
0x180013233  mov     rax, rdx
0x180013236  and     rax, rcx
0x180013239  cmp     rax, rdx
0x18001323c  jnz     short loc_1800132AD
0x18001323e  lea     rdx, byte_180018C57
0x180013245  jmp     short loc_180013281
0x180013247  mov     eax, cs:dword_18001C038
0x18001324d  cmp     eax, 5
0x180013250  jbe     short loc_1800132AD
0x180013252  mov     rdx, cs:qword_18001C050
0x180013259  mov     rcx, 400000000000h
0x180013263  mov     rax, cs:qword_18001C048
0x18001326a  test    rcx, rax
0x18001326d  jz      short loc_1800132AD
0x18001326f  mov     rax, rdx
0x180013272  and     rax, rcx
0x180013275  cmp     rax, rdx
0x180013278  jnz     short loc_1800132AD
0x18001327a  lea     rdx, unk_180018DE8
0x180013281  lea     rax, [rbp+arg_0]
0x180013285  mov     [rsp+50h+var_20], rax
0x18001328a  lea     rax, [rbp+arg_8]
0x18001328e  mov     [rsp+50h+var_28], rax
0x180013293  lea     rax, [rbp+var_10]
0x180013297  mov     [rsp+50h+var_30], rax
0x18001329c  mov     [rbp+arg_0], r14d
0x1800132a0  mov     [rbp+arg_8], rsi
0x1800132a4  mov     [rbp+var_10], rdi
0x1800132a8  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800132ad  lea     r11, [rsp+50h+var_s0]
0x1800132b2  mov     rbx, [r11+30h]
0x1800132b6  mov     rsi, [r11+38h]
0x1800132ba  mov     rsp, r11
0x1800132bd  pop     r14
0x1800132bf  pop     rdi
0x1800132c0  pop     rbp
0x1800132c1  retn
```
