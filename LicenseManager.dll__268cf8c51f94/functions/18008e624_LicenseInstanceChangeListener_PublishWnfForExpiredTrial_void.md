# LicenseInstanceChangeListener::PublishWnfForExpiredTrial(void)

- ea: `0x18008e624`
- end: `0x18008ea0c`
- name: `?PublishWnfForExpiredTrial@LicenseInstanceChangeListener@@QEAAXXZ`
- size: `1000`
- prototype: `void __fastcall(LicenseInstanceChangeListener *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180058d60`
- `0x18008c480`

## callees

- `0x180002664`
- `0x180002b14`
- `0x180012dc0`
- `0x180013b50`
- `0x180017230`
- `0x18002aae8`
- `0x180046f88`
- `0x1800593bc`
- `0x18006d3f8`
- `0x180075e60`
- `0x1800769f4`
- `0x18008e624`
- `0x1800b8010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18008e783`
- `ntdll!RtlPublishWnfStateData` at `0x18008e783`

## string_xrefs

- `0x18008e7bf`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008e9bb`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008e9d0`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008e9e5`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008e9fa`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LicenseInstanceChangeListener::PublishWnfForExpiredTrial(LicenseInstanceChangeListener *this)
{
  const unsigned __int16 **v2; // rbx
  const unsigned __int16 *v3; // r8
  int v4; // eax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  const unsigned __int16 *v8; // r8
  int v9; // eax
  int v10; // eax
  int v11; // esi
  const unsigned __int16 *v12; // rcx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  _QWORD *v19; // rcx
  int Format; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v23; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  const char *v26; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 **v28; // [rsp+80h] [rbp-80h] BYREF
  const char *v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v30[2]; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+B0h] [rbp-50h] BYREF
  char v33[4]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v34[255]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v35[133]; // [rsp+2B6h] [rbp+1B6h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v32 = -2143322103;
  memset_0(v33, 0, 0x308u);
  v2 = (const unsigned __int16 **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) <= 7u )
    v3 = (const unsigned __int16 *)((char *)this + 48);
  else
    v3 = *v2;
  v4 = StringCchCopyW(v35, 0x80u, v3);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x228,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v4,
      Format);
  v24 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD **))(**((_QWORD **)this + 23) + 104LL))(
         *((_QWORD *)this + 23),
         &GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57,
         &v24);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v5,
      Format);
  v23 = 0;
  v6 = *v24;
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t **))(v6 + 96))(v24, &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v7,
      Format);
  *(_OWORD *)v30 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v30[0]) = 0;
  if ( v23 )
  {
    std::wstring::assign(v30, v23);
    v8 = (const unsigned __int16 *)v30;
    if ( si128.m128i_i64[1] > 7uLL )
      v8 = v30[0];
  }
  else
  {
    v8 = (const unsigned __int16 *)v30;
  }
  v9 = StringCchCopyW(v34, 0xFFu, v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v9,
      Format);
  v10 = RtlPublishWnfStateData(WNF_LM_APP_LICENSE_EVENT, 0, &v32, 780, 0);
  v11 = v10;
  if ( *((_QWORD *)this + 9) <= 7u )
    v12 = (const unsigned __int16 *)((char *)this + 48);
  else
    v12 = *v2;
  LogMessage(
    2u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
    0x23Au,
    "LicenseInstanceChangeListener::PublishWnfForExpiredTrial",
    (wchar_t *)L"Sent LM_E_SATISFACTION_TRIAL_EXHAUSTED for %s - status = 0x%08x",
    v12,
    v10);
  if ( (v11 & 0xC0000000) == 0xC0000000 )
  {
    if ( _UnitTestWnfCallback )
    {
      _UnitTestWnfCallback((struct _WNF_STATE_NAME)WNF_LM_APP_LICENSE_EVENT, 0, 0, 0, &v32, 0x30Cu);
    }
    else
    {
      LODWORD(v21) = v11;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x245u,
        "LicenseInstanceChangeListener::PublishWnfForExpiredTrial",
        (wchar_t *)L"Failed to send LM_E_SATISFACTION_TRIAL_EXHAUSTED - status = 0x%08x",
        v21);
      if ( (unsigned int)dword_1800F11D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        if ( *((_QWORD *)this + 9) > 7u )
          v2 = (const unsigned __int16 **)*v2;
        v28 = v2;
        v29 = "LicenseInstanceChangeListener::PublishWnfForExpiredTrial";
        v25 = 585;
        v26 = "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp";
        v22 = v11;
        v27 = L"Failed to send LM_E_SATISFACTION_TRIAL_EXHAUSTED";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v13,
          (unsigned int)byte_1800D7533,
          v14,
          v15,
          (__int64)&v27,
          (__int64)&v22,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v29,
          (__int64)&v28);
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 32LL))(*((_QWORD *)this + 23));
    }
  }
  else if ( (unsigned int)dword_1800F11D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
  {
    v27 = v23;
    if ( *((_QWORD *)this + 9) > 7u )
      v2 = (const unsigned __int16 **)*v2;
    v26 = (const char *)v2;
    v22 = -2143322103;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v16,
      (unsigned int)&word_1800D74E6,
      v17,
      v18,
      (__int64)&v22,
      (__int64)&v26,
      (__int64)&v27);
  }
  ContentIdString::~ContentIdString((ContentIdString *)v30);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v23);
  v19 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
  }
}

```

## disassembly

```asm
0x18008e624  push    rbp
0x18008e626  push    rbx
0x18008e627  push    rsi
0x18008e628  push    rdi
0x18008e629  push    r13
0x18008e62b  push    r14
0x18008e62d  lea     rbp, [rsp-2D8h]
0x18008e635  sub     rsp, 3D8h
0x18008e63c  mov     rax, cs:__security_cookie
0x18008e643  xor     rax, rsp
0x18008e646  mov     [rbp+300h+var_40], rax
0x18008e64d  mov     r14, rcx
0x18008e650  mov     [rbp+300h+var_350], 803F8009h
0x18008e657  xor     edx, edx; Val
0x18008e659  mov     r8d, 308h; Size
0x18008e65f  lea     rcx, [rbp+300h+var_34C]; void *
0x18008e663  call    memset_0
0x18008e668  lea     rbx, [r14+30h]
0x18008e66c  cmp     qword ptr [rbx+18h], 7
0x18008e671  jbe     short loc_18008E678
0x18008e673  mov     r8, [rbx]
0x18008e676  jmp     short loc_18008E67B
0x18008e678  mov     r8, rbx; unsigned __int16 *
0x18008e67b  mov     edx, 80h; unsigned __int64
0x18008e680  lea     rcx, [rbp+300h+var_14A]; unsigned __int16 *
0x18008e687  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e68c  mov     rcx, [rbp+308h]; this
0x18008e693  test    eax, eax
0x18008e695  js      loc_18008E9CD
0x18008e69b  mov     [rsp+400h+var_3A0], 0
0x18008e6a4  mov     rcx, [r14+0B8h]
0x18008e6ab  mov     rax, [rcx]
0x18008e6ae  lea     r8, [rsp+400h+var_3A0]
0x18008e6b3  lea     rdx, _GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57
0x18008e6ba  mov     rax, [rax+68h]
0x18008e6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6c3  mov     rcx, [rbp+308h]; this
0x18008e6ca  test    eax, eax
0x18008e6cc  js      loc_18008E9E2
0x18008e6d2  mov     [rsp+400h+var_3A8], 0
0x18008e6db  mov     rcx, [rsp+400h+var_3A0]
0x18008e6e0  mov     rax, [rcx]
0x18008e6e3  mov     [rsp+400h+var_3A8], 0
0x18008e6ec  lea     rdx, [rsp+400h+var_3A8]
0x18008e6f1  mov     rax, [rax+60h]
0x18008e6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6fa  mov     rcx, [rbp+308h]; this
0x18008e701  test    eax, eax
0x18008e703  js      loc_18008E9F7
0x18008e709  xorps   xmm0, xmm0
0x18008e70c  movups  xmmword ptr [rbp+300h+var_370], xmm0
0x18008e710  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008e718  movdqu  [rbp+300h+var_360], xmm1
0x18008e71d  xor     eax, eax
0x18008e71f  mov     word ptr [rbp+300h+var_370], ax
0x18008e723  mov     rdx, [rsp+400h+var_3A8]
0x18008e728  test    rdx, rdx
0x18008e72b  jnz     short loc_18008E733
0x18008e72d  lea     r8, [rbp+300h+var_370]
0x18008e731  jmp     short loc_18008E74A
0x18008e733  lea     rcx, [rbp+300h+var_370]
0x18008e737  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008e73c  lea     r8, [rbp+300h+var_370]
0x18008e740  cmp     qword ptr [rbp+300h+var_360+8], 7
0x18008e745  cmova   r8, [rbp+300h+var_370]; unsigned __int16 *
0x18008e74a  mov     edx, 0FFh; unsigned __int64
0x18008e74f  lea     rcx, [rbp+300h+var_348]; unsigned __int16 *
0x18008e753  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e758  mov     rcx, [rbp+308h]; this
0x18008e75f  test    eax, eax
0x18008e761  js      loc_18008E9B8
0x18008e767  mov     [rsp+400h+Format], 0
0x18008e770  mov     r9d, 30Ch
0x18008e776  lea     r8, [rbp+300h+var_350]
0x18008e77a  xor     edx, edx
0x18008e77c  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008e783  call    cs:__imp_RtlPublishWnfStateData
0x18008e789  mov     esi, eax
0x18008e78b  cmp     qword ptr [rbx+18h], 7
0x18008e790  jbe     short loc_18008E797
0x18008e792  mov     rcx, [rbx]
0x18008e795  jmp     short loc_18008E79A
0x18008e797  mov     rcx, rbx
0x18008e79a  mov     dword ptr [rsp+400h+var_3D0], esi
0x18008e79e  mov     [rsp+400h+var_3D8], rcx
0x18008e7a3  lea     rax, aSentLmESatisfa; "Sent LM_E_SATISFACTION_TRIAL_EXHAUSTED "...
0x18008e7aa  mov     [rsp+400h+Format], rax; Format
0x18008e7af  lea     r13, aLicenseinstanc_4; "LicenseInstanceChangeListener::PublishW"...
0x18008e7b6  mov     r9, r13; char *
0x18008e7b9  mov     r8d, 23Ah; unsigned int
0x18008e7bf  lea     rdi, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008e7c6  mov     rdx, rdi; char *
0x18008e7c9  mov     ecx, 2; unsigned int
0x18008e7ce  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008e7d3  mov     eax, esi
0x18008e7d5  mov     ecx, 0C0000000h
0x18008e7da  and     eax, ecx
0x18008e7dc  cmp     eax, ecx
0x18008e7de  jnz     loc_18008E8F3
0x18008e7e4  mov     rax, cs:?_UnitTestWnfCallback@@3P6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZEA; long (*_UnitTestWnfCallback)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18008e7eb  test    rax, rax
0x18008e7ee  jz      short loc_18008E81A
0x18008e7f0  mov     dword ptr [rsp+400h+var_3D8], 30Ch
0x18008e7f8  lea     rcx, [rbp+300h+var_350]
0x18008e7fc  mov     [rsp+400h+Format], rcx
0x18008e801  xor     r9d, r9d
0x18008e804  xor     r8d, r8d
0x18008e807  xor     edx, edx
0x18008e809  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008e810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e815  jmp     loc_18008E964
0x18008e81a  mov     dword ptr [rsp+400h+var_3D8], esi
0x18008e81e  lea     rax, aFailedToSendLm_0; "Failed to send LM_E_SATISFACTION_TRIAL_"...
0x18008e825  mov     [rsp+400h+Format], rax; Format
0x18008e82a  mov     r9, r13; char *
0x18008e82d  mov     r8d, 245h; unsigned int
0x18008e833  mov     rdx, rdi; char *
0x18008e836  mov     ecx, 1; unsigned int
0x18008e83b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008e840  mov     eax, cs:dword_1800F11D0
0x18008e846  cmp     eax, 2
0x18008e849  jbe     loc_18008E8DE
0x18008e84f  mov     rdx, 200000000000h
0x18008e859  lea     rcx, dword_1800F11D0
0x18008e860  call    _tlgKeywordOn
0x18008e865  test    al, al
0x18008e867  jz      short loc_18008E8DE
0x18008e869  cmp     qword ptr [rbx+18h], 7
0x18008e86e  jbe     short loc_18008E873
0x18008e870  mov     rbx, [rbx]
0x18008e873  mov     [rbp+300h+var_380], rbx
0x18008e877  mov     [rbp+300h+var_378], r13
0x18008e87b  mov     [rsp+400h+var_398], 249h
0x18008e883  mov     [rsp+400h+var_390], rdi
0x18008e888  mov     [rsp+400h+var_3B0], esi
0x18008e88c  lea     rax, aFailedToSendLm_2; "Failed to send LM_E_SATISFACTION_TRIAL_"...
0x18008e893  mov     [rsp+400h+var_388], rax
0x18008e898  lea     rax, [rbp+300h+var_380]
0x18008e89c  mov     [rsp+400h+var_3B8], rax
0x18008e8a1  lea     rax, [rbp+300h+var_378]
0x18008e8a5  mov     [rsp+400h+var_3C0], rax
0x18008e8aa  lea     rax, [rsp+400h+var_398]
0x18008e8af  mov     [rsp+400h+var_3C8], rax
0x18008e8b4  lea     rax, [rsp+400h+var_390]
0x18008e8b9  mov     [rsp+400h+var_3D0], rax
0x18008e8be  lea     rax, [rsp+400h+var_3B0]
0x18008e8c3  mov     [rsp+400h+var_3D8], rax
0x18008e8c8  lea     rax, [rsp+400h+var_388]
0x18008e8cd  mov     [rsp+400h+Format], rax
0x18008e8d2  lea     rdx, byte_1800D7533
0x18008e8d9  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@453@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18008e8de  mov     rcx, [r14+0B8h]
0x18008e8e5  mov     rax, [rcx]
0x18008e8e8  mov     rax, [rax+20h]
0x18008e8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8f1  jmp     short loc_18008E964
0x18008e8f3  mov     eax, cs:dword_1800F11D0
0x18008e8f9  cmp     eax, 3
0x18008e8fc  jbe     short loc_18008E964
0x18008e8fe  mov     rdx, 200000000000h
0x18008e908  lea     rcx, dword_1800F11D0
0x18008e90f  call    _tlgKeywordOn
0x18008e914  test    al, al
0x18008e916  jz      short loc_18008E964
0x18008e918  mov     rax, [rsp+400h+var_3A8]
0x18008e91d  mov     [rsp+400h+var_388], rax
0x18008e922  cmp     qword ptr [rbx+18h], 7
0x18008e927  jbe     short loc_18008E92C
0x18008e929  mov     rbx, [rbx]
0x18008e92c  mov     [rsp+400h+var_390], rbx
0x18008e931  mov     [rsp+400h+var_3B0], 803F8009h
0x18008e939  lea     rax, [rsp+400h+var_388]
0x18008e93e  mov     [rsp+400h+var_3D0], rax
0x18008e943  lea     rax, [rsp+400h+var_390]
0x18008e948  mov     [rsp+400h+var_3D8], rax
0x18008e94d  lea     rax, [rsp+400h+var_3B0]
0x18008e952  mov     [rsp+400h+Format], rax
0x18008e957  lea     rdx, word_1800D74E6
0x18008e95e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18008e963  nop
0x18008e964  lea     rcx, [rbp+300h+var_370]; this
0x18008e968  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008e96d  nop
0x18008e96e  lea     rcx, [rsp+400h+var_3A8]
0x18008e973  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008e978  nop
0x18008e979  mov     rcx, [rsp+400h+var_3A0]
0x18008e97e  test    rcx, rcx
0x18008e981  jz      short loc_18008E999
0x18008e983  mov     [rsp+400h+var_3A0], 0
0x18008e98c  mov     rax, [rcx]
0x18008e98f  mov     rax, [rax+10h]
0x18008e993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e998  nop
0x18008e999  mov     rcx, [rbp+300h+var_40]
0x18008e9a0  xor     rcx, rsp; StackCookie
0x18008e9a3  call    __security_check_cookie
0x18008e9a8  add     rsp, 3D8h
0x18008e9af  pop     r14
0x18008e9b1  pop     r13
0x18008e9b3  pop     rdi
0x18008e9b4  pop     rsi
0x18008e9b5  pop     rbx
0x18008e9b6  pop     rbp
0x18008e9b7  retn
0x18008e9b8  mov     r9d, eax; char *
0x18008e9bb  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008e9c2  mov     edx, 237h; void *
0x18008e9c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e9cd  mov     r9d, eax; char *
0x18008e9d0  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008e9d7  mov     edx, 228h; void *
0x18008e9dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e9e2  mov     r9d, eax; char *
0x18008e9e5  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008e9ec  mov     edx, 22Ch; void *
0x18008e9f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e9f7  mov     r9d, eax; char *
0x18008e9fa  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008ea01  mov     edx, 22Fh; void *
0x18008ea06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
