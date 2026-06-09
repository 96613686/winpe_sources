# ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180008840`
- end: `0x18000897e`
- name: `?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `318`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800081a0`
- `0x180008370`

## callees

- `0x1800084a0`
- `0x180008840`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008967`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008967`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000885b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000885b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008943`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800088aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000891a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800088aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000891a`

## pseudocode

```c
__int64 __fastcall ConvertExifVersionOnRead(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  unsigned int v4; // ebx
  LONG lVal; // ebp
  int v6; // eax
  __int64 cchWideChar; // r14
  unsigned __int64 v8; // rcx
  size_t v9; // r15
  void *v10; // rax
  signed int LastError; // eax

  v4 = -2147467259;
  PropVariantClear(pvarDest);
  switch ( pvarSrc->vt )
  {
    case 0x1Eu:
      return (unsigned int)SniffAndConvertToWideString(pvarSrc, pvarDest);
    case 0x1Fu:
      return (unsigned int)PropVariantCopy(pvarDest, pvarSrc);
    case 0x41u:
      lVal = pvarSrc->lVal;
      if ( lVal )
      {
        v6 = MultiByteToWideChar(0, 0, pvarSrc->cac.pElems, lVal, 0, 0);
        cchWideChar = v6;
        if ( v6 <= 0 )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v8 = v6 + 1LL;
          pvarDest->vt = 31;
          if ( v8 >= v6 && (v9 = 2 * v8, is_mul_ok(v8, 2u)) )
          {
            v10 = CoTaskMemAlloc(2 * v8);
            pvarDest->hVal.QuadPart = (LONGLONG)v10;
            if ( v10 )
            {
              memset_0(v10, 0, v9);
              MultiByteToWideChar(0, 0, pvarSrc->cac.pElems, lVal, pvarDest->bstrVal, cchWideChar);
              v4 = 0;
              *(_WORD *)(pvarDest->hVal.QuadPart + 2 * cchWideChar) = 0;
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
          else
          {
            return (unsigned int)-2147024362;
          }
        }
      }
      break;
  }
  return v4;
}

```

## disassembly

```asm
0x180008840  push    rbx
0x180008842  push    rbp
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  push    r14
0x180008847  push    r15
0x180008849  sub     rsp, 38h
0x18000884d  mov     rsi, rcx
0x180008850  mov     rdi, rdx
0x180008853  mov     rcx, rdx; pvar
0x180008856  mov     ebx, 80004005h
0x18000885b  call    cs:__imp_PropVariantClear
0x180008861  movzx   r8d, word ptr [rsi]
0x180008865  sub     r8d, 1Eh
0x180008869  jz      loc_18000896F
0x18000886f  sub     r8d, 1
0x180008873  jz      loc_180008961
0x180008879  cmp     r8d, 22h ; '"'
0x18000887d  jnz     loc_180008934
0x180008883  mov     ebp, [rsi+8]
0x180008886  test    ebp, ebp
0x180008888  jz      loc_180008934
0x18000888e  mov     r8, [rsi+10h]; lpMultiByteStr
0x180008892  mov     r9d, ebp; cbMultiByte
0x180008895  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18000889d  xor     edx, edx; dwFlags
0x18000889f  xor     ecx, ecx; CodePage
0x1800088a1  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x1800088aa  call    cs:__imp_MultiByteToWideChar
0x1800088b0  movsxd  r14, eax
0x1800088b3  test    eax, eax
0x1800088b5  jle     loc_180008943
0x1800088bb  lea     rcx, [r14+1]
0x1800088bf  mov     word ptr [rdi], 1Fh
0x1800088c4  cmp     rcx, r14
0x1800088c7  jb      short loc_18000892F
0x1800088c9  mov     eax, 2
0x1800088ce  mov     [rsp+68h+arg_0], 0
0x1800088d7  mul     rcx
0x1800088da  mov     r15, rax
0x1800088dd  test    rdx, rdx
0x1800088e0  jnz     short loc_18000892F
0x1800088e2  mov     rcx, rax; cb
0x1800088e5  call    cs:__imp_CoTaskMemAlloc
0x1800088eb  mov     [rdi+8], rax
0x1800088ef  test    rax, rax
0x1800088f2  jz      short loc_18000895A
0x1800088f4  mov     r8, r15; Size
0x1800088f7  xor     edx, edx; Val
0x1800088f9  mov     rcx, rax; void *
0x1800088fc  call    memset_0
0x180008901  mov     rax, [rdi+8]
0x180008905  mov     r9d, ebp; cbMultiByte
0x180008908  mov     r8, [rsi+10h]; lpMultiByteStr
0x18000890c  xor     edx, edx; dwFlags
0x18000890e  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180008913  xor     ecx, ecx; CodePage
0x180008915  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18000891a  call    cs:__imp_MultiByteToWideChar
0x180008920  mov     rcx, [rdi+8]
0x180008924  xor     eax, eax
0x180008926  xor     ebx, ebx
0x180008928  mov     [rcx+r14*2], ax
0x18000892d  jmp     short loc_180008934
0x18000892f  mov     ebx, 80070216h
0x180008934  mov     eax, ebx
0x180008936  add     rsp, 38h
0x18000893a  pop     r15
0x18000893c  pop     r14
0x18000893e  pop     rdi
0x18000893f  pop     rsi
0x180008940  pop     rbp
0x180008941  pop     rbx
0x180008942  retn
0x180008943  call    cs:__imp_GetLastError
0x180008949  mov     ebx, eax
0x18000894b  test    eax, eax
0x18000894d  jle     short loc_180008934
0x18000894f  movzx   ebx, ax
0x180008952  or      ebx, 80070000h
0x180008958  jmp     short loc_180008934
0x18000895a  mov     ebx, 8007000Eh
0x18000895f  jmp     short loc_180008934
0x180008961  mov     rdx, rsi; pvarSrc
0x180008964  mov     rcx, rdi; pvarDest
0x180008967  call    cs:__imp_PropVariantCopy
0x18000896d  jmp     short loc_18000897A
0x18000896f  mov     rdx, rdi; pvarDest
0x180008972  mov     rcx, rsi; pvarSrc
0x180008975  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000897a  mov     ebx, eax
0x18000897c  jmp     short loc_180008934
```
