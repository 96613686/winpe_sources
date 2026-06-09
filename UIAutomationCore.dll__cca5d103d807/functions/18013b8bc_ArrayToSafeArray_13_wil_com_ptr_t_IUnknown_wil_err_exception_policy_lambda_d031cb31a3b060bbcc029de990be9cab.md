# ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_d031cb31a3b060bbcc029de990be9cab___

- ea: `0x18013b8bc`
- end: `0x18013babe`
- name: `ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_d031cb31a3b060bbcc029de990be9cab___`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bed0c`

## callees

- `0x18002f580`
- `0x180032724`
- `0x18013b8bc`
- `0x1801a4e68`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18013b934`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18013b934`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18013b9a6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18013b9a6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18013b98c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18013b98c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18013b9c9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18013b9c9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18013ba16`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18013ba16`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18013b957`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18013b957`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18013b900`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18013b900`

## string_xrefs

- `0x18013b93a`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18013b9f4`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18013ba7c`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
SAFEARRAY **ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_d031cb31a3b060bbcc029de990be9cab___(
        SAFEARRAY **a1,
        __int64 a2,
        signed int a3,
        ...)
{
  SAFEARRAY *Vector; // rax
  const char *v7; // r9
  HRESULT Vartype; // eax
  int v9; // ebx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v12; // eax
  __int64 i; // rbx
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r9
  LONG plLbound; // [rsp+20h] [rbp-20h] BYREF
  int v19; // [rsp+24h] [rbp-1Ch]
  SAFEARRAY *psa; // [rsp+28h] [rbp-18h]
  int v21; // [rsp+30h] [rbp-10h]
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  VARTYPE pvt; // [rsp+90h] [rbp+50h] BYREF
  __int64 plUbound; // [rsp+98h] [rbp+58h] BYREF
  va_list plUbounda; // [rsp+98h] [rbp+58h]
  va_list va1; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(plUbounda, a3);
  plUbound = va_arg(va1, _QWORD);
  v19 = 0;
  if ( a3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      plLbound);
  Vector = SafeArrayCreateVector(0xDu, 0, a3);
  *a1 = Vector;
  v19 = 1;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      v7);
  v21 = 0;
  ppvData = 0;
  psa = Vector;
  if ( SafeArrayGetDim(Vector) != 1 )
  {
    v16 = 92;
LABEL_22:
    v9 = -2147024809;
    v17 = 2147942487LL;
    goto LABEL_23;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v17 = (unsigned int)Vartype;
    v16 = 95;
    goto LABEL_23;
  }
  if ( pvt != 13 )
  {
    v16 = 106;
    goto LABEL_22;
  }
  plLbound = 0;
  LODWORD(plUbound) = 0;
  LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
  v9 = LBound;
  if ( LBound < 0 )
  {
    v17 = (unsigned int)LBound;
    v16 = 111;
  }
  else
  {
    UBound = SafeArrayGetUBound(psa, 1u, (LONG *)plUbounda);
    v9 = UBound;
    if ( UBound < 0 )
    {
      v17 = (unsigned int)UBound;
      v16 = 112;
    }
    else
    {
      v21 = plUbound - plLbound + 1;
      v12 = SafeArrayAccessData(psa, &ppvData);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v9 = 0;
        goto LABEL_10;
      }
      v17 = (unsigned int)v12;
      v16 = 115;
    }
  }
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
    (const char *)v17,
    plLbound);
LABEL_10:
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)(unsigned int)v9,
      plLbound);
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v15 = *(_QWORD *)(a2 + 8 * i);
    if ( v15 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 8LL))(*(_QWORD *)(a2 + 8 * i));
    *((_QWORD *)ppvData + i) = v15;
  }
  if ( psa )
    SafeArrayUnaccessData(psa);
  return a1;
}

```

## disassembly

```asm
0x18013b8bc  mov     [rsp-38h+plUbound], r9
0x18013b8c1  mov     [rsp-38h+arg_0], rcx
0x18013b8c6  push    rbp
0x18013b8c7  push    rbx
0x18013b8c8  push    rsi
0x18013b8c9  push    rdi
0x18013b8ca  push    r12
0x18013b8cc  push    r14
0x18013b8ce  push    r15
0x18013b8d0  mov     rbp, rsp
0x18013b8d3  sub     rsp, 40h
0x18013b8d7  mov     r14d, r8d
0x18013b8da  mov     r12, rdx
0x18013b8dd  mov     r15, rcx
0x18013b8e0  mov     [rbp+var_1C], 0
0x18013b8e7  mov     rcx, [rbp+38h]; this
0x18013b8eb  mov     eax, r8d
0x18013b8ee  shr     eax, 1Fh
0x18013b8f1  test    al, al
0x18013b8f3  jnz     loc_18013BA76
0x18013b8f9  mov     ecx, 0Dh; vt
0x18013b8fe  xor     edx, edx; lLbound
0x18013b900  call    cs:__imp_SafeArrayCreateVector
0x18013b906  mov     [r15], rax
0x18013b909  mov     esi, 1
0x18013b90e  mov     [rbp+var_1C], esi
0x18013b911  mov     rcx, [rbp+38h]; this
0x18013b915  test    rax, rax
0x18013b918  jz      loc_18013B9F4
0x18013b91e  mov     [rbp+var_10], 0
0x18013b925  mov     [rbp+ppvData], 0
0x18013b92d  mov     [rbp+psa], rax
0x18013b931  mov     rcx, rax; psa
0x18013b934  call    cs:__imp_SafeArrayGetDim
0x18013b93a  lea     rdi, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18013b941  cmp     eax, esi
0x18013b943  jnz     loc_18013BA58
0x18013b949  xor     eax, eax
0x18013b94b  mov     [rbp+pvt], ax
0x18013b94f  lea     rdx, [rbp+pvt]; pvt
0x18013b953  mov     rcx, [rbp+psa]; psa
0x18013b957  call    cs:__imp_SafeArrayGetVartype
0x18013b95d  mov     ebx, eax
0x18013b95f  test    eax, eax
0x18013b961  js      loc_18013BA8E
0x18013b967  lea     eax, [rsi+0Ch]
0x18013b96a  cmp     [rbp+pvt], ax
0x18013b96e  jnz     loc_18013BAAC
0x18013b974  mov     [rbp+plLbound], 0
0x18013b97b  mov     dword ptr [rbp+plUbound], 0
0x18013b982  lea     r8, [rbp+plLbound]; plLbound
0x18013b986  mov     edx, esi; nDim
0x18013b988  mov     rcx, [rbp+psa]; psa
0x18013b98c  call    cs:__imp_SafeArrayGetLBound
0x18013b992  mov     ebx, eax
0x18013b994  test    eax, eax
0x18013b996  js      loc_18013BA98
0x18013b99c  lea     r8, [rbp+plUbound]; plUbound
0x18013b9a0  mov     edx, esi; nDim
0x18013b9a2  mov     rcx, [rbp+psa]; psa
0x18013b9a6  call    cs:__imp_SafeArrayGetUBound
0x18013b9ac  mov     ebx, eax
0x18013b9ae  test    eax, eax
0x18013b9b0  js      loc_18013BAA2
0x18013b9b6  mov     eax, dword ptr [rbp+plUbound]
0x18013b9b9  sub     eax, [rbp+plLbound]
0x18013b9bc  add     eax, esi
0x18013b9be  mov     [rbp+var_10], eax
0x18013b9c1  lea     rdx, [rbp+ppvData]; ppvData
0x18013b9c5  mov     rcx, [rbp+psa]; psa
0x18013b9c9  call    cs:__imp_SafeArrayAccessData
0x18013b9cf  mov     ebx, eax
0x18013b9d1  test    eax, eax
0x18013b9d3  js      loc_18013BAB3
0x18013b9d9  xor     ebx, ebx
0x18013b9db  mov     rcx, [rbp+38h]; this
0x18013b9df  test    ebx, ebx
0x18013b9e1  jns     short loc_18013BA06
0x18013b9e3  mov     r9d, ebx; char *
0x18013b9e6  mov     r8, rdi; unsigned int
0x18013b9e9  mov     edx, 43h ; 'C'; void *
0x18013b9ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013b9f4  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18013b9fb  mov     edx, 132h; void *
0x18013ba00  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18013ba06  xor     ebx, ebx
0x18013ba08  test    r14d, r14d
0x18013ba0b  jnz     short loc_18013BA2E
0x18013ba0d  mov     rcx, [rbp+psa]; psa
0x18013ba11  test    rcx, rcx
0x18013ba14  jz      short loc_18013BA1C
0x18013ba16  call    cs:__imp_SafeArrayUnaccessData
0x18013ba1c  mov     rax, r15
0x18013ba1f  add     rsp, 40h
0x18013ba23  pop     r15
0x18013ba25  pop     r14
0x18013ba27  pop     r12
0x18013ba29  pop     rdi
0x18013ba2a  pop     rsi
0x18013ba2b  pop     rbx
0x18013ba2c  pop     rbp
0x18013ba2d  retn
0x18013ba2e  mov     rdi, [r12+rbx*8]
0x18013ba32  test    rdi, rdi
0x18013ba35  jz      short loc_18013BA47
0x18013ba37  mov     rax, [rdi]
0x18013ba3a  mov     rcx, rdi
0x18013ba3d  mov     rax, [rax+8]
0x18013ba41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ba46  nop
0x18013ba47  mov     rax, [rbp+ppvData]
0x18013ba4b  mov     [rax+rbx*8], rdi
0x18013ba4f  inc     ebx
0x18013ba51  cmp     ebx, r14d
0x18013ba54  jnb     short loc_18013BA0D
0x18013ba56  jmp     short loc_18013BA2E
0x18013ba58  mov     edx, 5Ch ; '\'; void *
0x18013ba5d  mov     ebx, 80070057h
0x18013ba62  mov     r9d, ebx; char *
0x18013ba65  mov     r8, rdi; unsigned int
0x18013ba68  mov     rcx, [rbp+38h]; this
0x18013ba6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ba71  jmp     loc_18013B9DB
0x18013ba76  mov     r9d, 80070057h; char *
0x18013ba7c  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18013ba83  mov     edx, 130h; void *
0x18013ba88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013ba8e  mov     r9d, eax
0x18013ba91  mov     edx, 5Fh ; '_'
0x18013ba96  jmp     short loc_18013BA65
0x18013ba98  mov     r9d, eax
0x18013ba9b  mov     edx, 6Fh ; 'o'
0x18013baa0  jmp     short loc_18013BA65
0x18013baa2  mov     r9d, eax
0x18013baa5  mov     edx, 70h ; 'p'
0x18013baaa  jmp     short loc_18013BA65
0x18013baac  mov     edx, 6Ah ; 'j'
0x18013bab1  jmp     short loc_18013BA5D
0x18013bab3  mov     r9d, eax
0x18013bab6  mov     edx, 73h ; 's'
0x18013babb  jmp     short loc_18013BA65
```
