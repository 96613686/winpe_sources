# CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)

- ea: `0x180023648`
- end: `0x1800238d8`
- name: `?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z`
- size: `656`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *__hidden this, struct CMetadataIPTCReaderWriter::DataSet *)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800224b0`
- `0x180022660`
- `0x180023324`
- `0x1801a8bc0`

## callees

- `0x18002343c`
- `0x180023648`
- `0x1800238e0`
- `0x1800257d0`
- `0x1800aec68`
- `0x1800bb784`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800237b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800237b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023792`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002379c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023792`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002379c`

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
0x180023648  push    rbp
0x18002364a  push    rbx
0x18002364b  push    rsi
0x18002364c  push    rdi
0x18002364d  push    r14
0x18002364f  push    r15
0x180023651  mov     rbp, rsp
0x180023654  sub     rsp, 68h
0x180023658  xorps   xmm0, xmm0
0x18002365b  xor     ebx, ebx
0x18002365d  xor     eax, eax
0x18002365f  mov     rdi, rdx
0x180023662  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180023668  mov     r15, rcx
0x18002366b  movups  xmmword ptr [rbp+var_26], xmm0
0x18002366f  lea     esi, [rbx+1Eh]
0x180023672  mov     word ptr [rbp+pvar], ax
0x180023676  movups  xmmword ptr [rbp+pvar+2], xmm0
0x18002367a  movups  xmmword ptr [rbp+var_26+0Eh], xmm0
0x18002367e  test    rdi, rdi
0x180023681  jz      loc_18002378E
0x180023687  xorps   xmm0, xmm0
0x18002368a  xor     eax, eax
0x18002368c  movups  xmmword ptr [rbp+pvar], xmm0
0x180023690  mov     dword ptr [rbp+arg_8+4], eax
0x180023693  movups  xmmword ptr [rbp-28h], xmm0
0x180023697  movups  xmmword ptr [rbp+var_26+0Eh], xmm0
0x18002369b  cmp     [rdi+4], eax
0x18002369e  jnz     loc_180023815
0x1800236a4  mov     rcx, [r15+78h]
0x1800236a8  test    rcx, rcx
0x1800236ab  jz      loc_18002386E
0x1800236b1  movzx   eax, byte ptr [rdi+0Ch]
0x1800236b5  add     rcx, 10h; this
0x1800236b9  add     eax, [rdi+8]
0x1800236bc  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800236bf  mov     dword ptr [rbp+arg_8], eax
0x1800236c2  xor     r8d, r8d; unsigned int
0x1800236c5  mov     rdx, qword ptr [rbp+arg_8]; union _LARGE_INTEGER
0x1800236c9  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800236ce  mov     ebx, eax
0x1800236d0  test    eax, eax
0x1800236d2  js      loc_180023848
0x1800236d8  mov     dl, [rdi+1]; unsigned __int8
0x1800236db  mov     cl, [rdi]; unsigned __int8
0x1800236dd  call    ?FindDataSetDescriptor@@YAPEBUDataSetDesc@CMetadataIPTCReaderWriter@@EE@Z; FindDataSetDescriptor(uchar,uchar)
0x1800236e2  mov     r8d, [rdi+10h]; unsigned int
0x1800236e6  mov     r14, rax
0x1800236e9  mov     rax, [r15+78h]
0x1800236ed  mov     r9, r14; struct CMetadataIPTCReaderWriter::DataSetDesc *
0x1800236f0  lea     rcx, [rax+10h]; this
0x1800236f4  neg     rax
0x1800236f7  lea     rax, [rbp+pvar]
0x1800236fb  sbb     rdx, rdx
0x1800236fe  mov     [rsp+68h+var_48], rax; struct tagPROPVARIANT *
0x180023703  and     rdx, rcx; struct IStream *
0x180023706  call    ?CreateVariantFromStreamAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEAUIStream@@IPEBUDataSetDesc@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(IStream *,uint,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)
0x18002370b  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180023711  mov     ebx, eax
0x180023713  test    eax, eax
0x180023715  js      loc_18002385D
0x18002371b  cmp     si, word ptr [rbp+pvar]
0x18002371f  jz      loc_18002381E
0x180023725  test    r14, r14
0x180023728  jz      loc_1800238AA
0x18002372e  mov     rax, [r14+8]
0x180023732  test    rax, rax
0x180023735  jz      loc_18002387F
0x18002373b  mov     r8d, 7FFFFFFFh
0x180023741  cmp     byte ptr [rax], 0
0x180023744  jz      short loc_18002374F
0x180023746  inc     rax
0x180023749  sub     r8, 1
0x18002374d  jnz     short loc_180023741
0x18002374f  mov     rax, r8
0x180023752  mov     ecx, 7FFFFFFFh
0x180023757  neg     rax
0x18002375a  mov     rax, r8
0x18002375d  sbb     ebx, ebx
0x18002375f  sub     rcx, r8
0x180023762  not     ebx
0x180023764  and     ebx, 80070057h
0x18002376a  neg     rax
0x18002376d  sbb     rsi, rsi
0x180023770  and     rsi, rcx
0x180023773  test    r8, r8
0x180023776  jz      loc_180023884
0x18002377c  test    ebx, ebx
0x18002377e  js      short loc_18002378E
0x180023780  lea     rcx, [rsi+1]; cb
0x180023784  cmp     rcx, rsi
0x180023787  jnb     short loc_1800237B1
0x180023789  mov     ebx, 80070216h
0x18002378e  lea     rcx, [rbp+pvar]; pvar
0x180023792  call    cs:__imp_PropVariantClear
0x180023798  lea     rcx, [rbp+var_26+6]; pvar
0x18002379c  call    cs:__imp_PropVariantClear
0x1800237a2  mov     eax, ebx
0x1800237a4  add     rsp, 68h
0x1800237a8  pop     r15
0x1800237aa  pop     r14
0x1800237ac  pop     rdi
0x1800237ad  pop     rsi
0x1800237ae  pop     rbx
0x1800237af  pop     rbp
0x1800237b0  retn
0x1800237b1  call    cs:__imp_CoTaskMemAlloc
0x1800237b7  mov     [rbp+var_26+0Eh], rax
0x1800237bb  test    rax, rax
0x1800237be  jz      loc_1800238CA
0x1800237c4  mov     byte ptr [rax+rsi], 0
0x1800237c8  mov     r8, rsi; Size
0x1800237cb  mov     rdx, [r14+8]; Src
0x1800237cf  mov     rcx, [rbp+var_26+0Eh]; void *
0x1800237d3  call    memcpy_0
0x1800237d8  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800237de  mov     esi, 1Eh
0x1800237e3  mov     word ptr [rbp+var_26+6], si
0x1800237e7  mov     dword ptr [rdi+4], 1
0x1800237ee  movups  xmm0, xmmword ptr [rbp+pvar]
0x1800237f2  movups  xmmword ptr [rdi+8], xmm0
0x1800237f6  movups  xmm1, xmmword ptr [rbp-28h]
0x1800237fa  movups  xmmword ptr [rdi+18h], xmm1
0x1800237fe  movups  xmm0, xmmword ptr [rbp+var_26+0Eh]
0x180023802  xorps   xmm1, xmm1
0x180023805  movups  xmmword ptr [rdi+28h], xmm0
0x180023809  movups  xmmword ptr [rbp+pvar], xmm1
0x18002380d  movups  xmmword ptr [rbp-28h], xmm1
0x180023811  movups  xmmword ptr [rbp+var_26+0Eh], xmm1
0x180023815  mov     rdi, [rdi+38h]
0x180023819  jmp     loc_18002367E
0x18002381e  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180023822  call    ?SniffAndConvertToWideString@CMetadataIPTCReaderWriter@@AEAAJPEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::SniffAndConvertToWideString(tagPROPVARIANT *)
0x180023827  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002382d  mov     ebx, eax
0x18002382f  test    eax, eax
0x180023831  jns     loc_180023725
0x180023837  test    edx, edx
0x180023839  jnz     short loc_180023851
0x18002383b  test    eax, eax
0x18002383d  jns     loc_180023725
0x180023843  jmp     loc_18002378E
0x180023848  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002384f  jz      short loc_180023896
0x180023851  mov     ecx, eax; int
0x180023853  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023858  jmp     loc_18002378E
0x18002385d  test    edx, edx
0x18002385f  jnz     short loc_180023851
0x180023861  test    eax, eax
0x180023863  jns     loc_18002371B
0x180023869  jmp     loc_18002378E
0x18002386e  mov     ebx, 88982F73h
0x180023873  test    edx, edx
0x180023875  jz      loc_18002378E
0x18002387b  mov     ecx, ebx
0x18002387d  jmp     short loc_180023853
0x18002387f  mov     ebx, 80070057h
0x180023884  mov     esi, ebx
0x180023886  test    edx, edx
0x180023888  jz      short loc_1800238A3
0x18002388a  mov     ecx, ebx; int
0x18002388c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023891  jmp     loc_18002378E
0x180023896  test    eax, eax
0x180023898  jns     loc_1800236D8
0x18002389e  jmp     loc_18002378E
0x1800238a3  xor     esi, esi
0x1800238a5  jmp     loc_18002377C
0x1800238aa  mov     eax, 12h
0x1800238af  mov     word ptr [rbp+var_26+6], ax
0x1800238b3  movzx   ecx, byte ptr [rdi]
0x1800238b6  movzx   eax, byte ptr [rdi+1]
0x1800238ba  shl     cx, 8
0x1800238be  or      cx, ax
0x1800238c1  mov     word ptr [rbp+var_26+0Eh], cx
0x1800238c5  jmp     loc_1800237E7
0x1800238ca  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800238d1  mov     ebx, 8007000Eh
0x1800238d6  jmp     short loc_180023875
```
