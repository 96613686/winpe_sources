# Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWlanInfo(_WLAN_CONNECTION_ATTRIBUTES *,Windows::Networking::UX::Internal::WlanClient *)

- ea: `0x180056744`
- end: `0x180056b93`
- name: `?GetWlanInfo@CWiFiAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAU_WLAN_CONNECTION_ATTRIBUTES@@PEAVWlanClient@2345@@Z`
- size: `1103`
- prototype: `int(Windows::Networking::UX::Internal::CWiFiAdapterProperties *__hidden this, struct _WLAN_CONNECTION_ATTRIBUTES *, struct Windows::Networking::UX::Internal::WlanClient *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056f00`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x1800147e4`
- `0x1800149dc`
- `0x180015b50`
- `0x18001668c`
- `0x1800167cc`
- `0x18001b230`
- `0x18001d4d4`
- `0x18001d6d0`
- `0x180040cb8`
- `0x180056014`
- `0x18005670c`
- `0x180056744`
- `0x180056bc0`
- `0x18007b354`
- `0x18008e010`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056947`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056a23`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056aef`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056947`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056a23`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180056aef`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18005684b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18005684b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWlanInfo(
        Windows::Networking::UX::Internal::CWiFiAdapterProperties *this,
        struct _WLAN_CONNECTION_ATTRIBUTES *a2,
        struct Windows::Networking::UX::Internal::WlanClient *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  int v15; // eax
  _DWORD *v16; // rbx
  int ConnectionInfo; // eax
  int BssEntry; // eax
  int v19; // edi
  unsigned int i; // edi
  int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, char *); // rdi
  int WifiBandFromBandId; // [rsp+20h] [rbp-E0h] BYREF
  int v28; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  PVOID pMemory; // [rsp+48h] [rbp-B8h] BYREF
  struct _WLAN_BSS_ENTRY v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[512]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_578e1a1036ab3313316334a71405751e_Traceguids);
  v31 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31, a2, a3);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Collections::IKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int>,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Collections::IKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int> *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Collections::IKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int> *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Collections::IKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int> *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Collections::IKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int> *>>>(
         v6,
         &v31);
  v10 = v7;
  if ( v7 < 0 )
  {
    v11 = 217;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
      (const char *)(unsigned int)v7,
      WifiBandFromBandId);
    goto LABEL_52;
  }
  if ( a2 && a2->isState == wlan_interface_state_connected )
  {
    if ( a2->wlanAssociationAttributes.dot11Ssid.uSSIDLength )
    {
      v32 = 256;
      v14 = WlanUtf8SsidToDisplayName(&a2->wlanAssociationAttributes, 1, v35, &v32);
      if ( v14 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xE6,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
                (const char *)v14,
                WifiBandFromBandId);
        goto LABEL_52;
      }
      v7 = Microsoft::WRL::Wrappers::HString::Set<65>((char *)this + 56, v35);
      v10 = v7;
      if ( v7 < 0 )
      {
        v11 = 232;
        goto LABEL_11;
      }
    }
    else
    {
      v7 = Microsoft::WRL::Wrappers::HString::Set<65>((char *)this + 56, a2->strProfileName);
      v10 = v7;
      if ( v7 < 0 )
      {
        v11 = 223;
        goto LABEL_11;
      }
    }
    *((_DWORD *)this + 18) = Windows::Networking::UX::Internal::WlanClient::SecurityTypeFromAuthAlgo((unsigned int)a2->wlanSecurityAttributes.dot11AuthAlgorithm);
    v15 = Windows::Networking::UX::Internal::WlanClient::ProtocolTypeFromPhyType(
            a3,
            (unsigned int)a2->wlanAssociationAttributes.dot11PhyType,
            (char *)this + 40);
    *((_DWORD *)this + 19) = v15;
    v16 = 0;
    pMemory = 0;
    if ( v15 == 12 )
    {
      ConnectionInfo = Windows::Networking::UX::Internal::WlanClient::GetConnectionInfo(a3, (char *)this + 40, &pMemory);
      if ( ConnectionInfo >= 0 )
      {
        v16 = pMemory;
        if ( pMemory )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v16[26] )
              goto LABEL_44;
            if ( !v16[12 * i + 33] )
            {
              WifiBandFromBandId = Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWifiBandFromBandId((unsigned int)v16[12 * i + 34]);
              v29 = 0;
              Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v29);
              v28 = v16[12 * i + 35];
              v21 = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0>::Make(
                      &WifiBandFromBandId,
                      &v28,
                      &v29);
              if ( v21 < 0 )
              {
                v22 = 248;
                goto LABEL_34;
              }
              v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 104LL))(v31, v29);
              if ( v21 < 0 )
              {
                v22 = 249;
LABEL_34:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v22,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
                  (const char *)(unsigned int)v21,
                  WifiBandFromBandId);
                Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v29);
                if ( v16 )
                  WlanFreeMemory(v16);
                v10 = v21;
                goto LABEL_52;
              }
              Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v29);
            }
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEF,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
          (const char *)(unsigned int)ConnectionInfo,
          WifiBandFromBandId);
        v16 = pMemory;
      }
    }
    memset_0(&v34, 0, sizeof(v34));
    BssEntry = Windows::Networking::UX::Internal::WlanClient::GetBssEntry(
                 a3,
                 (const struct _GUID *)((char *)this + 40),
                 (unsigned __int8 (*)[6])a2->wlanAssociationAttributes.dot11Bssid,
                 &v34);
    v19 = BssEntry;
    if ( BssEntry < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
        (const char *)(unsigned int)BssEntry,
        WifiBandFromBandId);
LABEL_21:
      if ( v16 )
        WlanFreeMemory(v16);
      v10 = v19;
      goto LABEL_52;
    }
    WifiBandFromBandId = 0;
    v28 = 0;
    if ( !(unsigned int)ConvertFrequencyToBandChannel(v34.ulChCenterFrequency, &WifiBandFromBandId, &v28) )
    {
      WifiBandFromBandId = Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWifiBandFromBandId((unsigned int)WifiBandFromBandId);
      v30 = 0;
      Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v30);
      v19 = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<enum Windows::Networking::UX::WiFiBand,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0>::Make(
              &WifiBandFromBandId,
              &v28,
              &v30);
      if ( v19 < 0 )
      {
        v23 = 266;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiadapterproperties.cpp",
          (const char *)(unsigned int)v19,
          WifiBandFromBandId);
        Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v30);
        goto LABEL_21;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 104LL))(v31, v30);
      if ( v19 < 0 )
      {
        v23 = 267;
        goto LABEL_40;
      }
      Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(&v30);
    }
LABEL_44:
    if ( v16 )
      WlanFreeMemory(v16);
  }
  v24 = v31;
  v25 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 88,
    v8,
    v9);
  v7 = v25(v24, (char *)this + 88);
  v10 = v7;
  if ( v7 < 0 )
  {
    v11 = 272;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_578e1a1036ab3313316334a71405751e_Traceguids, 0);
  v10 = 0;
LABEL_52:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31, v12, v13);
  return v10;
}

```

## disassembly

```asm
0x180056744  mov     [rsp-8+arg_18], rbx
0x180056749  push    rbp
0x18005674a  push    rsi
0x18005674b  push    rdi
0x18005674c  push    r12
0x18005674e  push    r13
0x180056750  push    r14
0x180056752  push    r15
0x180056754  lea     rbp, [rsp-2D0h]
0x18005675c  sub     rsp, 3D0h
0x180056763  mov     rax, cs:__security_cookie
0x18005676a  xor     rax, rsp
0x18005676d  mov     [rbp+300h+var_40], rax
0x180056774  mov     r12, r8
0x180056777  mov     rdi, rdx
0x18005677a  mov     r13, rcx
0x18005677d  lea     rax, WPP_GLOBAL_Control
0x180056784  mov     rcx, cs:WPP_GLOBAL_Control
0x18005678b  cmp     rcx, rax
0x18005678e  jz      short loc_1800567AB
0x180056790  test    byte ptr [rcx+1Ch], 8
0x180056794  jz      short loc_1800567AB
0x180056796  mov     edx, 10h
0x18005679b  lea     r8, WPP_578e1a1036ab3313316334a71405751e_Traceguids
0x1800567a2  mov     rcx, [rcx+10h]
0x1800567a6  call    WPP_SF_
0x1800567ab  xor     r15d, r15d
0x1800567ae  mov     [rsp+400h+var_3C8], r15
0x1800567b3  lea     rcx, [rsp+400h+var_3C8]
0x1800567b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800567bd  lea     rdx, [rsp+400h+var_3C8]
0x1800567c2  call    ??$CreateExternalObjectVector@U?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@V?$Vector@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@Internal@234@U?$DefaultLifetimeTraits@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@6234@U?$DefaultVectorOptions@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@6234@@Internal@234@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@Internal@234@U?$DefaultLifetimeTraits@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@6234@U?$DefaultVectorOptions@PEAU?$IKeyValuePair@W4WiFiBand@UX@Networking@Windows@@I@Collections@Foundation@Windows@@@6234@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint>,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Collections::IKeyValuePair<Windows::Networking::UX::WiFiBand,uint> *>> * *)
0x1800567c7  mov     ebx, eax
0x1800567c9  test    eax, eax
0x1800567cb  jns     short loc_1800567DB
0x1800567cd  lea     r8, aOnecoreuapNetU_16; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800567d4  mov     edx, 0D9h
0x1800567d9  jmp     short loc_18005681B
0x1800567db  lea     r14, aOnecoreuapNetU_16; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800567e2  test    rdi, rdi
0x1800567e5  jz      loc_180056AF5
0x1800567eb  cmp     dword ptr [rdi], 1
0x1800567ee  jnz     loc_180056AF5
0x1800567f4  lea     rsi, [rdi+208h]
0x1800567fb  cmp     [rsi], r15d
0x1800567fe  jnz     short loc_18005682F
0x180056800  lea     rdx, [rdi+8]
0x180056804  lea     rcx, [r13+38h]
0x180056808  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x18005680d  mov     ebx, eax
0x18005680f  test    eax, eax
0x180056811  jns     short loc_180056890
0x180056813  mov     edx, 0DFh; void *
0x180056818  mov     r8, r14; unsigned int
0x18005681b  mov     r9d, eax; char *
0x18005681e  mov     rcx, [rbp+308h]; this
0x180056825  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005682a  jmp     loc_180056B5D
0x18005682f  mov     [rsp+400h+var_3C0], 100h
0x180056837  lea     r9, [rsp+400h+var_3C0]
0x18005683c  lea     r8, [rbp+300h+var_240]
0x180056843  mov     edx, 1
0x180056848  mov     rcx, rsi
0x18005684b  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180056851  test    eax, eax
0x180056853  jz      short loc_180056873
0x180056855  mov     rcx, [rbp+308h]; this
0x18005685c  mov     r9d, eax; char *
0x18005685f  mov     r8, r14; unsigned int
0x180056862  mov     edx, 0E6h; void *
0x180056867  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005686c  mov     ebx, eax
0x18005686e  jmp     loc_180056B5D
0x180056873  lea     rcx, [r13+38h]
0x180056877  lea     rdx, [rbp+300h+var_240]
0x18005687e  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180056883  mov     ebx, eax
0x180056885  test    eax, eax
0x180056887  jns     short loc_180056890
0x180056889  mov     edx, 0E8h
0x18005688e  jmp     short loc_180056818
0x180056890  mov     ecx, [rdi+254h]
0x180056896  call    ?SecurityTypeFromAuthAlgo@WlanClient@Internal@UX@Networking@Windows@@SA?AW4WiFiSecurityType@345@W4_DOT11_AUTH_ALGORITHM@@@Z; Windows::Networking::UX::Internal::WlanClient::SecurityTypeFromAuthAlgo(_DOT11_AUTH_ALGORITHM)
0x18005689b  mov     [r13+48h], eax
0x18005689f  lea     r15, [r13+28h]
0x1800568a3  mov     r8, r15
0x1800568a6  mov     edx, [rdi+238h]
0x1800568ac  mov     rcx, r12
0x1800568af  call    ?ProtocolTypeFromPhyType@WlanClient@Internal@UX@Networking@Windows@@QEAA?AW4WiFiProtocolType@345@W4_DOT11_PHY_TYPE@@AEBU_GUID@@@Z; Windows::Networking::UX::Internal::WlanClient::ProtocolTypeFromPhyType(_DOT11_PHY_TYPE,_GUID const &)
0x1800568b4  mov     [r13+4Ch], eax
0x1800568b8  xor     ebx, ebx
0x1800568ba  mov     [rsp+400h+pMemory], rbx
0x1800568bf  cmp     eax, 0Ch
0x1800568c2  jnz     short loc_1800568F4
0x1800568c4  lea     r8, [rsp+400h+pMemory]
0x1800568c9  mov     rdx, r15
0x1800568cc  mov     rcx, r12
0x1800568cf  call    ?GetConnectionInfo@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@AEAV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::WlanClient::GetConnectionInfo(_GUID const &,wistd::unique_ptr<DOT11_CONNECTION_INFO,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>> &)
0x1800568d4  mov     rcx, [rbp+308h]; this
0x1800568db  test    eax, eax
0x1800568dd  jns     short loc_180056954
0x1800568df  mov     r9d, eax; char *
0x1800568e2  mov     r8, r14; unsigned int
0x1800568e5  mov     edx, 0EFh; void *
0x1800568ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800568ef  mov     rbx, [rsp+400h+pMemory]
0x1800568f4  xor     edx, edx; Val
0x1800568f6  mov     r8d, 168h; Size
0x1800568fc  lea     rcx, [rsp+400h+var_3B0]; void *
0x180056901  call    memset_0
0x180056906  lea     r8, [rsi+28h]; unsigned __int8 (*)[6]
0x18005690a  lea     r9, [rsp+400h+var_3B0]; struct _WLAN_BSS_ENTRY *
0x18005690f  mov     rdx, r15; struct _GUID *
0x180056912  mov     rcx, r12; this
0x180056915  call    ?GetBssEntry@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAY05EPEAU_WLAN_BSS_ENTRY@@@Z; Windows::Networking::UX::Internal::WlanClient::GetBssEntry(_GUID const &,uchar (*)[6],_WLAN_BSS_ENTRY *)
0x18005691a  mov     edi, eax
0x18005691c  xor     r15d, r15d
0x18005691f  test    eax, eax
0x180056921  jns     loc_180056A30
0x180056927  mov     rcx, [rbp+308h]; this
0x18005692e  mov     r9d, eax; char *
0x180056931  mov     r8, r14; unsigned int
0x180056934  mov     edx, 101h; void *
0x180056939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005693e  nop
0x18005693f  test    rbx, rbx
0x180056942  jz      short loc_18005694D
0x180056944  mov     rcx, rbx; pMemory
0x180056947  call    cs:__imp_WlanFreeMemory
0x18005694d  mov     ebx, edi
0x18005694f  jmp     loc_180056B5D
0x180056954  mov     rbx, [rsp+400h+pMemory]
0x180056959  test    rbx, rbx
0x18005695c  jz      short loc_1800568F4
0x18005695e  xor     r15d, r15d
0x180056961  mov     edi, r15d
0x180056964  cmp     edi, [rbx+68h]
0x180056967  jnb     loc_180056AE7
0x18005696d  mov     eax, edi
0x18005696f  lea     rsi, [rax+rax*2]
0x180056973  add     rsi, rsi
0x180056976  cmp     [rbx+rsi*8+84h], r15d
0x18005697e  jnz     short loc_1800569EA
0x180056980  mov     ecx, [rbx+rsi*8+88h]
0x180056987  call    ?GetWifiBandFromBandId@CWiFiAdapterProperties@Internal@UX@Networking@Windows@@CA?AW4WiFiBand@345@W4_DOT11_BAND_ID@@@Z; Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWifiBandFromBandId(_DOT11_BAND_ID)
0x18005698c  mov     [rsp+400h+var_3E0], eax; int
0x180056990  mov     [rsp+400h+var_3D8], r15
0x180056995  lea     rcx, [rsp+400h+var_3D8]
0x18005699a  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x18005699f  mov     eax, [rbx+rsi*8+8Ch]
0x1800569a6  mov     [rsp+400h+var_3DC], eax
0x1800569aa  lea     r8, [rsp+400h+var_3D8]
0x1800569af  lea     rdx, [rsp+400h+var_3DC]
0x1800569b4  lea     rcx, [rsp+400h+var_3E0]
0x1800569b9  call    ?Make@?$SimpleKeyValuePair@W4WiFiBand@UX@Networking@Windows@@IU?$DefaultLifetimeTraits@W4WiFiBand@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@I@6784@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBW4WiFiBand@UX@Networking@5@AEBIPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<Windows::Networking::UX::WiFiBand,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0>::Make(Windows::Networking::UX::WiFiBand const &,uint const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<Windows::Networking::UX::WiFiBand,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0> * *)
0x1800569be  mov     esi, eax
0x1800569c0  test    eax, eax
0x1800569c2  js      short loc_1800569F8
0x1800569c4  mov     rcx, [rsp+400h+var_3C8]
0x1800569c9  mov     rax, [rcx]
0x1800569cc  mov     rdx, [rsp+400h+var_3D8]
0x1800569d1  mov     rax, [rax+68h]
0x1800569d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569da  mov     esi, eax
0x1800569dc  test    eax, eax
0x1800569de  js      short loc_1800569F1
0x1800569e0  lea     rcx, [rsp+400h+var_3D8]
0x1800569e5  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x1800569ea  inc     edi
0x1800569ec  jmp     loc_180056964
0x1800569f1  mov     edx, 0F9h
0x1800569f6  jmp     short loc_1800569FD
0x1800569f8  mov     edx, 0F8h; void *
0x1800569fd  mov     r8, r14; unsigned int
0x180056a00  mov     r9d, esi; char *
0x180056a03  mov     rcx, [rbp+308h]; this
0x180056a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056a0f  nop
0x180056a10  lea     rcx, [rsp+400h+var_3D8]
0x180056a15  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x180056a1a  nop
0x180056a1b  test    rbx, rbx
0x180056a1e  jz      short loc_180056A29
0x180056a20  mov     rcx, rbx; pMemory
0x180056a23  call    cs:__imp_WlanFreeMemory
0x180056a29  mov     ebx, esi
0x180056a2b  jmp     loc_180056B5D
0x180056a30  mov     [rsp+400h+var_3E0], r15d
0x180056a35  mov     [rsp+400h+var_3DC], r15d
0x180056a3a  lea     r8, [rsp+400h+var_3DC]
0x180056a3f  lea     rdx, [rsp+400h+var_3E0]
0x180056a44  mov     ecx, [rbp+300h+var_3B0.ulChCenterFrequency]
0x180056a47  call    ConvertFrequencyToBandChannel
0x180056a4c  test    eax, eax
0x180056a4e  jnz     loc_180056AE7
0x180056a54  mov     ecx, [rsp+400h+var_3E0]
0x180056a58  call    ?GetWifiBandFromBandId@CWiFiAdapterProperties@Internal@UX@Networking@Windows@@CA?AW4WiFiBand@345@W4_DOT11_BAND_ID@@@Z; Windows::Networking::UX::Internal::CWiFiAdapterProperties::GetWifiBandFromBandId(_DOT11_BAND_ID)
0x180056a5d  mov     [rsp+400h+var_3E0], eax; int
0x180056a61  mov     [rsp+400h+var_3D0], r15
0x180056a66  lea     rcx, [rsp+400h+var_3D0]
0x180056a6b  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x180056a70  mov     eax, [rsp+400h+var_3DC]
0x180056a74  mov     [rsp+400h+var_3DC], eax
0x180056a78  lea     r8, [rsp+400h+var_3D0]
0x180056a7d  lea     rdx, [rsp+400h+var_3DC]
0x180056a82  lea     rcx, [rsp+400h+var_3E0]
0x180056a87  call    ?Make@?$SimpleKeyValuePair@W4WiFiBand@UX@Networking@Windows@@IU?$DefaultLifetimeTraits@W4WiFiBand@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@I@6784@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBW4WiFiBand@UX@Networking@5@AEBIPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<Windows::Networking::UX::WiFiBand,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0>::Make(Windows::Networking::UX::WiFiBand const &,uint const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<Windows::Networking::UX::WiFiBand,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::WiFiBand>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0> * *)
0x180056a8c  mov     edi, eax
0x180056a8e  test    eax, eax
0x180056a90  jns     short loc_180056AB9
0x180056a92  mov     edx, 10Ah; void *
0x180056a97  mov     r8, r14; unsigned int
0x180056a9a  mov     r9d, edi; char *
0x180056a9d  mov     rcx, [rbp+308h]; this
0x180056aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056aa9  nop
0x180056aaa  lea     rcx, [rsp+400h+var_3D0]
0x180056aaf  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x180056ab4  jmp     loc_18005693F
0x180056ab9  mov     rcx, [rsp+400h+var_3C8]
0x180056abe  mov     rax, [rcx]
0x180056ac1  mov     rdx, [rsp+400h+var_3D0]
0x180056ac6  mov     rax, [rax+68h]
0x180056aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056acf  mov     edi, eax
0x180056ad1  test    eax, eax
0x180056ad3  jns     short loc_180056ADC
0x180056ad5  mov     edx, 10Bh
0x180056ada  jmp     short loc_180056A97
0x180056adc  lea     rcx, [rsp+400h+var_3D0]
0x180056ae1  call    ?InternalRelease@?$ComPtr@VHotspotAdditionalMetadataImpl@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::HotspotAdditionalMetadataImpl>::InternalRelease(void)
0x180056ae6  nop
0x180056ae7  test    rbx, rbx
0x180056aea  jz      short loc_180056AF5
0x180056aec  mov     rcx, rbx; pMemory
0x180056aef  call    cs:__imp_WlanFreeMemory
0x180056af5  mov     rsi, [rsp+400h+var_3C8]
0x180056afa  mov     rax, [rsi]
0x180056afd  mov     rdi, [rax+40h]
0x180056b01  lea     rcx, [r13+58h]
0x180056b05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056b0a  lea     rdx, [r13+58h]
0x180056b0e  mov     rcx, rsi
0x180056b11  mov     rax, rdi
0x180056b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b19  mov     ebx, eax
0x180056b1b  test    eax, eax
0x180056b1d  jns     short loc_180056B29
0x180056b1f  mov     edx, 110h
0x180056b24  jmp     loc_180056818
0x180056b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b30  lea     rax, WPP_GLOBAL_Control
0x180056b37  cmp     rcx, rax
0x180056b3a  jz      short loc_180056B5A
0x180056b3c  test    byte ptr [rcx+1Ch], 8
0x180056b40  jz      short loc_180056B5A
0x180056b42  mov     edx, 11h
0x180056b47  xor     r9d, r9d
0x180056b4a  lea     r8, WPP_578e1a1036ab3313316334a71405751e_Traceguids
0x180056b51  mov     rcx, [rcx+10h]
0x180056b55  call    WPP_SF_d
0x180056b5a  mov     ebx, r15d
0x180056b5d  lea     rcx, [rsp+400h+var_3C8]
0x180056b62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056b67  mov     eax, ebx
0x180056b69  mov     rcx, [rbp+300h+var_40]
0x180056b70  xor     rcx, rsp; StackCookie
0x180056b73  call    __security_check_cookie
0x180056b78  mov     rbx, [rsp+400h+arg_18]
0x180056b80  add     rsp, 3D0h
0x180056b87  pop     r15
0x180056b89  pop     r14
0x180056b8b  pop     r13
0x180056b8d  pop     r12
0x180056b8f  pop     rdi
0x180056b90  pop     rsi
0x180056b91  pop     rbp
0x180056b92  retn
```
