# CMetadataRDFIndexReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180002710`
- end: `0x1800027d8`
- name: `?HrGetValue@CMetadataRDFIndexReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CMetadataRDFIndexReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001b50`
- `0x180002710`
- `0x1800027e0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFIndexReaderWriter::HrGetValue(
        CMetadataRDFIndexReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        PROPVARIANT *a4)
{
  CMetadataRDFIndexReaderWriter *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // ecx
  unsigned __int16 v14; // [rsp+60h] [rbp+18h] BYREF

  v7 = this;
  v14 = 0;
  if ( !a3->vt )
  {
    v8 = *(_QWORD *)this;
    v9 = 0;
LABEL_4:
    v10 = (*(__int64 (__fastcall **)(CMetadataRDFIndexReaderWriter *, __int64, _QWORD, _QWORD, PROPVARIANT *))(v8 + 168))(
            this,
            v9,
            0,
            0,
            a4);
    v11 = v10;
    if ( v10 >= 0 || !g_doStackCaptures )
      return v11;
    v13 = v10;
    goto LABEL_9;
  }
  if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v14) >= 0 )
  {
    v8 = *(_QWORD *)v7;
    v9 = v14;
    this = v7;
    goto LABEL_4;
  }
  if ( a3->vt != 72 )
  {
    v11 = -2147024809;
    if ( !g_doStackCaptures )
      return v11;
    v13 = -2147024809;
LABEL_9:
    DoStackCapture(v13);
    return v11;
  }
  return CMetadataRDFReaderWriter::HrGetValue(v7, a2, a3, a4);
}

```

## disassembly

```asm
0x180002710  mov     rax, rsp
0x180002713  mov     [rax+8], rbx
0x180002717  mov     [rax+10h], rbp
0x18000271b  push    rsi
0x18000271c  push    rdi
0x18000271d  push    r14
0x18000271f  sub     rsp, 30h
0x180002723  xor     r14d, r14d
0x180002726  mov     rsi, r9
0x180002729  mov     rbx, r8
0x18000272c  mov     rbp, rdx
0x18000272f  mov     rdi, rcx
0x180002732  mov     [rax+18h], r14w
0x180002737  cmp     [r8], r14w
0x18000273b  jz      short loc_180002793
0x18000273d  lea     r8, [rax+18h]; unsigned __int16 *
0x180002741  mov     rdx, rbx; struct tagPROPVARIANT *
0x180002744  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x180002749  test    eax, eax
0x18000274b  js      short loc_1800027BB
0x18000274d  mov     rax, [rdi]
0x180002750  xor     r9d, r9d
0x180002753  movzx   edx, [rsp+48h+arg_10]
0x180002758  xor     r8d, r8d
0x18000275b  mov     rcx, rdi
0x18000275e  mov     rax, [rax+0A8h]
0x180002765  mov     [rsp+48h+var_28], rsi
0x18000276a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276f  mov     ebx, eax
0x180002771  test    eax, eax
0x180002773  jns     short loc_18000277E
0x180002775  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18000277c  jnz     short loc_1800027A0
0x18000277e  mov     eax, ebx
0x180002780  mov     rbx, [rsp+48h+arg_0]
0x180002785  mov     rbp, [rsp+48h+arg_8]
0x18000278a  add     rsp, 30h
0x18000278e  pop     r14
0x180002790  pop     rdi
0x180002791  pop     rsi
0x180002792  retn
0x180002793  mov     rax, [rcx]
0x180002796  xor     r9d, r9d
0x180002799  xor     r8d, r8d
0x18000279c  xor     edx, edx
0x18000279e  jmp     short loc_18000275E
0x1800027a0  mov     ecx, eax; int
0x1800027a2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800027a7  jmp     short loc_18000277E
0x1800027a9  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800027b0  mov     ebx, 80070057h
0x1800027b5  jz      short loc_18000277E
0x1800027b7  mov     ecx, ebx
0x1800027b9  jmp     short loc_1800027A2
0x1800027bb  mov     eax, 48h ; 'H'
0x1800027c0  cmp     ax, [rbx]
0x1800027c3  jnz     short loc_1800027A9
0x1800027c5  mov     r9, rsi; struct tagPROPVARIANT *
0x1800027c8  mov     r8, rbx; struct tagPROPVARIANT *
0x1800027cb  mov     rdx, rbp; struct tagPROPVARIANT *
0x1800027ce  mov     rcx, rdi; this
0x1800027d1  call    ?HrGetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z; CMetadataRDFReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800027d6  jmp     short loc_180002780
```
