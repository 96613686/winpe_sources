# SrSettings::CSrSettings::GetDefaultValueFromRegistry(SrSettings::DEFAULT_SETTING_VALUE const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180009494`
- end: `0x180009a18`
- name: `?GetDefaultValueFromRegistry@CSrSettings@SrSettings@@AEAAJAEBUDEFAULT_SETTING_VALUE@2@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180006c00`

## callees

- `0x180002178`
- `0x180009494`
- `0x180009ec8`
- `0x180010a0c`
- `0x180011b60`
- `0x180011c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099a2`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800098a3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800098a3`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800097f6`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800097f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009573`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009852`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009573`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009852`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098ef`

## string_xrefs

- `0x1800095d9`: `Failed to open Software hive. Error: 0x%08x`
- `0x1800099b9`: `No registry key mapping for default value of setting %s`
- `0x180009590`: `Failed to open System hive. Error: 0x%08x`
- `0x1800096ad`: `Invalid registry hive type %d`
- `0x180009646`: `Failed to assign target OS path to hive path. Error: 0x%08x`
- `0x180009652`: `\System32\config`
- `0x180009666`: `Failed to append config to hive path. Error: 0x%08x`
- `0x180009678`: `$SR_Registry$`
- `0x18000968c`: `Failed to assign SR_ to mount point. Error: 0x%08x`
- `0x180009751`: `Failed to append SOFTWARE to hive path. Error: 0x%08x`
- `0x18000976e`: `Failed to append SOFTWARE to mount point. Error: 0x%08x`
- `0x180009713`: `Failed to append SYSTEM to hive path. Error: 0x%08x`
- `0x180009734`: `Failed to append SYSTEM to mount point. Error: 0x%08x`
- `0x1800097d3`: `Mounting hive %s to %s`
- `0x180009873`: `Failed to open loaded hive %s. Error: 0x%08x`
- `0x180009927`: `Registry key %s not found`
- `0x18000991e`: `Failed to open registry key %s. Error: 0x%08x`
- `0x180009974`: `Registry value %s not found`
- `0x18000995a`: `Failed to get registry value %s. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::GetDefaultValueFromRegistry(__int64 a1, _QWORD *a2, __int64 a3)
{
  char v6; // r13
  _WORD *v7; // rcx
  int v8; // r9d
  LSTATUS v9; // eax
  signed int v10; // edi
  LSTATUS v11; // eax
  LSTATUS KeyW; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  __int64 v17; // r9
  int RegValue; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-50h]
  PHKEY phkResulta; // [rsp+20h] [rbp-50h]
  signed int v21; // [rsp+28h] [rbp-48h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-40h] BYREF
  _WORD v23[8]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpFile[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v25[8]; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+40h]
  HKEY v28; // [rsp+B8h] [rbp+48h] BYREF

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
      if ( v8 != 1 )
      {
        if ( v8 == 2 )
        {
          v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0x20019u, &hKey);
          v10 = v9;
          if ( v9 > 0 )
            v10 = (unsigned __int16)v9 | 0x80070000;
          if ( v10 < 0 )
          {
            SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open System hive. Error: 0x%08x", (unsigned int)v10);
LABEL_16:
            if ( lpSubKey[0] != v23 )
              operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( lpFile[0] != v25 )
              operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
            return (unsigned int)v10;
          }
          goto LABEL_58;
        }
        goto LABEL_29;
      }
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
      v10 = v11;
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      if ( v10 < 0 )
      {
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open Software hive. Error: 0x%08x", (unsigned int)v10);
        goto LABEL_16;
      }
LABEL_58:
      v16 = RegOpenKeyExW(hKey, (LPCWSTR)a2[2], 0, 0x20019u, &v28);
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 >= 0 )
      {
        RegValue = SrSettings::CSrSettings::GetRegValue(a1, v28, a2[3], v27);
        v10 = RegValue;
        if ( (unsigned int)(RegValue + 2147024894) > 1 )
        {
          if ( RegValue < 0 )
          {
            LODWORD(phkResulta) = RegValue;
            SrSettings::CSrSettings::Trace(a1, 2, L"Failed to get registry value %s. Error: 0x%08x", a2[3], phkResulta);
          }
LABEL_70:
          if ( v28 )
            RegCloseKey(v28);
          if ( hKey )
            RegCloseKey(hKey);
          if ( !v6 )
            goto LABEL_16;
          goto LABEL_55;
        }
        SrSettings::CSrSettings::Trace(a1, 0, L"Registry value %s not found", a2[3]);
      }
      else
      {
        v17 = a2[2];
        if ( (unsigned int)(v10 + 2147024894) > 1 )
        {
          LODWORD(phkResulta) = v10;
          SrSettings::CSrSettings::Trace(a1, 2, L"Failed to open registry key %s. Error: 0x%08x", v17, phkResulta);
          goto LABEL_70;
        }
        SrSettings::CSrSettings::Trace(a1, 0, L"Registry key %s not found", v17);
      }
      v10 = 1;
      goto LABEL_70;
    }
    if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
           (__int64)lpFile,
           *(const void **)(a1 + 8),
           (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 1) )
    {
      if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
             (__int64)lpFile,
             L"\\System32\\config") )
      {
        if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
               (__int64)lpSubKey,
               L"$SR_Registry$",
               0xDu) )
        {
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                    (__int64)lpFile,
                    L"\\SOFTWARE") )
            {
              SrSettings::CSrSettings::Trace(
                a1,
                2,
                L"Failed to append SOFTWARE to hive path. Error: 0x%08x",
                2147942408LL);
              goto LABEL_42;
            }
            if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                    (__int64)lpSubKey,
                    L"SOFTWARE") )
            {
              SrSettings::CSrSettings::Trace(
                a1,
                2,
                L"Failed to append SOFTWARE to mount point. Error: 0x%08x",
                2147942408LL);
              goto LABEL_42;
            }
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
            {
LABEL_29:
              SrSettings::CSrSettings::Trace(a1, 2, L"Invalid registry hive type %d");
              if ( lpSubKey[0] != v23 )
                operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
              if ( lpFile[0] != v25 )
                operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
              return 2147942487LL;
            }
            if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                    (__int64)lpFile,
                    L"\\SYSTEM") )
            {
              SrSettings::CSrSettings::Trace(
                a1,
                2,
                L"Failed to append SYSTEM to hive path. Error: 0x%08x",
                2147942408LL);
              goto LABEL_42;
            }
            if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                    (__int64)lpSubKey,
                    "S\x00Y\x00S\x00T\x00E\x00M") )
            {
              SrSettings::CSrSettings::Trace(
                a1,
                2,
                L"Failed to append SYSTEM to mount point. Error: 0x%08x",
                2147942408LL);
              goto LABEL_42;
            }
          }
          SrSettings::CSrSettings::Trace(a1, 0, L"Mounting hive %s to %s", lpFile[0], lpSubKey[0]);
          KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0], lpFile[0]);
          v10 = KeyW;
          if ( KeyW > 0 )
            v10 = (unsigned __int16)KeyW | 0x80070000;
          if ( v10 < 0 )
          {
            v21 = v10;
            SrSettings::CSrSettings::Trace(
              a1,
              2,
              L"Failed to load hive %s to %s. Error: 0x%08x",
              lpFile[0],
              lpSubKey[0],
              v21);
            goto LABEL_16;
          }
          v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
          v10 = v14;
          if ( v14 > 0 )
            v10 = (unsigned __int16)v14 | 0x80070000;
          if ( v10 < 0 )
          {
            LODWORD(phkResult) = v10;
            SrSettings::CSrSettings::Trace(
              a1,
              2,
              L"Failed to open loaded hive %s. Error: 0x%08x",
              lpSubKey[0],
              phkResult);
LABEL_55:
            SrSettings::CSrSettings::Trace(a1, 0, L"Unloading hive %s", lpSubKey[0]);
            v15 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0]);
            if ( v15 < 0 )
            {
              LODWORD(phkResulta) = v15;
              SrSettings::CSrSettings::Trace(a1, 1, L"Failed to unload hive %s. Error: 0x%08x", lpSubKey[0], phkResulta);
            }
            goto LABEL_16;
          }
          v6 = 1;
          goto LABEL_58;
        }
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to assign SR_ to mount point. Error: 0x%08x", 2147942408LL);
      }
      else
      {
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to append config to hive path. Error: 0x%08x", 2147942408LL);
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(
        a1,
        2,
        L"Failed to assign target OS path to hive path. Error: 0x%08x",
        2147942408LL);
    }
LABEL_42:
    if ( lpSubKey[0] != v23 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpFile[0] != v25 )
      operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942408LL;
  }
  SrSettings::CSrSettings::Trace(a1, 0, L"No registry key mapping for default value of setting %s", *a2);
  if ( lpSubKey[0] != v23 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFile[0] != v25 )
    operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
  return 1;
}

```

## disassembly

```asm
0x180009494  mov     [rsp-28h+arg_0], rbx
0x180009499  mov     [rsp-28h+arg_10], r8
0x18000949e  push    rbp
0x18000949f  push    rdi
0x1800094a0  push    r12
0x1800094a2  push    r13
0x1800094a4  push    r14
0x1800094a6  mov     rbp, rsp
0x1800094a9  sub     rsp, 70h
0x1800094ad  mov     rdi, r8
0x1800094b0  mov     r14, rdx
0x1800094b3  mov     rbx, rcx
0x1800094b6  lea     rax, [rbp+var_10]
0x1800094ba  mov     [rbp+lpFile], rax
0x1800094be  lea     rax, [rbp+var_10]
0x1800094c2  mov     [rbp+var_18], rax
0x1800094c6  xor     r13d, r13d
0x1800094c9  mov     [rbp+var_10], r13w
0x1800094ce  lea     rax, [rbp+var_30]
0x1800094d2  mov     [rbp+lpSubKey], rax
0x1800094d6  lea     rax, [rbp+var_30]
0x1800094da  mov     [rbp+var_38], rax
0x1800094de  mov     [rbp+var_30], r13w
0x1800094e3  mov     [rbp+hKey], r13
0x1800094e7  mov     [rbp+arg_18], r13
0x1800094eb  mov     r9, [rdx]
0x1800094ee  lea     r8, aGettingDefault; "Getting default value for setting %s"
0x1800094f5  xor     edx, edx
0x1800094f7  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800094fc  mov     rcx, [rdi]
0x1800094ff  mov     [rdi+8], rcx
0x180009503  mov     [rcx], r13w
0x180009507  mov     r9d, [r14+8]
0x18000950b  test    r9d, r9d
0x18000950e  jz      loc_1800099B6
0x180009514  cmp     r9d, 3
0x180009518  jz      loc_1800099B6
0x18000951e  cmp     [r14+10h], r13
0x180009522  jz      loc_1800099B6
0x180009528  cmp     [r14+18h], r13
0x18000952c  jz      loc_1800099B6
0x180009532  cmp     [rbx+0F6Ah], r13b
0x180009539  jz      loc_18000962B
0x18000953f  mov     ecx, r9d
0x180009542  sub     ecx, 1
0x180009545  jz      short loc_180009599
0x180009547  cmp     ecx, 1
0x18000954a  jnz     loc_1800096AD
0x180009550  lea     rax, [rbp+hKey]
0x180009554  mov     [rsp+70h+phkResult], rax; phkResult
0x180009559  mov     r9d, 20019h; samDesired
0x18000955f  xor     r8d, r8d; ulOptions
0x180009562  lea     rdx, SubKey; "System"
0x180009569  mov     r12, 0FFFFFFFF80000002h
0x180009570  mov     rcx, r12; hKey
0x180009573  call    cs:__imp_RegOpenKeyExW
0x180009579  mov     edi, eax
0x18000957b  test    eax, eax
0x18000957d  jle     short loc_180009588
0x18000957f  movzx   edi, ax
0x180009582  or      edi, 80070000h
0x180009588  test    edi, edi
0x18000958a  jns     loc_1800098D5
0x180009590  lea     r8, aFailedToOpenSy; "Failed to open System hive. Error: 0x%0"...
0x180009597  jmp     short loc_1800095E0
0x180009599  lea     rax, [rbp+hKey]
0x18000959d  mov     [rsp+70h+phkResult], rax; phkResult
0x1800095a2  mov     r9d, 20019h; samDesired
0x1800095a8  xor     r8d, r8d; ulOptions
0x1800095ab  lea     rdx, aSoftware_1; "Software"
0x1800095b2  mov     r12, 0FFFFFFFF80000002h
0x1800095b9  mov     rcx, r12; hKey
0x1800095bc  call    cs:__imp_RegOpenKeyExW
0x1800095c2  mov     edi, eax
0x1800095c4  test    eax, eax
0x1800095c6  jle     short loc_1800095D1
0x1800095c8  movzx   edi, ax
0x1800095cb  or      edi, 80070000h
0x1800095d1  test    edi, edi
0x1800095d3  jns     loc_1800098D5
0x1800095d9  lea     r8, aFailedToOpenSo; "Failed to open Software hive. Error: 0x"...
0x1800095e0  mov     r9d, edi
0x1800095e3  mov     edx, 2
0x1800095e8  mov     rcx, rbx
0x1800095eb  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800095f0  nop
0x1800095f1  lea     rax, [rbp+var_30]
0x1800095f5  mov     rcx, [rbp+lpSubKey]; void *
0x1800095f9  cmp     rcx, rax
0x1800095fc  jz      short loc_18000960B
0x1800095fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009605  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000960a  nop
0x18000960b  lea     rax, [rbp+var_10]
0x18000960f  mov     rcx, [rbp+lpFile]; void *
0x180009613  cmp     rcx, rax
0x180009616  jz      short loc_180009624
0x180009618  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000961f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009624  mov     eax, edi
0x180009626  jmp     loc_180009A03
0x18000962b  mov     rdx, [rbx+8]
0x18000962f  mov     r8, [rbx+10h]
0x180009633  sub     r8, rdx
0x180009636  sar     r8, 1
0x180009639  lea     rcx, [rbp+lpFile]
0x18000963d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180009642  test    al, al
0x180009644  jnz     short loc_180009652
0x180009646  lea     r8, aFailedToAssign_2; "Failed to assign target OS path to hive"...
0x18000964d  jmp     loc_180009775
0x180009652  lea     rdx, aSystem32Config_0; "\\System32\\config"
0x180009659  lea     rcx, [rbp+lpFile]
0x18000965d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180009662  test    al, al
0x180009664  jnz     short loc_180009672
0x180009666  lea     r8, aFailedToAppend_2; "Failed to append config to hive path. E"...
0x18000966d  jmp     loc_180009775
0x180009672  mov     r8d, 0Dh
0x180009678  lea     rdx, aSrRegistry; "$SR_Registry$"
0x18000967f  lea     rcx, [rbp+lpSubKey]
0x180009683  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180009688  test    al, al
0x18000968a  jnz     short loc_180009698
0x18000968c  lea     r8, aFailedToAssign_6; "Failed to assign SR_ to mount point. Er"...
0x180009693  jmp     loc_180009775
0x180009698  mov     r9d, [r14+8]
0x18000969c  mov     ecx, r9d
0x18000969f  sub     ecx, 1
0x1800096a2  jz      loc_18000973D
0x1800096a8  cmp     ecx, 1
0x1800096ab  jz      short loc_1800096FF
0x1800096ad  lea     r8, aInvalidRegistr; "Invalid registry hive type %d"
0x1800096b4  mov     edx, 2
0x1800096b9  mov     rcx, rbx
0x1800096bc  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800096c1  nop
0x1800096c2  lea     rax, [rbp+var_30]
0x1800096c6  mov     rcx, [rbp+lpSubKey]; void *
0x1800096ca  cmp     rcx, rax
0x1800096cd  jz      short loc_1800096DC
0x1800096cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800096d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800096db  nop
0x1800096dc  lea     rax, [rbp+var_10]
0x1800096e0  mov     rcx, [rbp+lpFile]; void *
0x1800096e4  cmp     rcx, rax
0x1800096e7  jz      short loc_1800096F5
0x1800096e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800096f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800096f5  mov     eax, 80070057h
0x1800096fa  jmp     loc_180009A03
0x1800096ff  lea     rdx, aSystem_2; "\\SYSTEM"
0x180009706  lea     rcx, [rbp+lpFile]
0x18000970a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000970f  test    al, al
0x180009711  jnz     short loc_18000971C
0x180009713  lea     r8, aFailedToAppend_0; "Failed to append SYSTEM to hive path. E"...
0x18000971a  jmp     short loc_180009775
0x18000971c  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "S\x00Y\x00S\x00T\x00E\x00M"
0x180009723  lea     rcx, [rbp+lpSubKey]
0x180009727  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000972c  test    al, al
0x18000972e  jnz     loc_1800097C6
0x180009734  lea     r8, aFailedToAppend_8; "Failed to append SYSTEM to mount point."...
0x18000973b  jmp     short loc_180009775
0x18000973d  lea     rdx, aSoftware_0; "\\SOFTWARE"
0x180009744  lea     rcx, [rbp+lpFile]
0x180009748  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000974d  test    al, al
0x18000974f  jnz     short loc_18000975A
0x180009751  lea     r8, aFailedToAppend_3; "Failed to append SOFTWARE to hive path."...
0x180009758  jmp     short loc_180009775
0x18000975a  lea     rdx, aSoftware; "SOFTWARE"
0x180009761  lea     rcx, [rbp+lpSubKey]
0x180009765  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000976a  test    al, al
0x18000976c  jnz     short loc_1800097C6
0x18000976e  lea     r8, aFailedToAppend; "Failed to append SOFTWARE to mount poin"...
0x180009775  mov     r9d, 80070008h
0x18000977b  mov     edx, 2
0x180009780  mov     rcx, rbx
0x180009783  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180009788  nop
0x180009789  lea     rax, [rbp+var_30]
0x18000978d  mov     rcx, [rbp+lpSubKey]; void *
0x180009791  cmp     rcx, rax
0x180009794  jz      short loc_1800097A3
0x180009796  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000979d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800097a2  nop
0x1800097a3  lea     rax, [rbp+var_10]
0x1800097a7  mov     rcx, [rbp+lpFile]; void *
0x1800097ab  cmp     rcx, rax
0x1800097ae  jz      short loc_1800097BC
0x1800097b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800097b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800097bc  mov     eax, 80070008h
0x1800097c1  jmp     loc_180009A03
0x1800097c6  mov     rax, [rbp+lpSubKey]
0x1800097ca  mov     [rsp+70h+phkResult], rax
0x1800097cf  mov     r9, [rbp+lpFile]
0x1800097d3  lea     r8, aMountingHiveST; "Mounting hive %s to %s"
0x1800097da  xor     edx, edx
0x1800097dc  mov     rcx, rbx
0x1800097df  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800097e4  mov     r8, [rbp+lpFile]; lpFile
0x1800097e8  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800097ec  mov     r12, 0FFFFFFFF80000002h
0x1800097f3  mov     rcx, r12; hKey
0x1800097f6  call    cs:__imp_RegLoadKeyW
0x1800097fc  mov     edi, eax
0x1800097fe  test    eax, eax
0x180009800  jle     short loc_18000980B
0x180009802  movzx   edi, ax
0x180009805  or      edi, 80070000h
0x18000980b  test    edi, edi
0x18000980d  jns     short loc_180009839
0x18000980f  mov     [rsp+70h+var_48], edi
0x180009813  mov     rax, [rbp+lpSubKey]
0x180009817  mov     [rsp+70h+phkResult], rax
0x18000981c  mov     r9, [rbp+lpFile]
0x180009820  lea     r8, aFailedToLoadHi; "Failed to load hive %s to %s. Error: 0x"...
0x180009827  mov     edx, 2
0x18000982c  mov     rcx, rbx
0x18000982f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180009834  jmp     loc_1800095F1
0x180009839  lea     rax, [rbp+hKey]
0x18000983d  mov     [rsp+70h+phkResult], rax; phkResult
0x180009842  mov     r9d, 20019h; samDesired
0x180009848  xor     r8d, r8d; ulOptions
0x18000984b  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18000984f  mov     rcx, r12; hKey
0x180009852  call    cs:__imp_RegOpenKeyExW
0x180009858  mov     edi, eax
0x18000985a  test    eax, eax
0x18000985c  jle     short loc_180009867
0x18000985e  movzx   edi, ax
0x180009861  or      edi, 80070000h
0x180009867  test    edi, edi
0x180009869  jns     short loc_1800098D2
0x18000986b  mov     dword ptr [rsp+70h+phkResult], edi
0x18000986f  mov     r9, [rbp+lpSubKey]
0x180009873  lea     r8, aFailedToOpenLo_0; "Failed to open loaded hive %s. Error: 0"...
0x18000987a  mov     edx, 2
0x18000987f  mov     rcx, rbx
0x180009882  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180009887  mov     r9, [rbp+lpSubKey]
0x18000988b  lea     r8, aUnloadingHiveS; "Unloading hive %s"
0x180009892  xor     edx, edx
0x180009894  mov     rcx, rbx
0x180009897  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000989c  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800098a0  mov     rcx, r12; hKey
0x1800098a3  call    cs:__imp_RegUnLoadKeyW
0x1800098a9  test    eax, eax
0x1800098ab  jns     loc_1800095F1
0x1800098b1  mov     dword ptr [rsp+70h+phkResult], eax
0x1800098b5  mov     r9, [rbp+lpSubKey]
0x1800098b9  lea     r8, aFailedToUnload; "Failed to unload hive %s. Error: 0x%08x"
0x1800098c0  mov     edx, 1
0x1800098c5  mov     rcx, rbx
0x1800098c8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800098cd  jmp     loc_1800095F1
0x1800098d2  mov     r13b, 1
0x1800098d5  lea     rax, [rbp+arg_18]
0x1800098d9  mov     [rsp+70h+phkResult], rax; phkResult
0x1800098de  mov     r9d, 20019h; samDesired
0x1800098e4  xor     r8d, r8d; ulOptions
0x1800098e7  mov     rdx, [r14+10h]; lpSubKey
0x1800098eb  mov     rcx, [rbp+hKey]; hKey
0x1800098ef  call    cs:__imp_RegOpenKeyExW
0x1800098f5  mov     edi, eax
0x1800098f7  test    eax, eax
0x1800098f9  jle     short loc_180009904
0x1800098fb  movzx   edi, ax
0x1800098fe  or      edi, 80070000h
0x180009904  mov     rcx, rbx
0x180009907  test    edi, edi
0x180009909  jns     short loc_180009930
0x18000990b  lea     eax, [rdi+7FF8FFFEh]
0x180009911  mov     r9, [r14+10h]
0x180009915  cmp     eax, 1
0x180009918  jbe     short loc_180009927
0x18000991a  mov     dword ptr [rsp+70h+phkResult], edi
0x18000991e  lea     r8, aFailedToOpenRe; "Failed to open registry key %s. Error: "...
0x180009925  jmp     short loc_180009964
0x180009927  lea     r8, aRegistryKeySNo; "Registry key %s not found"
0x18000992e  jmp     short loc_18000997E
0x180009930  mov     r9, [rbp+arg_10]
0x180009934  mov     r8, [r14+18h]
0x180009938  mov     rdx, [rbp+arg_18]
0x18000993c  call    ?GetRegValue@CSrSettings@SrSettings@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetRegValue(HKEY__ *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180009941  mov     edi, eax
0x180009943  lea     ecx, [rax+7FF8FFFEh]
0x180009949  cmp     ecx, 1
0x18000994c  jbe     short loc_180009970
0x18000994e  test    eax, eax
0x180009950  jns     short loc_18000998A
0x180009952  mov     dword ptr [rsp+70h+phkResult], eax
  ... truncated ...
```
