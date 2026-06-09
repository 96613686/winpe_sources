# GenADTG::SaveResultDescriptor(CBidGenericBase const &)

- ea: `0x1800085ac`
- end: `0x18000899f`
- name: `?SaveResultDescriptor@GenADTG@@QEAAXAEBVCBidGenericBase@@@Z`
- size: `1011`
- prototype: `void __fastcall(GenADTG *__hidden this, const struct CBidGenericBase *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800091a4`

## callees

- `0x18000261c`
- `0x180002650`
- `0x18000266c`
- `0x1800027c0`
- `0x180003abc`
- `0x1800041f8`
- `0x1800063fc`
- `0x180006604`
- `0x180008190`
- `0x1800085ac`
- `0x180009490`
- `0x18001a6c8`
- `0x18002a1b4`
- `0x18002cd54`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GenADTG::SaveResultDescriptor(GenADTG *this, const struct CBidGenericBase *a2)
{
  int v4; // eax
  int v5; // esi
  unsigned int v6; // edx
  int ADCPropertiesNoError; // eax
  int v8; // r15d
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned int *v15; // r14
  GenADTG *v16; // rcx
  unsigned __int16 v17; // ax
  __int16 v18; // r12
  unsigned __int16 v19; // r11
  unsigned __int16 v20; // r10
  unsigned __int16 v21; // r13
  unsigned __int16 v22; // dx
  __int16 v23; // r10
  __int16 v24; // r11
  __int64 v25; // rax
  __int16 v26; // cx
  tagDBPROPIDSET v27; // [rsp+20h] [rbp-40h] BYREF
  int *v28; // [rsp+40h] [rbp-20h]
  int v29; // [rsp+48h] [rbp-18h]
  GUID v30; // [rsp+4Ch] [rbp-14h]
  unsigned __int8 v31; // [rsp+60h] [rbp+0h] BYREF
  unsigned __int8 v32; // [rsp+61h] [rbp+1h] BYREF
  unsigned __int8 v33; // [rsp+62h] [rbp+2h] BYREF
  unsigned __int8 v34; // [rsp+63h] [rbp+3h] BYREF
  _WORD v35[4]; // [rsp+64h] [rbp+4h] BYREF
  unsigned __int8 v36[4]; // [rsp+6Ch] [rbp+Ch] BYREF
  unsigned __int8 v37[4]; // [rsp+70h] [rbp+10h] BYREF
  unsigned __int16 Type; // [rsp+74h] [rbp+14h]
  unsigned __int8 v39[4]; // [rsp+78h] [rbp+18h] BYREF
  unsigned __int8 v40[4]; // [rsp+7Ch] [rbp+1Ch] BYREF
  __int64 v41; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v42; // [rsp+88h] [rbp+28h] BYREF
  struct tagDBPROPSET *v43; // [rsp+90h] [rbp+30h] BYREF
  struct IRowsetInfo *v44; // [rsp+98h] [rbp+38h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+40h] BYREF
  tagDBPROPIDSET *v46; // [rsp+A8h] [rbp+48h]
  __int64 v47; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v48; // [rsp+B8h] [rbp+58h] BYREF

  v32 = 3;
  strcpy((char *)v35, "!");
  v31 = 0;
  v33 = 0;
  v34 = 0;
  v35[2] = 0;
  *(_WORD *)v39 = 0;
  *(_DWORD *)v40 = -1;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  GenADTG::SaveToBuffer(this, &v32, 1u);
  v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IRowsetInfo **))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetInfo,
         &v44);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048590[0] )
        bidTraceW(off_1800481C0[0], 1072128, off_180048590[0], (unsigned int)v4, 1047);
    }
    ThrowHR(v5);
  }
  v48 = 0;
  OnNullThrowOOM(&v27);
  v27.rgPropertyIDs = (DBPROPID *)qword_180036868;
  v27.cPropertyIDs = 7;
  v27.guidPropertySet = DBPROPSET_ADC;
  v28 = &dword_180036884;
  v29 = 1;
  v30 = DBPROPSET_ROWSET;
  ADCPropertiesNoError = GetADCPropertiesNoError(v44, v6, &v27, &v42, &v43, a2);
  v8 = ADCPropertiesNoError;
  LODWORD(v41) = ADCPropertiesNoError;
  if ( ADCPropertiesNoError >= 0 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( ADCPropertiesNoError != -2147217887 )
    {
      v42 = 0;
      v43 = 0;
    }
  }
  v47 = 0;
  v10 = 4LL * v9;
  v11 = v10 + 15;
  if ( v10 + 15 < v10 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  v15 = (unsigned int *)&v27;
  v46 = &v27;
  OnNullThrowOOM(&v27);
  if ( v8 >= 0 )
  {
    v17 = GenADTG::DeterminePropLength(v16, v9, v43, (unsigned int *)&v27);
    v35[0] += v17;
  }
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)v35, 2u);
  GenADTG::SaveToBuffer(this, &qword_180036828, 0x10u);
  v31 = 0;
  GenADTG::SaveToBuffer(this, &v31, 1u);
  GenADTG::SaveToBuffer(this, &v33, 1u);
  GenADTG::SaveToBuffer(this, &v34, 1u);
  v18 = *((_WORD *)this + 65);
  *(_WORD *)v36 = v18;
  v19 = *((_WORD *)this + 64);
  *(_WORD *)v37 = v19;
  if ( *((_DWORD *)this + 50) )
  {
    v20 = 0;
    v21 = v19;
    if ( v19 )
    {
      do
      {
        Type = CMetaData::mdGetType((GenADTG *)((char *)this + 128), v20);
        if ( (CMetaData::mdGetFlags((GenADTG *)((char *)this + 128), v22) & 0x2000) != 0 || Type == 136 )
        {
          *(_WORD *)v36 = --v18;
          *(_WORD *)v37 = v24 - 1;
        }
        v20 = v23 + 1;
      }
      while ( v20 < v21 );
      v15 = (unsigned int *)v46;
      v8 = v41;
    }
  }
  GenADTG::SaveToBuffer(this, v36, 2u);
  GenADTG::SaveToBuffer(this, v37, 2u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)this + 132, 2u);
  v25 = *((_QWORD *)this + 22);
  if ( v25 )
  {
    v26 = v35[2];
    do
    {
      v35[2] = ++v26;
      v25 = *(_QWORD *)(v25 + 48);
    }
    while ( v25 );
  }
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v35[2], 2u);
  GenADTG::SaveToBuffer(this, v39, 2u);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetScroll,
         &v45) >= 0 )
  {
    v41 = -1;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v45 + 96LL))(
      v45,
      0,
      0,
      0,
      0,
      &v41);
    *(_DWORD *)v40 = DownsizeToULONGThrow<unsigned __int64>(v41);
  }
  GenADTG::SaveToBuffer(this, v40, 4u);
  if ( v8 >= 0 )
    GenADTG::SaveProperties(this, v9, v43, v15);
  CAutoP<_GUID>::~CAutoP<_GUID>(&v47);
  CAutoP<_GUID>::~CAutoP<_GUID>(&v48);
  DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v42);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v44);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v45);
}

```

## disassembly

```asm
0x1800085ac  push    rbp
0x1800085ae  push    rbx
0x1800085af  push    rsi
0x1800085b0  push    rdi
0x1800085b1  push    r12
0x1800085b3  push    r13
0x1800085b5  push    r14
0x1800085b7  push    r15
0x1800085b9  sub     rsp, 0B8h
0x1800085c0  lea     rbp, [rsp+40h]
0x1800085c5  mov     rax, cs:__security_cookie
0x1800085cc  xor     rax, rbp
0x1800085cf  mov     [rbp+0B0h+var_50], rax
0x1800085d3  mov     r14, rdx
0x1800085d6  mov     rdi, rcx
0x1800085d9  mov     [rbp+0B0h+var_AF], 3
0x1800085dd  mov     eax, 21h ; '!'
0x1800085e2  mov     word ptr [rbp+0B0h+var_AC], ax
0x1800085e6  xor     r13d, r13d
0x1800085e9  mov     [rbp+0B0h+var_B0], r13b
0x1800085ed  mov     [rbp+0B0h+var_AE], r13b
0x1800085f1  mov     [rbp+0B0h+var_AD], r13b
0x1800085f5  mov     word ptr [rbp+0B0h+var_AC+4], r13w
0x1800085fa  mov     word ptr [rbp+0B0h+var_98], r13w
0x1800085ff  mov     dword ptr [rbp+0B0h+var_94], 0FFFFFFFFh
0x180008606  mov     [rbp+0B0h+var_70], r13
0x18000860a  mov     [rbp+0B0h+var_78], r13
0x18000860e  mov     [rbp+0B0h+var_88], r13d
0x180008612  mov     [rbp+0B0h+var_80], r13
0x180008616  lea     r12d, [rax-20h]
0x18000861a  mov     r8d, r12d; unsigned int
0x18000861d  lea     rdx, [rbp+0B0h+var_AF]; unsigned __int8 *
0x180008621  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008626  mov     rcx, [rdi+18h]
0x18000862a  mov     rax, [rcx]
0x18000862d  lea     r8, [rbp+0B0h+var_78]
0x180008631  lea     rdx, IID_IRowsetInfo
0x180008638  mov     rax, [rax]
0x18000863b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008640  mov     esi, eax
0x180008642  test    eax, eax
0x180008644  jns     short loc_180008689
0x180008646  lea     ebx, [r13+2]
0x18000864a  test    byte ptr cs:_bidGblFlags, bl
0x180008650  jz      short loc_180008681
0x180008652  mov     rcx, cs:off_180048590; "<GenADTG::SaveResultDescriptor|ADO|ERR>"...
0x180008659  test    rcx, rcx
0x18000865c  jz      short loc_180008681
0x18000865e  mov     dword ptr [rsp+0F0h+var_D0], 417h
0x180008666  mov     r9d, eax
0x180008669  mov     r8, cs:off_180048590; "<GenADTG::SaveResultDescriptor|ADO|ERR>"...
0x180008670  mov     edx, 105C00h
0x180008675  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000867c  call    _bidTraceW
0x180008681  mov     ecx, esi; int
0x180008683  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180008689  mov     [rbp+0B0h+var_58], r13
0x18000868d  mov     eax, dword ptr [rsp+0F0h+var_F0.rgPropertyIDs]
0x180008690  sub     rsp, 40h
0x180008694  lea     rbx, [rsp+130h+var_F0]
0x180008699  mov     eax, [rbx]
0x18000869b  mov     rcx, rbx; void *
0x18000869e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800086a3  lea     rax, qword_180036868
0x1800086aa  mov     [rbx], rax
0x1800086ad  mov     dword ptr [rbx+8], 7
0x1800086b4  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x1800086bb  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800086c0  lea     rax, dword_180036884
0x1800086c7  mov     [rbx+20h], rax
0x1800086cb  mov     [rbx+28h], r12d
0x1800086cf  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800086d6  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x1800086db  mov     [rsp+130h+var_108], r14; struct CBidGenericBase *
0x1800086e0  lea     rax, [rbp+0B0h+var_80]
0x1800086e4  mov     [rsp+130h+var_110], rax; struct tagDBPROPSET **
0x1800086e9  lea     r9, [rbp+0B0h+var_88]; unsigned int *
0x1800086ed  mov     r8, rbx; struct tagDBPROPIDSET *
0x1800086f0  mov     rcx, [rbp+0B0h+var_78]; struct IRowsetInfo *
0x1800086f4  call    ?GetADCPropertiesNoError@@YAJPEAUIRowsetInfo@@KQEAUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; GetADCPropertiesNoError(IRowsetInfo *,ulong,tagDBPROPIDSET * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x1800086f9  mov     r15d, eax
0x1800086fc  mov     dword ptr [rbp+0B0h+var_90], eax
0x1800086ff  test    eax, eax
0x180008701  jns     short loc_180008717
0x180008703  mov     esi, r13d
0x180008706  cmp     eax, 80040E21h
0x18000870b  jz      short loc_18000871A
0x18000870d  mov     [rbp+0B0h+var_88], r13d
0x180008711  mov     [rbp+0B0h+var_80], r13
0x180008715  jmp     short loc_18000871A
0x180008717  mov     esi, r12d
0x18000871a  mov     [rbp+0B0h+var_60], r13
0x18000871e  mov     eax, esi
0x180008720  shl     rax, 2
0x180008724  lea     rcx, [rax+0Fh]
0x180008728  cmp     rcx, rax
0x18000872b  ja      short loc_180008737
0x18000872d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008737  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000873b  mov     rax, rcx
0x18000873e  call    _alloca_probe
0x180008743  sub     rsp, rcx
0x180008746  lea     r14, [rsp+130h+var_F0]
0x18000874b  mov     [rbp+0B0h+var_68], r14
0x18000874f  mov     rcx, r14; void *
0x180008752  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180008757  test    r15d, r15d
0x18000875a  js      short loc_18000876E
0x18000875c  mov     r9, r14; unsigned int *
0x18000875f  mov     r8, [rbp+0B0h+var_80]; struct tagDBPROPSET *
0x180008763  mov     edx, esi; unsigned int
0x180008765  call    ?DeterminePropLength@GenADTG@@AEAAGKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::DeterminePropLength(ulong,tagDBPROPSET *,ulong *)
0x18000876a  add     word ptr [rbp+0B0h+var_AC], ax
0x18000876e  mov     ebx, 2
0x180008773  mov     r8d, ebx; unsigned int
0x180008776  lea     rdx, [rbp+0B0h+var_AC]; unsigned __int8 *
0x18000877a  mov     rcx, rdi; this
0x18000877d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008782  lea     r8d, [rbx+0Eh]; unsigned int
0x180008786  lea     rdx, qword_180036828; unsigned __int8 *
0x18000878d  mov     rcx, rdi; this
0x180008790  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008795  mov     [rbp+0B0h+var_B0], r13b
0x180008799  mov     r8d, r12d; unsigned int
0x18000879c  lea     rdx, [rbp+0B0h+var_B0]; unsigned __int8 *
0x1800087a0  mov     rcx, rdi; this
0x1800087a3  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800087a8  mov     r8d, r12d; unsigned int
0x1800087ab  lea     rdx, [rbp+0B0h+var_AE]; unsigned __int8 *
0x1800087af  mov     rcx, rdi; this
0x1800087b2  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800087b7  mov     r8d, r12d; unsigned int
0x1800087ba  lea     rdx, [rbp+0B0h+var_AD]; unsigned __int8 *
0x1800087be  mov     rcx, rdi; this
0x1800087c1  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800087c6  movzx   r12d, word ptr [rdi+82h]
0x1800087ce  mov     word ptr [rbp+0B0h+var_A4], r12w
0x1800087d3  movzx   r11d, word ptr [rdi+80h]
0x1800087db  mov     word ptr [rbp+0B0h+var_A0], r11w
0x1800087e0  cmp     [rdi+0C8h], r13d
0x1800087e7  jz      short loc_18000885D
0x1800087e9  mov     r10d, r13d
0x1800087ec  movzx   r13d, r11w
0x1800087f0  xor     eax, eax
0x1800087f2  cmp     ax, r11w
0x1800087f6  jnb     short loc_18000885A
0x1800087f8  mov     ebx, 0FFFFh
0x1800087fd  lea     r15, [rdi+80h]
0x180008804  lea     r14d, [rax+1]
0x180008808  movzx   edx, r10w; unsigned __int16
0x18000880c  mov     rcx, r15; this
0x18000880f  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180008814  mov     [rbp+0B0h+var_9C], ax
0x180008818  mov     rcx, r15; this
0x18000881b  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180008820  bt      eax, 0Dh
0x180008824  jb      short loc_180008831
0x180008826  mov     eax, 88h
0x18000882b  cmp     [rbp+0B0h+var_9C], ax
0x18000882f  jnz     short loc_180008843
0x180008831  add     r12w, bx
0x180008835  mov     word ptr [rbp+0B0h+var_A4], r12w
0x18000883a  add     r11w, bx
0x18000883e  mov     word ptr [rbp+0B0h+var_A0], r11w
0x180008843  add     r10w, r14w
0x180008847  cmp     r10w, r13w
0x18000884b  jb      short loc_180008808
0x18000884d  mov     ebx, 2
0x180008852  mov     r14, [rbp+0B0h+var_68]
0x180008856  mov     r15d, dword ptr [rbp+0B0h+var_90]
0x18000885a  xor     r13d, r13d
0x18000885d  mov     r8d, ebx; unsigned int
0x180008860  lea     rdx, [rbp+0B0h+var_A4]; unsigned __int8 *
0x180008864  mov     rcx, rdi; this
0x180008867  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000886c  mov     r8d, ebx; unsigned int
0x18000886f  lea     rdx, [rbp+0B0h+var_A0]; unsigned __int8 *
0x180008873  mov     rcx, rdi; this
0x180008876  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000887b  lea     rdx, [rdi+84h]; unsigned __int8 *
0x180008882  mov     r8d, ebx; unsigned int
0x180008885  mov     rcx, rdi; this
0x180008888  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000888d  mov     rax, [rdi+0B0h]
0x180008894  test    rax, rax
0x180008897  jz      short loc_1800088B2
0x180008899  movzx   ecx, word ptr [rbp+0B0h+var_AC+4]
0x18000889d  mov     edx, 1
0x1800088a2  add     cx, dx
0x1800088a5  mov     word ptr [rbp+0B0h+var_AC+4], cx
0x1800088a9  mov     rax, [rax+30h]
0x1800088ad  test    rax, rax
0x1800088b0  jnz     short loc_1800088A2
0x1800088b2  mov     r8d, ebx; unsigned int
0x1800088b5  lea     rdx, [rbp+0B0h+var_AC+4]; unsigned __int8 *
0x1800088b9  mov     rcx, rdi; this
0x1800088bc  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800088c1  mov     r8d, ebx; unsigned int
0x1800088c4  lea     rdx, [rbp+0B0h+var_98]; unsigned __int8 *
0x1800088c8  mov     rcx, rdi; this
0x1800088cb  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800088d0  mov     rcx, [rdi+18h]
0x1800088d4  mov     rax, [rcx]
0x1800088d7  lea     r8, [rbp+0B0h+var_70]
0x1800088db  lea     rdx, IID_IRowsetScroll
0x1800088e2  mov     rax, [rax]
0x1800088e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ea  test    eax, eax
0x1800088ec  js      short loc_180008928
0x1800088ee  mov     [rbp+0B0h+var_90], 0FFFFFFFFFFFFFFFFh
0x1800088f6  mov     rcx, [rbp+0B0h+var_70]
0x1800088fa  mov     rax, [rcx]
0x1800088fd  lea     rdx, [rbp+0B0h+var_90]
0x180008901  mov     [rsp+130h+var_108], rdx
0x180008906  mov     [rsp+130h+var_110], r13
0x18000890b  xor     r9d, r9d
0x18000890e  xor     r8d, r8d
0x180008911  xor     edx, edx
0x180008913  mov     rax, [rax+60h]
0x180008917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891c  mov     rcx, [rbp+0B0h+var_90]
0x180008920  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180008925  mov     dword ptr [rbp+0B0h+var_94], eax
0x180008928  mov     r8d, 4; unsigned int
0x18000892e  lea     rdx, [rbp+0B0h+var_94]; unsigned __int8 *
0x180008932  mov     rcx, rdi; this
0x180008935  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000893a  test    r15d, r15d
0x18000893d  js      short loc_180008951
0x18000893f  mov     r9, r14; unsigned int *
0x180008942  mov     r8, [rbp+0B0h+var_80]; struct tagDBPROPSET *
0x180008946  mov     edx, esi; unsigned int
0x180008948  mov     rcx, rdi; this
0x18000894b  call    ?SaveProperties@GenADTG@@AEAAXKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::SaveProperties(ulong,tagDBPROPSET *,ulong *)
0x180008950  nop
0x180008951  lea     rcx, [rbp+0B0h+var_60]
0x180008955  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x18000895a  nop
0x18000895b  lea     rcx, [rbp+0B0h+var_58]
0x18000895f  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180008964  nop
0x180008965  lea     rcx, [rbp+0B0h+var_88]; this
0x180008969  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18000896e  nop
0x18000896f  lea     rcx, [rbp+0B0h+var_78]
0x180008973  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008978  nop
0x180008979  lea     rcx, [rbp+0B0h+var_70]
0x18000897d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008982  mov     rcx, [rbp+0B0h+var_50]
0x180008986  xor     rcx, rbp; StackCookie
0x180008989  call    __security_check_cookie
0x18000898e  lea     rsp, [rbp+78h]
0x180008992  pop     r15
0x180008994  pop     r14
0x180008996  pop     r13
0x180008998  pop     r12
0x18000899a  pop     rdi
0x18000899b  pop     rsi
0x18000899c  pop     rbx
0x18000899d  pop     rbp
0x18000899e  retn
```
