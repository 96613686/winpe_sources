# PolicyModel::CFilePathRule::GetXmlName(void)

- ea: `0x14000ed80`
- end: `0x14000ede5`
- name: `?GetXmlName@CFilePathRule@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000ed80`

## string_xrefs

- `0x14000edc3`: `FilePathRule`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePathRule::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000ed80  mov     [rsp+arg_8], rdx
0x14000ed85  push    rbx
0x14000ed86  sub     rsp, 30h
0x14000ed8a  mov     rbx, rdx
0x14000ed8d  mov     [rsp+38h+var_18], 0
0x14000ed95  lea     rax, WPP_GLOBAL_Control
0x14000ed9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eda3  cmp     rcx, rax
0x14000eda6  jz      short loc_14000EDC3
0x14000eda8  test    byte ptr [rcx+1Ch], 8
0x14000edac  jz      short loc_14000EDC3
0x14000edae  mov     edx, 0Dh
0x14000edb3  lea     r8, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids
0x14000edba  mov     rcx, [rcx+10h]
0x14000edbe  call    WPP_SF_
0x14000edc3  lea     rdx, aFilepathrule; "FilePathRule"
0x14000edca  mov     rcx, rbx
0x14000edcd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000edd2  nop
0x14000edd3  mov     [rsp+38h+var_18], 1
0x14000eddb  mov     rax, rbx
0x14000edde  add     rsp, 30h
0x14000ede2  pop     rbx
0x14000ede3  retn
```
