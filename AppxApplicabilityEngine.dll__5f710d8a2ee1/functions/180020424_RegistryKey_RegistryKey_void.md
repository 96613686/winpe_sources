# RegistryKey::~RegistryKey(void)

- ea: `0x180020424`
- end: `0x18002046e`
- name: `??1RegistryKey@@UEAA@XZ`
- size: `74`
- prototype: `void __fastcall(RegistryKey *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020550`

## callees

- `0x180004080`
- `0x180020424`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002044f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002044f`

## pseudocode

```c
void __fastcall RegistryKey::~RegistryKey(RegistryKey *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx

  *(_QWORD *)this = &RegistryKey::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 8);
  if ( v2 )
    RegCloseKey(v2);
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
    RegCloseKey(v3);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((char *)this + 16);
  *(_QWORD *)this = &IRegistryKey::`vftable';
}

```

## disassembly

```asm
0x180020424  push    rbx
0x180020426  sub     rsp, 20h
0x18002042a  lea     rax, ??_7RegistryKey@@6B@; const RegistryKey::`vftable'
0x180020431  mov     rbx, rcx
0x180020434  mov     [rcx], rax
0x180020437  mov     rcx, [rcx+40h]; hKey
0x18002043b  test    rcx, rcx
0x18002043e  jz      short loc_180020446
0x180020440  call    cs:__imp_RegCloseKey
0x180020446  mov     rcx, [rbx+8]; hKey
0x18002044a  test    rcx, rcx
0x18002044d  jz      short loc_180020455
0x18002044f  call    cs:__imp_RegCloseKey
0x180020455  lea     rcx, [rbx+10h]
0x180020459  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18002045e  lea     rax, ??_7IRegistryKey@@6B@; const IRegistryKey::`vftable'
0x180020465  mov     [rbx], rax
0x180020468  add     rsp, 20h
0x18002046c  pop     rbx
0x18002046d  retn
```
