# Windows::Networking::UX::Internal::CAdapterProperties::GetIpInfo(void)

- ea: `0x180003108`
- end: `0x1800034cd`
- name: `?GetIpInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `965`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000217c`

## callees

- `0x180002150`
- `0x1800023d0`
- `0x180003108`
- `0x180003b70`
- `0x18000414c`
- `0x180004600`
- `0x180005be0`
- `0x180005c80`
- `0x180005fc0`
- `0x18001664c`
- `0x18001e708`
- `0x18002cd20`
- `0x18005359c`
- `0x1800536fc`
- `0x1800546b4`
- `0x180055e24`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x1800031ac`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x1800031ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031b6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000317c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000317c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003439`

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
  _QWORD *ProfileDnsServerView; // rax
  _QWORD *v11; // rax
  __int64 j; // rsi
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rsi
  unsigned __int64 v15; // rcx
  unsigned int v16; // r8d
  const unsigned __int16 *v17; // rdx
  __int64 *v18; // rsi
  HSTRING v19; // rbx
  unsigned __int64 v20; // rcx
  bool v22; // [rsp+30h] [rbp-D8h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-D4h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  int v25; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h] BYREF
  char Str1[40]; // [rsp+58h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  if ( StringFromGUID2(this + 2, sz, 39) )
  {
    pv = 0;
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
      do
      {
        if ( !strncmp_0(Str1, *((const char **)v6 + 2), 0x27u) )
          goto LABEL_20;
        v6 = (LPVOID)*((_QWORD *)v6 + 1);
      }
      while ( v6 );
      v6 = v5;
      if ( v5 )
      {
        do
        {
          if ( *((_QWORD *)v6 + 3) )
          {
            v22 = 0;
            if ( Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
                   v7,
                   this + 2,
                   *((char **)v6 + 2),
                   &v22) >= 0
              && v22 )
            {
              break;
            }
          }
          v6 = (LPVOID)*((_QWORD *)v6 + 1);
        }
        while ( v6 );
        if ( v6 )
        {
LABEL_20:
          for ( i = (struct _IP_ADAPTER_UNICAST_ADDRESS_LH *)*((_QWORD *)v6 + 3); i; i = i->Next )
            Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(
              (Windows::Networking::UX::Internal::CAdapterProperties *)this,
              i);
          v9 = (struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *)*((_QWORD *)v6 + 26);
          if ( v9 )
            Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(
              (Windows::Networking::UX::Internal::CAdapterProperties *)this,
              v9);
          v25 = 0;
          TryGetInterfaceDnsServerView(&v27, this + 2, 4);
          if ( v27 )
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 56LL))(v27, &v25);
          if ( !v25 )
          {
            ProfileDnsServerView = TryGetProfileDnsServerView(&pv, this + 2, 4);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
              &v27,
              ProfileDnsServerView);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
          }
          TryGetInterfaceDnsServerView(&v26, this + 2, 6);
          if ( v26 )
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v25);
          if ( !v25 )
          {
            v11 = TryGetProfileDnsServerView(&pv, this + 2, 6);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(
              &v26,
              v11);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
          }
          for ( j = *((_QWORD *)v6 + 6); j; j = *(_QWORD *)(j + 8) )
          {
            v13 = *(_QWORD *)(j + 16);
            if ( v13 )
              Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress((__int64)this, v13, v27, v26);
          }
          v14 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
          if ( v14 )
          {
            v23 = 0;
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
            if ( (int)ULongLongToUInt(v15, &v23) < 0 )
            {
LABEL_45:
              v18 = (__int64 *)*((_QWORD *)v6 + 55);
              while ( v18 )
              {
                v19 = 0;
                pv = 0;
                v23 = 0;
                v20 = -1;
                do
                  ++v20;
                while ( *((_WORD *)v18 + v20 + 4) );
                AdapterAddressList = ULongLongToUInt(v20, &v23);
                if ( AdapterAddressList >= 0 )
                {
                  AdapterAddressList = Microsoft::WRL::Wrappers::HString::Set(
                                         (Microsoft::WRL::Wrappers::HString *)&pv,
                                         (const unsigned __int16 *)v18 + 4,
                                         v23);
                  v19 = (HSTRING)pv;
                }
                if ( AdapterAddressList >= 0 )
                {
                  (*(void (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)this[9].Data4 + 104LL))(
                    *(_QWORD *)this[9].Data4,
                    v19);
                  v19 = (HSTRING)pv;
                }
                v18 = (__int64 *)*v18;
                WindowsDeleteString(v19);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              goto LABEL_56;
            }
            v16 = v23;
            v17 = v14;
          }
          else
          {
            v16 = 0;
            v17 = &sourceString;
          }
          Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&this[5], v17, v16);
          goto LABEL_45;
        }
      }
    }
    AdapterAddressList = -2147024894;
LABEL_56:
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
0x180003108  mov     [rsp+arg_8], rbx
0x18000310d  mov     [rsp+arg_10], rsi
0x180003112  push    rdi
0x180003113  push    r12
0x180003115  push    r13
0x180003117  push    r14
0x180003119  push    r15
0x18000311b  sub     rsp, 0E0h
0x180003122  mov     rax, cs:__security_cookie
0x180003129  xor     rax, rsp
0x18000312c  mov     [rsp+108h+var_38], rax
0x180003134  mov     r13, rcx
0x180003137  lea     rax, WPP_GLOBAL_Control
0x18000313e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003145  cmp     rcx, rax
0x180003148  jz      short loc_180003165
0x18000314a  test    byte ptr [rcx+1Ch], 40h
0x18000314e  jz      short loc_180003165
0x180003150  mov     edx, 13h
0x180003155  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18000315c  mov     rcx, [rcx+10h]
0x180003160  call    WPP_SF_
0x180003165  lea     r14, [r13+20h]
0x180003169  mov     esi, 27h ; '''
0x18000316e  mov     r8d, esi; cchMax
0x180003171  lea     rdx, [rsp+108h+sz]; lpsz
0x180003179  mov     rcx, r14; rguid
0x18000317c  call    cs:__imp_StringFromGUID2
0x180003182  xor     r12d, r12d
0x180003185  test    eax, eax
0x180003187  jz      short loc_1800031B6
0x180003189  mov     [rsp+108h+pv], r12
0x18000318e  mov     [rsp+108h+var_E8], 26h ; '&'
0x180003197  lea     r9, [rsp+108h+sz]
0x18000319f  mov     r8d, esi
0x1800031a2  lea     rdx, [rsp+108h+Str1]
0x1800031a7  lea     rcx, [rsp+108h+pv]
0x1800031ac  call    cs:__imp__o_wcstombs_s
0x1800031b2  test    eax, eax
0x1800031b4  jz      short loc_1800031D3
0x1800031b6  call    cs:__imp_GetLastError
0x1800031bc  test    eax, eax
0x1800031be  mov     edi, eax
0x1800031c0  jle     short loc_1800031CB
0x1800031c2  movzx   edi, ax
0x1800031c5  or      edi, 80070000h
0x1800031cb  test    edi, edi
0x1800031cd  js      loc_180003466
0x1800031d3  mov     [rsp+108h+pv], r12
0x1800031d8  lea     rdx, [rsp+108h+pv]; struct _IP_ADAPTER_ADDRESSES_LH **
0x1800031dd  call    ?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)
0x1800031e2  mov     edi, eax
0x1800031e4  mov     r15, [rsp+108h+pv]
0x1800031e9  test    eax, eax
0x1800031eb  js      loc_180003458
0x1800031f1  test    r15, r15
0x1800031f4  jz      loc_180003458
0x1800031fa  mov     rbx, r15
0x1800031fd  mov     r8d, esi; MaxCount
0x180003200  mov     rdx, [rbx+10h]; Str2
0x180003204  lea     rcx, [rsp+108h+Str1]; Str1
0x180003209  call    strncmp_0
0x18000320e  test    eax, eax
0x180003210  jz      short loc_180003260
0x180003212  mov     rbx, [rbx+8]
0x180003216  test    rbx, rbx
0x180003219  jnz     short loc_1800031FD
0x18000321b  mov     rbx, r15
0x18000321e  test    r15, r15
0x180003221  jz      loc_180003458
0x180003227  cmp     [rbx+18h], r12
0x18000322b  jz      short loc_18000324E
0x18000322d  mov     [rsp+108h+var_D8], r12b
0x180003232  lea     r9, [rsp+108h+var_D8]; bool *
0x180003237  mov     r8, [rbx+10h]; char *
0x18000323b  mov     rdx, r14; struct _GUID *
0x18000323e  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)
0x180003243  test    eax, eax
0x180003245  js      short loc_18000324E
0x180003247  cmp     [rsp+108h+var_D8], r12b
0x18000324c  jnz     short loc_180003257
0x18000324e  mov     rbx, [rbx+8]
0x180003252  test    rbx, rbx
0x180003255  jnz     short loc_180003227
0x180003257  test    rbx, rbx
0x18000325a  jz      loc_180003458
0x180003260  mov     rsi, [rbx+18h]
0x180003264  test    rsi, rsi
0x180003267  jz      short loc_18000327A
0x180003269  mov     rdx, rsi; struct _IP_ADAPTER_UNICAST_ADDRESS_LH *
0x18000326c  mov     rcx, r13; this
0x18000326f  call    ?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)
0x180003274  mov     rsi, [rsi+8]
0x180003278  jmp     short loc_180003264
0x18000327a  mov     rdx, [rbx+0D0h]; struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *
0x180003281  test    rdx, rdx
0x180003284  jz      short loc_18000328E
0x180003286  mov     rcx, r13; this
0x180003289  call    ?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)
0x18000328e  mov     [rsp+108h+var_C8], r12d
0x180003293  mov     esi, 4
0x180003298  mov     r8d, esi
0x18000329b  mov     rdx, r14
0x18000329e  lea     rcx, [rsp+108h+var_B8]
0x1800032a3  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x1800032a8  nop
0x1800032a9  mov     rcx, [rsp+108h+var_B8]
0x1800032ae  test    rcx, rcx
0x1800032b1  jz      short loc_1800032C4
0x1800032b3  mov     rax, [rcx]
0x1800032b6  lea     rdx, [rsp+108h+var_C8]
0x1800032bb  mov     rax, [rax+38h]
0x1800032bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c4  cmp     [rsp+108h+var_C8], r12d
0x1800032c9  jnz     short loc_1800032F2
0x1800032cb  mov     r8d, esi
0x1800032ce  mov     rdx, r14
0x1800032d1  lea     rcx, [rsp+108h+pv]
0x1800032d6  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x1800032db  mov     rdx, rax
0x1800032de  lea     rcx, [rsp+108h+var_B8]
0x1800032e3  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x1800032e8  lea     rcx, [rsp+108h+pv]
0x1800032ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032f2  mov     esi, 6
0x1800032f7  mov     r8d, esi
0x1800032fa  mov     rdx, r14
0x1800032fd  lea     rcx, [rsp+108h+var_C0]
0x180003302  call    ?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x180003307  nop
0x180003308  mov     rcx, [rsp+108h+var_C0]
0x18000330d  test    rcx, rcx
0x180003310  jz      short loc_180003323
0x180003312  mov     rax, [rcx]
0x180003315  lea     rdx, [rsp+108h+var_C8]
0x18000331a  mov     rax, [rax+38h]
0x18000331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003323  cmp     [rsp+108h+var_C8], r12d
0x180003328  jnz     short loc_180003351
0x18000332a  mov     r8d, esi
0x18000332d  mov     rdx, r14
0x180003330  lea     rcx, [rsp+108h+pv]
0x180003335  call    ?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z; TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)
0x18000333a  mov     rdx, rax
0x18000333d  lea     rcx, [rsp+108h+var_C0]
0x180003342  call    ??4?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer>> &&)
0x180003347  lea     rcx, [rsp+108h+pv]
0x18000334c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003351  mov     rsi, [rbx+30h]
0x180003355  jmp     short loc_180003376
0x180003357  mov     rdx, [rsi+10h]
0x18000335b  test    rdx, rdx
0x18000335e  jz      short loc_180003372
0x180003360  mov     r9, [rsp+108h+var_C0]
0x180003365  mov     r8, [rsp+108h+var_B8]
0x18000336a  mov     rcx, r13
0x18000336d  call    ?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180003372  mov     rsi, [rsi+8]
0x180003376  test    rsi, rsi
0x180003379  jnz     short loc_180003357
0x18000337b  mov     rsi, [rbx+38h]
0x18000337f  test    rsi, rsi
0x180003382  jz      short loc_1800033AF
0x180003384  mov     [rsp+108h+var_D4], r12d
0x180003389  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000338d  inc     rcx; unsigned __int64
0x180003390  cmp     [rsi+rcx*2], r12w
0x180003395  jnz     short loc_18000338D
0x180003397  lea     rdx, [rsp+108h+var_D4]; unsigned int *
0x18000339c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800033a1  test    eax, eax
0x1800033a3  js      short loc_1800033C2
0x1800033a5  mov     r8d, [rsp+108h+var_D4]
0x1800033aa  mov     rdx, rsi
0x1800033ad  jmp     short loc_1800033B9
0x1800033af  xor     r8d, r8d; unsigned int
0x1800033b2  lea     rdx, sourceString; unsigned __int16 *
0x1800033b9  lea     rcx, [r13+50h]; this
0x1800033bd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800033c2  mov     rsi, [rbx+1B8h]
0x1800033c9  test    rsi, rsi
0x1800033cc  jz      short loc_180003441
0x1800033ce  mov     rbx, r12
0x1800033d1  mov     [rsp+108h+pv], rbx
0x1800033d6  mov     [rsp+108h+var_D4], r12d
0x1800033db  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800033df  inc     rcx; unsigned __int64
0x1800033e2  cmp     [rsi+rcx*2+8], r12w
0x1800033e8  jnz     short loc_1800033DF
0x1800033ea  lea     rdx, [rsp+108h+var_D4]; unsigned int *
0x1800033ef  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800033f4  mov     edi, eax
0x1800033f6  test    eax, eax
0x1800033f8  js      short loc_180003414
0x1800033fa  mov     r8d, [rsp+108h+var_D4]; unsigned int
0x1800033ff  lea     rdx, [rsi+8]; unsigned __int16 *
0x180003403  lea     rcx, [rsp+108h+pv]; this
0x180003408  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18000340d  mov     edi, eax
0x18000340f  mov     rbx, [rsp+108h+pv]
0x180003414  test    edi, edi
0x180003416  js      short loc_180003433
0x180003418  mov     rcx, [r13+98h]
0x18000341f  mov     rax, [rcx]
0x180003422  mov     rdx, rbx
0x180003425  mov     rax, [rax+68h]
0x180003429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342e  mov     rbx, [rsp+108h+pv]
0x180003433  mov     rsi, [rsi]
0x180003436  mov     rcx, rbx; string
0x180003439  call    cs:__imp_WindowsDeleteString
0x18000343f  jmp     short loc_1800033C9
0x180003441  lea     rcx, [rsp+108h+var_C0]
0x180003446  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000344b  nop
0x18000344c  lea     rcx, [rsp+108h+var_B8]
0x180003451  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003456  jmp     short loc_18000345D
0x180003458  mov     edi, 80070002h
0x18000345d  mov     rcx, r15; pv
0x180003460  call    cs:__imp_CoTaskMemFree
0x180003466  mov     rcx, cs:WPP_GLOBAL_Control
0x18000346d  lea     rax, WPP_GLOBAL_Control
0x180003474  cmp     rcx, rax
0x180003477  jz      short loc_180003497
0x180003479  test    byte ptr [rcx+1Ch], 40h
0x18000347d  jz      short loc_180003497
0x18000347f  mov     edx, 14h
0x180003484  mov     r9d, edi
0x180003487  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18000348e  mov     rcx, [rcx+10h]
0x180003492  call    WPP_SF_d
0x180003497  mov     eax, edi
0x180003499  jmp     short loc_18000349F
0x18000349b  mov     eax, [rsp+108h+var_D4]
0x18000349f  mov     rcx, [rsp+108h+var_38]
0x1800034a7  xor     rcx, rsp; StackCookie
0x1800034aa  call    __security_check_cookie
0x1800034af  lea     r11, [rsp+108h+var_28]
0x1800034b7  mov     rbx, [r11+38h]
0x1800034bb  mov     rsi, [r11+40h]
0x1800034bf  mov     rsp, r11
0x1800034c2  pop     r15
0x1800034c4  pop     r14
0x1800034c6  pop     r13
0x1800034c8  pop     r12
0x1800034ca  pop     rdi
0x1800034cb  retn
```
