# ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)

- ea: `0x1800078cc`
- end: `0x180007b0c`
- name: `?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *Delimiter, PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007828`

## callees

- `0x1800078cc`
- `0x180007b20`
- `0x180007d90`
- `0x18000e364`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18000795c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18000795c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007904`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007adf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007904`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      v8 = PIXStrDup(&qword_180088B80, (unsigned __int16 **)&pv);
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
0x1800078cc  mov     [rsp-38h+arg_8], rbx
0x1800078d1  push    rbp
0x1800078d2  push    rsi
0x1800078d3  push    rdi
0x1800078d4  push    r12
0x1800078d6  push    r13
0x1800078d8  push    r14
0x1800078da  push    r15
0x1800078dc  mov     rbp, rsp
0x1800078df  sub     rsp, 20h
0x1800078e3  xor     r13d, r13d
0x1800078e6  mov     rdi, r8
0x1800078e9  mov     rsi, rdx
0x1800078ec  mov     rbx, rcx
0x1800078ef  test    rcx, rcx
0x1800078f2  jz      loc_180007AF2
0x1800078f8  test    r8, r8
0x1800078fb  jz      loc_180007AF2
0x180007901  mov     rcx, r8; pvar
0x180007904  call    cs:__imp_PropVariantClear
0x18000790a  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18000790e  mov     r14d, r13d
0x180007911  mov     [rbp+pv], r13
0x180007915  cmp     [rbx], r13w
0x180007919  jz      loc_180007A75
0x18000791f  mov     rcx, rbx; unsigned __int16 *
0x180007922  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180007927  mov     r14, [rbp+pv]
0x18000792b  mov     ebx, eax
0x18000792d  test    eax, eax
0x18000792f  js      loc_180007A6A
0x180007935  test    r14, r14
0x180007938  jz      loc_180007A6A
0x18000793e  mov     [rdi+8], r13d
0x180007942  mov     rcx, r14
0x180007945  jmp     short loc_180007956
0x180007947  mov     eax, [rdi+8]
0x18000794a  cmp     eax, 0FFFFFFFEh
0x18000794d  ja      short loc_180007967
0x18000794f  inc     eax
0x180007951  mov     [rdi+8], eax
0x180007954  xor     ecx, ecx; String
0x180007956  xor     r8d, r8d; Context
0x180007959  mov     rdx, rsi; Delimiter
0x18000795c  call    cs:__imp_wcstok
0x180007962  test    rax, rax
0x180007965  jnz     short loc_180007947
0x180007967  cmp     [rdi+8], r13d
0x18000796b  jbe     loc_180007A6F
0x180007971  mov     ecx, [rdi+8]
0x180007974  mov     eax, 8
0x180007979  mul     rcx
0x18000797c  mov     word ptr [rdi], 101Fh
0x180007981  mov     [rbp+pv], r13
0x180007985  test    rdx, rdx
0x180007988  jnz     loc_180007A63
0x18000798e  lea     rdx, [rdi+10h]; void **
0x180007992  mov     rcx, rax; Size
0x180007995  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18000799a  mov     ebx, eax
0x18000799c  test    eax, eax
0x18000799e  js      loc_180007ADC
0x1800079a4  mov     r15, r14
0x1800079a7  mov     [rbp+pv], r13
0x1800079ab  mov     esi, r13d
0x1800079ae  cmp     esi, [rdi+8]
0x1800079b1  jnb     loc_180007A6F
0x1800079b7  test    r15, r15
0x1800079ba  jz      short loc_180007A27
0x1800079bc  mov     edx, 7FFFFFFFh
0x1800079c1  mov     rax, r15
0x1800079c4  cmp     [rax], r13w
0x1800079c8  jz      short loc_1800079D4
0x1800079ca  add     rax, 2
0x1800079ce  sub     rdx, 1
0x1800079d2  jnz     short loc_1800079C4
0x1800079d4  mov     rax, rdx
0x1800079d7  mov     ecx, 7FFFFFFFh
0x1800079dc  neg     rax
0x1800079df  mov     rax, rdx
0x1800079e2  sbb     ebx, ebx
0x1800079e4  sub     rcx, rdx
0x1800079e7  not     ebx
0x1800079e9  and     ebx, 80070057h
0x1800079ef  neg     rax
0x1800079f2  sbb     r12, r12
0x1800079f5  and     r12, rcx
0x1800079f8  test    rdx, rdx
0x1800079fb  jz      short loc_180007A2C
0x1800079fd  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180007a01  mov     rcx, r15; unsigned __int16 *
0x180007a04  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180007a09  mov     ebx, eax
0x180007a0b  test    eax, eax
0x180007a0d  js      short loc_180007A33
0x180007a0f  mov     rcx, [rdi+10h]
0x180007a13  lea     r15, [r15+r12*2]
0x180007a17  mov     rax, [rbp+pv]
0x180007a1b  add     r15, 2
0x180007a1f  mov     edx, esi
0x180007a21  mov     [rcx+rdx*8], rax
0x180007a25  jmp     short loc_180007A2C
0x180007a27  mov     ebx, 80070057h
0x180007a2c  inc     esi
0x180007a2e  jmp     loc_1800079AE
0x180007a33  mov     r15d, r13d
0x180007a36  test    esi, esi
0x180007a38  jz      short loc_180007A53
0x180007a3a  mov     rcx, [rdi+10h]
0x180007a3e  mov     eax, r15d
0x180007a41  mov     rcx, [rcx+rax*8]; pv
0x180007a45  call    cs:__imp_CoTaskMemFree
0x180007a4b  inc     r15d
0x180007a4e  cmp     r15d, esi
0x180007a51  jb      short loc_180007A3A
0x180007a53  mov     rcx, [rdi+10h]; pv
0x180007a57  call    cs:__imp_CoTaskMemFree
0x180007a5d  mov     [rdi+10h], r13
0x180007a61  jmp     short loc_180007A6F
0x180007a63  mov     ebx, 80070216h
0x180007a68  jmp     short loc_180007A6F
0x180007a6a  mov     ebx, 8007000Eh
0x180007a6f  test    ebx, ebx
0x180007a71  js      short loc_180007ADC
0x180007a73  jmp     short loc_180007AE5
0x180007a75  lea     rcx, qword_180088B80; unsigned __int16 *
0x180007a7c  mov     [rbp+pv], r13
0x180007a80  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180007a85  mov     ebx, eax
0x180007a87  test    eax, eax
0x180007a89  js      short loc_180007ADC
0x180007a8b  mov     edx, 8; ullMultiplier
0x180007a90  mov     [rbp+pullResult], r13
0x180007a94  lea     r8, [rbp+pullResult]; pullResult
0x180007a98  lea     ecx, [rdx-7]; ullMultiplicand
0x180007a9b  call    ULongLongMult
0x180007aa0  mov     ebx, eax
0x180007aa2  test    eax, eax
0x180007aa4  js      short loc_180007AD2
0x180007aa6  mov     rcx, [rbp+pullResult]; Size
0x180007aaa  lea     rdx, [rdi+10h]; void **
0x180007aae  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180007ab3  mov     ebx, eax
0x180007ab5  test    eax, eax
0x180007ab7  js      short loc_180007AD2
0x180007ab9  mov     rcx, [rdi+10h]
0x180007abd  mov     rax, [rbp+pv]
0x180007ac1  mov     dword ptr [rdi+8], 1
0x180007ac8  mov     [rcx], rax
0x180007acb  mov     word ptr [rdi], 101Fh
0x180007ad0  jmp     short loc_180007AE5
0x180007ad2  mov     rcx, [rbp+pv]; pv
0x180007ad6  call    cs:__imp_CoTaskMemFree
0x180007adc  mov     rcx, rdi; pvar
0x180007adf  call    cs:__imp_PropVariantClear
0x180007ae5  mov     rcx, r14; pv
0x180007ae8  call    cs:__imp_CoTaskMemFree
0x180007aee  mov     eax, ebx
0x180007af0  jmp     short loc_180007AF7
0x180007af2  mov     eax, 80004003h
0x180007af7  mov     rbx, [rsp+20h+arg_8]
0x180007afc  add     rsp, 20h
0x180007b00  pop     r15
0x180007b02  pop     r14
0x180007b04  pop     r13
0x180007b06  pop     r12
0x180007b08  pop     rdi
0x180007b09  pop     rsi
0x180007b0a  pop     rbp
0x180007b0b  retn
```
