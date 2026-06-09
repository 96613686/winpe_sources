# ATL::CComObject<CWerEventTraceExtender>::~CComObject<CWerEventTraceExtender>(void)

- ea: `0x1800028cc`
- end: `0x180002941`
- name: `??1?$CComObject@VCWerEventTraceExtender@@@ATL@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002a70`

## callees

- `0x1800028cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002934`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002934`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<CWerEventTraceExtender>::~CComObject<CWerEventTraceExtender>(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CWerEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *(_BYTE *)(a1 + 72) )
  {
    *(_BYTE *)(a1 + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  }
}

```

## disassembly

```asm
0x1800028cc  push    rbx
0x1800028ce  sub     rsp, 20h
0x1800028d2  mov     rbx, rcx
0x1800028d5  lea     rax, ??_7?$CComObject@VCWerEventTraceExtender@@@ATL@@6B@; const ATL::CComObject<CWerEventTraceExtender>::`vftable'
0x1800028dc  mov     [rcx], rax
0x1800028df  mov     dword ptr [rcx+18h], 0C0000001h
0x1800028e6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800028ed  mov     rax, [rcx]
0x1800028f0  mov     rax, [rax+10h]
0x1800028f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f9  nop
0x1800028fa  mov     rcx, [rbx+10h]
0x1800028fe  test    rcx, rcx
0x180002901  jz      short loc_180002910
0x180002903  mov     rax, [rcx]
0x180002906  mov     rax, [rax+10h]
0x18000290a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290f  nop
0x180002910  mov     rcx, [rbx+8]
0x180002914  test    rcx, rcx
0x180002917  jz      short loc_180002926
0x180002919  mov     rax, [rcx]
0x18000291c  mov     rax, [rax+10h]
0x180002920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002925  nop
0x180002926  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000292a  cmp     byte ptr [rcx+28h], 0
0x18000292e  jz      short loc_18000293B
0x180002930  mov     byte ptr [rcx+28h], 0
0x180002934  call    cs:__imp_DeleteCriticalSection
0x18000293a  nop
0x18000293b  add     rsp, 20h
0x18000293f  pop     rbx
0x180002940  retn
```
