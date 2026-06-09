# SrSettings::CSrSettings::DeleteSettings(void)

- ea: `0x180007490`
- end: `0x18000771b`
- name: `?DeleteSettings@CSrSettings@SrSettings@@UEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(const WCHAR **this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180007490`
- `0x180010a0c`
- `0x180011a20`
- `0x180012d7c`
- `0x1800142d2`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800075ea`
- `KERNEL32!GetLastError` at `0x180007647`
- `KERNEL32!GetLastError` at `0x1800076a8`
- `KERNEL32!GetLastError` at `0x1800075ea`
- `KERNEL32!GetLastError` at `0x180007647`
- `KERNEL32!GetLastError` at `0x1800076a8`
- `KERNEL32!DeleteFileW` at `0x1800075e0`
- `KERNEL32!DeleteFileW` at `0x18000763d`
- `KERNEL32!DeleteFileW` at `0x18000769a`
- `KERNEL32!DeleteFileW` at `0x1800075e0`
- `KERNEL32!DeleteFileW` at `0x18000763d`
- `KERNEL32!DeleteFileW` at `0x18000769a`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000754e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000757e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000754e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000757e`

## string_xrefs

- `0x18000762d`: `Delete backup settings file %s`
- `0x18000765c`: `Failed to delete backup settings file. Error: 0x%08x`
- `0x18000759e`: `Cannot delete settings in UseInWinRE mode`
- `0x1800075d0`: `Delete setting file %s`
- `0x1800075ff`: `Failed to delete settings file. Error: 0x%08x`
- `0x18000768a`: `Delete wifi settings file %s`
- `0x1800076bd`: `Failed to delete wifi settings file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::DeleteSettings(const WCHAR **this)
{
  __int64 (__fastcall **v2)(const WCHAR **); // rax
  unsigned int v3; // edi
  char IsEnabled; // al
  const WCHAR *v6; // rcx
  int v7; // eax
  const WCHAR *v8; // r9
  signed int LastError; // eax
  int v10; // eax
  const WCHAR *v11; // r9
  signed int v12; // eax
  int v13; // eax
  const WCHAR *v14; // r9
  signed int v15; // eax
  const WCHAR *lpFileName; // [rsp+28h] [rbp-240h]
  char v17; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v18[15]; // [rsp+31h] [rbp-237h] BYREF
  WCHAR ReturnedString[264]; // [rsp+40h] [rbp-228h] BYREF

  SrSettings::CSrSettings::Trace(this, 0, L"Checking if managed settings are present");
  v2 = (__int64 (__fastcall **)(const WCHAR **))*this;
  v18[0] = 0;
  v17 = 0;
  v3 = ((__int64 (__fastcall *)(const WCHAR **, _BYTE *, char *))v2[17])(this, v18, &v17);
  if ( (v3 & 0x80000000) != 0 )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to query WiFi settings. Error: 0x%08x", v3);
    return v3;
  }
  memset_0(ReturnedString, 0, 0x208u);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl'::`2'::impl);
  lpFileName = this[5];
  v6 = L"ManagedSettings";
  if ( IsEnabled )
  {
    if ( GetPrivateProfileStringW(L"ManagedSettings", 0, 0, ReturnedString, 0x104u, lpFileName) )
    {
LABEL_29:
      SrSettings::CSrSettings::Trace(
        this,
        0,
        L"Managed settings are present, we will clear non-managed settings instead");
      return (*((__int64 (__fastcall **)(const WCHAR **))*this + 11))(this);
    }
    lpFileName = this[5];
    v6 = L"ManagedSettings_GPO";
  }
  if ( GetPrivateProfileStringW(v6, 0, 0, ReturnedString, 0x104u, lpFileName) || v17 )
    goto LABEL_29;
  if ( !*((_BYTE *)this + 3944) )
  {
    v7 = FileExists(this[5]);
    v8 = this[5];
    if ( v7 )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Delete setting file %s", v8);
      if ( !DeleteFileW(this[5]) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        SrSettings::CSrSettings::Trace(this, 2, L"Failed to delete settings file. Error: 0x%08x", v3);
        return v3;
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Setting file %s doesn't exist", v8);
    }
    v10 = FileExists(this[9]);
    v11 = this[9];
    if ( v10 )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Delete backup settings file %s", v11);
      if ( !DeleteFileW(this[9]) )
      {
        v12 = GetLastError();
        v3 = v12;
        if ( v12 > 0 )
          v3 = (unsigned __int16)v12 | 0x80070000;
        SrSettings::CSrSettings::Trace(this, 2, L"Failed to delete backup settings file. Error: 0x%08x", v3);
        return v3;
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Backup setting file %s doesn't exist", v11);
    }
    v13 = FileExists(this[13]);
    v14 = this[13];
    if ( v13 )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Delete wifi settings file %s", v14);
      if ( !DeleteFileW(this[13]) )
      {
        v15 = GetLastError();
        v3 = v15;
        if ( v15 > 0 )
          v3 = (unsigned __int16)v15 | 0x80070000;
        SrSettings::CSrSettings::Trace(this, 2, L"Failed to delete wifi settings file. Error: 0x%08x", v3);
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(this, 0, L"WiFi setting file %s doesn't exist", v14);
    }
    return v3;
  }
  SrSettings::CSrSettings::Trace(this, 2, L"Cannot delete settings in UseInWinRE mode");
  return 2147942405LL;
}

```

## disassembly

```asm
0x180007490  mov     [rsp+arg_8], rbx
0x180007495  push    rdi
0x180007496  sub     rsp, 260h
0x18000749d  mov     rax, cs:__security_cookie
0x1800074a4  xor     rax, rsp
0x1800074a7  mov     [rsp+268h+var_18], rax
0x1800074af  lea     r8, aCheckingIfMana; "Checking if managed settings are presen"...
0x1800074b6  xor     edx, edx
0x1800074b8  mov     rbx, rcx
0x1800074bb  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800074c0  mov     rax, [rbx]
0x1800074c3  lea     r8, [rsp+268h+var_238]
0x1800074c8  lea     rdx, [rsp+268h+var_237]
0x1800074cd  mov     [rsp+268h+var_237], 0
0x1800074d2  mov     rcx, rbx
0x1800074d5  mov     [rsp+268h+var_238], 0
0x1800074da  mov     rax, [rax+88h]
0x1800074e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e6  mov     edi, eax
0x1800074e8  test    eax, eax
0x1800074ea  jns     short loc_18000750A
0x1800074ec  lea     r8, aFailedToQueryW; "Failed to query WiFi settings. Error: 0"...
0x1800074f3  mov     r9d, edi
0x1800074f6  mov     edx, 2
0x1800074fb  mov     rcx, rbx
0x1800074fe  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180007503  mov     eax, edi
0x180007505  jmp     loc_1800076FA
0x18000750a  xor     edx, edx; Val
0x18000750c  lea     rcx, [rsp+268h+ReturnedString]; void *
0x180007511  mov     r8d, 208h; Size
0x180007517  call    memset_0
0x18000751c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl(void)'::`2'::impl
0x180007523  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)
0x180007528  mov     rcx, [rbx+28h]
0x18000752c  lea     r9, [rsp+268h+ReturnedString]; lpReturnedString
0x180007531  mov     [rsp+268h+lpFileName], rcx; lpFileName
0x180007536  xor     r8d, r8d; lpDefault
0x180007539  xor     edx, edx; lpKeyName
0x18000753b  mov     [rsp+268h+nSize], 104h; nSize
0x180007543  lea     rcx, AppName; "ManagedSettings"
0x18000754a  test    al, al
0x18000754c  jz      short loc_18000757E
0x18000754e  call    cs:__imp_GetPrivateProfileStringW
0x180007554  test    eax, eax
0x180007556  jnz     loc_1800076DA
0x18000755c  mov     rax, [rbx+28h]
0x180007560  lea     r9, [rsp+268h+ReturnedString]; lpReturnedString
0x180007565  xor     r8d, r8d; lpDefault
0x180007568  mov     [rsp+268h+lpFileName], rax; lpFileName
0x18000756d  mov     [rsp+268h+nSize], 104h; nSize
0x180007575  lea     rcx, aManagedsetting; "ManagedSettings_GPO"
0x18000757c  xor     edx, edx; lpKeyName
0x18000757e  call    cs:__imp_GetPrivateProfileStringW
0x180007584  test    eax, eax
0x180007586  jnz     loc_1800076DA
0x18000758c  cmp     [rsp+268h+var_238], al
0x180007590  jnz     loc_1800076DA
0x180007596  cmp     [rbx+0F68h], al
0x18000759c  jz      short loc_1800075BA
0x18000759e  lea     r8, aCannotDeleteSe; "Cannot delete settings in UseInWinRE mo"...
0x1800075a5  mov     rcx, rbx
0x1800075a8  lea     edx, [rax+2]
0x1800075ab  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800075b0  mov     eax, 80070005h
0x1800075b5  jmp     loc_1800076FA
0x1800075ba  mov     rcx, [rbx+28h]
0x1800075be  call    FileExists
0x1800075c3  mov     r9, [rbx+28h]
0x1800075c7  xor     edx, edx
0x1800075c9  mov     rcx, rbx
0x1800075cc  test    eax, eax
0x1800075ce  jz      short loc_18000760B
0x1800075d0  lea     r8, aDeleteSettingF; "Delete setting file %s"
0x1800075d7  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800075dc  mov     rcx, [rbx+28h]; lpFileName
0x1800075e0  call    cs:__imp_DeleteFileW
0x1800075e6  test    eax, eax
0x1800075e8  jnz     short loc_180007617
0x1800075ea  call    cs:__imp_GetLastError
0x1800075f0  mov     edi, eax
0x1800075f2  test    eax, eax
0x1800075f4  jle     short loc_1800075FF
0x1800075f6  movzx   edi, ax
0x1800075f9  or      edi, 80070000h
0x1800075ff  lea     r8, aFailedToDelete_0; "Failed to delete settings file. Error: "...
0x180007606  jmp     loc_1800074F3
0x18000760b  lea     r8, aSettingFileSDo; "Setting file %s doesn't exist"
0x180007612  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180007617  mov     rcx, [rbx+48h]
0x18000761b  call    FileExists
0x180007620  mov     r9, [rbx+48h]
0x180007624  xor     edx, edx
0x180007626  mov     rcx, rbx
0x180007629  test    eax, eax
0x18000762b  jz      short loc_180007668
0x18000762d  lea     r8, aDeleteBackupSe; "Delete backup settings file %s"
0x180007634  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180007639  mov     rcx, [rbx+48h]; lpFileName
0x18000763d  call    cs:__imp_DeleteFileW
0x180007643  test    eax, eax
0x180007645  jnz     short loc_180007674
0x180007647  call    cs:__imp_GetLastError
0x18000764d  mov     edi, eax
0x18000764f  test    eax, eax
0x180007651  jle     short loc_18000765C
0x180007653  movzx   edi, ax
0x180007656  or      edi, 80070000h
0x18000765c  lea     r8, aFailedToDelete; "Failed to delete backup settings file. "...
0x180007663  jmp     loc_1800074F3
0x180007668  lea     r8, aBackupSettingF; "Backup setting file %s doesn't exist"
0x18000766f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180007674  mov     rcx, [rbx+68h]
0x180007678  call    FileExists
0x18000767d  mov     r9, [rbx+68h]
0x180007681  xor     edx, edx
0x180007683  mov     rcx, rbx
0x180007686  test    eax, eax
0x180007688  jz      short loc_1800076C9
0x18000768a  lea     r8, aDeleteWifiSett; "Delete wifi settings file %s"
0x180007691  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180007696  mov     rcx, [rbx+68h]; lpFileName
0x18000769a  call    cs:__imp_DeleteFileW
0x1800076a0  test    eax, eax
0x1800076a2  jnz     loc_180007503
0x1800076a8  call    cs:__imp_GetLastError
0x1800076ae  mov     edi, eax
0x1800076b0  test    eax, eax
0x1800076b2  jle     short loc_1800076BD
0x1800076b4  movzx   edi, ax
0x1800076b7  or      edi, 80070000h
0x1800076bd  lea     r8, aFailedToDelete_2; "Failed to delete wifi settings file. Er"...
0x1800076c4  jmp     loc_1800074F3
0x1800076c9  lea     r8, aWifiSettingFil; "WiFi setting file %s doesn't exist"
0x1800076d0  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800076d5  jmp     loc_180007503
0x1800076da  lea     r8, aManagedSetting; "Managed settings are present, we will c"...
0x1800076e1  xor     edx, edx
0x1800076e3  mov     rcx, rbx
0x1800076e6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800076eb  mov     rax, [rbx]
0x1800076ee  mov     rcx, rbx
0x1800076f1  mov     rax, [rax+58h]
0x1800076f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076fa  mov     rcx, [rsp+268h+var_18]
0x180007702  xor     rcx, rsp; StackCookie
0x180007705  call    __security_check_cookie
0x18000770a  mov     rbx, [rsp+268h+arg_8]
0x180007712  add     rsp, 260h
0x180007719  pop     rdi
0x18000771a  retn
```
