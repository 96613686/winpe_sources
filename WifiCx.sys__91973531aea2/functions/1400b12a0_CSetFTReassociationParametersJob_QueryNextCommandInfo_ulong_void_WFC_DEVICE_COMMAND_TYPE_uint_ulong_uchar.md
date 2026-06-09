# CSetFTReassociationParametersJob::QueryNextCommandInfo(ulong,void * *,_WFC_DEVICE_COMMAND_TYPE *,uint *,ulong *,uchar * *)

- ea: `0x1400b12a0`
- end: `0x1400b15f4`
- name: `?QueryNextCommandInfo@CSetFTReassociationParametersJob@@MEAAHKPEAPEAXPEAW4_WFC_DEVICE_COMMAND_TYPE@@PEAIPEAKPEAPEAE@Z`
- size: `852`
- prototype: `__int64 __usercall@<rax>(CSetFTReassociationParametersJob *__hidden this@<rcx>, unsigned int@<edx>, void **@<r8>, enum _WFC_DEVICE_COMMAND_TYPE *@<r9>, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000d054`
- `0x140014b30`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a9f8`
- `0x140040218`
- `0x1400683ac`
- `0x140070b20`
- `0x140071720`
- `0x1400b12a0`

## pseudocode

```c
__int64 __fastcall CSetFTReassociationParametersJob::QueryNextCommandInfo(
        CSetFTReassociationParametersJob *this,
        int a2,
        void **a3,
        enum _WFC_DEVICE_COMMAND_TYPE *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  __int64 v8; // r14
  int v9; // r10d
  const struct _DOT11_SSID *v13; // rdx
  unsigned int WdiSetFastBssTransitionParametersToIhv; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ebx
  int v18; // r9d
  int v19; // edi
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rbx
  CPropertyCache *PortPropertyCache; // rax
  unsigned int v26; // eax
  CPropertyCache *v27; // rax
  CPropertyCache *v28; // rax
  __int64 v29; // r8
  int v31; // [rsp+30h] [rbp-61h]
  __int64 v32; // [rsp+38h] [rbp-59h]
  __int128 v33; // [rsp+40h] [rbp-51h] BYREF
  __int64 v34; // [rsp+50h] [rbp-41h]
  __int64 v35; // [rsp+58h] [rbp-39h]
  __int64 v36; // [rsp+60h] [rbp-31h] BYREF
  __int64 v37; // [rsp+68h] [rbp-29h]
  __int64 v38; // [rsp+70h] [rbp-21h]
  __int64 v39; // [rsp+78h] [rbp-19h] BYREF
  __int64 v40; // [rsp+80h] [rbp-11h]
  __int64 v41; // [rsp+88h] [rbp-9h]

  v8 = *((_QWORD *)this + 137);
  v9 = v33 & 0xFFFFFFF8;
  LODWORD(v33) = v33 & 0xFFFFFFF8;
  *(_QWORD *)((char *)&v33 + 4) = 0;
  v34 = 0;
  LOBYTE(v35) = 0;
  LODWORD(v36) = 0;
  v37 = 0;
  LOBYTE(v38) = 0;
  LODWORD(v39) = 0;
  v40 = 0;
  LOBYTE(v41) = 0;
  v13 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v13,
      (_DWORD)a3,
      594,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v9 = v33;
    v13 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  }
  DWORD1(v33) = *(_DWORD *)(v8 + 4);
  if ( *(_DWORD *)(v8 + 4) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v13,
        (_DWORD)a3,
        595,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_DWORD *)(v8 + 4));
    }
LABEL_8:
    WdiSetFastBssTransitionParametersToIhv = GenerateWdiSetFastBssTransitionParametersToIhv(
                                               (unsigned int)&v33,
                                               a2,
                                               (unsigned int)*((_QWORD *)this + 67) + 5384,
                                               (_DWORD)a6,
                                               (__int64)a7);
    v17 = WdiSetFastBssTransitionParametersToIhv;
    if ( !WdiSetFastBssTransitionParametersToIhv )
    {
      *a3 = 0;
      *(_DWORD *)a4 = 1;
      *a5 = 127;
      goto LABEL_23;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v18 = 599;
    goto LABEL_18;
  }
  LODWORD(v33) = v9 | 1;
  v19 = *(_DWORD *)(v8 + 32);
  v20 = v8 + *(unsigned int *)(v8 + 36);
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup((char *)&v33 + 8);
  LODWORD(v33) = v33 | 2;
  v34 = v20;
  LOBYTE(v35) = 0;
  DWORD2(v33) = v19;
  v21 = *(_DWORD *)(v8 + 40);
  v22 = v8 + *(unsigned int *)(v8 + 44);
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v36);
  LODWORD(v33) = v33 | 4;
  v37 = v22;
  LOBYTE(v38) = 0;
  LODWORD(v36) = v21;
  v23 = *(_DWORD *)(v8 + 48);
  v24 = v8 + *(unsigned int *)(v8 + 52);
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v39);
  LOBYTE(v41) = 0;
  LODWORD(v39) = v23;
  v40 = v24;
  PortPropertyCache = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
  v26 = CPropertyCache::SetPropertyBuffer(PortPropertyCache, 0x11u, 0x10u, (const unsigned __int8 *)(v8 + 8));
  v17 = v26;
  if ( v26 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v18 = 596;
    LODWORD(v32) = v26;
    v31 = *((_DWORD *)this + 4);
    goto LABEL_14;
  }
  v27 = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
  WdiSetFastBssTransitionParametersToIhv = CPropertyCache::SetPropertyBuffer(
                                             v27,
                                             0x12u,
                                             *(_DWORD *)(v8 + 24),
                                             (const unsigned __int8 *)(v8 + *(unsigned int *)(v8 + 28)));
  v17 = WdiSetFastBssTransitionParametersToIhv;
  if ( !WdiSetFastBssTransitionParametersToIhv )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        1,
        598,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
    v28 = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
    LOBYTE(v29) = 1;
    CPropertyCache::SetPropertyBoolean(v28, 20, v29);
    goto LABEL_8;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_27;
  v18 = 597;
LABEL_18:
  LODWORD(v32) = WdiSetFastBssTransitionParametersToIhv;
  v31 = *((_DWORD *)this + 4);
LABEL_14:
  LOBYTE(v15) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v15,
    v16,
    v18,
    (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
    (char)this,
    v31,
    v32,
    v33,
    v34,
    v35,
    v36,
    v37,
    v38,
    v39,
    v40,
    v41);
LABEL_23:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    LODWORD(v32) = v17;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v16,
      600,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v32);
  }
LABEL_27:
  _WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND::~_WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND((_WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND *)&v33);
  return v17;
}

```

## disassembly

```asm
0x1400b12a0  push    rbp
0x1400b12a2  push    rbx
0x1400b12a3  push    rsi
0x1400b12a4  push    rdi
0x1400b12a5  push    r12
0x1400b12a7  push    r13
0x1400b12a9  push    r14
0x1400b12ab  push    r15
0x1400b12ad  lea     rbp, [rsp-7]
0x1400b12b2  sub     rsp, 98h
0x1400b12b9  mov     r10d, dword ptr [rbp+3Fh+var_90]
0x1400b12bd  mov     r15, r9
0x1400b12c0  mov     r14, [rcx+448h]
0x1400b12c7  and     r10d, 0FFFFFFF8h
0x1400b12cb  xor     edi, edi
0x1400b12cd  mov     dword ptr [rbp+3Fh+var_90], r10d
0x1400b12d1  mov     qword ptr [rbp+3Fh+var_90+4], rdi
0x1400b12d5  mov     r12, r8
0x1400b12d8  mov     [rbp+3Fh+var_80], rdi
0x1400b12dc  mov     r13d, edx
0x1400b12df  mov     byte ptr [rbp+3Fh+var_78], dil
0x1400b12e3  mov     rsi, rcx
0x1400b12e6  mov     dword ptr [rbp+3Fh+var_70], edi
0x1400b12e9  mov     [rbp+3Fh+var_68], rdi
0x1400b12ed  mov     byte ptr [rbp+3Fh+var_60], dil
0x1400b12f1  mov     dword ptr [rbp+3Fh+var_58], edi
0x1400b12f4  mov     [rbp+3Fh+var_50], rdi
0x1400b12f8  mov     byte ptr [rbp+3Fh+var_48], dil
0x1400b12fc  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b1303  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b130a  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1311  jz      short loc_1400B135A
0x1400b1313  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b131a  cmp     byte ptr [rcx+29h], 5
0x1400b131e  jnb     short loc_1400B1326
0x1400b1320  cmp     [rcx+48h], di
0x1400b1324  jz      short loc_1400B1353
0x1400b1326  mov     eax, [rsi+10h]
0x1400b1329  mov     r9d, 252h
0x1400b132f  mov     rcx, [rcx+40h]
0x1400b1333  mov     [rsp+0D0h+var_A0], eax
0x1400b1337  mov     [rsp+0D0h+var_A8], rsi
0x1400b133c  mov     [rsp+0D0h+var_B0], rdx
0x1400b1341  mov     dl, 5
0x1400b1343  call    WPP_RECORDER_SF_qD
0x1400b1348  mov     r10d, dword ptr [rbp+3Fh+var_90]
0x1400b134c  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1353  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b135a  mov     eax, [r14+4]
0x1400b135e  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x1400b1361  mov     eax, [r14+4]
0x1400b1365  test    eax, eax
0x1400b1367  jz      loc_1400B13F3
0x1400b136d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b1374  jz      short loc_1400B13A3
0x1400b1376  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b137d  mov     r9d, 253h
0x1400b1383  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400b1387  mov     eax, [rsi+10h]
0x1400b138a  mov     [rsp+0D0h+var_A0], eax
0x1400b138e  mov     rcx, [rcx+40h]
0x1400b1392  mov     [rsp+0D0h+var_A8], rsi
0x1400b1397  mov     [rsp+0D0h+var_B0], rdx
0x1400b139c  mov     dl, 2
0x1400b139e  call    WPP_RECORDER_SF_qDD
0x1400b13a3  lea     r14, WPP_RECORDER_INITIALIZED
0x1400b13aa  mov     r8, [rsi+218h]
0x1400b13b1  lea     rcx, [rbp+3Fh+var_90]
0x1400b13b5  mov     rax, [rbp+3Fh+arg_30]
0x1400b13b9  add     r8, 1508h
0x1400b13c0  mov     r9, [rbp+3Fh+arg_28]
0x1400b13c4  mov     edx, r13d
0x1400b13c7  mov     [rsp+0D0h+var_B0], rax
0x1400b13cc  call    GenerateWdiSetFastBssTransitionParametersToIhv
0x1400b13d1  mov     ebx, eax
0x1400b13d3  test    eax, eax
0x1400b13d5  jz      loc_1400B1576
0x1400b13db  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400b13e2  jz      loc_1400B15D4
0x1400b13e8  mov     r9d, 257h
0x1400b13ee  jmp     loc_1400B1512
0x1400b13f3  or      r10d, 1
0x1400b13f7  lea     rcx, [rbp+3Fh+var_90+8]; void *
0x1400b13fb  mov     dword ptr [rbp+3Fh+var_90], r10d
0x1400b13ff  mov     ebx, [r14+24h]
0x1400b1403  mov     edi, [r14+20h]
0x1400b1407  add     rbx, r14
0x1400b140a  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400b140f  or      dword ptr [rbp+3Fh+var_90], 2
0x1400b1413  lea     rcx, [rbp+3Fh+var_70]; void *
0x1400b1417  mov     [rbp+3Fh+var_80], rbx
0x1400b141b  mov     byte ptr [rbp+3Fh+var_78], 0
0x1400b141f  mov     dword ptr [rbp+3Fh+var_90+8], edi
0x1400b1422  mov     ebx, [r14+2Ch]
0x1400b1426  mov     edi, [r14+28h]
0x1400b142a  add     rbx, r14
0x1400b142d  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400b1432  or      dword ptr [rbp+3Fh+var_90], 4
0x1400b1436  lea     rcx, [rbp+3Fh+var_58]; void *
0x1400b143a  mov     [rbp+3Fh+var_68], rbx
0x1400b143e  mov     byte ptr [rbp+3Fh+var_60], 0
0x1400b1442  mov     dword ptr [rbp+3Fh+var_70], edi
0x1400b1445  mov     ebx, [r14+34h]
0x1400b1449  mov     edi, [r14+30h]
0x1400b144d  add     rbx, r14
0x1400b1450  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400b1455  mov     rcx, rsi; this
0x1400b1458  mov     byte ptr [rbp+3Fh+var_48], 0
0x1400b145c  mov     dword ptr [rbp+3Fh+var_58], edi
0x1400b145f  mov     [rbp+3Fh+var_50], rbx
0x1400b1463  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400b1468  mov     edx, 11h; unsigned int
0x1400b146d  lea     r9, [r14+8]; unsigned __int8 *
0x1400b1471  mov     rcx, rax; this
0x1400b1474  lea     r8d, [rdx-1]; unsigned int
0x1400b1478  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x1400b147d  xor     edi, edi
0x1400b147f  mov     ebx, eax
0x1400b1481  test    eax, eax
0x1400b1483  jz      short loc_1400B14D2
0x1400b1485  lea     r14, WPP_RECORDER_INITIALIZED
0x1400b148c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400b1493  jz      loc_1400B15D4
0x1400b1499  mov     ecx, [rsi+10h]
0x1400b149c  mov     r9d, 254h
0x1400b14a2  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400b14a6  mov     [rsp+0D0h+var_A0], ecx
0x1400b14aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b14b1  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b14b8  mov     [rsp+0D0h+var_A8], rsi
0x1400b14bd  mov     dl, 2
0x1400b14bf  mov     [rsp+0D0h+var_B0], r15
0x1400b14c4  mov     rcx, [rcx+40h]
0x1400b14c8  call    WPP_RECORDER_SF_qDD
0x1400b14cd  jmp     loc_1400B1592
0x1400b14d2  mov     rcx, rsi; this
0x1400b14d5  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400b14da  mov     r9d, [r14+1Ch]
0x1400b14de  mov     edx, 12h; unsigned int
0x1400b14e3  mov     r8d, [r14+18h]; unsigned int
0x1400b14e7  add     r9, r14; unsigned __int8 *
0x1400b14ea  mov     rcx, rax; this
0x1400b14ed  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x1400b14f2  mov     ebx, eax
0x1400b14f4  test    eax, eax
0x1400b14f6  jz      short loc_1400B151F
0x1400b14f8  lea     r14, WPP_RECORDER_INITIALIZED
0x1400b14ff  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400b1506  jz      loc_1400B15D4
0x1400b150c  mov     r9d, 255h
0x1400b1512  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400b1516  mov     eax, [rsi+10h]
0x1400b1519  mov     [rsp+0D0h+var_A0], eax
0x1400b151d  jmp     short loc_1400B14AA
0x1400b151f  lea     r14, WPP_RECORDER_INITIALIZED
0x1400b1526  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400b152d  jz      short loc_1400B1559
0x1400b152f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1536  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b153d  mov     r9d, 256h
0x1400b1543  mov     [rsp+0D0h+var_B0], rax
0x1400b1548  mov     r8d, 1
0x1400b154e  mov     dl, 4
0x1400b1550  mov     rcx, [rcx+40h]
0x1400b1554  call    WPP_RECORDER_SF_
0x1400b1559  mov     rcx, rsi; this
0x1400b155c  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400b1561  mov     r8b, 1; unsigned __int8
0x1400b1564  mov     edx, 14h; unsigned int
0x1400b1569  mov     rcx, rax; this
0x1400b156c  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400b1571  jmp     loc_1400B13AA
0x1400b1576  mov     rax, [rbp+3Fh+arg_20]
0x1400b157a  mov     [r12], rdi
0x1400b157e  mov     dword ptr [r15], 1
0x1400b1585  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b158c  mov     dword ptr [rax], 7Fh
0x1400b1592  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400b1599  jz      short loc_1400B15D4
0x1400b159b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b15a2  cmp     byte ptr [rcx+29h], 5
0x1400b15a6  jnb     short loc_1400B15AE
0x1400b15a8  cmp     [rcx+48h], di
0x1400b15ac  jz      short loc_1400B15D4
0x1400b15ae  mov     eax, [rsi+10h]
0x1400b15b1  mov     r9d, 258h
0x1400b15b7  mov     rcx, [rcx+40h]
0x1400b15bb  mov     dl, 5
0x1400b15bd  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1400b15c1  mov     [rsp+0D0h+var_A0], eax
0x1400b15c5  mov     [rsp+0D0h+var_A8], rsi
0x1400b15ca  mov     [rsp+0D0h+var_B0], r15
0x1400b15cf  call    WPP_RECORDER_SF_qDD
0x1400b15d4  lea     rcx, [rbp+3Fh+var_90]; this
0x1400b15d8  call    ??1_WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND@@QEAA@XZ; _WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND::~_WDI_SET_FAST_BSS_TRANSITION_PARAMETERS_COMMAND(void)
0x1400b15dd  mov     eax, ebx
0x1400b15df  add     rsp, 98h
0x1400b15e6  pop     r15
0x1400b15e8  pop     r14
0x1400b15ea  pop     r13
0x1400b15ec  pop     r12
0x1400b15ee  pop     rdi
0x1400b15ef  pop     rsi
0x1400b15f0  pop     rbx
0x1400b15f1  pop     rbp
0x1400b15f2  retn
```
