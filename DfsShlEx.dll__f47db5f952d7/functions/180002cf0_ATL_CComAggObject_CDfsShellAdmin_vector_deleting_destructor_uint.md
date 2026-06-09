# ATL::CComAggObject<CDfsShellAdmin>::`vector deleting destructor'(uint)

- ea: `0x180002cf0`
- end: `0x180002d3f`
- name: `??_E?$CComAggObject@VCDfsShellAdmin@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002cf0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d2b`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CDfsShellAdmin>::`vector deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CDfsShellAdmin>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002cf0  mov     [rsp+arg_0], rbx
0x180002cf5  push    rdi
0x180002cf6  sub     rsp, 20h
0x180002cfa  mov     dword ptr [rcx+8], 0C0000001h
0x180002d01  lea     rax, ??_7?$CComAggObject@VCDfsShellAdmin@@@ATL@@6B@; const ATL::CComAggObject<CDfsShellAdmin>::`vftable'
0x180002d08  mov     [rcx], rax
0x180002d0b  mov     rdi, rcx
0x180002d0e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d15  mov     ebx, edx
0x180002d17  mov     rax, [rcx]
0x180002d1a  mov     rax, [rax+10h]
0x180002d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d23  test    bl, 1
0x180002d26  jz      short loc_180002D31
0x180002d28  mov     rcx, rdi
0x180002d2b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d31  mov     rbx, [rsp+28h+arg_0]
0x180002d36  mov     rax, rdi
0x180002d39  add     rsp, 20h
0x180002d3d  pop     rdi
0x180002d3e  retn
```
