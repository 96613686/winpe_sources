# CMetadataXMPReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18001e7c0`
- end: `0x18001e81e`
- name: `?HrRemoveValue@CMetadataXMPReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0@Z`
- size: `94`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800014d0`
- `0x1800171c4`
- `0x18001e7c0`
- `0x18001e824`
- `0x18001e950`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrRemoveValue(
        CMetadataXMPReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  int v6; // eax
  unsigned int v7; // ebx

  if ( (unsigned int)CMetadataXMPReaderWriter::IsPaddingTag(this, a2, a3) )
    v6 = CMetadataXMPReaderWriter::RemovePaddingTag(this);
  else
    v6 = CMetadataRDFReaderWriter::HrRemoveValue(this, a2, a3);
  v7 = v6;
  if ( v6 < 0 && g_doStackCaptures )
    DoStackCapture(v6);
  return v7;
}

```

## disassembly

```asm
0x18001e7c0  mov     [rsp+arg_0], rbx
0x18001e7c5  mov     [rsp+arg_8], rsi
0x18001e7ca  push    rdi
0x18001e7cb  sub     rsp, 20h
0x18001e7cf  mov     rdi, r8
0x18001e7d2  mov     rsi, rdx
0x18001e7d5  mov     rbx, rcx
0x18001e7d8  call    ?IsPaddingTag@CMetadataXMPReaderWriter@@IEAAHPEBUtagPROPVARIANT@@0@Z; CMetadataXMPReaderWriter::IsPaddingTag(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18001e7dd  mov     rcx, rbx; this
0x18001e7e0  test    eax, eax
0x18001e7e2  jz      short loc_18001E7EB
0x18001e7e4  call    ?RemovePaddingTag@CMetadataXMPReaderWriter@@IEAAJXZ; CMetadataXMPReaderWriter::RemovePaddingTag(void)
0x18001e7e9  jmp     short loc_18001E7F6
0x18001e7eb  mov     r8, rdi; struct tagPROPVARIANT *
0x18001e7ee  mov     rdx, rsi; struct tagPROPVARIANT *
0x18001e7f1  call    ?HrRemoveValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0@Z; CMetadataRDFReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18001e7f6  mov     ebx, eax
0x18001e7f8  test    eax, eax
0x18001e7fa  jns     short loc_18001E80C
0x18001e7fc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001e803  jz      short loc_18001E80C
0x18001e805  mov     ecx, eax; int
0x18001e807  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001e80c  mov     rsi, [rsp+28h+arg_8]
0x18001e811  mov     eax, ebx
0x18001e813  mov     rbx, [rsp+28h+arg_0]
0x18001e818  add     rsp, 20h
0x18001e81c  pop     rdi
0x18001e81d  retn
```
