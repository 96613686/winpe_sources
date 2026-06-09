# PolicyModel::CFileHash::GetXmlName(void)

- ea: `0x140011020`
- end: `0x140011085`
- name: `?GetXmlName@CFileHash@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x140011020`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHash::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x140011020  mov     [rsp+arg_8], rdx
0x140011025  push    rbx
0x140011026  sub     rsp, 30h
0x14001102a  mov     rbx, rdx
0x14001102d  mov     [rsp+38h+var_18], 0
0x140011035  lea     rax, WPP_GLOBAL_Control
0x14001103c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011043  cmp     rcx, rax
0x140011046  jz      short loc_140011063
0x140011048  test    byte ptr [rcx+1Ch], 8
0x14001104c  jz      short loc_140011063
0x14001104e  mov     edx, 15h
0x140011053  lea     r8, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids
0x14001105a  mov     rcx, [rcx+10h]
0x14001105e  call    WPP_SF_
0x140011063  lea     rdx, aFilehash; "FileHash"
0x14001106a  mov     rcx, rbx
0x14001106d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011072  nop
0x140011073  mov     [rsp+38h+var_18], 1
0x14001107b  mov     rax, rbx
0x14001107e  add     rsp, 30h
0x140011082  pop     rbx
0x140011083  retn
```
