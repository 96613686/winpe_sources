# CIPSecurity::put_GrantByDefault(short)

- ea: `0x18000f390`
- end: `0x18000f3a5`
- name: `?put_GrantByDefault@CIPSecurity@@UEAAJF@Z`
- size: `21`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CIPSecurity::put_GrantByDefault(CIPSecurity *this, __int16 a2)
{
  *((_DWORD *)this + 58) = a2 != 0;
  return 0;
}

```

## disassembly

```asm
0x18000f390  xor     r8d, r8d
0x18000f393  mov     eax, r8d
0x18000f396  test    dx, dx
0x18000f399  setnz   al
0x18000f39c  mov     [rcx+0E8h], eax
0x18000f3a2  xor     eax, eax
0x18000f3a4  retn
```
