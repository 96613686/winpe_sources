# PolicyModel::CSddlCompiler::CreateOperator(PolicyModel::CSddlCompiler::BinaryOperatorType,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x14000bee4`
- end: `0x14000c130`
- name: `?CreateOperator@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4BinaryOperatorType@12@AEBV34@1_N@Z`
- size: `588`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, char)`
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000af60`
- `0x14000bd68`
- `0x14000cf50`
- `0x14000da10`
- `0x14000e5e0`

## callees

- `0x1400070e4`
- `0x140007db4`
- `0x140008368`
- `0x140008498`
- `0x14000997c`
- `0x1400099b4`
- `0x14000b4f8`
- `0x14000bc24`
- `0x14000bee4`
- `0x14000c4e0`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::CreateOperator(__int64 a1, int a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v9; // rdx
  const wchar_t *v10; // rdx
  _QWORD v12[4]; // [rsp+30h] [rbp-71h] BYREF
  _QWORD v13[4]; // [rsp+50h] [rbp-51h] BYREF
  _QWORD v14[4]; // [rsp+70h] [rbp-31h] BYREF
  _QWORD v15[4]; // [rsp+90h] [rbp-11h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  if ( !*(_QWORD *)(a3 + 16) )
  {
    if ( !*(_QWORD *)(a4 + 16) )
    {
      std::wstring::wstring(a1);
      return a1;
    }
    v9 = a4;
    goto LABEL_7;
  }
  if ( !*(_QWORD *)(a4 + 16) )
  {
    v9 = a3;
LABEL_7:
    std::wstring::wstring(a1, v9);
    return a1;
  }
  v12[3] = 7;
  v12[2] = 0;
  LOWORD(v12[0]) = 0;
  switch ( a2 )
  {
    case 2:
      v10 = L"&&";
      break;
    case 3:
      v10 = L"||";
      break;
    case 5:
      v10 = L">=";
      break;
    case 7:
      v10 = L"<=";
      break;
    case 8:
      v10 = L"Any_of";
      break;
    case 9:
      v10 = L"Contains";
      break;
    default:
      goto LABEL_24;
  }
  std::wstring::assign((__int64)v12, (__int64)v10);
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  Sharp::Util::StringHandler::Wrap<std::wstring>(v12, 32);
  std::wstring::wstring((__int64)v15, a3);
  std::wstring::wstring((__int64)v14, a4);
  if ( a5 )
  {
    PolicyModel::CSddlCompiler::WrapWithParenthesis(v15);
    PolicyModel::CSddlCompiler::WrapWithParenthesis(v14);
  }
  v13[3] = 7;
  v13[2] = 0;
  LOWORD(v13[0]) = 0;
  std::wstring::append(v13, v15, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::append(v13, v12, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::append(v13, v14, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::wstring(a1, v13);
  std::wstring::_Tidy(v13, 1, 0);
  std::wstring::_Tidy(v14, 1, 0);
  std::wstring::_Tidy(v15, 1, 0);
  std::wstring::_Tidy(v12, 1, 0);
  return a1;
}

```

## disassembly

```asm
0x14000bee4  push    rbp
0x14000bee6  push    rbx
0x14000bee7  push    rsi
0x14000bee8  push    rdi
0x14000bee9  push    r13
0x14000beeb  push    r14
0x14000beed  push    r15
0x14000beef  lea     rbp, [rsp-1Fh]
0x14000bef4  sub     rsp, 0C0h
0x14000befb  mov     rax, cs:__security_cookie
0x14000bf02  xor     rax, rsp
0x14000bf05  mov     [rbp+4Fh+var_40], rax
0x14000bf09  mov     rsi, r9
0x14000bf0c  mov     r14, r8
0x14000bf0f  mov     edi, edx
0x14000bf11  mov     rbx, rcx
0x14000bf14  mov     [rbp+4Fh+var_C8], rcx
0x14000bf18  xor     r15d, r15d
0x14000bf1b  mov     [rsp+0F0h+var_D0], r15d
0x14000bf20  lea     r13, WPP_GLOBAL_Control
0x14000bf27  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf2e  cmp     rcx, r13
0x14000bf31  jz      short loc_14000BF4D
0x14000bf33  test    byte ptr [rcx+1Ch], 8
0x14000bf37  jz      short loc_14000BF4D
0x14000bf39  lea     edx, [r15+0Bh]
0x14000bf3d  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000bf44  mov     rcx, [rcx+10h]
0x14000bf48  call    WPP_SF_
0x14000bf4d  cmp     [r14+10h], r15
0x14000bf51  jz      short loc_14000BF72
0x14000bf53  cmp     [rsi+10h], r15
0x14000bf57  jnz     short loc_14000BF8E
0x14000bf59  mov     rdx, r14
0x14000bf5c  mov     rcx, rbx
0x14000bf5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000bf64  nop
0x14000bf65  mov     [rsp+0F0h+var_D0], 1
0x14000bf6d  jmp     loc_14000C10E
0x14000bf72  cmp     [rsi+10h], r15
0x14000bf76  jnz     short loc_14000BF89
0x14000bf78  lea     rdx, dword_140018714
0x14000bf7f  mov     rcx, rbx
0x14000bf82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000bf87  jmp     short loc_14000BF65
0x14000bf89  mov     rdx, rsi
0x14000bf8c  jmp     short loc_14000BF5C
0x14000bf8e  mov     [rbp+4Fh+var_B0], r15
0x14000bf92  mov     [rbp+4Fh+var_A8], r15
0x14000bf96  mov     [rbp+4Fh+var_A8], 7
0x14000bf9e  mov     [rbp+4Fh+var_B0], r15
0x14000bfa2  mov     [rbp+4Fh+var_C0], r15w
0x14000bfa7  cmp     edi, 2
0x14000bfaa  jnz     short loc_14000BFB5
0x14000bfac  lea     rdx, asc_140018DE4; "&&"
0x14000bfb3  jmp     short loc_14000BFF9
0x14000bfb5  cmp     edi, 3
0x14000bfb8  jnz     short loc_14000BFC3
0x14000bfba  lea     rdx, asc_140018DEC; "||"
0x14000bfc1  jmp     short loc_14000BFF9
0x14000bfc3  cmp     edi, 5
0x14000bfc6  jnz     short loc_14000BFD1
0x14000bfc8  lea     rdx, asc_140018DF4; ">="
0x14000bfcf  jmp     short loc_14000BFF9
0x14000bfd1  cmp     edi, 7
0x14000bfd4  jnz     short loc_14000BFDF
0x14000bfd6  lea     rdx, asc_140018DFC; "<="
0x14000bfdd  jmp     short loc_14000BFF9
0x14000bfdf  cmp     edi, 8
0x14000bfe2  jnz     short loc_14000BFED
0x14000bfe4  lea     rdx, aAnyOf; "Any_of"
0x14000bfeb  jmp     short loc_14000BFF9
0x14000bfed  cmp     edi, 9
0x14000bff0  jnz     short loc_14000C002
0x14000bff2  lea     rdx, aContains; "Contains"
0x14000bff9  lea     rcx, [rbp+4Fh+var_C0]
0x14000bffd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14000c002  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c009  cmp     rcx, r13
0x14000c00c  jz      short loc_14000C029
0x14000c00e  test    byte ptr [rcx+1Ch], 8
0x14000c012  jz      short loc_14000C029
0x14000c014  mov     edx, 10h
0x14000c019  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c020  mov     rcx, [rcx+10h]
0x14000c024  call    WPP_SF_
0x14000c029  mov     edx, 20h ; ' '
0x14000c02e  lea     rcx, [rbp+4Fh+var_C0]
0x14000c032  call    ??$Wrap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StringHandler@Util@Sharp@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@G@Z; Sharp::Util::StringHandler::Wrap<std::wstring>(std::wstring &,ushort)
0x14000c037  mov     rdx, r14
0x14000c03a  lea     rcx, [rbp+4Fh+var_60]
0x14000c03e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000c043  nop
0x14000c044  mov     rdx, rsi
0x14000c047  lea     rcx, [rbp+4Fh+var_80]
0x14000c04b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000c050  nop
0x14000c051  cmp     [rbp+4Fh+arg_20], r15b
0x14000c055  jz      short loc_14000C069
0x14000c057  lea     rcx, [rbp+4Fh+var_60]
0x14000c05b  call    ?WrapWithParenthesis@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithParenthesis(std::wstring &)
0x14000c060  lea     rcx, [rbp+4Fh+var_80]
0x14000c064  call    ?WrapWithParenthesis@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithParenthesis(std::wstring &)
0x14000c069  mov     [rbp+4Fh+var_90], r15
0x14000c06d  mov     [rbp+4Fh+var_88], r15
0x14000c071  mov     [rbp+4Fh+var_88], 7
0x14000c079  mov     [rbp+4Fh+var_90], r15
0x14000c07d  mov     [rbp+4Fh+var_A0], r15w
0x14000c082  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c086  mov     r9, rdi
0x14000c089  xor     r8d, r8d
0x14000c08c  lea     rdx, [rbp+4Fh+var_60]
0x14000c090  lea     rcx, [rbp+4Fh+var_A0]
0x14000c094  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c099  mov     r9, rdi
0x14000c09c  xor     r8d, r8d
0x14000c09f  lea     rdx, [rbp+4Fh+var_C0]
0x14000c0a3  lea     rcx, [rbp+4Fh+var_A0]
0x14000c0a7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c0ac  mov     r9, rdi
0x14000c0af  xor     r8d, r8d
0x14000c0b2  lea     rdx, [rbp+4Fh+var_80]
0x14000c0b6  lea     rcx, [rbp+4Fh+var_A0]
0x14000c0ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c0bf  lea     rdx, [rbp+4Fh+var_A0]
0x14000c0c3  mov     rcx, rbx
0x14000c0c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000c0cb  mov     [rsp+0F0h+var_D0], 1
0x14000c0d3  xor     r8d, r8d
0x14000c0d6  mov     dl, 1
0x14000c0d8  lea     rcx, [rbp+4Fh+var_A0]
0x14000c0dc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c0e1  nop
0x14000c0e2  xor     r8d, r8d
0x14000c0e5  mov     dl, 1
0x14000c0e7  lea     rcx, [rbp+4Fh+var_80]
0x14000c0eb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c0f0  nop
0x14000c0f1  xor     r8d, r8d
0x14000c0f4  mov     dl, 1
0x14000c0f6  lea     rcx, [rbp+4Fh+var_60]
0x14000c0fa  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c0ff  nop
0x14000c100  xor     r8d, r8d
0x14000c103  mov     dl, 1
0x14000c105  lea     rcx, [rbp+4Fh+var_C0]
0x14000c109  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000c10e  mov     rax, rbx
0x14000c111  mov     rcx, [rbp+4Fh+var_40]
0x14000c115  xor     rcx, rsp; StackCookie
0x14000c118  call    __security_check_cookie
0x14000c11d  add     rsp, 0C0h
0x14000c124  pop     r15
0x14000c126  pop     r14
0x14000c128  pop     r13
0x14000c12a  pop     rdi
0x14000c12b  pop     rsi
0x14000c12c  pop     rbx
0x14000c12d  pop     rbp
0x14000c12e  retn
```
