# RegistryKey::RemoveValue(ushort const *)

- ea: `0x180020de0`
- end: `0x180020e23`
- name: `?RemoveValue@RegistryKey@@UEAAXPEBG@Z`
- size: `67`
- prototype: `void __fastcall(RegistryKey *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x180020de0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020ded`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020ded`

## pseudocode

```c
void __fastcall RegistryKey::RemoveValue(RegistryKey *this, const unsigned __int16 *a2)
{
  HKEY v2; // rcx
  int v3; // eax
  bool v4; // sf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 8);
  if ( v2 )
  {
    v3 = RegDeleteValueW(v2, a2);
    if ( v3 != 2 )
    {
      v4 = v3 < 0;
      if ( v3 > 0 )
      {
        v3 = (unsigned __int16)v3 | 0x80070000;
        v4 = v3 < 0;
      }
      if ( v4 )
      {
        pExceptionObject = v3;
        throw (long *)&pExceptionObject;
      }
    }
  }
}

```

## disassembly

```asm
0x180020de0  sub     rsp, 28h
0x180020de4  mov     rcx, [rcx+40h]; hKey
0x180020de8  test    rcx, rcx
0x180020deb  jz      short loc_180020E1E
0x180020ded  call    cs:__imp_RegDeleteValueW
0x180020df3  cmp     eax, 2
0x180020df6  jz      short loc_180020E1E
0x180020df8  test    eax, eax
0x180020dfa  jle     short loc_180020E06
0x180020dfc  movzx   eax, ax
0x180020dff  or      eax, 80070000h
0x180020e04  test    eax, eax
0x180020e06  jns     short loc_180020E1E
0x180020e08  lea     rdx, _TI1J; pThrowInfo
0x180020e0f  mov     [rsp+28h+pExceptionObject], eax
0x180020e13  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180020e18  call    _CxxThrowException_0
0x180020e1e  add     rsp, 28h
0x180020e22  retn
```
