# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000b834`
- end: `0x18000b854`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: `_BOOL8 __fastcall(_DWORD **)`
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
0x18000b834  push    rbp
0x18000b836  sub     rsp, 20h
0x18000b83a  mov     rbp, rdx
0x18000b83d  mov     rax, [rcx]
0x18000b840  xor     ecx, ecx
0x18000b842  cmp     dword ptr [rax], 0C0000017h
0x18000b848  setz    cl
0x18000b84b  mov     eax, ecx
0x18000b84d  add     rsp, 20h
0x18000b851  pop     rbp
0x18000b852  retn
```
