# CGeofenceStore::GetClosestGeofencesNearPosition(double,double,ulong,ulong,ulong *,ulong *,GEOFENCE_INFORMATION * *,ulong,ulong *,GEOFENCE_INFORMATION * *)

- ea: `0x1800fe780`
- end: `0x1800fec36`
- name: `?GetClosestGeofencesNearPosition@CGeofenceStore@@UEAAJNNKKPEAK0PEAPEAUGEOFENCE_INFORMATION@@K01@Z`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(CGeofenceStore *__hidden this@<rcx>, double@<xmm1>, double@<xmm2>, unsigned int@<r9d>, unsigned int, unsigned int *, unsigned int *, struct GEOFENCE_INFORMATION **, unsigned int, unsigned int *, struct GEOFENCE_INFORMATION **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000522c`
- `0x180012194`
- `0x1800123c0`
- `0x180021450`
- `0x1800425cc`
- `0x1800714d8`
- `0x180082c38`
- `0x1800831e0`
- `0x18009a6cc`
- `0x1800a98c0`
- `0x1800fe780`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fea0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fea0f`

## pseudocode

```c
__int64 __fastcall CGeofenceStore::GetClosestGeofencesNearPosition(
        CGeofenceStore *this,
        double a2,
        double a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7,
        struct GEOFENCE_INFORMATION **a8,
        unsigned int a9,
        unsigned int *a10,
        struct GEOFENCE_INFORMATION **a11)
{
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // r9d
  int GeofenceAppDataHandler; // ebx
  int v16; // eax
  __int64 v17; // rdi
  unsigned int v18; // edx
  int v19; // edx
  int v20; // r8d
  char *v21; // r14
  unsigned __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rax
  struct GEOFENCE_INFORMATION *v25; // r15
  unsigned __int64 v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rax
  struct GEOFENCE_INFORMATION **v29; // rax
  struct GEOFENCE_INFORMATION **v30; // rax
  int v32; // eax
  int v33; // [rsp+58h] [rbp-A1h] BYREF
  int v34; // [rsp+5Ch] [rbp-9Dh] BYREF
  struct GEOFENCE_INFORMATION **v35; // [rsp+60h] [rbp-99h] BYREF
  struct GEOFENCE_INFORMATION **v36; // [rsp+68h] [rbp-91h] BYREF
  __int128 v37; // [rsp+70h] [rbp-89h] BYREF
  double v38; // [rsp+80h] [rbp-79h] BYREF
  _BYTE v39[16]; // [rsp+88h] [rbp-71h] BYREF
  __int128 v40; // [rsp+98h] [rbp-61h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-51h]
  __int128 v42; // [rsp+B0h] [rbp-49h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-39h]

  v36 = a8;
  v35 = a11;
  v42 = 0;
  v33 = a4;
  v40 = 0;
  v43 = 0;
  v41 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v39,
    (char *)this + 120);
  if ( a8 && a7 && a6 && a10 && a11 )
  {
    GeofenceAppDataHandler = 0;
    *a8 = 0;
    *a7 = 0;
    *a11 = 0;
    *a10 = 0;
  }
  else
  {
    GeofenceAppDataHandler = -2147024809;
  }
  if ( *((_BYTE *)this + 160) )
  {
    if ( GeofenceAppDataHandler >= 0 )
      GeofenceAppDataHandler = -2147467260;
    goto LABEL_11;
  }
  if ( GeofenceAppDataHandler < 0 )
  {
LABEL_11:
    if ( (unsigned int)dword_1801DDEF8 > 5 )
    {
      v33 = GeofenceAppDataHandler;
      if ( a10 )
        v16 = *a10;
      else
        v16 = 0;
      v34 = v16;
      if ( a7 )
        v32 = *a7;
      else
        v32 = 0;
      LODWORD(v35) = v32;
      LODWORD(v36) = a5;
      v38 = a3;
      *(double *)&v37 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)word_1801B0E92,
        v13,
        v14,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33);
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v39);
    if ( (_QWORD)v40 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(v40, *((_QWORD *)&v40 + 1));
      std::_Deallocate<16>((void *)v40, (v41 - v40) & 0xFFFFFFFFFFFFFFF0uLL);
      v41 = 0;
      v40 = 0;
    }
    if ( (_QWORD)v42 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(v42, *((_QWORD *)&v42 + 1));
      std::_Deallocate<16>((void *)v42, (v43 - v42) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return (unsigned int)GeofenceAppDataHandler;
  }
  v17 = 0;
  if ( a5 )
  {
    while ( 1 )
    {
      v18 = a6[v17];
      v37 = 0;
      GeofenceAppDataHandler = CGeofenceStore::GetGeofenceAppDataHandler(this, v18);
      if ( GeofenceAppDataHandler < 0 )
        break;
      GeofenceAppDataHandler = CGeofenceDataManagement::GetClosestGeofencesToPosition(
                                 v37,
                                 v19,
                                 v20,
                                 v33,
                                 (__int64)&v42,
                                 a9,
                                 (__int64)&v40);
      if ( GeofenceAppDataHandler < 0 )
        break;
      LODWORD(v12) = DWORD2(v37);
      if ( *((_QWORD *)&v37 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v37 + 1));
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= a5 )
        goto LABEL_24;
    }
    std::vector<std::shared_ptr<GEOFENCE>>::clear(&v42);
    LODWORD(v12) = DWORD2(v37);
    if ( *((_QWORD *)&v37 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v37 + 1));
    goto LABEL_11;
  }
LABEL_24:
  v21 = 0;
  v22 = (__int64)(*((_QWORD *)&v42 + 1) - v42) >> 4;
  if ( v22 )
  {
    v21 = (char *)CoTaskMemAlloc(88 * v22);
    if ( !v21 )
    {
      GeofenceAppDataHandler = -2147024882;
      goto LABEL_11;
    }
    v14 = 0;
    do
    {
      v12 = 2LL * v14;
      v23 = v14++;
      v13 = *(_QWORD *)(v42 + 8 * v12);
      v24 = 88 * v23;
      *(_OWORD *)&v21[v24] = *(_OWORD *)(v13 + 128);
      *(_OWORD *)&v21[v24 + 16] = *(_OWORD *)(v13 + 144);
      *(_OWORD *)&v21[v24 + 32] = *(_OWORD *)(v13 + 160);
      *(_OWORD *)&v21[v24 + 48] = *(_OWORD *)(v13 + 176);
      *(_OWORD *)&v21[v24 + 64] = *(_OWORD *)(v13 + 192);
      *(_QWORD *)&v21[v24 + 80] = *(_QWORD *)(v13 + 208);
    }
    while ( v14 < v22 );
  }
  v25 = 0;
  v26 = (__int64)(*((_QWORD *)&v40 + 1) - v40) >> 4;
  if ( v26 )
  {
    v25 = (struct GEOFENCE_INFORMATION *)CoTaskMemAlloc(88 * v26);
    if ( !v25 )
    {
      GeofenceAppDataHandler = -2147024882;
      if ( v21 )
        CoTaskMemFree(v21);
      goto LABEL_11;
    }
    v14 = 0;
    do
    {
      v12 = 2LL * v14;
      v27 = v14++;
      v13 = *(_QWORD *)(v40 + 8 * v12);
      v28 = 88 * v27;
      *(_OWORD *)((char *)v25 + v28) = *(_OWORD *)(v13 + 128);
      *(_OWORD *)((char *)v25 + v28 + 16) = *(_OWORD *)(v13 + 144);
      *(_OWORD *)((char *)v25 + v28 + 32) = *(_OWORD *)(v13 + 160);
      *(_OWORD *)((char *)v25 + v28 + 48) = *(_OWORD *)(v13 + 176);
      *(_OWORD *)((char *)v25 + v28 + 64) = *(_OWORD *)(v13 + 192);
      *(_QWORD *)((char *)v25 + v28 + 80) = *(_QWORD *)(v13 + 208);
    }
    while ( v14 < v26 );
  }
  if ( v22 <= 0xFFFFFFFF && v26 <= 0xFFFFFFFF )
  {
    v29 = v36;
    *a7 = v22;
    *v29 = (struct GEOFENCE_INFORMATION *)v21;
    v30 = v35;
    *a10 = v26;
    *v30 = v25;
    goto LABEL_11;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v39);
  if ( (_QWORD)v40 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(v40, *((_QWORD *)&v40 + 1));
    std::_Deallocate<16>((void *)v40, (v41 - v40) & 0xFFFFFFFFFFFFFFF0uLL);
    v41 = 0;
    v40 = 0;
  }
  if ( (_QWORD)v42 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(v42, *((_QWORD *)&v42 + 1));
    std::_Deallocate<16>((void *)v42, (v43 - v42) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800fe780  mov     rax, rsp
0x1800fe783  push    rbp
0x1800fe784  push    rbx
0x1800fe785  push    rsi
0x1800fe786  push    rdi
0x1800fe787  push    r12
0x1800fe789  push    r13
0x1800fe78b  push    r14
0x1800fe78d  push    r15
0x1800fe78f  lea     rbp, [rax-47h]
0x1800fe793  sub     rsp, 0F8h
0x1800fe79a  movaps  xmmword ptr [rax-58h], xmm6
0x1800fe79e  movaps  xmmword ptr [rax-68h], xmm7
0x1800fe7a2  mov     rax, cs:__security_cookie
0x1800fe7a9  xor     rax, rsp
0x1800fe7ac  mov     [rbp+3Fh+var_70], rax
0x1800fe7b0  mov     r15, [rbp+3Fh+arg_38]
0x1800fe7b7  lea     rdx, [rcx+78h]
0x1800fe7bb  mov     rdi, [rbp+3Fh+arg_50]
0x1800fe7c2  xorps   xmm0, xmm0
0x1800fe7c5  mov     r14, [rbp+3Fh+arg_28]
0x1800fe7c9  mov     rsi, rcx
0x1800fe7cc  mov     r13, [rbp+3Fh+arg_30]
0x1800fe7d0  lea     rcx, [rbp+3Fh+var_B0]
0x1800fe7d4  mov     r12, [rbp+3Fh+arg_48]
0x1800fe7db  movaps  xmm6, xmm2
0x1800fe7de  mov     qword ptr [rsp+130h+var_D0], r15
0x1800fe7e3  movaps  xmm7, xmm1
0x1800fe7e6  mov     [rsp+130h+var_D8], rdi
0x1800fe7eb  movdqu  [rbp+3Fh+var_88], xmm0
0x1800fe7f0  mov     dword ptr [rsp+130h+var_E0], r9d
0x1800fe7f5  movdqu  [rbp+3Fh+var_A0], xmm0
0x1800fe7fa  mov     [rbp+3Fh+var_78], 0
0x1800fe802  mov     [rbp+3Fh+var_90], 0
0x1800fe80a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800fe80f  test    r15, r15
0x1800fe812  jz      short loc_1800FE83A
0x1800fe814  test    r13, r13
0x1800fe817  jz      short loc_1800FE83A
0x1800fe819  test    r14, r14
0x1800fe81c  jz      short loc_1800FE83A
0x1800fe81e  test    r12, r12
0x1800fe821  jz      short loc_1800FE83A
0x1800fe823  test    rdi, rdi
0x1800fe826  jz      short loc_1800FE83A
0x1800fe828  xor     ebx, ebx
0x1800fe82a  mov     [r15], rbx
0x1800fe82d  mov     [r13+0], ebx
0x1800fe831  mov     [rdi], rbx
0x1800fe834  mov     [r12], ebx
0x1800fe838  jmp     short loc_1800FE83F
0x1800fe83a  mov     ebx, 80070057h
0x1800fe83f  cmp     byte ptr [rsi+0A0h], 0
0x1800fe846  jz      short loc_1800FE876
0x1800fe848  test    ebx, ebx
0x1800fe84a  js      short loc_1800FE851
0x1800fe84c  mov     ebx, 80004004h
0x1800fe851  mov     eax, cs:dword_1801DDEF8
0x1800fe857  cmp     eax, 5
0x1800fe85a  jbe     loc_1800FEBA1
0x1800fe860  mov     dword ptr [rsp+130h+var_E0], ebx
0x1800fe864  test    r12, r12
0x1800fe867  jz      loc_1800FEB31
0x1800fe86d  mov     eax, [r12]
0x1800fe871  jmp     loc_1800FEB33
0x1800fe876  test    ebx, ebx
0x1800fe878  js      short loc_1800FE851
0x1800fe87a  xor     edi, edi
0x1800fe87c  cmp     [rbp+3Fh+arg_20], edi
0x1800fe87f  jbe     loc_1800FE91A
0x1800fe885  mov     r15d, [rbp+3Fh+arg_40]
0x1800fe88c  mov     edx, [r14+rdi*4]; unsigned int
0x1800fe890  lea     r8, [rsp+130h+var_D0+8]
0x1800fe895  xorps   xmm0, xmm0
0x1800fe898  mov     rcx, rsi; this
0x1800fe89b  movdqu  [rsp+130h+var_D0+8], xmm0
0x1800fe8a1  call    ?GetGeofenceAppDataHandler@CGeofenceStore@@AEAAJKPEAV?$shared_ptr@VCGeofenceDataManagement@@@std@@@Z; CGeofenceStore::GetGeofenceAppDataHandler(ulong,std::shared_ptr<CGeofenceDataManagement> *)
0x1800fe8a6  mov     ebx, eax
0x1800fe8a8  test    eax, eax
0x1800fe8aa  js      short loc_1800FE8F6
0x1800fe8ac  mov     r9d, dword ptr [rsp+130h+var_E0]
0x1800fe8b1  lea     rax, [rbp+3Fh+var_A0]
0x1800fe8b5  mov     rcx, qword ptr [rsp+130h+var_D0+8]
0x1800fe8ba  movaps  xmm2, xmm6
0x1800fe8bd  mov     [rsp+130h+var_100], rax
0x1800fe8c2  movaps  xmm1, xmm7
0x1800fe8c5  lea     rax, [rbp+3Fh+var_88]
0x1800fe8c9  mov     dword ptr [rsp+130h+var_108], r15d
0x1800fe8ce  mov     [rsp+130h+var_110], rax
0x1800fe8d3  call    ?GetClosestGeofencesToPosition@CGeofenceDataManagement@@QEAAJNNKAEAV?$vector@V?$shared_ptr@UGEOFENCE@@@std@@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@2@@std@@K0@Z; CGeofenceDataManagement::GetClosestGeofencesToPosition(double,double,ulong,std::vector<std::shared_ptr<GEOFENCE>> &,ulong,std::vector<std::shared_ptr<GEOFENCE>> &)
0x1800fe8d8  mov     ebx, eax
0x1800fe8da  test    eax, eax
0x1800fe8dc  js      short loc_1800FE8F6
0x1800fe8de  mov     rcx, [rsp+130h+var_C0]; this
0x1800fe8e3  test    rcx, rcx
0x1800fe8e6  jz      short loc_1800FE8ED
0x1800fe8e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800fe8ed  inc     edi
0x1800fe8ef  cmp     edi, [rbp+3Fh+arg_20]
0x1800fe8f2  jb      short loc_1800FE88C
0x1800fe8f4  jmp     short loc_1800FE91A
0x1800fe8f6  lea     rcx, [rbp+3Fh+var_88]
0x1800fe8fa  call    ?clear@?$vector@V?$shared_ptr@UGEOFENCE@@@std@@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<GEOFENCE>>::clear(void)
0x1800fe8ff  mov     rcx, [rsp+130h+var_C0]; this
0x1800fe904  test    rcx, rcx
0x1800fe907  jz      loc_1800FE851
0x1800fe90d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800fe912  test    ebx, ebx
0x1800fe914  js      loc_1800FE851
0x1800fe91a  mov     rdi, qword ptr [rbp+3Fh+var_88+8]
0x1800fe91e  xor     r14d, r14d
0x1800fe921  sub     rdi, qword ptr [rbp+3Fh+var_88]
0x1800fe925  sar     rdi, 4
0x1800fe929  test    rdi, rdi
0x1800fe92c  jz      loc_1800FE9C6
0x1800fe932  imul    rcx, rdi, 58h ; 'X'; cb
0x1800fe936  call    cs:__imp_CoTaskMemAlloc
0x1800fe93c  mov     r14, rax
0x1800fe93f  test    rax, rax
0x1800fe942  jnz     short loc_1800FE94E
0x1800fe944  mov     ebx, 8007000Eh
0x1800fe949  jmp     loc_1800FE851
0x1800fe94e  xor     r9d, r9d
0x1800fe951  mov     rax, qword ptr [rbp+3Fh+var_88]
0x1800fe955  mov     ecx, r9d
0x1800fe958  add     rcx, rcx
0x1800fe95b  mov     edx, r9d
0x1800fe95e  inc     r9d
0x1800fe961  mov     r8, [rax+rcx*8]
0x1800fe965  imul    rax, rdx, 58h ; 'X'
0x1800fe969  movups  xmm0, xmmword ptr [r8+80h]
0x1800fe971  movups  xmmword ptr [rax+r14], xmm0
0x1800fe976  movups  xmm1, xmmword ptr [r8+90h]
0x1800fe97e  movups  xmmword ptr [rax+r14+10h], xmm1
0x1800fe984  movups  xmm0, xmmword ptr [r8+0A0h]
0x1800fe98c  movups  xmmword ptr [rax+r14+20h], xmm0
0x1800fe992  movups  xmm1, xmmword ptr [r8+0B0h]
0x1800fe99a  movups  xmmword ptr [rax+r14+30h], xmm1
0x1800fe9a0  movups  xmm0, xmmword ptr [r8+0C0h]
0x1800fe9a8  movups  xmmword ptr [rax+r14+40h], xmm0
0x1800fe9ae  movsd   xmm1, qword ptr [r8+0D0h]
0x1800fe9b7  movsd   qword ptr [rax+r14+50h], xmm1
0x1800fe9be  mov     eax, r9d
0x1800fe9c1  cmp     rax, rdi
0x1800fe9c4  jb      short loc_1800FE951
0x1800fe9c6  mov     rsi, qword ptr [rbp+3Fh+var_A0+8]
0x1800fe9ca  xor     r15d, r15d
0x1800fe9cd  sub     rsi, qword ptr [rbp+3Fh+var_A0]
0x1800fe9d1  sar     rsi, 4
0x1800fe9d5  test    rsi, rsi
0x1800fe9d8  jz      loc_1800FEA96
0x1800fe9de  imul    rcx, rsi, 58h ; 'X'; cb
0x1800fe9e2  call    cs:__imp_CoTaskMemAlloc
0x1800fe9e8  mov     r15, rax
0x1800fe9eb  test    rax, rax
0x1800fe9ee  jnz     short loc_1800FEA1A
0x1800fe9f0  mov     ebx, 8007000Eh
0x1800fe9f5  test    r14, r14
0x1800fe9f8  jz      short loc_1800FEA03
0x1800fe9fa  mov     rcx, r14; pv
0x1800fe9fd  call    cs:__imp_CoTaskMemFree
0x1800fea03  test    r15, r15
0x1800fea06  jz      loc_1800FE851
0x1800fea0c  mov     rcx, r15; pv
0x1800fea0f  call    cs:__imp_CoTaskMemFree
0x1800fea15  jmp     loc_1800FE851
0x1800fea1a  test    ebx, ebx
0x1800fea1c  js      short loc_1800FE9F5
0x1800fea1e  xor     r9d, r9d
0x1800fea21  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x1800fea25  mov     ecx, r9d
0x1800fea28  add     rcx, rcx
0x1800fea2b  mov     edx, r9d
0x1800fea2e  inc     r9d
0x1800fea31  mov     r8, [rax+rcx*8]
0x1800fea35  imul    rax, rdx, 58h ; 'X'
0x1800fea39  movups  xmm0, xmmword ptr [r8+80h]
0x1800fea41  movups  xmmword ptr [rax+r15], xmm0
0x1800fea46  movups  xmm1, xmmword ptr [r8+90h]
0x1800fea4e  movups  xmmword ptr [rax+r15+10h], xmm1
0x1800fea54  movups  xmm0, xmmword ptr [r8+0A0h]
0x1800fea5c  movups  xmmword ptr [rax+r15+20h], xmm0
0x1800fea62  movups  xmm1, xmmword ptr [r8+0B0h]
0x1800fea6a  movups  xmmword ptr [rax+r15+30h], xmm1
0x1800fea70  movups  xmm0, xmmword ptr [r8+0C0h]
0x1800fea78  movups  xmmword ptr [rax+r15+40h], xmm0
0x1800fea7e  movsd   xmm1, qword ptr [r8+0D0h]
0x1800fea87  movsd   qword ptr [rax+r15+50h], xmm1
0x1800fea8e  mov     eax, r9d
0x1800fea91  cmp     rax, rsi
0x1800fea94  jb      short loc_1800FEA21
0x1800fea96  mov     eax, 0FFFFFFFFh
0x1800fea9b  cmp     rdi, rax
0x1800fea9e  ja      short loc_1800FEAC2
0x1800feaa0  cmp     rsi, rax
0x1800feaa3  ja      short loc_1800FEAC2
0x1800feaa5  mov     rax, qword ptr [rsp+130h+var_D0]
0x1800feaaa  mov     [r13+0], edi
0x1800feaae  mov     [rax], r14
0x1800feab1  mov     rax, [rsp+130h+var_D8]
0x1800feab6  mov     [r12], esi
0x1800feaba  mov     [rax], r15
0x1800feabd  jmp     loc_1800FE851
0x1800feac2  lea     rcx, [rbp+3Fh+var_B0]
0x1800feac6  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800feacb  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x1800feacf  test    rcx, rcx
0x1800fead2  jz      short loc_1800FEB01
0x1800fead4  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x1800fead8  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UGEOFENCE@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(std::shared_ptr<GEOFENCE> *,std::shared_ptr<GEOFENCE> * const,std::allocator<std::shared_ptr<GEOFENCE>> &)
0x1800feadd  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x1800feae1  mov     rdx, [rbp+3Fh+var_90]
0x1800feae5  sub     rdx, rcx
0x1800feae8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800feaec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800feaf1  xorps   xmm0, xmm0
0x1800feaf4  mov     [rbp+3Fh+var_90], 0
0x1800feafc  movdqu  [rbp+3Fh+var_A0], xmm0
0x1800feb01  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x1800feb05  test    rcx, rcx
0x1800feb08  jz      short loc_1800FEB27
0x1800feb0a  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x1800feb0e  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UGEOFENCE@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(std::shared_ptr<GEOFENCE> *,std::shared_ptr<GEOFENCE> * const,std::allocator<std::shared_ptr<GEOFENCE>> &)
0x1800feb13  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x1800feb17  mov     rdx, [rbp+3Fh+var_78]
0x1800feb1b  sub     rdx, rcx
0x1800feb1e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800feb22  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800feb27  mov     eax, 8000FFFFh
0x1800feb2c  jmp     loc_1800FEC08
0x1800feb31  xor     eax, eax
0x1800feb33  mov     dword ptr [rsp+130h+var_E0+4], eax
0x1800feb37  test    r13, r13
0x1800feb3a  jz      short loc_1800FEB42
0x1800feb3c  mov     eax, [r13+0]
0x1800feb40  jmp     short loc_1800FEB44
0x1800feb42  xor     eax, eax
0x1800feb44  mov     dword ptr [rsp+130h+var_D8], eax
0x1800feb48  lea     rdx, word_1801B0E92
0x1800feb4f  mov     eax, [rbp+3Fh+arg_20]
0x1800feb52  mov     dword ptr [rsp+130h+var_D0], eax
0x1800feb56  lea     rax, [rsp+130h+var_E0]
0x1800feb5b  mov     qword ptr [rsp+130h+var_E8], rax
0x1800feb60  lea     rax, [rsp+130h+var_E0+4]
0x1800feb65  mov     [rsp+130h+var_F0], rax
0x1800feb6a  lea     rax, [rsp+130h+var_D8]
0x1800feb6f  mov     [rsp+130h+var_F8], rax
0x1800feb74  lea     rax, [rsp+130h+var_D0]
0x1800feb79  mov     [rsp+130h+var_100], rax
0x1800feb7e  lea     rax, [rbp+3Fh+var_B8]
0x1800feb82  mov     [rsp+130h+var_108], rax
0x1800feb87  lea     rax, [rsp+130h+var_D0+8]
0x1800feb8c  mov     [rsp+130h+var_110], rax
0x1800feb91  movsd   [rbp+3Fh+var_B8], xmm6
0x1800feb96  movsd   qword ptr [rsp+130h+var_D0+8], xmm7
0x1800feb9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800feba1  lea     rcx, [rbp+3Fh+var_B0]
0x1800feba5  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800febaa  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x1800febae  test    rcx, rcx
0x1800febb1  jz      short loc_1800FEBE0
0x1800febb3  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x1800febb7  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UGEOFENCE@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(std::shared_ptr<GEOFENCE> *,std::shared_ptr<GEOFENCE> * const,std::allocator<std::shared_ptr<GEOFENCE>> &)
0x1800febbc  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x1800febc0  mov     rdx, [rbp+3Fh+var_90]
0x1800febc4  sub     rdx, rcx
0x1800febc7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800febcb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800febd0  xorps   xmm0, xmm0
0x1800febd3  mov     [rbp+3Fh+var_90], 0
0x1800febdb  movdqu  [rbp+3Fh+var_A0], xmm0
0x1800febe0  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x1800febe4  test    rcx, rcx
0x1800febe7  jz      short loc_1800FEC06
0x1800febe9  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x1800febed  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UGEOFENCE@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UGEOFENCE@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<GEOFENCE>>>(std::shared_ptr<GEOFENCE> *,std::shared_ptr<GEOFENCE> * const,std::allocator<std::shared_ptr<GEOFENCE>> &)
0x1800febf2  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x1800febf6  mov     rdx, [rbp+3Fh+var_78]
0x1800febfa  sub     rdx, rcx
0x1800febfd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800fec01  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800fec06  mov     eax, ebx
0x1800fec08  mov     rcx, [rbp+3Fh+var_70]
0x1800fec0c  xor     rcx, rsp; StackCookie
0x1800fec0f  call    __security_check_cookie
0x1800fec14  lea     r11, [rsp+130h+var_38]
0x1800fec1c  movaps  xmm6, xmmword ptr [r11-18h]
0x1800fec21  movaps  xmm7, xmmword ptr [r11-28h]
0x1800fec26  mov     rsp, r11
0x1800fec29  pop     r15
0x1800fec2b  pop     r14
0x1800fec2d  pop     r13
0x1800fec2f  pop     r12
0x1800fec31  pop     rdi
0x1800fec32  pop     rsi
0x1800fec33  pop     rbx
0x1800fec34  pop     rbp
0x1800fec35  retn
```
