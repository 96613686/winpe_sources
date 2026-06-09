# CMultipleValues::GetValue(tagPROPVARIANT *)

- ea: `0x18002d140`
- end: `0x18002d1a3`
- name: `?GetValue@CMultipleValues@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `99`
- prototype: `int(CMultipleValues *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002d140`
- `0x18002d9b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d17d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d17d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002d160`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002d18a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002d160`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002d18a`

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
0x18002d140  push    rbx
0x18002d142  push    rbp
0x18002d143  push    rsi
0x18002d144  push    rdi
0x18002d145  sub     rsp, 28h
0x18002d149  xor     eax, eax
0x18002d14b  mov     rsi, rdx
0x18002d14e  mov     [rdx], ax
0x18002d151  mov     rdi, rcx
0x18002d154  cmp     [rcx+40h], al
0x18002d157  jnz     short loc_18002D16A
0x18002d159  lea     rdx, [rcx+20h]; pvarSrc
0x18002d15d  mov     rcx, rsi; pvarDest
0x18002d160  call    cs:__imp_PropVariantCopy
0x18002d166  mov     ebp, eax
0x18002d168  jmp     short loc_18002D198
0x18002d16a  add     rcx, 38h ; '8'
0x18002d16e  call    ?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)
0x18002d173  mov     ebp, eax
0x18002d175  test    eax, eax
0x18002d177  js      short loc_18002D198
0x18002d179  lea     rcx, [rdi+20h]; pvar
0x18002d17d  call    cs:__imp_PropVariantClear
0x18002d183  mov     rdx, rsi; pvarSrc
0x18002d186  lea     rcx, [rdi+20h]; pvarDest
0x18002d18a  call    cs:__imp_PropVariantCopy
0x18002d190  test    eax, eax
0x18002d192  js      short loc_18002D198
0x18002d194  mov     byte ptr [rdi+40h], 0
0x18002d198  mov     eax, ebp
0x18002d19a  add     rsp, 28h
0x18002d19e  pop     rdi
0x18002d19f  pop     rsi
0x18002d1a0  pop     rbp
0x18002d1a1  pop     rbx
0x18002d1a2  retn
```
