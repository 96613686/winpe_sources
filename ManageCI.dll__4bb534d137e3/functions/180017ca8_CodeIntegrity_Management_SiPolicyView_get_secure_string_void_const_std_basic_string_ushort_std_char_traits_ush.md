# CodeIntegrity::Management::SiPolicyView::get_secure_string(void * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180017ca8`
- end: `0x180017ea4`
- name: `?get_secure_string@SiPolicyView@Management@CodeIntegrity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAXAEBV45@11@Z`
- size: `508`
- prototype: `void *__fastcall(__int64, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017928`

## callees

- `0x180002a90`
- `0x18000828c`
- `0x180008474`
- `0x18000a308`
- `0x18000d450`
- `0x18000d470`
- `0x18000def4`
- `0x18001097c`
- `0x1800109b4`
- `0x18001790c`
- `0x180017ca8`
- `0x1800242f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180017d0e`
- `ntdll!RtlInitUnicodeString` at `0x180017d27`
- `ntdll!RtlInitUnicodeString` at `0x180017d3c`
- `ntdll!RtlInitUnicodeString` at `0x180017d0e`
- `ntdll!RtlInitUnicodeString` at `0x180017d27`
- `ntdll!RtlInitUnicodeString` at `0x180017d3c`

## string_xrefs

- `0x180017d98`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x180017dbf`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x180017e1d`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x180017e44`: `onecore\base\ci\management\dll\sipolicyview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall CodeIntegrity::Management::SiPolicyView::get_secure_string(__int64 a1, void *a2, _QWORD *a3)
{
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  void *v10; // rbx
  int v11; // eax
  unsigned __int64 v12; // rdx
  int v14; // [rsp+40h] [rbp-49h] BYREF
  __int64 v15; // [rsp+48h] [rbp-41h]
  void *v16[2]; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING v17; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v18; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v16[0] = a2;
  std::wstring::wstring(v20, a2);
  DestinationString = 0;
  v18 = 0;
  v17 = 0;
  v14 = 3;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&DestinationString, v5);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&v18, v6);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  RtlInitUnicodeString(&v17, v7);
  v15 = 0;
  v8 = SIPolicyQueryOneSecurityPolicy(*a3, &DestinationString, &v18, &v17);
  if ( v8 == -1073741275 )
  {
    std::wstring::wstring(a2, v9);
  }
  else
  {
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x137,
        (int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
        (const char *)(unsigned int)v8,
        (int)&v14);
    std::make_unique<unsigned char [0],0>(v16, v15 + 2);
    v10 = v16[0];
    v11 = SIPolicyQueryOneSecurityPolicy(*a3, &DestinationString, &v18, &v17);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x145,
        (int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
        (const char *)(unsigned int)v11,
        (int)&v14);
    std::wstring::assign(v20, v10);
    std::wstring::wstring(a2, v20);
    std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(v16, v12);
  }
  std::wstring::_Tidy_deallocate((__int64)v20);
  return a2;
}

```

## disassembly

```asm
0x180017ca8  mov     [rsp-8+arg_0], rbx
0x180017cad  push    rbp
0x180017cae  push    rsi
0x180017caf  push    rdi
0x180017cb0  lea     rbp, [rsp-37h]
0x180017cb5  sub     rsp, 0C0h
0x180017cbc  mov     rax, cs:__security_cookie
0x180017cc3  xor     rax, rsp
0x180017cc6  mov     [rbp+47h+var_20], rax
0x180017cca  mov     rsi, r8
0x180017ccd  mov     rdi, rdx
0x180017cd0  mov     [rbp+47h+var_80], rdx
0x180017cd4  mov     rbx, [rbp+47h+arg_28]
0x180017cd8  lea     rcx, [rbp+47h+var_40]
0x180017cdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017ce1  nop
0x180017ce2  xorps   xmm1, xmm1
0x180017ce5  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x180017ce9  xorps   xmm0, xmm0
0x180017cec  movups  xmmword ptr [rbp+47h+var_60.Length], xmm0
0x180017cf0  movups  xmmword ptr [rbp+47h+var_70.Length], xmm1
0x180017cf4  mov     [rbp+47h+var_90], 3
0x180017cfb  lea     rcx, qword_1800397A0
0x180017d02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017d07  mov     rdx, rax; SourceString
0x180017d0a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180017d0e  call    cs:__imp_RtlInitUnicodeString
0x180017d14  lea     rcx, qword_180039760
0x180017d1b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017d20  mov     rdx, rax; SourceString
0x180017d23  lea     rcx, [rbp+47h+var_60]; DestinationString
0x180017d27  call    cs:__imp_RtlInitUnicodeString
0x180017d2d  mov     rcx, rbx
0x180017d30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017d35  mov     rdx, rax; SourceString
0x180017d38  lea     rcx, [rbp+47h+var_70]; DestinationString
0x180017d3c  call    cs:__imp_RtlInitUnicodeString
0x180017d42  mov     [rbp+47h+var_88], 0
0x180017d4a  lea     rax, [rbp+47h+var_88]
0x180017d4e  mov     [rsp+0D0h+var_A0], rax
0x180017d53  mov     [rsp+0D0h+var_A8], 0
0x180017d5c  lea     rax, [rbp+47h+var_90]
0x180017d60  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180017d65  lea     r9, [rbp+47h+var_70]
0x180017d69  lea     r8, [rbp+47h+var_60]
0x180017d6d  lea     rdx, [rbp+47h+DestinationString]
0x180017d71  mov     rcx, [rsi]
0x180017d74  call    SIPolicyQueryOneSecurityPolicy
0x180017d79  cmp     eax, 0C0000225h
0x180017d7e  jnz     short loc_180017D8D
0x180017d80  mov     rcx, rdi
0x180017d83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017d88  jmp     loc_180017E79
0x180017d8d  mov     rcx, [rbp+4Fh]; this
0x180017d91  test    eax, eax
0x180017d93  jns     short loc_180017DAA
0x180017d95  mov     r9d, eax; char *
0x180017d98  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017d9f  mov     edx, 137h; void *
0x180017da4  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180017daa  cmp     [rbp+47h+var_90], 3
0x180017dae  setnz   al
0x180017db1  mov     rcx, [rbp+4Fh]; this
0x180017db5  test    al, al
0x180017db7  jz      short loc_180017DD1
0x180017db9  mov     r9d, 8000FFFFh; char *
0x180017dbf  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017dc6  mov     edx, 138h; void *
0x180017dcb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017dd1  mov     rdx, [rbp+47h+var_88]
0x180017dd5  add     rdx, 2
0x180017dd9  lea     rcx, [rbp+47h+var_80]
0x180017ddd  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180017de2  nop
0x180017de3  lea     rax, [rbp+47h+var_88]
0x180017de7  mov     [rsp+0D0h+var_A0], rax
0x180017dec  mov     rbx, [rbp+47h+var_80]
0x180017df0  mov     [rsp+0D0h+var_A8], rbx
0x180017df5  lea     rax, [rbp+47h+var_90]
0x180017df9  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180017dfe  lea     r9, [rbp+47h+var_70]
0x180017e02  lea     r8, [rbp+47h+var_60]
0x180017e06  lea     rdx, [rbp+47h+DestinationString]
0x180017e0a  mov     rcx, [rsi]
0x180017e0d  call    SIPolicyQueryOneSecurityPolicy
0x180017e12  mov     rcx, [rbp+4Fh]; this
0x180017e16  test    eax, eax
0x180017e18  jns     short loc_180017E2F
0x180017e1a  mov     r9d, eax; char *
0x180017e1d  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017e24  mov     edx, 145h; void *
0x180017e29  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180017e2f  cmp     [rbp+47h+var_90], 3
0x180017e33  setnz   al
0x180017e36  mov     rcx, [rbp+4Fh]; this
0x180017e3a  test    al, al
0x180017e3c  jz      short loc_180017E56
0x180017e3e  mov     r9d, 8000FFFFh; char *
0x180017e44  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017e4b  mov     edx, 146h; void *
0x180017e50  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017e56  mov     rdx, rbx
0x180017e59  lea     rcx, [rbp+47h+var_40]
0x180017e5d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180017e62  lea     rdx, [rbp+47h+var_40]
0x180017e66  mov     rcx, rdi
0x180017e69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180017e6e  nop
0x180017e6f  lea     rcx, [rbp+47h+var_80]
0x180017e73  call    ??1?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$default_delete@$$BY0A@U_SIPOLICY_FILE_ITEM@@@std@@@std@@QEAA@XZ; std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(void)
0x180017e78  nop
0x180017e79  lea     rcx, [rbp+47h+var_40]
0x180017e7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017e82  mov     rax, rdi
0x180017e85  mov     rcx, [rbp+47h+var_20]
0x180017e89  xor     rcx, rsp; StackCookie
0x180017e8c  call    __security_check_cookie
0x180017e91  mov     rbx, [rsp+0D0h+arg_0]
0x180017e99  add     rsp, 0C0h
0x180017ea0  pop     rdi
0x180017ea1  pop     rsi
0x180017ea2  pop     rbp
0x180017ea3  retn
```
