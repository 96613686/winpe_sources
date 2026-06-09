# ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_ec403018b2b048e9b8cca220b05cfc06___

- ea: `0x18001ce34`
- end: `0x18001d034`
- name: `ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_ec403018b2b048e9b8cca220b05cfc06___`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d4bc`
- `0x180047b90`

## callees

- `0x18001ce34`
- `0x18002f580`
- `0x180032724`
- `0x1801a4e68`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001ceac`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001ceac`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001cf1e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001cf1e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001cf04`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001cf04`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cf41`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cf41`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cfb6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cfb6`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18001cecf`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18001cecf`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001ce78`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001ce78`

## string_xrefs

- `0x18001ceb2`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18001cf6c`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18001cff2`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
SAFEARRAY **ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_ec403018b2b048e9b8cca220b05cfc06___(
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
  __int64 v14; // rdi
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
LABEL_21:
    v9 = -2147024809;
    v17 = 2147942487LL;
    goto LABEL_22;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v17 = (unsigned int)Vartype;
    v16 = 95;
    goto LABEL_22;
  }
  if ( pvt != 13 )
  {
    v16 = 106;
    goto LABEL_21;
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
LABEL_22:
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
    v14 = *(_QWORD *)(a2 + 8 * i);
    if ( v14 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 8LL))(*(_QWORD *)(a2 + 8 * i));
    *((_QWORD *)ppvData + i) = v14;
  }
  if ( psa )
    SafeArrayUnaccessData(psa);
  return a1;
}

```

## disassembly

```asm
0x18001ce34  mov     [rsp-38h+plUbound], r9
0x18001ce39  mov     [rsp-38h+arg_0], rcx
0x18001ce3e  push    rbp
0x18001ce3f  push    rbx
0x18001ce40  push    rsi
0x18001ce41  push    rdi
0x18001ce42  push    r12
0x18001ce44  push    r14
0x18001ce46  push    r15
0x18001ce48  mov     rbp, rsp
0x18001ce4b  sub     rsp, 40h
0x18001ce4f  mov     r14d, r8d
0x18001ce52  mov     r12, rdx
0x18001ce55  mov     r15, rcx
0x18001ce58  mov     [rbp+var_1C], 0
0x18001ce5f  mov     rcx, [rbp+38h]; this
0x18001ce63  mov     eax, r8d
0x18001ce66  shr     eax, 1Fh
0x18001ce69  test    al, al
0x18001ce6b  jnz     loc_18001CFEC
0x18001ce71  mov     ecx, 0Dh; vt
0x18001ce76  xor     edx, edx; lLbound
0x18001ce78  call    cs:__imp_SafeArrayCreateVector
0x18001ce7e  mov     [r15], rax
0x18001ce81  mov     esi, 1
0x18001ce86  mov     [rbp+var_1C], esi
0x18001ce89  mov     rcx, [rbp+38h]; this
0x18001ce8d  test    rax, rax
0x18001ce90  jz      loc_18001CF6C
0x18001ce96  mov     [rbp+var_10], 0
0x18001ce9d  mov     [rbp+ppvData], 0
0x18001cea5  mov     [rbp+psa], rax
0x18001cea9  mov     rcx, rax; psa
0x18001ceac  call    cs:__imp_SafeArrayGetDim
0x18001ceb2  lea     rdi, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18001ceb9  cmp     eax, esi
0x18001cebb  jnz     loc_18001CFCE
0x18001cec1  xor     eax, eax
0x18001cec3  mov     [rbp+pvt], ax
0x18001cec7  lea     rdx, [rbp+pvt]; pvt
0x18001cecb  mov     rcx, [rbp+psa]; psa
0x18001cecf  call    cs:__imp_SafeArrayGetVartype
0x18001ced5  mov     ebx, eax
0x18001ced7  test    eax, eax
0x18001ced9  js      loc_18001D004
0x18001cedf  lea     eax, [rsi+0Ch]
0x18001cee2  cmp     [rbp+pvt], ax
0x18001cee6  jnz     loc_18001D022
0x18001ceec  mov     [rbp+plLbound], 0
0x18001cef3  mov     dword ptr [rbp+plUbound], 0
0x18001cefa  lea     r8, [rbp+plLbound]; plLbound
0x18001cefe  mov     edx, esi; nDim
0x18001cf00  mov     rcx, [rbp+psa]; psa
0x18001cf04  call    cs:__imp_SafeArrayGetLBound
0x18001cf0a  mov     ebx, eax
0x18001cf0c  test    eax, eax
0x18001cf0e  js      loc_18001D00E
0x18001cf14  lea     r8, [rbp+plUbound]; plUbound
0x18001cf18  mov     edx, esi; nDim
0x18001cf1a  mov     rcx, [rbp+psa]; psa
0x18001cf1e  call    cs:__imp_SafeArrayGetUBound
0x18001cf24  mov     ebx, eax
0x18001cf26  test    eax, eax
0x18001cf28  js      loc_18001D018
0x18001cf2e  mov     eax, dword ptr [rbp+plUbound]
0x18001cf31  sub     eax, [rbp+plLbound]
0x18001cf34  add     eax, esi
0x18001cf36  mov     [rbp+var_10], eax
0x18001cf39  lea     rdx, [rbp+ppvData]; ppvData
0x18001cf3d  mov     rcx, [rbp+psa]; psa
0x18001cf41  call    cs:__imp_SafeArrayAccessData
0x18001cf47  mov     ebx, eax
0x18001cf49  test    eax, eax
0x18001cf4b  js      loc_18001D029
0x18001cf51  xor     ebx, ebx
0x18001cf53  mov     rcx, [rbp+38h]; this
0x18001cf57  test    ebx, ebx
0x18001cf59  jns     short loc_18001CF7E
0x18001cf5b  mov     r9d, ebx; char *
0x18001cf5e  mov     r8, rdi; unsigned int
0x18001cf61  mov     edx, 43h ; 'C'; void *
0x18001cf66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001cf6c  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18001cf73  mov     edx, 132h; void *
0x18001cf78  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001cf7e  xor     ebx, ebx
0x18001cf80  test    r14d, r14d
0x18001cf83  jz      short loc_18001CFAD
0x18001cf85  mov     rdi, [r12+rbx*8]
0x18001cf89  test    rdi, rdi
0x18001cf8c  jz      short loc_18001CF9E
0x18001cf8e  mov     rax, [rdi]
0x18001cf91  mov     rcx, rdi
0x18001cf94  mov     rax, [rax+8]
0x18001cf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9d  nop
0x18001cf9e  mov     rax, [rbp+ppvData]
0x18001cfa2  mov     [rax+rbx*8], rdi
0x18001cfa6  inc     ebx
0x18001cfa8  cmp     ebx, r14d
0x18001cfab  jb      short loc_18001CF85
0x18001cfad  mov     rcx, [rbp+psa]; psa
0x18001cfb1  test    rcx, rcx
0x18001cfb4  jz      short loc_18001CFBC
0x18001cfb6  call    cs:__imp_SafeArrayUnaccessData
0x18001cfbc  mov     rax, r15
0x18001cfbf  add     rsp, 40h
0x18001cfc3  pop     r15
0x18001cfc5  pop     r14
0x18001cfc7  pop     r12
0x18001cfc9  pop     rdi
0x18001cfca  pop     rsi
0x18001cfcb  pop     rbx
0x18001cfcc  pop     rbp
0x18001cfcd  retn
0x18001cfce  mov     edx, 5Ch ; '\'; void *
0x18001cfd3  mov     ebx, 80070057h
0x18001cfd8  mov     r9d, ebx; char *
0x18001cfdb  mov     r8, rdi; unsigned int
0x18001cfde  mov     rcx, [rbp+38h]; this
0x18001cfe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfe7  jmp     loc_18001CF53
0x18001cfec  mov     r9d, 80070057h; char *
0x18001cff2  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18001cff9  mov     edx, 130h; void *
0x18001cffe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d004  mov     r9d, eax
0x18001d007  mov     edx, 5Fh ; '_'
0x18001d00c  jmp     short loc_18001CFDB
0x18001d00e  mov     r9d, eax
0x18001d011  mov     edx, 6Fh ; 'o'
0x18001d016  jmp     short loc_18001CFDB
0x18001d018  mov     r9d, eax
0x18001d01b  mov     edx, 70h ; 'p'
0x18001d020  jmp     short loc_18001CFDB
0x18001d022  mov     edx, 6Ah ; 'j'
0x18001d027  jmp     short loc_18001CFD3
0x18001d029  mov     r9d, eax
0x18001d02c  mov     edx, 73h ; 's'
0x18001d031  jmp     short loc_18001CFDB
```
