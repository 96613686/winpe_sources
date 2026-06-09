# RetailDemoUtil::AddUserToGroup(IPropertyStore *,ulong)

- ea: `0x18002f92c`
- end: `0x18002fa81`
- name: `?AddUserToGroup@RetailDemoUtil@@YAXPEAUIPropertyStore@@K@Z`
- size: `341`
- prototype: `void __fastcall(RetailDemoUtil *__hidden this, struct IPropertyStore *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021830`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x18002f92c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f974`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f974`

## string_xrefs

- `0x18002fa30`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18002fa45`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18002fa5a`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18002fa6f`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RetailDemoUtil::AddUserToGroup(RetailDemoUtil *this, struct IPropertyStore *a2, __int64 a3)
{
  unsigned int v3; // esi
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  int ppv; // [rsp+20h] [rbp-30h]
  __int16 v18; // [rsp+30h] [rbp-20h] BYREF
  RetailDemoUtil *v19; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  LPVOID v22; // [rsp+88h] [rbp+38h] BYREF

  v3 = (unsigned int)a2;
  v22 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, a2, a3);
  v5 = CoCreateInstance(&CLSID_LocalGroups, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &v22);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v21 = 0;
  v8 = v22;
  v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v22 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21, v6, v7);
  v10 = v9(v8, v3, &v21);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v10,
      ppv);
  v18 = 13;
  v19 = this;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int16 *))(*(_QWORD *)v21 + 48LL))(
          v21,
          PKEY_SAM_GroupMembers,
          &v18);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v12,
      ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21, v13, v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, v15, v16);
}

```

## disassembly

```asm
0x18002f92c  mov     [rsp-18h+arg_0], rbx
0x18002f931  mov     [rsp-18h+arg_8], rsi
0x18002f936  push    rbp
0x18002f937  push    rdi
0x18002f938  push    r14
0x18002f93a  mov     rbp, rsp
0x18002f93d  sub     rsp, 50h
0x18002f941  mov     esi, edx
0x18002f943  mov     r14, rcx
0x18002f946  mov     [rbp+arg_18], 0
0x18002f94e  lea     rcx, [rbp+arg_18]
0x18002f952  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f957  lea     rax, [rbp+arg_18]
0x18002f95b  mov     qword ptr [rsp+50h+ppv], rax; int
0x18002f960  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x18002f967  xor     edx, edx; pUnkOuter
0x18002f969  lea     r8d, [rdx+3]; dwClsContext
0x18002f96d  lea     rcx, CLSID_LocalGroups; rclsid
0x18002f974  call    cs:__imp_CoCreateInstance
0x18002f97a  mov     rcx, [rbp+18h]; this
0x18002f97e  test    eax, eax
0x18002f980  js      loc_18002FA42
0x18002f986  mov     [rbp+arg_10], 0
0x18002f98e  mov     rdi, [rbp+arg_18]
0x18002f992  mov     rax, [rdi]
0x18002f995  mov     rbx, [rax+50h]
0x18002f999  lea     rcx, [rbp+arg_10]
0x18002f99d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f9a2  lea     r8, [rbp+arg_10]
0x18002f9a6  mov     edx, esi
0x18002f9a8  mov     rcx, rdi
0x18002f9ab  mov     rax, rbx
0x18002f9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9b3  mov     rcx, [rbp+18h]; this
0x18002f9b7  test    eax, eax
0x18002f9b9  js      loc_18002FA57
0x18002f9bf  mov     eax, 0Dh
0x18002f9c4  mov     [rbp+var_20], ax
0x18002f9c8  mov     [rbp+var_18], r14
0x18002f9cc  mov     rcx, [rbp+arg_10]
0x18002f9d0  mov     rax, [rcx]
0x18002f9d3  lea     r8, [rbp+var_20]
0x18002f9d7  lea     rdx, PKEY_SAM_GroupMembers
0x18002f9de  mov     rax, [rax+30h]
0x18002f9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9e7  mov     rcx, [rbp+18h]; this
0x18002f9eb  test    eax, eax
0x18002f9ed  js      short loc_18002FA6C
0x18002f9ef  mov     rcx, [rbp+arg_10]
0x18002f9f3  mov     rax, [rcx]
0x18002f9f6  mov     rax, [rax+38h]
0x18002f9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9ff  mov     rcx, [rbp+18h]; this
0x18002fa03  test    eax, eax
0x18002fa05  js      short loc_18002FA2D
0x18002fa07  lea     rcx, [rbp+arg_10]
0x18002fa0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002fa10  nop
0x18002fa11  lea     rcx, [rbp+arg_18]
0x18002fa15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002fa1a  mov     rbx, [rsp+50h+arg_0]
0x18002fa1f  mov     rsi, [rsp+50h+arg_8]
0x18002fa24  add     rsp, 50h
0x18002fa28  pop     r14
0x18002fa2a  pop     rdi
0x18002fa2b  pop     rbp
0x18002fa2c  retn
0x18002fa2d  mov     r9d, eax; char *
0x18002fa30  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fa37  mov     edx, 2A4h; void *
0x18002fa3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fa42  mov     r9d, eax; char *
0x18002fa45  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fa4c  mov     edx, 29Eh; void *
0x18002fa51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fa57  mov     r9d, eax; char *
0x18002fa5a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fa61  mov     edx, 2A1h; void *
0x18002fa66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fa6c  mov     r9d, eax; char *
0x18002fa6f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fa76  mov     edx, 2A3h; void *
0x18002fa7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
