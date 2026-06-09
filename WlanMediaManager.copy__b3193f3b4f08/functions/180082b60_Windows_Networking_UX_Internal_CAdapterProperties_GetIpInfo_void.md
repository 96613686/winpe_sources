# Windows::Networking::UX::Internal::CAdapterProperties::GetIpInfo(void)

- ea: `0x180082b60`
- end: `0x180082eb1`
- name: `?GetIpInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `849`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800849f8`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18001d6d0`
- `0x1800373ec`
- `0x1800812c4`
- `0x18008168c`
- `0x18008186c`
- `0x1800820e8`
- `0x180082b60`
- `0x180083d00`
- `0x180084ea8`
- `0x1800871f0`
- `0x1800876d8`
- `0x180089410`
- `0x18008e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x180082bfc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x180082bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e29`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180082bcb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180082bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e50`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetIpInfo(GUID *this)
{
  Windows::Networking::UX::Internal::CAdapterProperties *v2; // rcx
  signed int LastError; // eax
  signed int AdapterAddressList; // ebx
  HSTRING v5; // r14
  HSTRING v6; // rdi
  Windows::Networking::UX::Internal::CAdapterProperties *v7; // rcx
  struct _IP_ADAPTER_UNICAST_ADDRESS_LH *i; // rsi
  struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *v9; // rdx
  wchar_t *ProfileDnsServerView; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  wchar_t *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 j; // rsi
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  _QWORD *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v24; // [rsp+20h] [rbp-F8h]
  bool v25; // [rsp+30h] [rbp-E8h] BYREF
  int v26; // [rsp+34h] [rbp-E4h] BYREF
  HSTRING string; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+48h] [rbp-D0h] BYREF
  char Str1[48]; // [rsp+50h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  if ( StringFromGUID2(this + 2, sz, 39) )
  {
    string = 0;
    v24 = 38;
    if ( !(unsigned int)_o_wcstombs_s(&string, Str1, 39, sz) )
      goto LABEL_9;
  }
  LastError = GetLastError();
  AdapterAddressList = LastError;
  if ( LastError > 0 )
    AdapterAddressList = (unsigned __int16)LastError | 0x80070000;
  if ( AdapterAddressList >= 0 )
  {
LABEL_9:
    string = 0;
    AdapterAddressList = Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(
                           v2,
                           (struct _IP_ADAPTER_ADDRESSES_LH **)&string);
    v5 = string;
    if ( AdapterAddressList >= 0 && string )
    {
      v6 = string;
      while ( strncmp_0(Str1, *((const char **)v6 + 2), 0x27u) )
      {
        v6 = (HSTRING)*((_QWORD *)v6 + 1);
        if ( !v6 )
        {
          v6 = v5;
          if ( !v5 )
            goto LABEL_44;
          do
          {
            if ( *((_QWORD *)v6 + 3) )
            {
              v25 = 0;
              if ( Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
                     v7,
                     this + 2,
                     *((char **)v6 + 2),
                     &v25) >= 0
                && v25 )
              {
                break;
              }
            }
            v6 = (HSTRING)*((_QWORD *)v6 + 1);
          }
          while ( v6 );
          if ( !v6 )
            goto LABEL_44;
          break;
        }
      }
      for ( i = (struct _IP_ADAPTER_UNICAST_ADDRESS_LH *)*((_QWORD *)v6 + 3); i; i = i->Next )
        Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(
          (Windows::Networking::UX::Internal::CAdapterProperties *)this,
          i);
      v9 = (struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *)*((_QWORD *)v6 + 26);
      if ( v9 )
        Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(
          (Windows::Networking::UX::Internal::CAdapterProperties *)this,
          v9);
      v26 = 0;
      TryGetInterfaceDnsServerView(&v29, this + 2, 4);
      if ( v29 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 56LL))(v29, &v26);
      if ( !v26 )
      {
        ProfileDnsServerView = TryGetProfileDnsServerView((wchar_t *)&string, this + 2, 4);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
          &v29,
          ProfileDnsServerView);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          &string,
          v11,
          v12);
      }
      TryGetInterfaceDnsServerView(&v28, this + 2, 6);
      if ( v28 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 56LL))(v28, &v26);
      if ( !v26 )
      {
        v13 = TryGetProfileDnsServerView((wchar_t *)&string, this + 2, 6);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
          &v28,
          v13);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          &string,
          v14,
          v15);
      }
      for ( j = *((_QWORD *)v6 + 6); j; j = *(_QWORD *)(j + 8) )
      {
        v17 = *(_QWORD *)(j + 16);
        if ( v17 )
          Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(this, v17, v29, v28, v24);
      }
      Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&this[5], v6 + 14);
      v20 = (_QWORD *)*((_QWORD *)v6 + 55);
      while ( v20 )
      {
        string = 0;
        AdapterAddressList = Microsoft::WRL::Wrappers::HString::Set<65>(&string, v20 + 1);
        if ( AdapterAddressList >= 0 )
          (*(void (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)this[9].Data4 + 104LL))(
            *(_QWORD *)this[9].Data4,
            string);
        v20 = (_QWORD *)*v20;
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v18, v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v21, v22);
    }
    else
    {
LABEL_44:
      AdapterAddressList = -2147024894;
    }
    CoTaskMemFree(v5);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
      (unsigned int)AdapterAddressList);
  return (unsigned int)AdapterAddressList;
}

```

## disassembly

```asm
0x180082b60  push    rbx
0x180082b62  push    rsi
0x180082b63  push    rdi
0x180082b64  push    r12
0x180082b66  push    r14
0x180082b68  push    r15
0x180082b6a  sub     rsp, 0E8h
0x180082b71  mov     rax, cs:__security_cookie
0x180082b78  xor     rax, rsp
0x180082b7b  mov     [rsp+118h+var_48], rax
0x180082b83  mov     r15, rcx
0x180082b86  lea     rax, WPP_GLOBAL_Control
0x180082b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b94  cmp     rcx, rax
0x180082b97  jz      short loc_180082BB4
0x180082b99  test    byte ptr [rcx+1Ch], 40h
0x180082b9d  jz      short loc_180082BB4
0x180082b9f  mov     edx, 13h
0x180082ba4  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180082bab  mov     rcx, [rcx+10h]
0x180082baf  call    WPP_SF_
0x180082bb4  lea     r12, [r15+20h]
0x180082bb8  mov     esi, 27h ; '''
0x180082bbd  mov     r8d, esi; cchMax
0x180082bc0  lea     rdx, [rsp+118h+sz]; lpsz
0x180082bc8  mov     rcx, r12; rguid
0x180082bcb  call    cs:__imp_StringFromGUID2
0x180082bd1  test    eax, eax
0x180082bd3  jz      short loc_180082C06
0x180082bd5  mov     [rsp+118h+string], 0
0x180082bde  mov     [rsp+118h+var_F8], 26h ; '&'
0x180082be7  lea     r9, [rsp+118h+sz]
0x180082bef  mov     r8d, esi
0x180082bf2  lea     rdx, [rsp+118h+Str1]
0x180082bf7  lea     rcx, [rsp+118h+string]
0x180082bfc  call    cs:__imp__o_wcstombs_s
0x180082c02  test    eax, eax
0x180082c04  jz      short loc_180082C23
0x180082c06  call    cs:__imp_GetLastError
0x180082c0c  test    eax, eax
0x180082c0e  mov     ebx, eax
0x180082c10  jle     short loc_180082C1B
0x180082c12  movzx   ebx, ax
0x180082c15  or      ebx, 80070000h
0x180082c1b  test    ebx, ebx
0x180082c1d  js      loc_180082E56
0x180082c23  mov     [rsp+118h+string], 0
0x180082c2c  lea     rdx, [rsp+118h+string]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180082c31  call    ?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)
0x180082c36  mov     ebx, eax
0x180082c38  mov     r14, [rsp+118h+string]
0x180082c3d  test    eax, eax
0x180082c3f  js      loc_180082E48
0x180082c45  test    r14, r14
0x180082c48  jz      loc_180082E48
0x180082c4e  mov     rdi, r14
0x180082c51  mov     r8d, esi; MaxCount
0x180082c54  mov     rdx, [rdi+10h]; Str2
0x180082c58  lea     rcx, [rsp+118h+Str1]; Str1
0x180082c5d  call    strncmp_0
0x180082c62  test    eax, eax
0x180082c64  jz      short loc_180082CB5
0x180082c66  mov     rdi, [rdi+8]
0x180082c6a  test    rdi, rdi
0x180082c6d  jnz     short loc_180082C51
0x180082c6f  mov     rdi, r14
0x180082c72  test    r14, r14
0x180082c75  jz      loc_180082E48
0x180082c7b  cmp     qword ptr [rdi+18h], 0
0x180082c80  jz      short loc_180082CA3
0x180082c82  mov     [rsp+118h+var_E8], 0
0x180082c87  lea     r9, [rsp+118h+var_E8]; bool *
0x180082c8c  mov     r8, [rdi+10h]; char *
0x180082c90  mov     rdx, r12; struct _GUID *
0x180082c93  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)
0x180082c98  test    eax, eax
0x180082c9a  js      short loc_180082CA3
0x180082c9c  cmp     [rsp+118h+var_E8], 0
0x180082ca1  jnz     short loc_180082CAC
0x180082ca3  mov     rdi, [rdi+8]
0x180082ca7  test    rdi, rdi
0x180082caa  jnz     short loc_180082C7B
0x180082cac  test    rdi, rdi
0x180082caf  jz      loc_180082E48
0x180082cb5  mov     rsi, [rdi+18h]
0x180082cb9  test    rsi, rsi
0x180082cbc  jz      short loc_180082CCF
0x180082cbe  mov     rdx, rsi; struct _IP_ADAPTER_UNICAST_ADDRESS_LH *
0x180082cc1  mov     rcx, r15; this
0x180082cc4  call    ?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)
0x180082cc9  mov     rsi, [rsi+8]
0x180082ccd  jmp     short loc_180082CB9
0x180082ccf  mov     rdx, [rdi+0D0h]; struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *
0x180082cd6  test    rdx, rdx
0x180082cd9  jz      short loc_180082CE3
0x180082cdb  mov     rcx, r15; this
0x180082cde  call    ?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)
0x180082ce3  mov     [rsp+118h+var_E4], 0
0x180082ceb  mov     esi, 4
0x180082cf0  mov     r8d, esi
0x180082cf3  mov     rdx, r12
0x180082cf6  lea     rcx, [rsp+118h+var_D0]
0x180082cfb  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180082d00  nop
0x180082d01  mov     rcx, [rsp+118h+var_D0]
0x180082d06  test    rcx, rcx
0x180082d09  jz      short loc_180082D1C
0x180082d0b  mov     rax, [rcx]
0x180082d0e  lea     rdx, [rsp+118h+var_E4]
0x180082d13  mov     rax, [rax+38h]
0x180082d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d1c  cmp     [rsp+118h+var_E4], 0
0x180082d21  jnz     short loc_180082D4A
0x180082d23  mov     r8d, esi
0x180082d26  mov     rdx, r12
0x180082d29  lea     rcx, [rsp+118h+string]
0x180082d2e  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180082d33  mov     rdx, rax
0x180082d36  lea     rcx, [rsp+118h+var_D0]
0x180082d3b  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x180082d40  lea     rcx, [rsp+118h+string]
0x180082d45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082d4a  mov     esi, 6
0x180082d4f  mov     r8d, esi
0x180082d52  mov     rdx, r12
0x180082d55  lea     rcx, [rsp+118h+var_D8]
0x180082d5a  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180082d5f  nop
0x180082d60  mov     rcx, [rsp+118h+var_D8]
0x180082d65  test    rcx, rcx
0x180082d68  jz      short loc_180082D7B
0x180082d6a  mov     rax, [rcx]
0x180082d6d  lea     rdx, [rsp+118h+var_E4]
0x180082d72  mov     rax, [rax+38h]
0x180082d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d7b  cmp     [rsp+118h+var_E4], 0
0x180082d80  jnz     short loc_180082DA9
0x180082d82  mov     r8d, esi
0x180082d85  mov     rdx, r12
0x180082d88  lea     rcx, [rsp+118h+string]
0x180082d8d  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180082d92  mov     rdx, rax
0x180082d95  lea     rcx, [rsp+118h+var_D8]
0x180082d9a  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x180082d9f  lea     rcx, [rsp+118h+string]
0x180082da4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082da9  mov     rsi, [rdi+30h]
0x180082dad  jmp     short loc_180082DCE
0x180082daf  mov     rdx, [rsi+10h]
0x180082db3  test    rdx, rdx
0x180082db6  jz      short loc_180082DCA
0x180082db8  mov     r9, [rsp+118h+var_D8]
0x180082dbd  mov     r8, [rsp+118h+var_D0]
0x180082dc2  mov     rcx, r15
0x180082dc5  call    ?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180082dca  mov     rsi, [rsi+8]
0x180082dce  test    rsi, rsi
0x180082dd1  jnz     short loc_180082DAF
0x180082dd3  lea     rdx, [rdi+38h]
0x180082dd7  lea     rcx, [r15+50h]
0x180082ddb  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180082de0  mov     rdi, [rdi+1B8h]
0x180082de7  test    rdi, rdi
0x180082dea  jz      short loc_180082E31
0x180082dec  mov     [rsp+118h+string], 0
0x180082df5  lea     rdx, [rdi+8]
0x180082df9  lea     rcx, [rsp+118h+string]
0x180082dfe  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180082e03  mov     ebx, eax
0x180082e05  test    eax, eax
0x180082e07  js      short loc_180082E21
0x180082e09  mov     rcx, [r15+98h]
0x180082e10  mov     rax, [rcx]
0x180082e13  mov     rdx, [rsp+118h+string]
0x180082e18  mov     rax, [rax+68h]
0x180082e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e21  mov     rdi, [rdi]
0x180082e24  mov     rcx, [rsp+118h+string]; string
0x180082e29  call    cs:__imp_WindowsDeleteString
0x180082e2f  jmp     short loc_180082DE7
0x180082e31  lea     rcx, [rsp+118h+var_D8]
0x180082e36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082e3b  nop
0x180082e3c  lea     rcx, [rsp+118h+var_D0]
0x180082e41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082e46  jmp     short loc_180082E4D
0x180082e48  mov     ebx, 80070002h
0x180082e4d  mov     rcx, r14; pv
0x180082e50  call    cs:__imp_CoTaskMemFree
0x180082e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180082e5d  lea     rax, WPP_GLOBAL_Control
0x180082e64  cmp     rcx, rax
0x180082e67  jz      short loc_180082E87
0x180082e69  test    byte ptr [rcx+1Ch], 40h
0x180082e6d  jz      short loc_180082E87
0x180082e6f  mov     edx, 14h
0x180082e74  mov     r9d, ebx
0x180082e77  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180082e7e  mov     rcx, [rcx+10h]
0x180082e82  call    WPP_SF_d
0x180082e87  mov     eax, ebx
0x180082e89  jmp     short loc_180082E8F
0x180082e8b  mov     eax, [rsp+118h+var_E4]
0x180082e8f  mov     rcx, [rsp+118h+var_48]
0x180082e97  xor     rcx, rsp; StackCookie
0x180082e9a  call    __security_check_cookie
0x180082e9f  add     rsp, 0E8h
0x180082ea6  pop     r15
0x180082ea8  pop     r14
0x180082eaa  pop     r12
0x180082eac  pop     rdi
0x180082ead  pop     rsi
0x180082eae  pop     rbx
0x180082eaf  retn
```
