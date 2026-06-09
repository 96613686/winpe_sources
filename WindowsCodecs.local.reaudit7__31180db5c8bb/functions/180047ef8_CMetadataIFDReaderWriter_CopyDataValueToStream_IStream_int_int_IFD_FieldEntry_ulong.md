# CMetadataIFDReaderWriter::CopyDataValueToStream(IStream *,int,int,IFD::FieldEntry *,ulong *)

- ea: `0x180047ef8`
- end: `0x180048112`
- name: `?CopyDataValueToStream@CMetadataIFDReaderWriter@@IEAAJPEAUIStream@@HHPEAVFieldEntry@IFD@@PEAK@Z`
- size: `538`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *this, struct IStream *, int, __int64, struct IFD::FieldEntry *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b9d0`

## callees

- `0x180047ef8`
- `0x180048118`
- `0x18004943c`
- `0x180049eb8`
- `0x18004a220`
- `0x1800542e8`
- `0x180055880`
- `0x180055dbc`
- `0x1800b6d34`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480f2`

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
0x180047ef8  mov     rax, rsp
0x180047efb  mov     [rax+20h], r9d
0x180047eff  push    rbx
0x180047f00  push    rbp
0x180047f01  push    rsi
0x180047f02  push    rdi
0x180047f03  push    r12
0x180047f05  push    r13
0x180047f07  push    r14
0x180047f09  push    r15
0x180047f0b  sub     rsp, 48h
0x180047f0f  mov     rbp, [rsp+88h+arg_20]
0x180047f17  mov     r12, rdx
0x180047f1a  mov     r14, rcx
0x180047f1d  lea     rdx, [rax+20h]; unsigned int *
0x180047f21  xor     r13d, r13d
0x180047f24  mov     rcx, rbp; this
0x180047f27  mov     r15d, r8d
0x180047f2a  mov     [rax+20h], r13d
0x180047f2e  call    ?GetValueDataSize@FieldEntry@IFD@@QEAAJPEAK@Z; IFD::FieldEntry::GetValueDataSize(ulong *)
0x180047f33  mov     ebx, eax
0x180047f35  test    eax, eax
0x180047f37  jns     short loc_180047F52
0x180047f39  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180047f40  jz      loc_1800480FE
0x180047f46  mov     ecx, eax; int
0x180047f48  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180047f4d  jmp     loc_1800480FE
0x180047f52  mov     esi, dword ptr [rsp+88h+cb]
0x180047f59  mov     ecx, esi; cb
0x180047f5b  call    cs:__imp_CoTaskMemAlloc
0x180047f62  nop     dword ptr [rax+rax+00h]
0x180047f67  mov     [rsp+88h+var_58], rax
0x180047f6c  mov     rdi, rax
0x180047f6f  test    rax, rax
0x180047f72  jnz     short loc_180047F7E
0x180047f74  mov     ebx, 8007000Eh
0x180047f79  jmp     loc_1800480DA
0x180047f7e  mov     rcx, rbp; this
0x180047f81  call    ?IsComplexEmbeddedMetadata@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsComplexEmbeddedMetadata(void)
0x180047f86  test    eax, eax
0x180047f88  jnz     loc_1800480D5
0x180047f8e  mov     eax, [rbp+8]
0x180047f91  xor     r9d, r9d; union _ULARGE_INTEGER *
0x180047f94  mov     rcx, [r14+78h]
0x180047f98  xor     r8d, r8d; unsigned int
0x180047f9b  mov     dword ptr [rsp+88h+var_50], eax
0x180047f9f  add     rcx, 10h; this
0x180047fa3  mov     dword ptr [rsp+88h+var_50+4], r13d
0x180047fa8  mov     rdx, qword ptr [rsp+88h+var_50]; union _LARGE_INTEGER
0x180047fad  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x180047fb2  mov     ebx, eax
0x180047fb4  test    eax, eax
0x180047fb6  jns     short loc_180047FCC
0x180047fb8  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180047fbf  jz      loc_1800480EA
0x180047fc5  mov     ecx, eax
0x180047fc7  jmp     loc_1800480E5
0x180047fcc  mov     rax, [r14+78h]
0x180047fd0  mov     r8d, esi; unsigned int
0x180047fd3  lea     rdx, [rax+10h]
0x180047fd7  neg     rax
0x180047fda  sbb     rcx, rcx
0x180047fdd  and     rcx, rdx; struct IStream *
0x180047fe0  mov     rdx, rdi; void *
0x180047fe3  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x180047fe8  mov     ebx, eax
0x180047fea  test    eax, eax
0x180047fec  js      short loc_180047FB8
0x180047fee  mov     eax, [r14+84h]
0x180047ff5  mov     r14d, 1
0x180047ffb  and     eax, r14d
0x180047ffe  cmp     eax, r15d
0x180048001  jz      short loc_180048067
0x180048003  mov     rcx, rbp; this
0x180048006  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x18004800b  test    eax, eax
0x18004800d  jz      short loc_180048026
0x18004800f  cmp     word ptr [rbp+2], 7
0x180048014  jnz     short loc_180048026
0x180048016  mov     r8d, esi; unsigned int
0x180048019  mov     rdx, rdi; unsigned __int8 *
0x18004801c  mov     rcx, rdi; unsigned __int8 *
0x18004801f  call    ?CopyCommentWithEndiannessSwap@@YAXPEAE0I@Z; CopyCommentWithEndiannessSwap(uchar *,uchar *,uint)
0x180048024  jmp     short loc_180048067
0x180048026  movzx   edx, word ptr [rbp+2]
0x18004802a  lea     r8, [rsp+88h+var_58]
0x18004802f  mov     r9d, [rbp+4]
0x180048033  mov     [rsp+88h+var_60], r13
0x180048038  mov     [rsp+88h+var_68], r14d
0x18004803d  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x180048042  mov     ebx, eax
0x180048044  test    eax, eax
0x180048046  jns     short loc_180048062
0x180048048  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004804f  jz      short loc_180048058
0x180048051  mov     ecx, eax; int
0x180048053  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180048058  mov     rdi, [rsp+88h+var_58]
0x18004805d  jmp     loc_1800480EA
0x180048062  mov     rdi, [rsp+88h+var_58]
0x180048067  mov     r8d, esi; unsigned int
0x18004806a  mov     rdx, rdi; void *
0x18004806d  mov     rcx, r12; struct IStream *
0x180048070  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x180048075  mov     ebx, eax
0x180048077  test    eax, eax
0x180048079  jns     short loc_18004808C
0x18004807b  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180048082  jnz     loc_180047FC5
0x180048088  test    eax, eax
0x18004808a  js      short loc_1800480EA
0x18004808c  test    r14b, sil
0x18004808f  jz      short loc_1800480C2
0x180048091  mov     r8d, r14d; unsigned int
0x180048094  mov     byte ptr [rsp+88h+cb], r13b
0x18004809c  lea     rdx, [rsp+88h+cb]; void *
0x1800480a4  mov     rcx, r12; struct IStream *
0x1800480a7  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800480ac  mov     ebx, eax
0x1800480ae  test    eax, eax
0x1800480b0  js      loc_180047FB8
0x1800480b6  lea     eax, [rsi+1]
0x1800480b9  cmp     eax, esi
0x1800480bb  jb      short loc_1800480CE
0x1800480bd  mov     esi, eax
0x1800480bf  mov     ebx, r13d
0x1800480c2  mov     rax, [rsp+88h+arg_28]
0x1800480ca  mov     [rax], esi
0x1800480cc  jmp     short loc_1800480EA
0x1800480ce  mov     ebx, 80070216h
0x1800480d3  jmp     short loc_1800480DA
0x1800480d5  mov     ebx, 80004001h
0x1800480da  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800480e1  jz      short loc_1800480EA
0x1800480e3  mov     ecx, ebx; int
0x1800480e5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800480ea  test    rdi, rdi
0x1800480ed  jz      short loc_1800480FE
0x1800480ef  mov     rcx, rdi; pv
0x1800480f2  call    cs:__imp_CoTaskMemFree
0x1800480f9  nop     dword ptr [rax+rax+00h]
0x1800480fe  mov     eax, ebx
0x180048100  add     rsp, 48h
0x180048104  pop     r15
0x180048106  pop     r14
0x180048108  pop     r13
0x18004810a  pop     r12
0x18004810c  pop     rdi
0x18004810d  pop     rsi
0x18004810e  pop     rbp
0x18004810f  pop     rbx
0x180048110  retn
```
