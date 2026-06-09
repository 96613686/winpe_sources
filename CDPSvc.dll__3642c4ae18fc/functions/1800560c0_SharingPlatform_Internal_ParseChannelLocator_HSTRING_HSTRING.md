# SharingPlatform::Internal::ParseChannelLocator(HSTRING__ *,HSTRING__ * *)

- ea: `0x1800560c0`
- end: `0x180056222`
- name: `?ParseChannelLocator@Internal@SharingPlatform@@YAJPEAUHSTRING__@@PEAPEAU3@@Z`
- size: `354`
- prototype: `int(SharingPlatform::Internal *__hidden this, HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004b760`

## callees

- `0x180006550`
- `0x18000a1a4`
- `0x18001177c`
- `0x1800130ec`
- `0x18001b524`
- `0x18002015c`
- `0x1800225a0`
- `0x18003e3d8`
- `0x1800560c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800561e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800561e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800560fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800560fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SharingPlatform::Internal::ParseChannelLocator(
        SharingPlatform::Internal *this,
        HSTRING *a2,
        HSTRING *a3)
{
  HSTRING v4; // r8
  PCWSTR StringRawBuffer; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rax
  unsigned int String; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rbx
  int v12; // eax
  const WCHAR *v13; // rcx
  UINT32 length; // [rsp+20h] [rbp-19h] BYREF
  PCNZWCH sourceString[2]; // [rsp+28h] [rbp-11h] BYREF
  unsigned __int64 v17[2]; // [rsp+38h] [rbp-1h]
  _QWORD v18[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  std::wstring::wstring(sourceString, a2, this);
  StringRawBuffer = WindowsGetStringRawBuffer(v4, 0);
  std::wstring::wstring(v18, StringRawBuffer);
  v6 = v18;
  if ( v18[3] > 7u )
    v6 = (_QWORD *)v18[0];
  v7 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v6, v18[2]);
  if ( v7 == -1 )
  {
    String = -2147024809;
    v9 = 2147942487LL;
    v10 = 170;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, (unsigned int)".\\helpers.cpp", (const char *)v9, length);
    goto LABEL_15;
  }
  v11 = std::wstring::substr(v18, v19, v7 + 1);
  if ( sourceString != (PCNZWCH *)v11 )
  {
    std::wstring::_Tidy_deallocate(sourceString);
    *(_OWORD *)sourceString = *(_OWORD *)v11;
    *(_OWORD *)v17 = *(_OWORD *)(v11 + 16);
    *(_QWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 24) = 7;
    *(_WORD *)v11 = 0;
  }
  std::wstring::_Tidy_deallocate(v19);
  if ( !v17[0] )
  {
    String = -2147024809;
    v9 = 2147942487LL;
    v10 = 173;
    goto LABEL_11;
  }
  v12 = ULongLongToUInt(v17[0], &length);
  String = v12;
  if ( v12 < 0 )
  {
    v9 = (unsigned int)v12;
    v10 = 176;
    goto LABEL_11;
  }
  v13 = (const WCHAR *)sourceString;
  if ( v17[1] > 7 )
    v13 = sourceString[0];
  String = WindowsCreateString(v13, length, a2);
LABEL_15:
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(sourceString);
  return String;
}

```

## disassembly

```asm
0x1800560c0  mov     [rsp-8+arg_10], rbx
0x1800560c5  mov     [rsp-8+arg_18], rdi
0x1800560ca  push    rbp
0x1800560cb  lea     rbp, [rsp-57h]
0x1800560d0  sub     rsp, 90h
0x1800560d7  mov     rax, cs:__security_cookie
0x1800560de  xor     rax, rsp
0x1800560e1  mov     [rbp+57h+var_8], rax
0x1800560e5  mov     rdi, rdx
0x1800560e8  mov     r8, rcx
0x1800560eb  lea     rcx, [rbp+57h+sourceString]
0x1800560ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800560f4  nop
0x1800560f5  xor     edx, edx; length
0x1800560f7  mov     rcx, r8; string
0x1800560fa  call    cs:__imp_WindowsGetStringRawBuffer
0x180056100  mov     rdx, rax
0x180056103  lea     rcx, [rbp+57h+var_48]
0x180056107  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005610c  nop
0x18005610d  lea     rcx, [rbp+57h+var_48]
0x180056111  cmp     [rbp+57h+var_30], 7
0x180056116  cmova   rcx, [rbp+57h+var_48]
0x18005611b  mov     rdx, [rbp+57h+var_38]
0x18005611f  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180056124  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180056128  jnz     short loc_18005613C
0x18005612a  mov     ebx, 80070057h
0x18005612f  mov     r9d, ebx
0x180056132  mov     edx, 0AAh
0x180056137  jmp     loc_1800561BE
0x18005613c  lea     r8, [rax+1]
0x180056140  lea     rdx, [rbp+57h+var_28]
0x180056144  lea     rcx, [rbp+57h+var_48]
0x180056148  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18005614d  mov     rbx, rax
0x180056150  lea     rax, [rbp+57h+sourceString]
0x180056154  cmp     rax, rbx
0x180056157  jz      short loc_180056186
0x180056159  lea     rcx, [rbp+57h+sourceString]
0x18005615d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056162  movups  xmm0, xmmword ptr [rbx]
0x180056165  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180056169  movups  xmm1, xmmword ptr [rbx+10h]
0x18005616d  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x180056171  mov     qword ptr [rbx+10h], 0
0x180056179  mov     qword ptr [rbx+18h], 7
0x180056181  xor     ecx, ecx
0x180056183  mov     [rbx], cx
0x180056186  lea     rcx, [rbp+57h+var_28]
0x18005618a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005618f  mov     rcx, [rbp+57h+var_58]; unsigned __int64
0x180056193  test    rcx, rcx
0x180056196  jnz     short loc_1800561A7
0x180056198  mov     ebx, 80070057h
0x18005619d  mov     r9d, ebx
0x1800561a0  mov     edx, 0ADh
0x1800561a5  jmp     short loc_1800561BE
0x1800561a7  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800561ab  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800561b0  mov     ebx, eax
0x1800561b2  test    eax, eax
0x1800561b4  jns     short loc_1800561D0
0x1800561b6  mov     r9d, eax; char *
0x1800561b9  mov     edx, 0B0h; void *
0x1800561be  mov     rcx, [rbp+5Fh]; this
0x1800561c2  lea     r8, aHelpersCpp; ".\\helpers.cpp"
0x1800561c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800561ce  jmp     short loc_1800561EC
0x1800561d0  lea     rcx, [rbp+57h+sourceString]
0x1800561d4  cmp     [rbp+57h+var_58+8], 7
0x1800561d9  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1800561de  mov     r8, rdi; string
0x1800561e1  mov     edx, [rbp+57h+length]; length
0x1800561e4  call    cs:__imp_WindowsCreateString
0x1800561ea  mov     ebx, eax
0x1800561ec  lea     rcx, [rbp+57h+var_48]
0x1800561f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800561f5  nop
0x1800561f6  lea     rcx, [rbp+57h+sourceString]
0x1800561fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800561ff  mov     eax, ebx
0x180056201  mov     rcx, [rbp+57h+var_8]
0x180056205  xor     rcx, rsp; StackCookie
0x180056208  call    __security_check_cookie
0x18005620d  lea     r11, [rsp+90h+var_s0]
0x180056215  mov     rbx, [r11+20h]
0x180056219  mov     rdi, [r11+28h]
0x18005621d  mov     rsp, r11
0x180056220  pop     rbp
0x180056221  retn
```
