# CMetadataRDFReaderWriter::HrFindInterface(_GUID const &,void * *)

- ea: `0x180011db0`
- end: `0x180011eb3`
- name: `?HrFindInterface@CMetadataRDFReaderWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011db0`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrFindInterface(
        CMetadataRDFReaderWriter *this,
        const struct _GUID *a2,
        void **a3)
{
  char *v3; // r9
  __int64 v4; // rax
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx

  v3 = (char *)this - 24;
  if ( *((_DWORD *)this + 36) )
  {
    v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWICMetadataWriter.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWICMetadataWriter.Data1 )
      v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWICMetadataWriter.Data4;
    if ( !v9 )
      goto LABEL_5;
  }
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWICMetadataReader.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWICMetadataReader.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWICMetadataReader.Data4;
  if ( !v4 )
    goto LABEL_5;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWICStreamProvider.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWICStreamProvider.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWICStreamProvider.Data4;
  if ( !v6 )
  {
    v8 = (unsigned __int64)this - 8;
    goto LABEL_15;
  }
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWICPersistStream.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWICPersistStream.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWICPersistStream.Data4;
  if ( !v7 )
    goto LABEL_14;
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStream.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStream.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStream.Data4;
  if ( !v10 )
    goto LABEL_14;
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersist.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersist.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersist.Data4;
  if ( !v11 )
  {
LABEL_14:
    v8 = (unsigned __int64)this - 16;
LABEL_15:
    *a3 = (void *)(v8 & -(__int64)(v3 != 0));
    return 0;
  }
  result = 2147500034LL;
  v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IXMPCMetadataRDF.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXMPCMetadataRDF.Data1 )
    v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IXMPCMetadataRDF.Data4;
  if ( !v12 )
  {
LABEL_5:
    *a3 = v3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011db0  lea     r9, [rcx-18h]
0x180011db4  cmp     dword ptr [r9+0A8h], 0
0x180011dbc  jnz     short loc_180011E2A
0x180011dbe  mov     rax, [rdx]
0x180011dc1  sub     rax, qword ptr cs:IID_IWICMetadataReader.Data1
0x180011dc8  jnz     short loc_180011DD5
0x180011dca  mov     rax, [rdx+8]
0x180011dce  sub     rax, qword ptr cs:IID_IWICMetadataReader.Data4
0x180011dd5  test    rax, rax
0x180011dd8  jnz     short loc_180011DE0
0x180011dda  mov     [r8], r9
0x180011ddd  xor     eax, eax
0x180011ddf  retn
0x180011de0  mov     rax, [rdx]
0x180011de3  sub     rax, qword ptr cs:IID_IWICStreamProvider.Data1
0x180011dea  jnz     short loc_180011DF7
0x180011dec  mov     rax, [rdx+8]
0x180011df0  sub     rax, qword ptr cs:IID_IWICStreamProvider.Data4
0x180011df7  test    rax, rax
0x180011dfa  jz      short loc_180011E4B
0x180011dfc  mov     rax, [rdx]
0x180011dff  sub     rax, qword ptr cs:IID_IWICPersistStream.Data1
0x180011e06  jnz     short loc_180011E13
0x180011e08  mov     rax, [rdx+8]
0x180011e0c  sub     rax, qword ptr cs:IID_IWICPersistStream.Data4
0x180011e13  test    rax, rax
0x180011e16  jnz     short loc_180011E51
0x180011e18  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180011e1c  neg     r9
0x180011e1f  sbb     rax, rax
0x180011e22  and     rax, rcx
0x180011e25  mov     [r8], rax
0x180011e28  jmp     short loc_180011DDD
0x180011e2a  mov     rax, [rdx]
0x180011e2d  sub     rax, qword ptr cs:IID_IWICMetadataWriter.Data1
0x180011e34  jnz     short loc_180011E41
0x180011e36  mov     rax, [rdx+8]
0x180011e3a  sub     rax, qword ptr cs:IID_IWICMetadataWriter.Data4
0x180011e41  test    rax, rax
0x180011e44  jz      short loc_180011DDA
0x180011e46  jmp     loc_180011DBE
0x180011e4b  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180011e4f  jmp     short loc_180011E1C
0x180011e51  mov     rax, [rdx]
0x180011e54  sub     rax, qword ptr cs:IID_IPersistStream.Data1
0x180011e5b  jnz     short loc_180011E68
0x180011e5d  mov     rax, [rdx+8]
0x180011e61  sub     rax, qword ptr cs:IID_IPersistStream.Data4
0x180011e68  test    rax, rax
0x180011e6b  jz      short loc_180011E18
0x180011e6d  mov     rax, [rdx]
0x180011e70  sub     rax, qword ptr cs:IID_IPersist.Data1
0x180011e77  jnz     short loc_180011E84
0x180011e79  mov     rax, [rdx+8]
0x180011e7d  sub     rax, qword ptr cs:IID_IPersist.Data4
0x180011e84  test    rax, rax
0x180011e87  jz      short loc_180011E18
0x180011e89  mov     rcx, [rdx]
0x180011e8c  mov     eax, 80004002h
0x180011e91  sub     rcx, qword ptr cs:IID_IXMPCMetadataRDF.Data1
0x180011e98  jnz     short loc_180011EA5
0x180011e9a  mov     rcx, [rdx+8]
0x180011e9e  sub     rcx, qword ptr cs:IID_IXMPCMetadataRDF.Data4
0x180011ea5  test    rcx, rcx
0x180011ea8  jnz     locret_180011DDF
0x180011eae  jmp     loc_180011DDA
```
