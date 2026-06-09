# CMetadataIFDReaderWriter::CopyDataValueToStream(IStream *,int,int,IFD::FieldEntry *,ulong *)

- ea: `0x1800aeeb4`
- end: `0x1800af0c1`
- name: `?CopyDataValueToStream@CMetadataIFDReaderWriter@@IEAAJPEAUIStream@@HHPEAVFieldEntry@IFD@@PEAK@Z`
- size: `525`
- prototype: `int(CMetadataIFDReaderWriter *__hidden this, struct IStream *, int, int, struct IFD::FieldEntry *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800573d0`

## callees

- `0x1800257d0`
- `0x180025d00`
- `0x180036cb4`
- `0x1800545f4`
- `0x180054fec`
- `0x180055340`
- `0x1800aeeb4`
- `0x1800af0c8`
- `0x1800b4bf4`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aef17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aef17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af0a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af0a8`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::CopyDataValueToStream(
        CMetadataIFDReaderWriter *this,
        struct IStream *a2,
        int a3,
        __int64 a4,
        struct IFD::FieldEntry *a5,
        unsigned int *a6)
{
  struct IFD::FieldEntry *v6; // rbp
  int ValueDataSize; // eax
  unsigned int v11; // ebx
  unsigned int v12; // esi
  void *v13; // rdi
  __int64 v14; // rcx
  int FullBufferFromStream; // eax
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // eax
  void *v20; // [rsp+30h] [rbp-58h] BYREF
  union _LARGE_INTEGER v21; // [rsp+38h] [rbp-50h]
  SIZE_T cb; // [rsp+A8h] [rbp+20h] BYREF

  v6 = a5;
  LODWORD(cb) = 0;
  ValueDataSize = IFD::FieldEntry::GetValueDataSize(a5, (unsigned int *)&cb);
  v11 = ValueDataSize;
  if ( ValueDataSize < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(ValueDataSize);
    return v11;
  }
  v12 = cb;
  v20 = CoTaskMemAlloc((unsigned int)cb);
  v13 = v20;
  if ( !v20 )
  {
    v11 = -2147024882;
LABEL_30:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_33;
    v16 = v11;
    goto LABEL_32;
  }
  if ( (unsigned int)IFD::FieldEntry::IsComplexEmbeddedMetadata(v6) )
  {
    v11 = -2147467263;
    goto LABEL_30;
  }
  v14 = *((_QWORD *)this + 15);
  v21.QuadPart = *((unsigned int *)v6 + 2);
  FullBufferFromStream = CStreamBase::Seek((CStreamBase *)(v14 + 16), v21, 0, 0);
  v11 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_8;
  FullBufferFromStream = ReadFullBufferFromStream(
                           (struct IStream *)((*((_QWORD *)this + 15) + 16LL) & -(__int64)(*((_QWORD *)this + 15) != 0)),
                           v20,
                           v12);
  v11 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_8;
  if ( (*((_DWORD *)this + 33) & 1) != a3 )
  {
    if ( (unsigned int)IFD::FieldEntry::IsCommentTag(v6) && *((_WORD *)v6 + 1) == 7 )
    {
      CopyCommentWithEndiannessSwap((unsigned __int8 *)v20, (unsigned __int8 *)v20, v12);
    }
    else
    {
      v18 = CMetadataIFDReaderWriter::SwapByteOrder(v17, *((unsigned __int16 *)v6 + 1), &v20, *((_DWORD *)v6 + 1), 1, 0);
      v11 = v18;
      if ( v18 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v18);
        v13 = v20;
        goto LABEL_33;
      }
      v13 = v20;
    }
  }
  FullBufferFromStream = WriteFullBufferToStream(a2, v13, v12);
  v11 = FullBufferFromStream;
  if ( FullBufferFromStream >= 0 )
  {
    if ( (v12 & 1) == 0 )
      goto LABEL_27;
    LOBYTE(cb) = 0;
    FullBufferFromStream = WriteFullBufferToStream(a2, &cb, 1u);
    v11 = FullBufferFromStream;
    if ( FullBufferFromStream >= 0 )
    {
      if ( v12 + 1 < v12 )
      {
        v11 = -2147024362;
        goto LABEL_30;
      }
      ++v12;
      v11 = 0;
LABEL_27:
      *a6 = v12;
      goto LABEL_33;
    }
LABEL_8:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_33;
    goto LABEL_9;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_9:
    v16 = FullBufferFromStream;
LABEL_32:
    DoStackCapture(v16);
  }
LABEL_33:
  if ( v13 )
    CoTaskMemFree(v13);
  return v11;
}

```

## disassembly

```asm
0x1800aeeb4  mov     rax, rsp
0x1800aeeb7  mov     [rax+20h], r9d
0x1800aeebb  push    rbx
0x1800aeebc  push    rbp
0x1800aeebd  push    rsi
0x1800aeebe  push    rdi
0x1800aeebf  push    r12
0x1800aeec1  push    r13
0x1800aeec3  push    r14
0x1800aeec5  push    r15
0x1800aeec7  sub     rsp, 48h
0x1800aeecb  mov     rbp, [rsp+88h+arg_20]
0x1800aeed3  mov     r12, rdx
0x1800aeed6  mov     r14, rcx
0x1800aeed9  lea     rdx, [rax+20h]; unsigned int *
0x1800aeedd  xor     r13d, r13d
0x1800aeee0  mov     rcx, rbp; this
0x1800aeee3  mov     r15d, r8d
0x1800aeee6  mov     [rax+20h], r13d
0x1800aeeea  call    ?GetValueDataSize@FieldEntry@IFD@@QEAAJPEAK@Z; IFD::FieldEntry::GetValueDataSize(ulong *)
0x1800aeeef  mov     ebx, eax
0x1800aeef1  test    eax, eax
0x1800aeef3  jns     short loc_1800AEF0E
0x1800aeef5  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800aeefc  jz      loc_1800AF0AE
0x1800aef02  mov     ecx, eax; int
0x1800aef04  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aef09  jmp     loc_1800AF0AE
0x1800aef0e  mov     esi, dword ptr [rsp+88h+cb]
0x1800aef15  mov     ecx, esi; cb
0x1800aef17  call    cs:__imp_CoTaskMemAlloc
0x1800aef1d  mov     [rsp+88h+var_58], rax
0x1800aef22  mov     rdi, rax
0x1800aef25  test    rax, rax
0x1800aef28  jnz     short loc_1800AEF34
0x1800aef2a  mov     ebx, 8007000Eh
0x1800aef2f  jmp     loc_1800AF090
0x1800aef34  mov     rcx, rbp; this
0x1800aef37  call    ?IsComplexEmbeddedMetadata@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsComplexEmbeddedMetadata(void)
0x1800aef3c  test    eax, eax
0x1800aef3e  jnz     loc_1800AF08B
0x1800aef44  mov     eax, [rbp+8]
0x1800aef47  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800aef4a  mov     rcx, [r14+78h]
0x1800aef4e  xor     r8d, r8d; unsigned int
0x1800aef51  mov     dword ptr [rsp+88h+var_50], eax
0x1800aef55  add     rcx, 10h; this
0x1800aef59  mov     dword ptr [rsp+88h+var_50+4], r13d
0x1800aef5e  mov     rdx, qword ptr [rsp+88h+var_50]; union _LARGE_INTEGER
0x1800aef63  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800aef68  mov     ebx, eax
0x1800aef6a  test    eax, eax
0x1800aef6c  jns     short loc_1800AEF82
0x1800aef6e  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800aef75  jz      loc_1800AF0A0
0x1800aef7b  mov     ecx, eax
0x1800aef7d  jmp     loc_1800AF09B
0x1800aef82  mov     rax, [r14+78h]
0x1800aef86  mov     r8d, esi; unsigned int
0x1800aef89  lea     rdx, [rax+10h]
0x1800aef8d  neg     rax
0x1800aef90  sbb     rcx, rcx
0x1800aef93  and     rcx, rdx; struct IStream *
0x1800aef96  mov     rdx, rdi; void *
0x1800aef99  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800aef9e  mov     ebx, eax
0x1800aefa0  test    eax, eax
0x1800aefa2  js      short loc_1800AEF6E
0x1800aefa4  mov     eax, [r14+84h]
0x1800aefab  mov     r14d, 1
0x1800aefb1  and     eax, r14d
0x1800aefb4  cmp     eax, r15d
0x1800aefb7  jz      short loc_1800AF01D
0x1800aefb9  mov     rcx, rbp; this
0x1800aefbc  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x1800aefc1  test    eax, eax
0x1800aefc3  jz      short loc_1800AEFDC
0x1800aefc5  cmp     word ptr [rbp+2], 7
0x1800aefca  jnz     short loc_1800AEFDC
0x1800aefcc  mov     r8d, esi; unsigned int
0x1800aefcf  mov     rdx, rdi; unsigned __int8 *
0x1800aefd2  mov     rcx, rdi; unsigned __int8 *
0x1800aefd5  call    ?CopyCommentWithEndiannessSwap@@YAXPEAE0I@Z; CopyCommentWithEndiannessSwap(uchar *,uchar *,uint)
0x1800aefda  jmp     short loc_1800AF01D
0x1800aefdc  movzx   edx, word ptr [rbp+2]
0x1800aefe0  lea     r8, [rsp+88h+var_58]
0x1800aefe5  mov     r9d, [rbp+4]
0x1800aefe9  mov     [rsp+88h+var_60], r13
0x1800aefee  mov     [rsp+88h+var_68], r14d
0x1800aeff3  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x1800aeff8  mov     ebx, eax
0x1800aeffa  test    eax, eax
0x1800aeffc  jns     short loc_1800AF018
0x1800aeffe  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800af005  jz      short loc_1800AF00E
0x1800af007  mov     ecx, eax; int
0x1800af009  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af00e  mov     rdi, [rsp+88h+var_58]
0x1800af013  jmp     loc_1800AF0A0
0x1800af018  mov     rdi, [rsp+88h+var_58]
0x1800af01d  mov     r8d, esi; unsigned int
0x1800af020  mov     rdx, rdi; void *
0x1800af023  mov     rcx, r12; struct IStream *
0x1800af026  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800af02b  mov     ebx, eax
0x1800af02d  test    eax, eax
0x1800af02f  jns     short loc_1800AF042
0x1800af031  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800af038  jnz     loc_1800AEF7B
0x1800af03e  test    eax, eax
0x1800af040  js      short loc_1800AF0A0
0x1800af042  test    r14b, sil
0x1800af045  jz      short loc_1800AF078
0x1800af047  mov     r8d, r14d; unsigned int
0x1800af04a  mov     byte ptr [rsp+88h+cb], r13b
0x1800af052  lea     rdx, [rsp+88h+cb]; void *
0x1800af05a  mov     rcx, r12; struct IStream *
0x1800af05d  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800af062  mov     ebx, eax
0x1800af064  test    eax, eax
0x1800af066  js      loc_1800AEF6E
0x1800af06c  lea     eax, [rsi+1]
0x1800af06f  cmp     eax, esi
0x1800af071  jb      short loc_1800AF084
0x1800af073  mov     esi, eax
0x1800af075  mov     ebx, r13d
0x1800af078  mov     rax, [rsp+88h+arg_28]
0x1800af080  mov     [rax], esi
0x1800af082  jmp     short loc_1800AF0A0
0x1800af084  mov     ebx, 80070216h
0x1800af089  jmp     short loc_1800AF090
0x1800af08b  mov     ebx, 80004001h
0x1800af090  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800af097  jz      short loc_1800AF0A0
0x1800af099  mov     ecx, ebx; int
0x1800af09b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af0a0  test    rdi, rdi
0x1800af0a3  jz      short loc_1800AF0AE
0x1800af0a5  mov     rcx, rdi; pv
0x1800af0a8  call    cs:__imp_CoTaskMemFree
0x1800af0ae  mov     eax, ebx
0x1800af0b0  add     rsp, 48h
0x1800af0b4  pop     r15
0x1800af0b6  pop     r14
0x1800af0b8  pop     r13
0x1800af0ba  pop     r12
0x1800af0bc  pop     rdi
0x1800af0bd  pop     rsi
0x1800af0be  pop     rbp
0x1800af0bf  pop     rbx
0x1800af0c0  retn
```
