# Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001ab88`
- end: `0x18001ad4d`
- name: `?GetMsaTicket@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ada0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800174f0`
- `0x18001ab88`
- `0x18001e7b4`
- `0x180020bd0`
- `0x180022d84`
- `0x1800252ec`
- `0x180026990`

## string_xrefs

- `0x18001acb1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ad00`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001abe7`: `https://ztd.dds.microsoft.com`
- `0x18001abee`: `DdsZtdMsaTicketUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(
        struct Windows::Data::Json::IJsonObject **a1)
{
  __m128i si128; // xmm6
  int RegistryDownloadKey; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // edi
  _WORD *v7; // rcx
  int MsaDeviceTicket; // eax
  unsigned int v9; // edx
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // r8
  _QWORD v13[3]; // [rsp+20h] [rbp-91h] BYREF
  __int64 v14; // [rsp+38h] [rbp-79h]
  unsigned __int64 v15; // [rsp+40h] [rbp-71h]
  _OWORD v16[2]; // [rsp+48h] [rbp-69h] BYREF
  _OWORD v17[2]; // [rsp+68h] [rbp-49h] BYREF
  _OWORD v18[3]; // [rsp+88h] [rbp-29h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  *(_OWORD *)&v13[1] = 0;
  v14 = 0;
  v15 = 7;
  LOWORD(v13[1]) = 0;
  v16[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v16[1] = si128;
  LOWORD(v16[0]) = 0;
  RegistryDownloadKey = Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(
                          (__int64)L"DdsZtdMsaTicketUri",
                          L"https://ztd.dds.microsoft.com",
                          (char **)v16);
  v4 = RegistryDownloadKey;
  if ( RegistryDownloadKey >= 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      v14 = 0;
      v7 = &v13[1];
      if ( v15 > 7 )
        v7 = (_WORD *)v13[1];
      *v7 = 0;
      v17[0] = 0;
      v17[1] = si128;
      LOWORD(v17[0]) = 0;
      v18[0] = 0;
      v18[1] = si128;
      LOWORD(v18[0]) = 0;
      v18[2] = 0;
      v19 = 0;
      MsaDeviceTicket = Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(
                          (__int64)v7,
                          v16,
                          (char **)&v13[1]);
      v4 = MsaDeviceTicket;
      if ( MsaDeviceTicket >= 0 )
        break;
      if ( MsaDeviceTicket != -2147012859 )
      {
        if ( !Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(MsaDeviceTicket) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A9,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)v4,
            v13[1]);
        std::wstring::_Tidy_deallocate(v18);
        std::wstring::_Tidy_deallocate(v17);
        goto LABEL_20;
      }
      Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(v10, v9);
      std::wstring::_Tidy_deallocate(v18);
      std::wstring::_Tidy_deallocate(v17);
      if ( (unsigned int)++v6 >= 2 )
        goto LABEL_14;
    }
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v17);
LABEL_14:
    v11 = (const unsigned __int16 *)&v13[1];
    if ( v15 > 7 )
      v11 = (const unsigned __int16 *)v13[1];
    RegistryDownloadKey = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a1, L"MsaTicket", v11);
    v4 = RegistryDownloadKey;
    if ( RegistryDownloadKey < 0 )
    {
      v5 = 684;
      goto LABEL_18;
    }
    v4 = 0;
  }
  else
  {
    v5 = 658;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)RegistryDownloadKey,
      v13[1]);
  }
LABEL_20:
  std::wstring::_Tidy_deallocate(v16);
  std::wstring::_Tidy_deallocate(&v13[1]);
  return v4;
}

```

## disassembly

```asm
0x18001ab88  mov     rax, rsp
0x18001ab8b  push    rbp
0x18001ab8c  push    rbx
0x18001ab8d  push    rsi
0x18001ab8e  push    rdi
0x18001ab8f  lea     rbp, [rax-5Fh]
0x18001ab93  sub     rsp, 0E8h
0x18001ab9a  movaps  xmmword ptr [rax-38h], xmm6
0x18001ab9e  mov     rax, cs:__security_cookie
0x18001aba5  xor     rax, rsp
0x18001aba8  mov     [rbp+57h+var_40], rax
0x18001abac  mov     rsi, rcx
0x18001abaf  xorps   xmm0, xmm0
0x18001abb2  movups  xmmword ptr [rsp+100h+var_E8+8], xmm0
0x18001abb7  mov     [rbp+57h+var_D0], 0
0x18001abbf  mov     [rbp+57h+var_C8], 7
0x18001abc7  xor     eax, eax
0x18001abc9  mov     word ptr [rsp+100h+var_E8+8], ax; int
0x18001abce  movups  [rbp+57h+var_C0], xmm0
0x18001abd2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001abda  movdqu  [rbp+57h+var_B0], xmm6
0x18001abdf  mov     word ptr [rbp+57h+var_C0], ax
0x18001abe3  lea     r8, [rbp+57h+var_C0]
0x18001abe7  lea     rdx, aHttpsZtdDdsMic_0; "https://ztd.dds.microsoft.com"
0x18001abee  lea     rcx, aDdsztdmsaticke; "DdsZtdMsaTicketUri"
0x18001abf5  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x18001abfa  mov     ebx, eax
0x18001abfc  test    eax, eax
0x18001abfe  jns     short loc_18001AC0A
0x18001ac00  mov     edx, 292h
0x18001ac05  jmp     loc_18001AD00
0x18001ac0a  xor     edi, edi
0x18001ac0c  mov     [rbp+57h+var_D0], 0
0x18001ac14  lea     rcx, [rsp+100h+var_E8+8]
0x18001ac19  cmp     [rbp+57h+var_C8], 7
0x18001ac1e  cmova   rcx, qword ptr [rsp+100h+var_E8+8]
0x18001ac24  xor     eax, eax
0x18001ac26  mov     [rcx], ax
0x18001ac29  xorps   xmm0, xmm0
0x18001ac2c  movups  [rbp+57h+var_A0], xmm0
0x18001ac30  movdqa  [rbp+57h+var_90], xmm6
0x18001ac35  mov     word ptr [rbp+57h+var_A0], ax
0x18001ac39  movups  [rbp+57h+var_80], xmm0
0x18001ac3d  movdqa  [rbp+57h+var_70], xmm6
0x18001ac42  mov     word ptr [rbp+57h+var_80], ax
0x18001ac46  movdqa  [rbp+57h+var_60], xmm0
0x18001ac4b  mov     [rbp+57h+var_50], rax
0x18001ac4f  lea     r8, [rsp+100h+var_E8+8]
0x18001ac54  lea     rdx, [rbp+57h+var_C0]
0x18001ac58  call    ?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::wstring const &,std::wstring &)
0x18001ac5d  mov     ebx, eax
0x18001ac5f  test    eax, eax
0x18001ac61  jns     short loc_18001ACC4
0x18001ac63  cmp     eax, 80072F05h
0x18001ac68  jnz     short loc_18001AC8B
0x18001ac6a  call    ?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)
0x18001ac6f  nop
0x18001ac70  lea     rcx, [rbp+57h+var_80]
0x18001ac74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac79  lea     rcx, [rbp+57h+var_A0]
0x18001ac7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac82  inc     edi
0x18001ac84  cmp     edi, 2
0x18001ac87  jb      short loc_18001AC0C
0x18001ac89  jmp     short loc_18001ACD6
0x18001ac8b  mov     ecx, ebx; int
0x18001ac8d  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x18001ac92  test    al, al
0x18001ac94  jz      short loc_18001ACAA
0x18001ac96  lea     rcx, [rbp+57h+var_80]
0x18001ac9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac9f  lea     rcx, [rbp+57h+var_A0]
0x18001aca3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aca8  jmp     short loc_18001AD17
0x18001acaa  mov     rcx, [rbp+5Fh]; this
0x18001acae  mov     r9d, ebx; char *
0x18001acb1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001acb8  mov     edx, 2A9h; void *
0x18001acbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acc2  jmp     short loc_18001AC96
0x18001acc4  lea     rcx, [rbp+57h+var_80]
0x18001acc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001accd  lea     rcx, [rbp+57h+var_A0]
0x18001acd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001acd6  lea     r8, [rsp+100h+var_E8+8]
0x18001acdb  cmp     [rbp+57h+var_C8], 7
0x18001ace0  cmova   r8, qword ptr [rsp+100h+var_E8+8]; unsigned __int16 *
0x18001ace6  lea     rdx, aMsaticket; "MsaTicket"
0x18001aced  mov     rcx, [rsi]; struct Windows::Data::Json::IJsonObject *
0x18001acf0  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001acf5  mov     ebx, eax
0x18001acf7  test    eax, eax
0x18001acf9  jns     short loc_18001AD15
0x18001acfb  mov     edx, 2ACh; void *
0x18001ad00  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ad07  mov     r9d, eax; char *
0x18001ad0a  mov     rcx, [rbp+5Fh]; this
0x18001ad0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad13  jmp     short loc_18001AD17
0x18001ad15  xor     ebx, ebx
0x18001ad17  lea     rcx, [rbp+57h+var_C0]
0x18001ad1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad20  nop
0x18001ad21  lea     rcx, [rsp+100h+var_E8+8]
0x18001ad26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad2b  mov     eax, ebx
0x18001ad2d  mov     rcx, [rbp+57h+var_40]
0x18001ad31  xor     rcx, rsp; StackCookie
0x18001ad34  call    __security_check_cookie
0x18001ad39  movaps  xmm6, [rsp+100h+var_38+8]
0x18001ad41  add     rsp, 0E8h
0x18001ad48  pop     rdi
0x18001ad49  pop     rsi
0x18001ad4a  pop     rbx
0x18001ad4b  pop     rbp
0x18001ad4c  retn
```
