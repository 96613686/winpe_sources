# CodeIntegrity::Management::detail::SbcpTokenView::get_binary(uint,ushort const *,ushort const *)

- ea: `0x180016b80`
- end: `0x180016c2f`
- name: `?get_binary@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$vector@EV?$allocator@E@std@@@std@@IPEBG0@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, __int64, int, const WCHAR *, PCWSTR SourceString)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009510`
- `0x180018e88`
- `0x180018f34`
- `0x180019108`
- `0x18001929c`

## callees

- `0x18000d470`
- `0x180016588`
- `0x180016b80`
- `0x18002944c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016bba`
- `ntdll!RtlInitUnicodeString` at `0x180016bc8`
- `ntdll!RtlInitUnicodeString` at `0x180016bba`
- `ntdll!RtlInitUnicodeString` at `0x180016bc8`

## string_xrefs

- `0x180016bfb`: `onecore\base\ci\management\dll\sbcptokenview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CodeIntegrity::Management::detail::SbcpTokenView::get_binary(
        __int64 a1,
        __int64 a2,
        int a3,
        const WCHAR *a4,
        PCWSTR SourceString)
{
  int RegistryBinaryInPolicy; // eax
  int v10; // [rsp+20h] [rbp-48h]
  int v11[2]; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING v12; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  __int64 v15; // [rsp+90h] [rbp+28h] BYREF

  v15 = 0;
  *(_QWORD *)v11 = 0;
  DestinationString = 0;
  v12 = 0;
  RtlInitUnicodeString(&DestinationString, a4);
  RtlInitUnicodeString(&v12, SourceString);
  RegistryBinaryInPolicy = SbGetRegistryBinaryInPolicy(
                             *(_QWORD *)(a1 + 16),
                             a3,
                             (unsigned int)&DestinationString,
                             (unsigned int)&v12,
                             (__int64)v11,
                             (__int64)&v15);
  if ( RegistryBinaryInPolicy < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB7,
      (int)"onecore\\base\\ci\\management\\dll\\sbcptokenview.cpp",
      (const char *)(unsigned int)RegistryBinaryInPolicy,
      v10);
  std::vector<unsigned char>::vector<unsigned char>(a2, v15, v15 + *(_QWORD *)v11);
  return a2;
}

```

## disassembly

```asm
0x180016b80  push    rbp
0x180016b82  push    rbx
0x180016b83  push    rsi
0x180016b84  push    rdi
0x180016b85  mov     rbp, rsp
0x180016b88  sub     rsp, 68h
0x180016b8c  mov     rsi, rdx
0x180016b8f  mov     [rbp+arg_0], 0
0x180016b97  mov     rbx, rcx
0x180016b9a  mov     qword ptr [rbp+var_30], 0
0x180016ba2  xorps   xmm0, xmm0
0x180016ba5  lea     rcx, [rbp+DestinationString]; DestinationString
0x180016ba9  xorps   xmm1, xmm1
0x180016bac  mov     rdx, r9; SourceString
0x180016baf  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180016bb3  mov     edi, r8d
0x180016bb6  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x180016bba  call    cs:__imp_RtlInitUnicodeString
0x180016bc0  mov     rdx, [rbp+SourceString]; SourceString
0x180016bc4  lea     rcx, [rbp+var_28]; DestinationString
0x180016bc8  call    cs:__imp_RtlInitUnicodeString
0x180016bce  mov     rcx, [rbx+10h]
0x180016bd2  lea     rax, [rbp+arg_0]
0x180016bd6  mov     [rsp+68h+var_40], rax
0x180016bdb  lea     r9, [rbp+var_28]
0x180016bdf  lea     rax, [rbp+var_30]
0x180016be3  mov     edx, edi
0x180016be5  lea     r8, [rbp+DestinationString]
0x180016be9  mov     qword ptr [rsp+68h+var_48], rax; int
0x180016bee  call    SbGetRegistryBinaryInPolicy
0x180016bf3  test    eax, eax
0x180016bf5  jns     short loc_180016C10
0x180016bf7  mov     rcx, [rbp+20h]; this
0x180016bfb  lea     r8, aOnecoreBaseCiM_2; "onecore\\base\\ci\\management\\dll\\sbc"...
0x180016c02  mov     r9d, eax; char *
0x180016c05  mov     edx, 0B7h; void *
0x180016c0a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180016c10  mov     rdx, [rbp+arg_0]
0x180016c14  mov     rcx, rsi
0x180016c17  mov     r8, qword ptr [rbp+var_30]
0x180016c1b  add     r8, rdx
0x180016c1e  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180016c23  mov     rax, rsi
0x180016c26  add     rsp, 68h
0x180016c2a  pop     rdi
0x180016c2b  pop     rsi
0x180016c2c  pop     rbx
0x180016c2d  pop     rbp
0x180016c2e  retn
```
