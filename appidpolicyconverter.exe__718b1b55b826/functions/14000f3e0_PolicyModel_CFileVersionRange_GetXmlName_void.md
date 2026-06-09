# PolicyModel::CFileVersionRange::GetXmlName(void)

- ea: `0x14000f3e0`
- end: `0x14000f445`
- name: `?GetXmlName@CFileVersionRange@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000f3e0`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileVersionRange::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000f3e0  mov     [rsp+arg_8], rdx
0x14000f3e5  push    rbx
0x14000f3e6  sub     rsp, 30h
0x14000f3ea  mov     rbx, rdx
0x14000f3ed  mov     [rsp+38h+var_18], 0
0x14000f3f5  lea     rax, WPP_GLOBAL_Control
0x14000f3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f403  cmp     rcx, rax
0x14000f406  jz      short loc_14000F423
0x14000f408  test    byte ptr [rcx+1Ch], 8
0x14000f40c  jz      short loc_14000F423
0x14000f40e  mov     edx, 15h
0x14000f413  lea     r8, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids
0x14000f41a  mov     rcx, [rcx+10h]
0x14000f41e  call    WPP_SF_
0x14000f423  lea     rdx, aBinaryversionr; "BinaryVersionRange"
0x14000f42a  mov     rcx, rbx
0x14000f42d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f432  nop
0x14000f433  mov     [rsp+38h+var_18], 1
0x14000f43b  mov     rax, rbx
0x14000f43e  add     rsp, 30h
0x14000f442  pop     rbx
0x14000f443  retn
```
