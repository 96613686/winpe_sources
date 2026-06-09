# std::_Format_handler<char>::_On_replacement_field(unsigned __int64,char const *)

- ea: `0x18002dcc4`
- end: `0x18002dd53`
- name: `?_On_replacement_field@?$_Format_handler@D@std@@QEAAX_KPEBD@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180026938`

## callees

- `0x1800256ec`
- `0x18002717c`
- `0x18002dcc4`

## pseudocode

```c
__int64 __fastcall std::_Format_handler<char>::_On_replacement_field(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 result; // rax
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  __int64 v10; // [rsp+30h] [rbp-29h]
  __int128 v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+50h] [rbp-9h]
  __int64 v13; // [rsp+60h] [rbp+7h] BYREF
  __int128 v14; // [rsp+68h] [rbp+Fh]
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  __int64 v16; // [rsp+80h] [rbp+27h]
  __int64 v17; // [rsp+C0h] [rbp+67h] BYREF

  v3 = (__int64 *)(a1 + 32);
  std::_Get_arg<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<char>>,char>>(&v9, a1 + 32, a2);
  if ( (_BYTE)v9 == 13 )
  {
    v6 = *(_QWORD *)a1 - a3;
    *(_QWORD *)a1 = a3;
    *(_QWORD *)(a1 + 8) += v6;
  }
  v7 = *v3;
  v14 = *(_OWORD *)(a1 + 40);
  v13 = v7;
  v15 = *(_QWORD *)(a1 + 56);
  v11 = v9;
  v16 = a1;
  v12 = v10;
  std::basic_format_arg<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<char>>,char>>::_Visit<std::_Default_arg_formatter<std::back_insert_iterator<std::_Fmt_buffer<char>>,char>>(
    &v11,
    &v17,
    &v13);
  result = v17;
  *v3 = v17;
  return result;
}

```

## disassembly

```asm
0x18002dcc4  push    rbp
0x18002dcc6  push    rbx
0x18002dcc7  push    rsi
0x18002dcc8  push    rdi
0x18002dcc9  lea     rbp, [rsp-3Fh]
0x18002dcce  sub     rsp, 98h
0x18002dcd5  lea     rsi, [rcx+20h]
0x18002dcd9  mov     rdi, r8
0x18002dcdc  mov     r8, rdx
0x18002dcdf  mov     rbx, rcx
0x18002dce2  mov     rdx, rsi
0x18002dce5  lea     rcx, [rbp+57h+var_90]
0x18002dce9  call    ??$_Get_arg@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@std@@@std@@YA?AV?$basic_format_arg@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@std@@@0@AEBV?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@0@_K@Z; std::_Get_arg<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<char>>,char>>(std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<char>>,char> const &,unsigned __int64)
0x18002dcee  cmp     byte ptr [rbp+57h+var_90], 0Dh
0x18002dcf2  jnz     short loc_18002DD01
0x18002dcf4  mov     rax, [rbx]
0x18002dcf7  sub     rax, rdi
0x18002dcfa  mov     [rbx], rdi
0x18002dcfd  add     [rbx+8], rax
0x18002dd01  movups  xmm0, xmmword ptr [rbx+28h]
0x18002dd05  mov     rax, [rsi]
0x18002dd08  lea     r8, [rbp+57h+var_50]
0x18002dd0c  movsd   xmm1, [rbp+57h+var_80]
0x18002dd11  lea     rdx, [rbp+57h+arg_0]
0x18002dd15  movdqu  [rbp+57h+var_48], xmm0
0x18002dd1a  mov     [rbp+57h+var_50], rax
0x18002dd1e  lea     rcx, [rbp+57h+var_70]
0x18002dd22  movups  xmm0, [rbp+57h+var_90]
0x18002dd26  mov     rax, [rbx+38h]
0x18002dd2a  mov     [rbp+57h+var_38], rax
0x18002dd2e  movaps  [rbp+57h+var_70], xmm0
0x18002dd32  mov     [rbp+57h+var_30], rbx
0x18002dd36  movsd   [rbp+57h+var_60], xmm1
0x18002dd3b  call    ??$_Visit@U?$_Default_arg_formatter@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@std@@@?$basic_format_arg@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@std@@@std@@QEAA?A_T$$QEAU?$_Default_arg_formatter@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@D@1@@Z
0x18002dd40  mov     rax, [rbp+57h+arg_0]
0x18002dd44  mov     [rsi], rax
0x18002dd47  add     rsp, 98h
0x18002dd4e  pop     rdi
0x18002dd4f  pop     rsi
0x18002dd50  pop     rbx
0x18002dd51  pop     rbp
0x18002dd52  retn
```
