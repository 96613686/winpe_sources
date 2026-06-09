# PolicyModel::CXmlSerializer::CXmlSerializer(void)

- ea: `0x14000baf8`
- end: `0x14000bb42`
- name: `??0CXmlSerializer@PolicyModel@@IEAA@XZ`
- size: `74`
- prototype: `PolicyModel::CXmlSerializer *__fastcall(PolicyModel::CXmlSerializer *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009a1c`
- `0x14000db08`
- `0x14000efc8`
- `0x14000f810`
- `0x1400109fc`

## callees

- `0x1400070e4`
- `0x14000baf8`

## pseudocode

```c
PolicyModel::CXmlSerializer *__fastcall PolicyModel::CXmlSerializer::CXmlSerializer(PolicyModel::CXmlSerializer *this)
{
  *(_QWORD *)this = &PolicyModel::CXmlSerializer::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9822af242fd937ad162aaa976899853f_Traceguids);
  return this;
}

```

## disassembly

```asm
0x14000baf8  push    rbx
0x14000bafa  sub     rsp, 20h
0x14000bafe  lea     rax, ??_7CXmlSerializer@PolicyModel@@6B@; const PolicyModel::CXmlSerializer::`vftable'
0x14000bb05  mov     rbx, rcx
0x14000bb08  mov     [rcx], rax
0x14000bb0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb12  lea     rax, WPP_GLOBAL_Control
0x14000bb19  cmp     rcx, rax
0x14000bb1c  jz      short loc_14000BB39
0x14000bb1e  test    byte ptr [rcx+1Ch], 8
0x14000bb22  jz      short loc_14000BB39
0x14000bb24  mov     rcx, [rcx+10h]
0x14000bb28  lea     r8, WPP_9822af242fd937ad162aaa976899853f_Traceguids
0x14000bb2f  mov     edx, 0Ah
0x14000bb34  call    WPP_SF_
0x14000bb39  mov     rax, rbx
0x14000bb3c  add     rsp, 20h
0x14000bb40  pop     rbx
0x14000bb41  retn
```
