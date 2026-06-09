# RegistryKey::RemoveSubKey(ushort const *)

- ea: `0x180020d90`
- end: `0x180020dd3`
- name: `?RemoveSubKey@RegistryKey@@UEAAXPEBG@Z`
- size: `67`
- prototype: `void __fastcall(RegistryKey *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x180020d90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180020d9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180020d9d`

## pseudocode

```c
void __fastcall RegistryKey::RemoveSubKey(RegistryKey *this, const unsigned __int16 *a2)
{
  HKEY v2; // rcx
  int v3; // eax
  bool v4; // sf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 8);
  if ( v2 )
  {
    v3 = RegDeleteTreeW(v2, a2);
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
0x180020d90  sub     rsp, 28h
0x180020d94  mov     rcx, [rcx+40h]; hKey
0x180020d98  test    rcx, rcx
0x180020d9b  jz      short loc_180020DCE
0x180020d9d  call    cs:__imp_RegDeleteTreeW
0x180020da3  cmp     eax, 2
0x180020da6  jz      short loc_180020DCE
0x180020da8  test    eax, eax
0x180020daa  jle     short loc_180020DB6
0x180020dac  movzx   eax, ax
0x180020daf  or      eax, 80070000h
0x180020db4  test    eax, eax
0x180020db6  jns     short loc_180020DCE
0x180020db8  lea     rdx, _TI1J; pThrowInfo
0x180020dbf  mov     [rsp+28h+pExceptionObject], eax
0x180020dc3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180020dc8  call    _CxxThrowException_0
0x180020dce  add     rsp, 28h
0x180020dd2  retn
```
