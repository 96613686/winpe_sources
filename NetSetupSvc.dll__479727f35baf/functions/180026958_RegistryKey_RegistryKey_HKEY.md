# RegistryKey::RegistryKey(HKEY__ *)

- ea: `0x180026958`
- end: `0x180026977`
- name: `??0RegistryKey@@QEAA@PEAUHKEY__@@@Z`
- size: `31`
- prototype: `RegistryKey *__fastcall(RegistryKey *__hidden this, HKEY)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000b1d4`
- `0x18000b2c0`
- `0x18001eb14`
- `0x180026a10`
- `0x180026dcc`
- `0x180027ef4`
- `0x1800285cc`
- `0x1800296fc`

## callees

- `0x18000d384`
- `0x180026958`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
RegistryKey *__fastcall RegistryKey::RegistryKey(RegistryKey *this, HKEY a2)
{
  if ( !a2 )
    Win32Exception::ThrowLastError();
  *(_QWORD *)this = a2;
  return this;
}

```

## disassembly

```asm
0x180026958  sub     rsp, 38h
0x18002695c  mov     [rsp+38h+var_18], rcx
0x180026961  test    rdx, rdx
0x180026964  jnz     short loc_18002696C
0x180026966  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x18002696c  mov     [rcx], rdx
0x18002696f  mov     rax, rcx
0x180026972  add     rsp, 38h
0x180026976  retn
```
