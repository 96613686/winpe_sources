# CodeIntegrity::Management::detail::SbcpTokenView::get_guid(uint,ushort const *,ushort const *)

- ea: `0x180016d10`
- end: `0x180016dd7`
- name: `?get_guid@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@IPEBG0@Z`
- size: `199`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, __int64, PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018b50`
- `0x180019418`

## callees

- `0x1800052e4`
- `0x18000d470`
- `0x180016754`
- `0x180016d10`
- `0x1800294a4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016d43`
- `ntdll!RtlInitUnicodeString` at `0x180016d56`
- `ntdll!RtlInitUnicodeString` at `0x180016d43`
- `ntdll!RtlInitUnicodeString` at `0x180016d56`

## string_xrefs

- `0x180016d96`: `onecore\base\ci\management\dll\sbcptokenview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall CodeIntegrity::Management::detail::SbcpTokenView::get_guid(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        PCWSTR SourceString)
{
  __int64 v7; // rbx
  int v8; // edx
  int RegistryGuidInPolicy; // eax
  int v11; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING v13[2]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = a4;
  v13[0] = 0;
  DestinationString = 0;
  RtlInitUnicodeString(v13, L"SupplementalPolicyAuthorization");
  RtlInitUnicodeString(&DestinationString, SourceString);
  std::make_unique<_GUID,,0>(&v15);
  v7 = v15;
  RegistryGuidInPolicy = SbGetRegistryGuidInPolicy(
                           *(_QWORD *)(a1 + 16),
                           v8,
                           (unsigned int)v13,
                           (unsigned int)&DestinationString,
                           v15);
  if ( RegistryGuidInPolicy < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x101,
      (int)"onecore\\base\\ci\\management\\dll\\sbcptokenview.cpp",
      (const char *)(unsigned int)RegistryGuidInPolicy,
      v11);
  v15 = 0;
  *a2 = v7;
  std::unique_ptr<_GUID>::~unique_ptr<_GUID>((void **)&v15);
  return a2;
}

```

## disassembly

```asm
0x180016d10  mov     rax, rsp
0x180016d13  mov     [rax+8], rbx
0x180016d17  mov     [rax+10h], rsi
0x180016d1b  mov     [rax+20h], r9
0x180016d1f  push    rdi
0x180016d20  sub     rsp, 60h
0x180016d24  mov     rsi, rdx
0x180016d27  mov     rdi, rcx
0x180016d2a  xorps   xmm0, xmm0
0x180016d2d  movups  xmmword ptr [rax-20h], xmm0
0x180016d31  xorps   xmm1, xmm1
0x180016d34  movups  xmmword ptr [rax-30h], xmm1
0x180016d38  lea     rdx, SourceString; "SupplementalPolicyAuthorization"
0x180016d3f  lea     rcx, [rax-20h]; DestinationString
0x180016d43  call    cs:__imp_RtlInitUnicodeString
0x180016d49  mov     rdx, [rsp+68h+SourceString]; SourceString
0x180016d51  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180016d56  call    cs:__imp_RtlInitUnicodeString
0x180016d5c  lea     rcx, [rsp+68h+arg_18]
0x180016d64  call    ??$make_unique@U_GUID@@$$V$0A@@std@@YA?AV?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@0@XZ; std::make_unique<_GUID,,0>(void)
0x180016d69  nop
0x180016d6a  mov     rbx, [rsp+68h+arg_18]
0x180016d72  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180016d77  lea     r9, [rsp+68h+DestinationString]
0x180016d7c  lea     r8, [rsp+68h+var_20]
0x180016d81  mov     rcx, [rdi+10h]
0x180016d85  call    SbGetRegistryGuidInPolicy
0x180016d8a  mov     rcx, [rsp+68h]; this
0x180016d8f  test    eax, eax
0x180016d91  jns     short loc_180016DA8
0x180016d93  mov     r9d, eax; char *
0x180016d96  lea     r8, aOnecoreBaseCiM_2; "onecore\\base\\ci\\management\\dll\\sbc"...
0x180016d9d  mov     edx, 101h; void *
0x180016da2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180016da8  mov     [rsp+68h+arg_18], 0
0x180016db4  mov     [rsi], rbx
0x180016db7  lea     rcx, [rsp+68h+arg_18]
0x180016dbf  call    ??1?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@QEAA@XZ; std::unique_ptr<_GUID>::~unique_ptr<_GUID>(void)
0x180016dc4  mov     rax, rsi
0x180016dc7  mov     rbx, [rsp+68h+arg_0]
0x180016dcc  mov     rsi, [rsp+68h+arg_8]
0x180016dd1  add     rsp, 60h
0x180016dd5  pop     rdi
0x180016dd6  retn
```
