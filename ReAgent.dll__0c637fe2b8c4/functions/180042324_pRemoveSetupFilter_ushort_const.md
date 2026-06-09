# pRemoveSetupFilter(ushort const *)

- ea: `0x180042324`
- end: `0x1800427f5`
- name: `?pRemoveSetupFilter@@YAHPEBG@Z`
- size: `1233`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180042b6c`

## callees

- `0x1800059fc`
- `0x180005c48`
- `0x180007554`
- `0x1800075ec`
- `0x180007838`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180042324`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800424f7`
- `KERNEL32!GetLastError` at `0x1800425bf`
- `KERNEL32!GetLastError` at `0x1800426ba`
- `KERNEL32!GetLastError` at `0x18004273d`
- `KERNEL32!GetLastError` at `0x180042765`
- `KERNEL32!GetLastError` at `0x1800424f7`
- `KERNEL32!GetLastError` at `0x1800425bf`
- `KERNEL32!GetLastError` at `0x1800426ba`
- `KERNEL32!GetLastError` at `0x18004273d`
- `KERNEL32!GetLastError` at `0x180042765`
- `KERNEL32!SetLastError` at `0x1800425a6`
- `KERNEL32!SetLastError` at `0x1800425b9`
- `KERNEL32!SetLastError` at `0x1800425a6`
- `KERNEL32!SetLastError` at `0x1800425b9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800424bd`
- `ADVAPI32!RegOpenKeyExW` at `0x180042561`
- `ADVAPI32!RegOpenKeyExW` at `0x1800424bd`
- `ADVAPI32!RegOpenKeyExW` at `0x180042561`
- `ADVAPI32!RegDeleteTreeW` at `0x180042574`
- `ADVAPI32!RegDeleteTreeW` at `0x180042574`
- `ADVAPI32!RegDeleteKeyExW` at `0x18004259c`
- `ADVAPI32!RegDeleteKeyExW` at `0x18004259c`
- `ADVAPI32!RegCloseKey` at `0x180042581`
- `ADVAPI32!RegCloseKey` at `0x1800427a8`
- `ADVAPI32!RegCloseKey` at `0x180042581`
- `ADVAPI32!RegCloseKey` at `0x1800427a8`
- `ADVAPI32!RegUnLoadKeyW` at `0x1800427c9`
- `ADVAPI32!RegUnLoadKeyW` at `0x1800427c9`
- `ADVAPI32!RegLoadKeyW` at `0x18004246b`
- `ADVAPI32!RegLoadKeyW` at `0x18004246b`

## string_xrefs

- `0x1800423f9`: `WINDOWS\System32\config\SYSTEM`
- `0x18004278d`: `RemoveSetupFilter: AppendPath (1) failed. Error: 0x%x.`
- `0x18004247f`: `RemoveSetupFilter: RegLoadKey %s failed. Error: 0x%x.`
- `0x1800424c7`: `RemoveSetupFilter: RegOpenKeyEx failed. Error: 0x%x.`
- `0x1800424fd`: `RemoveSetupFilter: Failed to get the current control set. Error: 0x%08X`
- `0x180042509`: `ControlSet%03u\Services\WinSetupBoot`
- `0x180042522`: `RemoveSetupFilter: Failed to create WinSetupBoot service key string. HRESULT: 0x%x.`
- `0x1800425d0`: `RemoveSetupFilter: Failed to delete registry tree HKLM\SYSTEM\%s`
- `0x180042638`: `WINDOWS\System32\drivers\WinSetupBoot.sys`
- `0x180042698`: `RemoveSetupFilter: AppendPath (2) failed. Error: 0x%x.`
- `0x1800426cb`: `RemoveSetupFilter: Failed to delete driver file %s`
- `0x1800426f9`: `RemoveSetupFilter: Failed to create control key string. HRESULT: 0x%x.`
- `0x180042746`: `RemoveSetupFilter: Cannot set BootDriverFlags value. Error: 0x%08X`
- `0x18004276b`: `RemoveSetupFilter: Failed to remove backup BootDriverFlags. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall pRemoveSetupFilter(const unsigned __int16 *a1)
{
  unsigned int v2; // r13d
  int v3; // edi
  int v4; // eax
  unsigned __int16 v5; // bx
  const unsigned __int16 *v6; // r12
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int LastError; // eax
  const wchar_t *v13; // rdx
  unsigned int Dword; // eax
  unsigned int v15; // r15d
  HKEY v16; // rsi
  LSTATUS v17; // edi
  LSTATUS v18; // eax
  int v19; // edi
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  int v23; // r8d
  int v24; // r9d
  DWORD v25; // eax
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v29[28]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v31; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[606]; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR File; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v34[606]; // [rsp+332h] [rbp+232h] BYREF

  File = 0;
  v2 = 0;
  memset_0(v34, 0, 0x25Au);
  hKey = 0;
  v31 = 0;
  v3 = 0;
  memset_0(v32, 0, 0x25Au);
  phkResult = 0;
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_63;
  }
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)&phkResult);
  v5 = v4;
  v6 = L"%s\\%s";
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 14;
LABEL_13:
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v4);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  if ( !phkResult || (v9 = L"%s\\%s", a1[(_QWORD)phkResult - 1] == 92) )
    v9 = L"%s%s";
  v4 = StringCchPrintfW(&File, 0x12Eu, v9, a1, L"WINDOWS\\System32\\config\\SYSTEM");
  v5 = v4;
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
      goto LABEL_13;
    }
LABEL_14:
    v10 = v5;
    if ( !v5 )
      goto LABEL_15;
LABEL_63:
    v13 = L"RemoveSetupFilter: AppendPath (1) failed. Error: 0x%x.";
    goto LABEL_64;
  }
LABEL_15:
  v11 = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM", &File);
  if ( v11 )
  {
    UnattendLogW(1, L"RemoveSetupFilter: RegLoadKey %s failed. Error: 0x%x.", L"$OFFLINE$SYSTEM", v11);
    goto LABEL_65;
  }
  v3 = 1;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM", 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    Dword = RegGetDword(hKey, L"Select", L"Current");
    v15 = Dword;
    if ( !Dword )
    {
      LastError = GetLastError();
      v13 = L"RemoveSetupFilter: Failed to get the current control set. Error: 0x%08X";
      goto LABEL_19;
    }
    LastError = StringCchPrintfW(SubKey, 0x24u, L"ControlSet%03u\\Services\\WinSetupBoot", Dword);
    if ( LastError )
    {
      v13 = L"RemoveSetupFilter: Failed to create WinSetupBoot service key string. HRESULT: 0x%x.";
      goto LABEL_19;
    }
    v16 = hKey;
    phkResult = 0;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL && SubKey[0] )
    {
      v17 = RegOpenKeyExW(hKey, SubKey, 0, 0x2000000u, &phkResult);
      if ( !v17 )
      {
        v17 = RegDeleteTreeW(phkResult, 0);
        v18 = RegCloseKey(phkResult);
        if ( !v17 )
        {
          if ( !v18 )
            v18 = RegDeleteKeyExW(v16, SubKey, 0, 0);
          v17 = v18;
        }
      }
      SetLastError(v17);
      if ( !v17 )
        goto LABEL_36;
      v3 = 1;
    }
    else
    {
      SetLastError(0x57u);
    }
    if ( GetLastError() != 2 )
    {
      UnattendLogW(1, L"RemoveSetupFilter: Failed to delete registry tree HKLM\\SYSTEM\\%s", SubKey);
      goto LABEL_65;
    }
LABEL_36:
    phkResult = 0;
    v19 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)&phkResult);
    if ( v19 >= 0 )
    {
      if ( !phkResult || a1[(_QWORD)phkResult - 1] == 92 )
        v6 = L"%s%s";
      v19 = StringCchPrintfW(&v31, 0x12Eu, v6, a1, L"WINDOWS\\System32\\drivers\\WinSetupBoot.sys");
      if ( v19 >= 0 )
        goto LABEL_51;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v21 = 15;
        goto LABEL_47;
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v21 = 14;
LABEL_47:
        WPP_SF_d(v20[2], v21, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v19);
      }
    }
    if ( (_WORD)v19 )
    {
      UnattendLogW(1, L"RemoveSetupFilter: AppendPath (2) failed. Error: 0x%x.");
      goto LABEL_50;
    }
LABEL_51:
    if ( DeleteFileEx2((__int64)&v31) || GetLastError() == 2 )
    {
      if ( !StringCchPrintfW(v29, 0x16u, L"ControlSet%03u\\Control", v15) )
      {
        v22 = RegGetDword(hKey, v29, L"BootDriverFlags.Bak");
        if ( v22 )
        {
          LODWORD(phkResult) = v22;
          if ( !(unsigned int)RegSetBinEx((int)hKey, (int)v29, v23, v24, (BYTE *)&phkResult) )
          {
            GetLastError();
            UnattendLogW(1, L"RemoveSetupFilter: Cannot set BootDriverFlags value. Error: 0x%08X");
            goto LABEL_50;
          }
          if ( !(unsigned int)RegDelete(hKey, v29) )
          {
            v25 = GetLastError();
            UnattendLogW(2, L"RemoveSetupFilter: Failed to remove backup BootDriverFlags. Error: 0x%08X", v25);
          }
        }
        v2 = 1;
        goto LABEL_50;
      }
      UnattendLogW(1, L"RemoveSetupFilter: Failed to create control key string. HRESULT: 0x%x.");
    }
    else
    {
      UnattendLogW(1, L"RemoveSetupFilter: Failed to delete driver file %s", &v31);
    }
LABEL_50:
    v3 = 1;
    goto LABEL_65;
  }
  v13 = L"RemoveSetupFilter: RegOpenKeyEx failed. Error: 0x%x.";
LABEL_19:
  v10 = LastError;
LABEL_64:
  UnattendLogW(1, v13, v10);
LABEL_65:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM");
  return v2;
}

```

## disassembly

```asm
0x180042324  push    rbp
0x180042326  push    rbx
0x180042327  push    rsi
0x180042328  push    rdi
0x180042329  push    r12
0x18004232b  push    r13
0x18004232d  push    r14
0x18004232f  push    r15
0x180042331  lea     rbp, [rsp-4A8h]
0x180042339  sub     rsp, 5A8h
0x180042340  mov     rax, cs:__security_cookie
0x180042347  xor     rax, rsp
0x18004234a  mov     [rbp+4E0h+var_50], rax
0x180042351  mov     r14, rcx
0x180042354  xor     eax, eax
0x180042356  mov     ebx, 25Ah
0x18004235b  mov     [rbp+4E0h+File], ax
0x180042362  mov     r8d, ebx; Size
0x180042365  lea     rcx, [rbp+4E0h+var_2AE]; void *
0x18004236c  xor     edx, edx; Val
0x18004236e  xor     r13d, r13d
0x180042371  call    memset_0
0x180042376  xor     eax, eax
0x180042378  mov     [rsp+5E0h+hKey], r13
0x18004237d  mov     r8d, ebx; Size
0x180042380  mov     [rbp+4E0h+var_510], ax
0x180042384  xor     edx, edx; Val
0x180042386  lea     rcx, [rbp+4E0h+var_50E]; void *
0x18004238a  xor     edi, edi
0x18004238c  call    memset_0
0x180042391  mov     [rsp+5E0h+var_5A8], rdi
0x180042396  test    r14, r14
0x180042399  jz      loc_180042787
0x18004239f  lea     r8, [rsp+5E0h+var_5A8]; unsigned __int64 *
0x1800423a4  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800423a9  mov     rcx, r14; unsigned __int16 *
0x1800423ac  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800423b1  lea     rsi, WPP_GLOBAL_Control
0x1800423b8  mov     ebx, eax
0x1800423ba  lea     r12, aSS_1; "%s\\%s"
0x1800423c1  test    eax, eax
0x1800423c3  jns     short loc_1800423DC
0x1800423c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423cc  cmp     rcx, rsi
0x1800423cf  jz      short loc_180042449
0x1800423d1  test    byte ptr [rcx+1Ch], 2
0x1800423d5  jz      short loc_180042449
0x1800423d7  lea     edx, [rdi+0Eh]
0x1800423da  jmp     short loc_180042436
0x1800423dc  mov     rax, [rsp+5E0h+var_5A8]
0x1800423e1  test    rax, rax
0x1800423e4  jz      short loc_1800423F2
0x1800423e6  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x1800423ed  mov     r8, r12
0x1800423f0  jnz     short loc_1800423F9
0x1800423f2  lea     r8, aSS_2; "%s%s"
0x1800423f9  lea     rax, aWindowsSystem3; "WINDOWS\\System32\\config\\SYSTEM"
0x180042400  mov     r9, r14
0x180042403  mov     edx, 12Eh; unsigned __int64
0x180042408  mov     [rsp+5E0h+phkResult], rax
0x18004240d  lea     rcx, [rbp+4E0h+File]; unsigned __int16 *
0x180042414  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042419  mov     ebx, eax
0x18004241b  test    eax, eax
0x18004241d  jns     short loc_180042456
0x18004241f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042426  cmp     rcx, rsi
0x180042429  jz      short loc_180042449
0x18004242b  test    byte ptr [rcx+1Ch], 2
0x18004242f  jz      short loc_180042449
0x180042431  mov     edx, 0Fh
0x180042436  mov     rcx, [rcx+10h]
0x18004243a  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180042441  mov     r9d, eax
0x180042444  call    WPP_SF_d
0x180042449  movzx   r8d, bx
0x18004244d  test    r8d, r8d
0x180042450  jnz     loc_18004278D
0x180042456  lea     r8, [rbp+4E0h+File]; lpFile
0x18004245d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042464  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18004246b  call    cs:__imp_RegLoadKeyW
0x180042471  test    eax, eax
0x180042473  jz      short loc_180042495
0x180042475  mov     r9d, eax
0x180042478  lea     r8, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18004247f  lea     rdx, aRemovesetupfil_4; "RemoveSetupFilter: RegLoadKey %s failed"...
0x180042486  mov     ecx, 1
0x18004248b  call    UnattendLogW
0x180042490  jmp     loc_18004279E
0x180042495  lea     rax, [rsp+5E0h+hKey]
0x18004249a  mov     ebx, 1
0x18004249f  mov     r9d, 20019h; samDesired
0x1800424a5  mov     [rsp+5E0h+phkResult], rax; phkResult
0x1800424aa  xor     r8d, r8d; ulOptions
0x1800424ad  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x1800424b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800424bb  mov     edi, ebx
0x1800424bd  call    cs:__imp_RegOpenKeyExW
0x1800424c3  test    eax, eax
0x1800424c5  jz      short loc_1800424D8
0x1800424c7  lea     rdx, aRemovesetupfil_6; "RemoveSetupFilter: RegOpenKeyEx failed."...
0x1800424ce  mov     r8d, eax
0x1800424d1  mov     ecx, ebx
0x1800424d3  jmp     loc_180042799
0x1800424d8  mov     rcx, [rsp+5E0h+hKey]
0x1800424dd  lea     r8, aCurrent; "Current"
0x1800424e4  lea     rdx, aSelect; "Select"
0x1800424eb  call    RegGetDword
0x1800424f0  mov     r15d, eax
0x1800424f3  test    eax, eax
0x1800424f5  jnz     short loc_180042506
0x1800424f7  call    cs:__imp_GetLastError
0x1800424fd  lea     rdx, aRemovesetupfil_2; "RemoveSetupFilter: Failed to get the cu"...
0x180042504  jmp     short loc_1800424CE
0x180042506  mov     r9d, r15d
0x180042509  lea     r8, aControlset03uS; "ControlSet%03u\\Services\\WinSetupBoot"
0x180042510  mov     edx, 24h ; '$'; unsigned __int64
0x180042515  lea     rcx, [rbp+4E0h+SubKey]; unsigned __int16 *
0x180042519  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004251e  test    eax, eax
0x180042520  jz      short loc_18004252B
0x180042522  lea     rdx, aRemovesetupfil_7; "RemoveSetupFilter: Failed to create Win"...
0x180042529  jmp     short loc_1800424CE
0x18004252b  mov     rsi, [rsp+5E0h+hKey]
0x180042530  mov     [rsp+5E0h+var_5A8], r13
0x180042535  lea     rax, [rsi-1]
0x180042539  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004253d  ja      short loc_1800425B4
0x18004253f  xor     eax, eax
0x180042541  cmp     ax, [rbp+4E0h+SubKey]
0x180042545  jz      short loc_1800425B4
0x180042547  lea     rax, [rsp+5E0h+var_5A8]
0x18004254c  mov     r9d, 2000000h; samDesired
0x180042552  xor     r8d, r8d; ulOptions
0x180042555  mov     [rsp+5E0h+phkResult], rax; phkResult
0x18004255a  lea     rdx, [rbp+4E0h+SubKey]; lpSubKey
0x18004255e  mov     rcx, rsi; hKey
0x180042561  call    cs:__imp_RegOpenKeyExW
0x180042567  mov     edi, eax
0x180042569  test    eax, eax
0x18004256b  jnz     short loc_1800425A4
0x18004256d  mov     rcx, [rsp+5E0h+var_5A8]; hKey
0x180042572  xor     edx, edx; lpSubKey
0x180042574  call    cs:__imp_RegDeleteTreeW
0x18004257a  mov     rcx, [rsp+5E0h+var_5A8]; hKey
0x18004257f  mov     edi, eax
0x180042581  call    cs:__imp_RegCloseKey
0x180042587  test    edi, edi
0x180042589  jnz     short loc_1800425A4
0x18004258b  test    eax, eax
0x18004258d  jnz     short loc_1800425A2
0x18004258f  xor     r9d, r9d; Reserved
0x180042592  lea     rdx, [rbp+4E0h+SubKey]; lpSubKey
0x180042596  xor     r8d, r8d; samDesired
0x180042599  mov     rcx, rsi; hKey
0x18004259c  call    cs:__imp_RegDeleteKeyExW
0x1800425a2  mov     edi, eax
0x1800425a4  mov     ecx, edi; dwErrCode
0x1800425a6  call    cs:__imp_SetLastError
0x1800425ac  test    edi, edi
0x1800425ae  jz      short loc_1800425E1
0x1800425b0  mov     edi, ebx
0x1800425b2  jmp     short loc_1800425BF
0x1800425b4  mov     ecx, 57h ; 'W'; dwErrCode
0x1800425b9  call    cs:__imp_SetLastError
0x1800425bf  call    cs:__imp_GetLastError
0x1800425c5  cmp     eax, 2
0x1800425c8  jz      short loc_1800425E1
0x1800425ca  lea     r8, [rbp+4E0h+SubKey]
0x1800425ce  mov     ecx, ebx
0x1800425d0  lea     rdx, aRemovesetupfil_5; "RemoveSetupFilter: Failed to delete reg"...
0x1800425d7  call    UnattendLogW
0x1800425dc  jmp     loc_18004279E
0x1800425e1  lea     r8, [rsp+5E0h+var_5A8]; unsigned __int64 *
0x1800425e6  mov     [rsp+5E0h+var_5A8], r13
0x1800425eb  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800425f0  mov     rcx, r14; unsigned __int16 *
0x1800425f3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800425f8  mov     edi, eax
0x1800425fa  test    eax, eax
0x1800425fc  jns     short loc_18004261E
0x1800425fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180042605  lea     rax, WPP_GLOBAL_Control
0x18004260c  cmp     rcx, rax
0x18004260f  jz      short loc_18004268F
0x180042611  test    byte ptr [rcx+1Ch], 2
0x180042615  jz      short loc_18004268F
0x180042617  mov     edx, 0Eh
0x18004261c  jmp     short loc_18004267C
0x18004261e  mov     rax, [rsp+5E0h+var_5A8]
0x180042623  test    rax, rax
0x180042626  jz      short loc_180042631
0x180042628  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x18004262f  jnz     short loc_180042638
0x180042631  lea     r12, aSS_2; "%s%s"
0x180042638  lea     rax, aWindowsSystem3_1; "WINDOWS\\System32\\drivers\\WinSetupBoo"...
0x18004263f  mov     r9, r14
0x180042642  mov     r8, r12; unsigned __int16 *
0x180042645  mov     [rsp+5E0h+phkResult], rax
0x18004264a  mov     edx, 12Eh; unsigned __int64
0x18004264f  lea     rcx, [rbp+4E0h+var_510]; unsigned __int16 *
0x180042653  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042658  mov     edi, eax
0x18004265a  test    eax, eax
0x18004265c  jns     short loc_1800426AD
0x18004265e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042665  lea     rax, WPP_GLOBAL_Control
0x18004266c  cmp     rcx, rax
0x18004266f  jz      short loc_18004268F
0x180042671  test    byte ptr [rcx+1Ch], 2
0x180042675  jz      short loc_18004268F
0x180042677  mov     edx, 0Fh
0x18004267c  mov     rcx, [rcx+10h]
0x180042680  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180042687  mov     r9d, edi
0x18004268a  call    WPP_SF_d
0x18004268f  movzx   r8d, di
0x180042693  test    r8d, r8d
0x180042696  jz      short loc_1800426AD
0x180042698  lea     rdx, aRemovesetupfil_0; "RemoveSetupFilter: AppendPath (2) faile"...
0x18004269f  mov     ecx, ebx
0x1800426a1  call    UnattendLogW
0x1800426a6  mov     edi, ebx
0x1800426a8  jmp     loc_18004279E
0x1800426ad  lea     rcx, [rbp+4E0h+var_510]
0x1800426b1  call    DeleteFileEx2
0x1800426b6  test    eax, eax
0x1800426b8  jnz     short loc_1800426D9
0x1800426ba  call    cs:__imp_GetLastError
0x1800426c0  cmp     eax, 2
0x1800426c3  jz      short loc_1800426D9
0x1800426c5  lea     r8, [rbp+4E0h+var_510]
0x1800426c9  mov     ecx, ebx
0x1800426cb  lea     rdx, aRemovesetupfil_3; "RemoveSetupFilter: Failed to delete dri"...
0x1800426d2  call    UnattendLogW
0x1800426d7  jmp     short loc_1800426A6
0x1800426d9  mov     r9d, r15d
0x1800426dc  lea     r8, aControlset03uC; "ControlSet%03u\\Control"
0x1800426e3  mov     edx, 16h; unsigned __int64
0x1800426e8  lea     rcx, [rsp+5E0h+var_598]; unsigned __int16 *
0x1800426ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800426f2  test    eax, eax
0x1800426f4  jz      short loc_180042702
0x1800426f6  mov     r8d, eax
0x1800426f9  lea     rdx, aRemovesetupfil_9; "RemoveSetupFilter: Failed to create con"...
0x180042700  jmp     short loc_18004269F
0x180042702  mov     rcx, [rsp+5E0h+hKey]
0x180042707  lea     r8, ValueName; "BootDriverFlags.Bak"
0x18004270e  lea     rdx, [rsp+5E0h+var_598]
0x180042713  call    RegGetDword
0x180042718  test    eax, eax
0x18004271a  jz      short loc_18004277F
0x18004271c  mov     rcx, [rsp+5E0h+hKey]; int
0x180042721  lea     rdx, [rsp+5E0h+var_598]; int
0x180042726  mov     dword ptr [rsp+5E0h+var_5A8], eax
0x18004272a  lea     rax, [rsp+5E0h+var_5A8]
0x18004272f  mov     [rsp+5E0h+phkResult], rax; lpData
0x180042734  call    RegSetBinEx
0x180042739  test    eax, eax
0x18004273b  jnz     short loc_180042752
0x18004273d  call    cs:__imp_GetLastError
0x180042743  mov     r8d, eax
0x180042746  lea     rdx, aRemovesetupfil_1; "RemoveSetupFilter: Cannot set BootDrive"...
0x18004274d  jmp     loc_18004269F
0x180042752  mov     rcx, [rsp+5E0h+hKey]
0x180042757  lea     rdx, [rsp+5E0h+var_598]
0x18004275c  call    RegDelete
0x180042761  test    eax, eax
0x180042763  jnz     short loc_18004277F
0x180042765  call    cs:__imp_GetLastError
0x18004276b  lea     rdx, aRemovesetupfil; "RemoveSetupFilter: Failed to remove bac"...
0x180042772  mov     ecx, 2
0x180042777  mov     r8d, eax
0x18004277a  call    UnattendLogW
0x18004277f  mov     r13d, ebx
0x180042782  jmp     loc_1800426A6
0x180042787  mov     r8d, 57h ; 'W'
0x18004278d  lea     rdx, aRemovesetupfil_8; "RemoveSetupFilter: AppendPath (1) faile"...
0x180042794  mov     ecx, 1
0x180042799  call    UnattendLogW
0x18004279e  mov     rcx, [rsp+5E0h+hKey]; hKey
0x1800427a3  test    rcx, rcx
0x1800427a6  jz      short loc_1800427B7
0x1800427a8  call    cs:__imp_RegCloseKey
0x1800427ae  mov     [rsp+5E0h+hKey], 0
0x1800427b7  test    edi, edi
0x1800427b9  jz      short loc_1800427CF
0x1800427bb  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x1800427c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800427c9  call    cs:__imp_RegUnLoadKeyW
0x1800427cf  mov     eax, r13d
0x1800427d2  mov     rcx, [rbp+4E0h+var_50]
0x1800427d9  xor     rcx, rsp; StackCookie
0x1800427dc  call    __security_check_cookie
0x1800427e1  add     rsp, 5A8h
0x1800427e8  pop     r15
0x1800427ea  pop     r14
0x1800427ec  pop     r13
0x1800427ee  pop     r12
  ... truncated ...
```
