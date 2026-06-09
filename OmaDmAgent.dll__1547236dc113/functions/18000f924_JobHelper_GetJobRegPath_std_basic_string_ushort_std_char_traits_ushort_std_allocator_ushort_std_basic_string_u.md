# JobHelper::GetJobRegPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000f924`
- end: `0x18000fa3e`
- name: `?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `282`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c734`
- `0x18000ea88`
- `0x180011398`
- `0x18001180c`
- `0x180011a44`
- `0x180011e54`
- `0x180012338`

## callees

- `0x1800062ac`
- `0x1800065f8`
- `0x180006998`
- `0x180009d64`
- `0x180009e20`
- `0x18000a890`
- `0x18000f924`
- `0x180012f54`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobHelper::GetJobRegPath(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  _WORD v10[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+48h] [rbp-20h]

  if ( (unsigned __int8)std::operator!=<unsigned short>(a1, a2) )
  {
    v5 = 0;
    std::wstring::assign(a2, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB");
    v12 = 7;
    v11 = 0;
    v10[0] = 0;
    v6 = std::char_traits<unsigned short>::length(L"\\");
    std::wstring::reserve(v10, *(_QWORD *)(a1 + 16) + v6);
    std::wstring::append(v10, L"\\");
    std::wstring::append(v10, a1, 0, -1);
    std::wstring::append(a2, v10, 0, -1);
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v10, v7, 0);
    if ( !(unsigned __int8)std::operator!=<unsigned short>(a2, v8) )
      v5 = -2147467259;
  }
  else
  {
    v5 = -2147024809;
  }
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(a1, v4, 0);
  return v5;
}

```

## disassembly

```asm
0x18000f924  mov     [rsp+arg_10], rbx
0x18000f929  mov     [rsp+arg_18], rsi
0x18000f92e  push    rdi
0x18000f92f  sub     rsp, 60h
0x18000f933  mov     rax, cs:__security_cookie
0x18000f93a  xor     rax, rsp
0x18000f93d  mov     [rsp+68h+var_18], rax
0x18000f942  mov     rsi, rdx
0x18000f945  mov     rbx, rcx
0x18000f948  mov     [rsp+68h+var_40], rcx
0x18000f94d  mov     [rsp+68h+var_48], 0
0x18000f955  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const *)
0x18000f95a  test    al, al
0x18000f95c  jnz     short loc_18000F968
0x18000f95e  mov     edi, 80070057h
0x18000f963  jmp     loc_18000FA0F
0x18000f968  xor     edi, edi
0x18000f96a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f971  mov     rcx, rsi
0x18000f974  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000f979  nop
0x18000f97a  mov     [rsp+68h+var_20], 7
0x18000f983  mov     [rsp+68h+var_28], rdi
0x18000f988  xor     eax, eax
0x18000f98a  mov     [rsp+68h+var_38], ax
0x18000f98f  mov     [rsp+68h+var_48], 1
0x18000f997  lea     rcx, asc_1800235F8; "\\"
0x18000f99e  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000f9a3  add     rax, [rbx+10h]
0x18000f9a7  mov     rdx, rax
0x18000f9aa  lea     rcx, [rsp+68h+var_38]
0x18000f9af  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18000f9b4  lea     rdx, asc_1800235F8; "\\"
0x18000f9bb  lea     rcx, [rsp+68h+var_38]
0x18000f9c0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000f9c5  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f9c9  xor     r8d, r8d
0x18000f9cc  mov     rdx, rbx
0x18000f9cf  lea     rcx, [rsp+68h+var_38]
0x18000f9d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f9d9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f9dd  xor     r8d, r8d
0x18000f9e0  lea     rdx, [rsp+68h+var_38]
0x18000f9e5  mov     rcx, rsi
0x18000f9e8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f9ed  nop
0x18000f9ee  xor     r8d, r8d
0x18000f9f1  mov     dl, 1
0x18000f9f3  lea     rcx, [rsp+68h+var_38]
0x18000f9f8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f9fd  mov     rcx, rsi
0x18000fa00  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const *)
0x18000fa05  mov     ecx, 80004005h
0x18000fa0a  test    al, al
0x18000fa0c  cmovz   edi, ecx
0x18000fa0f  xor     r8d, r8d
0x18000fa12  mov     dl, 1
0x18000fa14  mov     rcx, rbx
0x18000fa17  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fa1c  mov     eax, edi
0x18000fa1e  mov     rcx, [rsp+68h+var_18]
0x18000fa23  xor     rcx, rsp; StackCookie
0x18000fa26  call    __security_check_cookie
0x18000fa2b  lea     r11, [rsp+68h+var_8]
0x18000fa30  mov     rbx, [r11+20h]
0x18000fa34  mov     rsi, [r11+28h]
0x18000fa38  mov     rsp, r11
0x18000fa3b  pop     rdi
0x18000fa3c  retn
```
