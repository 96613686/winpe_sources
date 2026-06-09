# CIPSecurity::Release(void)

- ea: `0x18000ea80`
- end: `0x18000eaa7`
- name: `?Release@CIPSecurity@@UEAAKXZ`
- size: `39`
- prototype: `unsigned int __fastcall(CIPSecurity *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e1d0`
- `0x18000ea80`

## pseudocode

```c
__int64 __fastcall CIPSecurity::Release(CIPSecurity *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) != 1 )
    return *((unsigned int *)this + 2);
  if ( this )
    CIPSecurity::`scalar deleting destructor'(this);
  return 0;
}

```

## disassembly

```asm
0x18000ea80  sub     rsp, 28h
0x18000ea84  or      eax, 0FFFFFFFFh
0x18000ea87  lock xadd [rcx+8], eax
0x18000ea8c  cmp     eax, 1
0x18000ea8f  jnz     short loc_18000EA9F
0x18000ea91  test    rcx, rcx
0x18000ea94  jz      short loc_18000EA9B
0x18000ea96  call    ??_GCIPSecurity@@QEAAPEAXI@Z; CIPSecurity::`scalar deleting destructor'(uint)
0x18000ea9b  xor     eax, eax
0x18000ea9d  jmp     short loc_18000EAA2
0x18000ea9f  mov     eax, [rcx+8]
0x18000eaa2  add     rsp, 28h
0x18000eaa6  retn
```
