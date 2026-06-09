# CodeIntegrity::Management::SiPolicyView::get_secure_boolean(void * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180017b84`
- end: `0x180017ca0`
- name: `?get_secure_boolean@SiPolicyView@Management@CodeIntegrity@@QEAA_NAEBQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `284`
- prototype: `bool __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017928`

## callees

- `0x18000828c`
- `0x18000d450`
- `0x18000d470`
- `0x180017b84`
- `0x1800242f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180017bd2`
- `ntdll!RtlInitUnicodeString` at `0x180017beb`
- `ntdll!RtlInitUnicodeString` at `0x180017c04`
- `ntdll!RtlInitUnicodeString` at `0x180017bd2`
- `ntdll!RtlInitUnicodeString` at `0x180017beb`
- `ntdll!RtlInitUnicodeString` at `0x180017c04`

## string_xrefs

- `0x180017c54`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x180017c73`: `onecore\base\ci\management\dll\sipolicyview.cpp`

## pseudocode

```c
bool __fastcall CodeIntegrity::Management::SiPolicyView::get_secure_boolean(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rax
  int v8; // eax
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v11; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  int v14; // [rsp+90h] [rbp+20h] BYREF
  int v15; // [rsp+94h] [rbp+24h]
  __int64 v16; // [rsp+98h] [rbp+28h]

  v16 = a4;
  v15 = HIDWORD(a3);
  LOBYTE(v16) = 0;
  v14 = 0;
  DestinationString = 0;
  v11 = 0;
  v10 = 0;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&DestinationString, v5);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&v11, v6);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&v10, v7);
  v8 = SIPolicyQueryOneSecurityPolicy(*a2, &DestinationString, &v11, &v10);
  if ( v8 == -1073741275 )
    return 0;
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x112,
      (int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)(unsigned int)v8,
      (int)&v14);
  if ( v14 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x113,
      (int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v14);
  return (_BYTE)v16 != 0;
}

```

## disassembly

```asm
0x180017b84  mov     rax, rsp
0x180017b87  mov     [rax+10h], rbx
0x180017b8b  mov     [rax+20h], r9
0x180017b8f  mov     [rax+18h], r8
0x180017b93  mov     [rax+8], rcx
0x180017b97  push    rbp
0x180017b98  mov     rbp, rsp
0x180017b9b  sub     rsp, 70h
0x180017b9f  xorps   xmm0, xmm0
0x180017ba2  mov     byte ptr [rbp+arg_18], 0
0x180017ba6  xorps   xmm1, xmm1
0x180017ba9  mov     [rbp+arg_10], 0
0x180017bb0  lea     rcx, qword_180039780
0x180017bb7  mov     rbx, rdx
0x180017bba  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180017bbe  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x180017bc2  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180017bc6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017bcb  mov     rdx, rax; SourceString
0x180017bce  lea     rcx, [rbp+DestinationString]; DestinationString
0x180017bd2  call    cs:__imp_RtlInitUnicodeString
0x180017bd8  lea     rcx, qword_180039740
0x180017bdf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017be4  mov     rdx, rax; SourceString
0x180017be7  lea     rcx, [rbp+var_20]; DestinationString
0x180017beb  call    cs:__imp_RtlInitUnicodeString
0x180017bf1  lea     rcx, qword_1800397C0
0x180017bf8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017bfd  mov     rdx, rax; SourceString
0x180017c00  lea     rcx, [rbp+var_30]; DestinationString
0x180017c04  call    cs:__imp_RtlInitUnicodeString
0x180017c0a  mov     rcx, [rbx]
0x180017c0d  lea     rax, [rbp+arg_0]
0x180017c11  mov     [rsp+70h+var_40], rax
0x180017c16  lea     r9, [rbp+var_30]
0x180017c1a  lea     rax, [rbp+arg_18]
0x180017c1e  mov     [rbp+arg_0], 1
0x180017c26  mov     [rsp+70h+var_48], rax
0x180017c2b  lea     r8, [rbp+var_20]
0x180017c2f  lea     rax, [rbp+arg_10]
0x180017c33  lea     rdx, [rbp+DestinationString]
0x180017c37  mov     qword ptr [rsp+70h+var_50], rax; int
0x180017c3c  call    SIPolicyQueryOneSecurityPolicy
0x180017c41  cmp     eax, 0C0000225h
0x180017c46  jnz     short loc_180017C4C
0x180017c48  xor     al, al
0x180017c4a  jmp     short loc_180017C92
0x180017c4c  test    eax, eax
0x180017c4e  jns     short loc_180017C69
0x180017c50  mov     rcx, [rbp+8]; this
0x180017c54  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017c5b  mov     r9d, eax; char *
0x180017c5e  mov     edx, 112h; void *
0x180017c63  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180017c69  cmp     [rbp+arg_10], 0
0x180017c6d  jz      short loc_180017C8B
0x180017c6f  mov     rcx, [rbp+8]; this
0x180017c73  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017c7a  mov     r9d, 8000FFFFh; char *
0x180017c80  mov     edx, 113h; void *
0x180017c85  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017c8b  cmp     byte ptr [rbp+arg_18], 0
0x180017c8f  setnz   al
0x180017c92  mov     rbx, [rsp+70h+arg_8]
0x180017c9a  add     rsp, 70h
0x180017c9e  pop     rbp
0x180017c9f  retn
```
