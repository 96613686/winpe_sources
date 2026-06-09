# _CClassFactory::CreateInstance_::_1_::catch$1

- ea: `0x18000ba36`
- end: `0x18000ba7f`
- name: `_CClassFactory::CreateInstance_::_1_::catch$1`
- size: `73`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002e3c`
- `0x18000ba36`

## string_xrefs

- `0x18000ba61`: `CClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance_::_1_::catch_1(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    McTemplateU0sqq_EventWriteTransfer(a1, a2, (unsigned int)"CClassFactory::CreateInstance", 123, 14);
  return 0;
}

```

## disassembly

```asm
0x18000ba36  mov     [rsp+arg_8], rdx
0x18000ba3b  push    rbp
0x18000ba3c  sub     rsp, 30h
0x18000ba40  mov     rbp, rdx
0x18000ba43  mov     dword ptr [rbp+48h], 8007000Eh
0x18000ba4a  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18000ba51  jz      short loc_18000BA6E
0x18000ba53  mov     [rsp+38h+var_18], 8007000Eh
0x18000ba5b  mov     r9d, 7Bh ; '{'
0x18000ba61  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x18000ba68  call    McTemplateU0sqq_EventWriteTransfer
0x18000ba6d  nop
0x18000ba6e  mov     rax, 0
0x18000ba78  add     rsp, 30h
0x18000ba7c  pop     rbp
0x18000ba7d  retn
```
