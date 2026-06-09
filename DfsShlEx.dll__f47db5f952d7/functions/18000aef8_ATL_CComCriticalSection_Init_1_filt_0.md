# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000aef8`
- end: `0x18000af18`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall ATL::CComCriticalSection::Init_::_1_::filt_0(_DWORD **a1)
{
  return **a1 == -1073741801;
}

```

## disassembly

```asm
0x18000aef8  push    rbp
0x18000aefa  sub     rsp, 20h
0x18000aefe  mov     rbp, rdx
0x18000af01  mov     rax, [rcx]
0x18000af04  xor     ecx, ecx
0x18000af06  cmp     dword ptr [rax], 0C0000017h
0x18000af0c  setz    cl
0x18000af0f  mov     eax, ecx
0x18000af11  add     rsp, 20h
0x18000af15  pop     rbp
0x18000af16  retn
```
