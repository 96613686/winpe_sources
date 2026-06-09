# Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001b220`
- end: `0x18001b3e6`
- name: `?GetMsaTicket@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b430`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180017a20`
- `0x18001b220`
- `0x18001f030`
- `0x1800215e4`
- `0x1800238cc`
- `0x1800260b8`
- `0x180027904`

## string_xrefs

- `0x18001b349`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b398`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b27f`: `https://ztd.dds.microsoft.com`
- `0x18001b286`: `DdsZtdMsaTicketUri`

## pseudocode

```c
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
  __int64 v9; // rdx
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
                          L"DdsZtdMsaTicketUri",
                          L"https://ztd.dds.microsoft.com",
                          v16);
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
                          (__int64)&v13[1]);
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
        std::wstring::_Tidy_deallocate((char **)v18);
        std::wstring::_Tidy_deallocate((char **)v17);
        goto LABEL_20;
      }
      Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(v10, v9);
      std::wstring::_Tidy_deallocate((char **)v18);
      std::wstring::_Tidy_deallocate((char **)v17);
      if ( (unsigned int)++v6 >= 2 )
        goto LABEL_14;
    }
    std::wstring::_Tidy_deallocate((char **)v18);
    std::wstring::_Tidy_deallocate((char **)v17);
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
  std::wstring::_Tidy_deallocate((char **)v16);
  std::wstring::_Tidy_deallocate((char **)&v13[1]);
  return v4;
}

```

## disassembly

```asm
0x18001b220  mov     rax, rsp
0x18001b223  push    rbp
0x18001b224  push    rbx
0x18001b225  push    rsi
0x18001b226  push    rdi
0x18001b227  lea     rbp, [rax-5Fh]
0x18001b22b  sub     rsp, 0E8h
0x18001b232  movaps  xmmword ptr [rax-38h], xmm6
0x18001b236  mov     rax, cs:__security_cookie
0x18001b23d  xor     rax, rsp
0x18001b240  mov     [rbp+57h+var_40], rax
0x18001b244  mov     rsi, rcx
0x18001b247  xorps   xmm0, xmm0
0x18001b24a  movups  xmmword ptr [rsp+100h+var_E8+8], xmm0
0x18001b24f  mov     [rbp+57h+var_D0], 0
0x18001b257  mov     [rbp+57h+var_C8], 7
0x18001b25f  xor     eax, eax
0x18001b261  mov     word ptr [rsp+100h+var_E8+8], ax; int
0x18001b266  movups  [rbp+57h+var_C0], xmm0
0x18001b26a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001b272  movdqu  [rbp+57h+var_B0], xmm6
0x18001b277  mov     word ptr [rbp+57h+var_C0], ax
0x18001b27b  lea     r8, [rbp+57h+var_C0]
0x18001b27f  lea     rdx, aHttpsZtdDdsMic_0; "https://ztd.dds.microsoft.com"
0x18001b286  lea     rcx, aDdsztdmsaticke; "DdsZtdMsaTicketUri"
0x18001b28d  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x18001b292  mov     ebx, eax
0x18001b294  test    eax, eax
0x18001b296  jns     short loc_18001B2A2
0x18001b298  mov     edx, 292h
0x18001b29d  jmp     loc_18001B398
0x18001b2a2  xor     edi, edi
0x18001b2a4  mov     [rbp+57h+var_D0], 0
0x18001b2ac  lea     rcx, [rsp+100h+var_E8+8]
0x18001b2b1  cmp     [rbp+57h+var_C8], 7
0x18001b2b6  cmova   rcx, qword ptr [rsp+100h+var_E8+8]
0x18001b2bc  xor     eax, eax
0x18001b2be  mov     [rcx], ax
0x18001b2c1  xorps   xmm0, xmm0
0x18001b2c4  movups  [rbp+57h+var_A0], xmm0
0x18001b2c8  movdqa  [rbp+57h+var_90], xmm6
0x18001b2cd  mov     word ptr [rbp+57h+var_A0], ax
0x18001b2d1  movups  [rbp+57h+var_80], xmm0
0x18001b2d5  movdqa  [rbp+57h+var_70], xmm6
0x18001b2da  mov     word ptr [rbp+57h+var_80], ax
0x18001b2de  movdqa  [rbp+57h+var_60], xmm0
0x18001b2e3  mov     [rbp+57h+var_50], rax
0x18001b2e7  lea     r8, [rsp+100h+var_E8+8]
0x18001b2ec  lea     rdx, [rbp+57h+var_C0]
0x18001b2f0  call    ?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::wstring const &,std::wstring &)
0x18001b2f5  mov     ebx, eax
0x18001b2f7  test    eax, eax
0x18001b2f9  jns     short loc_18001B35C
0x18001b2fb  cmp     eax, 80072F05h
0x18001b300  jnz     short loc_18001B323
0x18001b302  call    ?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)
0x18001b307  nop
0x18001b308  lea     rcx, [rbp+57h+var_80]
0x18001b30c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b311  lea     rcx, [rbp+57h+var_A0]
0x18001b315  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b31a  inc     edi
0x18001b31c  cmp     edi, 2
0x18001b31f  jb      short loc_18001B2A4
0x18001b321  jmp     short loc_18001B36E
0x18001b323  mov     ecx, ebx; int
0x18001b325  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x18001b32a  test    al, al
0x18001b32c  jz      short loc_18001B342
0x18001b32e  lea     rcx, [rbp+57h+var_80]
0x18001b332  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b337  lea     rcx, [rbp+57h+var_A0]
0x18001b33b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b340  jmp     short loc_18001B3AF
0x18001b342  mov     rcx, [rbp+5Fh]; this
0x18001b346  mov     r9d, ebx; char *
0x18001b349  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b350  mov     edx, 2A9h; void *
0x18001b355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b35a  jmp     short loc_18001B32E
0x18001b35c  lea     rcx, [rbp+57h+var_80]
0x18001b360  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b365  lea     rcx, [rbp+57h+var_A0]
0x18001b369  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b36e  lea     r8, [rsp+100h+var_E8+8]
0x18001b373  cmp     [rbp+57h+var_C8], 7
0x18001b378  cmova   r8, qword ptr [rsp+100h+var_E8+8]; unsigned __int16 *
0x18001b37e  lea     rdx, aMsaticket; "MsaTicket"
0x18001b385  mov     rcx, [rsi]; struct Windows::Data::Json::IJsonObject *
0x18001b388  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001b38d  mov     ebx, eax
0x18001b38f  test    eax, eax
0x18001b391  jns     short loc_18001B3AD
0x18001b393  mov     edx, 2ACh; void *
0x18001b398  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b39f  mov     r9d, eax; char *
0x18001b3a2  mov     rcx, [rbp+5Fh]; this
0x18001b3a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3ab  jmp     short loc_18001B3AF
0x18001b3ad  xor     ebx, ebx
0x18001b3af  lea     rcx, [rbp+57h+var_C0]
0x18001b3b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b3b8  nop
0x18001b3b9  lea     rcx, [rsp+100h+var_E8+8]
0x18001b3be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b3c3  mov     eax, ebx
0x18001b3c5  mov     rcx, [rbp+57h+var_40]
0x18001b3c9  xor     rcx, rsp; StackCookie
0x18001b3cc  call    __security_check_cookie
0x18001b3d1  movaps  xmm6, [rsp+100h+var_38+8]
0x18001b3d9  add     rsp, 0E8h
0x18001b3e0  pop     rdi
0x18001b3e1  pop     rsi
0x18001b3e2  pop     rbx
0x18001b3e3  pop     rbp
0x18001b3e4  retn
```
