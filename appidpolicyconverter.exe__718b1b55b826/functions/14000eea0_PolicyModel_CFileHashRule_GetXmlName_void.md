# PolicyModel::CFileHashRule::GetXmlName(void)

- ea: `0x14000eea0`
- end: `0x14000ef05`
- name: `?GetXmlName@CFileHashRule@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000eea0`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHashRule::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4525850acc9d3991abe82a9f77fe7d31_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000eea0  mov     [rsp+arg_8], rdx
0x14000eea5  push    rbx
0x14000eea6  sub     rsp, 30h
0x14000eeaa  mov     rbx, rdx
0x14000eead  mov     [rsp+38h+var_18], 0
0x14000eeb5  lea     rax, WPP_GLOBAL_Control
0x14000eebc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eec3  cmp     rcx, rax
0x14000eec6  jz      short loc_14000EEE3
0x14000eec8  test    byte ptr [rcx+1Ch], 8
0x14000eecc  jz      short loc_14000EEE3
0x14000eece  mov     edx, 0Dh
0x14000eed3  lea     r8, WPP_4525850acc9d3991abe82a9f77fe7d31_Traceguids
0x14000eeda  mov     rcx, [rcx+10h]
0x14000eede  call    WPP_SF_
0x14000eee3  lea     rdx, aFilehashrule; "FileHashRule"
0x14000eeea  mov     rcx, rbx
0x14000eeed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000eef2  nop
0x14000eef3  mov     [rsp+38h+var_18], 1
0x14000eefb  mov     rax, rbx
0x14000eefe  add     rsp, 30h
0x14000ef02  pop     rbx
0x14000ef03  retn
```
