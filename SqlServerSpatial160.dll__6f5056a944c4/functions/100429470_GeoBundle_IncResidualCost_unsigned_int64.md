# GeoBundle::IncResidualCost(unsigned __int64)

- ea: `0x100429470`
- end: `0x10042947e`
- name: `?IncResidualCost@GeoBundle@@QEAAX_K@Z`
- size: `14`
- prototype: `void __fastcall(GeoBundle *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100429470`

## pseudocode

```c
void __fastcall GeoBundle::IncResidualCost(GeoBundle *this, __int64 a2)
{
  if ( (*(_BYTE *)this & 4) != 0 )
    *(_QWORD *)(*((_QWORD *)this + 11) + 32LL) += a2;
}

```

## disassembly

```asm
0x100429470  test    byte ptr [rcx], 4
0x100429473  jz      short locret_10042947D
0x100429475  mov     rax, [rcx+58h]
0x100429479  add     [rax+20h], rdx
0x10042947d  retn
```
