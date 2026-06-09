# CRTFObject::InitWrite(_reobject &,COleObject *)

- ea: `0x180158afc`
- end: `0x180158ea1`
- name: `?InitWrite@CRTFObject@@AEAAHAEAU_reobject@@PEAVCOleObject@@@Z`
- size: `933`
- prototype: `__int64 __fastcall(CRTFObject *__hidden this, struct _reobject *, struct COleObject *)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180159bb0`
- `0x18017f6b8`
- `0x18019ec34`

## callees

- `0x1800498d0`
- `0x18006733c`
- `0x1800693d4`
- `0x18006e770`
- `0x180127e14`
- `0x18013c916`
- `0x180147808`
- `0x18014bdec`
- `0x18014fc60`
- `0x1801502b0`
- `0x1801581e0`
- `0x1801583a8`
- `0x180158afc`
- `0x1801a5cb4`
- `0x1801a5d94`
- `0x1801a6fb0`
- `0x1801a72d0`
- `0x1801a7328`
- `0x1801a8650`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158e62`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158e62`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158e45`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158e45`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180158e59`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180158e59`

## pseudocode

```c
__int64 __fastcall CRTFObject::InitWrite(CRTFObject *this, struct _reobject *a2, CTxtEdit **a3)
{
  BOOL v6; // ebx
  DWORD v7; // edx
  __int64 v8; // rax
  _WORD *v9; // rsi
  BOOL v10; // r13d
  int IsSimplePersistBlob; // ebx
  CTextMarkContainer *v12; // rcx
  struct CImage *Image; // rax
  bool v14; // zf
  unsigned int EnhMetafilePict; // r15d
  CTextMarkContainer *v16; // rcx
  void *MetafilePictFromBlob; // rbx
  struct ITextBlob::BLOB_PROPERTIES *BlobProperties; // rax
  struct ITextBlob::BLOB_PROPERTIES *v19; // rsi
  CTextMarkContainer *v20; // rcx
  __int16 v21; // ax
  int v22; // ecx
  int v23; // r11d
  int v24; // ecx
  int v25; // eax
  LONG cy; // ecx
  unsigned int v27; // r11d
  LPVOID v29; // rax
  HMETAFILE v30; // rcx
  struct tagPOINT **v31; // [rsp+20h] [rbp-40h]
  struct tagSIZE sizel; // [rsp+30h] [rbp-30h] BYREF
  struct tagPOINT *v33; // [rsp+38h] [rbp-28h] BYREF
  int v34[4]; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+50h] [rbp-10h]
  int v36; // [rsp+A0h] [rbp+40h]
  CTextBlobSurrogate *v37; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v38; // [rsp+B8h] [rbp+58h]

  memset_0(a2, 0, sizeof(struct _reobject));
  a2->cbStruct = 72;
  COleObject::GetObjectData((COleObject *)a3, a2, 7u);
  memset_0(this, 0, 0x78u);
  v6 = a2->pstg != 0;
  v7 = a2->dwFlags & 0x40000000;
  v8 = *(_QWORD *)&a2->clsid.Data1 - *(_QWORD *)&CLSID_Picture_EnhMetafile.Data1;
  v36 = 1;
  v38 = v7;
  if ( !v8 )
    v8 = *(_QWORD *)a2->clsid.Data4 - *(_QWORD *)CLSID_Picture_EnhMetafile.Data4;
  v9 = (_WORD *)a3 + 77;
  v10 = v8 == 0;
  *(_WORD *)this = 8 * v10 + 1;
  if ( !v7 )
  {
    sizel = 0;
    if ( (*v9 & 0x1000) != 0 )
    {
      *(_WORD *)this = 8;
      if ( CTxtEdit::GetTextMarkContainer(a3[6]) )
      {
        CTextBlobSurrogatePointer::CTextBlobSurrogatePointer(
          (CTextBlobSurrogatePointer *)&v37,
          (const struct COleObject *)a3);
        IsSimplePersistBlob = CTextBlobSurrogate::IsSimplePersistBlob(v37);
        CTextBlobSurrogatePointer::~CTextBlobSurrogatePointer((CTextBlobSurrogatePointer *)&v37);
        if ( IsSimplePersistBlob )
        {
          Image = CTextMarkContainer::GetImage(v12, (const struct COleObject *)a3);
          v37 = Image;
          if ( Image )
          {
            *(_OWORD *)((char *)this + 52) = *((_OWORD *)Image + 11);
            *((_BYTE *)this + 10) = *((_BYTE *)Image + 200) & 3;
            *((_BYTE *)this + 12) = (*((_BYTE *)Image + 200) & 4) != 0;
            *((_BYTE *)this + 13) = (*((_BYTE *)Image + 200) & 8) != 0;
            *((_DWORD *)this + 4) = *((_DWORD *)Image + 51);
          }
          *(_WORD *)this = 12;
          Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v37);
        }
      }
      v6 = 1;
    }
    else if ( !(unsigned int)CW32System::ProgIDFromCLSID(&a2->clsid, (unsigned __int16 **)&sizel) )
    {
      *((struct tagSIZE *)this + 9) = sizel;
      *(_WORD *)this = 5;
      v36 = 0;
      goto LABEL_13;
    }
    if ( (*v9 & 0x1000) == 0 )
      *(_WORD *)this = 1;
  }
LABEL_13:
  *((_DWORD *)this + 12) = a2->dwFlags;
  if ( !v6 )
    return 0;
  v14 = a2->poleobj == 0;
  EnhMetafilePict = 1;
  sizel = a2->sizel;
  if ( v14 )
    goto LABEL_30;
  if ( (*v9 & 0x1000) != 0 )
  {
    if ( !CTxtEdit::GetTextMarkContainer(a3[6]) )
      goto LABEL_30;
    MetafilePictFromBlob = 0;
    BlobProperties = CTextMarkContainer::GetBlobProperties(v16, (const struct COleObject *)a3);
    v19 = BlobProperties;
    if ( BlobProperties )
    {
      if ( (*((_DWORD *)BlobProperties + 7) & 0x18) == 8 )
        MetafilePictFromBlob = GetMetafilePictFromBlob(a3, &sizel);
      if ( *((_DWORD *)v19 + 8) )
        *((_DWORD *)this + 7) = *((_DWORD *)v19 + 2) - *((_DWORD *)v19 + 8);
    }
    if ( (unsigned int)COleObject::FWrapTextAround((COleObject *)a3) )
    {
      LODWORD(v37) = 0;
      v35 = 0;
      v33 = 0;
      *(_OWORD *)v34 = 0;
      CTextMarkContainer::GetMultiLineBlobInfo(
        v20,
        (const struct COleObject *)a3,
        (unsigned int *)&v37,
        (struct ITextMarkContainer::MLBLOB_CREATE_DATA *)v34,
        (const struct tagPOINT **)&v33);
      v21 = CW32System::MulDivFunc(v34[3], 72, 127);
      v22 = v35;
      *((_WORD *)this + 22) = v21;
      *((_WORD *)this + 23) = CW32System::MulDivFunc(v22, v23 - 55, v23);
    }
  }
  else
  {
    v24 = *((_DWORD *)a3 + 24);
    *((_WORD *)this + 22) = *((_WORD *)a3 + 46);
    *((_WORD *)this + 23) = v24;
    MetafilePictFromBlob = OleStdGetMetafilePictFromOleObject(
                             a2->poleobj,
                             v10,
                             a2->dvaspect,
                             &sizel,
                             (struct tagDVTARGETDEVICE *)v31,
                             0);
  }
  if ( MetafilePictFromBlob )
  {
    if ( v10 )
    {
      EnhMetafilePict = CRTFObject::GetEnhMetafilePict(this, MetafilePictFromBlob, &sizel, 0, 0);
      goto LABEL_30;
    }
    EnhMetafilePict = CRTFObject::GetMetafilePict(this, MetafilePictFromBlob, &sizel);
    v29 = GlobalLock(MetafilePictFromBlob);
    if ( v29 )
    {
      v30 = (HMETAFILE)*((_QWORD *)v29 + 2);
      if ( v30 )
        DeleteMetaFile(v30);
      GlobalUnlock(MetafilePictFromBlob);
    }
    CW32System::GlobalFree(MetafilePictFromBlob);
    if ( EnhMetafilePict || !v36 )
      goto LABEL_30;
    return 0;
  }
LABEL_30:
  if ( !v38 )
  {
    v25 = CW32System::MulDivFunc(sizel.cx, 72, 127);
    cy = sizel.cy;
    *((_DWORD *)this + 5) = v25;
    *((_DWORD *)this + 6) = CW32System::MulDivFunc(cy, 72, 127);
    EnhMetafilePict = v27;
  }
  *((_BYTE *)this + 14) = 0;
  return EnhMetafilePict;
}

```

## disassembly

```asm
0x180158afc  mov     [rsp-38h+arg_10], rbx
0x180158b01  push    rbp
0x180158b02  push    rsi
0x180158b03  push    rdi
0x180158b04  push    r12
0x180158b06  push    r13
0x180158b08  push    r14
0x180158b0a  push    r15
0x180158b0c  mov     rbp, rsp
0x180158b0f  sub     rsp, 60h
0x180158b13  mov     r12, rdx
0x180158b16  mov     r14, r8
0x180158b19  mov     rdi, rcx
0x180158b1c  mov     ebx, 48h ; 'H'
0x180158b21  mov     r8d, ebx; Size
0x180158b24  mov     rcx, r12; void *
0x180158b27  xor     edx, edx; Val
0x180158b29  call    memset_0
0x180158b2e  lea     r8d, [rbx-41h]; unsigned int
0x180158b32  mov     [r12], ebx
0x180158b36  mov     rdx, r12; struct _reobject *
0x180158b39  mov     rcx, r14; this
0x180158b3c  call    ?GetObjectData@COleObject@@QEAAJPEAU_reobject@@K@Z; COleObject::GetObjectData(_reobject *,ulong)
0x180158b41  xor     edx, edx; Val
0x180158b43  lea     r8d, [rbx+30h]; Size
0x180158b47  mov     rcx, rdi; void *
0x180158b4a  call    memset_0
0x180158b4f  mov     edx, [r12+3Ch]
0x180158b54  lea     rcx, [r12+8]; struct _GUID *
0x180158b59  mov     rax, [rcx]
0x180158b5c  xor     r15d, r15d
0x180158b5f  cmp     [r12+20h], r15
0x180158b64  mov     ebx, r15d
0x180158b67  setnz   bl
0x180158b6a  and     edx, 40000000h
0x180158b70  sub     rax, qword ptr cs:CLSID_Picture_EnhMetafile.Data1
0x180158b77  lea     r11d, [r15+1]
0x180158b7b  mov     [rbp+arg_0], r11d
0x180158b7f  mov     [rbp+arg_18], edx
0x180158b82  jnz     short loc_180158B8F
0x180158b84  mov     rax, [rcx+8]
0x180158b88  sub     rax, qword ptr cs:CLSID_Picture_EnhMetafile.Data4
0x180158b8f  test    rax, rax
0x180158b92  lea     rsi, [r14+9Ah]
0x180158b99  mov     r13d, r15d
0x180158b9c  mov     r8d, 1000h
0x180158ba2  setz    r13b
0x180158ba6  movzx   eax, r13w
0x180158baa  shl     ax, 3
0x180158bae  add     ax, r11w
0x180158bb2  mov     [rdi], ax
0x180158bb5  test    edx, edx
0x180158bb7  jnz     loc_180158C7F
0x180158bbd  mov     qword ptr [rbp+var_30.cx], r15
0x180158bc1  test    [rsi], r8w
0x180158bc5  jz      loc_180158D6D
0x180158bcb  mov     word ptr [rdi], 8
0x180158bd0  mov     rcx, [r14+30h]; this
0x180158bd4  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x180158bd9  test    rax, rax
0x180158bdc  jz      loc_180158C66
0x180158be2  mov     rdx, r14; struct COleObject *
0x180158be5  lea     rcx, [rbp+arg_8]; this
0x180158be9  call    ??0CTextBlobSurrogatePointer@@QEAA@AEBVCOleObject@@@Z; CTextBlobSurrogatePointer::CTextBlobSurrogatePointer(COleObject const &)
0x180158bee  mov     rcx, [rbp+arg_8]; this
0x180158bf2  call    ?IsSimplePersistBlob@CTextBlobSurrogate@@QEBAHXZ; CTextBlobSurrogate::IsSimplePersistBlob(void)
0x180158bf7  lea     rcx, [rbp+arg_8]; this
0x180158bfb  mov     ebx, eax
0x180158bfd  call    ??1CTextBlobSurrogatePointer@@QEAA@XZ; CTextBlobSurrogatePointer::~CTextBlobSurrogatePointer(void)
0x180158c02  test    ebx, ebx
0x180158c04  jz      short loc_180158C66
0x180158c06  mov     rdx, r14; struct COleObject *
0x180158c09  call    ?GetImage@CTextMarkContainer@@QEAAPEAVCImage@@AEBVCOleObject@@@Z; CTextMarkContainer::GetImage(COleObject const &)
0x180158c0e  mov     [rbp+arg_8], rax
0x180158c12  mov     rdx, rax
0x180158c15  test    rax, rax
0x180158c18  jz      short loc_180158C58
0x180158c1a  movups  xmm0, xmmword ptr [rax+0B0h]
0x180158c21  movdqu  xmmword ptr [rdi+34h], xmm0
0x180158c26  mov     cl, [rax+0C8h]
0x180158c2c  and     cl, 3
0x180158c2f  mov     [rdi+0Ah], cl
0x180158c32  mov     cl, [rax+0C8h]
0x180158c38  shr     cl, 2
0x180158c3b  and     cl, 1
0x180158c3e  mov     [rdi+0Ch], cl
0x180158c41  mov     al, [rax+0C8h]
0x180158c47  shr     al, 3
0x180158c4a  and     al, 1
0x180158c4c  mov     [rdi+0Dh], al
0x180158c4f  mov     eax, [rdx+0CCh]
0x180158c55  mov     [rdi+10h], eax
0x180158c58  lea     rcx, [rbp+arg_8]; void *
0x180158c5c  mov     word ptr [rdi], 0Ch
0x180158c61  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180158c66  mov     r11d, 1
0x180158c6c  mov     ebx, r11d
0x180158c6f  mov     r8d, 1000h
0x180158c75  test    [rsi], r8w
0x180158c79  jnz     short loc_180158C7F
0x180158c7b  mov     [rdi], r11w
0x180158c7f  mov     eax, [r12+3Ch]
0x180158c84  mov     [rdi+30h], eax
0x180158c87  test    ebx, ebx
0x180158c89  jz      loc_180158E7F
0x180158c8f  cmp     qword ptr [r12+18h], 0
0x180158c95  mov     r15d, r11d
0x180158c98  mov     rax, [r12+30h]
0x180158c9d  mov     qword ptr [rbp+var_30.cx], rax
0x180158ca1  jz      loc_180158E99
0x180158ca7  test    [rsi], r8w
0x180158cab  jz      loc_180158DA0
0x180158cb1  mov     rcx, [r14+30h]; this
0x180158cb5  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x180158cba  xor     r12d, r12d
0x180158cbd  test    rax, rax
0x180158cc0  jz      loc_180158DFA
0x180158cc6  mov     rdx, r14; struct COleObject *
0x180158cc9  mov     ebx, r12d
0x180158ccc  call    ?GetBlobProperties@CTextMarkContainer@@QEAAPEAUBLOB_PROPERTIES@ITextBlob@@AEBVCOleObject@@@Z; CTextMarkContainer::GetBlobProperties(COleObject const &)
0x180158cd1  mov     rsi, rax
0x180158cd4  test    rax, rax
0x180158cd7  jz      short loc_180158D02
0x180158cd9  mov     ecx, [rax+1Ch]
0x180158cdc  and     cl, 18h
0x180158cdf  cmp     cl, 8
0x180158ce2  jnz     short loc_180158CF3
0x180158ce4  lea     rdx, [rbp+var_30]; struct tagSIZE *
0x180158ce8  mov     rcx, r14; struct COleObject *
0x180158ceb  call    ?GetMetafilePictFromBlob@@YAPEAXPEAVCOleObject@@PEAUtagSIZE@@@Z; GetMetafilePictFromBlob(COleObject *,tagSIZE *)
0x180158cf0  mov     rbx, rax
0x180158cf3  cmp     [rsi+20h], r12d
0x180158cf7  jz      short loc_180158D02
0x180158cf9  mov     ecx, [rsi+8]
0x180158cfc  sub     ecx, [rsi+20h]
0x180158cff  mov     [rdi+1Ch], ecx
0x180158d02  mov     rcx, r14; this
0x180158d05  call    ?FWrapTextAround@COleObject@@QEBAHXZ; COleObject::FWrapTextAround(void)
0x180158d0a  test    eax, eax
0x180158d0c  jz      loc_180158DD6
0x180158d12  xor     eax, eax
0x180158d14  mov     dword ptr [rbp+arg_8], r12d
0x180158d18  mov     [rbp+var_10], eax
0x180158d1b  lea     r9, [rbp+var_20]; struct ITextMarkContainer::MLBLOB_CREATE_DATA *
0x180158d1f  lea     rax, [rbp+var_28]
0x180158d23  mov     [rbp+var_28], r12
0x180158d27  xorps   xmm0, xmm0
0x180158d2a  mov     [rsp+60h+var_40], rax; struct tagPOINT **
0x180158d2f  lea     r8, [rbp+arg_8]; unsigned int *
0x180158d33  mov     rdx, r14; struct COleObject *
0x180158d36  movups  xmmword ptr [rbp+var_20], xmm0
0x180158d3a  call    ?GetMultiLineBlobInfo@CTextMarkContainer@@QEAAHAEBVCOleObject@@AEAKAEAUMLBLOB_CREATE_DATA@ITextMarkContainer@@AEAPEBUtagPOINT@@@Z; CTextMarkContainer::GetMultiLineBlobInfo(COleObject const &,ulong &,ITextMarkContainer::MLBLOB_CREATE_DATA &,tagPOINT const * &)
0x180158d3f  mov     ecx, [rbp+var_20+0Ch]; int
0x180158d42  mov     r11d, 7Fh
0x180158d48  mov     r8d, r11d; int
0x180158d4b  lea     edx, [r11-37h]; int
0x180158d4f  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158d54  mov     ecx, [rbp+var_10]; int
0x180158d57  lea     edx, [r11-37h]; int
0x180158d5b  mov     r8d, r11d; int
0x180158d5e  mov     [rdi+2Ch], ax
0x180158d62  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158d67  mov     [rdi+2Eh], ax
0x180158d6b  jmp     short loc_180158DD6
0x180158d6d  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x180158d71  call    ?ProgIDFromCLSID@CW32System@@SAJAEBU_GUID@@PEAPEAG@Z; CW32System::ProgIDFromCLSID(_GUID const &,ushort * *)
0x180158d76  mov     r11d, 1
0x180158d7c  test    eax, eax
0x180158d7e  jnz     loc_180158C6F
0x180158d84  mov     rax, qword ptr [rbp+var_30.cx]
0x180158d88  mov     r8d, 1000h
0x180158d8e  mov     [rdi+48h], rax
0x180158d92  mov     word ptr [rdi], 5
0x180158d97  mov     [rbp+arg_0], r15d
0x180158d9b  jmp     loc_180158C7F
0x180158da0  mov     ecx, [r14+60h]
0x180158da4  lea     r9, [rbp+var_30]; struct tagSIZE *
0x180158da8  movzx   eax, word ptr [r14+5Ch]
0x180158dad  mov     edx, r13d; int
0x180158db0  mov     [rdi+2Ch], ax
0x180158db4  mov     [rdi+2Eh], cx
0x180158db8  mov     r8d, [r12+38h]; unsigned int
0x180158dbd  mov     rcx, [r12+18h]; struct IOleObject *
0x180158dc2  mov     [rsp+60h+hdcRef], 0; hdcRef
0x180158dcb  call    ?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@HKPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; OleStdGetMetafilePictFromOleObject(IOleObject *,int,ulong,tagSIZE *,tagDVTARGETDEVICE *,HDC__ *)
0x180158dd0  mov     rbx, rax
0x180158dd3  xor     r12d, r12d
0x180158dd6  test    rbx, rbx
0x180158dd9  jz      short loc_180158DFA
0x180158ddb  lea     r8, [rbp+var_30]; struct tagSIZE *
0x180158ddf  mov     rdx, rbx; void *
0x180158de2  mov     rcx, rdi; this
0x180158de5  test    r13d, r13d
0x180158de8  jz      short loc_180158E3A
0x180158dea  xor     r9d, r9d; int
0x180158ded  mov     [rsp+60h+var_40], r12; struct CTxtEdit *
0x180158df2  call    ?GetEnhMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@HPEAVCTxtEdit@@@Z; CRTFObject::GetEnhMetafilePict(void *,tagSIZE const &,int,CTxtEdit *)
0x180158df7  mov     r15d, eax
0x180158dfa  mov     r11d, 1
0x180158e00  cmp     [rbp+arg_18], r12d
0x180158e04  jnz     short loc_180158E31
0x180158e06  mov     ecx, [rbp+var_30.cx]; int
0x180158e09  mov     edx, 48h ; 'H'; int
0x180158e0e  lea     r8d, [rdx+37h]; int
0x180158e12  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158e17  mov     ecx, [rbp+var_30.cy]; int
0x180158e1a  mov     edx, 48h ; 'H'; int
0x180158e1f  mov     [rdi+14h], eax
0x180158e22  lea     r8d, [rdx+37h]; int
0x180158e26  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158e2b  mov     [rdi+18h], eax
0x180158e2e  mov     r15d, r11d
0x180158e31  mov     [rdi+0Eh], r12b
0x180158e35  mov     eax, r15d
0x180158e38  jmp     short loc_180158E81
0x180158e3a  call    ?GetMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@@Z; CRTFObject::GetMetafilePict(void *,tagSIZE const &)
0x180158e3f  mov     rcx, rbx; hMem
0x180158e42  mov     r15d, eax
0x180158e45  call    cs:__imp_GlobalLock
0x180158e4b  test    rax, rax
0x180158e4e  jz      short loc_180158E68
0x180158e50  mov     rcx, [rax+10h]; hmf
0x180158e54  test    rcx, rcx
0x180158e57  jz      short loc_180158E5F
0x180158e59  call    cs:__imp_DeleteMetaFile
0x180158e5f  mov     rcx, rbx; hMem
0x180158e62  call    cs:__imp_GlobalUnlock
0x180158e68  mov     rcx, rbx; void *
0x180158e6b  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180158e70  test    r15d, r15d
0x180158e73  jnz     short loc_180158DFA
0x180158e75  cmp     [rbp+arg_0], r12d
0x180158e79  jz      loc_180158DFA
0x180158e7f  xor     eax, eax
0x180158e81  mov     rbx, [rsp+60h+arg_10]
0x180158e89  add     rsp, 60h
0x180158e8d  pop     r15
0x180158e8f  pop     r14
0x180158e91  pop     r13
0x180158e93  pop     r12
0x180158e95  pop     rdi
0x180158e96  pop     rsi
0x180158e97  pop     rbp
0x180158e98  retn
0x180158e99  xor     r12d, r12d
0x180158e9c  jmp     loc_180158E00
```
