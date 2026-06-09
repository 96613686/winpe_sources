# CRegistration::SetFilterRules(ushort const *,std::set<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>> &)

- ea: `0x180036650`
- end: `0x18003833c`
- name: `?SetFilterRules@CRegistration@@QEAAJPEBGAEAV?$set@_KU?$less@_K@std@@V?$allocator@_K@2@@std@@@Z`
- size: `7404`
- prototype: `__int64 __fastcall(__int64 *, const wchar_t *, void **)`
- caller_count: `2`
- callee_count: `48`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010a28`
- `0x180035660`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x18000498c`
- `0x180004998`
- `0x1800064c4`
- `0x18000659c`
- `0x1800069f0`
- `0x180006a5c`
- `0x180006d00`
- `0x18000c54c`
- `0x18000d388`
- `0x18000dd64`
- `0x18000df8c`
- `0x18000e05c`
- `0x18000e534`
- `0x18000e6e4`
- `0x18000efbc`
- `0x180014d20`
- `0x180015764`
- `0x180015aac`
- `0x18001c944`
- `0x18001d548`
- `0x18001d734`
- `0x18001f378`
- `0x18002ad60`
- `0x18003246c`
- `0x18003277c`
- `0x180032c30`
- `0x180032e94`
- `0x180032f88`
- `0x180033090`
- `0x180033198`
- `0x180033660`
- `0x1800337f8`
- `0x180033978`
- `0x180034bec`
- `0x180036650`
- `0x180038674`
- `0x180038710`
- `0x180051420`
- `0x180051628`
- `0x180063e2c`
- `0x180064090`
- `0x1800647dc`
- `0x180067cc4`
- `0x180068640`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800381ec`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800382af`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800382e6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800381ec`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800382af`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800382e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036f1c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036fdd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036fff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036f1c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036fdd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036fff`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180036ad2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180036ad2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037498`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037e37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037498`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037e37`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037483`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037e26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037483`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800374a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800374a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037e40`
- `OLEAUT32!__imp_SysAllocString` at `0x180036964`
- `OLEAUT32!__imp_SysAllocString` at `0x1800369b0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800369fd`
- `OLEAUT32!__imp_SysAllocString` at `0x180036a53`
- `OLEAUT32!__imp_SysAllocString` at `0x18003713f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003720c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800372bc`
- `OLEAUT32!__imp_SysAllocString` at `0x180036964`
- `OLEAUT32!__imp_SysAllocString` at `0x1800369b0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800369fd`
- `OLEAUT32!__imp_SysAllocString` at `0x180036a53`
- `OLEAUT32!__imp_SysAllocString` at `0x18003713f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003720c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800372bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003692b`
- `OLEAUT32!__imp_SysFreeString` at `0x180036992`
- `OLEAUT32!__imp_SysFreeString` at `0x1800369de`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180036aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ae9`
- `OLEAUT32!__imp_SysFreeString` at `0x180036b7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180036c47`
- `OLEAUT32!__imp_SysFreeString` at `0x180036d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f83`
- `OLEAUT32!__imp_SysFreeString` at `0x18003716e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003723b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800372eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800373ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800373ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18003742f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800374f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180037558`
- `OLEAUT32!__imp_SysFreeString` at `0x18003762c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800376a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003777b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800377f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800378ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180037945`
- `OLEAUT32!__imp_SysFreeString` at `0x180037a19`
- `OLEAUT32!__imp_SysFreeString` at `0x180037a94`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180037c36`
- `OLEAUT32!__imp_SysFreeString` at `0x180037cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180037da7`
- `OLEAUT32!__imp_SysFreeString` at `0x180037f50`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038266`
- `OLEAUT32!__imp_SysFreeString` at `0x180038295`
- `OLEAUT32!__imp_SysFreeString` at `0x1800382cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003692b`
- `OLEAUT32!__imp_SysFreeString` at `0x180036992`
- `OLEAUT32!__imp_SysFreeString` at `0x1800369de`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180036aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ae9`
- `OLEAUT32!__imp_SysFreeString` at `0x180036b7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180036c47`
- `OLEAUT32!__imp_SysFreeString` at `0x180036d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f83`
- `OLEAUT32!__imp_SysFreeString` at `0x18003716e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003723b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800372eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800373ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800373ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18003742f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800374f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180037558`
- `OLEAUT32!__imp_SysFreeString` at `0x18003762c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800376a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003777b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800377f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800378ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180037945`
- `OLEAUT32!__imp_SysFreeString` at `0x180037a19`
- `OLEAUT32!__imp_SysFreeString` at `0x180037a94`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180037c36`
- `OLEAUT32!__imp_SysFreeString` at `0x180037cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180037da7`
- `OLEAUT32!__imp_SysFreeString` at `0x180037f50`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038266`
- `OLEAUT32!__imp_SysFreeString` at `0x180038295`
- `OLEAUT32!__imp_SysFreeString` at `0x1800382cc`
- `OLEAUT32!__imp_SysStringLen` at `0x180036f6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180037274`
- `OLEAUT32!__imp_SysStringLen` at `0x180036f6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180037274`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036987`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800369d3`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036a20`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036a76`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180037162`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18003722f`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800372df`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036987`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800369d3`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036a20`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036a76`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180037162`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18003722f`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800372df`

## string_xrefs

- `0x180036763`: `Filter rules same as before for RegName: %S, AppName: %S, UserSid: %S`
- `0x180036864`: `Malformed FilterXML %S, RegName: %S, AppName: %S, UserSid: %S`
- `0x18003690a`: `Malformed FilterXML %S, RegName: %S, AppName: %S, UserSid: %S`
- `0x1800367e4`: `Filter rules updated for RegName: %S, AppName: %S, UserSid: %S`
- `0x180038240`: `Missing Action element FilterXML %S, RegName: %S, AppName: %S, UserSid: %S`
- `0x180036b57`: `Delivery action update not permitted FilterXML %S, RegName: %S, AppName: %S, UserSid: %S`
- `0x180036cd2`: `Parsing FilterXML %S failed, RegName: %S, AppName: %S, UserSid: %S`
- `0x180037ef2`: `Failed to obtain child nodes length, FilterXML %S .`
- `0x180037c77`: `Failed to obtain message type for filter at index %d, FilterXML %S .`
- `0x180037d2d`: `Failed to obtain child nodes for filter, FilterXML %S .`
- `0x1800374ce`: `AcceptImmediately or Peek text message filter %d requires TextPrefix with minimum %d characters, FilterXML %S.`
- `0x180037ad5`: `Failed to obtain child nodes length for broadcast message filter %d, FilterXML %S.`
- `0x180037ba6`: `Failed to obtain child nodes for broadcast message filter %d, FilterXML %S.`
- `0x180037842`: `Failed to obtain child node name at index %d for broadcast message filter %d, FilterXML %S.`
- `0x180037991`: `Failed to obtain child node at index %d for broadcast message filter %d, FilterXML %S.`
- `0x1800376f3`: `Failed to obtain channels for broadcast message filter %d, FilterXML %S.`
- `0x1800375a4`: `Failed to obtain types at index %d for broadcast message filter %d, FilterXML %S.`
- `0x180037475`: `SmsRouter\TextMessageReadyEvent`
- `0x180037deb`: `SmsRouter\TextMessageReadyEvent`
- `0x180037e18`: `SmsRouter\WapMessageReadyEvent`
- `0x180037e64`: `SmsRouter\WapMessageReadyEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistration::SetFilterRules(__int64 *a1, const wchar_t *a2, void **a3)
{
  __int64 *v5; // r13
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  size_t v8; // r8
  const wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  const wchar_t *v11; // r9
  int XmlDocument; // edi
  const wchar_t *v13; // rbx
  const wchar_t *v14; // rcx
  const wchar_t *v15; // r14
  const wchar_t *v16; // rdx
  const wchar_t *v17; // rsi
  const wchar_t *v18; // rax
  const wchar_t *v19; // r12
  struct IXMLDOMNode *v20; // r15
  int NodeTextValue; // eax
  OLECHAR *v22; // rax
  OLECHAR *v23; // rbx
  HRESULT v24; // edi
  int v25; // ebx
  int v26; // edi
  OLECHAR *v27; // rax
  OLECHAR *v28; // rbx
  HRESULT v29; // edi
  OLECHAR *v30; // rax
  OLECHAR *v31; // rbx
  HRESULT v32; // edi
  OLECHAR *v33; // rax
  OLECHAR *v34; // rbx
  HRESULT v35; // edi
  int v36; // eax
  const wchar_t *v37; // rax
  _DWORD *v38; // rbx
  int v39; // eax
  const wchar_t *v40; // rax
  struct IXMLDOMDocument *v41; // r14
  int v42; // esi
  __int64 v43; // rbx
  __int64 v44; // rcx
  struct IXMLDOMDocument *v45; // rbx
  int v46; // eax
  int v47; // edi
  BSTR v48; // rcx
  int v49; // eax
  int v50; // edi
  int v51; // edi
  struct IXMLDOMNode *v52; // rcx
  int v53; // r14d
  int v54; // eax
  int v55; // eax
  UINT v56; // edi
  int v57; // eax
  int v58; // eax
  SmsRouterBroadcastConfig *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rsi
  int v62; // edi
  _QWORD *v63; // rax
  OLECHAR *v64; // rax
  OLECHAR *v65; // rdi
  HRESULT v66; // r14d
  __int64 i; // rdi
  __int64 v68; // r14
  _QWORD *v69; // rcx
  OLECHAR *v70; // rax
  OLECHAR *v71; // rdi
  HRESULT v72; // r14d
  BSTR v73; // r9
  char **v74; // rcx
  unsigned __int64 v75; // rdx
  char *v76; // r14
  OLECHAR *v77; // rax
  OLECHAR *v78; // rdi
  HRESULT v79; // r14d
  __int64 *v80; // rdi
  __int64 **v81; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  __int64 v84; // rdi
  HANDLE EventW; // rax
  void *v86; // rdi
  unsigned int MinTextPrefixSize; // eax
  void *v88; // rcx
  _QWORD *v89; // rsi
  void *v90; // rcx
  void *v91; // rcx
  _QWORD *v92; // rsi
  void *v93; // rcx
  void *v94; // rcx
  _QWORD *v95; // rsi
  void *v96; // rcx
  void *v97; // rcx
  _QWORD *v98; // rsi
  void *v99; // rcx
  signed int LastError; // eax
  HANDLE v101; // rax
  void *v102; // rdi
  signed int v103; // eax
  _QWORD *v104; // rax
  BSTR v105; // rax
  void **v106; // r14
  OLECHAR *v107; // rsi
  struct IXMLDOMDocument *v108; // rdi
  _BYTE *v109; // rdx
  void **p_Block; // rcx
  __int64 *v111; // r8
  const unsigned __int16 *v112; // r8
  const wchar_t *v114; // rax
  const wchar_t *v115; // rcx
  const wchar_t *v116; // r12
  const wchar_t *v117; // [rsp+28h] [rbp-D8h]
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  int v119; // [rsp+48h] [rbp-B8h]
  BSTR bstrLeft; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMNode *v121; // [rsp+58h] [rbp-A8h] BYREF
  int v122; // [rsp+60h] [rbp-A0h]
  __int64 v123; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v124; // [rsp+70h] [rbp-90h]
  int v125; // [rsp+78h] [rbp-88h]
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  __int64 v127; // [rsp+88h] [rbp-78h]
  int v128; // [rsp+90h] [rbp-70h]
  int v129; // [rsp+94h] [rbp-6Ch] BYREF
  _DWORD *v130; // [rsp+98h] [rbp-68h]
  BSTR pbstr; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v132; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v133; // [rsp+B0h] [rbp-50h] BYREF
  int v134; // [rsp+B8h] [rbp-48h]
  BSTR v135; // [rsp+C0h] [rbp-40h] BYREF
  int v136; // [rsp+C8h] [rbp-38h] BYREF
  int v137; // [rsp+CCh] [rbp-34h] BYREF
  struct IXMLDOMDocument *v138; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v139; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v140; // [rsp+E8h] [rbp-18h]
  int v141; // [rsp+F0h] [rbp-10h]
  struct IXMLDOMNode *v142; // [rsp+F8h] [rbp-8h] BYREF
  void **v143; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v144; // [rsp+108h] [rbp+8h]
  struct IXMLDOMDocument *v145; // [rsp+110h] [rbp+10h]
  __int64 v146; // [rsp+118h] [rbp+18h]
  __int64 v147; // [rsp+120h] [rbp+20h]
  void **v148; // [rsp+128h] [rbp+28h]
  __int64 *v149; // [rsp+130h] [rbp+30h]
  _BYTE v150[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v151[24]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v152[152]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v153[104]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 v154; // [rsp+260h] [rbp+160h] BYREF
  __int64 v155; // [rsp+270h] [rbp+170h]
  __int64 v156; // [rsp+278h] [rbp+178h]
  _QWORD v157[8]; // [rsp+280h] [rbp+180h] BYREF

  v143 = a3;
  v124 = a2;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v152);
  v146 = 0;
  v147 = 0;
  v142 = 0;
  v148 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v5 = a1 + 38;
  v149 = a1 + 38;
  (*(void (__fastcall **)(__int64 *))a1[38])(a1 + 38);
  if ( !a2 || !*a2 )
  {
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
    SysFreeString(0);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v153);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v153);
    return 2147942487LL;
  }
  v129 = 0;
  if ( a1[20] )
  {
    v6 = (const wchar_t *)(a1 + 18);
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = a1[20];
    if ( (unsigned __int64)a1[21] > 7 )
      v6 = *(const wchar_t **)v6;
    if ( v8 == v7 && (!v8 || !wmemcmp(v6, a2, v8)) )
    {
      v9 = (const wchar_t *)(a1 + 14);
      if ( (unsigned __int64)a1[17] > 7 )
        v9 = *(const wchar_t **)v9;
      v10 = (const wchar_t *)(a1 + 10);
      if ( (unsigned __int64)a1[13] > 7 )
        v10 = *(const wchar_t **)v10;
      v11 = (const wchar_t *)(a1 + 6);
      if ( (unsigned __int64)a1[9] > 7 )
        v11 = *(const wchar_t **)v11;
      LogSmsRouterInfo(
        "CRegistration::SetFilterRules",
        0xEBu,
        "Filter rules same as before for RegName: %S, AppName: %S, UserSid: %S",
        v11,
        v10,
        v9);
      (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
      XmlDocument = 0;
      goto LABEL_339;
    }
    v129 = 1;
    v13 = (const wchar_t *)(a1 + 14);
    pbstr = (BSTR)(a1 + 14);
    v14 = (const wchar_t *)(a1 + 14);
    if ( (unsigned __int64)a1[17] > 7 )
      v14 = *(const wchar_t **)v13;
    v15 = (const wchar_t *)(a1 + 10);
    v16 = (const wchar_t *)(a1 + 10);
    if ( (unsigned __int64)a1[13] > 7 )
      v16 = *(const wchar_t **)v15;
    v17 = (const wchar_t *)(a1 + 6);
    v18 = (const wchar_t *)(a1 + 6);
    if ( (unsigned __int64)a1[9] > 7 )
      v18 = *(const wchar_t **)v17;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0xF7u,
      0,
      "Filter rules updated for RegName: %S, AppName: %S, UserSid: %S",
      v18,
      v16,
      v14);
  }
  else
  {
    v15 = (const wchar_t *)(a1 + 10);
    v17 = (const wchar_t *)(a1 + 6);
    v13 = (const wchar_t *)(a1 + 14);
    pbstr = (BSTR)(a1 + 14);
  }
  XmlDocument = Windows::Sms::Common::CSmsUtil::GetXmlDocument(a2, (struct IXMLDOMDocument **)&v142);
  if ( XmlDocument < 0 )
  {
    v19 = (const wchar_t *)(a1 + 14);
    if ( *((_QWORD *)v19 + 3) > 7u )
      v19 = *(const wchar_t **)v19;
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(const wchar_t **)v15;
    if ( *((_QWORD *)v17 + 3) > 7u )
      v17 = *(const wchar_t **)v17;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0x105u,
      XmlDocument,
      "Malformed FilterXML %S, RegName: %S, AppName: %S, UserSid: %S",
      a2,
      v17,
      v15,
      v19);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    if ( v142 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v142->lpVtbl->Release)(v142);
    goto LABEL_339;
  }
  bstrString = 0;
  v20 = v142;
  NodeTextValue = Windows::Sms::Common::CSmsUtil::GetNodeTextValue(v142, L"/SmsMessageFilter/@Action", &bstrString);
  XmlDocument = NodeTextValue;
  if ( NodeTextValue < 0 )
  {
    if ( *((_QWORD *)v13 + 3) > 7u )
      v13 = *(const wchar_t **)v13;
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(const wchar_t **)v15;
    if ( *((_QWORD *)v17 + 3) > 7u )
      v17 = *(const wchar_t **)v17;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0x115u,
      NodeTextValue,
      "Malformed FilterXML %S, RegName: %S, AppName: %S, UserSid: %S",
      v124,
      v17,
      v15,
      v13);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    goto LABEL_339;
  }
  v22 = SysAllocString(L"AcceptImmediately");
  v23 = v22;
  if ( !v22 )
    goto LABEL_341;
  v24 = VarBstrCmp(bstrString, v22, 0x400u, 0);
  SysFreeString(v23);
  if ( v24 == 1 )
  {
    v25 = 1;
    v26 = 0x10000000;
    goto LABEL_58;
  }
  v27 = SysAllocString(L"Drop");
  v28 = v27;
  if ( !v27 )
    goto LABEL_341;
  v29 = VarBstrCmp(bstrString, v27, 0x400u, 0);
  SysFreeString(v28);
  if ( v29 == 1 )
  {
    v25 = 2;
    v26 = 0x1000000;
    goto LABEL_58;
  }
  v30 = SysAllocString(L"Peek");
  v31 = v30;
  if ( !v30 )
    goto LABEL_341;
  v32 = VarBstrCmp(bstrString, v30, 0x400u, 0);
  SysFreeString(v31);
  if ( v32 == 1 )
  {
    v25 = 3;
    v26 = 0x100000;
    *((_DWORD *)a1 + 57) = 1;
    goto LABEL_58;
  }
  v33 = SysAllocString(L"Accept");
  v34 = v33;
  if ( !v33 )
LABEL_341:
    ATL::AtlThrowImpl(-2147024882);
  v35 = VarBstrCmp(bstrString, v33, 0x400u, 0);
  SysFreeString(v34);
  if ( v35 != 1 )
  {
    v114 = (const wchar_t *)(a1 + 14);
    if ( (unsigned __int64)a1[17] > 7 )
      v114 = *(const wchar_t **)v114;
    v115 = (const wchar_t *)(a1 + 10);
    if ( (unsigned __int64)a1[13] > 7 )
      v115 = *(const wchar_t **)v115;
    v116 = (const wchar_t *)(a1 + 6);
    if ( *((_QWORD *)v116 + 3) > 7u )
      v116 = *(const wchar_t **)v116;
    XmlDocument = -2147024809;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0x138u,
      -2147024809,
      "Missing Action element FilterXML %S, RegName: %S, AppName: %S, UserSid: %S",
      v124,
      v116,
      v115,
      v114);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    goto LABEL_339;
  }
  v25 = 4;
  v26 = 0x10000;
LABEL_58:
  v134 = v26;
  v122 = v25;
  SysFreeString(bstrString);
  bstrString = 0;
  if ( (int)Windows::Sms::Common::CSmsUtil::GetNodeTextValue(v20, L"/SmsMessageFilter/@Flags", &bstrString) < 0 )
    v36 = 0;
  else
    v36 = _o__wtoi(bstrString);
  *((_DWORD *)a1 + 58) = v36;
  SysFreeString(bstrString);
  bstrString = 0;
  if ( a1[20] && (*((_DWORD *)a1 + 55) != v26 || *((_DWORD *)a1 + 59) != v25) )
  {
    v37 = pbstr;
    if ( *((_QWORD *)pbstr + 3) > 7u )
      v37 = *(const wchar_t **)pbstr;
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(const wchar_t **)v15;
    if ( *((_QWORD *)v17 + 3) > 7u )
      v17 = *(const wchar_t **)v17;
    XmlDocument = -2147024846;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0x152u,
      -2147024846,
      "Delivery action update not permitted FilterXML %S, RegName: %S, AppName: %S, UserSid: %S",
      v124,
      v17,
      v15,
      v37);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    goto LABEL_339;
  }
  v144 = 0;
  v123 = 0;
  v38 = operator new(0x10u);
  v130 = v38;
  *(_QWORD *)v38 = &CSmsProcessorFactory::`vftable';
  v38[2] = 1;
  v144 = v38;
  v39 = ((__int64 (__fastcall *)(_DWORD *, const wchar_t *, __int64 *))CSmsProcessorFactory::GetSmsProcessor)(
          v38,
          L"Interceptor",
          &v123);
  XmlDocument = v39;
  if ( v39 < 0 )
  {
    LogSmsRouterError("CRegistration::SetFilterRules", 0x168u, v39, "Interceptor");
    if ( v123 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v38 + 16LL))(v38);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    goto LABEL_339;
  }
  XmlDocument = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode *))(*(_QWORD *)v123 + 24LL))(v123, v20);
  if ( XmlDocument < 0 )
  {
    v40 = pbstr;
    if ( *((_QWORD *)pbstr + 3) > 7u )
      v40 = *(const wchar_t **)pbstr;
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(const wchar_t **)v15;
    if ( *((_QWORD *)v17 + 3) > 7u )
      v17 = *(const wchar_t **)v17;
    LogSmsRouterError(
      "CRegistration::SetFilterRules",
      0x171u,
      XmlDocument,
      "Parsing FilterXML %S failed, RegName: %S, AppName: %S, UserSid: %S",
      v124,
      v17,
      v15,
      v40);
    if ( v123 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v38 + 16LL))(v38);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    goto LABEL_339;
  }
  v41 = 0;
  v42 = 0;
  v119 = 0;
  v43 = v123;
  if ( a1[30] != v123 )
  {
    if ( v123 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 8LL))(v123);
    v44 = a1[30];
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    a1[30] = v43;
  }
  v154 = 0;
  v155 = 0;
  v156 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v154, &LocaleName);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
    v152,
    &v154);
  std::wstring::~wstring(&v154);
  bstrLeft = 0;
  v45 = 0;
  v145 = 0;
  v46 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, BSTR *))v20->lpVtbl->selectNodes)(
          v20,
          L"/SmsMessageFilter/FilterRule",
          &bstrLeft);
  v47 = v46;
  if ( v46 == 1 )
  {
    v47 = -2147023728;
LABEL_99:
    v48 = bstrLeft;
    v138 = 0;
    goto LABEL_100;
  }
  if ( v46 < 0 )
    goto LABEL_99;
  v45 = (struct IXMLDOMDocument *)bstrLeft;
  v48 = 0;
  bstrLeft = 0;
  v145 = v45;
  v41 = v45;
  v138 = v45;
LABEL_100:
  if ( v48 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v47 < 0 )
  {
    v50 = v122;
LABEL_304:
    if ( v129 )
    {
      Block = 0;
      v127 = 0;
      v104 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(40);
      *v104 = v104;
      v104[1] = v104;
      v104[2] = v104;
      *((_WORD *)v104 + 12) = 257;
      Block = v104;
      v105 = *(BSTR *)a1[31];
      bstrLeft = v105;
      v106 = v143;
      while ( v105 != (BSTR)a1[31] )
      {
        v129 = 0;
        v107 = (OLECHAR *)*((_QWORD *)v105 + 4);
        pbstr = v107;
        v138 = 0;
        CSmsMessageStore::GetMessageXML((CSmsMessageStore *)a1[44], (unsigned __int64)v107, &v138);
        v108 = v138;
        if ( (a1[29] & 1) == 0 || (unsigned int)CSmsMessageStore::HasMessageFlag(a1[44], v107) )
          (*(void (__fastcall **)(__int64, struct IXMLDOMDocument *, int *))(*(_QWORD *)a1[30] + 32LL))(
            a1[30],
            v108,
            &v129);
        if ( v129 )
        {
          v109 = v151;
          p_Block = &Block;
        }
        else
        {
          v111 = a1;
          if ( (unsigned __int64)a1[3] > 7 )
            v111 = (__int64 *)*a1;
          CSmsMessageStore::SetMessageProcessStatus(a1[44], v107, v111, 1);
          v112 = (const unsigned __int16 *)a1;
          if ( (unsigned __int64)a1[3] > 7 )
            v112 = (const unsigned __int16 *)*a1;
          CSmsMessageStore::DeleteMessageDeliveryStatus((CSmsMessageStore *)a1[44], (unsigned __int64)v107, v112);
          v109 = v150;
          p_Block = v106;
        }
        std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(
          p_Block,
          v109,
          &pbstr);
        if ( v108 )
          ((void (__fastcall *)(struct IXMLDOMDocument *))v108->lpVtbl->Release)(v108);
        std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>>::operator++(
          &bstrLeft,
          &v143);
        v105 = bstrLeft;
      }
      std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::clear(a1 + 31);
      std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>>>(
        a1 + 31,
        *(_QWORD *)Block,
        Block);
      v5 = a1 + 38;
      if ( *((_DWORD *)a1 + 108) || v119 )
      {
        *((_DWORD *)a1 + 108) = v119;
        CBroadcastConfigManager::NotifyBroadcastConfigChange((CBroadcastConfigManager *)&CBroadcastConfigManager::s_Instance);
      }
      std::set<SmsServiceCallContext *>::~set<SmsServiceCallContext *>(&Block);
      v50 = v122;
    }
    std::wstring::operator=(a1 + 18, v124);
    *((_DWORD *)a1 + 55) = v134;
    *((_DWORD *)a1 + 59) = v50;
    if ( v45 )
      ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
    if ( v123 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    SysFreeString(0);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v153);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v153);
    return 0;
  }
  v137 = 0;
  v49 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, int *))v41->lpVtbl->get_nodeValue)(v41, &v137);
  if ( v49 >= 0 && v41 )
  {
    v50 = v122;
    if ( ((v122 - 1) & 0xFFFFFFFC) == 0 && v122 != 2 )
    {
      v51 = 0;
      v128 = 0;
      v141 = 0;
      v52 = 0;
      v121 = 0;
      v139 = 0;
      v140 = 0;
      v53 = 0;
      v125 = 0;
      if ( v137 > 0 )
      {
        while ( 1 )
        {
          if ( v52 )
          {
            v121 = 0;
            ((void (__fastcall *)(struct IXMLDOMNode *))v52->lpVtbl->Release)(v52);
          }
          v54 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD, struct IXMLDOMNode **))v138->lpVtbl->get_nodeName)(
                  v138,
                  (unsigned int)v53,
                  &v121);
          XmlDocument = v54;
          if ( v54 < 0 )
          {
            LogSmsRouterError(
              "CRegistration::SetFilterRules",
              0x193u,
              v54,
              "Failed to obtain child nodes for filter, FilterXML %S .",
              v124);
            std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
            if ( v121 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
            ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
            if ( v123 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
            SysFreeString(bstrString);
            (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
            if ( v20 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
            goto LABEL_339;
          }
          v55 = Windows::Sms::Common::CSmsUtil::GetNodeTextValue(v121, L"MessageType", &bstrString);
          XmlDocument = v55;
          if ( v55 < 0 )
          {
            LogSmsRouterError(
              "CRegistration::SetFilterRules",
              0x19Bu,
              v55,
              "Failed to obtain message type for filter at index %d, FilterXML %S .",
              v53,
              v124);
            std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
            if ( v121 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
            ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
            if ( v123 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
            SysFreeString(bstrString);
            (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
            if ( v20 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
            goto LABEL_339;
          }
          if ( (unsigned int)_o__wcsicmp(bstrString, L"Text") )
            break;
          if ( v122 == 1 || (a1[29] & 1) == 0 && v122 == 2 )
          {
            pbstr = 0;
            if ( (int)Windows::Sms::Common::CSmsUtil::GetNodeTextValue(v121, L"TextPrefix", &pbstr) < 0
              || (v56 = SysStringLen(pbstr), v56 < CRegistration::GetMinTextPrefixSize()) )
            {
              MinTextPrefixSize = CRegistration::GetMinTextPrefixSize();
              XmlDocument = -2147024891;
              LogSmsRouterError(
                "CRegistration::SetFilterRules",
                0x1ACu,
                -2147024891,
                "AcceptImmediately or Peek text message filter %d requires TextPrefix with minimum %d characters, FilterXML %S.",
                v53,
                MinTextPrefixSize,
                v124);
              SysFreeString(pbstr);
              std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
              if ( v121 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
              ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
              if ( v123 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
              SysFreeString(bstrString);
              (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
              if ( v20 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
              goto LABEL_339;
            }
            SysFreeString(pbstr);
          }
          if ( g_fTextDone )
            goto LABEL_178;
          v51 = 1;
          v128 = 1;
LABEL_179:
          SysFreeString(bstrString);
          bstrString = 0;
          v125 = ++v53;
          v52 = v121;
          if ( v53 >= v137 )
            goto LABEL_180;
        }
        if ( g_fWapDone || (unsigned int)_o__wcsicmp(bstrString, L"Wap") )
        {
          if ( !(unsigned int)_o__wcsicmp(bstrString, L"Broadcast") )
          {
            v133 = 0;
            v136 = 0;
            v57 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v121->lpVtbl->get_childNodes)(v121, &v133);
            XmlDocument = v57;
            if ( v57 < 0 )
            {
              LogSmsRouterError(
                "CRegistration::SetFilterRules",
                0x1C7u,
                v57,
                "Failed to obtain child nodes for broadcast message filter %d, FilterXML %S.",
                v53,
                v124);
              if ( v133 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
              std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
              if ( v121 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
              ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
              if ( v123 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
              SysFreeString(bstrString);
              (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
              if ( v20 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
              goto LABEL_339;
            }
            v58 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v133 + 64LL))(v133, &v136);
            if ( v58 < 0 )
            {
              LogSmsRouterError(
                "CRegistration::SetFilterRules",
                0x1D0u,
                v58,
                "Failed to obtain child nodes length for broadcast message filter %d, FilterXML %S.",
                v53,
                v124);
              if ( v133 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
              std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
              if ( v121 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
              ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
              if ( v123 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
              SysFreeString(bstrString);
              (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
              if ( v20 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
              goto LABEL_302;
            }
            memset_0(v157, 0, sizeof(v157));
            v59 = SmsRouterBroadcastConfig::SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v157);
            if ( *((_QWORD *)&v139 + 1) == v140 )
            {
              std::vector<SmsRouterBroadcastConfig>::_Emplace_reallocate<SmsRouterBroadcastConfig>(
                &v139,
                *((_QWORD *)&v139 + 1),
                v59);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<SmsRouterBroadcastConfig>>::construct<SmsRouterBroadcastConfig,SmsRouterBroadcastConfig>(
                v60,
                *((_QWORD *)&v139 + 1),
                v59);
              *((_QWORD *)&v139 + 1) += 64LL;
            }
            SmsRouterBroadcastConfig::~SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v157);
            v61 = *((_QWORD *)&v139 + 1);
            v62 = 0;
            v119 = 0;
            if ( v136 > 0 )
            {
              while ( 1 )
              {
                bstrLeft = 0;
                v132 = 0;
                Block = 0;
                v127 = 0;
                v63 = operator new(0x20u);
                *v63 = v63;
                v63[1] = v63;
                v63[2] = v63;
                *((_WORD *)v63 + 12) = 257;
                Block = v63;
                v154 = 0;
                v155 = 0;
                XmlDocument = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v133 + 56LL))(
                                v133,
                                (unsigned int)v62,
                                &v132);
                if ( XmlDocument < 0 )
                  break;
                XmlDocument = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v132 + 56LL))(v132, &bstrLeft);
                if ( XmlDocument < 0 )
                {
                  LogSmsRouterError(
                    "CRegistration::SetFilterRules",
                    0x1F4u,
                    XmlDocument,
                    "Failed to obtain child node name at index %d for broadcast message filter %d, FilterXML %S.",
                    v119,
                    v125,
                    v124);
                  std::vector<std::wstring>::~vector<std::wstring>(&v154);
                  v94 = Block;
                  v95 = (_QWORD *)*((_QWORD *)Block + 1);
                  if ( !*((_BYTE *)v95 + 25) )
                  {
                    do
                    {
                      std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>::_Erase_tree<std::allocator<std::_Tree_node<enum SMS_BROADCAST_TYPES,void *>>>(
                        &Block,
                        &Block,
                        v95[2]);
                      v96 = v95;
                      v95 = (_QWORD *)*v95;
                      operator delete(v96);
                    }
                    while ( !*((_BYTE *)v95 + 25) );
                    v94 = Block;
                  }
                  operator delete(v94);
                  if ( v132 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                  SysFreeString(bstrLeft);
                  if ( v133 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
                  std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
                  if ( v121 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
                  ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
                  if ( v123 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
                  SysFreeString(bstrString);
                  (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
                  if ( v20 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
                  goto LABEL_339;
                }
                v64 = SysAllocString(L"BroadcastType");
                v65 = v64;
                if ( !v64 )
                  goto LABEL_343;
                v66 = VarBstrCmp(bstrLeft, v64, 0x400u, 0);
                SysFreeString(v65);
                if ( v66 == 1 )
                {
                  XmlDocument = GetValueArray(v132, &v154);
                  if ( XmlDocument < 0 )
                  {
                    LogSmsRouterError(
                      "CRegistration::SetFilterRules",
                      0x205u,
                      XmlDocument,
                      "Failed to obtain types at index %d for broadcast message filter %d, FilterXML %S.",
                      v119,
                      v125,
                      v124);
                    std::vector<std::wstring>::~vector<std::wstring>(&v154);
                    v88 = Block;
                    v89 = (_QWORD *)*((_QWORD *)Block + 1);
                    if ( !*((_BYTE *)v89 + 25) )
                    {
                      do
                      {
                        std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>::_Erase_tree<std::allocator<std::_Tree_node<enum SMS_BROADCAST_TYPES,void *>>>(
                          &Block,
                          &Block,
                          v89[2]);
                        v90 = v89;
                        v89 = (_QWORD *)*v89;
                        operator delete(v90);
                      }
                      while ( !*((_BYTE *)v89 + 25) );
                      v88 = Block;
                    }
                    operator delete(v88);
                    if ( v132 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                    SysFreeString(bstrLeft);
                    if ( v133 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
                    std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
                    if ( v121 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
                    ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
                    if ( v123 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
                    SysFreeString(bstrString);
                    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
                    if ( v20 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
                    goto LABEL_339;
                  }
                  v68 = *((_QWORD *)&v154 + 1);
                  for ( i = v154; i != v68; i += 32 )
                  {
                    std::wstring::wstring(v157, i);
                    v69 = v157;
                    if ( v157[3] > 7u )
                      v69 = (_QWORD *)v157[0];
                    LODWORD(v135) = GetBroadcastMessageType(v69);
                    if ( (_DWORD)v135 )
                      std::_Tree<std::_Tset_traits<int,std::less<int>,std::allocator<int>,0>>::insert<0,0>(
                        v61 - 16,
                        v150,
                        &v135);
                    std::wstring::~wstring(v157);
                  }
                }
                else
                {
                  v77 = SysAllocString(L"BroadcastChannel");
                  v78 = v77;
                  if ( !v77 )
LABEL_343:
                    ATL::AtlThrowImpl(-2147024882);
                  v79 = VarBstrCmp(bstrLeft, v77, 0x400u, 0);
                  SysFreeString(v78);
                  if ( v79 == 1 )
                  {
                    XmlDocument = GetIntegerValueArray(v132, &Block);
                    if ( XmlDocument < 0 )
                    {
                      LODWORD(v117) = v125;
                      LogSmsRouterError(
                        "CRegistration::SetFilterRules",
                        0x21Fu,
                        XmlDocument,
                        "Failed to obtain channels for broadcast message filter %d, FilterXML %S.",
                        v119,
                        v117);
                      std::vector<std::wstring>::~vector<std::wstring>(&v154);
                      v91 = Block;
                      v92 = (_QWORD *)*((_QWORD *)Block + 1);
                      if ( !*((_BYTE *)v92 + 25) )
                      {
                        do
                        {
                          std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>::_Erase_tree<std::allocator<std::_Tree_node<enum SMS_BROADCAST_TYPES,void *>>>(
                            &Block,
                            &Block,
                            v92[2]);
                          v93 = v92;
                          v92 = (_QWORD *)*v92;
                          operator delete(v93);
                        }
                        while ( !*((_BYTE *)v92 + 25) );
                        v91 = Block;
                      }
                      operator delete(v91);
                      if ( v132 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                      SysFreeString(bstrLeft);
                      if ( v133 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
                      std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
                      if ( v121 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
                      ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
                      if ( v123 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
                      SysFreeString(bstrString);
                      (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
                      if ( v20 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
                      goto LABEL_339;
                    }
                    v80 = *(__int64 **)Block;
                    while ( !*((_BYTE *)v80 + 25) )
                    {
                      LODWORD(v135) = *((_DWORD *)v80 + 7);
                      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
                        v61 - 32,
                        v151,
                        &v135);
                      v81 = (__int64 **)v80[2];
                      if ( *((_BYTE *)v81 + 25) )
                      {
                        for ( j = (__int64 *)v80[1]; !*((_BYTE *)j + 25) && v80 == (__int64 *)j[2]; j = (__int64 *)j[1] )
                          v80 = j;
                        v80 = j;
                      }
                      else
                      {
                        v80 = (__int64 *)v80[2];
                        for ( k = *v81; !*((_BYTE *)k + 25); k = (__int64 *)*k )
                          v80 = k;
                      }
                    }
                  }
                }
                v70 = SysAllocString(L"SmsDeviceId");
                v71 = v70;
                if ( !v70 )
                  ATL::AtlThrowImpl(-2147024882);
                v72 = VarBstrCmp(bstrLeft, v70, 0x400u, 0);
                SysFreeString(v71);
                if ( v72 == 1 )
                {
                  v135 = 0;
                  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v132 + 208LL))(v132, &v135) >= 0
                    && SysStringLen(v135) )
                  {
                    v73 = v135;
                    v74 = (char **)(v61 - 64);
                    v75 = -1;
                    do
                      ++v75;
                    while ( v135[v75] );
                    if ( v75 > (unsigned __int64)v74[3] )
                    {
                      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v74);
                    }
                    else
                    {
                      if ( (unsigned __int64)v74[3] <= 7 )
                        v76 = (char *)(v61 - 64);
                      else
                        v76 = *v74;
                      v74[2] = (char *)v75;
                      v84 = 2 * v75;
                      memmove_0(v76, v73, 2 * v75);
                      *(_WORD *)&v76[v84] = 0;
                    }
                  }
                  SysFreeString(v135);
                }
                std::vector<std::wstring>::~vector<std::wstring>(&v154);
                std::set<int>::~set<int>(&Block);
                if ( v132 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                SysFreeString(bstrLeft);
                v62 = v119 + 1;
                v119 = v62;
                if ( v62 >= v136 )
                {
                  v53 = v125;
                  goto LABEL_176;
                }
              }
              LogSmsRouterError(
                "CRegistration::SetFilterRules",
                0x1E6u,
                XmlDocument,
                "Failed to obtain child node at index %d for broadcast message filter %d, FilterXML %S.",
                v119,
                v125,
                v124);
              std::vector<std::wstring>::~vector<std::wstring>(&v154);
              v97 = Block;
              v98 = (_QWORD *)*((_QWORD *)Block + 1);
              if ( !*((_BYTE *)v98 + 25) )
              {
                do
                {
                  std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>::_Erase_tree<std::allocator<std::_Tree_node<enum SMS_BROADCAST_TYPES,void *>>>(
                    &Block,
                    &Block,
                    v98[2]);
                  v99 = v98;
                  v98 = (_QWORD *)*v98;
                  operator delete(v99);
                }
                while ( !*((_BYTE *)v98 + 25) );
                v97 = Block;
              }
              operator delete(v97);
              if ( v132 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
              SysFreeString(bstrLeft);
              if ( v133 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
              std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
              if ( v121 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
              ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
              if ( v123 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
              SysFreeString(bstrString);
              (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
              if ( v20 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
              goto LABEL_339;
            }
LABEL_176:
            v42 = 1;
            v119 = 1;
            if ( v133 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
          }
        }
        else
        {
          v141 = 1;
        }
LABEL_178:
        v51 = v128;
        goto LABEL_179;
      }
LABEL_180:
      if ( v52 )
      {
        v121 = 0;
        ((void (__fastcall *)(struct IXMLDOMNode *, _QWORD))v52->lpVtbl->Release)(v52, 0);
      }
      if ( v51 )
      {
        EventW = CreateEventW(0, 0, 0, L"SmsRouter\\TextMessageReadyEvent");
        v86 = EventW;
        if ( EventW )
        {
          SetEvent(EventW);
          CloseHandle(v86);
          g_fTextDone = 1;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          LogSmsRouterError(
            "CRegistration::SetFilterRules",
            0x24Cu,
            LastError,
            "Failed to set %S",
            L"SmsRouter\\TextMessageReadyEvent");
        }
      }
      if ( v141 )
      {
        v101 = CreateEventW(0, 0, 0, L"SmsRouter\\WapMessageReadyEvent");
        v102 = v101;
        if ( v101 )
        {
          SetEvent(v101);
          CloseHandle(v102);
          g_fWapDone = 1;
        }
        else
        {
          v103 = GetLastError();
          if ( v103 > 0 )
            v103 = (unsigned __int16)v103 | 0x80070000;
          LogSmsRouterError(
            "CRegistration::SetFilterRules",
            0x25Bu,
            v103,
            "Failed to set %S",
            L"SmsRouter\\WapMessageReadyEvent");
        }
      }
      if ( v42 )
      {
        CBroadcastConfigManager::SetBroadcastConfig(&CBroadcastConfigManager::s_Instance, a1, &v139);
      }
      else if ( *((_DWORD *)a1 + 108) )
      {
        CBroadcastConfigManager::ClearBroadcastConfig(&CBroadcastConfigManager::s_Instance, a1);
      }
      std::vector<SmsRouterBroadcastConfig>::_Tidy(&v139);
      if ( v121 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v121->lpVtbl->Release)(v121);
      v50 = v122;
    }
    goto LABEL_304;
  }
  LogSmsRouterError(
    "CRegistration::SetFilterRules",
    0x185u,
    v49,
    "Failed to obtain child nodes length, FilterXML %S .",
    v124);
  if ( v41 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v45->lpVtbl->Release)(v45);
  if ( v123 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
  SysFreeString(bstrString);
  (*(void (__fastcall **)(__int64 *))(*v5 + 8))(a1 + 38);
  if ( v20 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
LABEL_302:
  XmlDocument = -2147467259;
LABEL_339:
  SysFreeString(0);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v153);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v153);
  return (unsigned int)XmlDocument;
}

```

## disassembly

```asm
0x180036650  mov     [rsp-8+arg_18], rbx
0x180036655  push    rbp
0x180036656  push    rsi
0x180036657  push    rdi
0x180036658  push    r12
0x18003665a  push    r13
0x18003665c  push    r14
0x18003665e  push    r15
0x180036660  lea     rbp, [rsp-1D0h]
0x180036668  sub     rsp, 2D0h
0x18003666f  mov     rax, cs:__security_cookie
0x180036676  xor     rax, rsp
0x180036679  mov     [rbp+200h+var_40], rax
0x180036680  mov     [rbp+200h+var_200], r8
0x180036684  mov     r15, rdx
0x180036687  mov     [rsp+300h+var_290], rdx
0x18003668c  mov     r12, rcx
0x18003668f  lea     rcx, [rbp+200h+var_1A0]
0x180036693  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180036698  nop
0x180036699  xor     ebx, ebx
0x18003669b  mov     [rbp+200h+var_1E8], rbx
0x18003669f  mov     [rbp+200h+var_1E0], rbx
0x1800366a3  mov     [rbp+200h+var_208], rbx
0x1800366a7  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800366ae  mov     [rbp+200h+var_1D8], rax
0x1800366b2  lea     r13, [r12+130h]
0x1800366ba  mov     [rbp+200h+var_1D0], r13
0x1800366be  mov     rax, [r13+0]
0x1800366c2  mov     rcx, r13
0x1800366c5  mov     rax, [rax]
0x1800366c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366cd  nop
0x1800366ce  test    r15, r15
0x1800366d1  jz      loc_1800382B9
0x1800366d7  cmp     [r15], bx
0x1800366db  jz      loc_1800382B9
0x1800366e1  mov     [rbp+200h+var_26C], ebx
0x1800366e4  cmp     [r12+0A0h], rbx
0x1800366ec  jbe     loc_180036801
0x1800366f2  lea     rcx, [r12+90h]
0x1800366fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800366fe  inc     rax
0x180036701  cmp     [r15+rax*2], bx
0x180036706  jnz     short loc_1800366FE
0x180036708  mov     r8, [rcx+10h]; N
0x18003670c  cmp     qword ptr [rcx+18h], 7
0x180036711  jbe     short loc_180036716
0x180036713  mov     rcx, [rcx]; S1
0x180036716  cmp     r8, rax
0x180036719  jnz     short loc_180036794
0x18003671b  test    r8, r8
0x18003671e  jz      short loc_18003672C
0x180036720  mov     rdx, r15; S2
0x180036723  call    wmemcmp
0x180036728  test    eax, eax
0x18003672a  jnz     short loc_180036794
0x18003672c  lea     rax, [r12+70h]
0x180036731  cmp     qword ptr [rax+18h], 7
0x180036736  jbe     short loc_18003673B
0x180036738  mov     rax, [rax]
0x18003673b  lea     rcx, [r12+50h]
0x180036740  cmp     qword ptr [rcx+18h], 7
0x180036745  jbe     short loc_18003674A
0x180036747  mov     rcx, [rcx]
0x18003674a  lea     r9, [r12+30h]
0x18003674f  cmp     qword ptr [r9+18h], 7
0x180036754  jbe     short loc_180036759
0x180036756  mov     r9, [r9]
0x180036759  mov     [rsp+300h+var_2D8], rax
0x18003675e  mov     [rsp+300h+var_2E0], rcx
0x180036763  lea     r8, aFilterRulesSam; "Filter rules same as before for RegName"...
0x18003676a  mov     edx, 0EBh; unsigned int
0x18003676f  lea     rcx, aCregistrationS_0; "CRegistration::SetFilterRules"
0x180036776  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18003677b  nop
0x18003677c  mov     rax, [r13+0]
0x180036780  mov     rcx, r13
0x180036783  mov     rax, [rax+8]
0x180036787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003678c  nop
0x18003678d  mov     edi, ebx
0x18003678f  jmp     loc_180038293
0x180036794  mov     [rbp+200h+var_26C], 1
0x18003679b  lea     rbx, [r12+70h]
0x1800367a0  mov     [rbp+200h+pbstr], rbx
0x1800367a4  mov     rcx, rbx
0x1800367a7  cmp     qword ptr [rbx+18h], 7
0x1800367ac  jbe     short loc_1800367B1
0x1800367ae  mov     rcx, [rbx]
0x1800367b1  lea     r14, [r12+50h]
0x1800367b6  mov     rdx, r14
0x1800367b9  cmp     qword ptr [r14+18h], 7
0x1800367be  jbe     short loc_1800367C3
0x1800367c0  mov     rdx, [r14]
0x1800367c3  lea     rsi, [r12+30h]
0x1800367c8  mov     rax, rsi
0x1800367cb  cmp     qword ptr [rsi+18h], 7
0x1800367d0  jbe     short loc_1800367D5
0x1800367d2  mov     rax, [rsi]
0x1800367d5  mov     [rsp+300h+var_2D0], rcx
0x1800367da  mov     [rsp+300h+var_2D8], rdx
0x1800367df  mov     [rsp+300h+var_2E0], rax
0x1800367e4  lea     r9, aFilterRulesUpd; "Filter rules updated for RegName: %S, A"...
0x1800367eb  xor     r8d, r8d; int
0x1800367ee  mov     edx, 0F7h; unsigned int
0x1800367f3  lea     rcx, aCregistrationS_0; "CRegistration::SetFilterRules"
0x1800367fa  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800367ff  jmp     short loc_180036814
0x180036801  lea     r14, [r12+50h]
0x180036806  lea     rsi, [r12+30h]
0x18003680b  lea     rbx, [r12+70h]
0x180036810  mov     [rbp+200h+pbstr], rbx
0x180036814  lea     rdx, [rbp+200h+var_208]; struct IXMLDOMDocument **
0x180036818  mov     rcx, r15; unsigned __int16 *
0x18003681b  call    ?GetXmlDocument@CSmsUtil@Common@Sms@Windows@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z; Windows::Sms::Common::CSmsUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)
0x180036820  mov     edi, eax
0x180036822  xor     eax, eax
0x180036824  test    edi, edi
0x180036826  jns     loc_1800368AC
0x18003682c  add     r12, 70h ; 'p'
0x180036830  cmp     qword ptr [r12+18h], 7
0x180036836  jbe     short loc_18003683C
0x180036838  mov     r12, [r12]
0x18003683c  cmp     qword ptr [r14+18h], 7
0x180036841  jbe     short loc_180036846
0x180036843  mov     r14, [r14]
0x180036846  cmp     qword ptr [rsi+18h], 7
0x18003684b  jbe     short loc_180036850
0x18003684d  mov     rsi, [rsi]
0x180036850  mov     [rsp+300h+var_2C8], r12
0x180036855  mov     [rsp+300h+var_2D0], r14
0x18003685a  mov     [rsp+300h+var_2D8], rsi
0x18003685f  mov     [rsp+300h+var_2E0], r15
0x180036864  lea     r9, aMalformedFilte; "Malformed FilterXML %S, RegName: %S, Ap"...
0x18003686b  mov     r8d, edi; int
0x18003686e  mov     edx, 105h; unsigned int
0x180036873  lea     rcx, aCregistrationS_0; "CRegistration::SetFilterRules"
0x18003687a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003687f  nop
0x180036880  mov     rax, [r13+0]
0x180036884  mov     rcx, r13
0x180036887  mov     rax, [rax+8]
0x18003688b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036890  nop
0x180036891  mov     rcx, [rbp+200h+var_208]
0x180036895  test    rcx, rcx
0x180036898  jz      short loc_1800368A7
0x18003689a  mov     rax, [rcx]
0x18003689d  mov     rax, [rax+10h]
0x1800368a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368a6  nop
0x1800368a7  jmp     loc_180038293
0x1800368ac  mov     [rsp+300h+bstrString], rax
0x1800368b1  lea     r8, [rsp+300h+bstrString]; unsigned __int16 **
0x1800368b6  lea     rdx, aSmsmessagefilt_3; "/SmsMessageFilter/@Action"
0x1800368bd  mov     r15, [rbp+200h+var_208]
0x1800368c1  mov     rcx, r15; struct IXMLDOMNode *
0x1800368c4  call    ?GetNodeTextValue@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; Windows::Sms::Common::CSmsUtil::GetNodeTextValue(IXMLDOMNode *,ushort const *,ushort * *)
0x1800368c9  mov     edi, eax
0x1800368cb  test    eax, eax
0x1800368cd  jns     loc_18003695D
0x1800368d3  cmp     qword ptr [rbx+18h], 7
0x1800368d8  jbe     short loc_1800368DD
0x1800368da  mov     rbx, [rbx]
0x1800368dd  cmp     qword ptr [r14+18h], 7
0x1800368e2  jbe     short loc_1800368E7
0x1800368e4  mov     r14, [r14]
0x1800368e7  cmp     qword ptr [rsi+18h], 7
0x1800368ec  jbe     short loc_1800368F1
0x1800368ee  mov     rsi, [rsi]
0x1800368f1  mov     [rsp+300h+var_2C8], rbx
0x1800368f6  mov     [rsp+300h+var_2D0], r14
0x1800368fb  mov     [rsp+300h+var_2D8], rsi
0x180036900  mov     rdx, [rsp+300h+var_290]
0x180036905  mov     [rsp+300h+var_2E0], rdx
0x18003690a  lea     r9, aMalformedFilte; "Malformed FilterXML %S, RegName: %S, Ap"...
0x180036911  mov     r8d, eax; int
0x180036914  mov     edx, 115h; unsigned int
0x180036919  lea     rcx, aCregistrationS_0; "CRegistration::SetFilterRules"
0x180036920  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180036925  nop
0x180036926  mov     rcx, [rsp+300h+bstrString]; bstrString
0x18003692b  call    cs:__imp_SysFreeString
0x180036931  nop
0x180036932  mov     rax, [r13+0]
0x180036936  mov     rcx, r13
0x180036939  mov     rax, [rax+8]
0x18003693d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036942  nop
0x180036943  test    r15, r15
0x180036946  jz      short loc_180036958
0x180036948  mov     rax, [r15]
0x18003694b  mov     rcx, r15
0x18003694e  mov     rax, [rax+10h]
0x180036952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036957  nop
0x180036958  jmp     loc_180038293
0x18003695d  lea     rcx, aAcceptimmediat_0; "AcceptImmediately"
0x180036964  call    cs:__imp_SysAllocString
0x18003696a  mov     rbx, rax
0x18003696d  test    rax, rax
0x180036970  jz      loc_18003831B
0x180036976  xor     r9d, r9d; dwFlags
0x180036979  mov     r8d, 400h; lcid
0x18003697f  mov     rdx, rax; bstrRight
0x180036982  mov     rcx, [rsp+300h+bstrString]; bstrLeft
0x180036987  call    cs:__imp_VarBstrCmp
0x18003698d  mov     edi, eax
0x18003698f  mov     rcx, rbx; bstrString
0x180036992  call    cs:__imp_SysFreeString
0x180036998  cmp     edi, 1
0x18003699b  jnz     short loc_1800369A9
0x18003699d  mov     ebx, edi
0x18003699f  mov     edi, 10000000h
0x1800369a4  jmp     loc_180036A98
0x1800369a9  lea     rcx, aDrop; "Drop"
0x1800369b0  call    cs:__imp_SysAllocString
0x1800369b6  mov     rbx, rax
0x1800369b9  test    rax, rax
0x1800369bc  jz      loc_18003831B
0x1800369c2  xor     r9d, r9d; dwFlags
0x1800369c5  mov     r8d, 400h; lcid
0x1800369cb  mov     rdx, rax; bstrRight
0x1800369ce  mov     rcx, [rsp+300h+bstrString]; bstrLeft
0x1800369d3  call    cs:__imp_VarBstrCmp
0x1800369d9  mov     edi, eax
0x1800369db  mov     rcx, rbx; bstrString
0x1800369de  call    cs:__imp_SysFreeString
0x1800369e4  cmp     edi, 1
0x1800369e7  jnz     short loc_1800369F6
0x1800369e9  lea     ebx, [rdi+1]
0x1800369ec  mov     edi, 1000000h
0x1800369f1  jmp     loc_180036A98
0x1800369f6  lea     rcx, aPeek; "Peek"
0x1800369fd  call    cs:__imp_SysAllocString
0x180036a03  mov     rbx, rax
0x180036a06  test    rax, rax
0x180036a09  jz      loc_18003831B
0x180036a0f  xor     r9d, r9d; dwFlags
0x180036a12  mov     r8d, 400h; lcid
0x180036a18  mov     rdx, rax; bstrRight
0x180036a1b  mov     rcx, [rsp+300h+bstrString]; bstrLeft
0x180036a20  call    cs:__imp_VarBstrCmp
0x180036a26  mov     edi, eax
0x180036a28  mov     rcx, rbx; bstrString
0x180036a2b  call    cs:__imp_SysFreeString
0x180036a31  cmp     edi, 1
0x180036a34  jnz     short loc_180036A4C
0x180036a36  lea     ebx, [rdi+2]
0x180036a39  mov     edi, 100000h
0x180036a3e  mov     dword ptr [r12+0E4h], 1
0x180036a4a  jmp     short loc_180036A98
0x180036a4c  lea     rcx, aAccept; "Accept"
0x180036a53  call    cs:__imp_SysAllocString
0x180036a59  mov     rbx, rax
0x180036a5c  test    rax, rax
0x180036a5f  jz      loc_18003831B
0x180036a65  xor     r9d, r9d; dwFlags
0x180036a68  mov     r8d, 400h; lcid
0x180036a6e  mov     rdx, rax; bstrRight
0x180036a71  mov     rcx, [rsp+300h+bstrString]; bstrLeft
0x180036a76  call    cs:__imp_VarBstrCmp
0x180036a7c  mov     edi, eax
0x180036a7e  mov     rcx, rbx; bstrString
0x180036a81  call    cs:__imp_SysFreeString
0x180036a87  cmp     edi, 1
0x180036a8a  jnz     loc_1800381F9
0x180036a90  lea     ebx, [rdi+3]
0x180036a93  mov     edi, 10000h
0x180036a98  mov     [rbp+200h+var_248], edi
0x180036a9b  mov     [rsp+300h+var_2A0], ebx
0x180036a9f  mov     rcx, [rsp+300h+bstrString]; bstrString
0x180036aa4  call    cs:__imp_SysFreeString
0x180036aaa  mov     [rsp+300h+bstrString], 0
0x180036ab3  lea     r8, [rsp+300h+bstrString]; unsigned __int16 **
0x180036ab8  lea     rdx, aSmsmessagefilt_4; "/SmsMessageFilter/@Flags"
0x180036abf  mov     rcx, r15; struct IXMLDOMNode *
0x180036ac2  call    ?GetNodeTextValue@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; Windows::Sms::Common::CSmsUtil::GetNodeTextValue(IXMLDOMNode *,ushort const *,ushort * *)
0x180036ac7  xor     ecx, ecx
0x180036ac9  test    eax, eax
0x180036acb  js      short loc_180036ADA
0x180036acd  mov     rcx, [rsp+300h+bstrString]
0x180036ad2  call    cs:__imp__o__wtoi
0x180036ad8  jmp     short loc_180036ADC
0x180036ada  mov     eax, ecx
0x180036adc  mov     [r12+0E8h], eax
0x180036ae4  mov     rcx, [rsp+300h+bstrString]; bstrString
0x180036ae9  call    cs:__imp_SysFreeString
0x180036aef  xor     eax, eax
0x180036af1  mov     [rsp+300h+bstrString], rax
0x180036af6  cmp     [r12+0A0h], rax
0x180036afe  jz      loc_180036BAF
0x180036b04  cmp     [r12+0DCh], edi
0x180036b0c  jnz     short loc_180036B1C
0x180036b0e  cmp     [r12+0ECh], ebx
0x180036b16  jz      loc_180036BAF
0x180036b1c  mov     rax, [rbp+200h+pbstr]
0x180036b20  cmp     qword ptr [rax+18h], 7
0x180036b25  jbe     short loc_180036B2A
  ... truncated ...
```
