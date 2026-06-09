# ATL::CComObject<CDfsShellAdmin>::`scalar deleting destructor'(uint)

- ea: `0x180002dc0`
- end: `0x180002e0f`
- name: `??_G?$CComObject@VCDfsShellAdmin@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002dc0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002dfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002dfb`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CDfsShellAdmin>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CDfsShellAdmin>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002dc0  mov     [rsp+arg_0], rbx
0x180002dc5  push    rdi
0x180002dc6  sub     rsp, 20h
0x180002dca  mov     dword ptr [rcx+8], 0C0000001h
0x180002dd1  lea     rax, ??_7?$CComObject@VCDfsShellAdmin@@@ATL@@6B@; const ATL::CComObject<CDfsShellAdmin>::`vftable'
0x180002dd8  mov     [rcx], rax
0x180002ddb  mov     rdi, rcx
0x180002dde  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002de5  mov     ebx, edx
0x180002de7  mov     rax, [rcx]
0x180002dea  mov     rax, [rax+10h]
0x180002dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df3  test    bl, 1
0x180002df6  jz      short loc_180002E01
0x180002df8  mov     rcx, rdi
0x180002dfb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e01  mov     rbx, [rsp+28h+arg_0]
0x180002e06  mov     rax, rdi
0x180002e09  add     rsp, 20h
0x180002e0d  pop     rdi
0x180002e0e  retn
```
