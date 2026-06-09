# MitigationOptionsPolicy::TelemetryHelper::LogImageMitigationPolicyFailureTelemetry(MitigationOptionsPolicy::_POLICY_ACTION,ushort const *,_IMAGE_MITIGATION_POLICY,long)

- ea: `0x1800132c8`
- end: `0x180013462`
- name: `?LogImageMitigationPolicyFailureTelemetry@TelemetryHelper@MitigationOptionsPolicy@@SAXW4_POLICY_ACTION@2@PEBGW4_IMAGE_MITIGATION_POLICY@@J@Z`
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
- `0x1800132c8`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180013321`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180013321`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::TelemetryHelper::LogImageMitigationPolicyFailureTelemetry(
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
    v10 = &byte_180018BAF;
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
    v10 = &byte_180018D47;
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
                   (__int64)word_180018D9A,
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
0x1800132c8  mov     [rsp-18h+arg_10], rbx
0x1800132cd  mov     [rsp-18h+arg_18], rsi
0x1800132d2  push    rbp
0x1800132d3  push    rdi
0x1800132d4  push    r14
0x1800132d6  mov     rbp, rsp
0x1800132d9  sub     rsp, 50h
0x1800132dd  mov     r14d, r9d
0x1800132e0  mov     ebx, ecx
0x1800132e2  cmp     r8d, 13h
0x1800132e6  jl      short loc_1800132F1
0x1800132e8  lea     rsi, aUnknown; "Unknown"
0x1800132ef  jmp     short loc_1800132FF
0x1800132f1  movsxd  rax, r8d
0x1800132f4  lea     rsi, ?s_mitigationNames@TelemetryHelper@MitigationOptionsPolicy@@0PAPEBGA; ushort const * near * MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames
0x1800132fb  mov     rsi, [rsi+rax*8]
0x1800132ff  test    rdx, rdx
0x180013302  lea     rdi, aSystemDefaults; "*System Defaults*"
0x180013309  lea     rcx, ?ImageMitigationPolicyTelemetryInitRunOnce@MitigationOptionsPolicy@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce
0x180013310  cmovnz  rdi, rdx
0x180013314  xor     r9d, r9d
0x180013317  xor     r8d, r8d
0x18001331a  lea     rdx, ?ImageMitigationPolicyTelemetryInitOnce@MitigationOptionsPolicy@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce(_RTL_RUN_ONCE *,void *,void * *)
0x180013321  call    cs:__imp_RtlRunOnceExecuteOnce
0x180013327  test    ebx, ebx
0x180013329  jz      loc_1800133E7
0x18001332f  sub     ebx, 1
0x180013332  jz      short loc_1800133A7
0x180013334  cmp     ebx, 1
0x180013337  jnz     loc_18001344D
0x18001333d  mov     eax, cs:dword_18001C038
0x180013343  cmp     eax, 5
0x180013346  jbe     loc_18001344D
0x18001334c  mov     rdx, cs:qword_18001C050
0x180013353  mov     rcx, 400000000000h
0x18001335d  mov     rax, cs:qword_18001C048
0x180013364  test    rcx, rax
0x180013367  jz      loc_18001344D
0x18001336d  mov     rax, rdx
0x180013370  and     rax, rcx
0x180013373  cmp     rax, rdx
0x180013376  jnz     loc_18001344D
0x18001337c  lea     rax, [rbp+arg_0]
0x180013380  mov     [rbp+arg_0], r14d
0x180013384  mov     [rsp+50h+var_28], rax
0x180013389  lea     rdx, word_180018D9A
0x180013390  lea     rax, [rbp+arg_8]
0x180013394  mov     [rbp+arg_8], rdi
0x180013398  mov     [rsp+50h+var_30], rax
0x18001339d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800133a2  jmp     loc_18001344D
0x1800133a7  mov     eax, cs:dword_18001C038
0x1800133ad  cmp     eax, 5
0x1800133b0  jbe     loc_18001344D
0x1800133b6  mov     rdx, cs:qword_18001C050
0x1800133bd  mov     rcx, 400000000000h
0x1800133c7  mov     rax, cs:qword_18001C048
0x1800133ce  test    rcx, rax
0x1800133d1  jz      short loc_18001344D
0x1800133d3  mov     rax, rdx
0x1800133d6  and     rax, rcx
0x1800133d9  cmp     rax, rdx
0x1800133dc  jnz     short loc_18001344D
0x1800133de  lea     rdx, byte_180018D47
0x1800133e5  jmp     short loc_180013421
0x1800133e7  mov     eax, cs:dword_18001C038
0x1800133ed  cmp     eax, 5
0x1800133f0  jbe     short loc_18001344D
0x1800133f2  mov     rdx, cs:qword_18001C050
0x1800133f9  mov     rcx, 400000000000h
0x180013403  mov     rax, cs:qword_18001C048
0x18001340a  test    rcx, rax
0x18001340d  jz      short loc_18001344D
0x18001340f  mov     rax, rdx
0x180013412  and     rax, rcx
0x180013415  cmp     rax, rdx
0x180013418  jnz     short loc_18001344D
0x18001341a  lea     rdx, byte_180018BAF
0x180013421  lea     rax, [rbp+arg_0]
0x180013425  mov     [rsp+50h+var_20], rax
0x18001342a  lea     rax, [rbp+arg_8]
0x18001342e  mov     [rsp+50h+var_28], rax
0x180013433  lea     rax, [rbp+var_10]
0x180013437  mov     [rsp+50h+var_30], rax
0x18001343c  mov     [rbp+arg_0], r14d
0x180013440  mov     [rbp+arg_8], rsi
0x180013444  mov     [rbp+var_10], rdi
0x180013448  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001344d  lea     r11, [rsp+50h+var_s0]
0x180013452  mov     rbx, [r11+30h]
0x180013456  mov     rsi, [r11+38h]
0x18001345a  mov     rsp, r11
0x18001345d  pop     r14
0x18001345f  pop     rdi
0x180013460  pop     rbp
0x180013461  retn
```
