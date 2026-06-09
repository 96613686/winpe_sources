# ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180007390`
- end: `0x1800074f3`
- name: `?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `355`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ca0`
- `0x180006e90`

## callees

- `0x180006fc0`
- `0x180007390`
- `0x180017408`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800074d6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800074d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800073ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800073ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ac`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007400`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000747c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007400`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000747c`

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
0x180007390  push    rbx
0x180007392  push    rbp
0x180007393  push    rsi
0x180007394  push    rdi
0x180007395  push    r14
0x180007397  push    r15
0x180007399  sub     rsp, 38h
0x18000739d  mov     rsi, rcx
0x1800073a0  mov     rdi, rdx
0x1800073a3  mov     rcx, rdx; pvar
0x1800073a6  mov     ebx, 80004005h
0x1800073ab  call    cs:__imp_PropVariantClear
0x1800073b2  nop     dword ptr [rax+rax+00h]
0x1800073b7  movzx   r8d, word ptr [rsi]
0x1800073bb  sub     r8d, 1Eh
0x1800073bf  jz      loc_1800074E4
0x1800073c5  sub     r8d, 1
0x1800073c9  jz      loc_1800074D0
0x1800073cf  cmp     r8d, 22h ; '"'
0x1800073d3  jnz     loc_18000749C
0x1800073d9  mov     ebp, [rsi+8]
0x1800073dc  test    ebp, ebp
0x1800073de  jz      loc_18000749C
0x1800073e4  mov     r8, [rsi+10h]; lpMultiByteStr
0x1800073e8  mov     r9d, ebp; cbMultiByte
0x1800073eb  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x1800073f3  xor     edx, edx; dwFlags
0x1800073f5  xor     ecx, ecx; CodePage
0x1800073f7  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x180007400  call    cs:__imp_MultiByteToWideChar
0x180007407  nop     dword ptr [rax+rax+00h]
0x18000740c  movsxd  r14, eax
0x18000740f  test    eax, eax
0x180007411  jle     loc_1800074AC
0x180007417  lea     rcx, [r14+1]
0x18000741b  mov     word ptr [rdi], 1Fh
0x180007420  cmp     rcx, r14
0x180007423  jb      short loc_180007497
0x180007425  mov     eax, 2
0x18000742a  mov     [rsp+68h+arg_0], 0
0x180007433  mul     rcx
0x180007436  mov     r15, rax
0x180007439  test    rdx, rdx
0x18000743c  jnz     short loc_180007497
0x18000743e  mov     rcx, rax; cb
0x180007441  call    cs:__imp_CoTaskMemAlloc
0x180007448  nop     dword ptr [rax+rax+00h]
0x18000744d  mov     [rdi+8], rax
0x180007451  test    rax, rax
0x180007454  jz      short loc_1800074C9
0x180007456  mov     r8, r15; Size
0x180007459  xor     edx, edx; Val
0x18000745b  mov     rcx, rax; void *
0x18000745e  call    memset_0
0x180007463  mov     rax, [rdi+8]
0x180007467  mov     r9d, ebp; cbMultiByte
0x18000746a  mov     r8, [rsi+10h]; lpMultiByteStr
0x18000746e  xor     edx, edx; dwFlags
0x180007470  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180007475  xor     ecx, ecx; CodePage
0x180007477  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18000747c  call    cs:__imp_MultiByteToWideChar
0x180007483  nop     dword ptr [rax+rax+00h]
0x180007488  mov     rcx, [rdi+8]
0x18000748c  xor     eax, eax
0x18000748e  xor     ebx, ebx
0x180007490  mov     [rcx+r14*2], ax
0x180007495  jmp     short loc_18000749C
0x180007497  mov     ebx, 80070216h
0x18000749c  mov     eax, ebx
0x18000749e  add     rsp, 38h
0x1800074a2  pop     r15
0x1800074a4  pop     r14
0x1800074a6  pop     rdi
0x1800074a7  pop     rsi
0x1800074a8  pop     rbp
0x1800074a9  pop     rbx
0x1800074aa  retn
0x1800074ac  call    cs:__imp_GetLastError
0x1800074b3  nop     dword ptr [rax+rax+00h]
0x1800074b8  mov     ebx, eax
0x1800074ba  test    eax, eax
0x1800074bc  jle     short loc_18000749C
0x1800074be  movzx   ebx, ax
0x1800074c1  or      ebx, 80070000h
0x1800074c7  jmp     short loc_18000749C
0x1800074c9  mov     ebx, 8007000Eh
0x1800074ce  jmp     short loc_18000749C
0x1800074d0  mov     rdx, rsi; pvarSrc
0x1800074d3  mov     rcx, rdi; pvarDest
0x1800074d6  call    cs:__imp_PropVariantCopy
0x1800074dd  nop     dword ptr [rax+rax+00h]
0x1800074e2  jmp     short loc_1800074EF
0x1800074e4  mov     rdx, rdi; pvarDest
0x1800074e7  mov     rcx, rsi; pvarSrc
0x1800074ea  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800074ef  mov     ebx, eax
0x1800074f1  jmp     short loc_18000749C
```
