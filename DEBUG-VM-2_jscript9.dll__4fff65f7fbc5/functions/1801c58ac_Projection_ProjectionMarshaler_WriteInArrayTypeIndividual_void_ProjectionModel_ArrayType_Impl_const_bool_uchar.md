# Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(void *,ProjectionModel::ArrayType::Impl const *,bool,uchar *,uchar *,bool,bool,uint)

- ea: `0x1801c58ac`
- end: `0x1801c5f11`
- name: `?WriteInArrayTypeIndividual@ProjectionMarshaler@Projection@@QEAAXPEAXPEBUImpl@ArrayType@ProjectionModel@@_NPEAE322I@Z`
- size: `1637`
- prototype: `void __fastcall(Projection::ProjectionMarshaler *__hidden this, void *, const struct ProjectionModel::ArrayType::Impl *, bool, unsigned __int8 *, unsigned __int8 *, bool, bool, unsigned int)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180225710`
- `0x1802427bc`
- `0x180247478`
- `0x180247684`

## callees

- `0x1800194d0`
- `0x18005f188`
- `0x1800dea90`
- `0x1800deb30`
- `0x180107364`
- `0x180109220`
- `0x18014d470`
- `0x1801758b8`
- `0x1801a8a70`
- `0x1801bdec0`
- `0x1801bf718`
- `0x1801c58ac`
- `0x1801c8178`
- `0x1801c989b`
- `0x1802262d4`
- `0x18022c8b4`
- `0x18022d398`
- `0x18022d5c0`
- `0x18022e810`
- `0x180241560`
- `0x1802465a0`
- `0x180246694`
- `0x180247478`
- `0x180330cc4`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801c5c55`
- `KERNEL32!LoadLibraryExW` at `0x1801c5d89`
- `KERNEL32!LoadLibraryExW` at `0x1801c5c55`
- `KERNEL32!LoadLibraryExW` at `0x1801c5d89`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801c5dee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801c5dee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(
        Projection::ProjectionMarshaler *this,
        unsigned int *a2,
        const struct ProjectionModel::Type **a3,
        char a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        bool a7,
        bool a8,
        unsigned int a9)
{
  bool IsArrayInstance; // di
  int TypeId; // eax
  int v13; // edx
  int v14; // r8d
  struct Js::ScriptContext *v15; // r15
  unsigned int v16; // edi
  unsigned int v17; // r14d
  const struct ProjectionModel::ConcreteType *v18; // rax
  const struct ProjectionModel::ConcreteType *v19; // rsi
  size_t v20; // r14
  double v21; // xmm0_8
  bool v22; // r12
  void **v23; // r15
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rbx
  unsigned int v27; // r12d
  __int64 v28; // r15
  unsigned int v29; // r14d
  _QWORD *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r12
  const WCHAR *v33; // rax
  void *v34; // rax
  __int64 v35; // rdi
  _QWORD *v36; // rbx
  _BYTE *v37; // rdx
  const WCHAR *v38; // rax
  HMODULE Library; // rax
  LPVOID v40; // rax
  __int64 v41; // r14
  _QWORD *v42; // rax
  unsigned int *v43; // rbx
  struct Js::ScriptContext *v44; // rdx
  unsigned __int8 *v45; // rdi
  unsigned int v46; // r14d
  __int64 v47; // r12
  void *v48; // rax
  void *ElementI; // rax
  unsigned int v50; // [rsp+38h] [rbp-C1h]
  __int64 v51; // [rsp+48h] [rbp-B1h] BYREF
  int v52; // [rsp+50h] [rbp-A9h]
  int v53; // [rsp+54h] [rbp-A5h]
  struct Js::ScriptContext *v54; // [rsp+58h] [rbp-A1h]
  int v55; // [rsp+60h] [rbp-99h]
  BOOL v56; // [rsp+64h] [rbp-95h]
  __int64 v57; // [rsp+68h] [rbp-91h]
  __int64 v58; // [rsp+70h] [rbp-89h]
  int v59; // [rsp+7Ch] [rbp-7Dh]
  __int64 v60; // [rsp+80h] [rbp-79h]
  _BYTE v61[176]; // [rsp+88h] [rbp-71h] BYREF

  v60 = -2;
  Projection::ProjectionMarshaler::RecordRecyclerVar(this, a2, 0);
  LODWORD(v51) = (unsigned int)Js::JavascriptOperators::GetTypeId(a2) <= 1;
  IsArrayInstance = Projection::ArrayAsCollection::IsArrayInstance(a2);
  v55 = Projection::ArrayProjection::Is(a2);
  v56 = (unsigned int)Js::JavascriptOperators::GetTypeId(a2) - 33 <= 0xC;
  TypeId = Js::JavascriptOperators::GetTypeId(a2);
  LODWORD(v57) = TypeId;
  v15 = *(struct Js::ScriptContext **)(*((_QWORD *)this + 2) + 112LL);
  v54 = v15;
  if ( (_DWORD)v51 )
  {
    if ( !IsArrayInstance )
      goto LABEL_9;
LABEL_8:
    v16 = a2[8];
    goto LABEL_15;
  }
  if ( IsArrayInstance )
    goto LABEL_8;
  if ( !v14 )
  {
    if ( !v13 )
    {
      if ( TypeId != 31 )
        Js::JavascriptError::ThrowTypeError(v15, -2146823257, 0);
      goto LABEL_12;
    }
LABEL_10:
    v16 = a2[12];
    goto LABEL_15;
  }
LABEL_9:
  if ( v13 )
    goto LABEL_10;
  if ( TypeId == 31 )
  {
LABEL_12:
    v16 = a2[10];
    goto LABEL_15;
  }
  v16 = 0;
  if ( v14 )
    v16 = *(_DWORD *)(*((_QWORD *)a2 + 6) + 16LL);
LABEL_15:
  v17 = v16;
  if ( a8 )
    v17 = a9;
  v50 = v17;
  v18 = ProjectionModel::ConcreteType::From(a3[5]);
  v19 = v18;
  if ( a8 && v17 > v16 )
    Js::JavascriptError::ThrowTypeError(v15, -2146823177, 0);
  v58 = *((_QWORD *)v18 + 3);
  v20 = v58 * v16;
  if ( v20 < v16
    || ((v20 & 0x8000000000000000uLL) != 0LL
      ? (v21 = (double)(int)(v20 & 1 | (v20 >> 1)) + (double)(int)(v20 & 1 | (v20 >> 1)))
      : (v21 = (double)(int)v20),
        (unsigned int)Js::JavascriptMath::ToInt32Core(v21, v15) < v16) )
  {
LABEL_79:
    Js::JavascriptError::MapAndThrowError(v15, -2147024882);
  }
  *(_DWORD *)a5 = v16;
  v22 = 1;
  v23 = (void **)a6;
  if ( !*((_DWORD *)this + 24) )
  {
    if ( v55 )
    {
      v24 = *((_QWORD *)a2 + 6);
      if ( *(_DWORD *)(*(_QWORD *)(v24 + 8) + 4LL) == *((_DWORD *)v19 + 1) )
      {
        v25 = *(_QWORD *)(v24 + 24);
        v22 = 0;
LABEL_38:
        *(_QWORD *)a6 = v25;
        if ( a7 )
        {
          v26 = v25;
          v27 = 0;
          if ( v16 )
          {
            do
            {
              Projection::ProjectionMarshaler::RecordTypeToUndo(
                (_DWORD)this,
                (unsigned int)Projection::ProjectionMarshaler::ClearString,
                (unsigned int)Projection::ProjectionMarshaler::ClearUnknown,
                (_DWORD)v19,
                v26,
                v58);
              v26 += v58;
              ++v27;
            }
            while ( v27 < v16 );
            v23 = (void **)a6;
          }
          memset_0(*v23, 0, v20);
          return;
        }
        if ( v50 >= v16 )
          return;
        v51 = v58 * v50;
        v28 = v51 + *(_QWORD *)a6;
        v29 = v50;
        do
        {
          Projection::ProjectionMarshaler::RecordTypeToUndo(
            (_DWORD)this,
            (unsigned int)Projection::ProjectionMarshaler::ClearString,
            (unsigned int)Projection::ProjectionMarshaler::ClearUnknown,
            (_DWORD)v19,
            v28,
            v58);
          v28 += v58;
          ++v29;
        }
        while ( v29 < v16 );
        v23 = (void **)a6;
        memset_0((void *)(*(_QWORD *)a6 + v51), 0, v58 * (v16 - v50));
        goto LABEL_71;
      }
      goto LABEL_48;
    }
    v22 = 0;
    if ( v56 )
    {
      if ( *(_DWORD *)v19 == 15
        && *((int *)ProjectionModel::BasicType::From(v19) + 10) <= 13
        && !(unsigned int)Projection::ArrayProjection::NeedConversion(v19, a2) )
      {
        v25 = *((_QWORD *)a2 + 7);
        goto LABEL_38;
      }
LABEL_48:
      Js::JavascriptError::ThrowTypeError(v54, -2146828275, 0);
    }
    if ( (_DWORD)v57 == 31 )
    {
      if ( *(_DWORD *)v19 == 15 && *((_DWORD *)ProjectionModel::BasicType::From(v19) + 10) == 5 )
      {
        v25 = *((_QWORD *)a2 + 4);
        goto LABEL_38;
      }
      goto LABEL_48;
    }
    if ( (_DWORD)v51 || ProjectionModel::ConcreteType::IsBlittable(v19) )
    {
      v51 = (__int64)ArenaAllocator::AllocZero;
      v52 = 0;
      v53 = v59;
      v35 = AllocateArray<ArenaAllocator,unsigned char,0>(*((_QWORD *)this + 1), &v51, v20);
      goto LABEL_59;
    }
    v51 = *((_QWORD *)v54 + 285);
    v30 = (_QWORD *)operator new<HeapAllocator>(72, v51, Recycler::AllocFinalized);
    if ( v30 )
    {
      v31 = *((_QWORD *)this + 2);
      v32 = *(_QWORD *)(v31 + 96) + 8408LL;
      if ( !*(_BYTE *)(*(_QWORD *)(v31 + 96) + 8424LL) )
      {
        v33 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(*(_QWORD *)(v31 + 96) + 8408LL);
        *(_QWORD *)(v32 + 8) = LoadLibraryExW(v33, 0, 0x800u);
        *(_BYTE *)(v32 + 16) = 1;
      }
      *v30 = &Projection::FinalizableTypedArrayContents::`vftable';
      v30[1] = v19;
      *((_DWORD *)v30 + 4) = v16;
      v30[3] = 0;
      v30[4] = v51;
      v30[5] = v32;
      v30[6] = *((_QWORD *)v19 + 3);
      v30[7] = 0;
      *((_DWORD *)v30 + 16) = 0;
    }
    else
    {
      v30 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v30, 1);
    v34 = operator new[](v20);
    v35 = (__int64)v34;
    if ( v34 )
    {
      memset_0(v34, 0, v20);
      v30[3] = v35;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v30);
LABEL_59:
      v22 = !a7;
LABEL_70:
      *(_QWORD *)a6 = v35;
LABEL_71:
      v43 = a2;
      if ( !v22 )
        return;
      goto LABEL_74;
    }
    goto LABEL_78;
  }
  if ( a4 )
  {
    v57 = *((_QWORD *)v54 + 285);
    v36 = (_QWORD *)operator new<HeapAllocator>(72, v57, Recycler::AllocFinalized);
    if ( v36 )
    {
      v37 = (_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 96LL) + 8408LL);
      v51 = (__int64)v37;
      if ( !v37[16] )
      {
        v38 = (const WCHAR *)(*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v37 + 8LL))(v37);
        Library = LoadLibraryExW(v38, 0, 0x800u);
        v37 = (_BYTE *)v51;
        *(_QWORD *)(v51 + 8) = Library;
        v37[16] = 1;
      }
      *v36 = &Projection::FinalizableTypedArrayContents::`vftable';
      v36[1] = v19;
      *((_DWORD *)v36 + 4) = v16;
      v36[3] = 0;
      v36[4] = v57;
      v36[5] = v37;
      v36[6] = *((_QWORD *)v19 + 3);
      v36[7] = 0;
      *((_DWORD *)v36 + 16) = 1;
    }
    else
    {
      v36 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v36, 1);
    v40 = CoTaskMemAlloc(v20);
    v35 = (__int64)v40;
    if ( v40 )
    {
      v36[3] = v40;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v36);
      v41 = *((_QWORD *)this + 11);
      v51 = (__int64)ArenaAllocator::Alloc;
      v52 = 0;
      v53 = v59;
      v42 = (_QWORD *)operator new<ArenaAllocator>(16, *((_QWORD *)this + 1), &v51);
      if ( v42 )
      {
        *v42 = v36;
        v42[1] = v41;
      }
      *((_QWORD *)this + 11) = v42;
      goto LABEL_70;
    }
LABEL_78:
    v15 = v54;
    goto LABEL_79;
  }
  v43 = a2;
LABEL_74:
  Projection::ProjectionMarshaler::ProjectionMarshaler(v61, 1, *((_QWORD *)this + 2));
  v45 = (unsigned __int8 *)*v23;
  v46 = 0;
  if ( v50 )
  {
    v47 = v58;
    do
    {
      v48 = Js::JavascriptNumber::ToVar(v46, v44);
      ElementI = Js::JavascriptOperators::OP_GetElementI(v43, v48, v54);
      Projection::ProjectionMarshaler::WriteInType((Projection::ProjectionMarshaler *)v61, ElementI, v19, v45, v47, 1);
      Projection::ProjectionMarshaler::RecordTypeToUndo(
        (_DWORD)this,
        (unsigned int)Projection::ProjectionMarshaler::RecordDelegateOutString,
        (unsigned int)Projection::ProjectionMarshaler::RecordDelegateOutUnknown,
        (_DWORD)v19,
        (__int64)v45,
        v47);
      v45 += v47;
      ++v46;
    }
    while ( v46 < v50 );
  }
  Projection::ProjectionMarshaler::~ProjectionMarshaler((Projection::ProjectionMarshaler *)v61);
}

```

## disassembly

```asm
0x1801c58ac  mov     rax, rsp
0x1801c58af  mov     [rax+20h], r9b
0x1801c58b3  mov     [rax+18h], r8
0x1801c58b7  mov     [rax+10h], rdx
0x1801c58bb  mov     [rax+8], rcx
0x1801c58bf  push    rbp
0x1801c58c0  push    rbx
0x1801c58c1  push    rsi
0x1801c58c2  push    rdi
0x1801c58c3  push    r12
0x1801c58c5  push    r13
0x1801c58c7  push    r14
0x1801c58c9  push    r15
0x1801c58cb  lea     rbp, [rax-47h]
0x1801c58cf  sub     rsp, 0F8h
0x1801c58d6  mov     [rbp+3Fh+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801c58de  xor     r8d, r8d; bool
0x1801c58e1  mov     rbx, [rbp+3Fh+arg_8]
0x1801c58e5  mov     rdx, rbx; void *
0x1801c58e8  mov     r13, [rbp+3Fh+arg_0]
0x1801c58ec  mov     rcx, r13; this
0x1801c58ef  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x1801c58f4  mov     rcx, rbx
0x1801c58f7  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c58fc  xor     esi, esi
0x1801c58fe  cmp     eax, 1
0x1801c5901  setbe   sil
0x1801c5905  mov     [rsp+130h+var_F0], esi
0x1801c5909  mov     rcx, rbx; void *
0x1801c590c  call    ?IsArrayInstance@ArrayAsCollection@Projection@@SA_NPEAX@Z; Projection::ArrayAsCollection::IsArrayInstance(void *)
0x1801c5911  mov     dil, al
0x1801c5914  mov     rcx, rbx; void *
0x1801c5917  call    ?Is@ArrayProjection@Projection@@SAHPEAX@Z; Projection::ArrayProjection::Is(void *)
0x1801c591c  mov     r8d, eax
0x1801c591f  mov     dword ptr [rsp+130h+var_D8], eax
0x1801c5923  mov     rcx, rbx
0x1801c5926  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c592b  add     eax, 0FFFFFFDFh
0x1801c592e  xor     edx, edx
0x1801c5930  cmp     eax, 0Ch
0x1801c5933  setbe   dl
0x1801c5936  mov     dword ptr [rsp+130h+var_D8+4], edx
0x1801c593a  mov     rcx, rbx
0x1801c593d  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c5942  mov     dword ptr [rsp+130h+var_D0], eax
0x1801c5946  mov     rcx, [r13+10h]
0x1801c594a  mov     r15, [rcx+70h]
0x1801c594e  mov     [rsp+130h+var_E0], r15
0x1801c5953  test    esi, esi
0x1801c5955  jnz     short loc_1801C597B
0x1801c5957  test    dil, dil
0x1801c595a  jnz     short loc_1801C5980
0x1801c595c  test    r8d, r8d
0x1801c595f  jnz     short loc_1801C5985
0x1801c5961  test    edx, edx
0x1801c5963  jnz     short loc_1801C5989
0x1801c5965  cmp     eax, 1Fh
0x1801c5968  jz      short loc_1801C5993
0x1801c596a  xor     r8d, r8d; unsigned __int16 *
0x1801c596d  mov     edx, 800A13A7h; int
0x1801c5972  mov     rcx, r15; struct Js::ScriptContext *
0x1801c5975  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c597b  test    dil, dil
0x1801c597e  jz      short loc_1801C5985
0x1801c5980  mov     edi, [rbx+20h]
0x1801c5983  jmp     short loc_1801C59A6
0x1801c5985  test    edx, edx
0x1801c5987  jz      short loc_1801C598E
0x1801c5989  mov     edi, [rbx+30h]
0x1801c598c  jmp     short loc_1801C59A6
0x1801c598e  cmp     eax, 1Fh
0x1801c5991  jnz     short loc_1801C5998
0x1801c5993  mov     edi, [rbx+28h]
0x1801c5996  jmp     short loc_1801C59A6
0x1801c5998  xor     edi, edi
0x1801c599a  test    r8d, r8d
0x1801c599d  jz      short loc_1801C59A6
0x1801c599f  mov     rax, [rbx+30h]
0x1801c59a3  mov     edi, [rax+10h]
0x1801c59a6  mov     r14d, edi
0x1801c59a9  mov     bl, [rbp+3Fh+arg_38]
0x1801c59af  test    bl, bl
0x1801c59b1  cmovnz  r14d, [rbp+3Fh+arg_40]
0x1801c59b9  mov     [rsp+30h], r14d
0x1801c59be  mov     rcx, [rbp+3Fh+arg_10]
0x1801c59c2  mov     rcx, [rcx+28h]; struct ProjectionModel::Type *
0x1801c59c6  call    ?From@ConcreteType@ProjectionModel@@SAPEBU12@PEBUType@2@@Z; ProjectionModel::ConcreteType::From(ProjectionModel::Type const *)
0x1801c59cb  mov     rsi, rax
0x1801c59ce  test    bl, bl
0x1801c59d0  jz      short loc_1801C59E8
0x1801c59d2  cmp     r14d, edi
0x1801c59d5  jbe     short loc_1801C59E8
0x1801c59d7  xor     r8d, r8d; unsigned __int16 *
0x1801c59da  mov     edx, 800A13F7h; int
0x1801c59df  mov     rcx, r15; struct Js::ScriptContext *
0x1801c59e2  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c59e8  mov     rcx, [rax+18h]
0x1801c59ec  mov     [rsp+130h+var_C8], rcx
0x1801c59f1  mov     eax, edi
0x1801c59f3  mov     r14d, edi
0x1801c59f6  imul    r14, rcx
0x1801c59fa  cmp     r14, rax
0x1801c59fd  jb      loc_1801C5F03
0x1801c5a03  xorps   xmm0, xmm0
0x1801c5a06  test    r14, r14
0x1801c5a09  js      short loc_1801C5A12
0x1801c5a0b  cvtsi2sd xmm0, r14
0x1801c5a10  jmp     short loc_1801C5A2A
0x1801c5a12  mov     rcx, r14
0x1801c5a15  shr     rcx, 1
0x1801c5a18  mov     rax, r14
0x1801c5a1b  and     eax, 1
0x1801c5a1e  or      rcx, rax
0x1801c5a21  cvtsi2sd xmm0, rcx
0x1801c5a26  addsd   xmm0, xmm0; double
0x1801c5a2a  mov     rdx, r15; struct Js::ScriptContext *
0x1801c5a2d  call    ?ToInt32Core@JavascriptMath@Js@@SAHNPEAVScriptContext@2@@Z; Js::JavascriptMath::ToInt32Core(double,Js::ScriptContext *)
0x1801c5a32  cmp     eax, edi
0x1801c5a34  jb      loc_1801C5F03
0x1801c5a3a  mov     rax, [rbp+3Fh+arg_20]
0x1801c5a3e  mov     [rax], edi
0x1801c5a40  mov     r12b, 1
0x1801c5a43  mov     r15, [rbp+3Fh+arg_28]
0x1801c5a47  cmp     dword ptr [r13+60h], 0
0x1801c5a4c  jnz     loc_1801C5D1A
0x1801c5a52  cmp     dword ptr [rsp+130h+var_D8], 0
0x1801c5a57  jz      short loc_1801C5A7A
0x1801c5a59  mov     rbx, [rbp+3Fh+arg_8]
0x1801c5a5d  mov     rdx, [rbx+30h]
0x1801c5a61  mov     rcx, [rdx+8]
0x1801c5a65  mov     eax, [rsi+4]
0x1801c5a68  cmp     [rcx+4], eax
0x1801c5a6b  jnz     loc_1801C5BC8
0x1801c5a71  mov     rax, [rdx+18h]
0x1801c5a75  xor     r12b, r12b
0x1801c5a78  jmp     short loc_1801C5AEA
0x1801c5a7a  xor     r12d, r12d
0x1801c5a7d  cmp     dword ptr [rsp+130h+var_D8+4], r12d
0x1801c5a82  jz      short loc_1801C5ABC
0x1801c5a84  cmp     dword ptr [rsi], 0Fh
0x1801c5a87  jnz     loc_1801C5BC8
0x1801c5a8d  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c5a90  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x1801c5a95  cmp     dword ptr [rax+28h], 0Dh
0x1801c5a99  jg      loc_1801C5BC8
0x1801c5a9f  mov     rbx, [rbp+3Fh+arg_8]
0x1801c5aa3  mov     rdx, rbx; void *
0x1801c5aa6  mov     rcx, rsi; struct ProjectionModel::ConcreteType *
0x1801c5aa9  call    ?NeedConversion@ArrayProjection@Projection@@SAHPEBUConcreteType@ProjectionModel@@PEAX@Z; Projection::ArrayProjection::NeedConversion(ProjectionModel::ConcreteType const *,void *)
0x1801c5aae  test    eax, eax
0x1801c5ab0  jnz     loc_1801C5BC8
0x1801c5ab6  mov     rax, [rbx+38h]
0x1801c5aba  jmp     short loc_1801C5AEA
0x1801c5abc  cmp     dword ptr [rsp+130h+var_D0], 1Fh
0x1801c5ac1  jnz     loc_1801C5BDB
0x1801c5ac7  cmp     dword ptr [rsi], 0Fh
0x1801c5aca  jnz     loc_1801C5BC8
0x1801c5ad0  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c5ad3  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x1801c5ad8  cmp     dword ptr [rax+28h], 5
0x1801c5adc  jnz     loc_1801C5BC8
0x1801c5ae2  mov     rbx, [rbp+3Fh+arg_8]
0x1801c5ae6  mov     rax, [rbx+20h]
0x1801c5aea  mov     [r15], rax
0x1801c5aed  cmp     [rbp+3Fh+arg_30], 0
0x1801c5af1  jz      short loc_1801C5B55
0x1801c5af3  mov     rbx, rax
0x1801c5af6  xor     r12d, r12d
0x1801c5af9  test    edi, edi
0x1801c5afb  jz      short loc_1801C5B34
0x1801c5afd  mov     r15, [rsp+130h+var_C8]
0x1801c5b02  mov     qword ptr [rsp+130h+var_108], r15
0x1801c5b07  mov     [rsp+130h+var_110], rbx
0x1801c5b0c  mov     r9, rsi
0x1801c5b0f  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x1801c5b16  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x1801c5b1d  mov     rcx, r13
0x1801c5b20  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x1801c5b25  add     rbx, r15
0x1801c5b28  inc     r12d
0x1801c5b2b  cmp     r12d, edi
0x1801c5b2e  jb      short loc_1801C5B02
0x1801c5b30  mov     r15, [rbp+3Fh+arg_28]
0x1801c5b34  mov     r8, r14; Size
0x1801c5b37  xor     edx, edx; Val
0x1801c5b39  mov     rcx, [r15]; void *
0x1801c5b3c  call    memset_0
0x1801c5b41  add     rsp, 0F8h
0x1801c5b48  pop     r15
0x1801c5b4a  pop     r14
0x1801c5b4c  pop     r13
0x1801c5b4e  pop     r12
0x1801c5b50  pop     rdi
0x1801c5b51  pop     rsi
0x1801c5b52  pop     rbx
0x1801c5b53  pop     rbp
0x1801c5b54  retn
0x1801c5b55  mov     ecx, [rsp+30h]
0x1801c5b59  cmp     ecx, edi
0x1801c5b5b  jnb     short loc_1801C5B41
0x1801c5b5d  mov     r14d, ecx
0x1801c5b60  mov     rbx, [rsp+130h+var_C8]
0x1801c5b65  imul    r14, rbx
0x1801c5b69  mov     qword ptr [rsp+130h+var_F0], r14
0x1801c5b6e  mov     r15, [r15]
0x1801c5b71  add     r15, r14
0x1801c5b74  mov     r14d, ecx
0x1801c5b77  mov     qword ptr [rsp+130h+var_108], rbx
0x1801c5b7c  mov     [rsp+130h+var_110], r15
0x1801c5b81  mov     r9, rsi
0x1801c5b84  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x1801c5b8b  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x1801c5b92  mov     rcx, r13
0x1801c5b95  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x1801c5b9a  add     r15, rbx
0x1801c5b9d  inc     r14d
0x1801c5ba0  cmp     r14d, edi
0x1801c5ba3  jb      short loc_1801C5B77
0x1801c5ba5  sub     edi, [rsp+30h]
0x1801c5ba9  mov     r8d, edi
0x1801c5bac  imul    r8, rbx; Size
0x1801c5bb0  mov     r15, [rbp+3Fh+arg_28]
0x1801c5bb4  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1801c5bb9  add     rcx, [r15]; void *
0x1801c5bbc  xor     edx, edx; Val
0x1801c5bbe  call    memset_0
0x1801c5bc3  jmp     loc_1801C5E51
0x1801c5bc8  xor     r8d, r8d; unsigned __int16 *
0x1801c5bcb  mov     edx, 800A000Dh; int
0x1801c5bd0  mov     rcx, [rsp+130h+var_E0]; struct Js::ScriptContext *
0x1801c5bd5  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c5bdb  cmp     [rsp+130h+var_F0], r12d
0x1801c5be0  jnz     loc_1801C5CE1
0x1801c5be6  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c5be9  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x1801c5bee  test    al, al
0x1801c5bf0  jnz     loc_1801C5CE1
0x1801c5bf6  mov     rax, [rsp+130h+var_E0]
0x1801c5bfb  mov     rax, [rax+8E8h]
0x1801c5c02  mov     qword ptr [rsp+130h+var_F0], rax
0x1801c5c07  lea     r8, ?AllocFinalized@Recycler@@QEAAPEAD_K@Z; Recycler::AllocFinalized(unsigned __int64)
0x1801c5c0e  mov     rdx, rax
0x1801c5c11  mov     ecx, 48h ; 'H'
0x1801c5c16  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x1801c5c1b  mov     rbx, rax
0x1801c5c1e  test    rax, rax
0x1801c5c21  jz      short loc_1801C5CA1
0x1801c5c23  mov     rax, [r13+10h]
0x1801c5c27  mov     r12, [rax+60h]
0x1801c5c2b  add     r12, 20D8h
0x1801c5c32  cmp     byte ptr [r12+10h], 0
0x1801c5c38  jnz     short loc_1801C5C66
0x1801c5c3a  mov     rax, [r12]
0x1801c5c3e  mov     rcx, r12
0x1801c5c41  mov     rax, [rax+8]
0x1801c5c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5c4a  mov     rcx, rax; lpLibFileName
0x1801c5c4d  xor     edx, edx; hFile
0x1801c5c4f  mov     r8d, 800h; dwFlags
0x1801c5c55  call    cs:__imp_LoadLibraryExW
0x1801c5c5b  mov     [r12+8], rax
0x1801c5c60  mov     byte ptr [r12+10h], 1
0x1801c5c66  lea     rax, ??_7FinalizableTypedArrayContents@Projection@@6B@; const Projection::FinalizableTypedArrayContents::`vftable'
0x1801c5c6d  mov     [rbx], rax
0x1801c5c70  mov     [rbx+8], rsi
0x1801c5c74  mov     [rbx+10h], edi
0x1801c5c77  mov     qword ptr [rbx+18h], 0
0x1801c5c7f  mov     rax, qword ptr [rsp+130h+var_F0]
0x1801c5c84  mov     [rbx+20h], rax
0x1801c5c88  mov     [rbx+28h], r12
0x1801c5c8c  mov     rax, [rsi+18h]
0x1801c5c90  mov     [rbx+30h], rax
0x1801c5c94  xor     r12d, r12d
0x1801c5c97  mov     [rbx+38h], r12
0x1801c5c9b  mov     [rbx+40h], r12d
0x1801c5c9f  jmp     short loc_1801C5CA4
0x1801c5ca1  mov     rbx, r12
0x1801c5ca4  mov     r8b, 1; bool
0x1801c5ca7  mov     rdx, rbx; void *
0x1801c5caa  mov     rcx, r13; this
0x1801c5cad  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x1801c5cb2  mov     rcx, r14; unsigned __int64
0x1801c5cb5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801c5cba  mov     rdi, rax
0x1801c5cbd  test    rax, rax
0x1801c5cc0  jz      loc_1801C5EFE
0x1801c5cc6  mov     r8, r14; Size
0x1801c5cc9  xor     edx, edx; Val
0x1801c5ccb  mov     rcx, rax; void *
0x1801c5cce  call    memset_0
0x1801c5cd3  mov     [rbx+18h], rdi
0x1801c5cd7  mov     rcx, rbx; this
0x1801c5cda  call    ?Initialize@FinalizableTypedArrayContents@Projection@@QEAAXXZ; Projection::FinalizableTypedArrayContents::Initialize(void)
0x1801c5cdf  jmp     short loc_1801C5D0D
0x1801c5ce1  lea     rax, ?AllocZero@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::AllocZero(unsigned __int64)
0x1801c5ce8  mov     qword ptr [rsp+130h+var_F0], rax
0x1801c5ced  mov     dword ptr [rsp+130h+var_E8], r12d
0x1801c5cf2  mov     eax, [rbp+3Fh+var_BC]
0x1801c5cf5  mov     dword ptr [rsp+130h+var_E8+4], eax
0x1801c5cf9  mov     r8, r14
  ... truncated ...
```
