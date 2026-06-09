# CodeIntegrity::Management::detail::SbcpTokenView::get_dword(uint,ushort const *,ushort const *)

- ea: `0x180016c38`
- end: `0x180016cd7`
- name: `?get_dword@SbcpTokenView@detail@Management@CodeIntegrity@@IEAAIIPEBG0@Z`
- size: `159`
- prototype: `__int64 __fastcall(CodeIntegrity::Management::detail::SbcpTokenView *this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800095b0`
- `0x180016ce0`
- `0x18001929c`

## callees

- `0x18000d470`
- `0x180016c38`
- `0x18002952c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016c65`
- `ntdll!RtlInitUnicodeString` at `0x180016c73`
- `ntdll!RtlInitUnicodeString` at `0x180016c65`
- `ntdll!RtlInitUnicodeString` at `0x180016c73`

## string_xrefs

- `0x180016cbf`: `onecore\base\ci\management\dll\sbcptokenview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CodeIntegrity::Management::detail::SbcpTokenView::get_dword(
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
    || (v9 = (unsigned int)MatchingRegistryRule[3], v10 = *(_QWORD *)(v7 + 88), (*(_BYTE *)(v9 + v10) & 0x1F) != 2) )
  {
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x6B,
      (int)"onecore\\base\\ci\\management\\dll\\sbcptokenview.cpp",
      (const char *)0xC0000225LL,
      *(int *)&DestinationString.Length);
  }
  return *(unsigned int *)(v9 + v10 + 2);
}

```

## disassembly

```asm
0x180016c38  mov     rax, rsp
0x180016c3b  mov     [rax+8], rbx
0x180016c3f  mov     [rax+10h], rsi
0x180016c43  push    rdi
0x180016c44  sub     rsp, 40h
0x180016c48  mov     esi, edx
0x180016c4a  mov     rdi, rcx
0x180016c4d  xorps   xmm0, xmm0
0x180016c50  lea     rcx, [rax-18h]; DestinationString
0x180016c54  xorps   xmm1, xmm1
0x180016c57  mov     rdx, r8; SourceString
0x180016c5a  movups  xmmword ptr [rax-18h], xmm0
0x180016c5e  mov     rbx, r9
0x180016c61  movups  xmmword ptr [rax-28h], xmm1
0x180016c65  call    cs:__imp_RtlInitUnicodeString
0x180016c6b  mov     rdx, rbx; SourceString
0x180016c6e  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180016c73  call    cs:__imp_RtlInitUnicodeString
0x180016c79  mov     rbx, [rdi+10h]
0x180016c7d  lea     r9, [rsp+48h+DestinationString]
0x180016c82  mov     rcx, rbx
0x180016c85  lea     r8, [rsp+48h+var_18]
0x180016c8a  mov     edx, esi
0x180016c8c  call    SbpFindMatchingRegistryRule
0x180016c91  test    rax, rax
0x180016c94  jz      short loc_180016CBA
0x180016c96  mov     ecx, [rax+0Ch]
0x180016c99  mov     rdx, [rbx+58h]
0x180016c9d  mov     al, [rcx+rdx]
0x180016ca0  and     al, 1Fh
0x180016ca2  cmp     al, 2
0x180016ca4  jnz     short loc_180016CBA
0x180016ca6  mov     eax, [rcx+rdx+2]
0x180016caa  mov     rbx, [rsp+48h+arg_0]
0x180016caf  mov     rsi, [rsp+48h+arg_8]
0x180016cb4  add     rsp, 40h
0x180016cb8  pop     rdi
0x180016cb9  retn
0x180016cba  mov     rcx, [rsp+48h]; this
0x180016cbf  lea     r8, aOnecoreBaseCiM_2; "onecore\\base\\ci\\management\\dll\\sbc"...
0x180016cc6  mov     r9d, 0C0000225h; char *
0x180016ccc  mov     edx, 6Bh ; 'k'; void *
0x180016cd1  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
