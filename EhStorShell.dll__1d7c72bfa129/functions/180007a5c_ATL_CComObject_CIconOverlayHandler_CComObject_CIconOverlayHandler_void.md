# ATL::CComObject<CIconOverlayHandler>::~CComObject<CIconOverlayHandler>(void)

- ea: `0x180007a5c`
- end: `0x180007ac6`
- name: `??1?$CComObject@VCIconOverlayHandler@@@ATL@@UEAA@XZ`
- size: `106`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b80`

## callees

- `0x18000684c`
- `0x180007a5c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007aa8`
- `KERNEL32!DeleteCriticalSection` at `0x180007aa8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIconOverlayHandler>::~CComObject<CIconOverlayHandler>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CIconOverlayHandler>::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids, a4);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
}

```

## disassembly

```asm
0x180007a5c  push    rbx
0x180007a5e  sub     rsp, 20h
0x180007a62  lea     rax, ??_7?$CComObject@VCIconOverlayHandler@@@ATL@@6B@; const ATL::CComObject<CIconOverlayHandler>::`vftable'
0x180007a69  mov     dword ptr [rcx+8], 0C0000001h
0x180007a70  mov     [rcx], rax
0x180007a73  mov     rbx, rcx
0x180007a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a7d  lea     rax, WPP_GLOBAL_Control
0x180007a84  cmp     rcx, rax
0x180007a87  jz      short loc_180007AA4
0x180007a89  test    byte ptr [rcx+1Ch], 20h
0x180007a8d  jz      short loc_180007AA4
0x180007a8f  mov     rcx, [rcx+10h]
0x180007a93  lea     r8, WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids
0x180007a9a  mov     edx, 0Ch
0x180007a9f  call    WPP_SF_
0x180007aa4  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007aa8  call    cs:__imp_DeleteCriticalSection
0x180007aae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ab5  mov     rax, [rcx]
0x180007ab8  mov     rax, [rax+10h]
0x180007abc  add     rsp, 20h
0x180007ac0  pop     rbx
0x180007ac1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
