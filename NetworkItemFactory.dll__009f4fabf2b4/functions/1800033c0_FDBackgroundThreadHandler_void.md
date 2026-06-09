# FDBackgroundThreadHandler(void *)

- ea: `0x1800033c0`
- end: `0x1800033ed`
- name: `?FDBackgroundThreadHandler@@YAKPEAX@Z`
- size: `45`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800033c0`
- `0x180005740`

## import_xrefs

- `ole32!CoUninitialize` at `0x1800033df`
- `ole32!CoUninitialize` at `0x1800033df`
- `ole32!CoInitializeEx` at `0x1800033cd`
- `ole32!CoInitializeEx` at `0x1800033cd`

## pseudocode

```c
__int64 __fastcall FDBackgroundThreadHandler(HANDLE *Parameter)
{
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    CNetworkItemFactory::s_StartFDInMTA(Parameter);
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x1800033c0  push    rbx
0x1800033c2  sub     rsp, 20h
0x1800033c6  mov     rbx, rcx
0x1800033c9  xor     edx, edx; dwCoInit
0x1800033cb  xor     ecx, ecx; pvReserved
0x1800033cd  call    cs:__imp_CoInitializeEx
0x1800033d3  test    eax, eax
0x1800033d5  js      short loc_1800033E5
0x1800033d7  mov     rcx, rbx; this
0x1800033da  call    ?s_StartFDInMTA@CNetworkItemFactory@@SAXPEAV1@@Z; CNetworkItemFactory::s_StartFDInMTA(CNetworkItemFactory *)
0x1800033df  call    cs:__imp_CoUninitialize
0x1800033e5  xor     eax, eax
0x1800033e7  add     rsp, 20h
0x1800033eb  pop     rbx
0x1800033ec  retn
```
