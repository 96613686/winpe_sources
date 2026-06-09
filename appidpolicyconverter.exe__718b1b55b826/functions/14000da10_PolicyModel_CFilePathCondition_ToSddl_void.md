# PolicyModel::CFilePathCondition::ToSddl(void)

- ea: `0x14000da10`
- end: `0x14000db00`
- name: `?ToSddl@CFilePathCondition@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `240`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000bee4`
- `0x14000da10`
- `0x140013b10`
- `0x140016010`

## string_xrefs

- `0x14000da88`: `APPID://PATH`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePathCondition::ToSddl(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _QWORD v6[4]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v7[4]; // [rsp+60h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(a1 + 16) + 8LL))(a1 + 16, v7);
  std::wstring::wstring((__int64)v6);
  PolicyModel::CSddlCompiler::CreateOperator(a2, 9, (__int64)v6, v4, 0);
  std::wstring::_Tidy(v6, 1, 0);
  std::wstring::_Tidy(v7, 1, 0);
  return a2;
}

```

## disassembly

```asm
0x14000da10  mov     [rsp+arg_10], rbx
0x14000da15  push    rdi
0x14000da16  sub     rsp, 90h
0x14000da1d  mov     rax, cs:__security_cookie
0x14000da24  xor     rax, rsp
0x14000da27  mov     [rsp+98h+var_18], rax
0x14000da2f  mov     rdi, rdx
0x14000da32  mov     rbx, rcx
0x14000da35  mov     [rsp+98h+var_60], rdx
0x14000da3a  mov     [rsp+98h+var_68], 0
0x14000da42  lea     rax, WPP_GLOBAL_Control
0x14000da49  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da50  cmp     rcx, rax
0x14000da53  jz      short loc_14000DA70
0x14000da55  test    byte ptr [rcx+1Ch], 8
0x14000da59  jz      short loc_14000DA70
0x14000da5b  mov     edx, 0Fh
0x14000da60  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000da67  mov     rcx, [rcx+10h]
0x14000da6b  call    WPP_SF_
0x14000da70  lea     rcx, [rbx+10h]
0x14000da74  mov     rax, [rcx]
0x14000da77  lea     rdx, [rsp+98h+var_38]
0x14000da7c  mov     rax, [rax+8]
0x14000da80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da85  mov     rbx, rax
0x14000da88  lea     rdx, aAppidPath; "APPID://PATH"
0x14000da8f  lea     rcx, [rsp+98h+var_58]
0x14000da94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000da99  nop
0x14000da9a  mov     [rsp+98h+var_78], 0
0x14000da9f  mov     r9, rbx
0x14000daa2  lea     r8, [rsp+98h+var_58]
0x14000daa7  mov     edx, 9
0x14000daac  mov     rcx, rdi
0x14000daaf  call    ?CreateOperator@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4BinaryOperatorType@12@AEBV34@1_N@Z; PolicyModel::CSddlCompiler::CreateOperator(PolicyModel::CSddlCompiler::BinaryOperatorType,std::wstring const &,std::wstring const &,bool)
0x14000dab4  mov     [rsp+98h+var_68], 1
0x14000dabc  xor     r8d, r8d
0x14000dabf  mov     dl, 1
0x14000dac1  lea     rcx, [rsp+98h+var_58]
0x14000dac6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dacb  nop
0x14000dacc  xor     r8d, r8d
0x14000dacf  mov     dl, 1
0x14000dad1  lea     rcx, [rsp+98h+var_38]
0x14000dad6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dadb  mov     rax, rdi
0x14000dade  mov     rcx, [rsp+98h+var_18]
0x14000dae6  xor     rcx, rsp; StackCookie
0x14000dae9  call    __security_check_cookie
0x14000daee  mov     rbx, [rsp+98h+arg_10]
0x14000daf6  add     rsp, 90h
0x14000dafd  pop     rdi
0x14000dafe  retn
```
