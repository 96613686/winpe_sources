# DeleteAttrsList(ldapmodW * *,ulong)

- ea: `0x180002a14`
- end: `0x180002a56`
- name: `?DeleteAttrsList@@YAXPEAPEAUldapmodW@@K@Z`
- size: `66`
- prototype: `void __fastcall(struct ldapmodW **, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002888`
- `0x180006dbc`

## callees

- `0x180002a14`
- `0x180010950`

## pseudocode

```c
void __fastcall DeleteAttrsList(struct ldapmodW **a1, unsigned int a2)
{
  __int64 i; // rbx
  struct ldapmodW *v5; // rcx

  if ( a1 )
  {
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      v5 = a1[i];
      if ( v5 )
      {
        SIDKeyProvFree(v5->mod_vals.modv_strvals);
        SIDKeyProvFree(a1[i]);
      }
    }
  }
}

```

## disassembly

```asm
0x180002a14  test    rcx, rcx
0x180002a17  jz      short locret_180002A55
0x180002a19  push    rbx
0x180002a1a  push    rbp
0x180002a1b  push    rsi
0x180002a1c  push    rdi
0x180002a1d  sub     rsp, 28h
0x180002a21  xor     ebx, ebx
0x180002a23  mov     esi, edx
0x180002a25  mov     rdi, rcx
0x180002a28  test    edx, edx
0x180002a2a  jz      short loc_180002A4D
0x180002a2c  mov     rcx, [rdi+rbx*8]
0x180002a30  test    rcx, rcx
0x180002a33  jz      short loc_180002A47
0x180002a35  mov     rcx, [rcx+10h]; lpMem
0x180002a39  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002a3e  mov     rcx, [rdi+rbx*8]; lpMem
0x180002a42  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002a47  inc     ebx
0x180002a49  cmp     ebx, esi
0x180002a4b  jb      short loc_180002A2C
0x180002a4d  add     rsp, 28h
0x180002a51  pop     rdi
0x180002a52  pop     rsi
0x180002a53  pop     rbp
0x180002a54  pop     rbx
0x180002a55  retn
```
