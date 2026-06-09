# SdbpCreateDatabaseInMemory

- ea: `0x180040584`
- end: `0x180040647`
- name: `SdbpCreateDatabaseInMemory`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180037b2c`
- `0x18003f760`
- `0x18004034c`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x180037274`
- `0x180040584`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800405b3`
- `ntdll!RtlAllocateHeap` at `0x1800405b3`

## string_xrefs

- `0x1800405ce`: `SdbpCreateDatabaseInMemory`
- `0x180040618`: `SdbpCreateDatabaseInMemory`
- `0x18004060b`: `Failed to write the header to disk`

## pseudocode

```c
_DWORD *SdbpCreateDatabaseInMemory()
{
  _DWORD *Heap; // rax
  _DWORD *v1; // rbx
  __int64 v3; // [rsp+30h] [rbp-18h] BYREF
  int v4; // [rsp+38h] [rbp-10h]

  v4 = 1717724275;
  v3 = 3;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v1 = Heap;
  if ( Heap )
  {
    Heap[6] |= 9u;
    Heap[4] = 1;
    if ( !(unsigned int)SdbpWriteBufferedData(Heap, 0, &v3, 12, 0) )
    {
      AslLogCallPrintf(1, "SdbpCreateDatabaseInMemory", 334, "Failed to write the header to disk");
      AslFree(NtCurrentPeb()->ProcessHeap, v1);
      return 0;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCreateDatabaseInMemory", 317, "Failed to allocate PDB");
  }
  return v1;
}

```

## disassembly

```asm
0x180040584  push    rbx
0x180040586  sub     rsp, 40h
0x18004058a  mov     rcx, gs:60h
0x180040593  mov     edx, 8; Flags
0x180040598  mov     r8d, 0A80h; Size
0x18004059e  mov     [rsp+48h+var_10], 66626473h
0x1800405a6  mov     [rsp+48h+var_18], 3
0x1800405af  mov     rcx, [rcx+30h]; HeapHandle
0x1800405b3  call    cs:__imp_RtlAllocateHeap
0x1800405b9  mov     rbx, rax
0x1800405bc  test    rax, rax
0x1800405bf  jnz     short loc_1800405DF
0x1800405c1  lea     r9, aFailedToAlloca_12; "Failed to allocate PDB"
0x1800405c8  mov     r8d, 13Dh
0x1800405ce  lea     rdx, aSdbpcreatedata; "SdbpCreateDatabaseInMemory"
0x1800405d5  lea     ecx, [rax+1]
0x1800405d8  call    AslLogCallPrintf
0x1800405dd  jmp     short loc_18004063E
0x1800405df  or      dword ptr [rax+18h], 9
0x1800405e3  lea     r8, [rsp+48h+var_18]
0x1800405e8  mov     r9d, 0Ch
0x1800405ee  mov     dword ptr [rax+10h], 1
0x1800405f5  xor     edx, edx
0x1800405f7  mov     [rsp+48h+var_28], 0
0x1800405ff  mov     rcx, rbx
0x180040602  call    SdbpWriteBufferedData
0x180040607  test    eax, eax
0x180040609  jnz     short loc_18004063E
0x18004060b  lea     r9, aFailedToWriteT_3; "Failed to write the header to disk"
0x180040612  mov     r8d, 14Eh
0x180040618  lea     rdx, aSdbpcreatedata; "SdbpCreateDatabaseInMemory"
0x18004061f  lea     ecx, [rax+1]
0x180040622  call    AslLogCallPrintf
0x180040627  mov     rcx, gs:60h
0x180040630  mov     rdx, rbx
0x180040633  mov     rcx, [rcx+30h]
0x180040637  call    AslFree
0x18004063c  xor     ebx, ebx
0x18004063e  mov     rax, rbx
0x180040641  add     rsp, 40h
0x180040645  pop     rbx
0x180040646  retn
```
