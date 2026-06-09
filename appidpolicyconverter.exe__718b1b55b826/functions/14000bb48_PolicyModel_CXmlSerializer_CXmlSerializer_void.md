# PolicyModel::CXmlSerializer::~CXmlSerializer(void)

- ea: `0x14000bb48`
- end: `0x14000bb8a`
- name: `??1CXmlSerializer@PolicyModel@@MEAA@XZ`
- size: `66`
- prototype: `void __fastcall(PolicyModel::CXmlSerializer *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009efc`
- `0x14000bb90`
- `0x14000db9c`
- `0x14000f05c`
- `0x14000f88c`
- `0x140010a98`
- `0x14001438d`
- `0x140014ae8`

## callees

- `0x1400070e4`
- `0x14000bb48`

## pseudocode

```c
void __fastcall PolicyModel::CXmlSerializer::~CXmlSerializer(PolicyModel::CXmlSerializer *this)
{
  *(_QWORD *)this = &PolicyModel::CXmlSerializer::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9822af242fd937ad162aaa976899853f_Traceguids);
}

```

## disassembly

```asm
0x14000bb48  sub     rsp, 28h
0x14000bb4c  lea     rax, ??_7CXmlSerializer@PolicyModel@@6B@; const PolicyModel::CXmlSerializer::`vftable'
0x14000bb53  mov     [rcx], rax
0x14000bb56  lea     rax, WPP_GLOBAL_Control
0x14000bb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb64  cmp     rcx, rax
0x14000bb67  jz      short loc_14000BB85
0x14000bb69  test    byte ptr [rcx+1Ch], 8
0x14000bb6d  jz      short loc_14000BB85
0x14000bb6f  mov     edx, 0Bh
0x14000bb74  lea     r8, WPP_9822af242fd937ad162aaa976899853f_Traceguids
0x14000bb7b  mov     rcx, [rcx+10h]
0x14000bb7f  call    WPP_SF_
0x14000bb84  nop
0x14000bb85  add     rsp, 28h
0x14000bb89  retn
```
