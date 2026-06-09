# CMultipleValues::GetValue(tagPROPVARIANT *)

- ea: `0x180065050`
- end: `0x1800650b3`
- name: `?GetValue@CMultipleValues@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `99`
- prototype: `int(CMultipleValues *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180065050`
- `0x1800656f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180065070`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006509a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180065070`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006509a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006508d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006508d`

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
0x180065050  push    rbx
0x180065052  push    rbp
0x180065053  push    rsi
0x180065054  push    rdi
0x180065055  sub     rsp, 28h
0x180065059  xor     eax, eax
0x18006505b  mov     rsi, rdx
0x18006505e  mov     [rdx], ax
0x180065061  mov     rdi, rcx
0x180065064  cmp     [rcx+40h], al
0x180065067  jnz     short loc_18006507A
0x180065069  lea     rdx, [rcx+20h]; pvarSrc
0x18006506d  mov     rcx, rsi; pvarDest
0x180065070  call    cs:__imp_PropVariantCopy
0x180065076  mov     ebp, eax
0x180065078  jmp     short loc_1800650A8
0x18006507a  add     rcx, 38h ; '8'
0x18006507e  call    ?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)
0x180065083  mov     ebp, eax
0x180065085  test    eax, eax
0x180065087  js      short loc_1800650A8
0x180065089  lea     rcx, [rdi+20h]; pvar
0x18006508d  call    cs:__imp_PropVariantClear
0x180065093  mov     rdx, rsi; pvarSrc
0x180065096  lea     rcx, [rdi+20h]; pvarDest
0x18006509a  call    cs:__imp_PropVariantCopy
0x1800650a0  test    eax, eax
0x1800650a2  js      short loc_1800650A8
0x1800650a4  mov     byte ptr [rdi+40h], 0
0x1800650a8  mov     eax, ebp
0x1800650aa  add     rsp, 28h
0x1800650ae  pop     rdi
0x1800650af  pop     rsi
0x1800650b0  pop     rbp
0x1800650b1  pop     rbx
0x1800650b2  retn
```
