# PolicyModel::CFilePublisherCondition::GetXmlName(void)

- ea: `0x14000cd80`
- end: `0x14000cde5`
- name: `?GetXmlName@CFilePublisherCondition@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000cd80`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePublisherCondition::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000cd80  mov     [rsp+arg_8], rdx
0x14000cd85  push    rbx
0x14000cd86  sub     rsp, 30h
0x14000cd8a  mov     rbx, rdx
0x14000cd8d  mov     [rsp+38h+var_18], 0
0x14000cd95  lea     rax, WPP_GLOBAL_Control
0x14000cd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cda3  cmp     rcx, rax
0x14000cda6  jz      short loc_14000CDC3
0x14000cda8  test    byte ptr [rcx+1Ch], 8
0x14000cdac  jz      short loc_14000CDC3
0x14000cdae  mov     edx, 0Eh
0x14000cdb3  lea     r8, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids
0x14000cdba  mov     rcx, [rcx+10h]
0x14000cdbe  call    WPP_SF_
0x14000cdc3  lea     rdx, aFilepublisherc; "FilePublisherCondition"
0x14000cdca  mov     rcx, rbx
0x14000cdcd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cdd2  nop
0x14000cdd3  mov     [rsp+38h+var_18], 1
0x14000cddb  mov     rax, rbx
0x14000cdde  add     rsp, 30h
0x14000cde2  pop     rbx
0x14000cde3  retn
```
