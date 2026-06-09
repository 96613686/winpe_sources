# CodeIntegrity::Management::detail::SbcpTokenView::get_qword(uint,ushort const *,ushort const *)

- ea: `0x180016de0`
- end: `0x180016e80`
- name: `?get_qword@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA_KIPEBG0@Z`
- size: `160`
- prototype: `unsigned __int64 __fastcall(CodeIntegrity::Management::detail::SbcpTokenView *this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800095e0`

## callees

- `0x18000d470`
- `0x180016de0`
- `0x18002952c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016e0d`
- `ntdll!RtlInitUnicodeString` at `0x180016e1b`
- `ntdll!RtlInitUnicodeString` at `0x180016e0d`
- `ntdll!RtlInitUnicodeString` at `0x180016e1b`

## string_xrefs

- `0x180016e68`: `onecore\base\ci\management\dll\sbcptokenview.cpp`

## pseudocode

```c
unsigned __int64 __fastcall CodeIntegrity::Management::detail::SbcpTokenView::get_qword(
        CodeIntegrity::Management::detail::SbcpTokenView *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rbx
  _DWORD *MatchingRegistryRule; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING v13; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v13 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&v13, a3);
  RtlInitUnicodeString(&DestinationString, a4);
  v7 = *((_QWORD *)this + 2);
  MatchingRegistryRule = SbpFindMatchingRegistryRule(v7, a2, &v13, &DestinationString);
  if ( !MatchingRegistryRule
    || (v9 = (unsigned int)MatchingRegistryRule[3], v10 = *(_QWORD *)(v7 + 88), (*(_BYTE *)(v9 + v10) & 0x1F) != 5) )
  {
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x91,
      (int)"onecore\\base\\ci\\management\\dll\\sbcptokenview.cpp",
      (const char *)0xC0000225LL,
      *(int *)&DestinationString.Length);
  }
  return *(_QWORD *)(v9 + v10 + 2);
}

```

## disassembly

```asm
0x180016de0  mov     rax, rsp
0x180016de3  mov     [rax+8], rbx
0x180016de7  mov     [rax+10h], rsi
0x180016deb  push    rdi
0x180016dec  sub     rsp, 40h
0x180016df0  mov     esi, edx
0x180016df2  mov     rdi, rcx
0x180016df5  xorps   xmm0, xmm0
0x180016df8  lea     rcx, [rax-18h]; DestinationString
0x180016dfc  xorps   xmm1, xmm1
0x180016dff  mov     rdx, r8; SourceString
0x180016e02  movups  xmmword ptr [rax-18h], xmm0
0x180016e06  mov     rbx, r9
0x180016e09  movups  xmmword ptr [rax-28h], xmm1
0x180016e0d  call    cs:__imp_RtlInitUnicodeString
0x180016e13  mov     rdx, rbx; SourceString
0x180016e16  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180016e1b  call    cs:__imp_RtlInitUnicodeString
0x180016e21  mov     rbx, [rdi+10h]
0x180016e25  lea     r9, [rsp+48h+DestinationString]
0x180016e2a  mov     rcx, rbx
0x180016e2d  lea     r8, [rsp+48h+var_18]
0x180016e32  mov     edx, esi
0x180016e34  call    SbpFindMatchingRegistryRule
0x180016e39  test    rax, rax
0x180016e3c  jz      short loc_180016E63
0x180016e3e  mov     ecx, [rax+0Ch]
0x180016e41  mov     rdx, [rbx+58h]
0x180016e45  mov     al, [rcx+rdx]
0x180016e48  and     al, 1Fh
0x180016e4a  cmp     al, 5
0x180016e4c  jnz     short loc_180016E63
0x180016e4e  mov     rax, [rcx+rdx+2]
0x180016e53  mov     rbx, [rsp+48h+arg_0]
0x180016e58  mov     rsi, [rsp+48h+arg_8]
0x180016e5d  add     rsp, 40h
0x180016e61  pop     rdi
0x180016e62  retn
0x180016e63  mov     rcx, [rsp+48h]; this
0x180016e68  lea     r8, aOnecoreBaseCiM_2; "onecore\\base\\ci\\management\\dll\\sbc"...
0x180016e6f  mov     r9d, 0C0000225h; char *
0x180016e75  mov     edx, 91h; void *
0x180016e7a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
