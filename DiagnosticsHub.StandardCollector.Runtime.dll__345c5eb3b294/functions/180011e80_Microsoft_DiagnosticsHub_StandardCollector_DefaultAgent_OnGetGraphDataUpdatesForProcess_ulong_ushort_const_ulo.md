# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::OnGetGraphDataUpdatesForProcess(ulong,ushort * const,ulong *,CollectorGraphPoint * * const,ulong *,CollectorGraphProcess * * const)

- ea: `0x180011e80`
- end: `0x180012406`
- name: `?OnGetGraphDataUpdatesForProcess@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJKQEAGPEAKQEAPEAUCollectorGraphPoint@@1QEAPEAUCollectorGraphProcess@@@Z`
- size: `1414`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, unsigned int, unsigned __int16 *const, unsigned int *, struct CollectorGraphPoint **const, unsigned int *, struct CollectorGraphProcess **const)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x18000334c`
- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x180011e80`
- `0x180012408`
- `0x180014d50`
- `0x180014e60`
- `0x180015548`
- `0x180049b50`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18001219b`
- `VCRUNTIME140!memset` at `0x18001220f`
- `VCRUNTIME140!memset` at `0x18001219b`
- `VCRUNTIME140!memset` at `0x18001220f`
- `VCRUNTIME140!memmove` at `0x1800120c5`
- `VCRUNTIME140!memmove` at `0x1800120dd`
- `VCRUNTIME140!memmove` at `0x18001228e`
- `VCRUNTIME140!memmove` at `0x1800120c5`
- `VCRUNTIME140!memmove` at `0x1800120dd`
- `VCRUNTIME140!memmove` at `0x18001228e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800123c4`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800123c4`
- `KERNEL32!AcquireSRWLockShared` at `0x180011f17`
- `KERNEL32!AcquireSRWLockShared` at `0x180011f17`
- `ole32!CoTaskMemAlloc` at `0x18001217d`
- `ole32!CoTaskMemAlloc` at `0x1800121d8`
- `ole32!CoTaskMemAlloc` at `0x18001217d`
- `ole32!CoTaskMemAlloc` at `0x1800121d8`
- `ole32!CoTaskMemFree` at `0x180012365`
- `ole32!CoTaskMemFree` at `0x180012396`
- `ole32!CoTaskMemFree` at `0x180012365`
- `ole32!CoTaskMemFree` at `0x180012396`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012332`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012332`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::OnGetGraphDataUpdatesForProcess(
        RTL_SRWLOCK *this,
        int a2,
        unsigned __int16 *const a3,
        unsigned int *a4,
        struct CollectorGraphPoint **const a5,
        unsigned int *a6,
        struct CollectorGraphProcess **const a7)
{
  unsigned __int16 *v7; // r15
  int v8; // ebx
  unsigned __int64 v10; // rsi
  RTL_SRWLOCK *v11; // r12
  struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters **Ptr; // rdi
  unsigned int v13; // r14d
  int GraphDataUpdates; // eax
  unsigned int v15; // ebx
  struct CollectorGraphPoint *v16; // r12
  __int64 v17; // rcx
  int v18; // r8d
  __int64 v19; // rdx
  void *v20; // r15
  signed __int64 v21; // rbx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  char *v25; // r14
  char *v26; // rcx
  bool v27; // zf
  const void *v28; // rdx
  char *v29; // r8
  void *v30; // rcx
  struct CollectorGraphPoint *v31; // rdi
  unsigned int v32; // eax
  struct CollectorGraphPoint *v33; // rax
  _QWORD *v34; // rbx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  struct CollectorGraphPoint *v37; // r14
  unsigned __int16 *v38; // r13
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // r15
  _QWORD *v42; // r12
  unsigned int v43; // r13d
  unsigned int v44; // ebx
  __int64 v45; // rcx
  unsigned int v48; // [rsp+34h] [rbp-BDh]
  unsigned int v49[2]; // [rsp+38h] [rbp-B9h] BYREF
  struct CollectorGraphPoint *v50; // [rsp+40h] [rbp-B1h] BYREF
  unsigned __int16 *v51; // [rsp+48h] [rbp-A9h]
  struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters **v52; // [rsp+50h] [rbp-A1h]
  unsigned int *v53; // [rsp+58h] [rbp-99h]
  struct CollectorGraphPoint **v54; // [rsp+60h] [rbp-91h]
  unsigned int *v55; // [rsp+68h] [rbp-89h]
  struct CollectorGraphProcess **v56; // [rsp+70h] [rbp-81h]
  RTL_SRWLOCK *v57; // [rsp+78h] [rbp-79h]
  int v58; // [rsp+80h] [rbp-71h]
  __int64 v59; // [rsp+88h] [rbp-69h] BYREF
  unsigned int v60; // [rsp+90h] [rbp-61h]
  int v61; // [rsp+98h] [rbp-59h]
  _QWORD v62[3]; // [rsp+A0h] [rbp-51h] BYREF
  int v63; // [rsp+B8h] [rbp-39h] BYREF
  void *Src[2]; // [rsp+C0h] [rbp-31h] BYREF
  char *v65; // [rsp+D0h] [rbp-21h]
  __int128 v66; // [rsp+D8h] [rbp-19h] BYREF
  __int64 v67; // [rsp+E8h] [rbp-9h]

  v53 = a4;
  v7 = a3;
  v51 = a3;
  v8 = a2;
  v54 = a5;
  v55 = a6;
  v56 = a7;
  v10 = 0;
  if ( !a3 || !a4 || !a5 )
    return 2147500035LL;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v11 = this + 19;
  v57 = this + 19;
  v58 = 0;
  AcquireSRWLockShared(this + 19);
  Ptr = (struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters **)this[21].Ptr;
  v52 = (struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters **)this[22].Ptr;
  if ( Ptr == v52 )
    goto LABEL_57;
  v63 = 0;
  v13 = 0;
  v48 = 0;
  *(_OWORD *)Src = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v62[0] = &v63;
  v62[1] = Src;
  v62[2] = &v66;
  while ( v8 && *(_DWORD *)*Ptr != v8 )
  {
LABEL_32:
    if ( ++Ptr == v52 )
    {
      v31 = 0;
      if ( !v13 )
      {
        v32 = 0;
        goto LABEL_35;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 0x20 )
      {
LABEL_48:
        LODWORD(v10) = -2147024882;
        v63 = -2147024882;
      }
      else
      {
        v32 = 32 * v13;
        if ( 32 * (unsigned __int64)v13 > 0x7FFFFFFF )
        {
          v31 = 0;
          goto LABEL_48;
        }
LABEL_35:
        v33 = (struct CollectorGraphPoint *)CoTaskMemAlloc(v32);
        v31 = v33;
        if ( !v33 )
          goto LABEL_48;
        memset(v33, 0, 32LL * v13);
        v34 = 0;
        v35 = (*((_QWORD *)&v66 + 1) - (_QWORD)v66) / 24LL;
        if ( !v35 )
        {
          LODWORD(v36) = 0;
          goto LABEL_38;
        }
        if ( 0xFFFFFFFFFFFFFFFFuLL / v35 < 0x10 )
        {
LABEL_53:
          LODWORD(v10) = -2147024882;
          v63 = -2147024882;
        }
        else
        {
          v36 = 16 * v35;
          if ( v36 > 0x7FFFFFFF )
          {
            v34 = 0;
            goto LABEL_53;
          }
LABEL_38:
          v34 = CoTaskMemAlloc((unsigned int)v36);
          if ( !v34 )
            goto LABEL_53;
          memset(v34, 0, 16 * ((*((_QWORD *)&v66 + 1) - (_QWORD)v66) / 24LL));
          v37 = v31;
          v38 = (unsigned __int16 *)v34;
          v39 = *((_QWORD *)&v66 + 1);
          v40 = v66;
          if ( (*((_QWORD *)&v66 + 1) - (_QWORD)v66) / 24LL )
          {
            v41 = 0;
            v42 = v34 + 1;
            v51 = (unsigned __int16 *)v34;
            v43 = 0;
            do
            {
              v44 = *(_DWORD *)(v40 + v41 + 8);
              v45 = *(_QWORD *)(v40 + v41);
              *((_DWORD *)v42 - 2) = *(_DWORD *)(v40 + v41 + 16);
              *((_DWORD *)v42 - 1) = v44;
              *v42 = v45;
              memmove((char *)v31 + 32 * v43, *((const void **)Src[0] + v10), 32LL * v44);
              v43 += v44;
              ++v10;
              v41 += 24;
              v42 += 2;
              v39 = *((_QWORD *)&v66 + 1);
              v40 = v66;
            }
            while ( v10 < (*((_QWORD *)&v66 + 1) - (_QWORD)v66) / 24LL );
            v38 = v51;
          }
          *v53 = v48;
          v31 = 0;
          *v54 = v37;
          *v55 = (v39 - v40) / 24;
          v34 = 0;
          *v56 = (struct CollectorGraphProcess *)v38;
          LODWORD(v10) = v63;
        }
        CoTaskMemFree(v34);
      }
      CoTaskMemFree(v31);
      goto LABEL_56;
    }
  }
  v49[0] = 0;
  v50 = 0;
  GraphDataUpdates = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetGraphDataUpdates(
                       (Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *)&this[-1],
                       *Ptr,
                       v7,
                       v49,
                       &v50);
  v63 = GraphDataUpdates;
  if ( !GraphDataUpdates )
  {
    v15 = v49[0];
    if ( v49[0] )
    {
      v16 = v50;
      if ( v50 )
      {
        v17 = *((_QWORD *)*Ptr + 1);
        v18 = *(_DWORD *)*Ptr;
        v59 = v17;
        v60 = v49[0];
        v61 = v18;
        v19 = *((_QWORD *)&v66 + 1);
        if ( *((_QWORD *)&v66 + 1) == v67 )
        {
          std::vector<std::tuple<unsigned long,unsigned long,unsigned __int64>>::_Emplace_reallocate<std::tuple<unsigned long,unsigned long,unsigned __int64>>(
            &v66,
            *((_QWORD *)&v66 + 1),
            &v59);
        }
        else
        {
          **((_QWORD **)&v66 + 1) = v17;
          *(_DWORD *)(v19 + 8) = v15;
          *(_DWORD *)(v19 + 16) = v18;
          *((_QWORD *)&v66 + 1) += 24LL;
        }
        v13 += v15;
        v48 = v13;
        v20 = Src[1];
        if ( Src[1] == v65 )
        {
          v21 = ((char *)Src[1] - (char *)Src[0]) >> 3;
          if ( v21 == 0x1FFFFFFFFFFFFFFFLL )
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(
              v65,
              v19);
          v50 = (struct CollectorGraphPoint *)(v21 + 1);
          v22 = (v65 - (char *)Src[0]) >> 3;
          if ( v22 <= 0x1FFFFFFFFFFFFFFFLL - (v22 >> 1) )
          {
            v24 = (v22 >> 1) + v22;
            v23 = v21 + 1;
            if ( v24 >= v21 + 1 )
              v23 = v24;
            if ( v23 > 0x1FFFFFFFFFFFFFFFLL )
              __scrt_throw_std_bad_array_new_length();
          }
          else
          {
            v23 = 0x1FFFFFFFFFFFFFFFLL;
          }
          _mm_lfence();
          *(_QWORD *)v49 = 8 * v23;
          v25 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(8 * v23);
          *(_QWORD *)&v25[8 * v21] = v16;
          v26 = v25;
          v27 = v20 == Src[1];
          _mm_lfence();
          v28 = Src[0];
          if ( v27 )
          {
            v29 = (char *)((char *)Src[1] - (char *)Src[0]);
          }
          else
          {
            memmove(v25, Src[0], (size_t)v20 - (unsigned __int64)Src[0]);
            v29 = (char *)((char *)Src[1] - (char *)v20);
            v26 = &v25[8 * v21 + 8];
            v28 = v20;
          }
          memmove(v26, v28, (size_t)v29);
          v30 = Src[0];
          if ( Src[0] )
          {
            if ( ((v65 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
            {
              _mm_lfence();
              v30 = (void *)*((_QWORD *)Src[0] - 1);
              if ( (unsigned __int64)((char *)Src[0] - (char *)v30 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            operator delete(v30);
          }
          Src[0] = v25;
          Src[1] = &v25[8 * (_QWORD)v50];
          v65 = &v25[*(_QWORD *)v49];
          v13 = v48;
        }
        else
        {
          *(_QWORD *)Src[1] = v16;
          Src[1] = (char *)Src[1] + 8;
        }
        v7 = v51;
      }
    }
    v8 = a2;
    goto LABEL_32;
  }
  LODWORD(v10) = GraphDataUpdates;
LABEL_56:
  DiagHubCommon::ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___::_ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___(v62);
  std::vector<std::tuple<unsigned long,unsigned long,unsigned __int64>>::~vector<std::tuple<unsigned long,unsigned long,unsigned __int64>>(&v66);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(Src);
  v11 = v57;
LABEL_57:
  ReleaseSRWLockShared(v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011e80  mov     [rsp-8+arg_8], rbx
0x180011e85  push    rbp
0x180011e86  push    rsi
0x180011e87  push    rdi
0x180011e88  push    r12
0x180011e8a  push    r13
0x180011e8c  push    r14
0x180011e8e  push    r15
0x180011e90  lea     rbp, [rsp-0Fh]
0x180011e95  sub     rsp, 100h
0x180011e9c  mov     rax, cs:__security_cookie
0x180011ea3  xor     rax, rsp
0x180011ea6  mov     [rbp+3Fh+var_40], rax
0x180011eaa  mov     rax, r9
0x180011ead  mov     [rsp+130h+var_D8], rax
0x180011eb2  mov     r15, r8
0x180011eb5  mov     [rsp+130h+var_E8], r8
0x180011eba  mov     ebx, edx
0x180011ebc  mov     [rsp+130h+var_100], edx
0x180011ec0  mov     r13, rcx
0x180011ec3  mov     rcx, [rbp+3Fh+arg_20]
0x180011ec7  mov     [rsp+130h+var_D0], rcx
0x180011ecc  mov     rdx, [rbp+3Fh+arg_28]
0x180011ed0  mov     [rsp+130h+var_C8], rdx
0x180011ed5  mov     r8, [rbp+3Fh+arg_30]
0x180011ed9  mov     [rsp+130h+var_C0], r8
0x180011ede  xor     esi, esi
0x180011ee0  test    r15, r15
0x180011ee3  jz      loc_1800123CE
0x180011ee9  test    rax, rax
0x180011eec  jz      loc_1800123CE
0x180011ef2  test    rcx, rcx
0x180011ef5  jz      loc_1800123CE
0x180011efb  mov     [r9], esi
0x180011efe  mov     [rcx], rsi
0x180011f01  mov     [rdx], esi
0x180011f03  mov     [r8], rsi
0x180011f06  lea     r12, [r13+98h]
0x180011f0d  mov     [rbp+3Fh+var_B8], r12
0x180011f11  mov     [rbp+3Fh+var_B0], esi
0x180011f14  mov     rcx, r12; SRWLock
0x180011f17  call    cs:__imp_AcquireSRWLockShared
0x180011f1d  nop
0x180011f1e  mov     rdi, [r13+0A8h]
0x180011f25  mov     rax, [r13+0B0h]
0x180011f2c  mov     [rsp+130h+var_E0], rax
0x180011f31  cmp     rdi, rax
0x180011f34  jz      loc_1800123C1
0x180011f3a  mov     [rbp+3Fh+var_78], esi
0x180011f3d  mov     r14d, esi
0x180011f40  mov     [rsp+130h+var_FC], esi
0x180011f44  xorps   xmm1, xmm1
0x180011f47  movdqu  xmmword ptr [rbp+3Fh+Src], xmm1
0x180011f4c  mov     [rbp+3Fh+var_60], rsi
0x180011f50  movdqu  [rbp+3Fh+var_58], xmm1
0x180011f55  mov     [rbp+3Fh+var_48], rsi
0x180011f59  lea     rax, [rbp+3Fh+var_78]
0x180011f5d  mov     [rbp+3Fh+var_90], rax
0x180011f61  lea     rax, [rbp+3Fh+Src]
0x180011f65  mov     [rbp+3Fh+var_88], rax
0x180011f69  lea     rax, [rbp+3Fh+var_58]
0x180011f6d  mov     [rbp+3Fh+var_80], rax
0x180011f71  test    ebx, ebx
0x180011f73  jz      short loc_180011F80
0x180011f75  mov     rax, [rdi]
0x180011f78  cmp     [rax], ebx
0x180011f7a  jnz     loc_180012150
0x180011f80  mov     [rsp+130h+var_F8], esi
0x180011f84  mov     [rsp+130h+var_F0], rsi
0x180011f89  lea     rcx, [r13-8]; this
0x180011f8d  lea     rax, [rsp+130h+var_F0]
0x180011f92  mov     [rsp+130h+Reserved], rax; struct CollectorGraphPoint **
0x180011f97  lea     r9, [rsp+130h+var_F8]; unsigned int *
0x180011f9c  mov     r8, r15; unsigned __int16 *
0x180011f9f  mov     rdx, [rdi]; struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *
0x180011fa2  call    ?GetGraphDataUpdates@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVProcessCounters@234@QEAGPEAKQEAPEAUCollectorGraphPoint@@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetGraphDataUpdates(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters &,ushort * const,ulong *,CollectorGraphPoint * * const)
0x180011fa7  mov     [rbp+3Fh+var_78], eax
0x180011faa  test    eax, eax
0x180011fac  jnz     loc_18001239E
0x180011fb2  mov     ebx, [rsp+130h+var_F8]
0x180011fb6  test    ebx, ebx
0x180011fb8  jz      loc_18001214C
0x180011fbe  mov     r12, [rsp+130h+var_F0]
0x180011fc3  test    r12, r12
0x180011fc6  jz      loc_18001214C
0x180011fcc  mov     rax, [rdi]
0x180011fcf  mov     rcx, [rax+8]
0x180011fd3  mov     r8d, [rax]
0x180011fd6  mov     [rbp+3Fh+var_A8], rcx
0x180011fda  mov     [rbp+3Fh+var_A0], ebx
0x180011fdd  mov     [rbp+3Fh+var_98], r8d
0x180011fe1  mov     rdx, qword ptr [rbp+3Fh+var_58+8]
0x180011fe5  cmp     rdx, [rbp+3Fh+var_48]
0x180011fe9  jz      short loc_180011FFC
0x180011feb  mov     [rdx], rcx
0x180011fee  mov     [rdx+8], ebx
0x180011ff1  mov     [rdx+10h], r8d
0x180011ff5  add     qword ptr [rbp+3Fh+var_58+8], 18h
0x180011ffa  jmp     short loc_180012009
0x180011ffc  lea     r8, [rbp+3Fh+var_A8]
0x180012000  lea     rcx, [rbp+3Fh+var_58]
0x180012004  call    ??$_Emplace_reallocate@V?$tuple@KK_K@std@@@?$vector@V?$tuple@KK_K@std@@V?$allocator@V?$tuple@KK_K@std@@@2@@std@@AEAAPEAV?$tuple@KK_K@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<ulong,ulong,unsigned __int64>>::_Emplace_reallocate<std::tuple<ulong,ulong,unsigned __int64>>(std::tuple<ulong,ulong,unsigned __int64> * const,std::tuple<ulong,ulong,unsigned __int64> &&)
0x180012009  add     r14d, ebx
0x18001200c  mov     [rsp+130h+var_FC], r14d
0x180012011  mov     r15, [rbp+3Fh+Src+8]
0x180012015  mov     rcx, [rbp+3Fh+var_60]
0x180012019  cmp     r15, rcx
0x18001201c  jz      short loc_18001202B
0x18001201e  mov     [r15], r12
0x180012021  add     [rbp+3Fh+Src+8], 8
0x180012026  jmp     loc_180012147
0x18001202b  mov     rbx, r15
0x18001202e  sub     rbx, [rbp+3Fh+Src]
0x180012032  sar     rbx, 3
0x180012036  mov     r9, 1FFFFFFFFFFFFFFFh
0x180012040  cmp     rbx, r9
0x180012043  jz      loc_1800123FA
0x180012049  lea     r8, [rbx+1]
0x18001204d  mov     [rsp+130h+var_F0], r8
0x180012052  sub     rcx, [rbp+3Fh+Src]
0x180012056  sar     rcx, 3
0x18001205a  mov     rdx, rcx
0x18001205d  shr     rdx, 1
0x180012060  mov     rax, r9
0x180012063  sub     rax, rdx
0x180012066  cmp     rcx, rax
0x180012069  jbe     short loc_180012070
0x18001206b  mov     rcx, r9
0x18001206e  jmp     short loc_180012087
0x180012070  lea     rax, [rdx+rcx]
0x180012074  mov     rcx, r8
0x180012077  cmp     rax, r8
0x18001207a  cmovnb  rcx, rax
0x18001207e  cmp     rcx, r9
0x180012081  ja      loc_180012400
0x180012087  lfence
0x18001208a  lea     rax, ds:0[rcx*8]
0x180012092  mov     qword ptr [rsp+130h+var_F8], rax
0x180012097  mov     rcx, rax
0x18001209a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001209f  mov     r14, rax
0x1800120a2  mov     [rax+rbx*8], r12
0x1800120a6  mov     rcx, rax; void *
0x1800120a9  cmp     r15, [rbp+3Fh+Src+8]
0x1800120ad  lfence
0x1800120b0  mov     rdx, [rbp+3Fh+Src]; Src
0x1800120b4  jnz     short loc_1800120BF
0x1800120b6  mov     r8, [rbp+3Fh+Src+8]
0x1800120ba  sub     r8, rdx
0x1800120bd  jmp     short loc_1800120DD
0x1800120bf  mov     r8, r15
0x1800120c2  sub     r8, rdx; Size
0x1800120c5  call    cs:__imp_memmove
0x1800120cb  mov     r8, [rbp+3Fh+Src+8]
0x1800120cf  sub     r8, r15; Size
0x1800120d2  lea     rcx, [rbx+1]
0x1800120d6  lea     rcx, [r14+rcx*8]; void *
0x1800120da  mov     rdx, r15; Src
0x1800120dd  call    cs:__imp_memmove
0x1800120e3  mov     rcx, [rbp+3Fh+Src]
0x1800120e7  test    rcx, rcx
0x1800120ea  jz      short loc_180012125
0x1800120ec  mov     rdx, [rbp+3Fh+var_60]
0x1800120f0  sub     rdx, rcx
0x1800120f3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800120f7  cmp     rdx, 1000h
0x1800120fe  jb      short loc_180012120
0x180012100  lfence
0x180012103  add     rdx, 27h ; '''
0x180012107  mov     rax, [rbp+3Fh+Src]
0x18001210b  mov     rcx, [rax-8]; Block
0x18001210f  sub     rax, rcx
0x180012112  sub     rax, 8
0x180012116  cmp     rax, 1Fh
0x18001211a  ja      loc_180012323
0x180012120  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012125  mov     [rbp+3Fh+Src], r14
0x180012129  mov     rax, [rsp+130h+var_F0]
0x18001212e  lea     rax, [r14+rax*8]
0x180012132  mov     [rbp+3Fh+Src+8], rax
0x180012136  mov     rax, qword ptr [rsp+130h+var_F8]
0x18001213b  add     rax, r14
0x18001213e  mov     [rbp+3Fh+var_60], rax
0x180012142  mov     r14d, [rsp+130h+var_FC]
0x180012147  mov     r15, [rsp+130h+var_E8]
0x18001214c  mov     ebx, [rsp+130h+var_100]
0x180012150  add     rdi, 8
0x180012154  cmp     rdi, [rsp+130h+var_E0]
0x180012159  jnz     loc_180011F71
0x18001215f  mov     rdi, rsi
0x180012162  mov     ebx, r14d
0x180012165  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012169  mov     r15d, 7FFFFFFFh
0x18001216f  test    r14d, r14d
0x180012172  jnz     loc_180012339
0x180012178  mov     rax, rsi
0x18001217b  mov     ecx, eax; cb
0x18001217d  call    cs:__imp_CoTaskMemAlloc
0x180012183  mov     rdi, rax
0x180012186  test    rax, rax
0x180012189  jz      loc_18001235A
0x18001218f  shl     rbx, 5
0x180012193  mov     r8, rbx; Size
0x180012196  xor     edx, edx; Val
0x180012198  mov     rcx, rax; void *
0x18001219b  call    cs:__imp_memset
0x1800121a1  mov     rbx, rsi
0x1800121a4  mov     rcx, qword ptr [rbp+3Fh+var_58+8]
0x1800121a8  sub     rcx, qword ptr [rbp+3Fh+var_58]
0x1800121ac  mov     r14, 2AAAAAAAAAAAAAABh
0x1800121b6  mov     rax, r14
0x1800121b9  imul    rcx
0x1800121bc  mov     rcx, rdx
0x1800121bf  sar     rcx, 2
0x1800121c3  mov     rax, rcx
0x1800121c6  shr     rax, 3Fh
0x1800121ca  add     rcx, rax
0x1800121cd  jnz     loc_18001236D
0x1800121d3  mov     rcx, rsi
0x1800121d6  mov     ecx, ecx; cb
0x1800121d8  call    cs:__imp_CoTaskMemAlloc
0x1800121de  mov     rbx, rax
0x1800121e1  test    rax, rax
0x1800121e4  jz      loc_18001238B
0x1800121ea  mov     rcx, qword ptr [rbp+3Fh+var_58+8]
0x1800121ee  sub     rcx, qword ptr [rbp+3Fh+var_58]
0x1800121f2  mov     rax, r14
0x1800121f5  imul    rcx
0x1800121f8  sar     rdx, 2
0x1800121fc  mov     r8, rdx
0x1800121ff  shr     r8, 3Fh
0x180012203  add     r8, rdx
0x180012206  shl     r8, 4; Size
0x18001220a  xor     edx, edx; Val
0x18001220c  mov     rcx, rbx; void *
0x18001220f  call    cs:__imp_memset
0x180012215  mov     r14, rdi
0x180012218  mov     r13, rbx
0x18001221b  mov     r8, qword ptr [rbp+3Fh+var_58+8]
0x18001221f  mov     rcx, r8
0x180012222  mov     r9, qword ptr [rbp+3Fh+var_58]
0x180012226  sub     rcx, r9
0x180012229  mov     rax, 2AAAAAAAAAAAAAABh
0x180012233  imul    rcx
0x180012236  sar     rdx, 2
0x18001223a  mov     rax, rdx
0x18001223d  shr     rax, 3Fh
0x180012241  add     rdx, rax
0x180012244  jz      loc_1800122D8
0x18001224a  mov     r15, rsi
0x18001224d  lea     r12, [rbx+8]
0x180012251  mov     [rsp+130h+var_E8], rbx
0x180012256  mov     r13d, esi
0x180012259  mov     ebx, [r9+r15+8]
0x18001225e  mov     rcx, [r9+r15]
0x180012262  mov     eax, [r9+r15+10h]
0x180012267  mov     [r12-8], eax
0x18001226c  mov     [r12-4], ebx
0x180012271  mov     [r12], rcx
0x180012275  mov     r8d, ebx
0x180012278  shl     r8, 5; Size
0x18001227c  mov     ecx, r13d
0x18001227f  shl     rcx, 5
0x180012283  add     rcx, rdi; void *
0x180012286  mov     rdx, [rbp+3Fh+Src]
0x18001228a  mov     rdx, [rdx+rsi*8]; Src
0x18001228e  call    cs:__imp_memmove
0x180012294  add     r13d, ebx
0x180012297  inc     rsi
0x18001229a  lea     r15, [r15+18h]
0x18001229e  lea     r12, [r12+10h]
0x1800122a3  mov     r8, qword ptr [rbp+3Fh+var_58+8]
0x1800122a7  mov     rcx, r8
0x1800122aa  mov     r9, qword ptr [rbp+3Fh+var_58]
0x1800122ae  sub     rcx, r9
0x1800122b1  mov     rax, 2AAAAAAAAAAAAAABh
0x1800122bb  imul    rcx
0x1800122be  sar     rdx, 2
0x1800122c2  mov     rax, rdx
0x1800122c5  shr     rax, 3Fh
0x1800122c9  add     rdx, rax
0x1800122cc  cmp     rsi, rdx
0x1800122cf  jb      short loc_180012259
0x1800122d1  xor     esi, esi
0x1800122d3  mov     r13, [rsp+130h+var_E8]
0x1800122d8  mov     ecx, [rsp+130h+var_FC]
0x1800122dc  mov     rdx, [rsp+130h+var_D8]
0x1800122e1  mov     [rdx], ecx
0x1800122e3  mov     rdi, rsi
0x1800122e6  mov     rcx, [rsp+130h+var_D0]
0x1800122eb  mov     [rcx], r14
0x1800122ee  sub     r8, r9
0x1800122f1  mov     rax, 2AAAAAAAAAAAAAABh
0x1800122fb  imul    r8
0x1800122fe  sar     rdx, 2
0x180012302  mov     rax, rdx
0x180012305  shr     rax, 3Fh
0x180012309  add     rdx, rax
0x18001230c  mov     rax, [rsp+130h+var_C8]
0x180012311  mov     [rax], edx
  ... truncated ...
```
