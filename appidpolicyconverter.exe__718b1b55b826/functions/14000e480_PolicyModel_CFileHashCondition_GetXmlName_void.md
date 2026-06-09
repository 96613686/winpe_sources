# PolicyModel::CFileHashCondition::GetXmlName(void)

- ea: `0x14000e480`
- end: `0x14000e4e5`
- name: `?GetXmlName@CFileHashCondition@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000e480`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHashCondition::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000e480  mov     [rsp+arg_8], rdx
0x14000e485  push    rbx
0x14000e486  sub     rsp, 30h
0x14000e48a  mov     rbx, rdx
0x14000e48d  mov     [rsp+38h+var_18], 0
0x14000e495  lea     rax, WPP_GLOBAL_Control
0x14000e49c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4a3  cmp     rcx, rax
0x14000e4a6  jz      short loc_14000E4C3
0x14000e4a8  test    byte ptr [rcx+1Ch], 8
0x14000e4ac  jz      short loc_14000E4C3
0x14000e4ae  mov     edx, 0Fh
0x14000e4b3  lea     r8, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids
0x14000e4ba  mov     rcx, [rcx+10h]
0x14000e4be  call    WPP_SF_
0x14000e4c3  lea     rdx, aFilehashcondit; "FileHashCondition"
0x14000e4ca  mov     rcx, rbx
0x14000e4cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000e4d2  nop
0x14000e4d3  mov     [rsp+38h+var_18], 1
0x14000e4db  mov     rax, rbx
0x14000e4de  add     rsp, 30h
0x14000e4e2  pop     rbx
0x14000e4e3  retn
```
