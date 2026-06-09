# Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(bool,ushort const *)

- ea: `0x1800486c8`
- end: `0x18004889c`
- name: `?_CompleteAddNetworkWiFiUriTipTest@WlanInterface@Internal@UX@Networking@Windows@@IEAAJ_NPEBG@Z`
- size: `468`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041c70`

## callees

- `0x1800097b4`
- `0x18000a394`
- `0x18000de4c`
- `0x18001d4d4`
- `0x1800373ec`
- `0x180039314`
- `0x18003a000`
- `0x18003a108`
- `0x18003ad00`
- `0x18003ae0c`
- `0x1800486c8`
- `0x18004dd08`
- `0x18004f768`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004887b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800487a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800487a6`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(
        Windows::Networking::UX::Internal::WlanInterface *this,
        char a2,
        const unsigned __int16 *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HSTRING v8; // rcx
  __int128 v10; // xmm0
  LPVOID v11; // rax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string2; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const unsigned __int16 *v18; // [rsp+80h] [rbp+30h] BYREF
  INT32 result; // [rsp+88h] [rbp+38h] BYREF

  v18 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  string2 = 0;
  v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string2, &v18);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1783;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v5,
      v13);
    WindowsDeleteString(string2);
    return v6;
  }
  v8 = (HSTRING)*((_QWORD *)this + 174);
  result = 0;
  v5 = WindowsCompareStringOrdinal(v8, string2, &result);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1786;
    goto LABEL_8;
  }
  if ( !result )
  {
    v10 = *((_OWORD *)this + 86);
    v13 = 0;
    v16 = v10;
    v11 = CoTaskMemAlloc(0x128u);
    if ( !v11 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
    v15[0] = tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>(
               v11,
               &v16);
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::operator=(
      &v13,
      v15);
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(v15);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v13 + 8) )
    {
      if ( a2 )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                                 &v13,
                                 v15)
                  + 276LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(v15);
      }
      tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(&v13);
    }
    *((GUID *)this + 86) = GUID_NULL;
    WindowsDeleteString(*((HSTRING *)this + 174));
    *((_QWORD *)this + 174) = 0;
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(&v13);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
  WindowsDeleteString(string2);
  return 0;
}

```

## disassembly

```asm
0x1800486c8  mov     [rsp-18h+arg_0], rbx
0x1800486cd  mov     [rsp-18h+arg_8], rsi
0x1800486d2  mov     [rsp-18h+arg_10], r8
0x1800486d7  push    rbp
0x1800486d8  push    rdi
0x1800486d9  push    r15
0x1800486db  mov     rbp, rsp
0x1800486de  sub     rsp, 50h
0x1800486e2  mov     sil, dl
0x1800486e5  mov     rdi, rcx
0x1800486e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486ef  lea     r15, WPP_GLOBAL_Control
0x1800486f6  cmp     rcx, r15
0x1800486f9  jz      short loc_180048716
0x1800486fb  test    byte ptr [rcx+1Ch], 8
0x1800486ff  jz      short loc_180048716
0x180048701  mov     rcx, [rcx+10h]
0x180048705  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004870c  mov     edx, 8Dh
0x180048711  call    WPP_SF_
0x180048716  lea     rdx, [rbp+arg_10]
0x18004871a  mov     [rbp+string2], 0
0x180048722  lea     rcx, [rbp+string2]
0x180048726  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004872b  mov     ebx, eax
0x18004872d  test    eax, eax
0x18004872f  jns     short loc_180048738
0x180048731  mov     edx, 6F7h
0x180048736  jmp     short loc_18004875F
0x180048738  mov     rdx, [rbp+string2]; string2
0x18004873c  lea     r8, [rbp+result]; result
0x180048740  mov     rcx, [rdi+570h]; string1
0x180048747  mov     [rbp+result], 0
0x18004874e  call    cs:__imp_WindowsCompareStringOrdinal
0x180048754  mov     ebx, eax
0x180048756  test    eax, eax
0x180048758  jns     short loc_180048783
0x18004875a  mov     edx, 6FAh; void *
0x18004875f  mov     rcx, [rbp+18h]; this
0x180048763  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004876a  mov     r9d, eax; char *
0x18004876d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048772  mov     rcx, [rbp+string2]; string
0x180048776  call    cs:__imp_WindowsDeleteString
0x18004877c  mov     eax, ebx
0x18004877e  jmp     loc_180048883
0x180048783  cmp     [rbp+result], 0
0x180048787  jnz     loc_18004884D
0x18004878d  movups  xmm0, xmmword ptr [rdi+560h]
0x180048794  mov     ecx, 128h; cb
0x180048799  mov     [rbp+var_30], 0
0x1800487a1  movdqu  [rbp+var_10], xmm0
0x1800487a6  call    cs:__imp_CoTaskMemAlloc
0x1800487ac  test    rax, rax
0x1800487af  jz      loc_180048896
0x1800487b5  lea     rdx, [rbp+var_10]
0x1800487b9  mov     rcx, rax
0x1800487bc  call    ??0?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>(_GUID *)
0x1800487c1  lea     rdx, [rbp+var_20]
0x1800487c5  mov     [rbp+var_20], rax
0x1800487c9  lea     rcx, [rbp+var_30]
0x1800487cd  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy> &&)
0x1800487d2  lea     rcx, [rbp+var_20]
0x1800487d6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(void)
0x1800487db  mov     rcx, [rbp+var_30]
0x1800487df  add     rcx, 8
0x1800487e3  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800487e8  test    al, al
0x1800487ea  jz      short loc_18004881D
0x1800487ec  test    sil, sil
0x1800487ef  jz      short loc_180048814
0x1800487f1  lea     rdx, [rbp+var_20]
0x1800487f5  lea     rcx, [rbp+var_30]
0x1800487f9  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x1800487fe  mov     rcx, [rax]
0x180048801  mov     dword ptr [rcx+114h], 3
0x18004880b  lea     rcx, [rbp+var_20]
0x18004880f  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x180048814  lea     rcx, [rbp+var_30]
0x180048818  call    ?complete@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(void)
0x18004881d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048824  movdqu  xmmword ptr [rdi+560h], xmm0
0x18004882c  mov     rcx, [rdi+570h]; string
0x180048833  call    cs:__imp_WindowsDeleteString
0x180048839  lea     rcx, [rbp+var_30]
0x18004883d  mov     qword ptr [rdi+570h], 0
0x180048848  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(void)
0x18004884d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048854  cmp     rcx, r15
0x180048857  jz      short loc_180048877
0x180048859  test    byte ptr [rcx+1Ch], 8
0x18004885d  jz      short loc_180048877
0x18004885f  mov     rcx, [rcx+10h]
0x180048863  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004886a  mov     edx, 8Eh
0x18004886f  xor     r9d, r9d
0x180048872  call    WPP_SF_d
0x180048877  mov     rcx, [rbp+string2]; string
0x18004887b  call    cs:__imp_WindowsDeleteString
0x180048881  xor     eax, eax
0x180048883  mov     rbx, [rsp+50h+arg_0]
0x180048888  mov     rsi, [rsp+50h+arg_8]
0x18004888d  add     rsp, 50h
0x180048891  pop     r15
0x180048893  pop     rdi
0x180048894  pop     rbp
0x180048895  retn
0x180048896  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
