# CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)

- ea: `0x18004f390`
- end: `0x18004f633`
- name: `?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z`
- size: `675`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *__hidden this, struct CMetadataIPTCReaderWriter::DataSet *)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e420`
- `0x18004e5e0`
- `0x18004f2f4`
- `0x1801ac060`

## callees

- `0x18004f390`
- `0x18004f63c`
- `0x18004f678`
- `0x18004ff44`
- `0x180055880`
- `0x1800bd9d4`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f506`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f4da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f4ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f4da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f4ea`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::EnsureDataSetLoaded(
        CMetadataIPTCReaderWriter *this,
        struct CMetadataIPTCReaderWriter::DataSet *a2)
{
  int v2; // ebx
  int v4; // edx
  __int64 v6; // rcx
  int VariantFromStreamAndDesc; // eax
  const struct CMetadataIPTCReaderWriter::DataSetDesc *DataSetDescriptor; // r14
  CMetadataIPTCReaderWriter *v9; // rcx
  _BYTE *v10; // rax
  __int64 v11; // r8
  size_t v12; // rsi
  _BYTE *v14; // rax
  int v15; // ecx
  bool v16; // zf
  struct tagPROPVARIANT pvar[2]; // [rsp+30h] [rbp-38h] BYREF

  v2 = 0;
  v4 = (int)g_doStackCaptures;
  memset(pvar, 0, sizeof(pvar));
  while ( 1 )
  {
    if ( !a2 )
      goto LABEL_17;
    memset(pvar, 0, sizeof(pvar));
    if ( !*((_DWORD *)a2 + 1) )
      break;
LABEL_21:
    a2 = (struct CMetadataIPTCReaderWriter::DataSet *)*((_QWORD *)a2 + 7);
  }
  v6 = *((_QWORD *)this + 15);
  if ( !v6 )
  {
    v2 = -2003292301;
    v16 = v4 == 0;
    goto LABEL_31;
  }
  VariantFromStreamAndDesc = CStreamBase::Seek(
                               (CStreamBase *)(v6 + 16),
                               (union _LARGE_INTEGER)(*((_DWORD *)a2 + 2) + (unsigned int)*((unsigned __int8 *)a2 + 12)),
                               0,
                               0);
  v2 = VariantFromStreamAndDesc;
  if ( VariantFromStreamAndDesc < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_17;
LABEL_26:
    v15 = VariantFromStreamAndDesc;
LABEL_27:
    DoStackCapture(v15);
    goto LABEL_17;
  }
  DataSetDescriptor = FindDataSetDescriptor(*(_BYTE *)a2, *((_BYTE *)a2 + 1));
  VariantFromStreamAndDesc = CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(
                               (CMetadataIPTCReaderWriter *)(*((_QWORD *)this + 15) + 16LL),
                               (struct IStream *)((*((_QWORD *)this + 15) + 16LL)
                                                & -(__int64)(*((_QWORD *)this + 15) != 0)),
                               *((_DWORD *)a2 + 4),
                               DataSetDescriptor,
                               pvar);
  v4 = (int)g_doStackCaptures;
  v2 = VariantFromStreamAndDesc;
  if ( VariantFromStreamAndDesc < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      goto LABEL_26;
    goto LABEL_17;
  }
  if ( pvar[0].vt == 30 )
  {
    VariantFromStreamAndDesc = CMetadataIPTCReaderWriter::SniffAndConvertToWideString(v9, pvar);
    v4 = (int)g_doStackCaptures;
    v2 = VariantFromStreamAndDesc;
    if ( VariantFromStreamAndDesc < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_17;
      goto LABEL_26;
    }
  }
  if ( !DataSetDescriptor )
  {
    pvar[1].vt = 18;
    pvar[1].iVal = _byteswap_ushort(*(_WORD *)a2);
    goto LABEL_20;
  }
  v10 = (_BYTE *)*((_QWORD *)DataSetDescriptor + 1);
  if ( v10 )
  {
    v11 = 0x7FFFFFFF;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v11;
    }
    while ( v11 );
    v2 = v11 == 0 ? 0x80070057 : 0;
    v12 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
    if ( v11 )
      goto LABEL_14;
  }
  else
  {
    v2 = -2147024809;
  }
  if ( v4 )
  {
    DoStackCapture(v2);
    goto LABEL_17;
  }
  v12 = 0;
LABEL_14:
  if ( v2 < 0 )
    goto LABEL_17;
  if ( v12 + 1 < v12 )
  {
    v2 = -2147024362;
    goto LABEL_17;
  }
  v14 = CoTaskMemAlloc(v12 + 1);
  pvar[1].hVal.QuadPart = (LONGLONG)v14;
  if ( v14 )
  {
    v14[v12] = 0;
    memcpy_0(pvar[1].puuid, *((const void **)DataSetDescriptor + 1), v12);
    v4 = (int)g_doStackCaptures;
    pvar[1].vt = 30;
LABEL_20:
    *((_DWORD *)a2 + 1) = 1;
    *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)&pvar[0].vt;
    *(_OWORD *)((char *)a2 + 24) = *((_OWORD *)&pvar[0].decVal + 1);
    *(_OWORD *)((char *)a2 + 40) = *(_OWORD *)&pvar[1].decVal.Lo32;
    memset(pvar, 0, sizeof(pvar));
    goto LABEL_21;
  }
  v16 = (_DWORD)g_doStackCaptures == 0;
  v2 = -2147024882;
LABEL_31:
  if ( !v16 )
  {
    v15 = v2;
    goto LABEL_27;
  }
LABEL_17:
  PropVariantClear((PROPVARIANT *)pvar);
  PropVariantClear((PROPVARIANT *)&pvar[1]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004f390  push    rbp
0x18004f392  push    rbx
0x18004f393  push    rsi
0x18004f394  push    rdi
0x18004f395  push    r14
0x18004f397  push    r15
0x18004f399  mov     rbp, rsp
0x18004f39c  sub     rsp, 68h
0x18004f3a0  xorps   xmm0, xmm0
0x18004f3a3  xor     ebx, ebx
0x18004f3a5  xor     eax, eax
0x18004f3a7  mov     rdi, rdx
0x18004f3aa  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004f3b0  mov     r15, rcx
0x18004f3b3  movups  xmmword ptr [rbp+var_26], xmm0
0x18004f3b7  lea     esi, [rbx+1Eh]
0x18004f3ba  mov     word ptr [rbp+pvar], ax
0x18004f3be  movups  xmmword ptr [rbp+pvar+2], xmm0
0x18004f3c2  movups  xmmword ptr [rbp+var_26+0Eh], xmm0
0x18004f3c6  test    rdi, rdi
0x18004f3c9  jz      loc_18004F4D6
0x18004f3cf  xorps   xmm0, xmm0
0x18004f3d2  xor     eax, eax
0x18004f3d4  movups  xmmword ptr [rbp+pvar], xmm0
0x18004f3d8  mov     dword ptr [rbp+arg_8+4], eax
0x18004f3db  movups  xmmword ptr [rbp-28h], xmm0
0x18004f3df  movups  xmmword ptr [rbp+var_26+0Eh], xmm0
0x18004f3e3  cmp     [rdi+4], eax
0x18004f3e6  jnz     loc_18004F570
0x18004f3ec  mov     rcx, [r15+78h]
0x18004f3f0  test    rcx, rcx
0x18004f3f3  jz      loc_18004F5C9
0x18004f3f9  movzx   eax, byte ptr [rdi+0Ch]
0x18004f3fd  add     rcx, 10h; this
0x18004f401  add     eax, [rdi+8]
0x18004f404  xor     r9d, r9d; union _ULARGE_INTEGER *
0x18004f407  mov     dword ptr [rbp+arg_8], eax
0x18004f40a  xor     r8d, r8d; unsigned int
0x18004f40d  mov     rdx, qword ptr [rbp+arg_8]; union _LARGE_INTEGER
0x18004f411  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x18004f416  mov     ebx, eax
0x18004f418  test    eax, eax
0x18004f41a  js      loc_18004F5A3
0x18004f420  mov     dl, [rdi+1]; unsigned __int8
0x18004f423  mov     cl, [rdi]; unsigned __int8
0x18004f425  call    ?FindDataSetDescriptor@@YAPEBUDataSetDesc@CMetadataIPTCReaderWriter@@EE@Z; FindDataSetDescriptor(uchar,uchar)
0x18004f42a  mov     r8d, [rdi+10h]; unsigned int
0x18004f42e  mov     r14, rax
0x18004f431  mov     rax, [r15+78h]
0x18004f435  mov     r9, r14; struct CMetadataIPTCReaderWriter::DataSetDesc *
0x18004f438  lea     rcx, [rax+10h]; this
0x18004f43c  neg     rax
0x18004f43f  lea     rax, [rbp+pvar]
0x18004f443  sbb     rdx, rdx
0x18004f446  mov     [rsp+68h+var_48], rax; struct tagPROPVARIANT *
0x18004f44b  and     rdx, rcx; struct IStream *
0x18004f44e  call    ?CreateVariantFromStreamAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEAUIStream@@IPEBUDataSetDesc@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(IStream *,uint,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)
0x18004f453  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004f459  mov     ebx, eax
0x18004f45b  test    eax, eax
0x18004f45d  js      loc_18004F5B8
0x18004f463  cmp     si, word ptr [rbp+pvar]
0x18004f467  jz      loc_18004F579
0x18004f46d  test    r14, r14
0x18004f470  jz      loc_18004F605
0x18004f476  mov     rax, [r14+8]
0x18004f47a  test    rax, rax
0x18004f47d  jz      loc_18004F5DA
0x18004f483  mov     r8d, 7FFFFFFFh
0x18004f489  cmp     byte ptr [rax], 0
0x18004f48c  jz      short loc_18004F497
0x18004f48e  inc     rax
0x18004f491  sub     r8, 1
0x18004f495  jnz     short loc_18004F489
0x18004f497  mov     rax, r8
0x18004f49a  mov     ecx, 7FFFFFFFh
0x18004f49f  neg     rax
0x18004f4a2  mov     rax, r8
0x18004f4a5  sbb     ebx, ebx
0x18004f4a7  sub     rcx, r8
0x18004f4aa  not     ebx
0x18004f4ac  and     ebx, 80070057h
0x18004f4b2  neg     rax
0x18004f4b5  sbb     rsi, rsi
0x18004f4b8  and     rsi, rcx
0x18004f4bb  test    r8, r8
0x18004f4be  jz      loc_18004F5DF
0x18004f4c4  test    ebx, ebx
0x18004f4c6  js      short loc_18004F4D6
0x18004f4c8  lea     rcx, [rsi+1]; cb
0x18004f4cc  cmp     rcx, rsi
0x18004f4cf  jnb     short loc_18004F506
0x18004f4d1  mov     ebx, 80070216h
0x18004f4d6  lea     rcx, [rbp+pvar]; pvar
0x18004f4da  call    cs:__imp_PropVariantClear
0x18004f4e1  nop     dword ptr [rax+rax+00h]
0x18004f4e6  lea     rcx, [rbp+var_26+6]; pvar
0x18004f4ea  call    cs:__imp_PropVariantClear
0x18004f4f1  nop     dword ptr [rax+rax+00h]
0x18004f4f6  mov     eax, ebx
0x18004f4f8  add     rsp, 68h
0x18004f4fc  pop     r15
0x18004f4fe  pop     r14
0x18004f500  pop     rdi
0x18004f501  pop     rsi
0x18004f502  pop     rbx
0x18004f503  pop     rbp
0x18004f504  retn
0x18004f506  call    cs:__imp_CoTaskMemAlloc
0x18004f50d  nop     dword ptr [rax+rax+00h]
0x18004f512  mov     [rbp+var_26+0Eh], rax
0x18004f516  test    rax, rax
0x18004f519  jz      loc_18004F625
0x18004f51f  mov     byte ptr [rax+rsi], 0
0x18004f523  mov     r8, rsi; Size
0x18004f526  mov     rdx, [r14+8]; Src
0x18004f52a  mov     rcx, [rbp+var_26+0Eh]; void *
0x18004f52e  call    memcpy_0
0x18004f533  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004f539  mov     esi, 1Eh
0x18004f53e  mov     word ptr [rbp+var_26+6], si
0x18004f542  mov     dword ptr [rdi+4], 1
0x18004f549  movups  xmm0, xmmword ptr [rbp+pvar]
0x18004f54d  movups  xmmword ptr [rdi+8], xmm0
0x18004f551  movups  xmm1, xmmword ptr [rbp-28h]
0x18004f555  movups  xmmword ptr [rdi+18h], xmm1
0x18004f559  movups  xmm0, xmmword ptr [rbp+var_26+0Eh]
0x18004f55d  xorps   xmm1, xmm1
0x18004f560  movups  xmmword ptr [rdi+28h], xmm0
0x18004f564  movups  xmmword ptr [rbp+pvar], xmm1
0x18004f568  movups  xmmword ptr [rbp-28h], xmm1
0x18004f56c  movups  xmmword ptr [rbp+var_26+0Eh], xmm1
0x18004f570  mov     rdi, [rdi+38h]
0x18004f574  jmp     loc_18004F3C6
0x18004f579  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x18004f57d  call    ?SniffAndConvertToWideString@CMetadataIPTCReaderWriter@@AEAAJPEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::SniffAndConvertToWideString(tagPROPVARIANT *)
0x18004f582  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004f588  mov     ebx, eax
0x18004f58a  test    eax, eax
0x18004f58c  jns     loc_18004F46D
0x18004f592  test    edx, edx
0x18004f594  jnz     short loc_18004F5AC
0x18004f596  test    eax, eax
0x18004f598  jns     loc_18004F46D
0x18004f59e  jmp     loc_18004F4D6
0x18004f5a3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004f5aa  jz      short loc_18004F5F1
0x18004f5ac  mov     ecx, eax; int
0x18004f5ae  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004f5b3  jmp     loc_18004F4D6
0x18004f5b8  test    edx, edx
0x18004f5ba  jnz     short loc_18004F5AC
0x18004f5bc  test    eax, eax
0x18004f5be  jns     loc_18004F463
0x18004f5c4  jmp     loc_18004F4D6
0x18004f5c9  mov     ebx, 88982F73h
0x18004f5ce  test    edx, edx
0x18004f5d0  jz      loc_18004F4D6
0x18004f5d6  mov     ecx, ebx
0x18004f5d8  jmp     short loc_18004F5AE
0x18004f5da  mov     ebx, 80070057h
0x18004f5df  mov     esi, ebx
0x18004f5e1  test    edx, edx
0x18004f5e3  jz      short loc_18004F5FE
0x18004f5e5  mov     ecx, ebx; int
0x18004f5e7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004f5ec  jmp     loc_18004F4D6
0x18004f5f1  test    eax, eax
0x18004f5f3  jns     loc_18004F420
0x18004f5f9  jmp     loc_18004F4D6
0x18004f5fe  xor     esi, esi
0x18004f600  jmp     loc_18004F4C4
0x18004f605  mov     eax, 12h
0x18004f60a  mov     word ptr [rbp+var_26+6], ax
0x18004f60e  movzx   ecx, byte ptr [rdi]
0x18004f611  movzx   eax, byte ptr [rdi+1]
0x18004f615  shl     cx, 8
0x18004f619  or      cx, ax
0x18004f61c  mov     word ptr [rbp+var_26+0Eh], cx
0x18004f620  jmp     loc_18004F542
0x18004f625  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004f62c  mov     ebx, 8007000Eh
0x18004f631  jmp     short loc_18004F5D0
```
