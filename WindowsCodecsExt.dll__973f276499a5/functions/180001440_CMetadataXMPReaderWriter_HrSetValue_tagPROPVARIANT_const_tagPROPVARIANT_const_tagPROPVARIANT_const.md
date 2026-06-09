# CMetadataXMPReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180001440`
- end: `0x1800014c6`
- name: `?HrSetValue@CMetadataXMPReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `134`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001440`
- `0x1800014d0`
- `0x180001630`
- `0x1800171c4`
- `0x180021578`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrSetValue(
        CMetadataXMPReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // ecx

  if ( (!a2 || a2->vt != 31) && a3->vt != 72 )
  {
    v9 = -2147024809;
    if ( !g_doStackCaptures )
      return v9;
    v11 = -2147024809;
    goto LABEL_9;
  }
  if ( (unsigned int)CMetadataXMPReaderWriter::IsPaddingTag(this, a2, a3) )
    v8 = CMetadataXMPReaderWriter::SetPaddingTag(this, a4);
  else
    v8 = CMetadataRDFReaderWriter::HrSetValue(this, a2, a3, a4);
  v9 = v8;
  if ( v8 < 0 && g_doStackCaptures )
  {
    v11 = v8;
LABEL_9:
    DoStackCapture(v11);
  }
  return v9;
}

```

## disassembly

```asm
0x180001440  push    rbx
0x180001442  push    rbp
0x180001443  push    rsi
0x180001444  push    rdi
0x180001445  sub     rsp, 28h
0x180001449  mov     rsi, r9
0x18000144c  mov     rdi, r8
0x18000144f  mov     rbx, rdx
0x180001452  mov     rbp, rcx
0x180001455  test    rdx, rdx
0x180001458  jz      short loc_1800014AF
0x18000145a  cmp     word ptr [rdx], 1Fh
0x18000145e  jnz     short loc_1800014AF
0x180001460  call    ?IsPaddingTag@CMetadataXMPReaderWriter@@IEAAHPEBUtagPROPVARIANT@@0@Z; CMetadataXMPReaderWriter::IsPaddingTag(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180001465  mov     rcx, rbp; this
0x180001468  test    eax, eax
0x18000146a  jnz     short loc_1800014BC
0x18000146c  mov     r9, rsi; struct tagPROPVARIANT *
0x18000146f  mov     r8, rdi; struct tagPROPVARIANT *
0x180001472  mov     rdx, rbx; struct tagPROPVARIANT *
0x180001475  call    ?HrSetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18000147a  mov     ebx, eax
0x18000147c  test    eax, eax
0x18000147e  jns     short loc_180001489
0x180001480  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001487  jnz     short loc_180001494
0x180001489  mov     eax, ebx
0x18000148b  add     rsp, 28h
0x18000148f  pop     rdi
0x180001490  pop     rsi
0x180001491  pop     rbp
0x180001492  pop     rbx
0x180001493  retn
0x180001494  mov     ecx, eax; int
0x180001496  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000149b  jmp     short loc_180001489
0x18000149d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800014a4  mov     ebx, 80070057h
0x1800014a9  jz      short loc_180001489
0x1800014ab  mov     ecx, ebx
0x1800014ad  jmp     short loc_180001496
0x1800014af  mov     eax, 48h ; 'H'
0x1800014b4  cmp     ax, [r8]
0x1800014b8  jz      short loc_180001460
0x1800014ba  jmp     short loc_18000149D
0x1800014bc  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800014bf  call    ?SetPaddingTag@CMetadataXMPReaderWriter@@IEAAJPEBUtagPROPVARIANT@@@Z; CMetadataXMPReaderWriter::SetPaddingTag(tagPROPVARIANT const *)
0x1800014c4  jmp     short loc_18000147A
```
