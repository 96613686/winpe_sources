# ArrayToSafeArray<3,int,_lambda_2671dcd1d58f104114f47bce693f236b_>(int const *,int,_lambda_2671dcd1d58f104114f47bce693f236b_ &&)

- ea: `0x1800c1e10`
- end: `0x1800c2002`
- name: `??$ArrayToSafeArray@$02HV_lambda_2671dcd1d58f104114f47bce693f236b_@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBHH$$QEAV_lambda_2671dcd1d58f104114f47bce693f236b_@@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c1db0`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800c1e10`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1e82`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1e82`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c1eee`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c1eee`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c1ed1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c1ed1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c1f11`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c1f11`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1f4d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1f4d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1e9e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1e9e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c1e56`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c1e56`

## string_xrefs

- `0x1800c1f67`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1f7f`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1f9d`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1fb0`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SAFEARRAY **ArrayToSafeArray<3,int,_lambda_2671dcd1d58f104114f47bce693f236b_>(
        SAFEARRAY **a1,
        __int64 a2,
        signed int a3,
        ...)
{
  SAFEARRAY *Vector; // rax
  const char *v7; // r9
  HRESULT Vartype; // eax
  unsigned int v9; // edi
  unsigned int i; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  LONG plLbound; // [rsp+20h] [rbp-20h] BYREF
  int v15; // [rsp+24h] [rbp-1Ch]
  SAFEARRAY *psa; // [rsp+28h] [rbp-18h]
  int v17; // [rsp+30h] [rbp-10h]
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  VARTYPE pvt; // [rsp+80h] [rbp+40h] BYREF
  __int64 plUbound; // [rsp+88h] [rbp+48h] BYREF
  va_list plUbounda; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(plUbounda, a3);
  plUbound = va_arg(va1, _QWORD);
  v15 = 0;
  if ( a3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      plLbound);
  Vector = SafeArrayCreateVector(3u, 0, a3);
  *a1 = Vector;
  v15 = 1;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      v7);
  v17 = 0;
  ppvData = 0;
  psa = Vector;
  if ( SafeArrayGetDim(Vector) != 1 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 92;
    goto LABEL_18;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 95;
    goto LABEL_17;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 106;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v13,
      plLbound);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v9,
      plLbound);
  }
  plLbound = 0;
  LODWORD(plUbound) = 0;
  Vartype = SafeArrayGetLBound(psa, 1u, &plLbound);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 111;
LABEL_17:
    v13 = (unsigned int)Vartype;
    goto LABEL_18;
  }
  Vartype = SafeArrayGetUBound(psa, 1u, (LONG *)plUbounda);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 112;
    goto LABEL_17;
  }
  v17 = plUbound - plLbound + 1;
  Vartype = SafeArrayAccessData(psa, &ppvData);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 115;
    goto LABEL_17;
  }
  for ( i = 0; i < a3; ++i )
    *((_DWORD *)ppvData + i) = *(_DWORD *)(4LL * i + a2);
  if ( psa )
    SafeArrayUnaccessData(psa);
  return a1;
}

```

## disassembly

```asm
0x1800c1e10  mov     [rsp-28h+arg_8], rbx
0x1800c1e15  mov     [rsp-28h+plUbound], r9
0x1800c1e1a  mov     [rsp-28h+arg_0], rcx
0x1800c1e1f  push    rbp
0x1800c1e20  push    rsi
0x1800c1e21  push    rdi
0x1800c1e22  push    r14
0x1800c1e24  push    r15
0x1800c1e26  mov     rbp, rsp
0x1800c1e29  sub     rsp, 40h
0x1800c1e2d  mov     ebx, r8d
0x1800c1e30  mov     rsi, rdx
0x1800c1e33  mov     r14, rcx
0x1800c1e36  xor     r15d, r15d
0x1800c1e39  mov     [rbp+var_1C], r15d
0x1800c1e3d  mov     rcx, [rbp+28h]; this
0x1800c1e41  mov     eax, r8d
0x1800c1e44  shr     eax, 1Fh
0x1800c1e47  test    al, al
0x1800c1e49  jnz     loc_1800C1F79
0x1800c1e4f  mov     ecx, 3; vt
0x1800c1e54  xor     edx, edx; lLbound
0x1800c1e56  call    cs:__imp_SafeArrayCreateVector
0x1800c1e5c  mov     [r14], rax
0x1800c1e5f  mov     [rbp+var_1C], 1
0x1800c1e66  mov     rcx, [rbp+28h]; this
0x1800c1e6a  test    rax, rax
0x1800c1e6d  jz      loc_1800C1F67
0x1800c1e73  mov     [rbp+var_10], r15d
0x1800c1e77  mov     [rbp+ppvData], r15
0x1800c1e7b  mov     [rbp+psa], rax
0x1800c1e7f  mov     rcx, rax; psa
0x1800c1e82  call    cs:__imp_SafeArrayGetDim
0x1800c1e88  cmp     eax, 1
0x1800c1e8b  jnz     loc_1800C1FC9
0x1800c1e91  mov     [rbp+pvt], r15w
0x1800c1e96  lea     rdx, [rbp+pvt]; pvt
0x1800c1e9a  mov     rcx, [rbp+psa]; psa
0x1800c1e9e  call    cs:__imp_SafeArrayGetVartype
0x1800c1ea4  mov     edi, eax
0x1800c1ea6  test    eax, eax
0x1800c1ea8  js      loc_1800C1FD9
0x1800c1eae  movzx   eax, [rbp+pvt]
0x1800c1eb2  cmp     ax, 3
0x1800c1eb6  jnz     loc_1800C1FE7
0x1800c1ebc  mov     [rbp+plLbound], r15d
0x1800c1ec0  mov     dword ptr [rbp+plUbound], r15d
0x1800c1ec4  lea     r8, [rbp+plLbound]; plLbound
0x1800c1ec8  mov     edx, 1; nDim
0x1800c1ecd  mov     rcx, [rbp+psa]; psa
0x1800c1ed1  call    cs:__imp_SafeArrayGetLBound
0x1800c1ed7  mov     edi, eax
0x1800c1ed9  test    eax, eax
0x1800c1edb  js      loc_1800C1F91
0x1800c1ee1  lea     r8, [rbp+plUbound]; plUbound
0x1800c1ee5  mov     edx, 1; nDim
0x1800c1eea  mov     rcx, [rbp+psa]; psa
0x1800c1eee  call    cs:__imp_SafeArrayGetUBound
0x1800c1ef4  mov     edi, eax
0x1800c1ef6  test    eax, eax
0x1800c1ef8  js      loc_1800C1FC2
0x1800c1efe  mov     eax, dword ptr [rbp+plUbound]
0x1800c1f01  sub     eax, [rbp+plLbound]
0x1800c1f04  inc     eax
0x1800c1f06  mov     [rbp+var_10], eax
0x1800c1f09  lea     rdx, [rbp+ppvData]; ppvData
0x1800c1f0d  mov     rcx, [rbp+psa]; psa
0x1800c1f11  call    cs:__imp_SafeArrayAccessData
0x1800c1f17  mov     edi, eax
0x1800c1f19  test    eax, eax
0x1800c1f1b  js      loc_1800C1FE0
0x1800c1f21  mov     eax, r15d
0x1800c1f24  test    ebx, ebx
0x1800c1f26  jz      short loc_1800C1F44
0x1800c1f28  mov     ecx, eax
0x1800c1f2a  lea     r8, ds:0[rcx*4]
0x1800c1f32  mov     edx, [r8+rsi]
0x1800c1f36  mov     rcx, [rbp+ppvData]
0x1800c1f3a  mov     [r8+rcx], edx
0x1800c1f3e  inc     eax
0x1800c1f40  cmp     eax, ebx
0x1800c1f42  jb      short loc_1800C1F28
0x1800c1f44  mov     rcx, [rbp+psa]; psa
0x1800c1f48  test    rcx, rcx
0x1800c1f4b  jz      short loc_1800C1F53
0x1800c1f4d  call    cs:__imp_SafeArrayUnaccessData
0x1800c1f53  mov     rax, r14
0x1800c1f56  mov     rbx, [rsp+40h+arg_8]
0x1800c1f5b  add     rsp, 40h
0x1800c1f5f  pop     r15
0x1800c1f61  pop     r14
0x1800c1f63  pop     rdi
0x1800c1f64  pop     rsi
0x1800c1f65  pop     rbp
0x1800c1f66  retn
0x1800c1f67  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1f6e  mov     edx, 132h; void *
0x1800c1f73  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800c1f79  mov     r9d, 80070057h; char *
0x1800c1f7f  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1f86  mov     edx, 130h; void *
0x1800c1f8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c1f91  mov     edx, 6Fh ; 'o'; void *
0x1800c1f96  mov     r9d, eax; char *
0x1800c1f99  mov     rcx, [rbp+28h]; this
0x1800c1f9d  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1fa9  mov     rcx, [rbp+28h]; this
0x1800c1fad  mov     r9d, edi; char *
0x1800c1fb0  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1fb7  mov     edx, 43h ; 'C'; void *
0x1800c1fbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c1fc2  mov     edx, 70h ; 'p'
0x1800c1fc7  jmp     short loc_1800C1F96
0x1800c1fc9  mov     r9d, 80070057h
0x1800c1fcf  mov     edi, r9d
0x1800c1fd2  mov     edx, 5Ch ; '\'
0x1800c1fd7  jmp     short loc_1800C1F99
0x1800c1fd9  mov     edx, 5Fh ; '_'
0x1800c1fde  jmp     short loc_1800C1F96
0x1800c1fe0  mov     edx, 73h ; 's'
0x1800c1fe5  jmp     short loc_1800C1F96
0x1800c1fe7  cmp     ax, 16h
0x1800c1feb  jz      loc_1800C1EBC
0x1800c1ff1  mov     r9d, 80070057h
0x1800c1ff7  mov     edi, r9d
0x1800c1ffa  mov     edx, 6Ah ; 'j'
0x1800c1fff  jmp     short loc_1800C1F99
```
