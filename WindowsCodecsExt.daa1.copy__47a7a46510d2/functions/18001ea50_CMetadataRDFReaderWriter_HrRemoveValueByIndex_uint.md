# CMetadataRDFReaderWriter::HrRemoveValueByIndex(uint)

- ea: `0x18001ea50`
- end: `0x18001eada`
- name: `?HrRemoveValueByIndex@CMetadataRDFReaderWriter@@MEAAJI@Z`
- size: `138`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e780`

## callees

- `0x180001010`
- `0x1800171c4`
- `0x18001ea50`
- `0x180023a98`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrRemoveValueByIndex(CMetadataRDFReaderWriter *this, int a2)
{
  unsigned int ItemPosition; // ebx
  int v5; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v6; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  ItemPosition = CMetadataRDFReaderWriter::FindItemPosition(this, 0, a2, 0, 0, &v5, &v6);
  if ( (ItemPosition & 0x80000000) != 0 )
  {
    if ( !g_doStackCaptures )
      return ItemPosition;
LABEL_6:
    DoStackCapture(ItemPosition);
    return ItemPosition;
  }
  if ( !v5 )
  {
    CMetadataRDFReaderWriter::RemoveItemByPosition(this, v6);
    return ItemPosition;
  }
  ItemPosition = -2003292352;
  if ( g_doStackCaptures )
    goto LABEL_6;
  return ItemPosition;
}

```

## disassembly

```asm
0x18001ea50  mov     r11, rsp
0x18001ea53  mov     [r11+8], rbx
0x18001ea57  push    rdi
0x18001ea58  sub     rsp, 40h
0x18001ea5c  lea     rax, [r11+20h]
0x18001ea60  mov     [rsp+48h+arg_18], 0
0x18001ea68  mov     [r11-18h], rax
0x18001ea6c  mov     r8d, edx; unsigned int
0x18001ea6f  lea     rax, [r11+18h]
0x18001ea73  mov     [rsp+48h+arg_10], 0
0x18001ea7b  mov     [r11-20h], rax
0x18001ea7f  xor     r9d, r9d; struct tagPROPVARIANT *
0x18001ea82  xor     edx, edx; int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)
0x18001ea84  mov     qword ptr [r11-28h], 0
0x18001ea8c  mov     rdi, rcx
0x18001ea8f  call    ?FindItemPosition@CMetadataRDFReaderWriter@@IEAAJP6AJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@ZI112PEAI@Z; CMetadataRDFReaderWriter::FindItemPosition(long (*)(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *),uint,tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x18001ea94  mov     ebx, eax
0x18001ea96  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18001ea9c  test    ebx, ebx
0x18001ea9e  jns     short loc_18001EAA8
0x18001eaa0  test    eax, eax
0x18001eaa2  jnz     short loc_18001EAB8
0x18001eaa4  test    ebx, ebx
0x18001eaa6  js      short loc_18001EACD
0x18001eaa8  cmp     [rsp+48h+arg_10], 0
0x18001eaad  jz      short loc_18001EAC1
0x18001eaaf  mov     ebx, 88982F40h
0x18001eab4  test    eax, eax
0x18001eab6  jz      short loc_18001EACD
0x18001eab8  mov     ecx, ebx; int
0x18001eaba  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001eabf  jmp     short loc_18001EACD
0x18001eac1  mov     edx, [rsp+48h+arg_18]; unsigned int
0x18001eac5  mov     rcx, rdi; this
0x18001eac8  call    ?RemoveItemByPosition@CMetadataRDFReaderWriter@@IEAAXI@Z; CMetadataRDFReaderWriter::RemoveItemByPosition(uint)
0x18001eacd  mov     eax, ebx
0x18001eacf  mov     rbx, [rsp+48h+arg_0]
0x18001ead4  add     rsp, 40h
0x18001ead8  pop     rdi
0x18001ead9  retn
```
