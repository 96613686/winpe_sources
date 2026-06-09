# GetSharedPCRegistryValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18002297c`
- end: `0x180022aaf`
- name: `?GetSharedPCRegistryValue@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c974`
- `0x1800115f0`
- `0x18001cb4c`
- `0x18001d3f0`
- `0x18001f5c0`
- `0x1800215d8`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000cd50`
- `0x180013dcc`
- `0x1800226e4`
- `0x18002297c`
- `0x180022ab8`
- `0x180022f0c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022a15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022a15`

## string_xrefs

- `0x1800229be`: `SharedPCConfiguration`

## pseudocode

```c
__int64 __fastcall GetSharedPCRegistryValue(__int64 a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v6; // rax
  int v7; // edi
  _BYTE *v8; // rcx
  _BYTE v10[8]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp+17h] BYREF

  std::wstring::wstring(v14, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC");
  std::wstring::wstring(v13, L"SharedPCConfiguration");
  GetPersistedRegistryLocationTargetPath(v12, v13, v14);
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v14);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  v7 = CompareStringOrdinal(L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC", -1, v6, -1, 1);
  GetValueIfExists(v10, v12, a1, a2);
  if ( v10[4] )
  {
    v8 = v10;
LABEL_6:
    a3 = *(_DWORD *)std::optional<unsigned long>::value(v8);
    goto LABEL_7;
  }
  if ( v7 != 2 )
  {
    std::wstring::wstring(v15, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC");
    GetValueIfExists(v11, v15, a1, a2);
    std::wstring::_Tidy_deallocate(v15);
    if ( v11[4] )
    {
      v8 = v11;
      goto LABEL_6;
    }
  }
LABEL_7:
  std::wstring::_Tidy_deallocate(v12);
  return a3;
}

```

## disassembly

```asm
0x18002297c  mov     [rsp-8+arg_10], rbx
0x180022981  mov     [rsp-8+arg_18], rsi
0x180022986  push    rbp
0x180022987  push    rdi
0x180022988  push    r14
0x18002298a  lea     rbp, [rsp-47h]
0x18002298f  sub     rsp, 0D0h
0x180022996  mov     rax, cs:__security_cookie
0x18002299d  xor     rax, rsp
0x1800229a0  mov     [rbp+57h+var_20], rax
0x1800229a4  mov     ebx, r8d
0x1800229a7  mov     r14, rdx
0x1800229aa  mov     rsi, rcx
0x1800229ad  lea     rdx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800229b4  lea     rcx, [rbp+57h+var_60]
0x1800229b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800229bd  nop
0x1800229be  lea     rdx, aSharedpcconfig; "SharedPCConfiguration"
0x1800229c5  lea     rcx, [rbp+57h+var_80]
0x1800229c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800229ce  nop
0x1800229cf  lea     r8, [rbp+57h+var_60]
0x1800229d3  lea     rdx, [rbp+57h+var_80]
0x1800229d7  lea     rcx, [rbp+57h+var_A0]
0x1800229db  call    ?GetPersistedRegistryLocationTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@0@Z; GetPersistedRegistryLocationTargetPath(std::wstring const &,std::wstring const &)
0x1800229e0  nop
0x1800229e1  lea     rcx, [rbp+57h+var_80]
0x1800229e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229ea  nop
0x1800229eb  lea     rcx, [rbp+57h+var_60]
0x1800229ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229f4  lea     rcx, [rbp+57h+var_A0]
0x1800229f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800229fd  mov     r8, rax; lpString2
0x180022a00  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x180022a08  or      edx, 0FFFFFFFFh; cchCount1
0x180022a0b  mov     r9d, edx; cchCount2
0x180022a0e  lea     rcx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180022a15  call    cs:__imp_CompareStringOrdinal
0x180022a1b  mov     edi, eax
0x180022a1d  mov     r9, r14
0x180022a20  mov     r8, rsi
0x180022a23  lea     rdx, [rbp+57h+var_A0]
0x180022a27  lea     rcx, [rbp+57h+var_B0]
0x180022a2b  call    ?GetValueIfExists@@YA?AV?$optional@K@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@00@Z; GetValueIfExists(std::wstring const &,std::wstring const &,std::wstring const &)
0x180022a30  cmp     [rbp+57h+var_AC], 0
0x180022a34  jz      short loc_180022A3C
0x180022a36  lea     rcx, [rbp+57h+var_B0]
0x180022a3a  jmp     short loc_180022A79
0x180022a3c  cmp     edi, 2
0x180022a3f  jz      short loc_180022A80
0x180022a41  lea     rdx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180022a48  lea     rcx, [rbp+57h+var_40]
0x180022a4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022a51  nop
0x180022a52  mov     r9, r14
0x180022a55  mov     r8, rsi
0x180022a58  lea     rdx, [rbp+57h+var_40]
0x180022a5c  lea     rcx, [rbp+57h+var_A8]
0x180022a60  call    ?GetValueIfExists@@YA?AV?$optional@K@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@00@Z; GetValueIfExists(std::wstring const &,std::wstring const &,std::wstring const &)
0x180022a65  nop
0x180022a66  lea     rcx, [rbp+57h+var_40]
0x180022a6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a6f  cmp     [rbp+57h+var_A4], 0
0x180022a73  jz      short loc_180022A80
0x180022a75  lea     rcx, [rbp+57h+var_A8]
0x180022a79  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x180022a7e  mov     ebx, [rax]
0x180022a80  lea     rcx, [rbp+57h+var_A0]
0x180022a84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a89  mov     eax, ebx
0x180022a8b  mov     rcx, [rbp+57h+var_20]
0x180022a8f  xor     rcx, rsp; StackCookie
0x180022a92  call    __security_check_cookie
0x180022a97  lea     r11, [rsp+0E0h+var_10]
0x180022a9f  mov     rbx, [r11+30h]
0x180022aa3  mov     rsi, [r11+38h]
0x180022aa7  mov     rsp, r11
0x180022aaa  pop     r14
0x180022aac  pop     rdi
0x180022aad  pop     rbp
0x180022aae  retn
```
