# TimidUpdateMultiSZValueUnderSubKey

- ea: `0x180059848`
- end: `0x180059905`
- name: `TimidUpdateMultiSZValueUnderSubKey`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800418b4`

## callees

- `0x18000e970`
- `0x18000ed1c`
- `0x180010200`
- `0x18001f2c4`
- `0x18004c978`
- `0x180059848`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800598c6`
- `msvcrt!_wcsicmp` at `0x1800598c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598f7`

## string_xrefs

- `0x180059876`: `Linkage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall TimidUpdateMultiSZValueUnderSubKey(HKEY *a1, __int64 a2, wchar_t *a3, const wchar_t **a4)
{
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rcx
  int v8; // ebx
  LSTATUS result; // eax
  HKEY hKey[2]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v11[7]; // [rsp+50h] [rbp-38h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  RegistryKey::CreateSubKey(a1, (HKEY)hKey, L"Linkage", 3u, 0, 0);
  if ( !RegistryKey::ValueExists((RegistryKey *)hKey, a3) )
    goto LABEL_7;
  RegistryKey::GetValueMultiString(hKey, v11, a3);
  v6 = *a4;
  if ( *((_QWORD *)*a4 + 3) >= 8u )
    v6 = *(const wchar_t **)v6;
  v7 = (const wchar_t *)v11[0];
  if ( *(_QWORD *)(v11[0] + 24LL) >= 8u )
    v7 = *(const wchar_t **)v11[0];
  v8 = _wcsicmp(v7, v6);
  result = std::vector<std::wstring>::_Tidy(v11);
  if ( v8 )
LABEL_7:
    result = RegistryKey::SetValue((RegistryKey *)hKey, a3);
  if ( hKey[0] )
    return RegCloseKey(hKey[0]);
  return result;
}

```

## disassembly

```asm
0x180059848  mov     rax, rsp
0x18005984b  push    rbx
0x18005984c  push    rsi
0x18005984d  push    rdi
0x18005984e  sub     rsp, 70h
0x180059852  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18005985a  mov     rsi, r9
0x18005985d  mov     rdi, r8
0x180059860  mov     qword ptr [rax-60h], 0
0x180059868  mov     qword ptr [rax-68h], 0
0x180059870  mov     r9d, 3
0x180059876  lea     r8, aLinkage; "Linkage"
0x18005987d  lea     rdx, [rax-48h]
0x180059881  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180059886  nop
0x180059887  mov     rdx, rdi; wchar_t *
0x18005988a  lea     rcx, [rsp+88h+hKey]; this
0x18005988f  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180059894  test    al, al
0x180059896  jz      short loc_1800598DC
0x180059898  mov     r8, rdi
0x18005989b  lea     rdx, [rsp+88h+var_38]
0x1800598a0  lea     rcx, [rsp+88h+hKey]
0x1800598a5  call    ?GetValueMultiString@RegistryKey@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEB_W@Z; RegistryKey::GetValueMultiString(wchar_t const *)
0x1800598aa  mov     rdx, [rsi]
0x1800598ad  cmp     qword ptr [rdx+18h], 8
0x1800598b2  jb      short loc_1800598B7
0x1800598b4  mov     rdx, [rdx]; String2
0x1800598b7  mov     rcx, [rsp+88h+var_38]
0x1800598bc  cmp     qword ptr [rcx+18h], 8
0x1800598c1  jb      short loc_1800598C6
0x1800598c3  mov     rcx, [rcx]; String1
0x1800598c6  call    cs:__imp__wcsicmp
0x1800598cc  mov     ebx, eax
0x1800598ce  lea     rcx, [rsp+88h+var_38]
0x1800598d3  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800598d8  test    ebx, ebx
0x1800598da  jz      short loc_1800598ED
0x1800598dc  mov     r8, rsi
0x1800598df  mov     rdx, rdi; wchar_t *
0x1800598e2  lea     rcx, [rsp+88h+hKey]; this
0x1800598e7  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; RegistryKey::SetValue(wchar_t const *,std::vector<std::wstring> const &)
0x1800598ec  nop
0x1800598ed  mov     rcx, [rsp+88h+hKey]; hKey
0x1800598f2  test    rcx, rcx
0x1800598f5  jz      short loc_1800598FD
0x1800598f7  call    cs:__imp_RegCloseKey
0x1800598fd  add     rsp, 70h
0x180059901  pop     rdi
0x180059902  pop     rsi
0x180059903  pop     rbx
0x180059904  retn
```
