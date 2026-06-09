# MitigationOptionsPolicy::TelemetryHelper::LogStoredMitigationPolicyValueTelemetry(ushort const *,_IMAGE_MITIGATION_POLICY,void *,ulong,void *,ulong)

- ea: `0x180013720`
- end: `0x18001390f`
- name: `?LogStoredMitigationPolicyValueTelemetry@TelemetryHelper@MitigationOptionsPolicy@@SAXPEBGW4_IMAGE_MITIGATION_POLICY@@PEAXK2K@Z`
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
- `0x180013720`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180013798`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180013798`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::TelemetryHelper::LogStoredMitigationPolicyValueTelemetry(
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
            (__int64)word_180018EAA,
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
          (__int64)byte_180018F0D,
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
0x180013720  mov     [rsp-8+arg_0], rbx
0x180013725  mov     [rsp-8+arg_8], rsi
0x18001372a  push    rbp
0x18001372b  push    rdi
0x18001372c  push    r12
0x18001372e  push    r14
0x180013730  push    r15
0x180013732  lea     rbp, [rsp-27h]
0x180013737  sub     rsp, 0B0h
0x18001373e  mov     rax, cs:__security_cookie
0x180013745  xor     rax, rsp
0x180013748  mov     [rbp+47h+var_30], rax
0x18001374c  mov     r15d, r9d
0x18001374f  mov     r12, r8
0x180013752  mov     rsi, [rbp+47h+arg_20]
0x180013756  mov     r14d, [rbp+47h+arg_28]
0x18001375a  cmp     edx, 13h
0x18001375d  jl      short loc_180013768
0x18001375f  lea     rbx, aUnknown; "Unknown"
0x180013766  jmp     short loc_180013776
0x180013768  movsxd  rax, edx
0x18001376b  lea     rbx, ?s_mitigationNames@TelemetryHelper@MitigationOptionsPolicy@@0PAPEBGA; ushort const * near * MitigationOptionsPolicy::TelemetryHelper::s_mitigationNames
0x180013772  mov     rbx, [rbx+rax*8]
0x180013776  lea     rdi, aSystemDefaults; "*System Defaults*"
0x18001377d  test    rcx, rcx
0x180013780  cmovnz  rdi, rcx
0x180013784  xor     r9d, r9d
0x180013787  xor     r8d, r8d
0x18001378a  lea     rdx, ?ImageMitigationPolicyTelemetryInitOnce@MitigationOptionsPolicy@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitOnce(_RTL_RUN_ONCE *,void *,void * *)
0x180013791  lea     rcx, ?ImageMitigationPolicyTelemetryInitRunOnce@MitigationOptionsPolicy@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE MitigationOptionsPolicy::ImageMitigationPolicyTelemetryInitRunOnce
0x180013798  call    cs:__imp_RtlRunOnceExecuteOnce
0x18001379e  mov     eax, cs:dword_18001C038
0x1800137a4  test    r15d, r15d
0x1800137a7  jz      loc_180013865
0x1800137ad  cmp     eax, 5
0x1800137b0  jbe     loc_1800138E7
0x1800137b6  mov     rcx, cs:qword_18001C050
0x1800137bd  mov     rax, cs:qword_18001C048
0x1800137c4  mov     rdx, 400000000000h
0x1800137ce  test    rdx, rax
0x1800137d1  jz      loc_1800138E7
0x1800137d7  mov     rax, rcx
0x1800137da  and     rax, rdx
0x1800137dd  cmp     rax, rcx
0x1800137e0  jnz     loc_1800138E7
0x1800137e6  mov     r8d, r14d
0x1800137e9  mov     rdx, rsi
0x1800137ec  lea     rcx, [rbp+47h+var_70]
0x1800137f0  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x1800137f5  nop
0x1800137f6  cmp     qword ptr [rax+18h], 7
0x1800137fb  jbe     short loc_180013800
0x1800137fd  mov     rax, [rax]
0x180013800  mov     [rbp+47h+var_78], rax
0x180013804  mov     r8d, r15d
0x180013807  mov     rdx, r12
0x18001380a  lea     rcx, [rbp+47h+var_50]
0x18001380e  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x180013813  cmp     qword ptr [rax+18h], 7
0x180013818  jbe     short loc_18001381D
0x18001381a  mov     rax, [rax]
0x18001381d  mov     [rbp+47h+var_90], rax
0x180013821  mov     [rbp+47h+var_88], rbx
0x180013825  mov     [rbp+47h+var_80], rdi
0x180013829  lea     rax, [rbp+47h+var_78]
0x18001382d  mov     [rsp+0D0h+var_98], rax
0x180013832  lea     rax, [rbp+47h+var_90]
0x180013836  mov     [rsp+0D0h+var_A0], rax
0x18001383b  lea     rax, [rbp+47h+var_88]
0x18001383f  mov     [rsp+0D0h+var_A8], rax
0x180013844  lea     rax, [rbp+47h+var_80]
0x180013848  mov     [rsp+0D0h+var_B0], rax
0x18001384d  lea     rdx, word_180018EAA
0x180013854  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180013859  lea     rcx, [rbp+47h+var_50]
0x18001385d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013862  nop
0x180013863  jmp     short loc_1800138DE
0x180013865  cmp     eax, 5
0x180013868  jbe     short loc_1800138E7
0x18001386a  mov     rcx, cs:qword_18001C050
0x180013871  mov     rax, cs:qword_18001C048
0x180013878  mov     rdx, 200000000000h
0x180013882  test    rdx, rax
0x180013885  jz      short loc_1800138E7
0x180013887  mov     rax, rcx
0x18001388a  and     rax, rdx
0x18001388d  cmp     rax, rcx
0x180013890  jnz     short loc_1800138E7
0x180013892  mov     r8d, r14d
0x180013895  mov     rdx, rsi
0x180013898  lea     rcx, [rbp+47h+var_70]
0x18001389c  call    ?Base64Encode@TelemetryHelper@MitigationOptionsPolicy@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXK@Z; MitigationOptionsPolicy::TelemetryHelper::Base64Encode(void *,ulong)
0x1800138a1  cmp     qword ptr [rax+18h], 7
0x1800138a6  jbe     short loc_1800138AB
0x1800138a8  mov     rax, [rax]
0x1800138ab  mov     [rbp+47h+var_80], rax
0x1800138af  mov     [rbp+47h+var_88], rbx
0x1800138b3  mov     [rbp+47h+var_90], rdi
0x1800138b7  lea     rax, [rbp+47h+var_80]
0x1800138bb  mov     [rsp+0D0h+var_A0], rax
0x1800138c0  lea     rax, [rbp+47h+var_88]
0x1800138c4  mov     [rsp+0D0h+var_A8], rax
0x1800138c9  lea     rax, [rbp+47h+var_90]
0x1800138cd  mov     [rsp+0D0h+var_B0], rax
0x1800138d2  lea     rdx, byte_180018F0D
0x1800138d9  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800138de  lea     rcx, [rbp+47h+var_70]
0x1800138e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800138e7  mov     rcx, [rbp+47h+var_30]
0x1800138eb  xor     rcx, rsp; StackCookie
0x1800138ee  call    __security_check_cookie
0x1800138f3  lea     r11, [rsp+0D0h+var_20]
0x1800138fb  mov     rbx, [r11+30h]
0x1800138ff  mov     rsi, [r11+38h]
0x180013903  mov     rsp, r11
0x180013906  pop     r15
0x180013908  pop     r14
0x18001390a  pop     r12
0x18001390c  pop     rdi
0x18001390d  pop     rbp
0x18001390e  retn
```
