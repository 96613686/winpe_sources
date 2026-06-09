# AIXTelemetry::PolicyTaskShouldRun_(bool,bool,bool,bool,bool,bool,bool,bool,ulong)

- ea: `0x18002a7b4`
- end: `0x18002ac81`
- name: `?PolicyTaskShouldRun_@AIXTelemetry@@QEAAX_N0000000K@Z`
- size: `1229`
- prototype: `void __fastcall(AIXTelemetry *__hidden this, bool, bool, bool, bool, bool, bool, bool, bool, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002b864`

## callees

- `0x18000163c`
- `0x18000191c`
- `0x180002590`
- `0x18000896c`
- `0x180020d3c`
- `0x180020f7c`
- `0x18002a7b4`

## pseudocode

```c
void __fastcall AIXTelemetry::PolicyTaskShouldRun_(
        AIXTelemetry *this,
        bool a2,
        bool a3,
        bool a4,
        bool a5,
        bool a6,
        bool a7,
        bool a8,
        bool a9,
        unsigned int a10)
{
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r10
  __int64 v15; // rax
  unsigned __int8 *v16; // rdx
  bool *v17; // rcx
  const struct _tlgProvider_t *v18; // rax
  int v19; // r9d
  const struct _tlgProvider_t *v20; // r8
  __int64 v21; // rax
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // rax
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // rax
  ULONG v26; // [rsp+20h] [rbp-E0h]
  bool v27; // [rsp+70h] [rbp-90h] BYREF
  bool v28; // [rsp+71h] [rbp-8Fh] BYREF
  bool v29; // [rsp+72h] [rbp-8Eh] BYREF
  bool v30; // [rsp+73h] [rbp-8Dh] BYREF
  bool v31; // [rsp+74h] [rbp-8Ch] BYREF
  bool v32; // [rsp+75h] [rbp-8Bh] BYREF
  bool v33; // [rsp+76h] [rbp-8Ah] BYREF
  bool v34; // [rsp+77h] [rbp-89h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+90h] [rbp-70h] BYREF
  bool *v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  bool *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  bool *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  bool *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  bool *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  bool *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  bool *v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  bool *v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]
  unsigned int *v54; // [rsp+130h] [rbp+30h]
  __int64 v55; // [rsp+138h] [rbp+38h]
  _QWORD *v56; // [rsp+140h] [rbp+40h]
  __int64 v57; // [rsp+148h] [rbp+48h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl'::`2'::impl) )
  {
    v13 = AIXTelemetryLogging::Provider();
    v14 = (__int64)v13;
    if ( *(_DWORD *)v13 > 5u )
    {
      v15 = *((_QWORD *)v13 + 3);
      if ( (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0 && (v15 & 0x400000000000LL) == v15 )
      {
        v35 = a10;
        v16 = (unsigned __int8 *)byte_18003A0C3;
        v34 = a9;
        v27 = a8;
        v28 = a7;
        v50 = &v27;
        v29 = a6;
        v48 = &v28;
        v30 = a5;
        v46 = &v29;
        v56 = v36;
        v44 = &v30;
        v54 = &v35;
        v42 = &v31;
        v52 = &v34;
        v40 = &v32;
        v17 = &v33;
        v26 = 12;
        v36[0] = 0x1000000;
        v31 = a4;
        v32 = a3;
        v33 = a2;
        v57 = 8;
        v55 = 4;
        v53 = 1;
LABEL_21:
        v51 = 1;
        goto LABEL_22;
      }
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl'::`2'::impl) )
  {
    v18 = AIXTelemetryLogging::Provider();
    v20 = v18;
    if ( *(_DWORD *)v18 > 5u )
    {
      v21 = *((_QWORD *)v18 + 3);
      if ( (*((_QWORD *)v20 + 2) & 0x400000000000LL) != 0 && (v21 & 0x400000000000LL) == v21 )
      {
        v33 = a9;
        v32 = a8;
        v31 = a7;
        v30 = a6;
        v29 = a5;
        v36[0] = 0x1000000;
        v28 = a4;
        v27 = a3;
        v34 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          (_DWORD)v20,
          (unsigned int)byte_18003A1B1,
          (_DWORD)v20,
          v19,
          (__int64)&v34,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)v36);
      }
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl'::`2'::impl) )
  {
    v22 = AIXTelemetryLogging::Provider();
    v14 = (__int64)v22;
    if ( *(_DWORD *)v22 > 5u )
    {
      v23 = *((_QWORD *)v22 + 3);
      if ( (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0 && (v23 & 0x400000000000LL) == v23 )
      {
        v33 = a9;
        v16 = (unsigned __int8 *)&dword_18003A28C;
        v35 = a10;
        v50 = (bool *)&v35;
        v32 = a7;
        v48 = &v32;
        v31 = a6;
        v46 = &v31;
        v30 = a5;
        v44 = &v30;
        v54 = (unsigned int *)v36;
        v42 = &v29;
        v52 = &v33;
        v40 = &v28;
        v17 = &v27;
        v26 = 11;
        v36[0] = 0x1000000;
        v29 = a4;
        v28 = a3;
        v27 = a2;
        v55 = 8;
        v53 = 1;
        v51 = 4;
LABEL_22:
        v38 = v17;
        v49 = 1;
        v47 = 1;
        v45 = 1;
        v43 = 1;
        v41 = 1;
        v39 = 1;
        tlgWriteTransfer_EventWriteTransfer(v14, v16, 0, 0, v26, &v37);
      }
    }
  }
  else
  {
    v24 = AIXTelemetryLogging::Provider();
    v14 = (__int64)v24;
    if ( *(_DWORD *)v24 > 5u )
    {
      v25 = *((_QWORD *)v24 + 3);
      if ( (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0 && (v25 & 0x400000000000LL) == v25 )
      {
        v33 = a9;
        v16 = (unsigned __int8 *)&word_18003A356;
        v32 = a7;
        v48 = &v32;
        v31 = a6;
        v46 = &v31;
        v30 = a5;
        v44 = &v30;
        v52 = (bool *)v36;
        v42 = &v29;
        v50 = &v33;
        v40 = &v28;
        v17 = &v27;
        v26 = 10;
        v36[0] = 0x1000000;
        v29 = a4;
        v28 = a3;
        v27 = a2;
        v53 = 8;
        goto LABEL_21;
      }
    }
  }
}

```

## disassembly

```asm
0x18002a7b4  push    rbp
0x18002a7b6  push    rbx
0x18002a7b7  push    rsi
0x18002a7b8  push    rdi
0x18002a7b9  push    r14
0x18002a7bb  lea     rbp, [rsp-60h]
0x18002a7c0  sub     rsp, 160h
0x18002a7c7  mov     rax, cs:__security_cookie
0x18002a7ce  xor     rax, rsp
0x18002a7d1  mov     [rbp+80h+var_30], rax
0x18002a7d5  mov     bl, r9b
0x18002a7d8  mov     dil, r8b
0x18002a7db  mov     sil, dl
0x18002a7de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55856303@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303> `wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl(void)'::`2'::impl
0x18002a7e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(void)
0x18002a7ea  test    al, al
0x18002a7ec  jz      loc_18002A91F
0x18002a7f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617> `wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl(void)'::`2'::impl
0x18002a7f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(void)
0x18002a7fe  test    al, al
0x18002a800  jz      loc_18002A91F
0x18002a806  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18002a80b  mov     r10, rax
0x18002a80e  mov     ecx, [rax]
0x18002a810  cmp     ecx, 5
0x18002a813  jbe     loc_18002AC67
0x18002a819  mov     rax, [rax+18h]
0x18002a81d  mov     rdx, 400000000000h
0x18002a827  mov     rcx, [r10+10h]
0x18002a82b  test    rdx, rcx
0x18002a82e  jz      loc_18002AC67
0x18002a834  mov     rcx, rax
0x18002a837  and     rcx, rdx
0x18002a83a  cmp     rcx, rax
0x18002a83d  jnz     loc_18002AC67
0x18002a843  mov     eax, [rbp+80h+arg_48]
0x18002a849  lea     rcx, [rsp+180h+var_110]
0x18002a84e  mov     [rsp+180h+var_108], eax
0x18002a852  lea     rdx, byte_18003A0C3
0x18002a859  mov     al, [rbp+80h+arg_40]
0x18002a85f  mov     [rsp+180h+var_109], al
0x18002a863  mov     al, [rbp+80h+arg_38]
0x18002a869  mov     [rsp+180h+var_110], al
0x18002a86d  mov     al, [rbp+80h+arg_30]
0x18002a873  mov     [rsp+180h+var_10F], al
0x18002a877  mov     al, [rbp+80h+arg_28]
0x18002a87d  mov     [rbp+80h+var_70], rcx
0x18002a881  lea     rcx, [rsp+180h+var_10F]
0x18002a886  mov     [rsp+180h+var_10E], al
0x18002a88a  mov     al, [rbp+80h+arg_20]
0x18002a890  mov     [rbp+80h+var_80], rcx
0x18002a894  lea     rcx, [rsp+180h+var_10E]
0x18002a899  mov     [rsp+180h+var_10D], al
0x18002a89d  lea     rax, [rbp+80h+var_100]
0x18002a8a1  mov     [rbp+80h+var_90], rcx
0x18002a8a5  lea     rcx, [rsp+180h+var_10D]
0x18002a8aa  mov     [rbp+80h+var_40], rax
0x18002a8ae  lea     rax, [rsp+180h+var_108]
0x18002a8b3  mov     [rbp+80h+var_A0], rcx
0x18002a8b7  lea     rcx, [rsp+180h+var_10C]
0x18002a8bc  mov     [rbp+80h+var_50], rax
0x18002a8c0  lea     rax, [rsp+180h+var_109]
0x18002a8c5  mov     [rbp+80h+var_B0], rcx
0x18002a8c9  lea     rcx, [rsp+180h+var_10B]
0x18002a8ce  mov     [rbp+80h+var_60], rax
0x18002a8d2  lea     rax, [rbp+80h+var_F0]
0x18002a8d6  mov     [rsp+180h+var_158], rax
0x18002a8db  mov     [rbp+80h+var_C0], rcx
0x18002a8df  lea     rcx, [rsp+180h+var_10A]
0x18002a8e4  mov     dword ptr [rsp+180h+var_160], 0Ch
0x18002a8ec  mov     [rbp+80h+var_100], 1000000h
0x18002a8f4  mov     [rsp+180h+var_10C], bl
0x18002a8f8  mov     [rsp+180h+var_10B], dil
0x18002a8fd  mov     [rsp+180h+var_10A], sil
0x18002a902  mov     [rbp+80h+var_38], 8
0x18002a90a  mov     [rbp+80h+var_48], 4
0x18002a912  mov     [rbp+80h+var_58], 1
0x18002a91a  jmp     loc_18002AC1D
0x18002a91f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55856303@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303> `wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl(void)'::`2'::impl
0x18002a926  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(void)
0x18002a92b  test    al, al
0x18002a92d  jz      loc_18002AA25
0x18002a933  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18002a938  mov     r8, rax
0x18002a93b  mov     ecx, [rax]
0x18002a93d  cmp     ecx, 5
0x18002a940  jbe     loc_18002AC67
0x18002a946  mov     rax, [rax+18h]
0x18002a94a  mov     rdx, 400000000000h
0x18002a954  mov     rcx, [r8+10h]
0x18002a958  test    rdx, rcx
0x18002a95b  jz      loc_18002AC67
0x18002a961  mov     rcx, rax
0x18002a964  and     rcx, rdx
0x18002a967  cmp     rcx, rax
0x18002a96a  jnz     loc_18002AC67
0x18002a970  mov     al, [rbp+80h+arg_40]
0x18002a976  lea     rdx, byte_18003A1B1
0x18002a97d  mov     [rsp+180h+var_10A], al
0x18002a981  mov     rcx, r8
0x18002a984  mov     al, [rbp+80h+arg_38]
0x18002a98a  mov     [rsp+180h+var_10B], al
0x18002a98e  mov     al, [rbp+80h+arg_30]
0x18002a994  mov     [rsp+180h+var_10C], al
0x18002a998  mov     al, [rbp+80h+arg_28]
0x18002a99e  mov     [rsp+180h+var_10D], al
0x18002a9a2  mov     al, [rbp+80h+arg_20]
0x18002a9a8  mov     [rsp+180h+var_10E], al
0x18002a9ac  lea     rax, [rbp+80h+var_100]
0x18002a9b0  mov     [rsp+180h+var_120], rax
0x18002a9b5  lea     rax, [rsp+180h+var_10A]
0x18002a9ba  mov     [rsp+180h+var_128], rax
0x18002a9bf  lea     rax, [rsp+180h+var_10B]
0x18002a9c4  mov     [rsp+180h+var_130], rax
0x18002a9c9  lea     rax, [rsp+180h+var_10C]
0x18002a9ce  mov     [rsp+180h+var_138], rax
0x18002a9d3  lea     rax, [rsp+180h+var_10D]
0x18002a9d8  mov     [rsp+180h+var_140], rax
0x18002a9dd  lea     rax, [rsp+180h+var_10E]
0x18002a9e2  mov     [rsp+180h+var_148], rax
0x18002a9e7  lea     rax, [rsp+180h+var_10F]
0x18002a9ec  mov     [rsp+180h+var_150], rax
0x18002a9f1  lea     rax, [rsp+180h+var_110]
0x18002a9f6  mov     [rsp+180h+var_158], rax
0x18002a9fb  lea     rax, [rsp+180h+var_109]
0x18002aa00  mov     [rsp+180h+var_160], rax
0x18002aa05  mov     [rbp+80h+var_100], 1000000h
0x18002aa0d  mov     [rsp+180h+var_10F], bl
0x18002aa11  mov     [rsp+180h+var_110], dil
0x18002aa16  mov     [rsp+180h+var_109], sil
0x18002aa1b  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3333333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18002aa20  jmp     loc_18002AC67
0x18002aa25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617> `wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl(void)'::`2'::impl
0x18002aa2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(void)
0x18002aa31  test    al, al
0x18002aa33  jz      loc_18002AB3F
0x18002aa39  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18002aa3e  mov     r10, rax
0x18002aa41  mov     ecx, [rax]
0x18002aa43  cmp     ecx, 5
0x18002aa46  jbe     loc_18002AC67
0x18002aa4c  mov     rax, [rax+18h]
0x18002aa50  mov     rdx, 400000000000h
0x18002aa5a  mov     rcx, [r10+10h]
0x18002aa5e  test    rdx, rcx
0x18002aa61  jz      loc_18002AC67
0x18002aa67  mov     rcx, rax
0x18002aa6a  and     rcx, rdx
0x18002aa6d  cmp     rcx, rax
0x18002aa70  jnz     loc_18002AC67
0x18002aa76  mov     al, [rbp+80h+arg_40]
0x18002aa7c  lea     rcx, [rsp+180h+var_108]
0x18002aa81  mov     [rsp+180h+var_10A], al
0x18002aa85  lea     rdx, dword_18003A28C
0x18002aa8c  mov     eax, [rbp+80h+arg_48]
0x18002aa92  mov     [rsp+180h+var_108], eax
0x18002aa96  mov     al, [rbp+80h+arg_30]
0x18002aa9c  mov     [rbp+80h+var_70], rcx
0x18002aaa0  lea     rcx, [rsp+180h+var_10B]
0x18002aaa5  mov     [rsp+180h+var_10B], al
0x18002aaa9  mov     al, [rbp+80h+arg_28]
0x18002aaaf  mov     [rbp+80h+var_80], rcx
0x18002aab3  lea     rcx, [rsp+180h+var_10C]
0x18002aab8  mov     [rsp+180h+var_10C], al
0x18002aabc  mov     al, [rbp+80h+arg_20]
0x18002aac2  mov     [rbp+80h+var_90], rcx
0x18002aac6  lea     rcx, [rsp+180h+var_10D]
0x18002aacb  mov     [rsp+180h+var_10D], al
0x18002aacf  lea     rax, [rbp+80h+var_100]
0x18002aad3  mov     [rbp+80h+var_A0], rcx
0x18002aad7  lea     rcx, [rsp+180h+var_10E]
0x18002aadc  mov     [rbp+80h+var_50], rax
0x18002aae0  lea     rax, [rsp+180h+var_10A]
0x18002aae5  mov     [rbp+80h+var_B0], rcx
0x18002aae9  lea     rcx, [rsp+180h+var_10F]
0x18002aaee  mov     [rbp+80h+var_60], rax
0x18002aaf2  lea     rax, [rbp+80h+var_F0]
0x18002aaf6  mov     [rsp+180h+var_158], rax
0x18002aafb  mov     [rbp+80h+var_C0], rcx
0x18002aaff  lea     rcx, [rsp+180h+var_110]
0x18002ab04  mov     dword ptr [rsp+180h+var_160], 0Bh
0x18002ab0c  mov     [rbp+80h+var_100], 1000000h
0x18002ab14  mov     [rsp+180h+var_10E], bl
0x18002ab18  mov     [rsp+180h+var_10F], dil
0x18002ab1d  mov     [rsp+180h+var_110], sil
0x18002ab22  mov     [rbp+80h+var_48], 8
0x18002ab2a  mov     [rbp+80h+var_58], 1
0x18002ab32  mov     [rbp+80h+var_68], 4
0x18002ab3a  jmp     loc_18002AC25
0x18002ab3f  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18002ab44  mov     r10, rax
0x18002ab47  mov     ecx, [rax]
0x18002ab49  cmp     ecx, 5
0x18002ab4c  jbe     loc_18002AC67
0x18002ab52  mov     rax, [rax+18h]
0x18002ab56  mov     rdx, 400000000000h
0x18002ab60  mov     rcx, [r10+10h]
0x18002ab64  test    rdx, rcx
0x18002ab67  jz      loc_18002AC67
0x18002ab6d  mov     rcx, rax
0x18002ab70  and     rcx, rdx
0x18002ab73  cmp     rcx, rax
0x18002ab76  jnz     loc_18002AC67
0x18002ab7c  mov     al, [rbp+80h+arg_40]
0x18002ab82  lea     rcx, [rsp+180h+var_10B]
0x18002ab87  mov     [rsp+180h+var_10A], al
0x18002ab8b  lea     rdx, word_18003A356
0x18002ab92  mov     al, [rbp+80h+arg_30]
0x18002ab98  mov     [rsp+180h+var_10B], al
0x18002ab9c  mov     al, [rbp+80h+arg_28]
0x18002aba2  mov     [rbp+80h+var_80], rcx
0x18002aba6  lea     rcx, [rsp+180h+var_10C]
0x18002abab  mov     [rsp+180h+var_10C], al
0x18002abaf  mov     al, [rbp+80h+arg_20]
0x18002abb5  mov     [rbp+80h+var_90], rcx
0x18002abb9  lea     rcx, [rsp+180h+var_10D]
0x18002abbe  mov     [rsp+180h+var_10D], al
0x18002abc2  lea     rax, [rbp+80h+var_100]
0x18002abc6  mov     [rbp+80h+var_A0], rcx
0x18002abca  lea     rcx, [rsp+180h+var_10E]
0x18002abcf  mov     [rbp+80h+var_60], rax
0x18002abd3  lea     rax, [rsp+180h+var_10A]
0x18002abd8  mov     [rbp+80h+var_B0], rcx
0x18002abdc  lea     rcx, [rsp+180h+var_10F]
0x18002abe1  mov     [rbp+80h+var_70], rax
0x18002abe5  lea     rax, [rbp+80h+var_F0]
0x18002abe9  mov     [rsp+180h+var_158], rax
0x18002abee  mov     [rbp+80h+var_C0], rcx
0x18002abf2  lea     rcx, [rsp+180h+var_110]
0x18002abf7  mov     dword ptr [rsp+180h+var_160], 0Ah
0x18002abff  mov     [rbp+80h+var_100], 1000000h
0x18002ac07  mov     [rsp+180h+var_10E], bl
0x18002ac0b  mov     [rsp+180h+var_10F], dil
0x18002ac10  mov     [rsp+180h+var_110], sil
0x18002ac15  mov     [rbp+80h+var_58], 8
0x18002ac1d  mov     [rbp+80h+var_68], 1
0x18002ac25  mov     [rbp+80h+var_D0], rcx
0x18002ac29  xor     r9d, r9d
0x18002ac2c  mov     rcx, r10
0x18002ac2f  mov     [rbp+80h+var_78], 1
0x18002ac37  xor     r8d, r8d
0x18002ac3a  mov     [rbp+80h+var_88], 1
0x18002ac42  mov     [rbp+80h+var_98], 1
0x18002ac4a  mov     [rbp+80h+var_A8], 1
0x18002ac52  mov     [rbp+80h+var_B8], 1
0x18002ac5a  mov     [rbp+80h+var_C8], 1
0x18002ac62  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ac67  mov     rcx, [rbp+80h+var_30]
0x18002ac6b  xor     rcx, rsp; StackCookie
0x18002ac6e  call    __security_check_cookie
0x18002ac73  add     rsp, 160h
0x18002ac7a  pop     r14
0x18002ac7c  pop     rdi
0x18002ac7d  pop     rsi
0x18002ac7e  pop     rbx
0x18002ac7f  pop     rbp
0x18002ac80  retn
```
