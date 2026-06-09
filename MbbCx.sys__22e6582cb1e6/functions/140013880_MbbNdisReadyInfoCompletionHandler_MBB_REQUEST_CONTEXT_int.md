# MbbNdisReadyInfoCompletionHandler(_MBB_REQUEST_CONTEXT *,int)

- ea: `0x140013880`
- end: `0x1400138c7`
- name: `?MbbNdisReadyInfoCompletionHandler@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `71`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140013880`
- `0x14002f75c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400138a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138a9`

## pseudocode

```c
void __fastcall MbbNdisReadyInfoCompletionHandler(struct _MBB_REQUEST_CONTEXT *a1, int a2)
{
  void *v3; // rcx

  if ( a2 )
  {
    if ( (*((_DWORD *)a1 + 182) & 4) != 0 )
      MbbNdisIndicateReadyInfoFailure(a1);
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
0x140013880  test    edx, edx
0x140013882  jz      short locret_1400138C5
0x140013884  push    rbx
0x140013885  sub     rsp, 20h
0x140013889  mov     eax, [rcx+2D8h]
0x14001388f  mov     rbx, rcx
0x140013892  test    al, 4
0x140013894  jz      short loc_14001389B
0x140013896  call    ?MbbNdisIndicateReadyInfoFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbNdisIndicateReadyInfoFailure(_MBB_REQUEST_CONTEXT *)
0x14001389b  mov     rcx, [rbx+2E0h]; P
0x1400138a2  test    rcx, rcx
0x1400138a5  jz      short loc_1400138C0
0x1400138a7  xor     edx, edx; Tag
0x1400138a9  call    cs:__imp_ExFreePoolWithTag
0x1400138b0  nop     dword ptr [rax+rax+00h]
0x1400138b5  mov     qword ptr [rbx+2E0h], 0
0x1400138c0  add     rsp, 20h
0x1400138c4  pop     rbx
0x1400138c5  retn
```
