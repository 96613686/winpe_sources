# ATL::CComObject<CTieringEngineApiServer>::~CComObject<CTieringEngineApiServer>(void)

- ea: `0x1400029a0`
- end: `0x140002a0e`
- name: `??1?$CComObject@VCTieringEngineApiServer@@@ATL@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(CTieringEngineApiServer *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002c50`

## callees

- `0x1400029a0`
- `0x140004a40`
- `0x1400381e8`
- `0x140041010`

## pseudocode

```c
void __fastcall ATL::CComObject<CTieringEngineApiServer>::~CComObject<CTieringEngineApiServer>(
        CTieringEngineApiServer *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CTieringEngineApiServer>::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
  }
  (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTieringEngineApiServer::~CTieringEngineApiServer(this);
}

```

## disassembly

```asm
0x1400029a0  push    rbx
0x1400029a2  sub     rsp, 20h
0x1400029a6  lea     rax, ??_7?$CComObject@VCTieringEngineApiServer@@@ATL@@6B@; const ATL::CComObject<CTieringEngineApiServer>::`vftable'
0x1400029ad  mov     dword ptr [rcx+8], 0C0000001h
0x1400029b4  mov     [rcx], rax
0x1400029b7  mov     rbx, rcx
0x1400029ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029c1  lea     rax, WPP_GLOBAL_Control
0x1400029c8  cmp     rcx, rax
0x1400029cb  jz      short loc_1400029EE
0x1400029cd  test    byte ptr [rcx+1Ch], 1
0x1400029d1  jz      short loc_1400029EE
0x1400029d3  cmp     byte ptr [rcx+19h], 4
0x1400029d7  jb      short loc_1400029EE
0x1400029d9  mov     rcx, [rcx+10h]
0x1400029dd  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x1400029e4  mov     edx, 0Bh
0x1400029e9  call    WPP_SF_
0x1400029ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400029f5  mov     rax, [rcx]
0x1400029f8  mov     rax, [rax+10h]
0x1400029fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a01  mov     rcx, rbx; this
0x140002a04  add     rsp, 20h
0x140002a08  pop     rbx
0x140002a09  jmp     ??1CTieringEngineApiServer@@QEAA@XZ; CTieringEngineApiServer::~CTieringEngineApiServer(void)
```
