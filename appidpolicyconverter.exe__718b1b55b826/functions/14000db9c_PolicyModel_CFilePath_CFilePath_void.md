# PolicyModel::CFilePath::~CFilePath(void)

- ea: `0x14000db9c`
- end: `0x14000dc1d`
- name: `??1CFilePath@PolicyModel@@UEAA@XZ`
- size: `129`
- prototype: `void __fastcall(PolicyModel::CFilePath *this, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140009520`
- `0x14000d7a8`
- `0x14000d840`
- `0x140014279`
- `0x140014ad2`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x14000bab0`
- `0x14000bb48`
- `0x14000db9c`

## pseudocode

```c
void __fastcall PolicyModel::CFilePath::~CFilePath(PolicyModel::CFilePath *this, __int64 a2)
{
  *(_QWORD *)this = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'};
  *((_QWORD *)this + 1) = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'};
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids);
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 16, a2, 0);
  PolicyModel::CXmlSerializer::~CXmlSerializer((PolicyModel::CFilePath *)((char *)this + 8));
  PolicyModel::CPolicyElement::~CPolicyElement(this);
}

```

## disassembly

```asm
0x14000db9c  mov     [rsp+arg_8], rbx
0x14000dba1  mov     [rsp+arg_0], rcx
0x14000dba6  push    rdi
0x14000dba7  sub     rsp, 20h
0x14000dbab  mov     rbx, rcx
0x14000dbae  lea     rax, ??_7CFilePath@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000dbb5  mov     [rcx], rax
0x14000dbb8  lea     rax, ??_7CFilePath@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000dbbf  mov     [rcx+8], rax
0x14000dbc3  lea     rax, WPP_GLOBAL_Control
0x14000dbca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbd1  cmp     rcx, rax
0x14000dbd4  jz      short loc_14000DBF2
0x14000dbd6  test    byte ptr [rcx+1Ch], 8
0x14000dbda  jz      short loc_14000DBF2
0x14000dbdc  mov     edx, 0Bh
0x14000dbe1  lea     r8, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids
0x14000dbe8  mov     rcx, [rcx+10h]
0x14000dbec  call    WPP_SF_
0x14000dbf1  nop
0x14000dbf2  lea     rcx, [rbx+10h]
0x14000dbf6  xor     r8d, r8d
0x14000dbf9  mov     dl, 1
0x14000dbfb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dc00  nop
0x14000dc01  lea     rcx, [rbx+8]; this
0x14000dc05  call    ??1CXmlSerializer@PolicyModel@@MEAA@XZ; PolicyModel::CXmlSerializer::~CXmlSerializer(void)
0x14000dc0a  nop
0x14000dc0b  mov     rcx, rbx; this
0x14000dc0e  mov     rbx, [rsp+28h+arg_8]
0x14000dc13  add     rsp, 20h
0x14000dc17  pop     rdi
0x14000dc18  jmp     ??1CPolicyElement@PolicyModel@@UEAA@XZ; PolicyModel::CPolicyElement::~CPolicyElement(void)
```
