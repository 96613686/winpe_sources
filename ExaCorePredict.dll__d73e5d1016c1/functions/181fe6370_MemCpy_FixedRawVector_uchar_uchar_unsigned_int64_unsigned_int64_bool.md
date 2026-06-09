# MemCpy_FixedRawVector(uchar *,uchar *,unsigned __int64,unsigned __int64,bool)

- ea: `0x181fe6370`
- end: `0x181fe63ac`
- name: `?MemCpy_FixedRawVector@@YAHPEAE0_K1_N@Z`
- size: `60`
- prototype: `int(unsigned __int8 *, unsigned __int8 *, unsigned __int64, unsigned __int64, bool)`
- caller_count: `157`
- callee_count: `2`
- tags: ``

## callers

- `0x181610290`
- `0x181610420`
- `0x1816105a0`
- `0x181610720`
- `0x181610890`
- `0x1816109f0`
- `0x181610cf0`
- `0x181611030`
- `0x181611290`
- `0x181611480`
- `0x1816116b0`
- `0x181611840`
- `0x1816119a0`
- `0x181611b20`
- `0x181611cb0`
- `0x181611e60`
- `0x181612000`
- `0x181612180`
- `0x181612520`
- `0x1816128f0`
- `0x181612b60`
- `0x181612d90`
- `0x181613000`
- `0x1816131b0`
- `0x181613330`
- `0x1816134b0`
- `0x181613660`
- `0x1816137f0`
- `0x181613990`
- `0x181613b10`
- `0x181613e50`
- `0x181614070`
- `0x1816142e0`
- `0x181614510`
- `0x181614780`
- `0x181614930`
- `0x181614ab0`
- `0x181614c40`
- `0x181614de0`
- `0x181614f90`
- `0x181615120`
- `0x1816152c0`
- `0x1816155e0`
- `0x1816157f0`
- `0x181615a70`
- `0x181615c90`
- `0x181615f00`
- `0x1816160a0`
- `0x181616220`
- `0x1816163b0`

## callees

- `0x1815ce310`
- `0x181fe6370`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x181fe639f`
- `VCRUNTIME140!memmove` at `0x181fe639f`

## pseudocode

```c
__int64 __fastcall MemCpy_FixedRawVector(unsigned __int8 *a1, unsigned __int8 *a2, __int64 a3, __int64 a4, bool a5)
{
  unsigned __int64 v5; // rax

  if ( a1 != a2 )
  {
    v5 = a4 * a3;
    if ( !a5 )
    {
      CxMemCpy(a1, v5, a2, v5);
      return 0;
    }
    memmove(a1, a2, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x181fe6370  sub     rsp, 28h
0x181fe6374  mov     rax, r8
0x181fe6377  cmp     rcx, rdx
0x181fe637a  jz      short loc_181FE63A5
0x181fe637c  imul    rax, r9
0x181fe6380  cmp     [rsp+28h+arg_20], 0
0x181fe6385  jnz     short loc_181FE639C
0x181fe6387  mov     r8, rdx; void *
0x181fe638a  mov     r9, rax; unsigned __int64
0x181fe638d  mov     rdx, rax; unsigned __int64
0x181fe6390  call    ?CxMemCpy@@YAPEAXPEAX_KPEBX1@Z; CxMemCpy(void *,unsigned __int64,void const *,unsigned __int64)
0x181fe6395  xor     eax, eax
0x181fe6397  add     rsp, 28h
0x181fe639b  retn
0x181fe639c  mov     r8, rax; Size
0x181fe639f  call    cs:__imp_memmove
0x181fe63a5  xor     eax, eax
0x181fe63a7  add     rsp, 28h
0x181fe63ab  retn
```
