# ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)

- ea: `0x180008c28`
- end: `0x180008e93`
- name: `?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *Delimiter, PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b7c`

## callees

- `0x180008c28`
- `0x180008ea0`
- `0x1800096a0`
- `0x18000ea14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180008cbe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180008cbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e68`

## pseudocode

```c
__int64 __fastcall ConvertDelimitedStringToPropvar(const unsigned __int16 *a1, wchar_t *Delimiter, PROPVARIANT *pvar)
{
  wchar_t *v6; // r14
  int v7; // eax
  HRESULT v8; // ebx
  wchar_t *i; // rcx
  LONG lVal; // eax
  unsigned __int64 ulVal; // kr00_8
  const unsigned __int16 *v12; // r15
  unsigned int j; // esi
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  __int64 v16; // r12
  unsigned int k; // r15d
  BYTE *pData; // rcx
  LPVOID v19; // rax
  LPVOID pv; // [rsp+60h] [rbp+40h] BYREF
  ULONGLONG pullResult; // [rsp+78h] [rbp+58h] BYREF

  if ( a1 && pvar )
  {
    PropVariantClear(pvar);
    v6 = 0;
    pv = 0;
    if ( *a1 )
    {
      v7 = PIXStrDup(a1, (unsigned __int16 **)&pv);
      v6 = (wchar_t *)pv;
      v8 = v7;
      if ( v7 < 0 || !pv )
      {
        v8 = -2147024882;
        goto LABEL_29;
      }
      pvar->lVal = 0;
      for ( i = v6; wcstok(i, Delimiter, 0); i = 0 )
      {
        lVal = pvar->lVal;
        if ( lVal == -1 )
          break;
        pvar->lVal = lVal + 1;
      }
      if ( !pvar->lVal )
      {
LABEL_29:
        if ( v8 >= 0 )
          goto LABEL_37;
        goto LABEL_36;
      }
      ulVal = pvar->ulVal;
      pvar->vt = 4127;
      pv = 0;
      if ( !is_mul_ok(ulVal, 8u) )
      {
        v8 = -2147024362;
        goto LABEL_29;
      }
      v8 = CoTaskMemAllocWithInit(8 * ulVal, (void **)&pvar->bstrblobVal.pData);
      if ( v8 >= 0 )
      {
        v12 = v6;
        pv = 0;
        for ( j = 0; j < pvar->lVal; ++j )
        {
          if ( v12 )
          {
            v14 = 0x7FFFFFFF;
            v15 = v12;
            do
            {
              if ( !*v15 )
                break;
              ++v15;
              --v14;
            }
            while ( v14 );
            v8 = v14 == 0 ? 0x80070057 : 0;
            v16 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
            if ( v14 )
            {
              v8 = PIXStrDup(v12, (unsigned __int16 **)&pv);
              if ( v8 < 0 )
              {
                for ( k = 0; k < j; ++k )
                  CoTaskMemFree(*(LPVOID *)&pvar->bstrblobVal.pData[8 * k]);
                CoTaskMemFree(pvar->bstrblobVal.pData);
                pvar->bstrblobVal.pData = 0;
                goto LABEL_29;
              }
              v12 += v16 + 1;
              *(_QWORD *)&pvar->bstrblobVal.pData[8 * j] = pv;
            }
          }
          else
          {
            v8 = -2147024809;
          }
        }
        goto LABEL_29;
      }
    }
    else
    {
      pv = 0;
      v8 = PIXStrDup(&qword_180089B60, (unsigned __int16 **)&pv);
      if ( v8 >= 0 )
      {
        pullResult = 0;
        v8 = ULongLongMult(1u, 8u, &pullResult);
        if ( v8 >= 0 )
        {
          v8 = CoTaskMemAllocWithInit(pullResult, (void **)&pvar->bstrblobVal.pData);
          if ( v8 >= 0 )
          {
            pData = pvar->bstrblobVal.pData;
            v19 = pv;
            pvar->lVal = 1;
            *(_QWORD *)pData = v19;
            pvar->vt = 4127;
LABEL_37:
            CoTaskMemFree(v6);
            return (unsigned int)v8;
          }
        }
        CoTaskMemFree(pv);
      }
    }
LABEL_36:
    PropVariantClear(pvar);
    goto LABEL_37;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180008c28  mov     [rsp-38h+arg_8], rbx
0x180008c2d  push    rbp
0x180008c2e  push    rsi
0x180008c2f  push    rdi
0x180008c30  push    r12
0x180008c32  push    r13
0x180008c34  push    r14
0x180008c36  push    r15
0x180008c38  mov     rbp, rsp
0x180008c3b  sub     rsp, 20h
0x180008c3f  xor     r13d, r13d
0x180008c42  mov     rdi, r8
0x180008c45  mov     rsi, rdx
0x180008c48  mov     rbx, rcx
0x180008c4b  test    rcx, rcx
0x180008c4e  jz      loc_180008E78
0x180008c54  test    r8, r8
0x180008c57  jz      loc_180008E78
0x180008c5d  mov     rcx, r8; pvar
0x180008c60  call    cs:__imp_PropVariantClear
0x180008c67  nop     dword ptr [rax+rax+00h]
0x180008c6c  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180008c70  mov     r14d, r13d
0x180008c73  mov     [rbp+pv], r13
0x180008c77  cmp     [rbx], r13w
0x180008c7b  jz      loc_180008DE9
0x180008c81  mov     rcx, rbx; unsigned __int16 *
0x180008c84  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180008c89  mov     r14, [rbp+pv]
0x180008c8d  mov     ebx, eax
0x180008c8f  test    eax, eax
0x180008c91  js      loc_180008DDE
0x180008c97  test    r14, r14
0x180008c9a  jz      loc_180008DDE
0x180008ca0  mov     [rdi+8], r13d
0x180008ca4  mov     rcx, r14
0x180008ca7  jmp     short loc_180008CB8
0x180008ca9  mov     eax, [rdi+8]
0x180008cac  cmp     eax, 0FFFFFFFEh
0x180008caf  ja      short loc_180008CCF
0x180008cb1  inc     eax
0x180008cb3  mov     [rdi+8], eax
0x180008cb6  xor     ecx, ecx; String
0x180008cb8  xor     r8d, r8d; Context
0x180008cbb  mov     rdx, rsi; Delimiter
0x180008cbe  call    cs:__imp_wcstok
0x180008cc5  nop     dword ptr [rax+rax+00h]
0x180008cca  test    rax, rax
0x180008ccd  jnz     short loc_180008CA9
0x180008ccf  cmp     [rdi+8], r13d
0x180008cd3  jbe     loc_180008DE3
0x180008cd9  mov     ecx, [rdi+8]
0x180008cdc  mov     eax, 8
0x180008ce1  mul     rcx
0x180008ce4  mov     word ptr [rdi], 101Fh
0x180008ce9  mov     [rbp+pv], r13
0x180008ced  test    rdx, rdx
0x180008cf0  jnz     loc_180008DD7
0x180008cf6  lea     rdx, [rdi+10h]; void **
0x180008cfa  mov     rcx, rax; Size
0x180008cfd  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180008d02  mov     ebx, eax
0x180008d04  test    eax, eax
0x180008d06  js      loc_180008E56
0x180008d0c  mov     r15, r14
0x180008d0f  mov     [rbp+pv], r13
0x180008d13  mov     esi, r13d
0x180008d16  cmp     esi, [rdi+8]
0x180008d19  jnb     loc_180008DE3
0x180008d1f  test    r15, r15
0x180008d22  jz      short loc_180008D8F
0x180008d24  mov     edx, 7FFFFFFFh
0x180008d29  mov     rax, r15
0x180008d2c  cmp     [rax], r13w
0x180008d30  jz      short loc_180008D3C
0x180008d32  add     rax, 2
0x180008d36  sub     rdx, 1
0x180008d3a  jnz     short loc_180008D2C
0x180008d3c  mov     rax, rdx
0x180008d3f  mov     ecx, 7FFFFFFFh
0x180008d44  neg     rax
0x180008d47  mov     rax, rdx
0x180008d4a  sbb     ebx, ebx
0x180008d4c  sub     rcx, rdx
0x180008d4f  not     ebx
0x180008d51  and     ebx, 80070057h
0x180008d57  neg     rax
0x180008d5a  sbb     r12, r12
0x180008d5d  and     r12, rcx
0x180008d60  test    rdx, rdx
0x180008d63  jz      short loc_180008D94
0x180008d65  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180008d69  mov     rcx, r15; unsigned __int16 *
0x180008d6c  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180008d71  mov     ebx, eax
0x180008d73  test    eax, eax
0x180008d75  js      short loc_180008D9B
0x180008d77  mov     rcx, [rdi+10h]
0x180008d7b  lea     r15, [r15+r12*2]
0x180008d7f  mov     rax, [rbp+pv]
0x180008d83  add     r15, 2
0x180008d87  mov     edx, esi
0x180008d89  mov     [rcx+rdx*8], rax
0x180008d8d  jmp     short loc_180008D94
0x180008d8f  mov     ebx, 80070057h
0x180008d94  inc     esi
0x180008d96  jmp     loc_180008D16
0x180008d9b  mov     r15d, r13d
0x180008d9e  test    esi, esi
0x180008da0  jz      short loc_180008DC1
0x180008da2  mov     rcx, [rdi+10h]
0x180008da6  mov     eax, r15d
0x180008da9  mov     rcx, [rcx+rax*8]; pv
0x180008dad  call    cs:__imp_CoTaskMemFree
0x180008db4  nop     dword ptr [rax+rax+00h]
0x180008db9  inc     r15d
0x180008dbc  cmp     r15d, esi
0x180008dbf  jb      short loc_180008DA2
0x180008dc1  mov     rcx, [rdi+10h]; pv
0x180008dc5  call    cs:__imp_CoTaskMemFree
0x180008dcc  nop     dword ptr [rax+rax+00h]
0x180008dd1  mov     [rdi+10h], r13
0x180008dd5  jmp     short loc_180008DE3
0x180008dd7  mov     ebx, 80070216h
0x180008ddc  jmp     short loc_180008DE3
0x180008dde  mov     ebx, 8007000Eh
0x180008de3  test    ebx, ebx
0x180008de5  js      short loc_180008E56
0x180008de7  jmp     short loc_180008E65
0x180008de9  lea     rcx, qword_180089B60; unsigned __int16 *
0x180008df0  mov     [rbp+pv], r13
0x180008df4  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180008df9  mov     ebx, eax
0x180008dfb  test    eax, eax
0x180008dfd  js      short loc_180008E56
0x180008dff  mov     edx, 8; ullMultiplier
0x180008e04  mov     [rbp+pullResult], r13
0x180008e08  lea     r8, [rbp+pullResult]; pullResult
0x180008e0c  lea     ecx, [rdx-7]; ullMultiplicand
0x180008e0f  call    ULongLongMult
0x180008e14  mov     ebx, eax
0x180008e16  test    eax, eax
0x180008e18  js      short loc_180008E46
0x180008e1a  mov     rcx, [rbp+pullResult]; Size
0x180008e1e  lea     rdx, [rdi+10h]; void **
0x180008e22  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180008e27  mov     ebx, eax
0x180008e29  test    eax, eax
0x180008e2b  js      short loc_180008E46
0x180008e2d  mov     rcx, [rdi+10h]
0x180008e31  mov     rax, [rbp+pv]
0x180008e35  mov     dword ptr [rdi+8], 1
0x180008e3c  mov     [rcx], rax
0x180008e3f  mov     word ptr [rdi], 101Fh
0x180008e44  jmp     short loc_180008E65
0x180008e46  mov     rcx, [rbp+pv]; pv
0x180008e4a  call    cs:__imp_CoTaskMemFree
0x180008e51  nop     dword ptr [rax+rax+00h]
0x180008e56  mov     rcx, rdi; pvar
0x180008e59  call    cs:__imp_PropVariantClear
0x180008e60  nop     dword ptr [rax+rax+00h]
0x180008e65  mov     rcx, r14; pv
0x180008e68  call    cs:__imp_CoTaskMemFree
0x180008e6f  nop     dword ptr [rax+rax+00h]
0x180008e74  mov     eax, ebx
0x180008e76  jmp     short loc_180008E7D
0x180008e78  mov     eax, 80004003h
0x180008e7d  mov     rbx, [rsp+20h+arg_8]
0x180008e82  add     rsp, 20h
0x180008e86  pop     r15
0x180008e88  pop     r14
0x180008e8a  pop     r13
0x180008e8c  pop     r12
0x180008e8e  pop     rdi
0x180008e8f  pop     rsi
0x180008e90  pop     rbp
0x180008e91  retn
```
