# CImpIColumnsRowset::GetColumnsRowset(IUnknown *,unsigned __int64,tagDBID const * const,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x180011f90`
- end: `0x1800123ce`
- name: `?GetColumnsRowset@CImpIColumnsRowset@@UEAAJPEAUIUnknown@@_KQEBUtagDBID@@AEBU_GUID@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(CImpIColumnsRowset *__hidden this, struct IUnknown *, unsigned __int64, const struct tagDBID *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000261c`
- `0x180002650`
- `0x18000266c`
- `0x180011c54`
- `0x180011f90`
- `0x180012678`
- `0x180012984`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011fe1`
- `KERNEL32!GetCurrentThreadId` at `0x180011fe1`
- `KERNEL32!LeaveCriticalSection` at `0x180012109`
- `KERNEL32!LeaveCriticalSection` at `0x1800123ad`
- `KERNEL32!LeaveCriticalSection` at `0x180012109`
- `KERNEL32!LeaveCriticalSection` at `0x1800123ad`
- `ole32!CoCreateInstance` at `0x18001213b`
- `ole32!CoCreateInstance` at `0x18001213b`
- `ole32!CoTaskMemFree` at `0x1800120bc`
- `ole32!CoTaskMemFree` at `0x180012310`
- `ole32!CoTaskMemFree` at `0x180012360`
- `ole32!CoTaskMemFree` at `0x1800120bc`
- `ole32!CoTaskMemFree` at `0x180012310`
- `ole32!CoTaskMemFree` at `0x180012360`
- `OLEAUT32!__imp_VariantClear` at `0x1800122fc`
- `OLEAUT32!__imp_VariantClear` at `0x1800122fc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012050`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012050`
- `MSDART!UMSEnterCSWraper` at `0x180011fc9`
- `MSDART!UMSEnterCSWraper` at `0x180011fc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CImpIColumnsRowset::GetColumnsRowset(
        CImpIColumnsRowset *this,
        struct IUnknown *a2,
        __int64 a3,
        struct tagDBID *a4,
        const struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  __int64 v9; // r14
  _DWORD *v10; // r15
  _DWORD *v11; // r12
  int v12; // ecx
  unsigned int v13; // ebx
  bool v14; // zf
  __int64 v15; // rcx
  HRESULT v17; // eax
  unsigned int v18; // eax
  CImpIColumnsRowset *v19; // rcx
  struct tagDBCOLUMNINFO *v20; // rdi
  struct tagDBPROPSET *v21; // rbx
  int v22; // eax
  int v23; // r13d
  int v24; // eax
  int v25; // edi
  unsigned int v26; // r13d
  __int64 v27; // r14
  __int64 v28; // rdi
  unsigned int v29; // edi
  struct tagDBPROPSET *v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-94h] BYREF
  struct IRowset *v34; // [rsp+48h] [rbp-90h] BYREF
  unsigned int *v35; // [rsp+50h] [rbp-88h] BYREF
  struct tagDBCOLUMNINFO *v36; // [rsp+58h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-78h] BYREF
  int v38; // [rsp+68h] [rbp-70h]
  __int64 v39; // [rsp+70h] [rbp-68h] BYREF
  struct tagDBPROPSET *v40; // [rsp+78h] [rbp-60h] BYREF
  __int64 v41; // [rsp+80h] [rbp-58h]
  int v42; // [rsp+88h] [rbp-50h] BYREF
  _DWORD *v43; // [rsp+90h] [rbp-48h]
  _DWORD *v44; // [rsp+98h] [rbp-40h]
  __int64 v45; // [rsp+A0h] [rbp-38h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  v41 = v9;
  UMSEnterCSWraper(v9);
  v10 = (_DWORD *)(v9 + 12);
  v43 = (_DWORD *)(v9 + 12);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)(v9 + 16);
  v44 = (_DWORD *)(v9 + 16);
  ++*(_DWORD *)(v9 + 16);
  v45 = v9;
  ppv = 0;
  v34 = 0;
  v39 = 0;
  v36 = 0;
  v33 = 0;
  v32 = 0;
  v40 = 0;
  v35 = 0;
  SetErrorInfo(0, 0);
  if ( a8 && (!a6 || a7) && (!a3 || a4) )
  {
    if ( a2 )
    {
      v12 = -2147217886;
LABEL_10:
      v13 = Exit(v12, 0);
      CAutoP<_GUID>::~CAutoP<_GUID>(&v35);
      CoTaskMemFree(0);
      CAutoP<_GUID>::~CAutoP<_GUID>(&v36);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v39);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v34);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
      --*v11;
      v14 = (*v10)-- == 1;
      if ( v14 )
        *(_DWORD *)(v9 + 8) = -1;
      v15 = *(_QWORD *)v9;
      --*(_DWORD *)(v15 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
      return v13;
    }
    *a8 = 0;
    v17 = CoCreateInstance(&CLSID_FoxRowset, 0, 1u, &IID_ICreateRowset, &ppv);
    v38 = v17;
    if ( v17 < 0 )
    {
      v12 = v17;
      goto LABEL_10;
    }
    try
    {
      v18 = DownsizeToULONGThrow<unsigned __int64>(a3);
      CImpIColumnsRowset::SetupColumnsInfo((CImpIColumnsRowset *)a4, &v33, &v36, v18, a4, &v35);
      CImpIColumnsRowset::SetupProperties(v19, &v32, &v40, a6, a7);
      v20 = v36;
      v21 = v40;
      v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct tagDBPROPSET *, _QWORD, struct tagDBCOLUMNINFO *, struct IRowset **))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v32,
              v40,
              v33,
              v36,
              &v34);
      v23 = v22;
      if ( v22 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048948[0] )
          bidTraceW(off_1800481D0[0], 145408, off_180048948[0], (unsigned int)v22, 142);
        ThrowHR(v23);
      }
      CImpIColumnsRowset::AddData(this, v34, v33, v20, v35);
      v24 = ((__int64 (__fastcall *)(struct IRowset *, const struct _GUID *, struct IUnknown **))v34->lpVtbl->QueryInterface)(
              v34,
              a5,
              a8);
      v25 = v24;
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048940[0] )
          bidTraceW(off_1800481D0[0], 149504, off_180048940[0], (unsigned int)v24, 146);
        ThrowHR(v25);
      }
    }
    catch ( long v42 )
    {
      v38 = v42;
      v21 = v40;
      v9 = v41;
      v10 = v43;
      v11 = v44;
    }
    v26 = 0;
    if ( v32 )
    {
      do
      {
        v27 = 0;
        v28 = v26;
        if ( v21[v28].cProperties )
        {
          do
          {
            VariantClear((VARIANTARG *)((char *)&v21[v28].rgProperties->vValue + 64 * v27 + 8 * v27));
            v27 = (unsigned int)(v27 + 1);
          }
          while ( (unsigned int)v27 < v21[v28].cProperties );
        }
        CoTaskMemFree(v21[v28].rgProperties);
        ++v26;
      }
      while ( v26 < v32 );
      v9 = v41;
    }
    v29 = Exit(v38, 0);
    CAutoP<_GUID>::~CAutoP<_GUID>(&v35);
    v30 = v21;
  }
  else
  {
    v29 = Exit(-2147024809, 0);
    CAutoP<_GUID>::~CAutoP<_GUID>(&v35);
    v30 = 0;
  }
  CoTaskMemFree(v30);
  CAutoP<_GUID>::~CAutoP<_GUID>(&v36);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v39);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v34);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
  --*v11;
  v14 = (*v10)-- == 1;
  if ( v14 )
    *(_DWORD *)(v9 + 8) = -1;
  v31 = *(_QWORD *)v9;
  --*(_DWORD *)(v31 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
  return v29;
}

```

## disassembly

```asm
0x180011f90  mov     rax, rsp
0x180011f93  mov     [rax+18h], rbx
0x180011f97  mov     [rax+20h], r9
0x180011f9b  mov     [rax+10h], rdx
0x180011f9f  mov     [rax+8], rcx
0x180011fa3  push    rdi
0x180011fa4  push    r12
0x180011fa6  push    r13
0x180011fa8  push    r14
0x180011faa  push    r15
0x180011fac  sub     rsp, 0B0h
0x180011fb3  mov     r13, r8
0x180011fb6  mov     r14, [rcx+18h]
0x180011fba  sub     r14, 0FFFFFFFFFFFFFF80h
0x180011fbe  mov     [rsp+0D8h+var_58], r14
0x180011fc6  mov     rcx, r14
0x180011fc9  call    cs:__imp_UMSEnterCSWraper
0x180011fcf  lea     r15, [r14+0Ch]
0x180011fd3  mov     [rsp+0D8h+var_48], r15
0x180011fdb  cmp     dword ptr [r15], 0
0x180011fdf  jnz     short loc_180011FEB
0x180011fe1  call    cs:__imp_GetCurrentThreadId
0x180011fe7  mov     [r14+8], eax
0x180011feb  inc     dword ptr [r15]
0x180011fee  lea     r12, [r14+10h]
0x180011ff2  mov     [rsp+0D8h+var_40], r12
0x180011ffa  inc     dword ptr [r12]
0x180011ffe  mov     [rsp+0D8h+var_38], r14
0x180012006  mov     [rsp+0D8h+var_78], 0
0x18001200f  mov     [rsp+0D8h+var_90], 0
0x180012018  mov     [rsp+0D8h+var_68], 0
0x180012021  mov     [rsp+0D8h+var_80], 0
0x18001202a  mov     [rsp+0D8h+var_94], 0
0x180012032  mov     [rsp+0D8h+var_98], 0
0x18001203a  mov     [rsp+0D8h+var_60], 0
0x180012043  mov     [rsp+0D8h+var_88], 0
0x18001204c  xor     edx, edx; perrinfo
0x18001204e  xor     ecx, ecx; dwReserved
0x180012050  call    cs:__imp_SetErrorInfo
0x180012056  mov     rax, [rsp+0D8h+arg_38]
0x18001205e  test    rax, rax
0x180012061  jz      loc_180012345
0x180012067  mov     rdi, [rsp+0D8h+arg_30]
0x18001206f  cmp     [rsp+0D8h+arg_28], 0
0x180012077  jbe     short loc_180012082
0x180012079  test    rdi, rdi
0x18001207c  jz      loc_180012345
0x180012082  test    r13, r13
0x180012085  jz      short loc_180012096
0x180012087  cmp     [rsp+0D8h+arg_18], 0
0x180012090  jz      loc_180012345
0x180012096  cmp     [rsp+0D8h+arg_8], 0
0x18001209f  jz      short loc_180012116
0x1800120a1  mov     ecx, 80040E22h; int
0x1800120a6  xor     edx, edx; unsigned int
0x1800120a8  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800120ad  mov     ebx, eax
0x1800120af  lea     rcx, [rsp+0D8h+var_88]
0x1800120b4  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800120b9  nop
0x1800120ba  xor     ecx, ecx; pv
0x1800120bc  call    cs:__imp_CoTaskMemFree
0x1800120c2  nop
0x1800120c3  lea     rcx, [rsp+0D8h+var_80]
0x1800120c8  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800120cd  nop
0x1800120ce  lea     rcx, [rsp+0D8h+var_68]
0x1800120d3  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800120d8  nop
0x1800120d9  lea     rcx, [rsp+0D8h+var_90]
0x1800120de  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800120e3  nop
0x1800120e4  lea     rcx, [rsp+0D8h+var_78]
0x1800120e9  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800120ee  nop
0x1800120ef  or      ecx, 0FFFFFFFFh
0x1800120f2  add     [r12], ecx
0x1800120f6  add     [r15], ecx
0x1800120f9  jnz     short loc_1800120FF
0x1800120fb  mov     [r14+8], ecx
0x1800120ff  mov     rcx, [r14]
0x180012102  dec     dword ptr [rcx+30h]
0x180012105  add     rcx, 8; lpCriticalSection
0x180012109  call    cs:__imp_LeaveCriticalSection
0x18001210f  mov     eax, ebx
0x180012111  jmp     loc_1800123B5
0x180012116  mov     qword ptr [rax], 0
0x18001211d  lea     rax, [rsp+0D8h+var_78]
0x180012122  mov     [rsp+0D8h+ppv], rax; ppv
0x180012127  lea     r9, IID_ICreateRowset; riid
0x18001212e  xor     edx, edx; pUnkOuter
0x180012130  lea     r8d, [rdx+1]; dwClsContext
0x180012134  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x18001213b  call    cs:__imp_CoCreateInstance
0x180012141  mov     [rsp+0D8h+var_70], eax
0x180012145  test    eax, eax
0x180012147  jns     short loc_180012150
0x180012149  mov     ecx, eax
0x18001214b  jmp     loc_1800120A6
0x180012150  mov     rcx, r13
0x180012153  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180012158  lea     rcx, [rsp+0D8h+var_88]
0x18001215d  mov     [rsp+0D8h+var_B0], rcx; unsigned int **
0x180012162  mov     rcx, [rsp+0D8h+arg_18]; this
0x18001216a  mov     [rsp+0D8h+ppv], rcx; struct tagDBID *
0x18001216f  mov     r9d, eax; unsigned int
0x180012172  lea     r8, [rsp+0D8h+var_80]; struct tagDBCOLUMNINFO **
0x180012177  lea     rdx, [rsp+0D8h+var_94]; unsigned int *
0x18001217c  call    ?SetupColumnsInfo@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBCOLUMNINFO@@KPEAUtagDBID@@PEAPEAK@Z; CImpIColumnsRowset::SetupColumnsInfo(ulong *,tagDBCOLUMNINFO * *,ulong,tagDBID *,ulong * *)
0x180012181  mov     [rsp+0D8h+ppv], rdi; struct tagDBPROPSET *
0x180012186  mov     r9d, [rsp+0D8h+arg_28]; unsigned int
0x18001218e  lea     r8, [rsp+0D8h+var_60]; struct tagDBPROPSET **
0x180012193  lea     rdx, [rsp+0D8h+var_98]; unsigned int *
0x180012198  call    ?SetupProperties@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBPROPSET@@KPEAU2@@Z; CImpIColumnsRowset::SetupProperties(ulong *,tagDBPROPSET * *,ulong,tagDBPROPSET *)
0x18001219d  mov     rcx, [rsp+0D8h+var_78]
0x1800121a2  mov     rax, [rcx]
0x1800121a5  lea     rdx, [rsp+0D8h+var_90]
0x1800121aa  mov     [rsp+0D8h+var_B0], rdx
0x1800121af  mov     rdi, [rsp+0D8h+var_80]
0x1800121b4  mov     [rsp+0D8h+ppv], rdi
0x1800121b9  mov     r9d, [rsp+0D8h+var_94]
0x1800121be  mov     rbx, [rsp+0D8h+var_60]
0x1800121c3  mov     r8, rbx
0x1800121c6  mov     edx, [rsp+0D8h+var_98]
0x1800121ca  mov     rax, [rax+18h]
0x1800121ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121d3  mov     r13d, eax
0x1800121d6  test    eax, eax
0x1800121d8  jns     short loc_18001221A
0x1800121da  test    byte ptr cs:_bidGblFlags, 2
0x1800121e1  jz      short loc_180012212
0x1800121e3  mov     rcx, cs:off_180048948; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x1800121ea  test    rcx, rcx
0x1800121ed  jz      short loc_180012212
0x1800121ef  mov     dword ptr [rsp+0D8h+ppv], 8Eh
0x1800121f7  mov     r9d, eax
0x1800121fa  mov     r8, cs:off_180048948; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x180012201  mov     edx, 23800h
0x180012206  mov     rcx, cs:off_1800481D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001220d  call    _bidTraceW
0x180012212  mov     ecx, r13d; int
0x180012215  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001221a  mov     rax, [rsp+0D8h+var_88]
0x18001221f  mov     [rsp+0D8h+ppv], rax; unsigned int *
0x180012224  mov     r9, rdi; struct tagDBCOLUMNINFO *
0x180012227  mov     r8d, [rsp+0D8h+var_94]; unsigned int
0x18001222c  mov     rdx, [rsp+0D8h+var_90]; struct IRowset *
0x180012231  mov     rcx, [rsp+0D8h+arg_0]; this
0x180012239  call    ?AddData@CImpIColumnsRowset@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@PEAK@Z; CImpIColumnsRowset::AddData(IRowset *,ulong,tagDBCOLUMNINFO *,ulong *)
0x18001223e  mov     rcx, [rsp+0D8h+var_90]
0x180012243  mov     rax, [rcx]
0x180012246  mov     r8, [rsp+0D8h+arg_38]
0x18001224e  mov     rdx, [rsp+0D8h+arg_20]
0x180012256  mov     rax, [rax]
0x180012259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225e  mov     edi, eax
0x180012260  test    eax, eax
0x180012262  jns     short loc_1800122A4
0x180012264  test    byte ptr cs:_bidGblFlags, 2
0x18001226b  jz      short loc_18001229C
0x18001226d  mov     rcx, cs:off_180048940; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x180012274  test    rcx, rcx
0x180012277  jz      short loc_18001229C
0x180012279  mov     dword ptr [rsp+0D8h+ppv], 92h
0x180012281  mov     r9d, eax
0x180012284  mov     r8, cs:off_180048940; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x18001228b  mov     edx, 24800h
0x180012290  mov     rcx, cs:off_1800481D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012297  call    _bidTraceW
0x18001229c  mov     ecx, edi; int
0x18001229e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800122a4  jmp     short loc_1800122CE
0x1800122a6  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x1800122ad  mov     [rsp+0D8h+var_70], eax
0x1800122b1  mov     rbx, [rsp+0D8h+var_60]
0x1800122b6  mov     r14, [rsp+0D8h+var_58]
0x1800122be  mov     r15, [rsp+0D8h+var_48]
0x1800122c6  mov     r12, [rsp+0D8h+var_40]
0x1800122ce  xor     r13d, r13d
0x1800122d1  cmp     [rsp+0D8h+var_98], r13d
0x1800122d6  jbe     short loc_180012328
0x1800122d8  xor     r14d, r14d
0x1800122db  mov     edi, r13d
0x1800122de  shl     rdi, 5
0x1800122e2  cmp     [rdi+rbx+8], r14d
0x1800122e7  jbe     short loc_18001230C
0x1800122e9  lea     rcx, ds:6[r14*8]
0x1800122f1  mov     rax, [rdi+rbx]
0x1800122f5  add     rcx, r14
0x1800122f8  lea     rcx, [rax+rcx*8]; pvarg
0x1800122fc  call    cs:__imp_VariantClear
0x180012302  inc     r14d
0x180012305  cmp     r14d, [rdi+rbx+8]
0x18001230a  jb      short loc_1800122E9
0x18001230c  mov     rcx, [rdi+rbx]; pv
0x180012310  call    cs:__imp_CoTaskMemFree
0x180012316  inc     r13d
0x180012319  cmp     r13d, [rsp+0D8h+var_98]
0x18001231e  jb      short loc_1800122D8
0x180012320  mov     r14, [rsp+0D8h+var_58]
0x180012328  xor     edx, edx; unsigned int
0x18001232a  mov     ecx, [rsp+0D8h+var_70]; int
0x18001232e  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180012333  mov     edi, eax
0x180012335  lea     rcx, [rsp+0D8h+var_88]
0x18001233a  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x18001233f  nop
0x180012340  mov     rcx, rbx
0x180012343  jmp     short loc_180012360
0x180012345  xor     edx, edx; unsigned int
0x180012347  mov     ecx, 80070057h; int
0x18001234c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180012351  mov     edi, eax
0x180012353  lea     rcx, [rsp+0D8h+var_88]
0x180012358  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x18001235d  nop
0x18001235e  xor     ecx, ecx; pv
0x180012360  call    cs:__imp_CoTaskMemFree
0x180012366  nop
0x180012367  lea     rcx, [rsp+0D8h+var_80]
0x18001236c  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180012371  nop
0x180012372  lea     rcx, [rsp+0D8h+var_68]
0x180012377  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001237c  nop
0x18001237d  lea     rcx, [rsp+0D8h+var_90]
0x180012382  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012387  nop
0x180012388  lea     rcx, [rsp+0D8h+var_78]
0x18001238d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012392  nop
0x180012393  or      ecx, 0FFFFFFFFh
0x180012396  add     [r12], ecx
0x18001239a  add     [r15], ecx
0x18001239d  jnz     short loc_1800123A3
0x18001239f  mov     [r14+8], ecx
0x1800123a3  mov     rcx, [r14]
0x1800123a6  dec     dword ptr [rcx+30h]
0x1800123a9  add     rcx, 8; lpCriticalSection
0x1800123ad  call    cs:__imp_LeaveCriticalSection
0x1800123b3  mov     eax, edi
0x1800123b5  mov     rbx, [rsp+0D8h+arg_10]
0x1800123bd  add     rsp, 0B0h
0x1800123c4  pop     r15
0x1800123c6  pop     r14
0x1800123c8  pop     r13
0x1800123ca  pop     r12
0x1800123cc  pop     rdi
0x1800123cd  retn
```
