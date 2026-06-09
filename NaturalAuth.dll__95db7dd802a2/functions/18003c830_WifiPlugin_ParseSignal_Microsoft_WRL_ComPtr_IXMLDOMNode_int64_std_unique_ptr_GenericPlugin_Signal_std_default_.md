# WifiPlugin::ParseSignal(Microsoft::WRL::ComPtr<IXMLDOMNode>,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x18003c830`
- end: `0x18003cd9b`
- name: `?ParseSignal@WifiPlugin@@UEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `1387`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004170`
- `0x18000cab8`
- `0x180011a04`
- `0x180011c68`
- `0x180014e7c`
- `0x18001f634`
- `0x18001fa4c`
- `0x18001fc6c`
- `0x18002072c`
- `0x1800207a0`
- `0x180021df4`
- `0x18003adec`
- `0x18003b47c`
- `0x18003b594`
- `0x18003b5c8`
- `0x18003b798`
- `0x18003c51c`
- `0x18003c5c0`
- `0x18003c77c`
- `0x18003c830`
- `0x18003cda4`
- `0x18003d01c`
- `0x180041d94`
- `0x180046010`

## string_xrefs

- `0x18003caaa`: `bssid`
- `0x18003cb00`: `security`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall WifiPlugin::ParseSignal(__int64 a1, __int64 *a2, __int64 a3, WifiSignal **a4, __int64 a5)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **Address; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **v23; // rax
  int v24; // eax
  const wchar_t **v25; // rbx
  const wchar_t *v26; // rdx
  __int64 v27; // rax
  _BYTE *v28; // rdx
  struct Properties *v29; // rcx
  const wchar_t *v30; // rdx
  __int64 v31; // rdx
  const wchar_t *v32; // rdx
  const wchar_t *v33; // rdx
  const wchar_t *v34; // rdx
  const wchar_t *v35; // r9
  __int64 v37; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v38; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v39; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h] BYREF
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh]
  _QWORD v43[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v44[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct Properties v45; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v47[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  _QWORD v49[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v50; // [rsp+E8h] [rbp-18h]
  int v51; // [rsp+E9h] [rbp-17h]
  __int16 v52; // [rsp+EDh] [rbp-13h]
  char v53; // [rsp+EFh] [rbp-11h]
  _BYTE v54[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v55[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v56[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v57[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v58[32]; // [rsp+170h] [rbp+70h] BYREF

  v43[2] = a2;
  v40 = 0;
  v41 = 0;
  v8 = *a2;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  v10 = v9(v8, &v40);
  if ( v10 < 0 )
    _com_issue_error(v10);
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v41);
  if ( v11 < 0 )
    _com_issue_error(v11);
  v12 = 0;
  std::string::string(&v45);
  std::string::string(v46);
  std::string::string(v47);
  v48 = 0;
  v49[0] = 0;
  v49[1] = 0;
  std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Alloc_sentinel_and_proxy(v49);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::string::string(v57);
  std::string::string(v56);
  std::string::string(v55);
  std::string::string(v54);
  v42 = 0;
  for ( i = 0; (int)i < v41; ++i )
  {
    v39 = 0;
    v14 = v40;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v16 = v15(v14, i, &v39);
    if ( v16 < 0 )
      _com_issue_error(v16);
    v43[0] = 0;
    v17 = v39;
    v18 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v39 + 56LL);
    Address = _bstr_t::GetAddress((_bstr_t *)v43);
    v20 = v18(v17, Address);
    if ( v20 < 0 )
      _com_issue_error(v20);
    v38 = 0;
    v21 = v39;
    v22 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v39 + 208LL);
    v23 = _bstr_t::GetAddress((_bstr_t *)&v38);
    v24 = v22(v21, v23);
    if ( v24 < 0 )
      _com_issue_error(v24);
    if ( !_bstr_t::length((_bstr_t *)&v38) )
    {
      _bstr_t::_Free((_bstr_t *)&v38);
      _bstr_t::_Free((_bstr_t *)v43);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      std::string::_Tidy_deallocate(v54);
      std::string::_Tidy_deallocate(v55);
      std::string::_Tidy_deallocate(v56);
      std::string::_Tidy_deallocate(v57);
      WifiSignal::Properties::~Properties((WifiSignal::Properties *)&v45);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
      return 2147943865LL;
    }
    v25 = (const wchar_t **)v43[0];
    if ( v43[0] )
      v26 = *(const wchar_t **)v43[0];
    else
      v26 = 0;
    if ( !wcscmp_0(L"ssid", v26) )
    {
      v37 = v38;
      if ( v38 )
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
      v43[1] = &v37;
      v27 = _bstr_t::operator char *(&v37);
      std::string::string((__int64)v58, v27);
      std::string::operator=(v57, v58);
      std::string::_Tidy_deallocate(v58);
      _bstr_t::_Free((_bstr_t *)&v37);
      v12 = 0;
      v28 = v57;
      v29 = &v45;
LABEL_18:
      std::string::operator=(v29, v28);
      goto LABEL_51;
    }
    if ( v25 )
      v30 = *v25;
    else
      v30 = 0;
    if ( !wcscmp_0(L"bssid", v30) )
    {
      v37 = v38;
      if ( v38 )
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
      v12 = ParseBssid((_bstr_t *)&v37);
      if ( v12 < 0 )
        goto LABEL_59;
      v50 |= 1u;
      v28 = v56;
      v29 = (struct Properties *)v47;
      goto LABEL_18;
    }
    if ( v25 )
      v32 = *v25;
    else
      v32 = 0;
    if ( !wcscmp_0(L"security", v32) )
    {
      v37 = v38;
      if ( v38 )
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
      v12 = ParseSecurity((_bstr_t *)&v37);
      if ( v12 < 0 )
        goto LABEL_59;
      v28 = v55;
      v29 = (struct Properties *)v46;
      goto LABEL_18;
    }
    if ( v25 )
      v33 = *v25;
    else
      v33 = 0;
    if ( !wcscmp_0(L"trustedRootCA", v33) )
    {
      v37 = v38;
      if ( v38 )
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
      v12 = ParseTrCA((_bstr_t *)&v37);
      if ( v12 < 0 )
        goto LABEL_59;
      std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(
        v49,
        v44,
        v54);
    }
    else
    {
      if ( v25 )
        v34 = *v25;
      else
        v34 = 0;
      if ( wcscmp_0(L"sig_quality", v34) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v25 )
            v35 = *v25;
          else
            v35 = 0;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_144dc3462c353fa21006ff9a189489cc_Traceguids, v35);
        }
        v12 = -805265277;
LABEL_59:
        SetSource<IXMLDOMNode>((unsigned __int16 *)(a5 + 8), v31, &v39);
        _bstr_t::_Free((_bstr_t *)&v38);
        _bstr_t::_Free((_bstr_t *)v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        break;
      }
      v37 = v38;
      if ( v38 )
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
      v12 = ParseSigQuality((_bstr_t *)&v37);
      if ( v12 < 0 )
        goto LABEL_59;
      v50 |= 2u;
      LODWORD(v48) = v42;
    }
LABEL_51:
    _bstr_t::_Free((_bstr_t *)&v38);
    _bstr_t::_Free((_bstr_t *)v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  }
  if ( v12 >= 0 )
    v12 = WifiSignal::Create(a3, &v45, a4);
  std::string::_Tidy_deallocate(v54);
  std::string::_Tidy_deallocate(v55);
  std::string::_Tidy_deallocate(v56);
  std::string::_Tidy_deallocate(v57);
  WifiSignal::Properties::~Properties((WifiSignal::Properties *)&v45);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003c830  mov     [rsp-8+arg_0], rbx
0x18003c835  push    rbp
0x18003c836  push    rsi
0x18003c837  push    rdi
0x18003c838  push    r12
0x18003c83a  push    r13
0x18003c83c  push    r14
0x18003c83e  push    r15
0x18003c840  lea     rbp, [rsp-0A0h]
0x18003c848  sub     rsp, 1A0h
0x18003c84f  mov     rax, cs:__security_cookie
0x18003c856  xor     rax, rsp
0x18003c859  mov     [rbp+0D0h+var_40], rax
0x18003c860  mov     r12, r9
0x18003c863  mov     r15, r8
0x18003c866  mov     r14, rdx
0x18003c869  mov     [rsp+1D0h+var_178], rdx
0x18003c86e  mov     r13, [rbp+0D0h+arg_20]
0x18003c875  mov     [rsp+1D0h+var_198], 0
0x18003c87e  mov     [rsp+1D0h+var_190], 0
0x18003c886  mov     rdi, [rdx]
0x18003c889  mov     rax, [rdi]
0x18003c88c  mov     rbx, [rax+60h]
0x18003c890  lea     rcx, [rsp+1D0h+var_198]
0x18003c895  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c89a  lea     rdx, [rsp+1D0h+var_198]
0x18003c89f  mov     rcx, rdi
0x18003c8a2  mov     rax, rbx
0x18003c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8aa  xor     edi, edi
0x18003c8ac  test    eax, eax
0x18003c8ae  jns     short loc_18003C8B8
0x18003c8b0  mov     ecx, eax; int
0x18003c8b2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003c8b8  mov     rcx, [rsp+1D0h+var_198]
0x18003c8bd  mov     rax, [rcx]
0x18003c8c0  lea     rdx, [rsp+1D0h+var_190]
0x18003c8c5  mov     rax, [rax+40h]
0x18003c8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8ce  test    eax, eax
0x18003c8d0  jns     short loc_18003C8DA
0x18003c8d2  mov     ecx, eax; int
0x18003c8d4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003c8da  mov     ebx, edi
0x18003c8dc  lea     rcx, [rsp+1D0h+var_160]
0x18003c8e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c8e6  nop
0x18003c8e7  lea     rcx, [rbp+0D0h+var_140]
0x18003c8eb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c8f0  nop
0x18003c8f1  lea     rcx, [rbp+0D0h+var_120]
0x18003c8f5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c8fa  nop
0x18003c8fb  xor     eax, eax
0x18003c8fd  mov     [rbp+0D0h+var_100], rax
0x18003c901  mov     [rbp+0D0h+var_F8], rdi
0x18003c905  mov     [rbp+0D0h+var_F0], rdi
0x18003c909  lea     rcx, [rbp+0D0h+var_F8]
0x18003c90d  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Alloc_sentinel_and_proxy(void)
0x18003c912  mov     [rbp+0D0h+var_E8], dil
0x18003c916  xor     eax, eax
0x18003c918  mov     [rbp+0D0h+var_E7], eax
0x18003c91b  mov     [rbp+0D0h+var_E3], ax
0x18003c91f  mov     [rbp+0D0h+var_E1], al
0x18003c922  lea     rcx, [rbp+0D0h+var_80]
0x18003c926  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c92b  nop
0x18003c92c  lea     rcx, [rbp+0D0h+var_A0]
0x18003c930  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c935  nop
0x18003c936  lea     rcx, [rbp+0D0h+var_C0]
0x18003c93a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c93f  nop
0x18003c940  lea     rcx, [rbp+0D0h+var_E0]
0x18003c944  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003c949  nop
0x18003c94a  mov     [rsp+1D0h+var_18C], edi
0x18003c94e  mov     esi, edi
0x18003c950  cmp     esi, [rsp+1D0h+var_190]
0x18003c954  jge     loc_18003CC8A
0x18003c95a  mov     [rsp+1D0h+var_1A0], rdi
0x18003c95f  mov     rdi, [rsp+1D0h+var_198]
0x18003c964  mov     rax, [rdi]
0x18003c967  mov     rbx, [rax+38h]
0x18003c96b  lea     rcx, [rsp+1D0h+var_1A0]
0x18003c970  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c975  lea     r8, [rsp+1D0h+var_1A0]
0x18003c97a  mov     edx, esi
0x18003c97c  mov     rcx, rdi
0x18003c97f  mov     rax, rbx
0x18003c982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c987  test    eax, eax
0x18003c989  js      loc_18003CD93
0x18003c98f  mov     [rsp+1D0h+var_188], 0
0x18003c998  mov     rdi, [rsp+1D0h+var_1A0]
0x18003c99d  mov     rax, [rdi]
0x18003c9a0  mov     rbx, [rax+38h]
0x18003c9a4  lea     rcx, [rsp+1D0h+var_188]; this
0x18003c9a9  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x18003c9ae  mov     rdx, rax
0x18003c9b1  mov     rcx, rdi
0x18003c9b4  mov     rax, rbx
0x18003c9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9bc  test    eax, eax
0x18003c9be  js      loc_18003CD8B
0x18003c9c4  mov     [rsp+1D0h+var_1A8], 0
0x18003c9cd  mov     rdi, [rsp+1D0h+var_1A0]
0x18003c9d2  mov     rax, [rdi]
0x18003c9d5  mov     rbx, [rax+0D0h]
0x18003c9dc  lea     rcx, [rsp+1D0h+var_1A8]; this
0x18003c9e1  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x18003c9e6  mov     rdx, rax
0x18003c9e9  mov     rcx, rdi
0x18003c9ec  mov     rax, rbx
0x18003c9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9f4  xor     edi, edi
0x18003c9f6  test    eax, eax
0x18003c9f8  js      loc_18003CD83
0x18003c9fe  lea     rcx, [rsp+1D0h+var_1A8]; this
0x18003ca03  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003ca08  test    eax, eax
0x18003ca0a  jz      loc_18003CD12
0x18003ca10  mov     rbx, [rsp+1D0h+var_188]
0x18003ca15  test    rbx, rbx
0x18003ca18  jz      short loc_18003CA1F
0x18003ca1a  mov     rdx, [rbx]
0x18003ca1d  jmp     short loc_18003CA22
0x18003ca1f  mov     rdx, rdi; String2
0x18003ca22  lea     rcx, aSsid; "ssid"
0x18003ca29  call    wcscmp_0
0x18003ca2e  test    eax, eax
0x18003ca30  jnz     short loc_18003CA9D
0x18003ca32  mov     rax, [rsp+1D0h+var_1A8]
0x18003ca37  mov     [rsp+1D0h+var_1B0], rax
0x18003ca3c  test    rax, rax
0x18003ca3f  jz      short loc_18003CA45
0x18003ca41  lock inc dword ptr [rax+10h]
0x18003ca45  lea     rax, [rsp+1D0h+var_1B0]
0x18003ca4a  mov     [rsp+1D0h+var_180], rax
0x18003ca4f  lea     rcx, [rsp+1D0h+var_1B0]
0x18003ca54  call    ??B_bstr_t@@QEBAPEADXZ; _bstr_t::operator char *(void)
0x18003ca59  mov     rdx, rax
0x18003ca5c  lea     rcx, [rbp+0D0h+var_60]
0x18003ca60  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003ca65  nop
0x18003ca66  lea     rdx, [rbp+0D0h+var_60]
0x18003ca6a  lea     rcx, [rbp+0D0h+var_80]
0x18003ca6e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18003ca73  nop
0x18003ca74  lea     rcx, [rbp+0D0h+var_60]
0x18003ca78  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003ca7d  nop
0x18003ca7e  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18003ca83  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003ca88  mov     ebx, edi
0x18003ca8a  lea     rdx, [rbp+0D0h+var_80]
0x18003ca8e  lea     rcx, [rsp+1D0h+var_160]
0x18003ca93  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18003ca98  jmp     loc_18003CBF4
0x18003ca9d  test    rbx, rbx
0x18003caa0  jz      short loc_18003CAA7
0x18003caa2  mov     rdx, [rbx]
0x18003caa5  jmp     short loc_18003CAAA
0x18003caa7  mov     rdx, rdi; String2
0x18003caaa  lea     rcx, aBssid; "bssid"
0x18003cab1  call    wcscmp_0
0x18003cab6  test    eax, eax
0x18003cab8  jnz     short loc_18003CAF3
0x18003caba  mov     rax, [rsp+1D0h+var_1A8]
0x18003cabf  mov     [rsp+1D0h+var_1B0], rax
0x18003cac4  test    rax, rax
0x18003cac7  jz      short loc_18003CACD
0x18003cac9  lock inc dword ptr [rax+10h]
0x18003cacd  lea     rdx, [rbp+0D0h+var_A0]
0x18003cad1  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18003cad6  call    ParseBssid
0x18003cadb  mov     ebx, eax
0x18003cadd  test    eax, eax
0x18003cadf  js      loc_18003CC5B
0x18003cae5  or      [rbp+0D0h+var_E8], 1
0x18003cae9  lea     rdx, [rbp+0D0h+var_A0]
0x18003caed  lea     rcx, [rbp+0D0h+var_120]
0x18003caf1  jmp     short loc_18003CA93
0x18003caf3  test    rbx, rbx
0x18003caf6  jz      short loc_18003CAFD
0x18003caf8  mov     rdx, [rbx]
0x18003cafb  jmp     short loc_18003CB00
0x18003cafd  mov     rdx, rdi; String2
0x18003cb00  lea     rcx, aSecurity; "security"
0x18003cb07  call    wcscmp_0
0x18003cb0c  test    eax, eax
0x18003cb0e  jnz     short loc_18003CB48
0x18003cb10  mov     rax, [rsp+1D0h+var_1A8]
0x18003cb15  mov     [rsp+1D0h+var_1B0], rax
0x18003cb1a  test    rax, rax
0x18003cb1d  jz      short loc_18003CB23
0x18003cb1f  lock inc dword ptr [rax+10h]
0x18003cb23  lea     rdx, [rbp+0D0h+var_C0]
0x18003cb27  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18003cb2c  call    ParseSecurity
0x18003cb31  mov     ebx, eax
0x18003cb33  test    eax, eax
0x18003cb35  js      loc_18003CC5B
0x18003cb3b  lea     rdx, [rbp+0D0h+var_C0]
0x18003cb3f  lea     rcx, [rbp+0D0h+var_140]
0x18003cb43  jmp     loc_18003CA93
0x18003cb48  test    rbx, rbx
0x18003cb4b  jz      short loc_18003CB52
0x18003cb4d  mov     rdx, [rbx]
0x18003cb50  jmp     short loc_18003CB55
0x18003cb52  mov     rdx, rdi; String2
0x18003cb55  lea     rcx, aTrustedrootca; "trustedRootCA"
0x18003cb5c  call    wcscmp_0
0x18003cb61  test    eax, eax
0x18003cb63  jnz     short loc_18003CBA4
0x18003cb65  mov     rax, [rsp+1D0h+var_1A8]
0x18003cb6a  mov     [rsp+1D0h+var_1B0], rax
0x18003cb6f  test    rax, rax
0x18003cb72  jz      short loc_18003CB78
0x18003cb74  lock inc dword ptr [rax+10h]
0x18003cb78  lea     rdx, [rbp+0D0h+var_E0]
0x18003cb7c  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18003cb81  call    ParseTrCA
0x18003cb86  mov     ebx, eax
0x18003cb88  test    eax, eax
0x18003cb8a  js      loc_18003CC5B
0x18003cb90  lea     r8, [rbp+0D0h+var_E0]
0x18003cb94  lea     rdx, [rsp+1D0h+var_170]
0x18003cb99  lea     rcx, [rbp+0D0h+var_F8]
0x18003cb9d  call    ??$_Emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(std::string const &)
0x18003cba2  jmp     short loc_18003CBF4
0x18003cba4  test    rbx, rbx
0x18003cba7  jz      short loc_18003CBAE
0x18003cba9  mov     rdx, [rbx]
0x18003cbac  jmp     short loc_18003CBB1
0x18003cbae  mov     rdx, rdi; String2
0x18003cbb1  lea     rcx, aSigQuality; "sig_quality"
0x18003cbb8  call    wcscmp_0
0x18003cbbd  test    eax, eax
0x18003cbbf  jnz     short loc_18003CC1B
0x18003cbc1  mov     rax, [rsp+1D0h+var_1A8]
0x18003cbc6  mov     [rsp+1D0h+var_1B0], rax
0x18003cbcb  test    rax, rax
0x18003cbce  jz      short loc_18003CBD4
0x18003cbd0  lock inc dword ptr [rax+10h]
0x18003cbd4  lea     rdx, [rsp+1D0h+var_18C]
0x18003cbd9  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18003cbde  call    ParseSigQuality
0x18003cbe3  mov     ebx, eax
0x18003cbe5  test    eax, eax
0x18003cbe7  js      short loc_18003CC5B
0x18003cbe9  or      [rbp+0D0h+var_E8], 2
0x18003cbed  mov     eax, [rsp+1D0h+var_18C]
0x18003cbf1  mov     dword ptr [rbp+0D0h+var_100], eax
0x18003cbf4  lea     rcx, [rsp+1D0h+var_1A8]; this
0x18003cbf9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003cbfe  nop
0x18003cbff  lea     rcx, [rsp+1D0h+var_188]; this
0x18003cc04  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003cc09  nop
0x18003cc0a  lea     rcx, [rsp+1D0h+var_1A0]
0x18003cc0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cc14  inc     esi
0x18003cc16  jmp     loc_18003C950
0x18003cc1b  lea     rax, WPP_GLOBAL_Control
0x18003cc22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc29  cmp     rcx, rax
0x18003cc2c  jz      short loc_18003CC56
0x18003cc2e  test    byte ptr [rcx+1Ch], 1
0x18003cc32  jz      short loc_18003CC56
0x18003cc34  test    rbx, rbx
0x18003cc37  jz      short loc_18003CC3E
0x18003cc39  mov     r9, [rbx]
0x18003cc3c  jmp     short loc_18003CC41
0x18003cc3e  mov     r9, rdi
0x18003cc41  mov     edx, 1Bh
0x18003cc46  lea     r8, WPP_144dc3462c353fa21006ff9a189489cc_Traceguids
0x18003cc4d  mov     rcx, [rcx+10h]
0x18003cc51  call    WPP_SF_S
0x18003cc56  mov     ebx, 0D000A083h
0x18003cc5b  lea     rcx, [r13+8]; unsigned __int16 *
0x18003cc5f  lea     r8, [rsp+1D0h+var_1A0]
0x18003cc64  call    ??$SetSource@UIXMLDOMNode@@@@YAXPEAG_KAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; SetSource<IXMLDOMNode>(ushort *,unsigned __int64,Microsoft::WRL::ComPtr<IXMLDOMNode> const &)
0x18003cc69  nop
0x18003cc6a  lea     rcx, [rsp+1D0h+var_1A8]; this
0x18003cc6f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003cc74  nop
0x18003cc75  lea     rcx, [rsp+1D0h+var_188]; this
0x18003cc7a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003cc7f  nop
0x18003cc80  lea     rcx, [rsp+1D0h+var_1A0]
0x18003cc85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cc8a  test    ebx, ebx
0x18003cc8c  js      short loc_18003CCA0
0x18003cc8e  mov     r8, r12
0x18003cc91  lea     rdx, [rsp+1D0h+var_160]; struct Properties *
0x18003cc96  mov     rcx, r15; __int64
0x18003cc99  call    ?Create@WifiSignal@@SAJ_JAEBUProperties@1@PEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@Z; WifiSignal::Create(__int64,WifiSignal::Properties const &,std::unique_ptr<GenericPlugin::Signal> *)
0x18003cc9e  mov     ebx, eax
0x18003cca0  lea     rcx, [rbp+0D0h+var_E0]
  ... truncated ...
```
