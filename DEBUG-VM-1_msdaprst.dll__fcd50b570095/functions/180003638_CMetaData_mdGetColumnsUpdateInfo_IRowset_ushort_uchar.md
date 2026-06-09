# CMetaData::mdGetColumnsUpdateInfo(IRowset *,ushort * *,uchar * *)

- ea: `0x180003638`
- end: `0x180003ab3`
- name: `?mdGetColumnsUpdateInfo@CMetaData@@AEAAHPEAUIRowset@@PEAPEAGPEAPEAE@Z`
- size: `1147`
- prototype: `__int64 __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180002b1c`

## callees

- `0x180001d94`
- `0x18000261c`
- `0x18000266c`
- `0x1800027c0`
- `0x180002ec0`
- `0x180003638`
- `0x180003af4`
- `0x18000443c`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e02a`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800036a5`
- `ole32!CoTaskMemFree` at `0x1800036b1`
- `ole32!CoTaskMemFree` at `0x1800036bd`
- `ole32!CoTaskMemFree` at `0x180003a74`
- `ole32!CoTaskMemFree` at `0x180003a80`
- `ole32!CoTaskMemFree` at `0x180003a8c`
- `ole32!CoTaskMemFree` at `0x1800036a5`
- `ole32!CoTaskMemFree` at `0x1800036b1`
- `ole32!CoTaskMemFree` at `0x1800036bd`
- `ole32!CoTaskMemFree` at `0x180003a74`
- `ole32!CoTaskMemFree` at `0x180003a80`
- `ole32!CoTaskMemFree` at `0x180003a8c`
- `ole32!CoTaskMemAlloc` at `0x180003776`
- `ole32!CoTaskMemAlloc` at `0x180003776`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMetaData::mdGetColumnsUpdateInfo(
        CMetaData *this,
        struct IRowset *a2,
        unsigned __int16 **a3,
        unsigned __int8 **a4)
{
  void *v6; // rbx
  int v7; // eax
  unsigned int v9; // r15d
  int v10; // eax
  int v11; // esi
  CMetaData *v12; // rcx
  unsigned int HiddenCount; // eax
  void *v14; // rcx
  unsigned __int128 v15; // rax
  unsigned __int8 *v16; // rax
  unsigned __int16 v17; // r12
  unsigned __int16 v18; // si
  __int64 v19; // r14
  __int64 v20; // r10
  unsigned __int16 *v21; // r8
  __int16 v22; // r13
  unsigned __int16 *v23; // rax
  unsigned __int8 *v24; // rax
  LPVOID v25; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-B8h] BYREF
  int v28; // [rsp+48h] [rbp-B0h]
  LPVOID v29; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A0h] BYREF
  int v31; // [rsp+60h] [rbp-98h] BYREF
  struct tagDBCOLUMNINFO v32; // [rsp+70h] [rbp-88h] BYREF
  int v33; // [rsp+108h] [rbp+10h] BYREF
  unsigned __int16 **v34; // [rsp+110h] [rbp+18h]
  unsigned __int8 **v35; // [rsp+118h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  try
  {
    v6 = 0;
    v28 = 0;
    v30 = 0;
    v26 = 0;
    v22 = 0;
    LOWORD(v33) = 0;
    v25 = 0;
    v29 = 0;
    pv = 0;
    v7 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsUpdateInfo,
           &v30);
  }
  catch ( long v31 )
  {
    v33 = v31;
    v9 = v28;
    v6 = pv;
    goto LABEL_26;
  }
  if ( v7 )
  {
    CoTaskMemFree(pv);
    CoTaskMemFree(v29);
    CoTaskMemFree(v25);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
    return 0;
  }
  else
  {
    v9 = 1;
    v28 = 1;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *, LPVOID *))(*(_QWORD *)v30 + 24LL))(
            v30,
            &v26,
            &v25,
            &v29,
            &pv);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048488[0] )
          bidTraceW(off_1800481B8[0], 338944, off_180048488[0], (unsigned int)v10, 331);
      }
      ThrowHR(v11);
    }
    DownsizeToULONGThrow<unsigned __int64>(v26);
    HiddenCount = CMetaData::mdGetHiddenCount(v12, a2);
    v26 += HiddenCount;
    v14 = CoTaskMemAlloc((unsigned int)(168 * v26));
    *((_QWORD *)this + 1) = v14;
    if ( !v14 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048480[0] )
        bidTraceW(off_1800481B8[0], 348160, off_180048480[0], 2147942414LL, 340);
      ThrowHR(-2147024882);
    }
    memset_0(v14, 0, (unsigned int)(168 * v26));
    if ( pv )
    {
      v15 = (unsigned __int64)(int)v26 * (unsigned __int128)4uLL;
      if ( !is_mul_ok((int)v26, 4u) )
        LODWORD(v15) = -1;
      v16 = MMMAlloc(v15, DWORD2(v15));
      *((_QWORD *)this + 5) = v16;
      OnNullThrowOOM(v16);
      memset_0(*((void **)this + 5), 0, (unsigned int)(4 * v26));
    }
    v17 = 0;
    v18 = 0;
    while ( v17 < v26 )
    {
      v19 = 168LL * v17;
      v32 = *(struct tagDBCOLUMNINFO *)((char *)v25 + v19);
      if ( (unsigned int)CMetaData::mdGetColInfo(this, &v32, v18, (unsigned __int16 *)&v33) )
      {
        v20 = 168LL * v18;
        *(_WORD *)(v20 + *((_QWORD *)this + 1) + 112) = *(_WORD *)((char *)v25 + v19 + 112);
        *(_WORD *)(v20 + *((_QWORD *)this + 1) + 114) = *(_WORD *)((char *)v25 + v19 + 114);
        *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 120) = *(_QWORD *)((char *)v25 + v19 + 120);
        *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 128) = *(_QWORD *)((char *)v25 + v19 + 128);
        *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 160) = *(_DWORD *)((char *)v25 + v19 + 160);
        if ( pv )
        {
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 80) = *(_QWORD *)((char *)v25 + v19 + 80);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 88) = *(_QWORD *)((char *)v25 + v19 + 88);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 96) = *(_QWORD *)((char *)v25 + v19 + 96);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 104) = *(_QWORD *)((char *)v25 + v19 + 104);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 136) = *(_QWORD *)((char *)v25 + v19 + 136);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 144) = *(_QWORD *)((char *)v25 + v19 + 144);
          v21 = (unsigned __int16 *)(*((_QWORD *)this + 5) + 4LL * v18);
          CMetaData::mdReadTableData(this, (struct DBCOLUMNUPDATEINFO *)(v20 + *((_QWORD *)this + 1)), v21, v21 + 1);
        }
        ++v18;
      }
      ++v17;
      v22 = v33;
    }
    *(_WORD *)this = v18;
    *((_WORD *)this + 1) = v18 - v22;
    v23 = (unsigned __int16 *)v29;
    v29 = 0;
    *v34 = v23;
    v24 = (unsigned __int8 *)pv;
    pv = 0;
    *v35 = v24;
    *((_WORD *)this + 2) = 0;
LABEL_26:
    CoTaskMemFree(v6);
    CoTaskMemFree(v29);
    CoTaskMemFree(v25);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
    return v9;
  }
}

```

## disassembly

```asm
0x180003638  mov     rax, rsp
0x18000363b  mov     [rax+20h], r9
0x18000363f  mov     [rax+18h], r8
0x180003643  push    rbx
0x180003644  push    rsi
0x180003645  push    rdi
0x180003646  push    r12
0x180003648  push    r13
0x18000364a  push    r14
0x18000364c  push    r15
0x18000364e  sub     rsp, 0C0h
0x180003655  mov     r14, rdx
0x180003658  mov     rdi, rcx
0x18000365b  xor     ebx, ebx
0x18000365d  mov     [rsp+0F8h+var_B0], ebx
0x180003661  mov     [rsp+0F8h+var_A0], rbx
0x180003666  mov     [rsp+0F8h+var_C0], rbx
0x18000366b  movzx   r13d, bx
0x18000366f  mov     [rax+10h], bx
0x180003673  mov     [rsp+0F8h+var_C8], rbx
0x180003678  mov     [rsp+0F8h+var_A8], rbx
0x18000367d  mov     [rsp+0F8h+pv], rbx
0x180003682  mov     rax, [rdx]
0x180003685  lea     r8, [rsp+0F8h+var_A0]
0x18000368a  lea     rdx, IID_IColumnsUpdateInfo
0x180003691  mov     rcx, r14
0x180003694  mov     rax, [rax]
0x180003697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369c  test    eax, eax
0x18000369e  jz      short loc_1800036D5
0x1800036a0  mov     rcx, [rsp+0F8h+pv]; pv
0x1800036a5  call    cs:__imp_CoTaskMemFree
0x1800036ab  nop
0x1800036ac  mov     rcx, [rsp+0F8h+var_A8]; pv
0x1800036b1  call    cs:__imp_CoTaskMemFree
0x1800036b7  nop
0x1800036b8  mov     rcx, [rsp+0F8h+var_C8]; pv
0x1800036bd  call    cs:__imp_CoTaskMemFree
0x1800036c3  nop
0x1800036c4  lea     rcx, [rsp+0F8h+var_A0]
0x1800036c9  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800036ce  xor     eax, eax
0x1800036d0  jmp     loc_180003AA0
0x1800036d5  mov     r15d, 1
0x1800036db  mov     [rsp+0F8h+var_B0], r15d
0x1800036e0  mov     rcx, [rsp+0F8h+var_A0]
0x1800036e5  mov     rax, [rcx]
0x1800036e8  lea     rdx, [rsp+0F8h+pv]
0x1800036ed  mov     [rsp+0F8h+var_D8], rdx
0x1800036f2  lea     r9, [rsp+0F8h+var_A8]
0x1800036f7  lea     r8, [rsp+0F8h+var_C8]
0x1800036fc  lea     rdx, [rsp+0F8h+var_C0]
0x180003701  mov     rax, [rax+18h]
0x180003705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370a  mov     esi, eax
0x18000370c  test    eax, eax
0x18000370e  jns     short loc_18000374F
0x180003710  test    byte ptr cs:_bidGblFlags, 2
0x180003717  jz      short loc_180003748
0x180003719  mov     rcx, cs:off_180048488; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003720  test    rcx, rcx
0x180003723  jz      short loc_180003748
0x180003725  mov     dword ptr [rsp+0F8h+var_D8], 14Bh
0x18000372d  mov     r9d, eax
0x180003730  mov     r8, cs:off_180048488; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003737  mov     edx, 52C00h
0x18000373c  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003743  call    _bidTraceW
0x180003748  mov     ecx, esi; int
0x18000374a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000374f  mov     rcx, [rsp+0F8h+var_C0]
0x180003754  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180003759  mov     rdx, r14; struct IRowset *
0x18000375c  call    ?mdGetHiddenCount@CMetaData@@AEAAKPEAUIRowset@@@Z; CMetaData::mdGetHiddenCount(IRowset *)
0x180003761  mov     eax, eax
0x180003763  mov     rcx, [rsp+0F8h+var_C0]
0x180003768  add     rcx, rax
0x18000376b  mov     [rsp+0F8h+var_C0], rcx
0x180003770  imul    ecx, 0A8h; cb
0x180003776  call    cs:__imp_CoTaskMemAlloc
0x18000377c  mov     rcx, rax; void *
0x18000377f  mov     [rdi+8], rax
0x180003783  test    rax, rax
0x180003786  jnz     short loc_1800037CD
0x180003788  test    byte ptr cs:_bidGblFlags, 2
0x18000378f  jz      short loc_1800037C3
0x180003791  mov     rax, cs:off_180048480; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003798  test    rax, rax
0x18000379b  jz      short loc_1800037C3
0x18000379d  mov     dword ptr [rsp+0F8h+var_D8], 154h
0x1800037a5  mov     r9d, 8007000Eh
0x1800037ab  mov     r8, cs:off_180048480; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x1800037b2  mov     edx, 55000h
0x1800037b7  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800037be  call    _bidTraceW
0x1800037c3  mov     ecx, 8007000Eh; int
0x1800037c8  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800037cd  imul    r8d, dword ptr [rsp+0F8h+var_C0], 0A8h; Size
0x1800037d6  xor     edx, edx; Val
0x1800037d8  call    memset_0
0x1800037dd  cmp     [rsp+0F8h+pv], rbx
0x1800037e2  jz      short loc_180003823
0x1800037e4  movsxd  rcx, dword ptr [rsp+0F8h+var_C0]
0x1800037e9  mov     eax, 4
0x1800037ee  mul     rcx
0x1800037f1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800037f8  cmovb   rax, rcx
0x1800037fc  mov     ecx, eax; unsigned int
0x1800037fe  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180003803  mov     [rdi+28h], rax
0x180003807  mov     rcx, rax; void *
0x18000380a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000380f  mov     r8d, dword ptr [rsp+0F8h+var_C0]
0x180003814  shl     r8d, 2; Size
0x180003818  xor     edx, edx; Val
0x18000381a  mov     rcx, [rdi+28h]; void *
0x18000381e  call    memset_0
0x180003823  movzx   r12d, bx
0x180003827  movzx   esi, bx
0x18000382a  movzx   eax, r12w
0x18000382e  cmp     rax, [rsp+0F8h+var_C0]
0x180003833  jnb     loc_1800039DC
0x180003839  imul    r14, rax, 0A8h
0x180003840  mov     rax, [rsp+0F8h+var_C8]
0x180003845  movups  xmm0, xmmword ptr [r14+rax]
0x18000384a  movaps  xmmword ptr [rsp+0F8h+var_88.pwszName], xmm0
0x18000384f  movups  xmm1, xmmword ptr [r14+rax+10h]
0x180003855  movaps  xmmword ptr [rsp+0F8h+var_88.iOrdinal], xmm1
0x18000385d  movups  xmm0, xmmword ptr [r14+rax+20h]
0x180003863  movaps  xmmword ptr [rsp+0F8h+var_88.ulColumnSize], xmm0
0x18000386b  movups  xmm1, xmmword ptr [r14+rax+30h]
0x180003871  movaps  xmmword ptr [rsp+0F8h+var_88.columnid.uGuid], xmm1
0x180003879  movups  xmm0, xmmword ptr [r14+rax+40h]
0x18000387f  movaps  xmmword ptr [rsp+0F8h+var_88.columnid.eKind], xmm0
0x180003887  lea     r9, [rsp+0F8h+arg_8]; unsigned __int16 *
0x18000388f  movzx   r8d, si; unsigned __int16
0x180003893  lea     rdx, [rsp+0F8h+var_88]; struct tagDBCOLUMNINFO
0x180003898  mov     rcx, rdi; this
0x18000389b  call    ?mdGetColInfo@CMetaData@@AEAAHUtagDBCOLUMNINFO@@GPEAG@Z; CMetaData::mdGetColInfo(tagDBCOLUMNINFO,ushort,ushort *)
0x1800038a0  test    eax, eax
0x1800038a2  jz      loc_1800039CA
0x1800038a8  movzx   r8d, si
0x1800038ac  imul    r10, r8, 0A8h
0x1800038b3  mov     rdx, [rdi+8]
0x1800038b7  mov     rax, [rsp+0F8h+var_C8]
0x1800038bc  movzx   ecx, word ptr [r14+rax+70h]
0x1800038c2  mov     [r10+rdx+70h], cx
0x1800038c8  mov     rdx, [rdi+8]
0x1800038cc  mov     rax, [rsp+0F8h+var_C8]
0x1800038d1  movzx   ecx, word ptr [r14+rax+72h]
0x1800038d7  mov     [r10+rdx+72h], cx
0x1800038dd  mov     rdx, [rdi+8]
0x1800038e1  mov     rax, [rsp+0F8h+var_C8]
0x1800038e6  mov     rcx, [r14+rax+78h]
0x1800038eb  mov     [r10+rdx+78h], rcx
0x1800038f0  mov     rdx, [rdi+8]
0x1800038f4  mov     rax, [rsp+0F8h+var_C8]
0x1800038f9  mov     rcx, [r14+rax+80h]
0x180003901  mov     [r10+rdx+80h], rcx
0x180003909  mov     rdx, [rdi+8]
0x18000390d  mov     rax, [rsp+0F8h+var_C8]
0x180003912  mov     ecx, [r14+rax+0A0h]
0x18000391a  mov     [r10+rdx+0A0h], ecx
0x180003922  cmp     [rsp+0F8h+pv], rbx
0x180003927  jz      loc_1800039C6
0x18000392d  mov     rdx, [rdi+8]
0x180003931  mov     rax, [rsp+0F8h+var_C8]
0x180003936  mov     rcx, [r14+rax+50h]
0x18000393b  mov     [r10+rdx+50h], rcx
0x180003940  mov     rdx, [rdi+8]
0x180003944  mov     rax, [rsp+0F8h+var_C8]
0x180003949  mov     rcx, [r14+rax+58h]
0x18000394e  mov     [r10+rdx+58h], rcx
0x180003953  mov     rdx, [rdi+8]
0x180003957  mov     rax, [rsp+0F8h+var_C8]
0x18000395c  mov     rcx, [r14+rax+60h]
0x180003961  mov     [r10+rdx+60h], rcx
0x180003966  mov     rdx, [rdi+8]
0x18000396a  mov     rax, [rsp+0F8h+var_C8]
0x18000396f  mov     rcx, [r14+rax+68h]
0x180003974  mov     [r10+rdx+68h], rcx
0x180003979  mov     rdx, [rdi+8]
0x18000397d  mov     rax, [rsp+0F8h+var_C8]
0x180003982  mov     rcx, [r14+rax+88h]
0x18000398a  mov     [r10+rdx+88h], rcx
0x180003992  mov     rdx, [rdi+8]
0x180003996  mov     rax, [rsp+0F8h+var_C8]
0x18000399b  mov     rcx, [r14+rax+90h]
0x1800039a3  mov     [r10+rdx+90h], rcx
0x1800039ab  mov     rax, [rdi+28h]
0x1800039af  lea     r8, [rax+r8*4]; unsigned __int16 *
0x1800039b3  lea     r9, [r8+2]; unsigned __int16 *
0x1800039b7  mov     rdx, [rdi+8]
0x1800039bb  add     rdx, r10; struct DBCOLUMNUPDATEINFO *
0x1800039be  mov     rcx, rdi; this
0x1800039c1  call    ?mdReadTableData@CMetaData@@AEAAXPEAUDBCOLUMNUPDATEINFO@@PEAG1@Z; CMetaData::mdReadTableData(DBCOLUMNUPDATEINFO *,ushort *,ushort *)
0x1800039c6  add     si, r15w
0x1800039ca  add     r12w, r15w
0x1800039ce  movzx   r13d, word ptr [rsp+0F8h+arg_8]
0x1800039d7  jmp     loc_18000382A
0x1800039dc  mov     [rdi], si
0x1800039df  sub     si, r13w
0x1800039e3  mov     [rdi+2], si
0x1800039e7  mov     rax, [rsp+0F8h+var_A8]
0x1800039ec  mov     [rsp+0F8h+var_A8], rbx
0x1800039f1  mov     rcx, [rsp+0F8h+arg_10]
0x1800039f9  mov     [rcx], rax
0x1800039fc  mov     rax, [rsp+0F8h+pv]
0x180003a01  mov     [rsp+0F8h+pv], rbx
0x180003a06  mov     rcx, [rsp+0F8h+arg_18]
0x180003a0e  mov     [rcx], rax
0x180003a11  mov     [rdi+4], bx
0x180003a15  jmp     short loc_180003A71
0x180003a17  mov     r15d, [rsp+0F8h+var_B0]
0x180003a1c  test    r15d, r15d
0x180003a1f  jz      short loc_180003A6C
0x180003a21  mov     edi, [rsp+0F8h+arg_8]
0x180003a28  test    edi, edi
0x180003a2a  jns     short loc_180003A6C
0x180003a2c  test    byte ptr cs:_bidGblFlags, 2
0x180003a33  jz      short loc_180003A64
0x180003a35  mov     rax, cs:off_180048478; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003a3c  test    rax, rax
0x180003a3f  jz      short loc_180003A64
0x180003a41  mov     dword ptr [rsp+0F8h+var_D8], 18Eh
0x180003a49  mov     r9d, edi
0x180003a4c  mov     r8, cs:off_180048478; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003a53  mov     edx, 63800h
0x180003a58  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003a5f  call    _bidTraceW
0x180003a64  mov     ecx, edi; int
0x180003a66  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180003a6c  mov     rbx, [rsp+0F8h+pv]
0x180003a71  mov     rcx, rbx; pv
0x180003a74  call    cs:__imp_CoTaskMemFree
0x180003a7a  nop
0x180003a7b  mov     rcx, [rsp+0F8h+var_A8]; pv
0x180003a80  call    cs:__imp_CoTaskMemFree
0x180003a86  nop
0x180003a87  mov     rcx, [rsp+0F8h+var_C8]; pv
0x180003a8c  call    cs:__imp_CoTaskMemFree
0x180003a92  nop
0x180003a93  lea     rcx, [rsp+0F8h+var_A0]
0x180003a98  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180003a9d  mov     eax, r15d
0x180003aa0  add     rsp, 0C0h
0x180003aa7  pop     r15
0x180003aa9  pop     r14
0x180003aab  pop     r13
0x180003aad  pop     r12
0x180003aaf  pop     rdi
0x180003ab0  pop     rsi
0x180003ab1  pop     rbx
0x180003ab2  retn
```
