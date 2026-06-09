# JobHelper::GetJobDependencyRegPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000f7d4`
- end: `0x18000f8dc`
- name: `?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z`
- size: `264`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e524`
- `0x180011160`
- `0x180011574`
- `0x180011bfc`
- `0x180012050`

## callees

- `0x1800062ac`
- `0x1800065f8`
- `0x180009d64`
- `0x180009e20`
- `0x18000a890`
- `0x18000f7d4`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobHelper::GetJobDependencyRegPath(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx

  if ( (unsigned __int8)std::operator!=<unsigned short>(a1, a2)
    && (unsigned __int8)std::operator!=<unsigned short>(a2, v6) )
  {
    v7 = 0;
    std::wstring::assign(a3, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB");
    std::wstring::append(a3, L"\\");
    std::wstring::append(a3, a1, 0, -1);
    std::wstring::append(a3, L"\\");
    std::wstring::append(a3, L"Dependencies");
    std::wstring::append(a3, L"\\");
    std::wstring::append(a3, a2, 0, -1);
    if ( !(unsigned __int8)std::operator!=<unsigned short>(a3, v8) )
      v7 = -2147467259;
  }
  else
  {
    v7 = -2147024809;
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(a1, v6, 0);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(a2, v9, 0);
  return v7;
}

```

## disassembly

```asm
0x18000f7d4  mov     [rsp+arg_18], rbx
0x18000f7d9  push    rbp
0x18000f7da  push    rsi
0x18000f7db  push    rdi
0x18000f7dc  sub     rsp, 40h
0x18000f7e0  mov     rax, cs:__security_cookie
0x18000f7e7  xor     rax, rsp
0x18000f7ea  mov     [rsp+58h+var_28], rax
0x18000f7ef  mov     rbp, r8
0x18000f7f2  mov     rdi, rdx
0x18000f7f5  mov     rsi, rcx
0x18000f7f8  mov     [rsp+58h+var_38], rcx
0x18000f7fd  mov     [rsp+58h+var_30], rdx
0x18000f802  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const *)
0x18000f807  test    al, al
0x18000f809  jnz     short loc_18000F815
0x18000f80b  mov     ebx, 80070057h
0x18000f810  jmp     loc_18000F8A4
0x18000f815  mov     rcx, rdi
0x18000f818  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const *)
0x18000f81d  test    al, al
0x18000f81f  jz      short loc_18000F80B
0x18000f821  xor     ebx, ebx
0x18000f823  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f82a  mov     rcx, rbp
0x18000f82d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000f832  lea     rdx, asc_1800235F8; "\\"
0x18000f839  mov     rcx, rbp
0x18000f83c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000f841  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f845  xor     r8d, r8d
0x18000f848  mov     rdx, rsi
0x18000f84b  mov     rcx, rbp
0x18000f84e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f853  lea     rdx, asc_1800235F8; "\\"
0x18000f85a  mov     rcx, rbp
0x18000f85d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000f862  lea     rdx, aDependencies; "Dependencies"
0x18000f869  mov     rcx, rbp
0x18000f86c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000f871  lea     rdx, asc_1800235F8; "\\"
0x18000f878  mov     rcx, rbp
0x18000f87b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000f880  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f884  xor     r8d, r8d
0x18000f887  mov     rdx, rdi
0x18000f88a  mov     rcx, rbp
0x18000f88d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f892  mov     rcx, rbp
0x18000f895  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const *)
0x18000f89a  mov     ecx, 80004005h
0x18000f89f  test    al, al
0x18000f8a1  cmovz   ebx, ecx
0x18000f8a4  xor     r8d, r8d
0x18000f8a7  mov     dl, 1
0x18000f8a9  mov     rcx, rsi
0x18000f8ac  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f8b1  nop
0x18000f8b2  xor     r8d, r8d
0x18000f8b5  mov     dl, 1
0x18000f8b7  mov     rcx, rdi
0x18000f8ba  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f8bf  mov     eax, ebx
0x18000f8c1  mov     rcx, [rsp+58h+var_28]
0x18000f8c6  xor     rcx, rsp; StackCookie
0x18000f8c9  call    __security_check_cookie
0x18000f8ce  mov     rbx, [rsp+58h+arg_18]
0x18000f8d3  add     rsp, 40h
0x18000f8d7  pop     rdi
0x18000f8d8  pop     rsi
0x18000f8d9  pop     rbp
0x18000f8da  retn
```
