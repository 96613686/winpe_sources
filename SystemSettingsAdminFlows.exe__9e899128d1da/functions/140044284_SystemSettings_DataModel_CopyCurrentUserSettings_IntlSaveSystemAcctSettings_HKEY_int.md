# SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveSystemAcctSettings(HKEY__ *,int)

- ea: `0x140044284`
- end: `0x140044356`
- name: `?IntlSaveSystemAcctSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@H@Z`
- size: `210`
- prototype: `unsigned int __fastcall(HKEY hKey, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400437e4`

## callees

- `0x140005f30`
- `0x140044284`
- `0x1400446a4`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140044330`
- `KERNEL32!GetLastError` at `0x140044330`
- `KERNEL32!SetLastError` at `0x14004432a`
- `KERNEL32!SetLastError` at `0x14004432a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400442cd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400442cd`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveSystemAcctSettings(HKEY hKey)
{
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // edi
  _DWORD SidToCheck[4]; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+30h] [rbp-10h] BYREF

  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  IsMember = 0;
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) || !IsMember )
    SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(
      hKey,
      v2,
      L".DEFAULT\\Control Panel\\International");
  SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(
    hKey,
    v2,
    L"S-1-5-19\\Control Panel\\International");
  SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(
    hKey,
    v3,
    L"S-1-5-20\\Control Panel\\International");
  if ( !SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings )
  {
    SetLastError(0);
    return GetLastError();
  }
  v4 = 0;
  if ( !SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings(0, hKey) )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x140044284  mov     [rsp-8+arg_8], rbx
0x140044289  mov     [rsp-8+arg_10], rdi
0x14004428e  push    rbp
0x14004428f  mov     rbp, rsp
0x140044292  sub     rsp, 40h
0x140044296  mov     rax, cs:__security_cookie
0x14004429d  xor     rax, rsp
0x1400442a0  mov     [rbp+var_8], rax
0x1400442a4  mov     rbx, rcx
0x1400442a7  mov     [rbp+SidToCheck], 101h
0x1400442ae  xor     ecx, ecx; TokenHandle
0x1400442b0  mov     [rbp+var_1C], 5000000h
0x1400442b7  lea     r8, [rbp+IsMember]; IsMember
0x1400442bb  mov     [rbp+var_18], 12h
0x1400442c2  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1400442c6  mov     [rbp+IsMember], 0
0x1400442cd  call    cs:__imp_CheckTokenMembership
0x1400442d3  test    eax, eax
0x1400442d5  jz      short loc_1400442DD
0x1400442d7  cmp     [rbp+IsMember], 0
0x1400442db  jnz     short loc_1400442EC
0x1400442dd  lea     r8, aDefaultControl; ".DEFAULT\\Control Panel\\International"
0x1400442e4  mov     rcx, rbx; hKey
0x1400442e7  call    ?IntlSaveValuesToSystemAccts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@PEBG1@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x1400442ec  lea     r8, aS1519ControlPa; "S-1-5-19\\Control Panel\\International"
0x1400442f3  mov     rcx, rbx; hKey
0x1400442f6  call    ?IntlSaveValuesToSystemAccts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@PEBG1@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x1400442fb  lea     r8, aS1520ControlPa; "S-1-5-20\\Control Panel\\International"
0x140044302  mov     rcx, rbx; hKey
0x140044305  call    ?IntlSaveValuesToSystemAccts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@PEBG1@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x14004430a  mov     rax, cs:?s_pfnSaveSystemAcctInputSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@0P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA; int (*SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings)(HWND__ *,HKEY__ *)
0x140044311  test    rax, rax
0x140044314  jz      short loc_140044328
0x140044316  mov     rdx, rbx
0x140044319  xor     ecx, ecx
0x14004431b  xor     edi, edi
0x14004431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044322  test    eax, eax
0x140044324  jnz     short loc_140044338
0x140044326  jmp     short loc_140044330
0x140044328  xor     ecx, ecx; dwErrCode
0x14004432a  call    cs:__imp_SetLastError
0x140044330  call    cs:__imp_GetLastError
0x140044336  mov     edi, eax
0x140044338  mov     eax, edi
0x14004433a  mov     rcx, [rbp+var_8]
0x14004433e  xor     rcx, rsp; StackCookie
0x140044341  call    __security_check_cookie
0x140044346  mov     rbx, [rsp+40h+arg_8]
0x14004434b  mov     rdi, [rsp+40h+arg_10]
0x140044350  add     rsp, 40h
0x140044354  pop     rbp
0x140044355  retn
```
