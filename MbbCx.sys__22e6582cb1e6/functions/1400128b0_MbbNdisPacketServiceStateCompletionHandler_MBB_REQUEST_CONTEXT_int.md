# MbbNdisPacketServiceStateCompletionHandler(_MBB_REQUEST_CONTEXT *,int)

- ea: `0x1400128b0`
- end: `0x1400128f7`
- name: `?MbbNdisPacketServiceStateCompletionHandler@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `71`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400128b0`
- `0x14002f0c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400128d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400128d9`

## pseudocode

```c
void __fastcall MbbNdisPacketServiceStateCompletionHandler(struct _MBB_REQUEST_CONTEXT *a1, int a2)
{
  void *v3; // rcx

  if ( a2 )
  {
    if ( (*((_DWORD *)a1 + 182) & 2) != 0 )
      MbbNdisIndicatePacketServiceFailure(a1, a2);
    v3 = (void *)*((_QWORD *)a1 + 92);
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0);
      *((_QWORD *)a1 + 92) = 0;
    }
  }
}

```

## disassembly

```asm
0x1400128b0  test    edx, edx
0x1400128b2  jz      short locret_1400128F5
0x1400128b4  push    rbx
0x1400128b5  sub     rsp, 20h
0x1400128b9  mov     eax, [rcx+2D8h]
0x1400128bf  mov     rbx, rcx
0x1400128c2  test    al, 2
0x1400128c4  jz      short loc_1400128CB
0x1400128c6  call    ?MbbNdisIndicatePacketServiceFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@K@Z; MbbNdisIndicatePacketServiceFailure(_MBB_REQUEST_CONTEXT *,ulong)
0x1400128cb  mov     rcx, [rbx+2E0h]; P
0x1400128d2  test    rcx, rcx
0x1400128d5  jz      short loc_1400128F0
0x1400128d7  xor     edx, edx; Tag
0x1400128d9  call    cs:__imp_ExFreePoolWithTag
0x1400128e0  nop     dword ptr [rax+rax+00h]
0x1400128e5  mov     qword ptr [rbx+2E0h], 0
0x1400128f0  add     rsp, 20h
0x1400128f4  pop     rbx
0x1400128f5  retn
```
