# ANON_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180002250`
- end: `0x180002276`
- name: `?GetImpersonationToken@ANON_USER_CONTEXT@@UEAAPEAXXZ`
- size: `38`
- prototype: `void *__fastcall(ANON_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002250`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall ANON_USER_CONTEXT::GetImpersonationToken(ANON_USER_CONTEXT *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 56LL))(v1);
  else
    return *((_QWORD *)s_pAnonAuthProvider + 325);
}

```

## disassembly

```asm
0x180002250  mov     rcx, [rcx+10h]
0x180002254  test    rcx, rcx
0x180002257  jz      short loc_180002266
0x180002259  mov     rax, [rcx]
0x18000225c  mov     rax, [rax+38h]
0x180002260  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002265  retn
0x180002266  mov     rax, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x18000226d  mov     rax, [rax+0A28h]
0x180002274  jmp     short locret_180002265
```
