# Windows::Networking::UX::Internal::CWiFiProtocolUri::_IsNetworkVisible(Windows::Networking::UX::Internal::WlanMediaManager *,uchar *,Windows::Networking::UX::WiFiSecurityType *)

- ea: `0x180061870`
- end: `0x180061c83`
- name: `?_IsNetworkVisible@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAEPEAW4WiFiSecurityType@345@@Z`
- size: `1043`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this, struct Windows::Networking::UX::Internal::WlanMediaManager *, unsigned __int8 *, enum Windows::Networking::UX::WiFiSecurityType *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060cf0`

## callees

- `0x180003ed0`
- `0x18000623d`
- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x18001540c`
- `0x18001668c`
- `0x18001d4d4`
- `0x180022958`
- `0x1800359ac`
- `0x180061870`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061927`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180061935`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180061935`

## string_xrefs

- `0x1800618f0`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x18006194a`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x1800619a0`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x1800619f2`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x180061a86`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x180061b2c`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
int __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::_IsNetworkVisible(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this,
        struct Windows::Networking::UX::Internal::WlanMediaManager *a2,
        unsigned __int8 *a3,
        enum Windows::Networking::UX::WiFiSecurityType *a4)
{
  PCWSTR StringRawBuffer; // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int AvailableNetworkList; // eax
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int i; // r14d
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // eax
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  int v46; // r10d
  __int64 v47; // rdx
  __int64 v48; // r8
  int v49; // r10d
  int v50; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+38h] [rbp-B0h] BYREF
  __int128 v54; // [rsp+40h] [rbp-A8h] BYREF
  _OWORD Buf2[2]; // [rsp+50h] [rbp-98h] BYREF
  int v56; // [rsp+70h] [rbp-78h]
  _OWORD Buf1[2]; // [rsp+78h] [rbp-70h] BYREF
  int v58; // [rsp+98h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_798799ef23c633adda075654372160e0_Traceguids);
  *a3 = 0;
  *(_DWORD *)a4 = 0;
  if ( *((_QWORD *)this + 8) )
  {
    memset(Buf1, 0, sizeof(Buf1));
    v58 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
    v10 = WlanStringToUtf8Ssid(StringRawBuffer, Buf1);
    if ( v10 )
    {
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1CF,
               (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
               (const char *)v10,
               v50);
    }
    else
    {
      v52 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52, v11, v12);
      v54 = *(_OWORD *)((char *)this + 72);
      AvailableNetworkList = Windows::Networking::UX::Internal::WlanMediaManager::Category_get_AvailableNetworkList(
                               a2,
                               &v54,
                               &v52);
      v14 = AvailableNetworkList;
      if ( AvailableNetworkList >= 0 )
      {
        v50 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 56LL))(v52, &v50);
        v20 = v17;
        if ( v17 >= 0 )
        {
          for ( i = 0; i < v50; ++i )
          {
            v53 = 0;
            v24 = v52;
            v25 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v53,
              v18,
              v19);
            if ( v25(v24, i, &v53) >= 0 )
            {
              v51 = 0;
              v28 = Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                      &v53,
                      &v51);
              v29 = v28;
              if ( v28 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1DD,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
                  (const char *)(unsigned int)v28,
                  v50);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v51,
                  v30,
                  v31);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v53,
                  v32,
                  v33);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v52,
                  v34,
                  v35);
                return v29;
              }
              *(_QWORD *)&v54 = 0;
              LODWORD(v54) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 88LL))(v51);
              DWORD1(v54) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 96LL))(v51);
              memset(Buf2, 0, sizeof(Buf2));
              v56 = 0;
              v36 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v51 + 80LL))(v51, Buf2);
              v39 = v36;
              if ( v36 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1E4,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
                  (const char *)(unsigned int)v36,
                  v50);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v51,
                  v40,
                  v41);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v53,
                  v42,
                  v43);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v52,
                  v44,
                  v45);
                return v39;
              }
              if ( LODWORD(Buf1[0]) == LODWORD(Buf2[0])
                && !memcmp_0((char *)Buf1 + 4, (char *)Buf2 + 4, LODWORD(Buf1[0])) )
              {
                if ( (unsigned __int8)Windows::Networking::UX::Internal::WlanClient::IsSecurityTypeSameAuthCipherPair(
                                        *((unsigned int *)this + 35),
                                        &v54) )
                {
                  *a3 = 1;
                  *(_DWORD *)a4 = *((_DWORD *)this + 35);
LABEL_23:
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                    &v51,
                    v37,
                    v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                    &v53,
                    v47,
                    v48);
                  break;
                }
                if ( v46 == 12
                  && *((_BYTE *)this + 147)
                  && (unsigned __int8)Windows::Networking::UX::Internal::WlanClient::IsSecurityTypeSameAuthCipherPair(
                                        4,
                                        &v54) )
                {
                  *a3 = 1;
                  *(_DWORD *)a4 = v49;
                  goto LABEL_23;
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v51,
                v37,
                v38);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v53,
              v26,
              v27);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_798799ef23c633adda075654372160e0_Traceguids, 0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v52,
            v18,
            v19);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D5,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
            (const char *)(unsigned int)v17,
            v50);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v52,
            v21,
            v22);
          return v20;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D2,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
          (const char *)(unsigned int)AvailableNetworkList,
          v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52, v15, v16);
        return v14;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
      (const char *)0x80004003LL,
      v50);
    return -2147467261;
  }
}

```

## disassembly

```asm
0x180061870  push    rbx
0x180061872  push    rsi
0x180061873  push    rdi
0x180061874  push    r12
0x180061876  push    r14
0x180061878  push    r15
0x18006187a  sub     rsp, 0B8h
0x180061881  mov     rax, cs:__security_cookie
0x180061888  xor     rax, rsp
0x18006188b  mov     [rsp+0E8h+var_48], rax
0x180061893  mov     r12, r9
0x180061896  mov     r15, r8
0x180061899  mov     rbx, rdx
0x18006189c  mov     rsi, rcx
0x18006189f  lea     rax, WPP_GLOBAL_Control
0x1800618a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618ad  cmp     rcx, rax
0x1800618b0  jz      short loc_1800618CD
0x1800618b2  test    byte ptr [rcx+1Ch], 40h
0x1800618b6  jz      short loc_1800618CD
0x1800618b8  mov     edx, 26h ; '&'
0x1800618bd  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x1800618c4  mov     rcx, [rcx+10h]
0x1800618c8  call    WPP_SF_
0x1800618cd  mov     byte ptr [r15], 0
0x1800618d1  mov     dword ptr [r12], 0
0x1800618d9  cmp     qword ptr [rsi+40h], 0
0x1800618de  jnz     short loc_180061908
0x1800618e0  mov     rcx, [rsp+0E8h]; this
0x1800618e8  mov     ebx, 80004003h
0x1800618ed  mov     r9d, ebx; char *
0x1800618f0  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800618f7  mov     edx, 1CDh; void *
0x1800618fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061901  mov     eax, ebx
0x180061903  jmp     loc_180061C10
0x180061908  xorps   xmm0, xmm0
0x18006190b  xor     eax, eax
0x18006190d  movups  [rsp+0E8h+Buf1], xmm0
0x180061912  movups  [rsp+0E8h+var_60], xmm0
0x18006191a  mov     [rsp+0E8h+var_50], eax
0x180061921  xor     edx, edx; length
0x180061923  mov     rcx, [rsi+78h]; string
0x180061927  call    cs:__imp_WindowsGetStringRawBuffer
0x18006192d  lea     rdx, [rsp+0E8h+Buf1]
0x180061932  mov     rcx, rax
0x180061935  call    cs:__imp_WlanStringToUtf8Ssid
0x18006193b  test    eax, eax
0x18006193d  jz      short loc_180061960
0x18006193f  mov     rcx, [rsp+0E8h]; this
0x180061947  mov     r9d, eax; char *
0x18006194a  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180061951  mov     edx, 1CFh; void *
0x180061956  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006195b  jmp     loc_180061C10
0x180061960  mov     [rsp+0E8h+var_B8], 0
0x180061969  lea     rcx, [rsp+0E8h+var_B8]
0x18006196e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061973  movups  xmm0, xmmword ptr [rsi+48h]
0x180061977  movdqu  [rsp+0E8h+var_A8], xmm0
0x18006197d  lea     r8, [rsp+0E8h+var_B8]
0x180061982  lea     rdx, [rsp+0E8h+var_A8]
0x180061987  mov     rcx, rbx
0x18006198a  call    ?Category_get_AvailableNetworkList@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@PEAPEAU?$IVector@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::WlanMediaManager::Category_get_AvailableNetworkList(_GUID,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IAvailableNetwork *> * *)
0x18006198f  mov     ebx, eax
0x180061991  test    eax, eax
0x180061993  jns     short loc_1800619C3
0x180061995  mov     rcx, [rsp+0E8h]; this
0x18006199d  mov     r9d, eax; char *
0x1800619a0  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800619a7  mov     edx, 1D2h; void *
0x1800619ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800619b1  nop
0x1800619b2  lea     rcx, [rsp+0E8h+var_B8]
0x1800619b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800619bc  mov     eax, ebx
0x1800619be  jmp     loc_180061C10
0x1800619c3  mov     [rsp+0E8h+var_C8], 0; int
0x1800619cb  mov     rcx, [rsp+0E8h+var_B8]
0x1800619d0  mov     rax, [rcx]
0x1800619d3  lea     rdx, [rsp+0E8h+var_C8]
0x1800619d8  mov     rax, [rax+38h]
0x1800619dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619e1  mov     ebx, eax
0x1800619e3  test    eax, eax
0x1800619e5  jns     short loc_180061A15
0x1800619e7  mov     rcx, [rsp+0E8h]; this
0x1800619ef  mov     r9d, eax; char *
0x1800619f2  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800619f9  mov     edx, 1D5h; void *
0x1800619fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061a03  nop
0x180061a04  lea     rcx, [rsp+0E8h+var_B8]
0x180061a09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061a0e  mov     eax, ebx
0x180061a10  jmp     loc_180061C10
0x180061a15  xor     r14d, r14d
0x180061a18  cmp     r14d, [rsp+0E8h+var_C8]
0x180061a1d  jnb     loc_180061BCC
0x180061a23  mov     [rsp+0E8h+var_B0], 0
0x180061a2c  mov     rdi, [rsp+0E8h+var_B8]
0x180061a31  mov     rax, [rdi]
0x180061a34  mov     rbx, [rax+30h]
0x180061a38  lea     rcx, [rsp+0E8h+var_B0]
0x180061a3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061a42  lea     r8, [rsp+0E8h+var_B0]
0x180061a47  mov     edx, r14d
0x180061a4a  mov     rcx, rdi
0x180061a4d  mov     rax, rbx
0x180061a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a55  test    eax, eax
0x180061a57  js      loc_180061C6F
0x180061a5d  mov     [rsp+0E8h+var_C0], 0
0x180061a66  lea     rdx, [rsp+0E8h+var_C0]
0x180061a6b  lea     rcx, [rsp+0E8h+var_B0]
0x180061a70  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x180061a75  mov     ebx, eax
0x180061a77  test    eax, eax
0x180061a79  jns     short loc_180061ABF
0x180061a7b  mov     rcx, [rsp+0E8h]; this
0x180061a83  mov     r9d, eax; char *
0x180061a86  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180061a8d  mov     edx, 1DDh; void *
0x180061a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061a97  nop
0x180061a98  lea     rcx, [rsp+0E8h+var_C0]
0x180061a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061aa2  nop
0x180061aa3  lea     rcx, [rsp+0E8h+var_B0]
0x180061aa8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061aad  nop
0x180061aae  lea     rcx, [rsp+0E8h+var_B8]
0x180061ab3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061ab8  mov     eax, ebx
0x180061aba  jmp     loc_180061C10
0x180061abf  mov     qword ptr [rsp+0E8h+var_A8], 0
0x180061ac8  mov     rcx, [rsp+0E8h+var_C0]
0x180061acd  mov     rax, [rcx]
0x180061ad0  mov     rax, [rax+58h]
0x180061ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ad9  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180061add  mov     rcx, [rsp+0E8h+var_C0]
0x180061ae2  mov     rax, [rcx]
0x180061ae5  mov     rax, [rax+60h]
0x180061ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061aee  mov     dword ptr [rsp+0E8h+var_A8+4], eax
0x180061af2  xorps   xmm0, xmm0
0x180061af5  xor     eax, eax
0x180061af7  movups  [rsp+0E8h+Buf2], xmm0
0x180061afc  movups  [rsp+0E8h+var_88], xmm0
0x180061b01  mov     [rsp+0E8h+var_78], eax
0x180061b05  mov     rcx, [rsp+0E8h+var_C0]
0x180061b0a  mov     rax, [rcx]
0x180061b0d  lea     rdx, [rsp+0E8h+Buf2]
0x180061b12  mov     rax, [rax+50h]
0x180061b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b1b  mov     ebx, eax
0x180061b1d  test    eax, eax
0x180061b1f  jns     short loc_180061B65
0x180061b21  mov     rcx, [rsp+0E8h]; this
0x180061b29  mov     r9d, eax; char *
0x180061b2c  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180061b33  mov     edx, 1E4h; void *
0x180061b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061b3d  nop
0x180061b3e  lea     rcx, [rsp+0E8h+var_C0]
0x180061b43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061b48  nop
0x180061b49  lea     rcx, [rsp+0E8h+var_B0]
0x180061b4e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061b53  nop
0x180061b54  lea     rcx, [rsp+0E8h+var_B8]
0x180061b59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061b5e  mov     eax, ebx
0x180061b60  jmp     loc_180061C10
0x180061b65  mov     eax, dword ptr [rsp+0E8h+Buf1]
0x180061b69  cmp     eax, dword ptr [rsp+0E8h+Buf2]
0x180061b6d  jnz     loc_180061C64
0x180061b73  mov     r8d, eax; Size
0x180061b76  lea     rdx, [rsp+0E8h+Buf2+4]; Buf2
0x180061b7b  lea     rcx, [rsp+0E8h+Buf1+4]; Buf1
0x180061b80  call    memcmp_0
0x180061b85  test    eax, eax
0x180061b87  jnz     loc_180061C64
0x180061b8d  mov     r10d, [rsi+8Ch]
0x180061b94  lea     rdx, [rsp+0E8h+var_A8]
0x180061b99  mov     ecx, r10d
0x180061b9c  call    ?IsSecurityTypeSameAuthCipherPair@WlanClient@Internal@UX@Networking@Windows@@SA_NW4WiFiSecurityType@345@AEBUDOT11_AUTH_CIPHER_PAIR@@@Z; Windows::Networking::UX::Internal::WlanClient::IsSecurityTypeSameAuthCipherPair(Windows::Networking::UX::WiFiSecurityType,DOT11_AUTH_CIPHER_PAIR const &)
0x180061ba1  test    al, al
0x180061ba3  jz      loc_180061C31
0x180061ba9  mov     byte ptr [r15], 1
0x180061bad  mov     eax, [rsi+8Ch]
0x180061bb3  mov     [r12], eax
0x180061bb7  lea     rcx, [rsp+0E8h+var_C0]
0x180061bbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061bc1  nop
0x180061bc2  lea     rcx, [rsp+0E8h+var_B0]
0x180061bc7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bd3  lea     rax, WPP_GLOBAL_Control
0x180061bda  cmp     rcx, rax
0x180061bdd  jz      short loc_180061BFE
0x180061bdf  test    byte ptr [rcx+1Ch], 8
0x180061be3  jz      short loc_180061BFE
0x180061be5  mov     edx, 27h ; '''
0x180061bea  xor     r9d, r9d
0x180061bed  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x180061bf4  mov     rcx, [rcx+10h]
0x180061bf8  call    WPP_SF_d
0x180061bfd  nop
0x180061bfe  lea     rcx, [rsp+0E8h+var_B8]
0x180061c03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061c08  xor     eax, eax
0x180061c0a  jmp     short loc_180061C10
0x180061c0c  mov     eax, [rsp+0E8h+var_C8]
0x180061c10  mov     rcx, [rsp+0E8h+var_48]
0x180061c18  xor     rcx, rsp; StackCookie
0x180061c1b  call    __security_check_cookie
0x180061c20  add     rsp, 0B8h
0x180061c27  pop     r15
0x180061c29  pop     r14
0x180061c2b  pop     r12
0x180061c2d  pop     rdi
0x180061c2e  pop     rsi
0x180061c2f  pop     rbx
0x180061c30  retn
0x180061c31  cmp     r10d, 0Ch
0x180061c35  jnz     short loc_180061C64
0x180061c37  cmp     byte ptr [rsi+93h], 0
0x180061c3e  jz      short loc_180061C64
0x180061c40  lea     rdx, [rsp+0E8h+var_A8]
0x180061c45  mov     r10d, 4
0x180061c4b  mov     ecx, r10d
0x180061c4e  call    ?IsSecurityTypeSameAuthCipherPair@WlanClient@Internal@UX@Networking@Windows@@SA_NW4WiFiSecurityType@345@AEBUDOT11_AUTH_CIPHER_PAIR@@@Z; Windows::Networking::UX::Internal::WlanClient::IsSecurityTypeSameAuthCipherPair(Windows::Networking::UX::WiFiSecurityType,DOT11_AUTH_CIPHER_PAIR const &)
0x180061c53  test    al, al
0x180061c55  jz      short loc_180061C64
0x180061c57  mov     byte ptr [r15], 1
0x180061c5b  mov     [r12], r10d
0x180061c5f  jmp     loc_180061BB7
0x180061c64  lea     rcx, [rsp+0E8h+var_C0]
0x180061c69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061c6e  nop
0x180061c6f  lea     rcx, [rsp+0E8h+var_B0]
0x180061c74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061c79  inc     r14d
0x180061c7c  jmp     loc_180061A18
```
