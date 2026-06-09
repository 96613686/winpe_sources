# PolicyModel::CFilePath::CFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000db08`
- end: `0x14000db96`
- name: `??0CFilePath@PolicyModel@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140009520`

## callees

- `0x1400070e4`
- `0x14000997c`
- `0x14000ba60`
- `0x14000baf8`
- `0x14000db08`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePath::CFilePath(__int64 a1, __int64 a2)
{
  PolicyModel::CPolicyElement::CPolicyElement((PolicyModel::CPolicyElement *)a1);
  PolicyModel::CXmlSerializer::CXmlSerializer((PolicyModel::CXmlSerializer *)(a1 + 8));
  *(_QWORD *)a1 = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'};
  *(_QWORD *)(a1 + 8) = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'};
  std::wstring::wstring(a1 + 16, a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids);
  return a1;
}

```

## disassembly

```asm
0x14000db08  mov     [rsp+arg_8], rbx
0x14000db0d  mov     [rsp+arg_10], rsi
0x14000db12  mov     [rsp+arg_0], rcx
0x14000db17  push    rdi
0x14000db18  sub     rsp, 20h
0x14000db1c  mov     rdi, rdx
0x14000db1f  mov     rsi, rcx
0x14000db22  call    ??0CPolicyElement@PolicyModel@@IEAA@XZ; PolicyModel::CPolicyElement::CPolicyElement(void)
0x14000db27  nop
0x14000db28  lea     rcx, [rsi+8]; this
0x14000db2c  call    ??0CXmlSerializer@PolicyModel@@IEAA@XZ; PolicyModel::CXmlSerializer::CXmlSerializer(void)
0x14000db31  nop
0x14000db32  lea     rax, ??_7CFilePath@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000db39  mov     [rsi], rax
0x14000db3c  lea     rax, ??_7CFilePath@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000db43  mov     [rsi+8], rax
0x14000db47  lea     rcx, [rsi+10h]
0x14000db4b  mov     rdx, rdi
0x14000db4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000db53  nop
0x14000db54  lea     rax, WPP_GLOBAL_Control
0x14000db5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db62  cmp     rcx, rax
0x14000db65  jz      short loc_14000DB83
0x14000db67  test    byte ptr [rcx+1Ch], 8
0x14000db6b  jz      short loc_14000DB83
0x14000db6d  mov     edx, 0Ah
0x14000db72  lea     r8, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids
0x14000db79  mov     rcx, [rcx+10h]
0x14000db7d  call    WPP_SF_
0x14000db82  nop
0x14000db83  mov     rax, rsi
0x14000db86  mov     rbx, [rsp+28h+arg_8]
0x14000db8b  mov     rsi, [rsp+28h+arg_10]
0x14000db90  add     rsp, 20h
0x14000db94  pop     rdi
0x14000db95  retn
```
