# ATL::CComObject<CTieringEngineTaskHandler>::~CComObject<CTieringEngineTaskHandler>(void)

- ea: `0x140002a14`
- end: `0x140002a85`
- name: `??1?$CComObject@VCTieringEngineTaskHandler@@@ATL@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(CTieringEngineTaskHandler *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140002c90`

## callees

- `0x140002a14`
- `0x140002ac8`
- `0x140009f1c`
- `0x140041010`

## pseudocode

```c
void __fastcall ATL::CComObject<CTieringEngineTaskHandler>::~CComObject<CTieringEngineTaskHandler>(
        CTieringEngineTaskHandler *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CTieringEngineTaskHandler>::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, this);
  }
  (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTieringEngineTaskHandler::~CTieringEngineTaskHandler(this);
}

```

## disassembly

```asm
0x140002a14  push    rbx
0x140002a16  sub     rsp, 20h
0x140002a1a  lea     rax, ??_7?$CComObject@VCTieringEngineTaskHandler@@@ATL@@6B@; const ATL::CComObject<CTieringEngineTaskHandler>::`vftable'
0x140002a21  mov     dword ptr [rcx+8], 0C0000001h
0x140002a28  mov     [rcx], rax
0x140002a2b  mov     rbx, rcx
0x140002a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a35  lea     rax, WPP_GLOBAL_Control
0x140002a3c  cmp     rcx, rax
0x140002a3f  jz      short loc_140002A65
0x140002a41  test    byte ptr [rcx+1Ch], 1
0x140002a45  jz      short loc_140002A65
0x140002a47  cmp     byte ptr [rcx+19h], 4
0x140002a4b  jb      short loc_140002A65
0x140002a4d  mov     rcx, [rcx+10h]
0x140002a51  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140002a58  mov     edx, 10h
0x140002a5d  mov     r9, rbx
0x140002a60  call    WPP_SF_q
0x140002a65  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002a6c  mov     rax, [rcx]
0x140002a6f  mov     rax, [rax+10h]
0x140002a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a78  mov     rcx, rbx; this
0x140002a7b  add     rsp, 20h
0x140002a7f  pop     rbx
0x140002a80  jmp     ??1CTieringEngineTaskHandler@@QEAA@XZ; CTieringEngineTaskHandler::~CTieringEngineTaskHandler(void)
```
