# PolicyModel::CSddlCompiler::CreateOperator(PolicyModel::CSddlCompiler::UnaryOperatorType,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x14000c138`
- end: `0x14000c301`
- name: `?CreateOperator@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnaryOperatorType@12@AEBV34@_N@Z`
- size: `457`
- prototype: `__int64 __fastcall(__int64, int, __int64, char)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000af60`
- `0x14000cf50`
- `0x14000e5e0`

## callees

- `0x1400070e4`
- `0x140007db4`
- `0x140008368`
- `0x140008498`
- `0x14000863c`
- `0x14000997c`
- `0x1400099b4`
- `0x14000b4f8`
- `0x14000b5c4`
- `0x14000c138`
- `0x14000c4e0`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::CreateOperator(__int64 a1, int a2, __int64 a3, char a4)
{
  const wchar_t *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  _QWORD v12[4]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v13[4]; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v14[4]; // [rsp+70h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  if ( !*(_QWORD *)(a3 + 16) )
  {
    std::wstring::wstring(a1);
    return a1;
  }
  v13[3] = 7;
  v13[2] = 0;
  LOWORD(v13[0]) = 0;
  if ( !a2 )
  {
    v8 = L"!";
LABEL_10:
    std::wstring::assign((__int64)v13, (__int64)v8);
    goto LABEL_11;
  }
  if ( a2 == 1 )
  {
    v8 = L"Exists";
    goto LABEL_10;
  }
LABEL_11:
  std::wstring::wstring((__int64)v14, a3);
  if ( a4 )
    PolicyModel::CSddlCompiler::WrapWithParenthesis(v14);
  v12[3] = 7;
  v12[2] = 0;
  LOWORD(v12[0]) = 0;
  std::wstring::append(v12, v13, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( !a4 )
  {
    v9 = std::char_traits<unsigned short>::length(L" ");
    std::wstring::append(v12, v10, v9);
  }
  std::wstring::append(v12, v14, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::wstring(a1, v12);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::_Tidy(v14, 1, 0);
  std::wstring::_Tidy(v13, 1, 0);
  return a1;
}

```

## disassembly

```asm
0x14000c138  mov     [rsp-8+arg_8], rbx
0x14000c13d  mov     [rsp-8+arg_18], rsi
0x14000c142  push    rbp
0x14000c143  push    rdi
0x14000c144  push    r14
0x14000c146  lea     rbp, [rsp-47h]
0x14000c14b  sub     rsp, 0A0h
0x14000c152  mov     rax, cs:__security_cookie
0x14000c159  xor     rax, rsp
0x14000c15c  mov     [rbp+57h+var_20], rax
0x14000c160  mov     r14b, r9b
0x14000c163  mov     rsi, r8
0x14000c166  mov     edi, edx
0x14000c168  mov     rbx, rcx
0x14000c16b  mov     [rbp+57h+var_88], rcx
0x14000c16f  mov     [rbp+57h+var_90], 0
0x14000c176  lea     rax, WPP_GLOBAL_Control
0x14000c17d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c184  cmp     rcx, rax
0x14000c187  jz      short loc_14000C1A4
0x14000c189  test    byte ptr [rcx+1Ch], 8
0x14000c18d  jz      short loc_14000C1A4
0x14000c18f  mov     edx, 0Ah
0x14000c194  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c19b  mov     rcx, [rcx+10h]
0x14000c19f  call    WPP_SF_
0x14000c1a4  cmp     qword ptr [rsi+10h], 0
0x14000c1a9  jnz     short loc_14000C1C7
0x14000c1ab  lea     rdx, dword_140018714
0x14000c1b2  mov     rcx, rbx
0x14000c1b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000c1ba  nop
0x14000c1bb  mov     [rbp+57h+var_90], 1
0x14000c1c2  jmp     loc_14000C2D9
0x14000c1c7  mov     [rbp+57h+var_50], 0
0x14000c1cf  mov     [rbp+57h+var_48], 0
0x14000c1d7  mov     [rbp+57h+var_48], 7
0x14000c1df  mov     [rbp+57h+var_50], 0
0x14000c1e7  xor     eax, eax
0x14000c1e9  mov     [rbp+57h+var_60], ax
0x14000c1ed  test    edi, edi
0x14000c1ef  jnz     short loc_14000C1FA
0x14000c1f1  lea     rdx, asc_140018DE0; "!"
0x14000c1f8  jmp     short loc_14000C206
0x14000c1fa  cmp     edi, 1
0x14000c1fd  jnz     short loc_14000C20F
0x14000c1ff  lea     rdx, aExists; "Exists"
0x14000c206  lea     rcx, [rbp+57h+var_60]
0x14000c20a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14000c20f  mov     rdx, rsi
0x14000c212  lea     rcx, [rbp+57h+var_40]
0x14000c216  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000c21b  nop
0x14000c21c  test    r14b, r14b
0x14000c21f  jz      short loc_14000C22A
0x14000c221  lea     rcx, [rbp+57h+var_40]
0x14000c225  call    ?WrapWithParenthesis@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithParenthesis(std::wstring &)
0x14000c22a  mov     [rbp+57h+var_70], 0
0x14000c232  mov     [rbp+57h+var_68], 0
0x14000c23a  mov     [rbp+57h+var_68], 7
0x14000c242  mov     [rbp+57h+var_70], 0
0x14000c24a  xor     eax, eax
0x14000c24c  mov     [rbp+57h+var_80], ax
0x14000c250  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c254  mov     r9, rdi
0x14000c257  xor     r8d, r8d
0x14000c25a  lea     rdx, [rbp+57h+var_60]
0x14000c25e  lea     rcx, [rbp+57h+var_80]
0x14000c262  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c267  test    r14b, r14b
0x14000c26a  jnz     short loc_14000C287
0x14000c26c  lea     rcx, asc_140018E3C; " "
0x14000c273  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000c278  mov     r8, rax
0x14000c27b  mov     rdx, rcx
0x14000c27e  lea     rcx, [rbp+57h+var_80]
0x14000c282  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000c287  mov     r9, rdi
0x14000c28a  xor     r8d, r8d
0x14000c28d  lea     rdx, [rbp+57h+var_40]
0x14000c291  lea     rcx, [rbp+57h+var_80]
0x14000c295  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c29a  lea     rdx, [rbp+57h+var_80]
0x14000c29e  mov     rcx, rbx
0x14000c2a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000c2a6  mov     [rbp+57h+var_90], 1
0x14000c2ad  xor     r8d, r8d
0x14000c2b0  mov     dl, 1
0x14000c2b2  lea     rcx, [rbp+57h+var_80]
0x14000c2b6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c2bb  nop
0x14000c2bc  xor     r8d, r8d
0x14000c2bf  mov     dl, 1
0x14000c2c1  lea     rcx, [rbp+57h+var_40]
0x14000c2c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c2ca  nop
0x14000c2cb  xor     r8d, r8d
0x14000c2ce  mov     dl, 1
0x14000c2d0  lea     rcx, [rbp+57h+var_60]
0x14000c2d4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c2d9  mov     rax, rbx
0x14000c2dc  mov     rcx, [rbp+57h+var_20]
0x14000c2e0  xor     rcx, rsp; StackCookie
0x14000c2e3  call    __security_check_cookie
0x14000c2e8  lea     r11, [rsp+0B0h+var_10]
0x14000c2f0  mov     rbx, [r11+28h]
0x14000c2f4  mov     rsi, [r11+38h]
0x14000c2f8  mov     rsp, r11
0x14000c2fb  pop     r14
0x14000c2fd  pop     rdi
0x14000c2fe  pop     rbp
0x14000c2ff  retn
```
