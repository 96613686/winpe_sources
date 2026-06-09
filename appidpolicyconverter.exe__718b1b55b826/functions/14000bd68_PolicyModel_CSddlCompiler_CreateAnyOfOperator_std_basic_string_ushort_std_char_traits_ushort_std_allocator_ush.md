# PolicyModel::CSddlCompiler::CreateAnyOfOperator(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x14000bd68`
- end: `0x14000bede`
- name: `?CreateAnyOfOperator@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `374`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e5e0`

## callees

- `0x1400070e4`
- `0x140007db4`
- `0x140008368`
- `0x14000863c`
- `0x1400099b4`
- `0x14000b4f8`
- `0x14000b5c4`
- `0x14000bd68`
- `0x14000bee4`
- `0x14000c454`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::CreateAnyOfOperator(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *i; // rbx
  __int64 v7; // rax
  _QWORD v9[2]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v10; // [rsp+50h] [rbp+7h]
  __int64 v11; // [rsp+58h] [rbp+Fh]
  _QWORD v12[4]; // [rsp+60h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  if ( a3[1] )
  {
    v11 = 7;
    v10 = 0;
    LOWORD(v9[0]) = 0;
    for ( i = (_QWORD *)*a3; ; std::wstring::append(v9, i + 2, 0, 0xFFFFFFFFFFFFFFFFuLL) )
    {
      i = (_QWORD *)*i;
      if ( i == (_QWORD *)*a3 )
        break;
      if ( v10 )
      {
        v7 = std::char_traits<unsigned short>::length(L", ");
        std::wstring::append(v9, L", ", v7);
      }
    }
    PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(v9);
    PolicyModel::CSddlCompiler::CreateOperator((unsigned int)v12, 8, a2, (unsigned int)v9, 0);
    std::wstring::wstring(a1, v12);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::_Tidy(v9, 1, 0);
  }
  else
  {
    std::wstring::wstring(a1);
  }
  return a1;
}

```

## disassembly

```asm
0x14000bd68  mov     [rsp-8+arg_10], rbx
0x14000bd6d  mov     [rsp-8+arg_18], rsi
0x14000bd72  push    rbp
0x14000bd73  push    rdi
0x14000bd74  push    r14
0x14000bd76  lea     rbp, [rsp-47h]
0x14000bd7b  sub     rsp, 90h
0x14000bd82  mov     rax, cs:__security_cookie
0x14000bd89  xor     rax, rsp
0x14000bd8c  mov     [rbp+57h+var_20], rax
0x14000bd90  mov     rsi, r8
0x14000bd93  mov     r14, rdx
0x14000bd96  mov     rdi, rcx
0x14000bd99  mov     [rbp+57h+var_68], rcx
0x14000bd9d  mov     [rbp+57h+var_70], 0
0x14000bda4  lea     rax, WPP_GLOBAL_Control
0x14000bdab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdb2  cmp     rcx, rax
0x14000bdb5  jz      short loc_14000BDD2
0x14000bdb7  test    byte ptr [rcx+1Ch], 8
0x14000bdbb  jz      short loc_14000BDD2
0x14000bdbd  mov     edx, 0Ch
0x14000bdc2  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000bdc9  mov     rcx, [rcx+10h]
0x14000bdcd  call    WPP_SF_
0x14000bdd2  cmp     qword ptr [rsi+8], 0
0x14000bdd7  jnz     short loc_14000BDF5
0x14000bdd9  lea     rdx, dword_140018714
0x14000bde0  mov     rcx, rdi
0x14000bde3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000bde8  nop
0x14000bde9  mov     [rbp+57h+var_70], 1
0x14000bdf0  jmp     loc_14000BEB6
0x14000bdf5  mov     [rbp+57h+var_50], 0
0x14000bdfd  mov     [rbp+57h+var_48], 0
0x14000be05  mov     [rbp+57h+var_48], 7
0x14000be0d  mov     [rbp+57h+var_50], 0
0x14000be15  xor     eax, eax
0x14000be17  mov     [rbp+57h+var_60], ax
0x14000be1b  mov     rbx, [rsi]
0x14000be1e  mov     rbx, [rbx]
0x14000be21  cmp     rbx, [rsi]
0x14000be24  jz      short loc_14000BE62
0x14000be26  cmp     [rbp+57h+var_50], 0
0x14000be2b  jz      short loc_14000BE4C
0x14000be2d  lea     rcx, asc_140018E40; ", "
0x14000be34  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000be39  mov     r8, rax
0x14000be3c  lea     rdx, asc_140018E40; ", "
0x14000be43  lea     rcx, [rbp+57h+var_60]
0x14000be47  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000be4c  lea     rdx, [rbx+10h]
0x14000be50  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000be54  xor     r8d, r8d
0x14000be57  lea     rcx, [rbp+57h+var_60]
0x14000be5b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000be60  jmp     short loc_14000BE1E
0x14000be62  lea     rcx, [rbp+57h+var_60]
0x14000be66  call    ?WrapWithCurlyBrackets@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(std::wstring &)
0x14000be6b  mov     [rsp+0A0h+var_80], 0
0x14000be70  lea     r9, [rbp+57h+var_60]
0x14000be74  mov     r8, r14
0x14000be77  mov     edx, 8
0x14000be7c  lea     rcx, [rbp+57h+var_40]
0x14000be80  call    ?CreateOperator@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4BinaryOperatorType@12@AEBV34@1_N@Z; PolicyModel::CSddlCompiler::CreateOperator(PolicyModel::CSddlCompiler::BinaryOperatorType,std::wstring const &,std::wstring const &,bool)
0x14000be85  nop
0x14000be86  lea     rdx, [rbp+57h+var_40]
0x14000be8a  mov     rcx, rdi
0x14000be8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000be92  mov     [rbp+57h+var_70], 1
0x14000be99  xor     r8d, r8d
0x14000be9c  mov     dl, 1
0x14000be9e  lea     rcx, [rbp+57h+var_40]
0x14000bea2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000bea7  nop
0x14000bea8  xor     r8d, r8d
0x14000beab  mov     dl, 1
0x14000bead  lea     rcx, [rbp+57h+var_60]
0x14000beb1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000beb6  mov     rax, rdi
0x14000beb9  mov     rcx, [rbp+57h+var_20]
0x14000bebd  xor     rcx, rsp; StackCookie
0x14000bec0  call    __security_check_cookie
0x14000bec5  lea     r11, [rsp+0A0h+var_10]
0x14000becd  mov     rbx, [r11+30h]
0x14000bed1  mov     rsi, [r11+38h]
0x14000bed5  mov     rsp, r11
0x14000bed8  pop     r14
0x14000beda  pop     rdi
0x14000bedb  pop     rbp
0x14000bedc  retn
```
