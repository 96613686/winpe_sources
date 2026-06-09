# ATL::CComAggObject<CTieringEngineApiServer>::~CComAggObject<CTieringEngineApiServer>(void)

- ea: `0x1400028ac`
- end: `0x14000291b`
- name: `??1?$CComAggObject@VCTieringEngineApiServer@@@ATL@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002bd0`

## callees

- `0x1400028ac`
- `0x140004a40`
- `0x1400381e8`
- `0x140041010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CTieringEngineApiServer>::~CComAggObject<CTieringEngineApiServer>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CTieringEngineApiServer>::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
  }
  (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTieringEngineApiServer::~CTieringEngineApiServer((CTieringEngineApiServer *)(a1 + 24));
}

```

## disassembly

```asm
0x1400028ac  push    rbx
0x1400028ae  sub     rsp, 20h
0x1400028b2  lea     rax, ??_7?$CComAggObject@VCTieringEngineApiServer@@@ATL@@6B@; const ATL::CComAggObject<CTieringEngineApiServer>::`vftable'
0x1400028b9  mov     dword ptr [rcx+8], 0C0000001h
0x1400028c0  mov     [rcx], rax
0x1400028c3  mov     rbx, rcx
0x1400028c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028cd  lea     rax, WPP_GLOBAL_Control
0x1400028d4  cmp     rcx, rax
0x1400028d7  jz      short loc_1400028FA
0x1400028d9  test    byte ptr [rcx+1Ch], 1
0x1400028dd  jz      short loc_1400028FA
0x1400028df  cmp     byte ptr [rcx+19h], 4
0x1400028e3  jb      short loc_1400028FA
0x1400028e5  mov     rcx, [rcx+10h]
0x1400028e9  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x1400028f0  mov     edx, 0Bh
0x1400028f5  call    WPP_SF_
0x1400028fa  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002901  mov     rax, [rcx]
0x140002904  mov     rax, [rax+10h]
0x140002908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000290d  lea     rcx, [rbx+18h]; this
0x140002911  add     rsp, 20h
0x140002915  pop     rbx
0x140002916  jmp     ??1CTieringEngineApiServer@@QEAA@XZ; CTieringEngineApiServer::~CTieringEngineApiServer(void)
```
