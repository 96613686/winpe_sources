# _anonymous_namespace_::AddCommandLine

- ea: `0x1400449e4`
- end: `0x140044b99`
- name: `_anonymous_namespace_::AddCommandLine`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140044e50`
- `0x140045230`
- `0x140045970`
- `0x140045d80`

## callees

- `0x14000a6e4`
- `0x14003d008`
- `0x1400449e4`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140044a8a`
- `OLEAUT32!__imp_SysAllocString` at `0x140044a8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140044ac5`
- `OLEAUT32!__imp_SysFreeString` at `0x140044ac5`

## string_xrefs

- `0x140044b87`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140044b36`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044b4b`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044b60`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140044b75`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall anonymous_namespace_::AddCommandLine(__int64 a1, const OLECHAR *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // eax
  _QWORD *v6; // rdi
  __int64 v7; // rsi
  BSTR v8; // rax
  const char *v9; // r9
  OLECHAR *v10; // rbx
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v14; // rcx
  _QWORD v15[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  _QWORD *v17; // [rsp+60h] [rbp+30h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD **); // [rsp+68h] [rbp+38h] BYREF

  v15[0] = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 136LL))(a1, v15);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3D,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v3,
      v15[0]);
  v18 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)v15[0] + 64LL))(v15[0], 1, &v18);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      v15[0]);
  v17 = 0;
  v5 = (**v18)(v18, &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047, &v17);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x43,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v5,
      v15[0]);
  v6 = v17;
  v7 = *v17;
  v8 = SysAllocString(a2);
  v10 = v8;
  v15[1] = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v11 = (*(__int64 (__fastcall **)(_QWORD *, BSTR))(v7 + 104))(v6, v8);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x45,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v11,
      v15[0]);
  SysFreeString(v10);
  v12 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
  }
  v13 = v18;
  if ( v18 )
  {
    v18 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v13)[2])(v13);
  }
  v14 = v15[0];
  if ( v15[0] )
  {
    v15[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
}

```

## disassembly

```asm
0x1400449e4  mov     [rsp-18h+arg_8], rbx
0x1400449e9  push    rbp
0x1400449ea  push    rsi
0x1400449eb  push    rdi
0x1400449ec  mov     rbp, rsp
0x1400449ef  sub     rsp, 30h
0x1400449f3  mov     rbx, rdx
0x1400449f6  mov     [rbp+arg_0], 0
0x1400449fd  mov     [rbp+var_10], 0
0x140044a05  mov     rax, [rcx]
0x140044a08  lea     rdx, [rbp+var_10]
0x140044a0c  mov     rax, [rax+88h]
0x140044a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044a18  mov     rcx, [rbp+18h]; this
0x140044a1c  test    eax, eax
0x140044a1e  js      loc_140044B48
0x140044a24  mov     [rbp+arg_18], 0
0x140044a2c  mov     rcx, [rbp+var_10]
0x140044a30  mov     rax, [rcx]
0x140044a33  lea     r8, [rbp+arg_18]
0x140044a37  mov     edx, 1
0x140044a3c  mov     rax, [rax+40h]
0x140044a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044a45  mov     rcx, [rbp+18h]; this
0x140044a49  test    eax, eax
0x140044a4b  js      loc_140044B5D
0x140044a51  mov     [rbp+arg_10], 0
0x140044a59  mov     rcx, [rbp+arg_18]
0x140044a5d  mov     rax, [rcx]
0x140044a60  lea     r8, [rbp+arg_10]
0x140044a64  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x140044a6b  mov     rax, [rax]
0x140044a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044a73  nop
0x140044a74  mov     rcx, [rbp+18h]; this
0x140044a78  test    eax, eax
0x140044a7a  js      loc_140044B72
0x140044a80  mov     rdi, [rbp+arg_10]
0x140044a84  mov     rsi, [rdi]
0x140044a87  mov     rcx, rbx; psz
0x140044a8a  call    cs:__imp_SysAllocString
0x140044a90  mov     rbx, rax
0x140044a93  mov     [rbp+var_8], rax
0x140044a97  mov     [rbp+arg_0], 1
0x140044a9e  mov     rcx, [rbp+18h]; this
0x140044aa2  test    rax, rax
0x140044aa5  jz      loc_140044B87
0x140044aab  mov     rdx, rax
0x140044aae  mov     rcx, rdi
0x140044ab1  mov     rax, [rsi+68h]
0x140044ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044aba  mov     rcx, [rbp+18h]; this
0x140044abe  test    eax, eax
0x140044ac0  js      short loc_140044B33
0x140044ac2  mov     rcx, rbx; bstrString
0x140044ac5  call    cs:__imp_SysFreeString
0x140044acb  nop
0x140044acc  mov     rcx, [rbp+arg_10]
0x140044ad0  test    rcx, rcx
0x140044ad3  jz      short loc_140044AEA
0x140044ad5  mov     [rbp+arg_10], 0
0x140044add  mov     rax, [rcx]
0x140044ae0  mov     rax, [rax+10h]
0x140044ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044ae9  nop
0x140044aea  mov     rcx, [rbp+arg_18]
0x140044aee  test    rcx, rcx
0x140044af1  jz      short loc_140044B08
0x140044af3  mov     [rbp+arg_18], 0
0x140044afb  mov     rax, [rcx]
0x140044afe  mov     rax, [rax+10h]
0x140044b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b07  nop
0x140044b08  mov     rcx, [rbp+var_10]
0x140044b0c  test    rcx, rcx
0x140044b0f  jz      short loc_140044B26
0x140044b11  mov     [rbp+var_10], 0
0x140044b19  mov     rax, [rcx]
0x140044b1c  mov     rax, [rax+10h]
0x140044b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b25  nop
0x140044b26  mov     rbx, [rsp+30h+arg_8]
0x140044b2b  add     rsp, 30h
0x140044b2f  pop     rdi
0x140044b30  pop     rsi
0x140044b31  pop     rbp
0x140044b32  retn
0x140044b33  mov     r9d, eax; char *
0x140044b36  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044b3d  mov     edx, 45h ; 'E'; void *
0x140044b42  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044b48  mov     r9d, eax; char *
0x140044b4b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044b52  mov     edx, 3Dh ; '='; void *
0x140044b57  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044b5d  mov     r9d, eax; char *
0x140044b60  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044b67  mov     edx, 40h ; '@'; void *
0x140044b6c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044b72  mov     r9d, eax; char *
0x140044b75  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044b7c  mov     edx, 43h ; 'C'; void *
0x140044b81  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140044b87  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140044b8e  mov     edx, 15F3h; void *
0x140044b93  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
