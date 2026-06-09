# PolicyModel::CFilePath::ToSddl(void)

- ea: `0x14000de00`
- end: `0x14000de7e`
- name: `?ToSddl@CFilePath@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `126`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400070e4`
- `0x14000997c`
- `0x14000c56c`
- `0x14000c6f0`
- `0x14000de00`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePath::ToSddl(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids);
  std::wstring::wstring(a2, a1 + 16);
  Sharp::Util::StringHandler::ToUppercase<std::wstring>(a2);
  PolicyModel::CSddlCompiler::WrapWithQuotes(a2);
  return a2;
}

```

## disassembly

```asm
0x14000de00  mov     [rsp+arg_0], rbx
0x14000de05  mov     [rsp+arg_8], rdx
0x14000de0a  push    rdi
0x14000de0b  sub     rsp, 30h
0x14000de0f  mov     rbx, rdx
0x14000de12  mov     rdi, rcx
0x14000de15  mov     [rsp+38h+var_18], 0
0x14000de1d  lea     rax, WPP_GLOBAL_Control
0x14000de24  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de2b  cmp     rcx, rax
0x14000de2e  jz      short loc_14000DE4B
0x14000de30  test    byte ptr [rcx+1Ch], 8
0x14000de34  jz      short loc_14000DE4B
0x14000de36  mov     edx, 0Fh
0x14000de3b  lea     r8, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids
0x14000de42  mov     rcx, [rcx+10h]
0x14000de46  call    WPP_SF_
0x14000de4b  lea     rdx, [rdi+10h]
0x14000de4f  mov     rcx, rbx
0x14000de52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000de57  mov     [rsp+38h+var_18], 1
0x14000de5f  mov     rcx, rbx
0x14000de62  call    ??$ToUppercase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StringHandler@Util@Sharp@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; Sharp::Util::StringHandler::ToUppercase<std::wstring>(std::wstring &)
0x14000de67  mov     rcx, rbx
0x14000de6a  call    ?WrapWithQuotes@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithQuotes(std::wstring &)
0x14000de6f  mov     rax, rbx
0x14000de72  mov     rbx, [rsp+38h+arg_0]
0x14000de77  add     rsp, 30h
0x14000de7b  pop     rdi
0x14000de7c  retn
```
