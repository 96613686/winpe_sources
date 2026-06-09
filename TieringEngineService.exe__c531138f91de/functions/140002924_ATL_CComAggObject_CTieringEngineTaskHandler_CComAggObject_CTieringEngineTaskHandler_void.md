# ATL::CComAggObject<CTieringEngineTaskHandler>::~CComAggObject<CTieringEngineTaskHandler>(void)

- ea: `0x140002924`
- end: `0x140002997`
- name: `??1?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@UEAA@XZ`
- size: `115`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140002c10`

## callees

- `0x140002924`
- `0x140002ac8`
- `0x140009f1c`
- `0x140041010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CTieringEngineTaskHandler>::~CComAggObject<CTieringEngineTaskHandler>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CTieringEngineTaskHandler>::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, a1 + 24);
  }
  (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTieringEngineTaskHandler::~CTieringEngineTaskHandler((CTieringEngineTaskHandler *)(a1 + 24));
}

```

## disassembly

```asm
0x140002924  push    rbx
0x140002926  sub     rsp, 20h
0x14000292a  lea     rax, ??_7?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CTieringEngineTaskHandler>::`vftable'
0x140002931  mov     dword ptr [rcx+8], 0C0000001h
0x140002938  mov     [rcx], rax
0x14000293b  mov     rbx, rcx
0x14000293e  mov     rcx, cs:WPP_GLOBAL_Control
0x140002945  lea     rax, WPP_GLOBAL_Control
0x14000294c  cmp     rcx, rax
0x14000294f  jz      short loc_140002976
0x140002951  test    byte ptr [rcx+1Ch], 1
0x140002955  jz      short loc_140002976
0x140002957  cmp     byte ptr [rcx+19h], 4
0x14000295b  jb      short loc_140002976
0x14000295d  mov     rcx, [rcx+10h]
0x140002961  lea     r9, [rbx+18h]
0x140002965  mov     edx, 10h
0x14000296a  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140002971  call    WPP_SF_q
0x140002976  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000297d  mov     rax, [rcx]
0x140002980  mov     rax, [rax+10h]
0x140002984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002989  lea     rcx, [rbx+18h]; this
0x14000298d  add     rsp, 20h
0x140002991  pop     rbx
0x140002992  jmp     ??1CTieringEngineTaskHandler@@QEAA@XZ; CTieringEngineTaskHandler::~CTieringEngineTaskHandler(void)
```
