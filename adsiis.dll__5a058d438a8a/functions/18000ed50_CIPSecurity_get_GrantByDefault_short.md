# CIPSecurity::get_GrantByDefault(short *)

- ea: `0x18000ed50`
- end: `0x18000ed6c`
- name: `?get_GrantByDefault@CIPSecurity@@UEAAJPEAF@Z`
- size: `28`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ed50`

## pseudocode

```c
__int64 __fastcall CIPSecurity::get_GrantByDefault(CIPSecurity *this, __int16 *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = -(*((_DWORD *)this + 58) != 0);
  return result;
}

```

## disassembly

```asm
0x18000ed50  test    rdx, rdx
0x18000ed53  jnz     short loc_18000ED5B
0x18000ed55  mov     eax, 80004003h
0x18000ed5a  retn
0x18000ed5b  mov     eax, [rcx+0E8h]
0x18000ed61  neg     eax
0x18000ed63  sbb     cx, cx
0x18000ed66  xor     eax, eax
0x18000ed68  mov     [rdx], cx
0x18000ed6b  retn
```
