# SrSettings::CSrSettings::DeleteSettings(void)

- ea: `0x180047080`
- end: `0x18004730b`
- name: `?DeleteSettings@CSrSettings@SrSettings@@UEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(const WCHAR **this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180006120`
- `0x18001efcc`
- `0x180047080`
- `0x18004c0e8`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800471da`
- `KERNEL32!GetLastError` at `0x180047237`
- `KERNEL32!GetLastError` at `0x180047298`
- `KERNEL32!GetLastError` at `0x1800471da`
- `KERNEL32!GetLastError` at `0x180047237`
- `KERNEL32!GetLastError` at `0x180047298`
- `KERNEL32!GetPrivateProfileStringW` at `0x18004713e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18004716e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18004713e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18004716e`
- `KERNEL32!DeleteFileW` at `0x1800471d0`
- `KERNEL32!DeleteFileW` at `0x18004722d`
- `KERNEL32!DeleteFileW` at `0x18004728a`
- `KERNEL32!DeleteFileW` at `0x1800471d0`
- `KERNEL32!DeleteFileW` at `0x18004722d`
- `KERNEL32!DeleteFileW` at `0x18004728a`

## string_xrefs

- `0x18004721d`: `Delete backup settings file %s`
- `0x18004724c`: `Failed to delete backup settings file. Error: 0x%08x`
- `0x18004718e`: `Cannot delete settings in UseInWinRE mode`
- `0x1800471c0`: `Delete setting file %s`
- `0x1800471ef`: `Failed to delete settings file. Error: 0x%08x`
- `0x18004727a`: `Delete wifi settings file %s`
- `0x1800472ad`: `Failed to delete wifi settings file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::DeleteSettings(const WCHAR **this)
{
  const WCHAR *v2; // rax
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
  v2 = *this;
  v18[0] = 0;
  v17 = 0;
  v3 = (*((__int64 (__fastcall **)(const WCHAR **, _BYTE *, char *))v2 + 17))(this, v18, &v17);
  if ( (v3 & 0x80000000) != 0 )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to query WiFi settings. Error: 0x%08x", v3);
    return v3;
  }
  memset_0(ReturnedString, 0, 0x208u);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl'::`2'::impl);
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
0x180047080  mov     [rsp+arg_8], rbx
0x180047085  push    rdi
0x180047086  sub     rsp, 260h
0x18004708d  mov     rax, cs:__security_cookie
0x180047094  xor     rax, rsp
0x180047097  mov     [rsp+268h+var_18], rax
0x18004709f  lea     r8, aCheckingIfMana; "Checking if managed settings are presen"...
0x1800470a6  xor     edx, edx
0x1800470a8  mov     rbx, rcx
0x1800470ab  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800470b0  mov     rax, [rbx]
0x1800470b3  lea     r8, [rsp+268h+var_238]
0x1800470b8  lea     rdx, [rsp+268h+var_237]
0x1800470bd  mov     [rsp+268h+var_237], 0
0x1800470c2  mov     rcx, rbx
0x1800470c5  mov     [rsp+268h+var_238], 0
0x1800470ca  mov     rax, [rax+88h]
0x1800470d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470d6  mov     edi, eax
0x1800470d8  test    eax, eax
0x1800470da  jns     short loc_1800470FA
0x1800470dc  lea     r8, aFailedToQueryW_0; "Failed to query WiFi settings. Error: 0"...
0x1800470e3  mov     r9d, edi
0x1800470e6  mov     edx, 2
0x1800470eb  mov     rcx, rbx
0x1800470ee  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800470f3  mov     eax, edi
0x1800470f5  jmp     loc_1800472EA
0x1800470fa  xor     edx, edx; Val
0x1800470fc  lea     rcx, [rsp+268h+ReturnedString]; void *
0x180047101  mov     r8d, 208h; Size
0x180047107  call    memset_0
0x18004710c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl(void)'::`2'::impl
0x180047113  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)
0x180047118  mov     rcx, [rbx+28h]
0x18004711c  lea     r9, [rsp+268h+ReturnedString]; lpReturnedString
0x180047121  mov     [rsp+268h+lpFileName], rcx; lpFileName
0x180047126  xor     r8d, r8d; lpDefault
0x180047129  xor     edx, edx; lpKeyName
0x18004712b  mov     [rsp+268h+nSize], 104h; nSize
0x180047133  lea     rcx, aManagedsetting_0; "ManagedSettings"
0x18004713a  test    al, al
0x18004713c  jz      short loc_18004716E
0x18004713e  call    cs:__imp_GetPrivateProfileStringW
0x180047144  test    eax, eax
0x180047146  jnz     loc_1800472CA
0x18004714c  mov     rax, [rbx+28h]
0x180047150  lea     r9, [rsp+268h+ReturnedString]; lpReturnedString
0x180047155  xor     r8d, r8d; lpDefault
0x180047158  mov     [rsp+268h+lpFileName], rax; lpFileName
0x18004715d  mov     [rsp+268h+nSize], 104h; nSize
0x180047165  lea     rcx, aManagedsetting; "ManagedSettings_GPO"
0x18004716c  xor     edx, edx; lpKeyName
0x18004716e  call    cs:__imp_GetPrivateProfileStringW
0x180047174  test    eax, eax
0x180047176  jnz     loc_1800472CA
0x18004717c  cmp     [rsp+268h+var_238], al
0x180047180  jnz     loc_1800472CA
0x180047186  cmp     [rbx+0F68h], al
0x18004718c  jz      short loc_1800471AA
0x18004718e  lea     r8, aCannotDeleteSe; "Cannot delete settings in UseInWinRE mo"...
0x180047195  mov     rcx, rbx
0x180047198  lea     edx, [rax+2]
0x18004719b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800471a0  mov     eax, 80070005h
0x1800471a5  jmp     loc_1800472EA
0x1800471aa  mov     rcx, [rbx+28h]
0x1800471ae  call    FileExists
0x1800471b3  mov     r9, [rbx+28h]
0x1800471b7  xor     edx, edx
0x1800471b9  mov     rcx, rbx
0x1800471bc  test    eax, eax
0x1800471be  jz      short loc_1800471FB
0x1800471c0  lea     r8, aDeleteSettingF; "Delete setting file %s"
0x1800471c7  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800471cc  mov     rcx, [rbx+28h]; lpFileName
0x1800471d0  call    cs:__imp_DeleteFileW
0x1800471d6  test    eax, eax
0x1800471d8  jnz     short loc_180047207
0x1800471da  call    cs:__imp_GetLastError
0x1800471e0  mov     edi, eax
0x1800471e2  test    eax, eax
0x1800471e4  jle     short loc_1800471EF
0x1800471e6  movzx   edi, ax
0x1800471e9  or      edi, 80070000h
0x1800471ef  lea     r8, aFailedToDelete_0; "Failed to delete settings file. Error: "...
0x1800471f6  jmp     loc_1800470E3
0x1800471fb  lea     r8, aSettingFileSDo; "Setting file %s doesn't exist"
0x180047202  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180047207  mov     rcx, [rbx+48h]
0x18004720b  call    FileExists
0x180047210  mov     r9, [rbx+48h]
0x180047214  xor     edx, edx
0x180047216  mov     rcx, rbx
0x180047219  test    eax, eax
0x18004721b  jz      short loc_180047258
0x18004721d  lea     r8, aDeleteBackupSe; "Delete backup settings file %s"
0x180047224  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180047229  mov     rcx, [rbx+48h]; lpFileName
0x18004722d  call    cs:__imp_DeleteFileW
0x180047233  test    eax, eax
0x180047235  jnz     short loc_180047264
0x180047237  call    cs:__imp_GetLastError
0x18004723d  mov     edi, eax
0x18004723f  test    eax, eax
0x180047241  jle     short loc_18004724C
0x180047243  movzx   edi, ax
0x180047246  or      edi, 80070000h
0x18004724c  lea     r8, aFailedToDelete; "Failed to delete backup settings file. "...
0x180047253  jmp     loc_1800470E3
0x180047258  lea     r8, aBackupSettingF; "Backup setting file %s doesn't exist"
0x18004725f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180047264  mov     rcx, [rbx+68h]
0x180047268  call    FileExists
0x18004726d  mov     r9, [rbx+68h]
0x180047271  xor     edx, edx
0x180047273  mov     rcx, rbx
0x180047276  test    eax, eax
0x180047278  jz      short loc_1800472B9
0x18004727a  lea     r8, aDeleteWifiSett; "Delete wifi settings file %s"
0x180047281  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180047286  mov     rcx, [rbx+68h]; lpFileName
0x18004728a  call    cs:__imp_DeleteFileW
0x180047290  test    eax, eax
0x180047292  jnz     loc_1800470F3
0x180047298  call    cs:__imp_GetLastError
0x18004729e  mov     edi, eax
0x1800472a0  test    eax, eax
0x1800472a2  jle     short loc_1800472AD
0x1800472a4  movzx   edi, ax
0x1800472a7  or      edi, 80070000h
0x1800472ad  lea     r8, aFailedToDelete_9; "Failed to delete wifi settings file. Er"...
0x1800472b4  jmp     loc_1800470E3
0x1800472b9  lea     r8, aWifiSettingFil; "WiFi setting file %s doesn't exist"
0x1800472c0  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800472c5  jmp     loc_1800470F3
0x1800472ca  lea     r8, aManagedSetting; "Managed settings are present, we will c"...
0x1800472d1  xor     edx, edx
0x1800472d3  mov     rcx, rbx
0x1800472d6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800472db  mov     rax, [rbx]
0x1800472de  mov     rcx, rbx
0x1800472e1  mov     rax, [rax+58h]
0x1800472e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ea  mov     rcx, [rsp+268h+var_18]
0x1800472f2  xor     rcx, rsp; StackCookie
0x1800472f5  call    __security_check_cookie
0x1800472fa  mov     rbx, [rsp+268h+arg_8]
0x180047302  add     rsp, 260h
0x180047309  pop     rdi
0x18004730a  retn
```
