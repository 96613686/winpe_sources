# CMetadataXMPAltReaderWriter::HrSetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800213c0`
- end: `0x18002141b`
- name: `?HrSetValueByIndex@CMetadataXMPAltReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `91`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800171c4`
- `0x1800213c0`
- `0x1800214e0`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::HrSetValueByIndex(
        CMetadataXMPAltReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5)
{
  bool v5; // zf
  int v6; // eax
  unsigned int v7; // ebx
  struct tagPROPVARIANT v9; // [rsp+30h] [rbp-28h] BYREF

  v5 = a4->vt == 31;
  memset(&v9, 0, sizeof(v9));
  if ( v5 )
    *((_DWORD *)this + 62) = 1;
  v6 = CMetadataRDFReaderWriter::HrSetValueByIndex(this, a2, &v9, a4, a5);
  v7 = v6;
  if ( v6 < 0 && g_doStackCaptures )
    DoStackCapture(v6);
  return v7;
}

```

## disassembly

```asm
0x1800213c0  push    rbx
0x1800213c2  sub     rsp, 50h
0x1800213c6  xor     eax, eax
0x1800213c8  xorps   xmm0, xmm0
0x1800213cb  cmp     word ptr [r9], 1Fh
0x1800213d0  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800213d5  mov     qword ptr [rsp+58h+var_28+10h], rax
0x1800213da  jnz     short loc_1800213E6
0x1800213dc  mov     dword ptr [rcx+0F8h], 1
0x1800213e6  mov     rax, [rsp+58h+arg_20]
0x1800213ee  lea     r8, [rsp+58h+var_28]; struct tagPROPVARIANT *
0x1800213f3  mov     [rsp+58h+var_38], rax; struct tagPROPVARIANT *
0x1800213f8  call    ?HrSetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrSetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800213fd  mov     ebx, eax
0x1800213ff  test    eax, eax
0x180021401  jns     short loc_180021413
0x180021403  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002140a  jz      short loc_180021413
0x18002140c  mov     ecx, eax; int
0x18002140e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180021413  mov     eax, ebx
0x180021415  add     rsp, 50h
0x180021419  pop     rbx
0x18002141a  retn
```
