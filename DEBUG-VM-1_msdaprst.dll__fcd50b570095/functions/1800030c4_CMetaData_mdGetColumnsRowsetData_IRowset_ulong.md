# CMetaData::mdGetColumnsRowsetData(IRowset *,ulong)

- ea: `0x1800030c4`
- end: `0x180003631`
- name: `?mdGetColumnsRowsetData@CMetaData@@AEAAXPEAUIRowset@@K@Z`
- size: `1389`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x180002b1c`

## callees

- `0x180001d94`
- `0x180002650`
- `0x18000266c`
- `0x1800027c0`
- `0x1800030c4`
- `0x180004238`
- `0x1800050c4`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e006`
- `0x18002e02a`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800035ed`
- `ole32!CoTaskMemFree` at `0x1800035ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CMetaData::mdGetColumnsRowsetData(CMetaData *this, struct IRowset *a2, unsigned int a3)
{
  unsigned int v3; // esi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  struct IRowset **v11; // rdi
  unsigned __int128 v12; // rax
  unsigned int v13; // r14d
  unsigned int v14; // edx
  unsigned int v15; // r12d
  __int64 v16; // rbx
  unsigned int i; // r15d
  __int64 v18; // rax
  char *v19; // rcx
  CMetaData *v20; // rcx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  unsigned __int64 *v27; // rax
  unsigned __int128 v28; // rax
  unsigned __int128 v29; // rax
  unsigned __int8 *v30; // rax
  unsigned __int128 v31; // rax
  unsigned __int8 *v32; // rax
  __int64 v33; // r15
  int v34; // esi
  __int64 v35; // rdx
  int v36; // esi
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  int v40; // ebx
  void *v41; // rcx
  struct IRowset *v42; // [rsp+50h] [rbp+0h] BYREF
  unsigned __int64 *v43; // [rsp+58h] [rbp+8h] BYREF
  unsigned __int64 *v44; // [rsp+60h] [rbp+10h] BYREF
  __int64 v45; // [rsp+68h] [rbp+18h] BYREF
  __int64 v46; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v47[2]; // [rsp+78h] [rbp+28h] BYREF
  __int64 v48; // [rsp+80h] [rbp+30h] BYREF
  char *v49; // [rsp+88h] [rbp+38h] BYREF
  struct IRowset **v50; // [rsp+90h] [rbp+40h] BYREF
  char *v51; // [rsp+98h] [rbp+48h]
  __int128 Buf1; // [rsp+A0h] [rbp+50h] BYREF
  __int128 v53; // [rsp+B0h] [rbp+60h]

  v3 = a3;
  LODWORD(v44) = a3;
  v5 = 0;
  v45 = 0;
  v42 = 0;
  v48 = 0;
  v49 = 0;
  v46 = 0;
  *(_QWORD *)v47 = 0;
  if ( *((_QWORD *)this + 4) || *((_QWORD *)this + 1) )
  {
    v41 = 0;
  }
  else
  {
    if ( ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsRowset,
           &v45) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *, char **))(*(_QWORD *)v45 + 24LL))(v45, &v46, &v49) >= 0 )
    {
      v50 = 0;
      if ( (unsigned int)v46 > 0x20 )
      {
        v12 = (unsigned int)v46 * (unsigned __int128)0x20uLL;
        if ( !is_mul_ok((unsigned int)v46, 0x20u) )
          LODWORD(v12) = -1;
        v11 = (struct IRowset **)MMMAlloc(v12, DWORD2(v12));
        v50 = v11;
      }
      else
      {
        v6 = 32LL * (unsigned int)v46;
        v7 = v6 + 15;
        if ( v6 + 15 < v6 )
          v7 = 0xFFFFFFFFFFFFFF0LL;
        v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
        v9 = alloca(v8);
        v10 = alloca(v8);
        v11 = &v42;
      }
      OnNullThrowOOM(v11);
      v13 = 0;
      v14 = 0;
      LODWORD(v43) = 0;
      v15 = v46;
      if ( (_DWORD)v46 )
      {
        do
        {
          v16 = 32LL * v13;
          v51 = v49;
          Buf1 = *(_OWORD *)&v49[v16];
          v53 = *(_OWORD *)&v49[v16 + 16];
          for ( i = 11; i < 0x1F; ++i )
          {
            if ( (_DWORD)v53 == *((_DWORD *)&g_rgDesiredColumn + 20 * i + 4)
              && !memcmp_0(&Buf1, &g_rgDesiredColumn + 10 * i, 0x10u)
              && DWORD2(v53) == *((_DWORD *)&g_rgDesiredColumn + 20 * i + 6) )
            {
              v18 = 4LL * (unsigned int)v43;
              v14 = (_DWORD)v43 + 1;
              LODWORD(v43) = (_DWORD)v43 + 1;
              v19 = v51;
              *(_OWORD *)&v11[v18] = *(_OWORD *)&v51[v16];
              *(_OWORD *)&v11[v18 + 2] = *(_OWORD *)&v19[v16 + 16];
              v15 = v46;
              goto LABEL_21;
            }
          }
          v14 = (unsigned int)v43;
LABEL_21:
          ++v13;
        }
        while ( v13 < v15 );
        v3 = (unsigned int)v44;
        v5 = 0;
      }
      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, struct IRowset **, GUID *, _DWORD, _QWORD, struct IRowset **))(*(_QWORD *)v45 + 32LL))(
             v45,
             0,
             v14,
             v11,
             &IID_IRowset,
             0,
             0,
             &v42) >= 0 )
      {
        v21 = CMetaData::mdSetupAccessor(v20, v42);
        if ( v21 )
        {
          v44 = 0;
          v43 = 0;
          v22 = v3;
          if ( v3 > 0x80 )
          {
            v28 = v3 * (unsigned __int128)8uLL;
            if ( !is_mul_ok(v3, 8u) )
              LODWORD(v28) = -1;
            v27 = (unsigned __int64 *)MMMAlloc(v28, DWORD2(v28));
            v43 = v27;
          }
          else
          {
            v23 = 8LL * v3 + 15;
            if ( v23 <= 8 * (unsigned __int64)v3 )
              v23 = 0xFFFFFFFFFFFFFF0LL;
            v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
            v25 = alloca(v24);
            v26 = alloca(v24);
            v27 = (unsigned __int64 *)&v42;
          }
          v44 = v27;
          v29 = v3 * (unsigned __int128)0x25B0uLL;
          if ( !is_mul_ok(v3, 0x25B0u) )
            LODWORD(v29) = -1;
          v30 = MMMAlloc(v29, DWORD2(v29));
          *((_QWORD *)this + 4) = v30;
          OnNullThrowOOM(v30);
          v31 = v3 * (unsigned __int128)4uLL;
          if ( !is_mul_ok(v3, 4u) )
            LODWORD(v31) = -1;
          v32 = MMMAlloc(v31, DWORD2(v31));
          *((_QWORD *)this + 5) = v32;
          OnNullThrowOOM(v32);
          memset_0(*((void **)this + 5), 0, 4 * v3);
          v33 = v3 + 1;
          while ( 1 )
          {
            v34 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD, _QWORD, unsigned __int64, unsigned int *, unsigned __int64 **))v42->lpVtbl->GetNextRows)(
                    v42,
                    0,
                    0,
                    v33 - v5,
                    v47,
                    &v44);
            if ( v34 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048470[0] )
                bidTraceW(off_1800481B8[0], 504832, off_180048470[0], (unsigned int)v34, 493);
              ThrowHR(v34);
            }
            v35 = *(_QWORD *)v47;
            v5 += *(_QWORD *)v47;
            if ( v5 <= v22 )
            {
              CMetaData::mdIterateColumns(this, v42, v44, v21, v47[0]);
              v35 = *(_QWORD *)v47;
            }
            v36 = ((__int64 (__fastcall *)(struct IRowset *, __int64, unsigned __int64 *, _QWORD, _QWORD, _QWORD))v42->lpVtbl->ReleaseRows)(
                    v42,
                    v35,
                    v44,
                    0,
                    0,
                    0);
            if ( v36 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048468[0] )
                bidTraceW(off_1800481B8[0], 508928, off_180048468[0], (unsigned int)v36, 497);
              ThrowHR(v36);
            }
            if ( v5 >= v22 )
              break;
            if ( !*(_QWORD *)v47 )
              goto LABEL_45;
          }
          if ( v5 != v22 )
          {
LABEL_45:
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_180048460[0] )
                bidTraceW(off_1800481B8[0], 518144, off_180048460[0], 2147549183LL, 506);
            }
            ThrowHR(-2147418113);
          }
          v37 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))v42->lpVtbl->QueryInterface)(
                  v42,
                  &IID_IAccessor,
                  &v48);
          v38 = v37;
          if ( v37 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048458[0] )
              bidTraceW(off_1800481B8[0], 521216, off_180048458[0], (unsigned int)v37, 509);
            ThrowHR(v38);
          }
          v39 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v48 + 48LL))(v48, v21, 0);
          v40 = v39;
          if ( v39 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048450[0] )
              bidTraceW(off_1800481B8[0], 522240, off_180048450[0], (unsigned int)v39, 510);
            ThrowHR(v40);
          }
          CAutoP<_GUID>::~CAutoP<_GUID>(&v43);
        }
      }
      CAutoP<_GUID>::~CAutoP<_GUID>(&v50);
    }
    v41 = v49;
  }
  CoTaskMemFree(v41);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v48);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v42);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v45);
}

```

## disassembly

```asm
0x1800030c4  push    rbp
0x1800030c6  push    rbx
0x1800030c7  push    rsi
0x1800030c8  push    rdi
0x1800030c9  push    r12
0x1800030cb  push    r13
0x1800030cd  push    r14
0x1800030cf  push    r15
0x1800030d1  sub     rsp, 0D8h
0x1800030d8  lea     rbp, [rsp+50h]
0x1800030dd  mov     rax, cs:__security_cookie
0x1800030e4  xor     rax, rbp
0x1800030e7  mov     [rbp+0C0h+var_50], rax
0x1800030eb  mov     esi, r8d
0x1800030ee  mov     dword ptr [rbp+0C0h+var_B0], r8d
0x1800030f2  mov     r9, rdx
0x1800030f5  mov     r13, rcx
0x1800030f8  xor     ebx, ebx
0x1800030fa  mov     [rbp+0C0h+var_A8], rbx
0x1800030fe  mov     [rbp+0C0h+var_C0], rbx
0x180003102  mov     [rbp+0C0h+var_90], rbx
0x180003106  mov     [rbp+0C0h+var_88], rbx
0x18000310a  mov     [rbp+0C0h+var_A0], rbx
0x18000310e  mov     qword ptr [rbp+0C0h+var_98], rbx
0x180003112  cmp     [rcx+20h], rbx
0x180003116  jnz     loc_1800035EB
0x18000311c  cmp     [rcx+8], rbx
0x180003120  jnz     loc_1800035EB
0x180003126  mov     rax, [rdx]
0x180003129  lea     r8, [rbp+0C0h+var_A8]
0x18000312d  lea     rdx, IID_IColumnsRowset
0x180003134  mov     rcx, r9
0x180003137  mov     rax, [rax]
0x18000313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313f  test    eax, eax
0x180003141  js      loc_180003562
0x180003147  mov     rcx, [rbp+0C0h+var_A8]
0x18000314b  mov     rax, [rcx]
0x18000314e  lea     r8, [rbp+0C0h+var_88]
0x180003152  lea     rdx, [rbp+0C0h+var_A0]
0x180003156  mov     rax, [rax+18h]
0x18000315a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315f  test    eax, eax
0x180003161  js      loc_180003562
0x180003167  mov     [rbp+0C0h+var_80], rbx
0x18000316b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000316f  mov     r15, 0FFFFFFFFFFFFFF0h
0x180003179  mov     rax, [rbp+0C0h+var_A0]
0x18000317d  cmp     eax, 20h ; ' '
0x180003180  ja      short loc_1800031AA
0x180003182  mov     eax, eax
0x180003184  shl     rax, 5
0x180003188  lea     rcx, [rax+0Fh]
0x18000318c  cmp     rcx, rax
0x18000318f  ja      short loc_180003194
0x180003191  mov     rcx, r15
0x180003194  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180003198  mov     rax, rcx
0x18000319b  call    _alloca_probe
0x1800031a0  sub     rsp, rcx
0x1800031a3  lea     rdi, [rsp+110h+var_C0]
0x1800031a8  jmp     short loc_1800031C6
0x1800031aa  mov     ecx, eax
0x1800031ac  mov     eax, 20h ; ' '
0x1800031b1  mul     rcx
0x1800031b4  cmovb   rax, r8
0x1800031b8  mov     ecx, eax; unsigned int
0x1800031ba  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800031bf  mov     rdi, rax
0x1800031c2  mov     [rbp+0C0h+var_80], rax
0x1800031c6  mov     rcx, rdi; void *
0x1800031c9  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800031ce  mov     r14d, ebx
0x1800031d1  mov     edx, ebx
0x1800031d3  mov     dword ptr [rbp+0C0h+var_B8], ebx
0x1800031d6  mov     r12, [rbp+0C0h+var_A0]
0x1800031da  test    r12d, r12d
0x1800031dd  jz      loc_1800032A4
0x1800031e3  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x1800031ea  mov     ebx, r14d
0x1800031ed  shl     rbx, 5
0x1800031f1  mov     rax, [rbp+0C0h+var_88]
0x1800031f5  mov     [rbp+0C0h+var_78], rax
0x1800031f9  movups  xmm0, xmmword ptr [rbx+rax]
0x1800031fd  movaps  [rbp+0C0h+Buf1], xmm0
0x180003201  movups  xmm1, xmmword ptr [rbx+rax+10h]
0x180003206  movaps  [rbp+0C0h+var_60], xmm1
0x18000320a  mov     r15d, 0Bh
0x180003210  cmp     r15d, 1Fh
0x180003214  jnb     short loc_180003286
0x180003216  mov     eax, r15d
0x180003219  lea     rsi, [rax+rax*4]
0x18000321d  add     rsi, rsi
0x180003220  mov     eax, dword ptr [rbp+0C0h+var_60]
0x180003223  cmp     eax, [rcx+rsi*8+10h]
0x180003227  jnz     short loc_180003250
0x180003229  lea     rdx, [rcx+rsi*8]; Buf2
0x18000322d  mov     r8d, 10h; Size
0x180003233  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x180003237  call    memcmp_0
0x18000323c  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180003243  test    eax, eax
0x180003245  jnz     short loc_180003250
0x180003247  mov     eax, dword ptr [rbp+0C0h+var_60+8]
0x18000324a  cmp     eax, [rcx+rsi*8+18h]
0x18000324e  jz      short loc_180003255
0x180003250  inc     r15d
0x180003253  jmp     short loc_180003210
0x180003255  mov     edx, dword ptr [rbp+0C0h+var_B8]
0x180003258  mov     eax, edx
0x18000325a  shl     rax, 5
0x18000325e  inc     edx
0x180003260  mov     dword ptr [rbp+0C0h+var_B8], edx
0x180003263  mov     rcx, [rbp+0C0h+var_78]
0x180003267  movups  xmm0, xmmword ptr [rbx+rcx]
0x18000326b  movups  xmmword ptr [rax+rdi], xmm0
0x18000326f  movups  xmm1, xmmword ptr [rbx+rcx+10h]
0x180003274  movups  xmmword ptr [rax+rdi+10h], xmm1
0x180003279  mov     r12, [rbp+0C0h+var_A0]
0x18000327d  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180003284  jmp     short loc_180003289
0x180003286  mov     edx, dword ptr [rbp+0C0h+var_B8]
0x180003289  inc     r14d
0x18000328c  cmp     r14d, r12d
0x18000328f  jb      loc_1800031EA
0x180003295  mov     esi, dword ptr [rbp+0C0h+var_B0]
0x180003298  xor     ebx, ebx
0x18000329a  mov     r15, 0FFFFFFFFFFFFFF0h
0x1800032a4  mov     rcx, [rbp+0C0h+var_A8]
0x1800032a8  mov     rax, [rcx]
0x1800032ab  mov     r8d, edx
0x1800032ae  lea     rdx, [rbp+0C0h+var_C0]
0x1800032b2  mov     [rsp+110h+var_D8], rdx
0x1800032b7  mov     [rsp+110h+var_E0], rbx
0x1800032bc  mov     dword ptr [rsp+110h+var_E8], ebx
0x1800032c0  lea     rdx, IID_IRowset
0x1800032c7  mov     qword ptr [rsp+110h+var_F0], rdx
0x1800032cc  mov     r9, rdi
0x1800032cf  xor     edx, edx
0x1800032d1  mov     rax, [rax+20h]
0x1800032d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032da  test    eax, eax
0x1800032dc  js      loc_180003558
0x1800032e2  mov     rdx, [rbp+0C0h+var_C0]; struct IRowset *
0x1800032e6  call    ?mdSetupAccessor@CMetaData@@AEAA_KPEAUIRowset@@@Z; CMetaData::mdSetupAccessor(IRowset *)
0x1800032eb  mov     r14, rax
0x1800032ee  test    rax, rax
0x1800032f1  jz      loc_180003558
0x1800032f7  mov     [rbp+0C0h+var_B0], rbx
0x1800032fb  mov     [rbp+0C0h+var_B8], rbx
0x1800032ff  mov     edi, esi
0x180003301  cmp     esi, 80h
0x180003307  ja      short loc_180003337
0x180003309  lea     rax, ds:0[rdi*8]
0x180003311  lea     rcx, [rax+0Fh]
0x180003315  cmp     rcx, rax
0x180003318  ja      short loc_18000331D
0x18000331a  mov     rcx, r15
0x18000331d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180003321  mov     rax, rcx
0x180003324  call    _alloca_probe
0x180003329  sub     rsp, rcx
0x18000332c  lea     rax, [rsp+110h+var_C0]
0x180003331  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003335  jmp     short loc_180003355
0x180003337  mov     eax, 8
0x18000333c  mul     rdi
0x18000333f  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003346  cmovb   rax, r15
0x18000334a  mov     ecx, eax; unsigned int
0x18000334c  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180003351  mov     [rbp+0C0h+var_B8], rax
0x180003355  mov     [rbp+0C0h+var_B0], rax
0x180003359  mov     eax, 25B0h
0x18000335e  mul     rdi
0x180003361  cmovb   rax, r15
0x180003365  mov     ecx, eax; unsigned int
0x180003367  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000336c  mov     [r13+20h], rax
0x180003370  mov     rcx, rax; void *
0x180003373  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180003378  mov     eax, 4
0x18000337d  mul     rdi
0x180003380  cmovb   rax, r15
0x180003384  mov     ecx, eax; unsigned int
0x180003386  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000338b  mov     [r13+28h], rax
0x18000338f  mov     rcx, rax; void *
0x180003392  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180003397  lea     r8d, ds:0[rsi*4]; Size
0x18000339f  xor     edx, edx; Val
0x1800033a1  mov     rcx, [r13+28h]; void *
0x1800033a5  call    memset_0
0x1800033aa  lea     r15d, [rsi+1]
0x1800033ae  xor     r12d, r12d
0x1800033b1  mov     rcx, [rbp+0C0h+var_C0]
0x1800033b5  mov     rax, [rcx]
0x1800033b8  mov     r9, r15
0x1800033bb  sub     r9, rbx
0x1800033be  lea     rdx, [rbp+0C0h+var_B0]
0x1800033c2  mov     [rsp+110h+var_E8], rdx
0x1800033c7  lea     rdx, [rbp+0C0h+var_98]
0x1800033cb  mov     qword ptr [rsp+110h+var_F0], rdx
0x1800033d0  xor     r8d, r8d
0x1800033d3  xor     edx, edx
0x1800033d5  mov     rax, [rax+28h]
0x1800033d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033de  mov     esi, eax
0x1800033e0  test    eax, eax
0x1800033e2  js      loc_1800035AB
0x1800033e8  mov     rdx, qword ptr [rbp+0C0h+var_98]
0x1800033ec  add     rbx, rdx
0x1800033ef  cmp     rbx, rdi
0x1800033f2  ja      short loc_18000340F
0x1800033f4  mov     [rsp+110h+var_F0], edx; unsigned int
0x1800033f8  mov     r9, r14; unsigned __int64
0x1800033fb  mov     r8, [rbp+0C0h+var_B0]; unsigned __int64 *
0x1800033ff  mov     rdx, [rbp+0C0h+var_C0]; struct IRowset *
0x180003403  mov     rcx, r13; this
0x180003406  call    ?mdIterateColumns@CMetaData@@AEAAXPEAUIRowset@@PEA_K_KK@Z; CMetaData::mdIterateColumns(IRowset *,unsigned __int64 *,unsigned __int64,ulong)
0x18000340b  mov     rdx, qword ptr [rbp+0C0h+var_98]
0x18000340f  mov     rcx, [rbp+0C0h+var_C0]
0x180003413  mov     rax, [rcx]
0x180003416  mov     [rsp+110h+var_E8], r12
0x18000341b  mov     qword ptr [rsp+110h+var_F0], r12
0x180003420  xor     r9d, r9d
0x180003423  mov     r8, [rbp+0C0h+var_B0]
0x180003427  mov     rax, [rax+30h]
0x18000342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003430  mov     esi, eax
0x180003432  test    eax, eax
0x180003434  js      loc_18000356B
0x18000343a  cmp     rbx, rdi
0x18000343d  jnb     short loc_18000344B
0x18000343f  cmp     qword ptr [rbp+0C0h+var_98], r12
0x180003443  jnz     loc_1800033B1
0x180003449  jmp     short loc_18000344D
0x18000344b  jz      short loc_180003492
0x18000344d  mov     ebx, 8000FFFFh
0x180003452  test    byte ptr cs:_bidGblFlags, 2
0x180003459  jz      short loc_18000348A
0x18000345b  mov     rax, cs:off_180048460; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x180003462  test    rax, rax
0x180003465  jz      short loc_18000348A
0x180003467  mov     [rsp+110h+var_F0], 1FAh
0x18000346f  mov     r9d, ebx
0x180003472  mov     r8, cs:off_180048460; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x180003479  mov     edx, 7E800h
0x18000347e  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003485  call    _bidTraceW
0x18000348a  mov     ecx, ebx; int
0x18000348c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180003492  mov     rcx, [rbp+0C0h+var_C0]
0x180003496  mov     rax, [rcx]
0x180003499  lea     r8, [rbp+0C0h+var_90]
0x18000349d  lea     rdx, IID_IAccessor
0x1800034a4  mov     rax, [rax]
0x1800034a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ac  mov     ebx, eax
0x1800034ae  test    eax, eax
0x1800034b0  jns     short loc_1800034F2
0x1800034b2  test    byte ptr cs:_bidGblFlags, 2
0x1800034b9  jz      short loc_1800034EA
0x1800034bb  mov     rcx, cs:off_180048458; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x1800034c2  test    rcx, rcx
0x1800034c5  jz      short loc_1800034EA
0x1800034c7  mov     [rsp+110h+var_F0], 1FDh
0x1800034cf  mov     r9d, eax
0x1800034d2  mov     r8, cs:off_180048458; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x1800034d9  mov     edx, 7F400h
0x1800034de  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800034e5  call    _bidTraceW
0x1800034ea  mov     ecx, ebx; int
0x1800034ec  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800034f2  mov     rcx, [rbp+0C0h+var_90]
0x1800034f6  mov     rax, [rcx]
0x1800034f9  xor     r8d, r8d
0x1800034fc  mov     rdx, r14
0x1800034ff  mov     rax, [rax+30h]
0x180003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003508  mov     ebx, eax
0x18000350a  test    eax, eax
0x18000350c  jns     short loc_18000354E
0x18000350e  test    byte ptr cs:_bidGblFlags, 2
0x180003515  jz      short loc_180003546
0x180003517  mov     rcx, cs:off_180048450; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x18000351e  test    rcx, rcx
0x180003521  jz      short loc_180003546
0x180003523  mov     [rsp+110h+var_F0], 1FEh
0x18000352b  mov     r9d, eax
0x18000352e  mov     r8, cs:off_180048450; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x180003535  mov     edx, 7F800h
0x18000353a  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003541  call    _bidTraceW
0x180003546  mov     ecx, ebx; int
0x180003548  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000354e  lea     rcx, [rbp+0C0h+var_B8]
0x180003552  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180003557  nop
0x180003558  lea     rcx, [rbp+0C0h+var_80]
  ... truncated ...
```
