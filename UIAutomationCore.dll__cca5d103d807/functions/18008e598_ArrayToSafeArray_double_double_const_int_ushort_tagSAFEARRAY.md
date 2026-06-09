# ArrayToSafeArray<double>(double const *,int,ushort,tagSAFEARRAY * *)

- ea: `0x18008e598`
- end: `0x18008e7b0`
- name: `??$ArrayToSafeArray@N@@YAJPEBNHGPEAPEAUtagSAFEARRAY@@@Z`
- size: `536`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18008e3c0`
- `0x18008e890`
- `0x1800bd1f4`
- `0x18027faf0`
- `0x18028187c`

## callees

- `0x18002f580`
- `0x180032724`
- `0x18008e598`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e616`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e616`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e6a1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e6a1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e682`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e682`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e6cc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e6cc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e738`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e738`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008e63c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008e63c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008e5d4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008e5d4`

## string_xrefs

- `0x18008e5ec`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18008e6e4`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18008e701`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18008e755`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArrayToSafeArray<double>(__int64 a1, signed int a2, __int16 a3, SAFEARRAY **a4)
{
  SAFEARRAY *Vector; // rax
  const char *v8; // r9
  SAFEARRAY *v9; // rbx
  HRESULT Vartype; // eax
  int v11; // edi
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 i; // r8
  const char *v18; // r9
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+20h] [rbp-48h]
  SAFEARRAY *psa; // [rsp+28h] [rbp-40h]
  void *ppvData; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LONG plUbound; // [rsp+78h] [rbp+10h] BYREF
  int pvt; // [rsp+80h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+20h] BYREF

  LOWORD(pvt) = a3;
  try
  {
    *a4 = 0;
    if ( a2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        (const char *)0x80070057LL,
        v20);
    Vector = SafeArrayCreateVector(5u, 0, a2);
    v9 = Vector;
    v21 = (int)Vector;
    if ( !Vector )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        v8);
    ppvData = 0;
    psa = Vector;
    if ( SafeArrayGetDim(Vector) == 1 )
    {
      LOWORD(pvt) = 0;
      Vartype = SafeArrayGetVartype(psa, (VARTYPE *)&pvt);
      v11 = Vartype;
      if ( Vartype < 0 )
      {
        v15 = (unsigned int)Vartype;
        v16 = 95;
        goto LABEL_13;
      }
      if ( (_WORD)pvt == 5 )
      {
        plLbound = 0;
        plUbound = 0;
        LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
        v11 = LBound;
        if ( LBound < 0 )
        {
          v15 = (unsigned int)LBound;
          v16 = 111;
        }
        else
        {
          UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
          v11 = UBound;
          if ( UBound < 0 )
          {
            v15 = (unsigned int)UBound;
            v16 = 112;
          }
          else
          {
            v14 = SafeArrayAccessData(psa, &ppvData);
            v11 = v14;
            if ( v14 >= 0 )
            {
              v11 = 0;
LABEL_14:
              if ( v11 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                  (const char *)(unsigned int)v11,
                  v21);
              for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
                *((_QWORD *)ppvData + i) = *(_QWORD *)(a1 + 8 * i);
              SafeArrayUnaccessData(psa);
              *a4 = v9;
              return 0;
            }
            v15 = (unsigned int)v14;
            v16 = 115;
          }
        }
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)v15,
          v21);
        goto LABEL_14;
      }
      v16 = 106;
    }
    else
    {
      v16 = 92;
    }
    v11 = -2147024809;
    v15 = 2147942487LL;
    goto LABEL_13;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF8,
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18008e598  mov     word ptr [rsp+pvt], r8w
0x18008e59e  push    rbx
0x18008e59f  push    rsi
0x18008e5a0  push    rdi
0x18008e5a1  push    r14
0x18008e5a3  push    r15
0x18008e5a5  sub     rsp, 40h
0x18008e5a9  mov     r14, r9
0x18008e5ac  mov     esi, edx
0x18008e5ae  mov     r15, rcx
0x18008e5b1  mov     qword ptr [r9], 0
0x18008e5b8  mov     rcx, [rsp+68h]; this
0x18008e5bd  mov     eax, edx
0x18008e5bf  shr     eax, 1Fh
0x18008e5c2  test    al, al
0x18008e5c4  jnz     loc_18008E74F
0x18008e5ca  mov     ecx, 5; vt
0x18008e5cf  mov     r8d, edx; cElements
0x18008e5d2  xor     edx, edx; lLbound
0x18008e5d4  call    cs:__imp_SafeArrayCreateVector
0x18008e5da  mov     rbx, rax
0x18008e5dd  mov     qword ptr [rsp+68h+var_48], rax; int
0x18008e5e2  mov     rcx, [rsp+68h]; this
0x18008e5e7  test    rax, rax
0x18008e5ea  jnz     short loc_18008E5FD
0x18008e5ec  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18008e5f3  mov     edx, 0EAh; void *
0x18008e5f8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18008e5fd  mov     [rsp+68h+var_38], 0
0x18008e605  mov     [rsp+68h+ppvData], 0
0x18008e60e  mov     [rsp+68h+psa], rbx
0x18008e613  mov     rcx, rbx; psa
0x18008e616  call    cs:__imp_SafeArrayGetDim
0x18008e61c  cmp     eax, 1
0x18008e61f  jnz     loc_18008E7A0
0x18008e625  xor     eax, eax
0x18008e627  mov     word ptr [rsp+68h+pvt], ax
0x18008e62f  lea     rdx, [rsp+68h+pvt]; pvt
0x18008e637  mov     rcx, [rsp+68h+psa]; psa
0x18008e63c  call    cs:__imp_SafeArrayGetVartype
0x18008e642  mov     edi, eax
0x18008e644  test    eax, eax
0x18008e646  js      loc_18008E774
0x18008e64c  mov     eax, 5
0x18008e651  cmp     word ptr [rsp+68h+pvt], ax
0x18008e659  jnz     loc_18008E781
0x18008e65f  mov     [rsp+68h+plLbound], 0
0x18008e66a  mov     [rsp+68h+plUbound], 0
0x18008e672  lea     r8, [rsp+68h+plLbound]; plLbound
0x18008e67a  lea     edx, [rax-4]; nDim
0x18008e67d  mov     rcx, [rsp+68h+psa]; psa
0x18008e682  call    cs:__imp_SafeArrayGetLBound
0x18008e688  mov     edi, eax
0x18008e68a  test    eax, eax
0x18008e68c  js      loc_18008E767
0x18008e692  lea     r8, [rsp+68h+plUbound]; plUbound
0x18008e697  mov     edx, 1; nDim
0x18008e69c  mov     rcx, [rsp+68h+psa]; psa
0x18008e6a1  call    cs:__imp_SafeArrayGetUBound
0x18008e6a7  mov     edi, eax
0x18008e6a9  test    eax, eax
0x18008e6ab  js      loc_18008E793
0x18008e6b1  mov     eax, [rsp+68h+plUbound]
0x18008e6b5  sub     eax, [rsp+68h+plLbound]
0x18008e6bc  inc     eax
0x18008e6be  mov     [rsp+68h+var_38], eax
0x18008e6c2  lea     rdx, [rsp+68h+ppvData]; ppvData
0x18008e6c7  mov     rcx, [rsp+68h+psa]; psa
0x18008e6cc  call    cs:__imp_SafeArrayAccessData
0x18008e6d2  mov     edi, eax
0x18008e6d4  test    eax, eax
0x18008e6d6  js      short loc_18008E6DC
0x18008e6d8  xor     edi, edi
0x18008e6da  jmp     short loc_18008E6F5
0x18008e6dc  mov     r9d, eax; char *
0x18008e6df  mov     edx, 73h ; 's'; void *
0x18008e6e4  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18008e6eb  mov     rcx, [rsp+68h]; this
0x18008e6f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e6f5  mov     rcx, [rsp+68h]; this
0x18008e6fa  test    edi, edi
0x18008e6fc  jns     short loc_18008E712
0x18008e6fe  mov     r9d, edi; char *
0x18008e701  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18008e708  mov     edx, 43h ; 'C'; void *
0x18008e70d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e712  xor     r8d, r8d
0x18008e715  test    esi, esi
0x18008e717  jz      short loc_18008E72E
0x18008e719  mov     rcx, [r15+r8*8]
0x18008e71d  mov     rax, [rsp+68h+ppvData]
0x18008e722  mov     [rax+r8*8], rcx
0x18008e726  inc     r8d
0x18008e729  cmp     r8d, esi
0x18008e72c  jb      short loc_18008E719
0x18008e72e  mov     rcx, [rsp+68h+psa]; psa
0x18008e733  test    rcx, rcx
0x18008e736  jz      short loc_18008E73E
0x18008e738  call    cs:__imp_SafeArrayUnaccessData
0x18008e73e  mov     [r14], rbx
0x18008e741  xor     eax, eax
0x18008e743  add     rsp, 40h
0x18008e747  pop     r15
0x18008e749  pop     r14
0x18008e74b  pop     rdi
0x18008e74c  pop     rsi
0x18008e74d  pop     rbx
0x18008e74e  retn
0x18008e74f  mov     r9d, 80070057h; char *
0x18008e755  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18008e75c  mov     edx, 0E8h; void *
0x18008e761  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e767  mov     r9d, eax
0x18008e76a  mov     edx, 6Fh ; 'o'
0x18008e76f  jmp     loc_18008E6E4
0x18008e774  mov     r9d, eax
0x18008e777  mov     edx, 5Fh ; '_'
0x18008e77c  jmp     loc_18008E6E4
0x18008e781  mov     edx, 6Ah ; 'j'
0x18008e786  mov     edi, 80070057h
0x18008e78b  mov     r9d, edi
0x18008e78e  jmp     loc_18008E6E4
0x18008e793  mov     r9d, eax
0x18008e796  mov     edx, 70h ; 'p'
0x18008e79b  jmp     loc_18008E6E4
0x18008e7a0  mov     edx, 5Ch ; '\'
0x18008e7a5  jmp     short loc_18008E786
0x18008e7a7  mov     eax, [rsp+68h+pvt]
0x18008e7ae  jmp     short loc_18008E743
```
