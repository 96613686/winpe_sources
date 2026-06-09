# wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(ushort const *)

- ea: `0x140025078`
- end: `0x140025113`
- name: `??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025884`

## callees

- `0x140002d30`
- `0x140004dbc`
- `0x140007c0c`
- `0x140023b10`
- `0x140025078`
- `0x140025508`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400250c1`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400250c1`

## string_xrefs

- `0x1400250d3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v5[4]; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = L"Windows.Management.Deployment.Internal.PackageManagerInternal";
  *(_QWORD *)v5 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
  v3 = RoActivateInstance(*(_QWORD *)(v2 + 24), v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v3,
      v5[0]);
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::Internal::IPackageManagerInternal>(
    v5,
    a1);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x140025078  mov     r11, rsp
0x14002507b  push    rbx
0x14002507c  sub     rsp, 70h
0x140025080  mov     rax, cs:__security_cookie
0x140025087  xor     rax, rsp
0x14002508a  mov     [rsp+78h+var_10], rax
0x14002508f  mov     rbx, rcx
0x140025092  mov     [rsp+78h+var_48], rcx
0x140025097  lea     rax, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x14002509e  mov     [r11-48h], rax
0x1400250a2  mov     qword ptr [r11-58h], 0
0x1400250aa  lea     rdx, [r11-48h]
0x1400250ae  lea     rcx, [r11-30h]
0x1400250b2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400250b7  nop
0x1400250b8  lea     rdx, [rsp+78h+var_58]
0x1400250bd  mov     rcx, [rax+18h]
0x1400250c1  call    cs:__imp_RoActivateInstance
0x1400250c7  mov     rcx, [rsp+78h]; this
0x1400250cc  test    eax, eax
0x1400250ce  jns     short loc_1400250E5
0x1400250d0  mov     r9d, eax; char *
0x1400250d3  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400250da  mov     edx, 74Dh; void *
0x1400250df  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400250e5  mov     rdx, rbx
0x1400250e8  lea     rcx, [rsp+78h+var_58]
0x1400250ed  call    ??$query@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::Internal::IPackageManagerInternal>(void)
0x1400250f2  nop
0x1400250f3  lea     rcx, [rsp+78h+var_58]
0x1400250f8  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1400250fd  mov     rax, rbx
0x140025100  mov     rcx, [rsp+78h+var_10]
0x140025105  xor     rcx, rsp; StackCookie
0x140025108  call    __security_check_cookie
0x14002510d  add     rsp, 70h
0x140025111  pop     rbx
0x140025112  retn
```
