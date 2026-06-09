# PolicyModel::CSddlCompiler::WrapWithQuotes(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000c56c`
- end: `0x14000c5b5`
- name: `?WrapWithQuotes@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000cf50`
- `0x14000de00`

## callees

- `0x1400070e4`
- `0x14000bc24`
- `0x14000c56c`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::WrapWithQuotes(__int64 a1)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  return Sharp::Util::StringHandler::Wrap<std::wstring>(a1, 34);
}

```

## disassembly

```asm
0x14000c56c  push    rbx
0x14000c56e  sub     rsp, 20h
0x14000c572  mov     rbx, rcx
0x14000c575  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c57c  lea     rax, WPP_GLOBAL_Control
0x14000c583  cmp     rcx, rax
0x14000c586  jz      short loc_14000C5A3
0x14000c588  test    byte ptr [rcx+1Ch], 8
0x14000c58c  jz      short loc_14000C5A3
0x14000c58e  mov     rcx, [rcx+10h]
0x14000c592  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c599  mov     edx, 0Fh
0x14000c59e  call    WPP_SF_
0x14000c5a3  mov     edx, 22h ; '"'
0x14000c5a8  mov     rcx, rbx
0x14000c5ab  add     rsp, 20h
0x14000c5af  pop     rbx
0x14000c5b0  jmp     ??$Wrap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StringHandler@Util@Sharp@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@G@Z; Sharp::Util::StringHandler::Wrap<std::wstring>(std::wstring &,ushort)
```
