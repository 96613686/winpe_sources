# CPropertyCache::flushpropcache(void)

- ea: `0x180010c50`
- end: `0x180010cd2`
- name: `?flushpropcache@CPropertyCache@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(CPropertyCache *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061c0`
- `0x180006f40`

## callees

- `0x180010c50`
- `0x1800184ac`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x180010cac`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180010cac`

## pseudocode

```c
void __fastcall CPropertyCache::flushpropcache(CPropertyCache *this)
{
  unsigned int *v1; // rdi
  unsigned int i; // esi
  __int64 v4; // r14
  __int64 v5; // rbp
  struct _iistype *v6; // rcx

  v1 = (unsigned int *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v4 = *((_QWORD *)this + 4);
      v5 = 544LL * i;
      v6 = *(struct _iistype **)(v4 + v5 + 536);
      if ( v6 )
      {
        IISTypeFreeIISObjects(v6, *(_DWORD *)(v4 + v5 + 524));
        *(_QWORD *)(v4 + v5 + 536) = 0;
      }
    }
    FreeADsMem(*((LPVOID *)this + 4));
  }
  *((_QWORD *)this + 4) = 0;
  *v1 = 0;
  *((_DWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x180010c50  push    rbx
0x180010c52  push    rbp
0x180010c53  push    rsi
0x180010c54  push    rdi
0x180010c55  push    r14
0x180010c57  sub     rsp, 20h
0x180010c5b  cmp     qword ptr [rcx+20h], 0
0x180010c60  lea     rdi, [rcx+8]
0x180010c64  mov     rbx, rcx
0x180010c67  jz      short loc_180010CB2
0x180010c69  xor     esi, esi
0x180010c6b  cmp     [rdi], esi
0x180010c6d  jbe     short loc_180010CA8
0x180010c6f  mov     r14, [rbx+20h]
0x180010c73  mov     eax, esi
0x180010c75  imul    rbp, rax, 220h
0x180010c7c  mov     rcx, [r14+rbp+218h]; struct _iistype *
0x180010c84  test    rcx, rcx
0x180010c87  jz      short loc_180010CA2
0x180010c89  mov     edx, [r14+rbp+20Ch]; unsigned int
0x180010c91  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180010c96  mov     qword ptr [r14+rbp+218h], 0
0x180010ca2  inc     esi
0x180010ca4  cmp     esi, [rdi]
0x180010ca6  jb      short loc_180010C6F
0x180010ca8  mov     rcx, [rbx+20h]; pMem
0x180010cac  call    cs:__imp_FreeADsMem
0x180010cb2  mov     qword ptr [rbx+20h], 0
0x180010cba  mov     dword ptr [rdi], 0
0x180010cc0  mov     dword ptr [rbx+2Ch], 0
0x180010cc7  add     rsp, 20h
0x180010ccb  pop     r14
0x180010ccd  pop     rdi
0x180010cce  pop     rsi
0x180010ccf  pop     rbp
0x180010cd0  pop     rbx
0x180010cd1  retn
```
