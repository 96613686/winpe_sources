# CMetadataRDFReaderWriter::CompareItemEmbeddedGUID(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *)

- ea: `0x1800235a0`
- end: `0x180023603`
- name: `?CompareItemEmbeddedGUID@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z`
- size: `99`
- prototype: `__int64 __fastcall(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800171c4`
- `0x1800235a0`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CompareItemEmbeddedGUID(
        struct RDFItem *a1,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        int *a4)
{
  BSTR *v4; // rcx
  unsigned int v5; // ebx
  BSTR *pbstrVal; // rdx
  char *v7; // rax

  *a4 = 0;
  if ( a3 && a3->vt == 72 )
  {
    v4 = (BSTR *)*((_QWORD *)a1 + 5);
    v5 = 0;
    if ( v4 )
    {
      pbstrVal = a3->pbstrVal;
      v7 = (char *)((char *)*pbstrVal - (char *)*v4);
      if ( *pbstrVal == *v4 )
        v7 = (char *)((char *)pbstrVal[1] - (char *)v4[1]);
      if ( !v7 )
        *a4 = 1;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  return v5;
}

```

## disassembly

```asm
0x1800235a0  push    rbx
0x1800235a2  sub     rsp, 20h
0x1800235a6  mov     dword ptr [r9], 0
0x1800235ad  test    r8, r8
0x1800235b0  jz      short loc_1800235E6
0x1800235b2  cmp     word ptr [r8], 48h ; 'H'
0x1800235b7  jnz     short loc_1800235E6
0x1800235b9  mov     rcx, [rcx+28h]
0x1800235bd  xor     ebx, ebx
0x1800235bf  test    rcx, rcx
0x1800235c2  jz      short loc_1800235FB
0x1800235c4  mov     rdx, [r8+8]
0x1800235c8  mov     rax, [rdx]
0x1800235cb  sub     rax, [rcx]
0x1800235ce  jnz     short loc_1800235D8
0x1800235d0  mov     rax, [rdx+8]
0x1800235d4  sub     rax, [rcx+8]
0x1800235d8  test    rax, rax
0x1800235db  jnz     short loc_1800235FB
0x1800235dd  mov     dword ptr [r9], 1
0x1800235e4  jmp     short loc_1800235FB
0x1800235e6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800235ed  mov     ebx, 80070057h
0x1800235f2  jz      short loc_1800235FB
0x1800235f4  mov     ecx, ebx; int
0x1800235f6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800235fb  mov     eax, ebx
0x1800235fd  add     rsp, 20h
0x180023601  pop     rbx
0x180023602  retn
```
