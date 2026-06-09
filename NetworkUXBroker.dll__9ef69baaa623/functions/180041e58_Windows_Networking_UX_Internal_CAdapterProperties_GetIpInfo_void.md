# Windows::Networking::UX::Internal::CAdapterProperties::GetIpInfo(void)

- ea: `0x180041e58`
- end: `0x1800421e3`
- name: `?GetIpInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `907`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042718`

## callees

- `0x180002520`
- `0x18000955c`
- `0x18000a6e4`
- `0x18000b43c`
- `0x18000e86c`
- `0x18000efb4`
- `0x180037c4c`
- `0x18003a438`
- `0x18003a920`
- `0x180041074`
- `0x1800410ec`
- `0x1800412cc`
- `0x1800417e0`
- `0x180041e58`
- `0x180043270`
- `0x180043730`
- `0x180044a64`
- `0x180047010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x180041efc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x180041efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004214f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004214f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042176`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041ecc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041ecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetIpInfo(GUID *this)
{
  Windows::Networking::UX::Internal::CAdapterProperties *v2; // rcx
  signed int LastError; // eax
  signed int AdapterAddressList; // edi
  void *v5; // r15
  LPVOID v6; // rbx
  Windows::Networking::UX::Internal::CAdapterProperties *v7; // rcx
  struct _IP_ADAPTER_UNICAST_ADDRESS_LH *i; // rsi
  struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *v9; // rdx
  wchar_t *ProfileDnsServerView; // rax
  wchar_t *v11; // rax
  __int64 j; // rsi
  __int64 v13; // rdx
  __int64 *v14; // rsi
  HSTRING v15; // rbx
  unsigned __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-E8h]
  bool v19; // [rsp+30h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v23; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B8h] BYREF
  char Str1[40]; // [rsp+58h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  if ( StringFromGUID2(this + 2, sz, 39) )
  {
    pv = 0;
    v18 = 38;
    if ( !(unsigned int)_o_wcstombs_s(&pv, Str1, 39, sz) )
      goto LABEL_9;
  }
  LastError = GetLastError();
  AdapterAddressList = LastError;
  if ( LastError > 0 )
    AdapterAddressList = (unsigned __int16)LastError | 0x80070000;
  if ( AdapterAddressList >= 0 )
  {
LABEL_9:
    pv = 0;
    AdapterAddressList = Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(
                           v2,
                           (struct _IP_ADAPTER_ADDRESSES_LH **)&pv);
    v5 = pv;
    if ( AdapterAddressList >= 0 && pv )
    {
      v6 = pv;
      while ( strncmp_0(Str1, *((const char **)v6 + 2), 0x27u) )
      {
        v6 = (LPVOID)*((_QWORD *)v6 + 1);
        if ( !v6 )
        {
          v6 = v5;
          if ( !v5 )
            goto LABEL_48;
          do
          {
            if ( *((_QWORD *)v6 + 3) )
            {
              v19 = 0;
              if ( Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
                     v7,
                     this + 2,
                     *((char **)v6 + 2),
                     &v19) >= 0
                && v19 )
              {
                break;
              }
            }
            v6 = (LPVOID)*((_QWORD *)v6 + 1);
          }
          while ( v6 );
          if ( !v6 )
            goto LABEL_48;
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
      v21 = 0;
      TryGetInterfaceDnsServerView(&v24, this + 2, 4);
      if ( v24 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 56LL))(v24, &v21);
      if ( !v21 )
      {
        ProfileDnsServerView = TryGetProfileDnsServerView((wchar_t *)&pv, this + 2, 4);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
          &v24,
          ProfileDnsServerView);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      }
      TryGetInterfaceDnsServerView(&v23, this + 2, 6);
      if ( v23 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 56LL))(v23, &v21);
      if ( !v21 )
      {
        v11 = TryGetProfileDnsServerView((wchar_t *)&pv, this + 2, 6);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
          &v23,
          v11);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      }
      for ( j = *((_QWORD *)v6 + 6); j; j = *(_QWORD *)(j + 8) )
      {
        v13 = *(_QWORD *)(j + 16);
        if ( v13 )
          Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(this, v13, v24, v23, v18);
      }
      Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&this[5]);
      v14 = (__int64 *)*((_QWORD *)v6 + 55);
      while ( v14 )
      {
        v15 = 0;
        pv = 0;
        v22 = 0;
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v14 + v16 + 4) );
        AdapterAddressList = ULongLongToUInt(v16, &v22);
        if ( AdapterAddressList >= 0 )
        {
          AdapterAddressList = Microsoft::WRL::Wrappers::HString::Set(
                                 (Microsoft::WRL::Wrappers::HString *)&pv,
                                 (const unsigned __int16 *)v14 + 4,
                                 v22);
          v15 = (HSTRING)pv;
        }
        if ( AdapterAddressList >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)this[9].Data4 + 104LL))(*(_QWORD *)this[9].Data4, v15);
          v15 = (HSTRING)pv;
        }
        v14 = (__int64 *)*v14;
        WindowsDeleteString(v15);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    }
    else
    {
LABEL_48:
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
0x180041e58  mov     [rsp+arg_8], rbx
0x180041e5d  mov     [rsp+arg_10], rsi
0x180041e62  push    rdi
0x180041e63  push    r12
0x180041e65  push    r13
0x180041e67  push    r14
0x180041e69  push    r15
0x180041e6b  sub     rsp, 0E0h
0x180041e72  mov     rax, cs:__security_cookie
0x180041e79  xor     rax, rsp
0x180041e7c  mov     [rsp+108h+var_38], rax
0x180041e84  mov     r13, rcx
0x180041e87  lea     rax, WPP_GLOBAL_Control
0x180041e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e95  cmp     rcx, rax
0x180041e98  jz      short loc_180041EB5
0x180041e9a  test    byte ptr [rcx+1Ch], 40h
0x180041e9e  jz      short loc_180041EB5
0x180041ea0  mov     edx, 13h
0x180041ea5  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041eac  mov     rcx, [rcx+10h]
0x180041eb0  call    WPP_SF_
0x180041eb5  lea     r14, [r13+20h]
0x180041eb9  mov     esi, 27h ; '''
0x180041ebe  mov     r8d, esi; cchMax
0x180041ec1  lea     rdx, [rsp+108h+sz]; lpsz
0x180041ec9  mov     rcx, r14; rguid
0x180041ecc  call    cs:__imp_StringFromGUID2
0x180041ed2  xor     r12d, r12d
0x180041ed5  test    eax, eax
0x180041ed7  jz      short loc_180041F06
0x180041ed9  mov     [rsp+108h+pv], r12
0x180041ede  mov     [rsp+108h+var_E8], 26h ; '&'
0x180041ee7  lea     r9, [rsp+108h+sz]
0x180041eef  mov     r8d, esi
0x180041ef2  lea     rdx, [rsp+108h+Str1]
0x180041ef7  lea     rcx, [rsp+108h+pv]
0x180041efc  call    cs:__imp__o_wcstombs_s
0x180041f02  test    eax, eax
0x180041f04  jz      short loc_180041F23
0x180041f06  call    cs:__imp_GetLastError
0x180041f0c  test    eax, eax
0x180041f0e  mov     edi, eax
0x180041f10  jle     short loc_180041F1B
0x180041f12  movzx   edi, ax
0x180041f15  or      edi, 80070000h
0x180041f1b  test    edi, edi
0x180041f1d  js      loc_18004217C
0x180041f23  mov     [rsp+108h+pv], r12
0x180041f28  lea     rdx, [rsp+108h+pv]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180041f2d  call    ?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)
0x180041f32  mov     edi, eax
0x180041f34  mov     r15, [rsp+108h+pv]
0x180041f39  test    eax, eax
0x180041f3b  js      loc_18004216E
0x180041f41  test    r15, r15
0x180041f44  jz      loc_18004216E
0x180041f4a  mov     rbx, r15
0x180041f4d  mov     r8d, esi; MaxCount
0x180041f50  mov     rdx, [rbx+10h]; Str2
0x180041f54  lea     rcx, [rsp+108h+Str1]; Str1
0x180041f59  call    strncmp_0
0x180041f5e  test    eax, eax
0x180041f60  jz      short loc_180041FB0
0x180041f62  mov     rbx, [rbx+8]
0x180041f66  test    rbx, rbx
0x180041f69  jnz     short loc_180041F4D
0x180041f6b  mov     rbx, r15
0x180041f6e  test    r15, r15
0x180041f71  jz      loc_18004216E
0x180041f77  cmp     [rbx+18h], r12
0x180041f7b  jz      short loc_180041F9E
0x180041f7d  mov     [rsp+108h+var_D8], r12b
0x180041f82  lea     r9, [rsp+108h+var_D8]; bool *
0x180041f87  mov     r8, [rbx+10h]; char *
0x180041f8b  mov     rdx, r14; struct _GUID *
0x180041f8e  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)
0x180041f93  test    eax, eax
0x180041f95  js      short loc_180041F9E
0x180041f97  cmp     [rsp+108h+var_D8], r12b
0x180041f9c  jnz     short loc_180041FA7
0x180041f9e  mov     rbx, [rbx+8]
0x180041fa2  test    rbx, rbx
0x180041fa5  jnz     short loc_180041F77
0x180041fa7  test    rbx, rbx
0x180041faa  jz      loc_18004216E
0x180041fb0  mov     rsi, [rbx+18h]
0x180041fb4  test    rsi, rsi
0x180041fb7  jz      short loc_180041FCA
0x180041fb9  mov     rdx, rsi; struct _IP_ADAPTER_UNICAST_ADDRESS_LH *
0x180041fbc  mov     rcx, r13; this
0x180041fbf  call    ?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)
0x180041fc4  mov     rsi, [rsi+8]
0x180041fc8  jmp     short loc_180041FB4
0x180041fca  mov     rdx, [rbx+0D0h]; struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *
0x180041fd1  test    rdx, rdx
0x180041fd4  jz      short loc_180041FDE
0x180041fd6  mov     rcx, r13; this
0x180041fd9  call    ?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)
0x180041fde  mov     [rsp+108h+var_C8], r12d
0x180041fe3  mov     esi, 4
0x180041fe8  mov     r8d, esi
0x180041feb  mov     rdx, r14
0x180041fee  lea     rcx, [rsp+108h+var_B8]
0x180041ff3  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180041ff8  nop
0x180041ff9  mov     rcx, [rsp+108h+var_B8]
0x180041ffe  test    rcx, rcx
0x180042001  jz      short loc_180042014
0x180042003  mov     rax, [rcx]
0x180042006  lea     rdx, [rsp+108h+var_C8]
0x18004200b  mov     rax, [rax+38h]
0x18004200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042014  cmp     [rsp+108h+var_C8], r12d
0x180042019  jnz     short loc_180042042
0x18004201b  mov     r8d, esi
0x18004201e  mov     rdx, r14
0x180042021  lea     rcx, [rsp+108h+pv]
0x180042026  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x18004202b  mov     rdx, rax
0x18004202e  lea     rcx, [rsp+108h+var_B8]
0x180042033  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x180042038  lea     rcx, [rsp+108h+pv]
0x18004203d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042042  mov     esi, 6
0x180042047  mov     r8d, esi
0x18004204a  mov     rdx, r14
0x18004204d  lea     rcx, [rsp+108h+var_C0]
0x180042052  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180042057  nop
0x180042058  mov     rcx, [rsp+108h+var_C0]
0x18004205d  test    rcx, rcx
0x180042060  jz      short loc_180042073
0x180042062  mov     rax, [rcx]
0x180042065  lea     rdx, [rsp+108h+var_C8]
0x18004206a  mov     rax, [rax+38h]
0x18004206e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042073  cmp     [rsp+108h+var_C8], r12d
0x180042078  jnz     short loc_1800420A1
0x18004207a  mov     r8d, esi
0x18004207d  mov     rdx, r14
0x180042080  lea     rcx, [rsp+108h+pv]
0x180042085  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x18004208a  mov     rdx, rax
0x18004208d  lea     rcx, [rsp+108h+var_C0]
0x180042092  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x180042097  lea     rcx, [rsp+108h+pv]
0x18004209c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800420a1  mov     rsi, [rbx+30h]
0x1800420a5  jmp     short loc_1800420C6
0x1800420a7  mov     rdx, [rsi+10h]
0x1800420ab  test    rdx, rdx
0x1800420ae  jz      short loc_1800420C2
0x1800420b0  mov     r9, [rsp+108h+var_C0]
0x1800420b5  mov     r8, [rsp+108h+var_B8]
0x1800420ba  mov     rcx, r13
0x1800420bd  call    ?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x1800420c2  mov     rsi, [rsi+8]
0x1800420c6  test    rsi, rsi
0x1800420c9  jnz     short loc_1800420A7
0x1800420cb  lea     rdx, [rbx+38h]
0x1800420cf  lea     rcx, [r13+50h]; this
0x1800420d3  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800420d8  mov     rsi, [rbx+1B8h]
0x1800420df  test    rsi, rsi
0x1800420e2  jz      short loc_180042157
0x1800420e4  mov     rbx, r12
0x1800420e7  mov     [rsp+108h+pv], rbx
0x1800420ec  mov     [rsp+108h+var_C4], r12d
0x1800420f1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800420f5  inc     rcx; unsigned __int64
0x1800420f8  cmp     [rsi+rcx*2+8], r12w
0x1800420fe  jnz     short loc_1800420F5
0x180042100  lea     rdx, [rsp+108h+var_C4]; unsigned int *
0x180042105  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004210a  mov     edi, eax
0x18004210c  test    eax, eax
0x18004210e  js      short loc_18004212A
0x180042110  mov     r8d, [rsp+108h+var_C4]; unsigned int
0x180042115  lea     rdx, [rsi+8]; unsigned __int16 *
0x180042119  lea     rcx, [rsp+108h+pv]; this
0x18004211e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180042123  mov     edi, eax
0x180042125  mov     rbx, [rsp+108h+pv]
0x18004212a  test    edi, edi
0x18004212c  js      short loc_180042149
0x18004212e  mov     rcx, [r13+98h]
0x180042135  mov     rax, [rcx]
0x180042138  mov     rdx, rbx
0x18004213b  mov     rax, [rax+68h]
0x18004213f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042144  mov     rbx, [rsp+108h+pv]
0x180042149  mov     rsi, [rsi]
0x18004214c  mov     rcx, rbx; string
0x18004214f  call    cs:__imp_WindowsDeleteString
0x180042155  jmp     short loc_1800420DF
0x180042157  lea     rcx, [rsp+108h+var_C0]
0x18004215c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042161  nop
0x180042162  lea     rcx, [rsp+108h+var_B8]
0x180042167  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004216c  jmp     short loc_180042173
0x18004216e  mov     edi, 80070002h
0x180042173  mov     rcx, r15; pv
0x180042176  call    cs:__imp_CoTaskMemFree
0x18004217c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042183  lea     rax, WPP_GLOBAL_Control
0x18004218a  cmp     rcx, rax
0x18004218d  jz      short loc_1800421AD
0x18004218f  test    byte ptr [rcx+1Ch], 40h
0x180042193  jz      short loc_1800421AD
0x180042195  mov     edx, 14h
0x18004219a  mov     r9d, edi
0x18004219d  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800421a4  mov     rcx, [rcx+10h]
0x1800421a8  call    WPP_SF_d
0x1800421ad  mov     eax, edi
0x1800421af  jmp     short loc_1800421B5
0x1800421b1  mov     eax, [rsp+108h+var_C4]
0x1800421b5  mov     rcx, [rsp+108h+var_38]
0x1800421bd  xor     rcx, rsp; StackCookie
0x1800421c0  call    __security_check_cookie
0x1800421c5  lea     r11, [rsp+108h+var_28]
0x1800421cd  mov     rbx, [r11+38h]
0x1800421d1  mov     rsi, [r11+40h]
0x1800421d5  mov     rsp, r11
0x1800421d8  pop     r15
0x1800421da  pop     r14
0x1800421dc  pop     r13
0x1800421de  pop     r12
0x1800421e0  pop     rdi
0x1800421e1  retn
```
