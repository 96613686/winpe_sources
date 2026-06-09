# GenADTG::SaveResultContext(void)

- ea: `0x180008344`
- end: `0x1800085a3`
- name: `?SaveResultContext@GenADTG@@QEAAXXZ`
- size: `607`
- prototype: `void __fastcall(GenADTG *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1800091a4`

## callees

- `0x180001d94`
- `0x180002650`
- `0x18000266c`
- `0x1800027c0`
- `0x1800063fc`
- `0x180008190`
- `0x180008344`
- `0x180009490`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008556`
- `ole32!CoTaskMemFree` at `0x18000857c`
- `ole32!CoTaskMemFree` at `0x180008556`
- `ole32!CoTaskMemFree` at `0x18000857c`
- `OLEAUT32!__imp_VariantClear` at `0x18000853b`
- `OLEAUT32!__imp_VariantClear` at `0x18000853b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GenADTG::SaveResultContext(GenADTG *this)
{
  int v2; // eax
  int v3; // ebx
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  unsigned int *v9; // rbx
  unsigned __int128 v10; // rax
  GenADTG *v11; // rcx
  unsigned int i; // edi
  unsigned __int16 v13; // si
  __int64 v14; // rbx
  char *v15; // rcx
  unsigned int v16[3]; // [rsp+10h] [rbp-40h] BYREF
  GUID v17; // [rsp+1Ch] [rbp-34h]
  __int64 *v18; // [rsp+30h] [rbp-20h]
  int v19; // [rsp+38h] [rbp-18h]
  GUID v20; // [rsp+3Ch] [rbp-14h]
  unsigned __int8 v21[4]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp+4h] BYREF
  unsigned __int8 v23[8]; // [rsp+58h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+10h] BYREF
  __int64 v25; // [rsp+68h] [rbp+18h] BYREF
  unsigned int *v26; // [rsp+70h] [rbp+20h] BYREF
  __int64 v27; // [rsp+78h] [rbp+28h] BYREF

  v21[0] = 16;
  *(_WORD *)v23 = 0;
  v25 = 0;
  v22 = 0;
  pv = 0;
  GenADTG::SaveToBuffer(this, v21, 1u);
  v2 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetInfo,
         &v25);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048588[0] )
        bidTraceW(off_1800481C0[0], 1201152, off_180048588[0], (unsigned int)v2, 1173);
    }
    ThrowHR(v3);
  }
  v27 = 0;
  OnNullThrowOOM(v16);
  *(_QWORD *)v16 = qword_180036858;
  v16[2] = 4;
  v17 = DBPROPSET_ROWSET;
  v18 = qword_180036840;
  v19 = 5;
  v20 = DBPROPSET_ADC;
  if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, unsigned int *, LPVOID *))(*(_QWORD *)v25 + 24LL))(
         v25,
         2,
         v16,
         &v22,
         &pv) >= 0 )
  {
    v26 = 0;
    if ( v22 > 0x100 )
    {
      v10 = v22 * (unsigned __int128)4uLL;
      if ( !is_mul_ok(v22, 4u) )
        LODWORD(v10) = -1;
      v9 = (unsigned int *)MMMAlloc(v10, DWORD2(v10));
      v26 = v9;
    }
    else
    {
      v4 = 4LL * v22;
      v5 = v4 + 15;
      if ( v4 + 15 < v4 )
        v5 = 0xFFFFFFFFFFFFFF0LL;
      v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
      v7 = alloca(v6);
      v8 = alloca(v6);
      v9 = v16;
    }
    OnNullThrowOOM(v9);
    *(_WORD *)v23 = GenADTG::DeterminePropLength(v11, v22, (struct tagDBPROPSET *)pv, v9);
    GenADTG::SaveToBuffer(this, v23, 2u);
    GenADTG::SaveProperties(this, v22, (struct tagDBPROPSET *)pv, v9);
    for ( i = 0; i < v22; ++i )
    {
      v13 = 0;
      v14 = 32LL * i;
      v15 = (char *)pv;
      if ( *(_DWORD *)((char *)pv + v14 + 8) )
      {
        do
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)&v15[v14] + 8 * (9LL * v13++ + 6)));
          v15 = (char *)pv;
        }
        while ( (unsigned int)v13 < *(_DWORD *)((char *)pv + v14 + 8) );
      }
      CoTaskMemFree(*(LPVOID *)&v15[v14]);
    }
    CAutoP<_GUID>::~CAutoP<_GUID>(&v26);
  }
  CAutoP<_GUID>::~CAutoP<_GUID>(&v27);
  CoTaskMemFree(pv);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v25);
}

```

## disassembly

```asm
0x180008344  push    rbp
0x180008346  push    rbx
0x180008347  push    rsi
0x180008348  push    rdi
0x180008349  push    r15
0x18000834b  sub     rsp, 70h
0x18000834f  lea     rbp, [rsp+30h]
0x180008354  mov     rax, cs:__security_cookie
0x18000835b  xor     rax, rbp
0x18000835e  mov     [rbp+60h+var_30], rax
0x180008362  mov     rdi, rcx
0x180008365  mov     [rbp+60h+var_60], 10h
0x180008369  xor     eax, eax
0x18000836b  mov     word ptr [rbp+60h+var_58], ax
0x18000836f  mov     [rbp+60h+var_48], rax
0x180008373  mov     [rbp+60h+var_5C], eax
0x180008376  mov     [rbp+60h+pv], rax
0x18000837a  lea     r15d, [rax+1]
0x18000837e  mov     r8d, r15d; unsigned int
0x180008381  lea     rdx, [rbp+60h+var_60]; unsigned __int8 *
0x180008385  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000838a  mov     rcx, [rdi+18h]
0x18000838e  mov     rax, [rcx]
0x180008391  lea     r8, [rbp+60h+var_48]
0x180008395  lea     rdx, IID_IRowsetInfo
0x18000839c  mov     rax, [rax]
0x18000839f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a4  mov     ebx, eax
0x1800083a6  test    eax, eax
0x1800083a8  jns     short loc_1800083EA
0x1800083aa  test    byte ptr cs:_bidGblFlags, 2
0x1800083b1  jz      short loc_1800083E2
0x1800083b3  mov     rcx, cs:off_180048588; "<GenADTG::SaveResultContext|ADO|ERR>  H"...
0x1800083ba  test    rcx, rcx
0x1800083bd  jz      short loc_1800083E2
0x1800083bf  mov     [rsp+90h+var_70], 495h
0x1800083c7  mov     r9d, eax
0x1800083ca  mov     r8, cs:off_180048588; "<GenADTG::SaveResultContext|ADO|ERR>  H"...
0x1800083d1  mov     edx, 125400h
0x1800083d6  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800083dd  call    _bidTraceW
0x1800083e2  mov     ecx, ebx; int
0x1800083e4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800083ea  mov     [rbp+60h+var_38], 0
0x1800083f2  mov     eax, [rsp+90h+var_90]
0x1800083f5  sub     rsp, 40h
0x1800083f9  lea     rbx, [rsp+0D0h+var_A0]
0x1800083fe  mov     eax, [rbx]
0x180008400  mov     rcx, rbx; void *
0x180008403  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180008408  lea     rax, qword_180036858
0x18000840f  mov     [rbx], rax
0x180008412  mov     esi, 4
0x180008417  mov     [rbx+8], esi
0x18000841a  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180008421  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180008426  lea     rax, qword_180036840
0x18000842d  mov     [rbx+20h], rax
0x180008431  mov     dword ptr [rbx+28h], 5
0x180008438  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x18000843f  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x180008444  mov     rcx, [rbp+60h+var_48]
0x180008448  mov     rax, [rcx]
0x18000844b  lea     rdx, [rbp+60h+pv]
0x18000844f  mov     [rsp+0D0h+var_B0], rdx
0x180008454  lea     r9, [rbp+60h+var_5C]
0x180008458  mov     r8, rbx
0x18000845b  lea     edx, [rsi-2]
0x18000845e  mov     rax, [rax+18h]
0x180008462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008467  test    eax, eax
0x180008469  js      loc_18000856E
0x18000846f  mov     [rbp+60h+var_40], 0
0x180008477  mov     eax, [rbp+60h+var_5C]
0x18000847a  cmp     eax, 100h
0x18000847f  ja      short loc_1800084AE
0x180008481  shl     rax, 2
0x180008485  lea     rcx, [rax+0Fh]
0x180008489  cmp     rcx, rax
0x18000848c  ja      short loc_180008498
0x18000848e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008498  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000849c  mov     rax, rcx
0x18000849f  call    _alloca_probe
0x1800084a4  sub     rsp, rcx
0x1800084a7  lea     rbx, [rsp+0D0h+var_A0]
0x1800084ac  jmp     short loc_1800084D0
0x1800084ae  mov     rcx, rax
0x1800084b1  mov     rax, rsi
0x1800084b4  mul     rcx
0x1800084b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800084be  cmovb   rax, rcx
0x1800084c2  mov     ecx, eax; unsigned int
0x1800084c4  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800084c9  mov     rbx, rax
0x1800084cc  mov     [rbp+60h+var_40], rax
0x1800084d0  mov     rcx, rbx; void *
0x1800084d3  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800084d8  mov     r9, rbx; unsigned int *
0x1800084db  mov     r8, [rbp+60h+pv]; struct tagDBPROPSET *
0x1800084df  mov     edx, [rbp+60h+var_5C]; unsigned int
0x1800084e2  call    ?DeterminePropLength@GenADTG@@AEAAGKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::DeterminePropLength(ulong,tagDBPROPSET *,ulong *)
0x1800084e7  mov     word ptr [rbp+60h+var_58], ax
0x1800084eb  mov     r8d, 2; unsigned int
0x1800084f1  lea     rdx, [rbp+60h+var_58]; unsigned __int8 *
0x1800084f5  mov     rcx, rdi; this
0x1800084f8  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800084fd  mov     r9, rbx; unsigned int *
0x180008500  mov     r8, [rbp+60h+pv]; struct tagDBPROPSET *
0x180008504  mov     edx, [rbp+60h+var_5C]; unsigned int
0x180008507  mov     rcx, rdi; this
0x18000850a  call    ?SaveProperties@GenADTG@@AEAAXKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::SaveProperties(ulong,tagDBPROPSET *,ulong *)
0x18000850f  xor     edi, edi
0x180008511  cmp     [rbp+60h+var_5C], edi
0x180008514  jbe     short loc_180008564
0x180008516  xor     esi, esi
0x180008518  mov     ebx, edi
0x18000851a  shl     rbx, 5
0x18000851e  mov     rcx, [rbp+60h+pv]
0x180008522  cmp     [rbx+rcx+8], esi
0x180008526  jbe     short loc_180008552
0x180008528  movzx   eax, si
0x18000852b  lea     rdx, [rax+rax*8]
0x18000852f  mov     rax, [rbx+rcx]
0x180008533  lea     rdx, [rdx+6]
0x180008537  lea     rcx, [rax+rdx*8]; pvarg
0x18000853b  call    cs:__imp_VariantClear
0x180008541  add     si, r15w
0x180008545  movzx   eax, si
0x180008548  mov     rcx, [rbp+60h+pv]
0x18000854c  cmp     eax, [rbx+rcx+8]
0x180008550  jb      short loc_180008528
0x180008552  mov     rcx, [rbx+rcx]; pv
0x180008556  call    cs:__imp_CoTaskMemFree
0x18000855c  add     edi, r15d
0x18000855f  cmp     edi, [rbp+60h+var_5C]
0x180008562  jb      short loc_180008516
0x180008564  lea     rcx, [rbp+60h+var_40]
0x180008568  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x18000856d  nop
0x18000856e  lea     rcx, [rbp+60h+var_38]
0x180008572  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180008577  nop
0x180008578  mov     rcx, [rbp+60h+pv]; pv
0x18000857c  call    cs:__imp_CoTaskMemFree
0x180008582  nop
0x180008583  lea     rcx, [rbp+60h+var_48]
0x180008587  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000858c  mov     rcx, [rbp+60h+var_30]
0x180008590  xor     rcx, rbp; StackCookie
0x180008593  call    __security_check_cookie
0x180008598  lea     rsp, [rbp+40h]
0x18000859c  pop     r15
0x18000859e  pop     rdi
0x18000859f  pop     rsi
0x1800085a0  pop     rbx
0x1800085a1  pop     rbp
0x1800085a2  retn
```
