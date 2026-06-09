# CMetadataXMPReaderWriter::IsPaddingTag(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800014d0`
- end: `0x180001539`
- name: `?IsPaddingTag@CMetadataXMPReaderWriter@@IEAAHPEBUtagPROPVARIANT@@0@Z`
- size: `105`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001440`
- `0x18001e7c0`
- `0x180021430`

## callees

- `0x1800014d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001507`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001524`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001507`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001524`

## pseudocode

```c
_BOOL8 __fastcall CMetadataXMPReaderWriter::IsPaddingTag(
        CMetadataXMPReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  LARGE_INTEGER hVal; // rcx

  if ( a2
    && a2->vt == 31
    && a3
    && a3->vt == 31
    && (hVal = a2->hVal, hVal.QuadPart)
    && a3->hVal.QuadPart
    && !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(
                        (LARGE_INTEGER)hVal.QuadPart,
                        L"PaddingSchema") )
  {
    return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(
                           (LARGE_INTEGER)a3->hVal.QuadPart,
                           L"padding") == 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800014d0  push    rbx
0x1800014d2  sub     rsp, 20h
0x1800014d6  mov     rbx, r8
0x1800014d9  test    rdx, rdx
0x1800014dc  jz      short loc_180001511
0x1800014de  cmp     word ptr [rdx], 1Fh
0x1800014e2  jnz     short loc_180001511
0x1800014e4  test    rbx, rbx
0x1800014e7  jz      short loc_180001511
0x1800014e9  cmp     word ptr [r8], 1Fh
0x1800014ee  jnz     short loc_180001511
0x1800014f0  mov     rcx, [rdx+8]
0x1800014f4  test    rcx, rcx
0x1800014f7  jz      short loc_180001511
0x1800014f9  cmp     qword ptr [r8+8], 0
0x1800014fe  jz      short loc_180001511
0x180001500  lea     rdx, aPaddingschema; "PaddingSchema"
0x180001507  call    cs:__imp__o__wcsicmp
0x18000150d  test    eax, eax
0x18000150f  jz      short loc_180001519
0x180001511  xor     eax, eax
0x180001513  add     rsp, 20h
0x180001517  pop     rbx
0x180001518  retn
0x180001519  mov     rcx, [rbx+8]
0x18000151d  lea     rdx, aPadding; "padding"
0x180001524  call    cs:__imp__o__wcsicmp
0x18000152a  xor     ecx, ecx
0x18000152c  test    eax, eax
0x18000152e  setz    cl
0x180001531  mov     eax, ecx
0x180001533  add     rsp, 20h
0x180001537  pop     rbx
0x180001538  retn
```
