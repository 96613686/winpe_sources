# SrSettings::CSrSettings::GetDefaultValueFromRegistry(SrSettings::DEFAULT_SETTING_VALUE const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800480a8`
- end: `0x1800485b5`
- name: `?GetDefaultValueFromRegistry@CSrSettings@SrSettings@@AEAAJAEBUDEFAULT_SETTING_VALUE@2@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x180046b88`

## callees

- `0x1800480a8`
- `0x1800485bc`
- `0x18004c0e8`
- `0x18004c44c`
- `0x18004c5c8`
- `0x18004c6c8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800481ac`
- `ADVAPI32!RegOpenKeyExW` at `0x180048208`
- `ADVAPI32!RegOpenKeyExW` at `0x1800483fb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800484aa`
- `ADVAPI32!RegOpenKeyExW` at `0x1800481ac`
- `ADVAPI32!RegOpenKeyExW` at `0x180048208`
- `ADVAPI32!RegOpenKeyExW` at `0x1800483fb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800484aa`
- `ADVAPI32!RegCloseKey` at `0x18004854e`
- `ADVAPI32!RegCloseKey` at `0x18004855d`
- `ADVAPI32!RegCloseKey` at `0x18004854e`
- `ADVAPI32!RegCloseKey` at `0x18004855d`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004844c`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004844c`
- `ADVAPI32!RegLoadKeyW` at `0x18004839f`
- `ADVAPI32!RegLoadKeyW` at `0x18004839f`

## string_xrefs

- `0x180048225`: `Failed to open Software hive. Error: 0x%08x`
- `0x180048574`: `No registry key mapping for default value of setting %s`
- `0x1800481c9`: `Failed to open System hive. Error: 0x%08x`
- `0x18004816b`: `Invalid registry hive type %d`
- `0x18004824e`: `Failed to assign target OS path to hive path. Error: 0x%08x`
- `0x180048260`: `\System32\config`
- `0x180048279`: `Failed to append config to hive path. Error: 0x%08x`
- `0x18004828b`: `$SR_Registry$`
- `0x1800482a4`: `Failed to assign SR_ to mount point. Error: 0x%08x`
- `0x180048338`: `Failed to append SOFTWARE to hive path. Error: 0x%08x`
- `0x180048363`: `Failed to append SOFTWARE to mount point. Error: 0x%08x`
- `0x1800482e2`: `Failed to append SYSTEM to hive path. Error: 0x%08x`
- `0x18004830d`: `Failed to append SYSTEM to mount point. Error: 0x%08x`
- `0x18004837c`: `Mounting hive %s to %s`
- `0x18004841c`: `Failed to open loaded hive %s. Error: 0x%08x`
- `0x1800484e2`: `Registry key %s not found`
- `0x1800484d9`: `Failed to open registry key %s. Error: 0x%08x`
- `0x18004852f`: `Registry value %s not found`
- `0x180048515`: `Failed to get registry value %s. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::GetDefaultValueFromRegistry(__int64 a1, _QWORD *a2, __int64 a3)
{
  char v6; // r13
  _WORD *v7; // rcx
  int v8; // r9d
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS KeyW; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v16; // eax
  __int64 v17; // r9
  int RegValue; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-60h]
  PHKEY phkResulta; // [rsp+20h] [rbp-60h]
  signed int v21; // [rsp+28h] [rbp-58h]
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-48h] BYREF
  _WORD v23[8]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFile[2]; // [rsp+58h] [rbp-28h] BYREF
  _WORD v25[12]; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+40h]
  HKEY v28; // [rsp+C8h] [rbp+48h] BYREF

  v27 = a3;
  lpFile[0] = v25;
  lpFile[1] = v25;
  v6 = 0;
  v25[0] = 0;
  lpSubKey[0] = v23;
  lpSubKey[1] = v23;
  v23[0] = 0;
  hKey = 0;
  v28 = 0;
  SrSettings::CSrSettings::Trace(a1, 0, L"Getting default value for setting %s", *a2);
  v7 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  *v7 = 0;
  v8 = *((_DWORD *)a2 + 2);
  if ( v8 && v8 != 3 && a2[2] && a2[3] )
  {
    if ( *(_BYTE *)(a1 + 3946) )
    {
      if ( v8 == 1 )
      {
        v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
        v9 = v11;
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        if ( v9 < 0 )
        {
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open Software hive. Error: 0x%08x", (unsigned int)v9);
          goto LABEL_44;
        }
      }
      else
      {
        if ( v8 != 2 )
        {
LABEL_8:
          SrSettings::CSrSettings::Trace(a1, 2, L"Invalid registry hive type %d");
          v9 = -2147024809;
LABEL_44:
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpSubKey);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpFile);
          return (unsigned int)v9;
        }
        v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0x20019u, &hKey);
        v9 = v10;
        if ( v10 > 0 )
          v9 = (unsigned __int16)v10 | 0x80070000;
        if ( v9 < 0 )
        {
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open System hive. Error: 0x%08x", (unsigned int)v9);
          goto LABEL_44;
        }
      }
    }
    else
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               lpFile,
                               *(_QWORD *)(a1 + 8),
                               (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 1) )
      {
        v9 = -2147024888;
        SrSettings::CSrSettings::Trace(
          a1,
          2,
          L"Failed to assign target OS path to hive path. Error: 0x%08x",
          2147942408LL);
        goto LABEL_44;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               lpFile,
                               L"\\System32\\config",
                               16) )
      {
        v9 = -2147024888;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to append config to hive path. Error: 0x%08x", 2147942408LL);
        goto LABEL_44;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               lpSubKey,
                               L"$SR_Registry$",
                               13) )
      {
        v9 = -2147024888;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to assign SR_ to mount point. Error: 0x%08x", 2147942408LL);
        goto LABEL_44;
      }
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpFile,
                                 L"\\SOFTWARE",
                                 9) )
        {
          v9 = -2147024888;
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to append SOFTWARE to hive path. Error: 0x%08x", 2147942408LL);
          goto LABEL_44;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpSubKey,
                                 L"SOFTWARE",
                                 8) )
        {
          v9 = -2147024888;
          SrSettings::CSrSettings::Trace(
            a1,
            2,
            L"Failed to append SOFTWARE to mount point. Error: 0x%08x",
            2147942408LL);
          goto LABEL_44;
        }
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_8;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpFile,
                                 L"\\SYSTEM",
                                 7) )
        {
          v9 = -2147024888;
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to append SYSTEM to hive path. Error: 0x%08x", 2147942408LL);
          goto LABEL_44;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpSubKey,
                                 L"SYSTEM",
                                 6) )
        {
          v9 = -2147024888;
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to append SYSTEM to mount point. Error: 0x%08x", 2147942408LL);
          goto LABEL_44;
        }
      }
      SrSettings::CSrSettings::Trace(a1, 0, L"Mounting hive %s to %s", lpFile[0], lpSubKey[0]);
      KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0], lpFile[0]);
      v9 = KeyW;
      if ( KeyW > 0 )
        v9 = (unsigned __int16)KeyW | 0x80070000;
      if ( v9 < 0 )
      {
        v21 = v9;
        SrSettings::CSrSettings::Trace(
          a1,
          2,
          L"Failed to load hive %s to %s. Error: 0x%08x",
          lpFile[0],
          lpSubKey[0],
          v21,
          -2);
        goto LABEL_44;
      }
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
      v9 = v13;
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      if ( v9 < 0 )
      {
        LODWORD(phkResult) = v9;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open loaded hive %s. Error: 0x%08x", lpSubKey[0], phkResult);
LABEL_42:
        SrSettings::CSrSettings::Trace(a1, 0, L"Unloading hive %s", lpSubKey[0]);
        v14 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0]);
        if ( v14 < 0 )
        {
          LODWORD(phkResulta) = v14;
          SrSettings::CSrSettings::Trace(a1, 1, L"Failed to unload hive %s. Error: 0x%08x", lpSubKey[0], phkResulta);
        }
        goto LABEL_44;
      }
      v6 = 1;
    }
    v16 = RegOpenKeyExW(hKey, (LPCWSTR)a2[2], 0, 0x20019u, &v28);
    v9 = v16;
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    if ( v9 >= 0 )
    {
      RegValue = SrSettings::CSrSettings::GetRegValue(a1, v28, a2[3], v27);
      v9 = RegValue;
      if ( (unsigned int)(RegValue + 2147024894) > 1 )
      {
        if ( RegValue < 0 )
        {
          LODWORD(phkResulta) = RegValue;
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to get registry value %s. Error: 0x%08x", a2[3], phkResulta);
        }
LABEL_58:
        if ( v28 )
          RegCloseKey(v28);
        if ( hKey )
          RegCloseKey(hKey);
        if ( !v6 )
          goto LABEL_44;
        goto LABEL_42;
      }
      SrSettings::CSrSettings::Trace(a1, 0, L"Registry value %s not found", a2[3]);
    }
    else
    {
      v17 = a2[2];
      if ( (unsigned int)(v9 + 2147024894) > 1 )
      {
        LODWORD(phkResulta) = v9;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open registry key %s. Error: 0x%08x", v17, phkResulta);
        goto LABEL_58;
      }
      SrSettings::CSrSettings::Trace(a1, 0, L"Registry key %s not found", v17);
    }
    v9 = 1;
    goto LABEL_58;
  }
  SrSettings::CSrSettings::Trace(a1, 0, L"No registry key mapping for default value of setting %s", *a2);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpSubKey);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpFile);
  return 1;
}

```

## disassembly

```asm
0x1800480a8  mov     rax, rsp
0x1800480ab  mov     [rax+18h], r8
0x1800480af  push    rbp
0x1800480b0  push    rsi
0x1800480b1  push    rdi
0x1800480b2  push    r12
0x1800480b4  push    r13
0x1800480b6  mov     rbp, rsp
0x1800480b9  sub     rsp, 80h
0x1800480c0  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x1800480c8  mov     [rax+8], rbx
0x1800480cc  mov     rbx, r8
0x1800480cf  mov     rsi, rdx
0x1800480d2  mov     rdi, rcx
0x1800480d5  lea     rax, [rbp+var_18]
0x1800480d9  mov     [rbp+lpFile], rax
0x1800480dd  lea     rax, [rbp+var_18]
0x1800480e1  mov     [rbp+var_20], rax
0x1800480e5  xor     r13d, r13d
0x1800480e8  mov     [rbp+var_18], r13w
0x1800480ed  lea     rax, [rbp+var_38]
0x1800480f1  mov     [rbp+lpSubKey], rax
0x1800480f5  lea     rax, [rbp+var_38]
0x1800480f9  mov     [rbp+var_40], rax
0x1800480fd  mov     [rbp+var_38], r13w
0x180048102  mov     [rbp+hKey], r13
0x180048106  mov     [rbp+arg_18], r13
0x18004810a  mov     r9, [rdx]
0x18004810d  lea     r8, aGettingDefault; "Getting default value for setting %s"
0x180048114  xor     edx, edx
0x180048116  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004811b  mov     rcx, [rbx]
0x18004811e  mov     [rbx+8], rcx
0x180048122  mov     [rcx], r13w
0x180048126  mov     r9d, [rsi+8]
0x18004812a  test    r9d, r9d
0x18004812d  jz      loc_180048571
0x180048133  cmp     r9d, 3
0x180048137  jz      loc_180048571
0x18004813d  cmp     [rsi+10h], r13
0x180048141  jz      loc_180048571
0x180048147  cmp     [rsi+18h], r13
0x18004814b  jz      loc_180048571
0x180048151  cmp     [rdi+0F6Ah], r13b
0x180048158  jz      loc_18004822E
0x18004815e  mov     ecx, r9d
0x180048161  sub     ecx, 1
0x180048164  jz      short loc_1800481E5
0x180048166  cmp     ecx, 1
0x180048169  jz      short loc_180048189
0x18004816b  lea     r8, aInvalidRegistr; "Invalid registry hive type %d"
0x180048172  mov     edx, 2
0x180048177  mov     rcx, rdi
0x18004817a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004817f  mov     ebx, 80070057h
0x180048184  jmp     loc_180048473
0x180048189  lea     rax, [rbp+hKey]
0x18004818d  mov     [rsp+80h+phkResult], rax; phkResult
0x180048192  mov     r9d, 20019h; samDesired
0x180048198  xor     r8d, r8d; ulOptions
0x18004819b  lea     rdx, aSystem_0; "System"
0x1800481a2  mov     r12, 0FFFFFFFF80000002h
0x1800481a9  mov     rcx, r12; hKey
0x1800481ac  call    cs:__imp_RegOpenKeyExW
0x1800481b2  mov     ebx, eax
0x1800481b4  test    eax, eax
0x1800481b6  jle     short loc_1800481C1
0x1800481b8  movzx   ebx, ax
0x1800481bb  or      ebx, 80070000h
0x1800481c1  test    ebx, ebx
0x1800481c3  jns     loc_180048490
0x1800481c9  lea     r8, aFailedToOpenSy; "Failed to open System hive. Error: 0x%0"...
0x1800481d0  mov     r9d, ebx
0x1800481d3  mov     edx, 2
0x1800481d8  mov     rcx, rdi
0x1800481db  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800481e0  jmp     loc_180048473
0x1800481e5  lea     rax, [rbp+hKey]
0x1800481e9  mov     [rsp+80h+phkResult], rax; phkResult
0x1800481ee  mov     r9d, 20019h; samDesired
0x1800481f4  xor     r8d, r8d; ulOptions
0x1800481f7  lea     rdx, aSoftware_1; "Software"
0x1800481fe  mov     r12, 0FFFFFFFF80000002h
0x180048205  mov     rcx, r12; hKey
0x180048208  call    cs:__imp_RegOpenKeyExW
0x18004820e  mov     ebx, eax
0x180048210  test    eax, eax
0x180048212  jle     short loc_18004821D
0x180048214  movzx   ebx, ax
0x180048217  or      ebx, 80070000h
0x18004821d  test    ebx, ebx
0x18004821f  jns     loc_180048490
0x180048225  lea     r8, aFailedToOpenSo; "Failed to open Software hive. Error: 0x"...
0x18004822c  jmp     short loc_1800481D0
0x18004822e  mov     rdx, [rdi+8]
0x180048232  mov     r8, [rdi+10h]
0x180048236  sub     r8, rdx
0x180048239  sar     r8, 1
0x18004823c  lea     rcx, [rbp+lpFile]
0x180048240  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048245  test    al, al
0x180048247  jnz     short loc_18004825A
0x180048249  mov     ebx, 80070008h
0x18004824e  lea     r8, aFailedToAssign_2; "Failed to assign target OS path to hive"...
0x180048255  jmp     loc_1800481D0
0x18004825a  mov     r8d, 10h
0x180048260  lea     rdx, aSystem32Config_2; "\\System32\\config"
0x180048267  lea     rcx, [rbp+lpFile]
0x18004826b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180048270  test    al, al
0x180048272  jnz     short loc_180048285
0x180048274  mov     ebx, 80070008h
0x180048279  lea     r8, aFailedToAppend_3; "Failed to append config to hive path. E"...
0x180048280  jmp     loc_1800481D0
0x180048285  mov     r8d, 0Dh
0x18004828b  lea     rdx, aSrRegistry; "$SR_Registry$"
0x180048292  lea     rcx, [rbp+lpSubKey]
0x180048296  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004829b  test    al, al
0x18004829d  jnz     short loc_1800482B0
0x18004829f  mov     ebx, 80070008h
0x1800482a4  lea     r8, aFailedToAssign_6; "Failed to assign SR_ to mount point. Er"...
0x1800482ab  jmp     loc_1800481D0
0x1800482b0  mov     r9d, [rsi+8]
0x1800482b4  mov     ecx, r9d
0x1800482b7  sub     ecx, 1
0x1800482ba  jz      short loc_180048319
0x1800482bc  cmp     ecx, 1
0x1800482bf  jnz     loc_18004816B
0x1800482c5  lea     r8d, [rcx+6]
0x1800482c9  lea     rdx, aSystem_2; "\\SYSTEM"
0x1800482d0  lea     rcx, [rbp+lpFile]
0x1800482d4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800482d9  test    al, al
0x1800482db  jnz     short loc_1800482EE
0x1800482dd  mov     ebx, 80070008h
0x1800482e2  lea     r8, aFailedToAppend_0; "Failed to append SYSTEM to hive path. E"...
0x1800482e9  jmp     loc_1800481D0
0x1800482ee  mov     r8d, 6
0x1800482f4  lea     rdx, aSystem; "SYSTEM"
0x1800482fb  lea     rcx, [rbp+lpSubKey]
0x1800482ff  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180048304  test    al, al
0x180048306  jnz     short loc_18004836F
0x180048308  mov     ebx, 80070008h
0x18004830d  lea     r8, aFailedToAppend_15; "Failed to append SYSTEM to mount point."...
0x180048314  jmp     loc_1800481D0
0x180048319  mov     r8d, 9
0x18004831f  lea     rdx, aSoftware_0; "\\SOFTWARE"
0x180048326  lea     rcx, [rbp+lpFile]
0x18004832a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004832f  test    al, al
0x180048331  jnz     short loc_180048344
0x180048333  mov     ebx, 80070008h
0x180048338  lea     r8, aFailedToAppend_4; "Failed to append SOFTWARE to hive path."...
0x18004833f  jmp     loc_1800481D0
0x180048344  mov     r8d, 8
0x18004834a  lea     rdx, aSoftware; "SOFTWARE"
0x180048351  lea     rcx, [rbp+lpSubKey]
0x180048355  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004835a  test    al, al
0x18004835c  jnz     short loc_18004836F
0x18004835e  mov     ebx, 80070008h
0x180048363  lea     r8, aFailedToAppend; "Failed to append SOFTWARE to mount poin"...
0x18004836a  jmp     loc_1800481D0
0x18004836f  mov     rax, [rbp+lpSubKey]
0x180048373  mov     [rsp+80h+phkResult], rax
0x180048378  mov     r9, [rbp+lpFile]
0x18004837c  lea     r8, aMountingHiveST; "Mounting hive %s to %s"
0x180048383  xor     edx, edx
0x180048385  mov     rcx, rdi
0x180048388  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004838d  mov     r8, [rbp+lpFile]; lpFile
0x180048391  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180048395  mov     r12, 0FFFFFFFF80000002h
0x18004839c  mov     rcx, r12; hKey
0x18004839f  call    cs:__imp_RegLoadKeyW
0x1800483a5  mov     ebx, eax
0x1800483a7  test    eax, eax
0x1800483a9  jle     short loc_1800483B4
0x1800483ab  movzx   ebx, ax
0x1800483ae  or      ebx, 80070000h
0x1800483b4  test    ebx, ebx
0x1800483b6  jns     short loc_1800483E2
0x1800483b8  mov     [rsp+80h+var_58], ebx
0x1800483bc  mov     rax, [rbp+lpSubKey]
0x1800483c0  mov     [rsp+80h+phkResult], rax
0x1800483c5  mov     r9, [rbp+lpFile]
0x1800483c9  lea     r8, aFailedToLoadHi; "Failed to load hive %s to %s. Error: 0x"...
0x1800483d0  mov     edx, 2
0x1800483d5  mov     rcx, rdi
0x1800483d8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800483dd  jmp     loc_180048473
0x1800483e2  lea     rax, [rbp+hKey]
0x1800483e6  mov     [rsp+80h+phkResult], rax; phkResult
0x1800483eb  mov     r9d, 20019h; samDesired
0x1800483f1  xor     r8d, r8d; ulOptions
0x1800483f4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800483f8  mov     rcx, r12; hKey
0x1800483fb  call    cs:__imp_RegOpenKeyExW
0x180048401  mov     ebx, eax
0x180048403  test    eax, eax
0x180048405  jle     short loc_180048410
0x180048407  movzx   ebx, ax
0x18004840a  or      ebx, 80070000h
0x180048410  test    ebx, ebx
0x180048412  jns     short loc_18004848D
0x180048414  mov     dword ptr [rsp+80h+phkResult], ebx
0x180048418  mov     r9, [rbp+lpSubKey]
0x18004841c  lea     r8, aFailedToOpenLo_1; "Failed to open loaded hive %s. Error: 0"...
0x180048423  mov     edx, 2
0x180048428  mov     rcx, rdi
0x18004842b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048430  mov     r9, [rbp+lpSubKey]
0x180048434  lea     r8, aUnloadingHiveS; "Unloading hive %s"
0x18004843b  xor     edx, edx
0x18004843d  mov     rcx, rdi
0x180048440  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048445  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180048449  mov     rcx, r12; hKey
0x18004844c  call    cs:__imp_RegUnLoadKeyW
0x180048452  test    eax, eax
0x180048454  jns     short loc_180048473
0x180048456  mov     dword ptr [rsp+80h+phkResult], eax
0x18004845a  mov     r9, [rbp+lpSubKey]
0x18004845e  lea     r8, aFailedToUnload; "Failed to unload hive %s. Error: 0x%08x"
0x180048465  mov     edx, 1
0x18004846a  mov     rcx, rdi
0x18004846d  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048472  nop
0x180048473  lea     rcx, [rbp+lpSubKey]
0x180048477  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004847c  nop
0x18004847d  lea     rcx, [rbp+lpFile]
0x180048481  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180048486  mov     eax, ebx
0x180048488  jmp     loc_18004859E
0x18004848d  mov     r13b, 1
0x180048490  lea     rax, [rbp+arg_18]
0x180048494  mov     [rsp+80h+phkResult], rax; phkResult
0x180048499  mov     r9d, 20019h; samDesired
0x18004849f  xor     r8d, r8d; ulOptions
0x1800484a2  mov     rdx, [rsi+10h]; lpSubKey
0x1800484a6  mov     rcx, [rbp+hKey]; hKey
0x1800484aa  call    cs:__imp_RegOpenKeyExW
0x1800484b0  mov     ebx, eax
0x1800484b2  test    eax, eax
0x1800484b4  jle     short loc_1800484BF
0x1800484b6  movzx   ebx, ax
0x1800484b9  or      ebx, 80070000h
0x1800484bf  mov     rcx, rdi
0x1800484c2  test    ebx, ebx
0x1800484c4  jns     short loc_1800484EB
0x1800484c6  lea     eax, [rbx+7FF8FFFEh]
0x1800484cc  mov     r9, [rsi+10h]
0x1800484d0  cmp     eax, 1
0x1800484d3  jbe     short loc_1800484E2
0x1800484d5  mov     dword ptr [rsp+80h+phkResult], ebx
0x1800484d9  lea     r8, aFailedToOpenRe_2; "Failed to open registry key %s. Error: "...
0x1800484e0  jmp     short loc_18004851F
0x1800484e2  lea     r8, aRegistryKeySNo; "Registry key %s not found"
0x1800484e9  jmp     short loc_180048539
0x1800484eb  mov     r9, [rbp+arg_10]
0x1800484ef  mov     r8, [rsi+18h]
0x1800484f3  mov     rdx, [rbp+arg_18]
0x1800484f7  call    ?GetRegValue@CSrSettings@SrSettings@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetRegValue(HKEY__ *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800484fc  mov     ebx, eax
0x1800484fe  lea     ecx, [rax+7FF8FFFEh]
0x180048504  cmp     ecx, 1
0x180048507  jbe     short loc_18004852B
0x180048509  test    eax, eax
0x18004850b  jns     short loc_180048545
0x18004850d  mov     dword ptr [rsp+80h+phkResult], eax
0x180048511  mov     r9, [rsi+18h]
0x180048515  lea     r8, aFailedToGetReg; "Failed to get registry value %s. Error:"...
0x18004851c  mov     rcx, rdi
0x18004851f  mov     edx, 2
0x180048524  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048529  jmp     short loc_180048545
0x18004852b  mov     r9, [rsi+18h]
0x18004852f  lea     r8, aRegistryValueS; "Registry value %s not found"
0x180048536  mov     rcx, rdi
0x180048539  xor     edx, edx
0x18004853b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048540  mov     ebx, 1
0x180048545  mov     rcx, [rbp+arg_18]; hKey
0x180048549  test    rcx, rcx
0x18004854c  jz      short loc_180048554
0x18004854e  call    cs:__imp_RegCloseKey
0x180048554  mov     rcx, [rbp+hKey]; hKey
0x180048558  test    rcx, rcx
0x18004855b  jz      short loc_180048563
0x18004855d  call    cs:__imp_RegCloseKey
0x180048563  test    r13b, r13b
0x180048566  jz      loc_180048473
0x18004856c  jmp     loc_180048430
0x180048571  mov     r9, [rsi]
0x180048574  lea     r8, aNoRegistryKeyM; "No registry key mapping for default val"...
0x18004857b  xor     edx, edx
0x18004857d  mov     rcx, rdi
  ... truncated ...
```
