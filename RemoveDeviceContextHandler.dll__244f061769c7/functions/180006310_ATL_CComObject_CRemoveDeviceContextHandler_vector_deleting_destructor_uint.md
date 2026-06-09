# ATL::CComObject<CRemoveDeviceContextHandler>::`vector deleting destructor'(uint)

- ea: `0x180006310`
- end: `0x180006369`
- name: `??_E?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAPEAXI@Z`
- size: `89`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001be0`
- `0x180006310`
- `0x18000e010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CRemoveDeviceContextHandler>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[4] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180006310  mov     [rsp+arg_0], rbx
0x180006315  push    rdi
0x180006316  sub     rsp, 20h
0x18000631a  mov     dword ptr [rcx+10h], 0C0000001h
0x180006321  lea     rax, ??_7?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@6BIExplorerCommand@@@; const ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'}
0x180006328  mov     [rcx], rax
0x18000632b  mov     rdi, rcx
0x18000632e  lea     rax, ??_7?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@6BIInitializeCommand@@@; const ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'}
0x180006335  mov     ebx, edx
0x180006337  mov     [rcx+8], rax
0x18000633b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006342  mov     rax, [rcx]
0x180006345  mov     rax, [rax+10h]
0x180006349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634e  test    bl, 1
0x180006351  jz      short loc_18000635B
0x180006353  mov     rcx, rdi; Block
0x180006356  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000635b  mov     rbx, [rsp+28h+arg_0]
0x180006360  mov     rax, rdi
0x180006363  add     rsp, 20h
0x180006367  pop     rdi
0x180006368  retn
```
