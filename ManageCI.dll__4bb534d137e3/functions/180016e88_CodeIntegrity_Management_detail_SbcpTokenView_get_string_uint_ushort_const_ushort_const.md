# CodeIntegrity::Management::detail::SbcpTokenView::get_string(uint,ushort const *,ushort const *)

- ea: `0x180016e88`
- end: `0x180016f41`
- name: `?get_string@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IPEBG0@Z`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const WCHAR *, const WCHAR *SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009610`

## callees

- `0x180009f94`
- `0x18000d470`
- `0x180016e88`
- `0x18002952c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016eb6`
- `ntdll!RtlInitUnicodeString` at `0x180016ec9`
- `ntdll!RtlInitUnicodeString` at `0x180016eb6`
- `ntdll!RtlInitUnicodeString` at `0x180016ec9`

## string_xrefs

- `0x180016f29`: `onecore\base\ci\management\dll\sbcptokenview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CodeIntegrity::Management::detail::SbcpTokenView::get_string(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const WCHAR *a4,
        const WCHAR *SourceString)
{
  __int64 v8; // rbx
  __int64 MatchingRegistryRule; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-30h] BYREF
  struct _UNICODE_STRING v15[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v15[0] = 0;
  DestinationString = 0;
  RtlInitUnicodeString(v15, a4);
  RtlInitUnicodeString(&DestinationString, SourceString);
  v8 = *(_QWORD *)(a1 + 16);
  MatchingRegistryRule = SbpFindMatchingRegistryRule(v8, a3, v15, &DestinationString);
  if ( !MatchingRegistryRule
    || (v10 = *(unsigned int *)(MatchingRegistryRule + 12),
        v11 = *(_QWORD *)(v8 + 88),
        (*(_BYTE *)(v10 + v11) & 0x1F) != 0) )
  {
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\sbcptokenview.cpp",
      (const char *)0xC0000225LL,
      v13);
  }
  std::wstring::wstring(a2, v10 + v11 + 4, (unsigned __int64)*(unsigned __int16 *)(v10 + v11 + 2) >> 1);
  return a2;
}

```

## disassembly

```asm
0x180016e88  mov     rax, rsp
0x180016e8b  mov     [rax+8], rbx
0x180016e8f  mov     [rax+10h], rsi
0x180016e93  push    rdi
0x180016e94  sub     rsp, 50h
0x180016e98  mov     rsi, rdx
0x180016e9b  mov     rbx, rcx
0x180016e9e  xorps   xmm0, xmm0
0x180016ea1  lea     rcx, [rax-20h]; DestinationString
0x180016ea5  xorps   xmm1, xmm1
0x180016ea8  mov     rdx, r9; SourceString
0x180016eab  movups  xmmword ptr [rax-20h], xmm0
0x180016eaf  mov     edi, r8d
0x180016eb2  movups  xmmword ptr [rax-30h], xmm1
0x180016eb6  call    cs:__imp_RtlInitUnicodeString
0x180016ebc  mov     rdx, [rsp+58h+SourceString]; SourceString
0x180016ec4  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x180016ec9  call    cs:__imp_RtlInitUnicodeString
0x180016ecf  mov     rbx, [rbx+10h]
0x180016ed3  lea     r9, [rsp+58h+DestinationString]
0x180016ed8  mov     rcx, rbx
0x180016edb  lea     r8, [rsp+58h+var_20]
0x180016ee0  mov     edx, edi
0x180016ee2  call    SbpFindMatchingRegistryRule
0x180016ee7  test    rax, rax
0x180016eea  jz      short loc_180016F24
0x180016eec  mov     eax, [rax+0Ch]
0x180016eef  mov     rcx, [rbx+58h]
0x180016ef3  test    byte ptr [rax+rcx], 1Fh
0x180016ef7  jnz     short loc_180016F24
0x180016ef9  movzx   r8d, word ptr [rax+rcx+2]
0x180016eff  lea     rdx, [rcx+4]
0x180016f03  add     rdx, rax
0x180016f06  shr     r8, 1
0x180016f09  mov     rcx, rsi
0x180016f0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180016f11  mov     rbx, [rsp+58h+arg_0]
0x180016f16  mov     rax, rsi
0x180016f19  mov     rsi, [rsp+58h+arg_8]
0x180016f1e  add     rsp, 50h
0x180016f22  pop     rdi
0x180016f23  retn
0x180016f24  mov     rcx, [rsp+58h]; this
0x180016f29  lea     r8, aOnecoreBaseCiM_2; "onecore\\base\\ci\\management\\dll\\sbc"...
0x180016f30  mov     r9d, 0C0000225h; char *
0x180016f36  mov     edx, 0DCh; void *
0x180016f3b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
