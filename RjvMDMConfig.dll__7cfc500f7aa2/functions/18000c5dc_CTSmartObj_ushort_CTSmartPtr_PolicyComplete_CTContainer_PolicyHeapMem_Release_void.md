# CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)

- ea: `0x18000c5dc`
- end: `0x18000c618`
- name: `?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ`
- size: `60`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007388`
- `0x18000c980`
- `0x180018f30`
- `0x180019044`
- `0x18001a204`
- `0x18001aa68`
- `0x18001ad90`
- `0x18001afbc`
- `0x18001b0dc`

## callees

- `0x18000c5dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c605`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c605`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c5f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c5f1`

## pseudocode

```c
void __fastcall CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x18000c5dc  push    rbx
0x18000c5de  sub     rsp, 20h
0x18000c5e2  mov     rbx, [rcx]
0x18000c5e5  mov     qword ptr [rcx], 0
0x18000c5ec  test    rbx, rbx
0x18000c5ef  jz      short loc_18000C611
0x18000c5f1  call    cs:__imp_GetProcessHeap
0x18000c5f8  nop     dword ptr [rax+rax+00h]
0x18000c5fd  mov     r8, rbx; lpMem
0x18000c600  xor     edx, edx; dwFlags
0x18000c602  mov     rcx, rax; hHeap
0x18000c605  call    cs:__imp_HeapFree
0x18000c60c  nop     dword ptr [rax+rax+00h]
0x18000c611  add     rsp, 20h
0x18000c615  pop     rbx
0x18000c616  retn
```
