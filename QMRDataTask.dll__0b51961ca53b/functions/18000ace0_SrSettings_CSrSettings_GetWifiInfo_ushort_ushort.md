# SrSettings::CSrSettings::GetWifiInfo(ushort * *,ushort * *)

- ea: `0x18000ace0`
- end: `0x18000af60`
- name: `?GetWifiInfo@CSrSettings@SrSettings@@UEAAJPEAPEAG0@Z`
- size: `640`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callees

- `0x180002178`
- `0x180007080`
- `0x18000a1c0`
- `0x18000ace0`
- `0x180010a0c`
- `0x1800118e0`
- `0x180012d7c`

## string_xrefs

- `0x18000adaf`: `Failed to get managed WiFi SSID, trying user set SSID. Error: 0x%08x`
- `0x18000ae71`: `Failed to get managed WiFi SSID, trying user set SSID. Error: 0x%08x`
- `0x18000adea`: `Failed to get user set WiFi SSID. Error: 0x%08x`
- `0x18000aeed`: `Failed to copy WiFi SSID. Error: 0x%08x`
- `0x18000af08`: `Failed to copy WiFi password. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::GetWifiInfo(
        SrSettings::CSrSettings *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  char IsEnabled; // al
  __int64 v8; // rdx
  int v9; // eax
  SrSettings::CSrSettings *v10; // rcx
  errno_t v11; // edi
  SrSettings::CSrSettings *v12; // rcx
  const wchar_t *v13; // r8
  int ResourceString; // eax
  void *v15[2]; // [rsp+30h] [rbp-48h] BYREF
  _WORD v16[8]; // [rsp+40h] [rbp-38h] BYREF
  void *v17[2]; // [rsp+50h] [rbp-28h] BYREF
  _WORD v18[12]; // [rsp+60h] [rbp-18h] BYREF

  if ( !*((_BYTE *)this + 3945) )
    return 2147942421LL;
  if ( !(unsigned int)FileExists(*((const wchar_t **)this + 13)) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"WiFi setting file %s doesn't exist", *((_QWORD *)this + 13));
    return 2147942402LL;
  }
  v17[0] = v18;
  v17[1] = v18;
  v18[0] = 0;
  v15[0] = v16;
  v15[1] = v16;
  v16[0] = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetImpl'::`2'::impl);
  v8 = *((_QWORD *)this + 13);
  if ( !IsEnabled )
  {
    ResourceString = SrSettings::CSrSettings::GetResourceString(this, v8, L"ManagedWiFiCredential", L"SSID", v17);
    v10 = this;
    if ( ResourceString < 0 )
    {
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to get managed WiFi SSID, trying user set SSID. Error: 0x%08x",
        (unsigned int)ResourceString);
      v11 = SrSettings::CSrSettings::GetResourceString(this, *((_QWORD *)this + 13), L"WiFiCredential", L"SSID", v17);
      v12 = this;
      if ( v11 < 0 )
        goto LABEL_8;
      v11 = SrSettings::CSrSettings::GetResourceString(
              this,
              *((_QWORD *)this + 13),
              L"WiFiCredential",
              L"Password",
              v15);
      if ( v11 >= 0 )
        goto LABEL_22;
      goto LABEL_10;
    }
    goto LABEL_11;
  }
  v9 = SrSettings::CSrSettings::GetResourceString(this, v8, L"ManagedWiFiCredential", L"SSID", v17);
  v10 = this;
  if ( v9 >= 0 )
  {
LABEL_11:
    v11 = SrSettings::CSrSettings::GetResourceString(
            v10,
            *((_QWORD *)this + 13),
            L"ManagedWiFiCredential",
            L"Password",
            v15);
    if ( v11 < 0 )
    {
      v13 = L"Failed to get WiFi password. Error: 0x%08x";
      goto LABEL_21;
    }
    goto LABEL_17;
  }
  SrSettings::CSrSettings::Trace(
    this,
    2,
    L"Failed to get managed WiFi SSID, trying user set SSID. Error: 0x%08x",
    (unsigned int)v9);
  v11 = SrSettings::CSrSettings::GetResourceString(this, *((_QWORD *)this + 13), L"WiFiCredential", L"SSID", v17);
  v12 = this;
  if ( v11 >= 0 )
  {
    v11 = SrSettings::CSrSettings::GetResourceString(this, *((_QWORD *)this + 13), L"WiFiCredential", L"Password", v15);
    if ( v11 < 0 )
    {
LABEL_10:
      v13 = L"Failed to get user set WiFi password. Error: 0x%08x";
      goto LABEL_21;
    }
LABEL_17:
    v11 = CopyString((__int64)v17, (void **)a2);
    if ( v11 >= 0 )
    {
      v11 = CopyString((__int64)v15, (void **)a3);
      if ( v11 >= 0 )
        goto LABEL_22;
      v13 = L"Failed to copy WiFi password. Error: 0x%08x";
    }
    else
    {
      v13 = L"Failed to copy WiFi SSID. Error: 0x%08x";
    }
LABEL_21:
    SrSettings::CSrSettings::Trace(this, 2, v13, (unsigned int)v11);
    goto LABEL_22;
  }
LABEL_8:
  SrSettings::CSrSettings::Trace(v12, 2, L"Failed to get user set WiFi SSID. Error: 0x%08x", (unsigned int)v11);
LABEL_22:
  if ( v15[0] != v16 )
    operator delete(v15[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v17[0] != v18 )
    operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ace0  push    rbp
0x18000ace2  push    rbx
0x18000ace3  push    rsi
0x18000ace4  push    rdi
0x18000ace5  push    r14
0x18000ace7  push    r15
0x18000ace9  mov     rbp, rsp
0x18000acec  sub     rsp, 78h
0x18000acf0  mov     r14, r8
0x18000acf3  mov     rsi, rdx
0x18000acf6  mov     rbx, rcx
0x18000acf9  cmp     byte ptr [rcx+0F69h], 0
0x18000ad00  jnz     short loc_18000AD0C
0x18000ad02  mov     eax, 80070015h
0x18000ad07  jmp     loc_18000AF53
0x18000ad0c  mov     rcx, [rcx+68h]
0x18000ad10  call    FileExists
0x18000ad15  test    eax, eax
0x18000ad17  jnz     short loc_18000AD38
0x18000ad19  mov     r9, [rbx+68h]
0x18000ad1d  lea     r8, aWifiSettingFil; "WiFi setting file %s doesn't exist"
0x18000ad24  xor     edx, edx
0x18000ad26  mov     rcx, rbx
0x18000ad29  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ad2e  mov     eax, 80070002h
0x18000ad33  jmp     loc_18000AF53
0x18000ad38  lea     rax, [rbp+var_18]
0x18000ad3c  mov     [rbp+var_28], rax
0x18000ad40  lea     rax, [rbp+var_18]
0x18000ad44  mov     [rbp+var_20], rax
0x18000ad48  xor     eax, eax
0x18000ad4a  mov     [rbp+var_18], ax
0x18000ad4e  lea     rax, [rbp+var_38]
0x18000ad52  mov     [rbp+var_48], rax
0x18000ad56  lea     rax, [rbp+var_38]
0x18000ad5a  mov     [rbp+var_40], rax
0x18000ad5e  xor     eax, eax
0x18000ad60  mov     [rbp+var_38], ax
0x18000ad64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetImpl(void)'::`2'::impl
0x18000ad6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::__private_IsEnabled(void)
0x18000ad70  mov     rdx, [rbx+68h]
0x18000ad74  mov     r15d, 2
0x18000ad7a  lea     r9, aSsid; "SSID"
0x18000ad81  lea     r8, aManagedwificre; "ManagedWiFiCredential"
0x18000ad88  mov     rcx, rbx
0x18000ad8b  test    al, al
0x18000ad8d  lea     rax, [rbp+var_28]
0x18000ad91  mov     [rsp+78h+var_58], rax
0x18000ad96  jz      loc_18000AE62
0x18000ad9c  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ada1  mov     rcx, rbx
0x18000ada4  test    eax, eax
0x18000ada6  jns     loc_18000AE2C
0x18000adac  mov     r9d, eax
0x18000adaf  lea     r8, aFailedToGetMan; "Failed to get managed WiFi SSID, trying"...
0x18000adb6  mov     edx, r15d
0x18000adb9  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000adbe  lea     rax, [rbp+var_28]
0x18000adc2  mov     [rsp+78h+var_58], rax
0x18000adc7  lea     r9, aSsid; "SSID"
0x18000adce  lea     r8, aWificredential; "WiFiCredential"
0x18000add5  mov     rdx, [rbx+68h]
0x18000add9  mov     rcx, rbx
0x18000addc  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ade1  mov     edi, eax
0x18000ade3  mov     rcx, rbx
0x18000ade6  test    eax, eax
0x18000ade8  jns     short loc_18000ADF6
0x18000adea  lea     r8, aFailedToGetUse_0; "Failed to get user set WiFi SSID. Error"...
0x18000adf1  jmp     loc_18000AF12
0x18000adf6  lea     rax, [rbp+var_48]
0x18000adfa  mov     [rsp+78h+var_58], rax
0x18000adff  lea     r9, aPassword; "Password"
0x18000ae06  lea     r8, aWificredential; "WiFiCredential"
0x18000ae0d  mov     rdx, [rbx+68h]
0x18000ae11  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ae16  mov     edi, eax
0x18000ae18  test    eax, eax
0x18000ae1a  jns     loc_18000AEDB
0x18000ae20  lea     r8, aFailedToGetUse; "Failed to get user set WiFi password. E"...
0x18000ae27  jmp     loc_18000AF0F
0x18000ae2c  lea     rax, [rbp+var_48]
0x18000ae30  mov     [rsp+78h+var_58], rax
0x18000ae35  lea     r9, aPassword; "Password"
0x18000ae3c  lea     r8, aManagedwificre; "ManagedWiFiCredential"
0x18000ae43  mov     rdx, [rbx+68h]
0x18000ae47  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ae4c  mov     edi, eax
0x18000ae4e  test    eax, eax
0x18000ae50  jns     loc_18000AEDB
0x18000ae56  lea     r8, aFailedToGetWif; "Failed to get WiFi password. Error: 0x%"...
0x18000ae5d  jmp     loc_18000AF0F
0x18000ae62  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ae67  mov     rcx, rbx
0x18000ae6a  test    eax, eax
0x18000ae6c  jns     short loc_18000AE2C
0x18000ae6e  mov     r9d, eax
0x18000ae71  lea     r8, aFailedToGetMan; "Failed to get managed WiFi SSID, trying"...
0x18000ae78  mov     edx, r15d
0x18000ae7b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ae80  lea     rax, [rbp+var_28]
0x18000ae84  mov     [rsp+78h+var_58], rax
0x18000ae89  lea     r9, aSsid; "SSID"
0x18000ae90  lea     r8, aWificredential; "WiFiCredential"
0x18000ae97  mov     rdx, [rbx+68h]
0x18000ae9b  mov     rcx, rbx
0x18000ae9e  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000aea3  mov     edi, eax
0x18000aea5  mov     rcx, rbx
0x18000aea8  test    eax, eax
0x18000aeaa  js      loc_18000ADEA
0x18000aeb0  lea     rax, [rbp+var_48]
0x18000aeb4  mov     [rsp+78h+var_58], rax
0x18000aeb9  lea     r9, aPassword; "Password"
0x18000aec0  lea     r8, aWificredential; "WiFiCredential"
0x18000aec7  mov     rdx, [rbx+68h]
0x18000aecb  call    ?GetResourceString@CSrSettings@SrSettings@@AEAAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetResourceString(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000aed0  mov     edi, eax
0x18000aed2  test    eax, eax
0x18000aed4  jns     short loc_18000AF1E
0x18000aed6  jmp     loc_18000AE20
0x18000aedb  mov     rdx, rsi
0x18000aede  lea     rcx, [rbp+var_28]
0x18000aee2  call    ?CopyString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAPEAG@Z; CopyString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort * *)
0x18000aee7  mov     edi, eax
0x18000aee9  test    eax, eax
0x18000aeeb  jns     short loc_18000AEF6
0x18000aeed  lea     r8, aFailedToCopyWi_0; "Failed to copy WiFi SSID. Error: 0x%08x"
0x18000aef4  jmp     short loc_18000AF0F
0x18000aef6  mov     rdx, r14
0x18000aef9  lea     rcx, [rbp+var_48]
0x18000aefd  call    ?CopyString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAPEAG@Z; CopyString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort * *)
0x18000af02  mov     edi, eax
0x18000af04  test    eax, eax
0x18000af06  jns     short loc_18000AF1E
0x18000af08  lea     r8, aFailedToCopyWi; "Failed to copy WiFi password. Error: 0x"...
0x18000af0f  mov     rcx, rbx
0x18000af12  mov     r9d, edi
0x18000af15  mov     edx, r15d
0x18000af18  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000af1d  nop
0x18000af1e  lea     rax, [rbp+var_38]
0x18000af22  mov     rcx, [rbp+var_48]; void *
0x18000af26  cmp     rcx, rax
0x18000af29  jz      short loc_18000AF38
0x18000af2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000af32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000af37  nop
0x18000af38  lea     rax, [rbp+var_18]
0x18000af3c  mov     rcx, [rbp+var_28]; void *
0x18000af40  cmp     rcx, rax
0x18000af43  jz      short loc_18000AF51
0x18000af45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000af4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000af51  mov     eax, edi
0x18000af53  add     rsp, 78h
0x18000af57  pop     r15
0x18000af59  pop     r14
0x18000af5b  pop     rdi
0x18000af5c  pop     rsi
0x18000af5d  pop     rbx
0x18000af5e  pop     rbp
0x18000af5f  retn
```
