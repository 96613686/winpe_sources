# ATL::CCRTHeap::GetSize(void *)

- ea: `0x1800028d0`
- end: `0x1800028da`
- name: `?GetSize@CCRTHeap@ATL@@UEAA_KPEAX@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(ATL::CCRTHeap *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x1800028d3`

## pseudocode

```c
__int64 __fastcall ATL::CCRTHeap::GetSize(ATL::CCRTHeap *this, void *a2)
{
  return _o__msize(a2);
}

```

## disassembly

```asm
0x1800028d0  mov     rcx, rdx
0x1800028d3  jmp     cs:__imp__o__msize
```
