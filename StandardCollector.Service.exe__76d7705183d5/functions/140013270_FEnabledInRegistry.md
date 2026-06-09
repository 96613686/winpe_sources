# FEnabledInRegistry

- ea: `0x140013270`
- end: `0x14001335d`
- name: `FEnabledInRegistry`
- size: `237`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400134ac`

## callees

- `0x140013270`
- `0x140013360`
- `0x140013410`
- `0x1400137e0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1400132e4`
- `ADVAPI32!RegQueryValueExW` at `0x1400132e4`
- `ADVAPI32!RegCloseKey` at `0x1400132f1`
- `ADVAPI32!RegCloseKey` at `0x1400132f1`

## pseudocode

```c
bool __fastcall FEnabledInRegistry(unsigned __int16 *a1, char a2)
{
  LSTATUS v5; // esi
  unsigned int v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v9; // [rsp+3Ch] [rbp-1Ch] BYREF

  if ( !a1 )
    return 0;
  hKey = 0;
  if ( (unsigned int)GetPerformanceRegKey(HKEY_LOCAL_MACHINE, a1, &hKey) )
    return a2;
  if ( !hKey )
    return a2;
  cbData = 0;
  v5 = RegQueryValueExW(hKey, 0, 0, 0, 0, &cbData);
  RegCloseKey(hKey);
  if ( v5 )
  {
    if ( v5 != 234 )
      return a2;
  }
  if ( !cbData )
    return a2;
  v9 = 0;
  if ( (unsigned int)GetPerformanceRegistryDwordValue(HKEY_LOCAL_MACHINE, a1, off_140023008, (BYTE *)&v9) )
    v6 = 0;
  else
    v6 = v9;
  return v6 == 0;
}

```

## disassembly

```asm
0x140013270  mov     [rsp+arg_8], rbx
0x140013275  mov     [rsp+arg_10], rsi
0x14001327a  push    rdi
0x14001327b  sub     rsp, 50h
0x14001327f  mov     rax, cs:__security_cookie
0x140013286  xor     rax, rsp
0x140013289  mov     [rsp+58h+var_18], rax
0x14001328e  mov     dil, dl
0x140013291  mov     rbx, rcx
0x140013294  test    rcx, rcx
0x140013297  jnz     short loc_1400132A0
0x140013299  xor     al, al
0x14001329b  jmp     loc_140013340
0x1400132a0  and     [rsp+58h+hKey], 0
0x1400132a6  lea     r8, [rsp+58h+hKey]
0x1400132ab  mov     rdx, rbx
0x1400132ae  mov     rcx, 0FFFFFFFF80000002h
0x1400132b5  call    GetPerformanceRegKey
0x1400132ba  test    eax, eax
0x1400132bc  jnz     short loc_14001333D
0x1400132be  mov     rcx, [rsp+58h+hKey]; hKey
0x1400132c3  test    rcx, rcx
0x1400132c6  jz      short loc_14001333D
0x1400132c8  and     [rsp+58h+cbData], eax
0x1400132cc  xor     r9d, r9d; lpType
0x1400132cf  lea     rax, [rsp+58h+cbData]
0x1400132d4  xor     r8d, r8d; lpReserved
0x1400132d7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1400132dc  xor     edx, edx; lpValueName
0x1400132de  and     [rsp+58h+var_38], 0
0x1400132e4  call    cs:__imp_RegQueryValueExW
0x1400132ea  mov     rcx, [rsp+58h+hKey]; hKey
0x1400132ef  mov     esi, eax
0x1400132f1  call    cs:__imp_RegCloseKey
0x1400132f7  test    esi, esi
0x1400132f9  jz      short loc_140013303
0x1400132fb  cmp     esi, 0EAh
0x140013301  jnz     short loc_14001333D
0x140013303  cmp     [rsp+58h+cbData], 0
0x140013308  jz      short loc_14001333D
0x14001330a  mov     r8, cs:off_140023008; unsigned __int16 *
0x140013311  lea     r9, [rsp+58h+var_1C]; unsigned int *
0x140013316  and     [rsp+58h+var_1C], 0
0x14001331b  mov     rdx, rbx; unsigned __int16 *
0x14001331e  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140013325  call    ?GetPerformanceRegistryDwordValue@@YAJPEAUHKEY__@@PEBG1AEAK@Z; GetPerformanceRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x14001332a  test    eax, eax
0x14001332c  jz      short loc_140013332
0x14001332e  xor     eax, eax
0x140013330  jmp     short loc_140013336
0x140013332  mov     eax, [rsp+58h+var_1C]
0x140013336  test    eax, eax
0x140013338  setz    al
0x14001333b  jmp     short loc_140013340
0x14001333d  mov     al, dil
0x140013340  mov     rcx, [rsp+58h+var_18]
0x140013345  xor     rcx, rsp; StackCookie
0x140013348  call    __security_check_cookie
0x14001334d  mov     rbx, [rsp+58h+arg_8]
0x140013352  mov     rsi, [rsp+58h+arg_10]
0x140013357  add     rsp, 50h
0x14001335b  pop     rdi
0x14001335c  retn
```
