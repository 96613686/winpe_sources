# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(uint)

- ea: `0x180005e30`
- end: `0x180005e7f`
- name: `??_E?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005e30`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005e30  mov     [rsp+arg_0], rbx
0x180005e35  push    rdi
0x180005e36  sub     rsp, 20h
0x180005e3a  mov     dword ptr [rcx+8], 0C0000001h
0x180005e41  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x180005e48  mov     [rcx], rax
0x180005e4b  mov     rdi, rcx
0x180005e4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005e55  mov     ebx, edx
0x180005e57  mov     rax, [rcx]
0x180005e5a  mov     rax, [rax+10h]
0x180005e5e  call    cs:__guard_dispatch_icall_fptr
0x180005e64  test    bl, 1
0x180005e67  jz      short loc_180005E71
0x180005e69  mov     rcx, rdi; Block
0x180005e6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e71  mov     rax, rdi
0x180005e74  mov     rbx, [rsp+28h+arg_0]
0x180005e79  add     rsp, 20h
0x180005e7d  pop     rdi
0x180005e7e  retn
```
