# ANON_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180004970`
- end: `0x180004994`
- name: `?GetPrimaryToken@ANON_USER_CONTEXT@@UEAAPEAXXZ`
- size: `36`
- prototype: `void *__fastcall(ANON_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004970`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall ANON_USER_CONTEXT::GetPrimaryToken(ANON_USER_CONTEXT *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 64LL))(v1);
  else
    return *((_QWORD *)s_pAnonAuthProvider + 324);
}

```

## disassembly

```asm
0x180004970  mov     rcx, [rcx+10h]
0x180004974  test    rcx, rcx
0x180004977  jnz     short loc_180004988
0x180004979  mov     rax, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x180004980  mov     rax, [rax+0A20h]
0x180004987  retn
0x180004988  mov     rax, [rcx]
0x18000498b  mov     rax, [rax+40h]
0x18000498f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
