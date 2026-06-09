# CMultipleValues::GetValue(tagPROPVARIANT *)

- ea: `0x1800462e0`
- end: `0x180046343`
- name: `?GetValue@CMultipleValues@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `99`
- prototype: `int(CMultipleValues *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800462e0`
- `0x180046990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180046300`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004632a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180046300`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004632a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004631d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004631d`

## pseudocode

```c
__int64 __fastcall CMultipleValues::GetValue(CMultipleValues *this, PROPVARIANT *a2)
{
  int inited; // ebp

  *(_WORD *)a2 = 0;
  if ( *((_BYTE *)this + 64) )
  {
    inited = InitPropVariantFromPropVariantDSA((HDSA *)this + 7, (__int64)a2);
    if ( inited >= 0 )
    {
      PropVariantClear((PROPVARIANT *)this + 4);
      if ( PropVariantCopy((PROPVARIANT *)this + 4, a2) >= 0 )
        *((_BYTE *)this + 64) = 0;
    }
  }
  else
  {
    return (unsigned int)PropVariantCopy(a2, (const PROPVARIANT *)this + 4);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800462e0  push    rbx
0x1800462e2  push    rbp
0x1800462e3  push    rsi
0x1800462e4  push    rdi
0x1800462e5  sub     rsp, 28h
0x1800462e9  xor     eax, eax
0x1800462eb  mov     rsi, rdx
0x1800462ee  mov     [rdx], ax
0x1800462f1  mov     rdi, rcx
0x1800462f4  cmp     [rcx+40h], al
0x1800462f7  jnz     short loc_18004630A
0x1800462f9  lea     rdx, [rcx+20h]; pvarSrc
0x1800462fd  mov     rcx, rsi; pvarDest
0x180046300  call    cs:__imp_PropVariantCopy
0x180046306  mov     ebp, eax
0x180046308  jmp     short loc_180046338
0x18004630a  add     rcx, 38h ; '8'
0x18004630e  call    ?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)
0x180046313  mov     ebp, eax
0x180046315  test    eax, eax
0x180046317  js      short loc_180046338
0x180046319  lea     rcx, [rdi+20h]; pvar
0x18004631d  call    cs:__imp_PropVariantClear
0x180046323  mov     rdx, rsi; pvarSrc
0x180046326  lea     rcx, [rdi+20h]; pvarDest
0x18004632a  call    cs:__imp_PropVariantCopy
0x180046330  test    eax, eax
0x180046332  js      short loc_180046338
0x180046334  mov     byte ptr [rdi+40h], 0
0x180046338  mov     eax, ebp
0x18004633a  add     rsp, 28h
0x18004633e  pop     rdi
0x18004633f  pop     rsi
0x180046340  pop     rbp
0x180046341  pop     rbx
0x180046342  retn
```
