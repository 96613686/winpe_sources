# _anonymous_namespace_::AddWnfTrigger

- ea: `0x140044ba0`
- end: `0x140044e44`
- name: `_anonymous_namespace_::AddWnfTrigger`
- size: `676`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140045230`
- `0x140045970`

## callees

- `0x14000a6e4`
- `0x14000e548`
- `0x140028824`
- `0x140044ba0`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x140044c46`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140044cc9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140044c46`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140044cc9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140044d22`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140044d3e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140044d22`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140044d3e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140044c5f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140044ce2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140044c5f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140044ce2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140044d15`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140044d31`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140044d15`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140044d31`

## string_xrefs

- `0x140044daf`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044dde`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044df3`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044e08`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044e1d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044e32`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall anonymous_namespace_::AddWnfTrigger(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // eax
  SAFEARRAY *v6; // rax
  SAFEARRAY *v7; // rdi
  HRESULT v8; // eax
  unsigned int i; // ebx
  int v10; // eax
  int v11; // eax
  SAFEARRAY *v12; // rax
  SAFEARRAY *v13; // rbx
  HRESULT v14; // eax
  int v15; // eax
  HRESULT result; // eax
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v19; // rcx
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v23; // [rsp+60h] [rbp+20h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  __int64 v25; // [rsp+78h] [rbp+38h] BYREF

  v25 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 72LL))(a1, &v25);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v3,
      rgsabound.cElements);
  v24 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 80LL))(v25, 12, &v24);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      rgsabound.cElements);
  v23 = 0;
  v5 = (**v24)(v24, &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f, &v23);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v5,
      rgsabound.cElements);
  rgsabound = (SAFEARRAYBOUND)8LL;
  v6 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v7 = v6;
  v21[0] = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
LABEL_27:
    ATL::AtlThrowImpl(v8);
  }
  v8 = SafeArrayLock(v6);
  if ( v8 < 0 )
    goto LABEL_27;
  for ( i = 0; i < 8; ++i )
  {
    v10 = ATL::CComSafeArray<unsigned char,17>::SetAt(v21, i, a2 + (int)i);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1F,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v10,
        rgsabound.cElements);
  }
  v11 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v23 + 184LL))(v23, v7);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x22,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v11,
      rgsabound.cElements);
  rgsabound = 0;
  v12 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v13 = v12;
  v21[1] = v12;
  if ( !v12 )
  {
    v14 = -2147024882;
LABEL_29:
    ATL::AtlThrowImpl(v14);
  }
  v14 = SafeArrayLock(v12);
  if ( v14 < 0 )
    goto LABEL_29;
  v15 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v23 + 200LL))(v23, v13);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v15,
      rgsabound.cElements);
  result = SafeArrayUnlock(v13);
  if ( result >= 0 )
    result = SafeArrayDestroy(v13);
  if ( v7 )
  {
    result = SafeArrayUnlock(v7);
    if ( result >= 0 )
      result = SafeArrayDestroy(v7);
  }
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    result = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
  }
  v19 = v25;
  if ( v25 )
  {
    v25 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return result;
}

```

## disassembly

```asm
0x140044ba0  mov     [rsp-18h+arg_8], rbx
0x140044ba5  push    rbp
0x140044ba6  push    rsi
0x140044ba7  push    rdi
0x140044ba8  mov     rbp, rsp
0x140044bab  sub     rsp, 40h
0x140044baf  mov     rsi, rdx
0x140044bb2  mov     [rbp+arg_18], 0
0x140044bba  mov     rax, [rcx]
0x140044bbd  lea     rdx, [rbp+arg_18]
0x140044bc1  mov     rax, [rax+48h]
0x140044bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044bca  mov     rcx, [rbp+18h]; this
0x140044bce  test    eax, eax
0x140044bd0  js      loc_140044DF0
0x140044bd6  mov     [rbp+arg_10], 0
0x140044bde  mov     rcx, [rbp+arg_18]
0x140044be2  mov     rax, [rcx]
0x140044be5  lea     r8, [rbp+arg_10]
0x140044be9  mov     edx, 0Ch
0x140044bee  mov     rax, [rax+50h]
0x140044bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044bf7  mov     rcx, [rbp+18h]; this
0x140044bfb  test    eax, eax
0x140044bfd  js      loc_140044E05
0x140044c03  mov     [rbp+arg_0], 0
0x140044c0b  mov     rcx, [rbp+arg_10]
0x140044c0f  mov     rax, [rcx]
0x140044c12  lea     r8, [rbp+arg_0]
0x140044c16  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x140044c1d  mov     rax, [rax]
0x140044c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044c25  nop
0x140044c26  mov     rcx, [rbp+18h]; this
0x140044c2a  test    eax, eax
0x140044c2c  js      loc_140044E1A
0x140044c32  mov     qword ptr [rbp+rgsabound.cElements], 8
0x140044c3a  mov     ecx, 11h; vt
0x140044c3f  lea     r8, [rbp+rgsabound]; rgsabound
0x140044c43  lea     edx, [rcx-10h]; cDims
0x140044c46  call    cs:__imp_SafeArrayCreate
0x140044c4c  mov     rdi, rax
0x140044c4f  mov     [rbp+var_18], rax
0x140044c53  test    rax, rax
0x140044c56  jz      loc_140044DC1
0x140044c5c  mov     rcx, rdi; psa
0x140044c5f  call    cs:__imp_SafeArrayLock
0x140044c65  test    eax, eax
0x140044c67  js      loc_140044DC6
0x140044c6d  xor     ebx, ebx
0x140044c6f  movsxd  r8, ebx
0x140044c72  add     r8, rsi
0x140044c75  mov     edx, ebx
0x140044c77  lea     rcx, [rbp+var_18]
0x140044c7b  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x140044c80  mov     rcx, [rbp+18h]; this
0x140044c84  test    eax, eax
0x140044c86  js      loc_140044DDB
0x140044c8c  inc     ebx
0x140044c8e  cmp     ebx, 8
0x140044c91  jb      short loc_140044C6F
0x140044c93  mov     rcx, [rbp+arg_0]
0x140044c97  mov     rax, [rcx]
0x140044c9a  mov     rdx, rdi
0x140044c9d  mov     rax, [rax+0B8h]
0x140044ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044ca9  mov     rcx, [rbp+18h]; this
0x140044cad  test    eax, eax
0x140044caf  js      loc_140044E2F
0x140044cb5  mov     qword ptr [rbp+rgsabound.cElements], 0
0x140044cbd  mov     ecx, 11h; vt
0x140044cc2  lea     r8, [rbp+rgsabound]; rgsabound
0x140044cc6  lea     edx, [rcx-10h]; cDims
0x140044cc9  call    cs:__imp_SafeArrayCreate
0x140044ccf  mov     rbx, rax
0x140044cd2  mov     [rbp+var_10], rax
0x140044cd6  test    rax, rax
0x140044cd9  jz      loc_140044DCE
0x140044cdf  mov     rcx, rbx; psa
0x140044ce2  call    cs:__imp_SafeArrayLock
0x140044ce8  test    eax, eax
0x140044cea  js      loc_140044DD3
0x140044cf0  mov     rcx, [rbp+arg_0]
0x140044cf4  mov     rax, [rcx]
0x140044cf7  mov     rdx, rbx
0x140044cfa  mov     rax, [rax+0C8h]
0x140044d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044d06  mov     rcx, [rbp+18h]; this
0x140044d0a  test    eax, eax
0x140044d0c  js      loc_140044DAC
0x140044d12  mov     rcx, rbx; psa
0x140044d15  call    cs:__imp_SafeArrayUnlock
0x140044d1b  test    eax, eax
0x140044d1d  js      short loc_140044D29
0x140044d1f  mov     rcx, rbx; psa
0x140044d22  call    cs:__imp_SafeArrayDestroy
0x140044d28  nop
0x140044d29  test    rdi, rdi
0x140044d2c  jz      short loc_140044D45
0x140044d2e  mov     rcx, rdi; psa
0x140044d31  call    cs:__imp_SafeArrayUnlock
0x140044d37  test    eax, eax
0x140044d39  js      short loc_140044D45
0x140044d3b  mov     rcx, rdi; psa
0x140044d3e  call    cs:__imp_SafeArrayDestroy
0x140044d44  nop
0x140044d45  mov     rcx, [rbp+arg_0]
0x140044d49  test    rcx, rcx
0x140044d4c  jz      short loc_140044D63
0x140044d4e  mov     [rbp+arg_0], 0
0x140044d56  mov     rax, [rcx]
0x140044d59  mov     rax, [rax+10h]
0x140044d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044d62  nop
0x140044d63  mov     rcx, [rbp+arg_10]
0x140044d67  test    rcx, rcx
0x140044d6a  jz      short loc_140044D81
0x140044d6c  mov     [rbp+arg_10], 0
0x140044d74  mov     rax, [rcx]
0x140044d77  mov     rax, [rax+10h]
0x140044d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044d80  nop
0x140044d81  mov     rcx, [rbp+arg_18]
0x140044d85  test    rcx, rcx
0x140044d88  jz      short loc_140044D9F
0x140044d8a  mov     [rbp+arg_18], 0
0x140044d92  mov     rax, [rcx]
0x140044d95  mov     rax, [rax+10h]
0x140044d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044d9e  nop
0x140044d9f  mov     rbx, [rsp+40h+arg_8]
0x140044da4  add     rsp, 40h
0x140044da8  pop     rdi
0x140044da9  pop     rsi
0x140044daa  pop     rbp
0x140044dab  retn
0x140044dac  mov     r9d, eax; char *
0x140044daf  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044db6  mov     edx, 24h ; '$'; void *
0x140044dbb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044dc1  mov     eax, 8007000Eh
0x140044dc6  mov     ecx, eax; int
0x140044dc8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140044dce  mov     eax, 8007000Eh
0x140044dd3  mov     ecx, eax; int
0x140044dd5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140044ddb  mov     r9d, eax; char *
0x140044dde  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044de5  mov     edx, 1Fh; void *
0x140044dea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044df0  mov     r9d, eax; char *
0x140044df3  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044dfa  mov     edx, 14h; void *
0x140044dff  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044e05  mov     r9d, eax; char *
0x140044e08  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044e0f  mov     edx, 17h; void *
0x140044e14  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044e1a  mov     r9d, eax; char *
0x140044e1d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044e24  mov     edx, 1Ah; void *
0x140044e29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044e2f  mov     r9d, eax; char *
0x140044e32  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044e39  mov     edx, 22h ; '"'; void *
0x140044e3e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
