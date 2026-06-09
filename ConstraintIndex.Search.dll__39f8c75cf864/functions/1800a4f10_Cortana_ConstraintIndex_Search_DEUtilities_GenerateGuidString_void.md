# Cortana::ConstraintIndex::Search::DEUtilities::GenerateGuidString(void)

- ea: `0x1800a4f10`
- end: `0x1800a4fa8`
- name: `?GenerateGuidString@DEUtilities@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@XZ`
- size: `152`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800884b4`
- `0x1800a5448`

## callees

- `0x1800049e0`
- `0x18000617a`
- `0x18003ff8c`
- `0x1800999d0`
- `0x1800a457c`
- `0x1800a4f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a4f36`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a4f36`
- `wincorlib!?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ` at `0x1800a4f6c`
- `wincorlib!?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ` at `0x1800a4f6c`

## string_xrefs

- `0x1800a4f48`: `shellcommon\shell\cortana\constraintindex\src\Search\DEUtilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Cortana::ConstraintIndex::Search::DEUtilities::GenerateGuidString()
{
  HRESULT v0; // eax
  __int64 v1; // rax
  __int64 v2; // rbx
  int v4; // [rsp+20h] [rbp-38h]
  HSTRING v5; // [rsp+20h] [rbp-38h]
  _BYTE v6[16]; // [rsp+28h] [rbp-30h] BYREF
  GUID pguid; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  pguid = 0;
  v0 = CoCreateGuid(&pguid);
  if ( v0 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\DEUtilities.cpp",
      (const char *)(unsigned int)v0,
      v4);
  v1 = Platform::Guid::Guid((Platform::Guid *)v6, &pguid);
  v5 = (HSTRING)Platform::Guid::ToString(v1);
  v2 = __abi_winrt_ptrto_string_ctor(v5);
  WindowsDeleteString_0(v5);
  return v2;
}

```

## disassembly

```asm
0x1800a4f10  mov     [rsp+arg_0], rbx
0x1800a4f15  push    rdi
0x1800a4f16  sub     rsp, 50h
0x1800a4f1a  mov     rax, cs:__security_cookie
0x1800a4f21  xor     rax, rsp
0x1800a4f24  mov     [rsp+58h+var_10], rax
0x1800a4f29  xorps   xmm0, xmm0
0x1800a4f2c  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x1800a4f31  lea     rcx, [rsp+58h+pguid]; pguid
0x1800a4f36  call    cs:__imp_CoCreateGuid
0x1800a4f3c  mov     rcx, [rsp+58h]; this
0x1800a4f41  test    eax, eax
0x1800a4f43  jns     short loc_1800A4F5A
0x1800a4f45  mov     r9d, eax; char *
0x1800a4f48  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\cortana\\constraint"...
0x1800a4f4f  mov     edx, 120h; void *
0x1800a4f54  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a4f5a  lea     rdx, [rsp+58h+pguid]; struct _GUID *
0x1800a4f5f  lea     rcx, [rsp+58h+var_30]; this
0x1800a4f64  call    ??0Guid@Platform@@QEAA@AEBU_GUID@@@Z; Platform::Guid::Guid(_GUID const &)
0x1800a4f69  mov     rcx, rax
0x1800a4f6c  call    cs:__imp_?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ; Platform::Guid::ToString(void)
0x1800a4f72  mov     rdi, rax
0x1800a4f75  mov     [rsp+58h+var_38], rax
0x1800a4f7a  mov     rcx, rax
0x1800a4f7d  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800a4f82  mov     rbx, rax
0x1800a4f85  mov     rcx, rdi; string
0x1800a4f88  call    WindowsDeleteString_0
0x1800a4f8d  mov     rax, rbx
0x1800a4f90  mov     rcx, [rsp+58h+var_10]
0x1800a4f95  xor     rcx, rsp; StackCookie
0x1800a4f98  call    __security_check_cookie
0x1800a4f9d  mov     rbx, [rsp+58h+arg_0]
0x1800a4fa2  add     rsp, 50h
0x1800a4fa6  pop     rdi
0x1800a4fa7  retn
```
