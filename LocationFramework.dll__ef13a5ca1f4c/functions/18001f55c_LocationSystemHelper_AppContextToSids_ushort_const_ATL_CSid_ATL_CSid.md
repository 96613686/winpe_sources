# LocationSystemHelper::AppContextToSids(ushort const *,ATL::CSid &,ATL::CSid &)

- ea: `0x18001f55c`
- end: `0x18001f745`
- name: `?AppContextToSids@LocationSystemHelper@@SAJPEBGAEAVCSid@ATL@@1@Z`
- size: `489`
- prototype: `static int(const unsigned __int16 *, struct ATL::CSid *, struct ATL::CSid *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800123f0`
- `0x18005c0ec`
- `0x180080ae8`
- `0x18009ca80`

## callees

- `0x18001e858`
- `0x18001eb88`
- `0x18001f55c`
- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020a6c`
- `0x180020af8`
- `0x180020c64`
- `0x180056544`
- `0x18008f888`
- `0x18009a8bc`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f647`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f647`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LocationSystemHelper::AppContextToSids(
        const unsigned __int16 *a1,
        struct ATL::CSid *a2,
        struct ATL::CSid *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rdx
  const WCHAR *v11; // rax
  wil::details *v12; // rcx
  const unsigned __int16 *v13; // r8
  int LastErrorFailHr; // ebx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  PSID Sid; // [rsp+20h] [rbp-29h] BYREF
  __int128 v21; // [rsp+28h] [rbp-21h] BYREF
  __int64 v22; // [rsp+38h] [rbp-11h]
  __int64 v23; // [rsp+40h] [rbp-9h]
  _BYTE v24[16]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v25; // [rsp+58h] [rbp+Fh]
  _BYTE v26[32]; // [rsp+68h] [rbp+1Fh] BYREF

  if ( !ATL::CSid::IsValid(a2) && !ATL::CSid::IsValid(a3) )
  {
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v6 = std::_WChar_traits<unsigned short>::length(a1);
    std::wstring::_Construct<1,unsigned short const *>(&v21, a1, v6);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v21, v7);
    v9 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v8, v22, 0);
    if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastErrorFailHr = -2147024809;
      goto LABEL_11;
    }
    std::wstring::substr(&v21, v26, 0);
    std::wstring::substr(&v21, v24, v9 + 1);
    Sid = 0;
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26, v10);
    if ( ConvertStringSidToSidW(v11, &Sid) && ATL::CSid::LoadAccount(a2, (struct _SID *)Sid, v13) )
    {
      LocalFree(Sid);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
      LocalFree(Sid);
      if ( LastErrorFailHr < 0 )
      {
LABEL_10:
        std::wstring::_Tidy_deallocate(v24);
        std::wstring::_Tidy_deallocate(v26);
LABEL_11:
        std::wstring::_Tidy_deallocate(&v21);
        return (unsigned int)LastErrorFailHr;
      }
    }
    std::_WChar_traits<unsigned short>::length(L"NonPackagedApp");
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24, v15);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v16, v25, v17, v18)
      || (LastErrorFailHr = LocationSystemHelper::GetSid(v24, a3), LastErrorFailHr >= 0) )
    {
      std::wstring::_Tidy_deallocate(v24);
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(&v21);
      return 0;
    }
    goto LABEL_10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f55c  mov     [rsp-8+arg_18], rbx
0x18001f561  push    rbp
0x18001f562  push    rsi
0x18001f563  push    rdi
0x18001f564  lea     rbp, [rsp-47h]
0x18001f569  sub     rsp, 90h
0x18001f570  mov     rax, cs:__security_cookie
0x18001f577  xor     rax, rsp
0x18001f57a  mov     [rbp+57h+var_18], rax
0x18001f57e  mov     rdi, r8
0x18001f581  mov     rbx, rdx
0x18001f584  mov     rsi, rcx
0x18001f587  mov     rcx, rdx; this
0x18001f58a  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18001f58f  test    al, al
0x18001f591  jnz     loc_18001F726
0x18001f597  mov     rcx, rdi; this
0x18001f59a  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18001f59f  test    al, al
0x18001f5a1  jnz     loc_18001F726
0x18001f5a7  xorps   xmm0, xmm0
0x18001f5aa  movups  [rbp+57h+var_78], xmm0
0x18001f5ae  mov     [rbp+57h+var_68], 0
0x18001f5b6  mov     [rbp+57h+var_60], 0
0x18001f5be  mov     rcx, rsi
0x18001f5c1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001f5c6  mov     r8, rax
0x18001f5c9  mov     rdx, rsi
0x18001f5cc  lea     rcx, [rbp+57h+var_78]
0x18001f5d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f5d5  nop
0x18001f5d6  mov     r9d, 5Fh ; '_'
0x18001f5dc  lea     rcx, [rbp+57h+var_78]
0x18001f5e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f5e5  mov     rcx, rax
0x18001f5e8  xor     r8d, r8d
0x18001f5eb  mov     rdx, [rbp+57h+var_68]
0x18001f5ef  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18001f5f4  mov     rsi, rax
0x18001f5f7  lea     rcx, [rax-1]
0x18001f5fb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001f5ff  ja      loc_18001F71F
0x18001f605  mov     r9, rax
0x18001f608  xor     r8d, r8d
0x18001f60b  lea     rdx, [rbp+57h+var_38]
0x18001f60f  lea     rcx, [rbp+57h+var_78]
0x18001f613  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18001f618  nop
0x18001f619  lea     r8, [rsi+1]
0x18001f61d  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001f621  lea     rdx, [rbp+57h+var_58]
0x18001f625  lea     rcx, [rbp+57h+var_78]
0x18001f629  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18001f62e  nop
0x18001f62f  mov     [rbp+57h+Sid], 0
0x18001f637  lea     rcx, [rbp+57h+var_38]
0x18001f63b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f640  mov     rcx, rax; StringSid
0x18001f643  lea     rdx, [rbp+57h+Sid]; Sid
0x18001f647  call    cs:__imp_ConvertStringSidToSidW
0x18001f64d  test    eax, eax
0x18001f64f  jnz     loc_18001F6DB
0x18001f655  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f65a  mov     ebx, eax
0x18001f65c  mov     rcx, [rbp+57h+Sid]; hMem
0x18001f660  call    cs:__imp_LocalFree
0x18001f666  test    ebx, ebx
0x18001f668  js      loc_18001F6FE
0x18001f66e  lea     r8, aNonpackagedapp; "NonPackagedApp"
0x18001f675  mov     rcx, r8
0x18001f678  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001f67d  mov     r9, rax
0x18001f680  lea     rcx, [rbp+57h+var_58]
0x18001f684  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f689  mov     rcx, rax
0x18001f68c  mov     rdx, [rbp+57h+var_48]
0x18001f690  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001f695  test    al, al
0x18001f697  jz      loc_18001F72D
0x18001f69d  lea     rcx, [rbp+57h+var_58]
0x18001f6a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f6a6  nop
0x18001f6a7  lea     rcx, [rbp+57h+var_38]
0x18001f6ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f6b0  nop
0x18001f6b1  lea     rcx, [rbp+57h+var_78]
0x18001f6b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f6ba  xor     eax, eax
0x18001f6bc  mov     rcx, [rbp+57h+var_18]
0x18001f6c0  xor     rcx, rsp; StackCookie
0x18001f6c3  call    __security_check_cookie
0x18001f6c8  mov     rbx, [rsp+0A0h+arg_18]
0x18001f6d0  add     rsp, 90h
0x18001f6d7  pop     rdi
0x18001f6d8  pop     rsi
0x18001f6d9  pop     rbp
0x18001f6da  retn
0x18001f6db  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x18001f6df  mov     rcx, rbx; this
0x18001f6e2  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18001f6e7  test    al, al
0x18001f6e9  jz      loc_18001F655
0x18001f6ef  mov     rcx, [rbp+57h+Sid]; hMem
0x18001f6f3  call    cs:__imp_LocalFree
0x18001f6f9  jmp     loc_18001F66E
0x18001f6fe  lea     rcx, [rbp+57h+var_58]
0x18001f702  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f707  nop
0x18001f708  lea     rcx, [rbp+57h+var_38]
0x18001f70c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f711  nop
0x18001f712  lea     rcx, [rbp+57h+var_78]
0x18001f716  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f71b  mov     eax, ebx
0x18001f71d  jmp     short loc_18001F6BC
0x18001f71f  mov     ebx, 80070057h
0x18001f724  jmp     short loc_18001F712
0x18001f726  mov     eax, 80070057h
0x18001f72b  jmp     short loc_18001F6BC
0x18001f72d  mov     rdx, rdi
0x18001f730  lea     rcx, [rbp+57h+var_58]
0x18001f734  call    ?GetSid@LocationSystemHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCSid@ATL@@@Z; LocationSystemHelper::GetSid(std::wstring const &,ATL::CSid &)
0x18001f739  mov     ebx, eax
0x18001f73b  test    eax, eax
0x18001f73d  js      short loc_18001F6FE
0x18001f73f  jmp     loc_18001F69D
```
