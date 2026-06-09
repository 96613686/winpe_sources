# ATL::CComObject<CAutoplayHandler>::~CComObject<CAutoplayHandler>(void)

- ea: `0x180005bb8`
- end: `0x180005c12`
- name: `??1?$CComObject@VCAutoplayHandler@@@ATL@@UEAA@XZ`
- size: `90`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b80`

## callees

- `0x180005bb8`
- `0x18000684c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAutoplayHandler>::~CComObject<CAutoplayHandler>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CAutoplayHandler>::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, a4);
  return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
}

```

## disassembly

```asm
0x180005bb8  sub     rsp, 28h
0x180005bbc  lea     rax, ??_7?$CComObject@VCAutoplayHandler@@@ATL@@6B@; const ATL::CComObject<CAutoplayHandler>::`vftable'
0x180005bc3  mov     dword ptr [rcx+8], 0C0000001h
0x180005bca  mov     [rcx], rax
0x180005bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bd4  lea     rax, WPP_GLOBAL_Control
0x180005bdb  cmp     rcx, rax
0x180005bde  jz      short loc_180005BFB
0x180005be0  test    byte ptr [rcx+1Ch], 20h
0x180005be4  jz      short loc_180005BFB
0x180005be6  mov     rcx, [rcx+10h]
0x180005bea  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x180005bf1  mov     edx, 0Ch
0x180005bf6  call    WPP_SF_
0x180005bfb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c02  mov     rax, [rcx]
0x180005c05  mov     rax, [rax+10h]
0x180005c09  add     rsp, 28h
0x180005c0d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
