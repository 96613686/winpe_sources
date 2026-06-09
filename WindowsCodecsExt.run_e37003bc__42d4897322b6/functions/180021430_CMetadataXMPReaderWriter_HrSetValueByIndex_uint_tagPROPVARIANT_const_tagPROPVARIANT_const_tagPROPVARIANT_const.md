# CMetadataXMPReaderWriter::HrSetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180021430`
- end: `0x1800214d4`
- name: `?HrSetValueByIndex@CMetadataXMPReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `164`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800014d0`
- `0x1800171c4`
- `0x180021430`
- `0x1800214e0`
- `0x180021578`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrSetValueByIndex(
        CMetadataXMPReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // ecx

  if ( a3 && a3->vt == 31 )
  {
    if ( a2 == *((_DWORD *)this + 43)
      && (unsigned int)CMetadataXMPReaderWriter::IsPaddingTag(this, a3, a4)
      && (v9 = CMetadataXMPReaderWriter::SetPaddingTag(this, a5), v10 = v9, v9 < 0)
      || (v9 = CMetadataRDFReaderWriter::HrSetValueByIndex(this, a2, a3, a4, a5), v10 = v9, v9 < 0) )
    {
      if ( g_doStackCaptures )
      {
        v11 = v9;
LABEL_12:
        DoStackCapture(v11);
      }
    }
  }
  else
  {
    v10 = -2147024809;
    if ( g_doStackCaptures )
    {
      v11 = -2147024809;
      goto LABEL_12;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180021430  push    rbx
0x180021432  push    rbp
0x180021433  push    rsi
0x180021434  push    rdi
0x180021435  push    r14
0x180021437  push    r15
0x180021439  sub     rsp, 38h
0x18002143d  mov     r15, r9
0x180021440  mov     rdi, r8
0x180021443  mov     r14d, edx
0x180021446  mov     rsi, rcx
0x180021449  test    r8, r8
0x18002144c  jz      short loc_1800214B0
0x18002144e  cmp     word ptr [r8], 1Fh
0x180021453  jnz     short loc_1800214B0
0x180021455  mov     rbp, [rsp+68h+arg_20]
0x18002145d  cmp     edx, [rcx+0ACh]
0x180021463  jnz     short loc_180021492
0x180021465  mov     r8, r9; struct tagPROPVARIANT *
0x180021468  mov     rdx, rdi; struct tagPROPVARIANT *
0x18002146b  call    ?IsPaddingTag@CMetadataXMPReaderWriter@@IEAAHPEBUtagPROPVARIANT@@0@Z; CMetadataXMPReaderWriter::IsPaddingTag(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180021470  test    eax, eax
0x180021472  jz      short loc_180021492
0x180021474  mov     rdx, rbp; struct tagPROPVARIANT *
0x180021477  mov     rcx, rsi; this
0x18002147a  call    ?SetPaddingTag@CMetadataXMPReaderWriter@@IEAAJPEBUtagPROPVARIANT@@@Z; CMetadataXMPReaderWriter::SetPaddingTag(tagPROPVARIANT const *)
0x18002147f  mov     ebx, eax
0x180021481  test    eax, eax
0x180021483  jns     short loc_180021492
0x180021485  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002148c  jz      short loc_1800214C5
0x18002148e  mov     ecx, eax
0x180021490  jmp     short loc_1800214C0
0x180021492  mov     r9, r15; struct tagPROPVARIANT *
0x180021495  mov     [rsp+68h+var_48], rbp; struct tagPROPVARIANT *
0x18002149a  mov     r8, rdi; struct tagPROPVARIANT *
0x18002149d  mov     edx, r14d; unsigned int
0x1800214a0  mov     rcx, rsi; this
0x1800214a3  call    ?HrSetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrSetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800214a8  mov     ebx, eax
0x1800214aa  test    eax, eax
0x1800214ac  jns     short loc_1800214C5
0x1800214ae  jmp     short loc_180021485
0x1800214b0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800214b7  mov     ebx, 80070057h
0x1800214bc  jz      short loc_1800214C5
0x1800214be  mov     ecx, ebx; int
0x1800214c0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800214c5  mov     eax, ebx
0x1800214c7  add     rsp, 38h
0x1800214cb  pop     r15
0x1800214cd  pop     r14
0x1800214cf  pop     rdi
0x1800214d0  pop     rsi
0x1800214d1  pop     rbp
0x1800214d2  pop     rbx
0x1800214d3  retn
```
