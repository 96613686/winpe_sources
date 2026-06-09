# ATL::CComObject<CIconOverlayHandler>::CComObject<CIconOverlayHandler>(void *)

- ea: `0x1800040c4`
- end: `0x180004140`
- name: `??0?$CComObject@VCIconOverlayHandler@@@ATL@@QEAA@PEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003fb8`

## callees

- `0x1800040c4`
- `0x18000684c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004114`
- `KERNEL32!InitializeCriticalSection` at `0x180004114`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIconOverlayHandler>::CComObject<CIconOverlayHandler>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct ATL::CAtlModule *v5; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 56) = -1;
  *(_DWORD *)(a1 + 60) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids, a4);
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v5 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CIconOverlayHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
  return a1;
}

```

## disassembly

```asm
0x1800040c4  push    rbx
0x1800040c6  sub     rsp, 20h
0x1800040ca  mov     dword ptr [rcx+8], 0
0x1800040d1  mov     rbx, rcx
0x1800040d4  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x1800040db  mov     dword ptr [rcx+3Ch], 0
0x1800040e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040e9  lea     rax, WPP_GLOBAL_Control
0x1800040f0  cmp     rcx, rax
0x1800040f3  jz      short loc_180004110
0x1800040f5  test    byte ptr [rcx+1Ch], 20h
0x1800040f9  jz      short loc_180004110
0x1800040fb  mov     rcx, [rcx+10h]
0x1800040ff  lea     r8, WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids
0x180004106  mov     edx, 0Ah
0x18000410b  call    WPP_SF_
0x180004110  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004114  call    cs:__imp_InitializeCriticalSection
0x18000411a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004121  lea     rax, ??_7?$CComObject@VCIconOverlayHandler@@@ATL@@6B@; const ATL::CComObject<CIconOverlayHandler>::`vftable'
0x180004128  mov     [rbx], rax
0x18000412b  mov     rax, [rcx]
0x18000412e  mov     rax, [rax+8]
0x180004132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004137  mov     rax, rbx
0x18000413a  add     rsp, 20h
0x18000413e  pop     rbx
0x18000413f  retn
```
