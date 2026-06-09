# CMetadataRDFReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18001e950`
- end: `0x18001ea43`
- name: `?HrRemoveValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0@Z`
- size: `243`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e7c0`
- `0x18001e880`
- `0x180024a30`

## callees

- `0x180001010`
- `0x18000285c`
- `0x1800171c4`
- `0x18001e950`
- `0x180023a98`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrRemoveValue(
        CMetadataRDFReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  int ItemPosition; // eax
  unsigned int v7; // ebx
  bool v8; // zf
  int v10; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  v10 = 0;
  if ( a3->vt != 72 )
  {
    if ( a3->vt == 31 )
    {
      if ( !(*(unsigned int (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 272LL))(this) )
      {
        ItemPosition = CMetadataRDFReaderWriter::FindItemPosition(
                         this,
                         (int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *))CMetadataRDFReaderWriter::CompareItemSchemaAndValue,
                         0,
                         a2,
                         a3,
                         &v10,
                         &v11);
        goto LABEL_6;
      }
      v7 = -2003292352;
    }
    else
    {
      v7 = -2147024809;
    }
    v8 = g_doStackCaptures == 0;
    goto LABEL_15;
  }
  ItemPosition = CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(this, a2, a3, &v10, &v11);
LABEL_6:
  v7 = ItemPosition;
  if ( ItemPosition < 0 )
  {
    if ( !g_doStackCaptures )
      return v7;
    goto LABEL_16;
  }
  if ( !v10 )
  {
    CMetadataRDFReaderWriter::RemoveItemByPosition(this, v11);
    return v7;
  }
  v7 = -2003292352;
  v8 = g_doStackCaptures == 0;
LABEL_15:
  if ( !v8 )
LABEL_16:
    DoStackCapture(v7);
  return v7;
}

```

## disassembly

```asm
0x18001e950  mov     r11, rsp
0x18001e953  mov     [r11+8], rbx
0x18001e957  mov     [r11+10h], rsi
0x18001e95b  push    rdi
0x18001e95c  sub     rsp, 40h
0x18001e960  mov     eax, 48h ; 'H'
0x18001e965  mov     [rsp+48h+arg_18], 0
0x18001e96d  mov     rbx, r8
0x18001e970  mov     rsi, rdx
0x18001e973  mov     rdi, rcx
0x18001e976  mov     [rsp+48h+arg_10], 0
0x18001e97e  cmp     ax, [r8]
0x18001e982  jnz     short loc_18001E997
0x18001e984  lea     rax, [r11+20h]
0x18001e988  lea     r9, [r11+18h]; int *
0x18001e98c  mov     [r11-28h], rax
0x18001e990  call    ?FindItemPositionByGuidAndIndex@CMetadataRDFReaderWriter@@IEAAJPEBUtagPROPVARIANT@@0PEAHPEAI@Z; CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x18001e995  jmp     short loc_18001E9E3
0x18001e997  mov     eax, 1Fh
0x18001e99c  cmp     ax, [r8]
0x18001e9a0  jnz     short loc_18001EA1C
0x18001e9a2  mov     rax, [rcx]
0x18001e9a5  mov     rax, [rax+110h]
0x18001e9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b1  test    eax, eax
0x18001e9b3  jnz     short loc_18001EA15
0x18001e9b5  lea     rax, [rsp+48h+arg_18]
0x18001e9ba  mov     r9, rsi; struct tagPROPVARIANT *
0x18001e9bd  mov     [rsp+48h+var_18], rax; unsigned int *
0x18001e9c2  lea     rdx, ?CompareItemSchemaAndValue@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z; int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)
0x18001e9c9  lea     rax, [rsp+48h+arg_10]
0x18001e9ce  xor     r8d, r8d; unsigned int
0x18001e9d1  mov     [rsp+48h+var_20], rax; int *
0x18001e9d6  mov     rcx, rdi; this
0x18001e9d9  mov     [rsp+48h+var_28], rbx; struct tagPROPVARIANT *
0x18001e9de  call    ?FindItemPosition@CMetadataRDFReaderWriter@@IEAAJP6AJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@ZI112PEAI@Z; CMetadataRDFReaderWriter::FindItemPosition(long (*)(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *),uint,tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x18001e9e3  mov     ebx, eax
0x18001e9e5  test    eax, eax
0x18001e9e7  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18001e9ed  jns     short loc_18001E9F7
0x18001e9ef  test    eax, eax
0x18001e9f1  jnz     short loc_18001EA2A
0x18001e9f3  test    ebx, ebx
0x18001e9f5  js      short loc_18001EA31
0x18001e9f7  cmp     [rsp+48h+arg_10], 0
0x18001e9fc  jz      short loc_18001EA07
0x18001e9fe  mov     ebx, 88982F40h
0x18001ea03  test    eax, eax
0x18001ea05  jmp     short loc_18001EA28
0x18001ea07  mov     edx, [rsp+48h+arg_18]; unsigned int
0x18001ea0b  mov     rcx, rdi; this
0x18001ea0e  call    ?RemoveItemByPosition@CMetadataRDFReaderWriter@@IEAAXI@Z; CMetadataRDFReaderWriter::RemoveItemByPosition(uint)
0x18001ea13  jmp     short loc_18001EA31
0x18001ea15  mov     ebx, 88982F40h
0x18001ea1a  jmp     short loc_18001EA21
0x18001ea1c  mov     ebx, 80070057h
0x18001ea21  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001ea28  jz      short loc_18001EA31
0x18001ea2a  mov     ecx, ebx; int
0x18001ea2c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001ea31  mov     rsi, [rsp+48h+arg_8]
0x18001ea36  mov     eax, ebx
0x18001ea38  mov     rbx, [rsp+48h+arg_0]
0x18001ea3d  add     rsp, 40h
0x18001ea41  pop     rdi
0x18001ea42  retn
```
