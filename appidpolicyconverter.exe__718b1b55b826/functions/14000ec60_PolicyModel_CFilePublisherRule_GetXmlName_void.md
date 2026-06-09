# PolicyModel::CFilePublisherRule::GetXmlName(void)

- ea: `0x14000ec60`
- end: `0x14000ecc5`
- name: `?GetXmlName@CFilePublisherRule@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000ec60`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePublisherRule::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_66277d6f64ee3c41faa92a6d43bd2707_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000ec60  mov     [rsp+arg_8], rdx
0x14000ec65  push    rbx
0x14000ec66  sub     rsp, 30h
0x14000ec6a  mov     rbx, rdx
0x14000ec6d  mov     [rsp+38h+var_18], 0
0x14000ec75  lea     rax, WPP_GLOBAL_Control
0x14000ec7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec83  cmp     rcx, rax
0x14000ec86  jz      short loc_14000ECA3
0x14000ec88  test    byte ptr [rcx+1Ch], 8
0x14000ec8c  jz      short loc_14000ECA3
0x14000ec8e  mov     edx, 0Dh
0x14000ec93  lea     r8, WPP_66277d6f64ee3c41faa92a6d43bd2707_Traceguids
0x14000ec9a  mov     rcx, [rcx+10h]
0x14000ec9e  call    WPP_SF_
0x14000eca3  lea     rdx, aFilepublisherr; "FilePublisherRule"
0x14000ecaa  mov     rcx, rbx
0x14000ecad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ecb2  nop
0x14000ecb3  mov     [rsp+38h+var_18], 1
0x14000ecbb  mov     rax, rbx
0x14000ecbe  add     rsp, 30h
0x14000ecc2  pop     rbx
0x14000ecc3  retn
```
