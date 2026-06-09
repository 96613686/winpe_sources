# ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(void *)

- ea: `0x180005a30`
- end: `0x180005ab0`
- name: `??0?$CComObject@VCContextMenuHandler@@@ATL@@QEAA@PEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003000`
- `0x180005c80`

## callees

- `0x180005a30`
- `0x18000684c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct ATL::CAtlModule *v5; // rcx

  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
  v5 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CContextMenuHandler>::`vftable'{for `IContextMenu'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CContextMenuHandler>::`vftable'{for `IShellExtInit'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
  return a1;
}

```

## disassembly

```asm
0x180005a30  push    rbx
0x180005a32  sub     rsp, 20h
0x180005a36  xor     eax, eax
0x180005a38  mov     rbx, rcx
0x180005a3b  mov     [rcx+10h], eax
0x180005a3e  mov     [rcx+18h], rax
0x180005a42  mov     [rcx+20h], rax
0x180005a46  mov     [rcx+28h], rax
0x180005a4a  mov     [rcx+30h], rax
0x180005a4e  mov     [rcx+38h], eax
0x180005a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a58  lea     rax, WPP_GLOBAL_Control
0x180005a5f  cmp     rcx, rax
0x180005a62  jz      short loc_180005A7F
0x180005a64  test    byte ptr [rcx+1Ch], 20h
0x180005a68  jz      short loc_180005A7F
0x180005a6a  mov     rcx, [rcx+10h]
0x180005a6e  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180005a75  mov     edx, 0Ah
0x180005a7a  call    WPP_SF_
0x180005a7f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005a86  lea     rax, ??_7?$CComObject@VCContextMenuHandler@@@ATL@@6BIContextMenu@@@; const ATL::CComObject<CContextMenuHandler>::`vftable'{for `IContextMenu'}
0x180005a8d  mov     [rbx], rax
0x180005a90  lea     rax, ??_7?$CComObject@VCContextMenuHandler@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CContextMenuHandler>::`vftable'{for `IShellExtInit'}
0x180005a97  mov     [rbx+8], rax
0x180005a9b  mov     rax, [rcx]
0x180005a9e  mov     rax, [rax+8]
0x180005aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa7  mov     rax, rbx
0x180005aaa  add     rsp, 20h
0x180005aae  pop     rbx
0x180005aaf  retn
```
