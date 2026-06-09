# ShieldProvider::QueryAndActionManager::GetConsolidatedHistory(ulong *,HistoryItem * * *)

- ea: `0x180030440`
- end: `0x180030b20`
- name: `?GetConsolidatedHistory@QueryAndActionManager@ShieldProvider@@QEAAJPEAKPEAPEAPEAUHistoryItem@@@Z`
- size: `1760`
- prototype: `__int64 __fastcall(ShieldProvider::QueryAndActionManager *__hidden this, unsigned int *, struct HistoryItem ***)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800201a0`

## callees

- `0x18000d7fc`
- `0x180016d08`
- `0x18002a034`
- `0x18002e194`
- `0x18002ee18`
- `0x18002efa0`
- `0x180030440`
- `0x1800315ac`
- `0x180031a2c`
- `0x180033fcc`
- `0x180034144`
- `0x180034920`
- `0x180034bd8`
- `0x18003522c`
- `0x1800e17e8`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x180030997`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x180030997`
- `ole32!CoTaskMemFree` at `0x1800309dc`
- `ole32!CoTaskMemFree` at `0x180030a0c`
- `ole32!CoTaskMemFree` at `0x180030a35`
- `ole32!CoTaskMemFree` at `0x180030a5f`
- `ole32!CoTaskMemFree` at `0x180030ade`
- `ole32!CoTaskMemFree` at `0x180030aef`
- `ole32!CoTaskMemFree` at `0x1800309dc`
- `ole32!CoTaskMemFree` at `0x180030a0c`
- `ole32!CoTaskMemFree` at `0x180030a35`
- `ole32!CoTaskMemFree` at `0x180030a5f`
- `ole32!CoTaskMemFree` at `0x180030ade`
- `ole32!CoTaskMemFree` at `0x180030aef`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::GetConsolidatedHistory(
        ShieldProvider **this,
        unsigned int *a2,
        struct HistoryItem ***a3)
{
  char *v4; // r14
  int AllowedThreatIdList; // eax
  __int64 v6; // rdx
  int AsrBlockedActionInfos; // eax
  int Threats; // eax
  unsigned int v9; // r15d
  struct tagMPTHREAT_INFO **v10; // r13
  int OfflineThreats; // eax
  unsigned int v12; // ebx
  int v13; // eax
  struct tagMPTHREAT_INFO *v14; // rdx
  unsigned __int64 v15; // r8
  bool v16; // r9
  unsigned int v17; // eax
  __int64 v18; // r15
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // r12d
  __int64 v22; // rsi
  char *v23; // rdi
  enum HistoryItemType *v24; // r9
  _DWORD *v25; // rax
  struct tagMPTHREAT_INFO **v26; // r8
  __int64 v27; // rax
  struct tagMPTHREAT_INFO *v28; // rdx
  struct tagMPTHREAT_INFO *v29; // rcx
  __int128 v30; // xmm0
  char v31; // cl
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rdi
  char *v36; // rsi
  struct tagMPTHREAT_INFO **v37; // r8
  ShieldProvider **v38; // r14
  unsigned int v39; // r12d
  __int64 i; // rdi
  struct tagMPTHREAT_INFO **v41; // r12
  unsigned int v42; // r14d
  __int64 v43; // rdi
  __int64 j; // rdi
  __int64 v46; // rsi
  __int64 v47; // rdi
  unsigned int v48; // [rsp+48h] [rbp-69h]
  unsigned int v49; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v50; // [rsp+54h] [rbp-5Dh] BYREF
  unsigned __int64 v51; // [rsp+58h] [rbp-59h] BYREF
  void *Base; // [rsp+60h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-49h] BYREF
  struct tagMPTHREAT_INFO **v54; // [rsp+70h] [rbp-41h] BYREF
  struct tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO **v55; // [rsp+78h] [rbp-39h]
  __int128 v56; // [rsp+88h] [rbp-29h] BYREF
  __int128 v57; // [rsp+98h] [rbp-19h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-9h]
  GUID v59; // [rsp+B8h] [rbp+7h] BYREF
  int v63; // [rsp+130h] [rbp+7Fh]

  if ( !a2 || !a3 )
    return 2147942487LL;
  *a2 = 0;
  v4 = 0;
  *a3 = 0;
  Base = 0;
  v57 = 0;
  v58 = 0;
  v55 = 0;
  v54 = 0;
  v50 = 0;
  pv = 0;
  v49 = 0;
  *(_QWORD *)&v56 = 0;
  LODWORD(v51) = 0;
  AllowedThreatIdList = ShieldProvider::GetAllowedThreatIdList(&v57);
  if ( AllowedThreatIdList < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      144,
      WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
      (unsigned int)AllowedThreatIdList);
  }
  v59 = GUID_NULL;
  AsrBlockedActionInfos = ShieldProvider::QueryAndActionManager::GetAsrBlockedActionInfos(this, v6, &v59);
  if ( AsrBlockedActionInfos < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        145,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)AsrBlockedActionInfos);
    v55 = 0;
  }
  Threats = ShieldProvider::QueryAndActionManager::GetThreats(this, 2, &v50, &v54);
  if ( Threats >= 0 )
  {
    v10 = v54;
    v9 = v50;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        146,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)Threats);
    v9 = 0;
    v10 = 0;
  }
  v48 = v9;
  OfflineThreats = ShieldProvider::QueryAndActionManager::GetOfflineThreats(
                     (ShieldProvider::QueryAndActionManager *)this,
                     &v49,
                     (struct tagMPTHREAT_INFO ***)&pv);
  if ( OfflineThreats >= 0 )
  {
    v12 = v49;
    v54 = (struct tagMPTHREAT_INFO **)pv;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)OfflineThreats);
    v12 = 0;
    v54 = 0;
  }
  v49 = v12;
  v13 = ShieldProvider::QueryAndActionManager::GetThreats(this, 3, &v51, &v56);
  if ( v13 >= 0 )
  {
    pv = (LPVOID)v56;
    v50 = v51;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)v13);
    v50 = 0;
    pv = 0;
  }
  v17 = v9;
  v18 = v9 + v12;
  if ( (unsigned int)v18 < v17 )
  {
    v19 = -2147024362;
    LODWORD(v18) = -1;
    v63 = -2147024362;
  }
  else
  {
    if ( !(_DWORD)v18 )
    {
      v19 = 1;
      v63 = 1;
      goto LABEL_63;
    }
    LOBYTE(v15) = 1;
    v20 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&Base, (void **)(8 * v18), v15, v16);
    v4 = (char *)Base;
    v19 = v20;
    v63 = v20;
    if ( v20 >= 0 )
    {
      v21 = 0;
      v22 = 0;
      LODWORD(Base) = 0;
      if ( v48 )
      {
        while ( 1 )
        {
          v23 = &v4[8 * v21];
          v63 = CommonUtil::UtilCoTaskMemAllocObject<HistoryItem>(v23);
          v19 = v63;
          if ( v63 < 0 )
            goto LABEL_82;
          v25 = *(_DWORD **)v23;
          LODWORD(v51) = 0;
          *v25 = 2;
          *(_QWORD *)(*(_QWORD *)v23 + 8LL) = *((_QWORD *)v10[v22] + 23);
          *(_QWORD *)(*(_QWORD *)v23 + 16LL) = 0;
          v63 = ShieldProvider::AssignHistoryItemType(
                  this[2],
                  *(struct tagMPCONTEXT **)v10[v22],
                  (unsigned __int64)&v51,
                  v24);
          v19 = v63;
          if ( v63 < 0 )
            goto LABEL_82;
          v27 = *(_QWORD *)v23;
          if ( (_DWORD)v51 == 3 )
            break;
          if ( (_DWORD)v51 == 4 )
          {
            *(_DWORD *)(v27 + 24) = 4;
            goto LABEL_56;
          }
          *(_DWORD *)(v27 + 24) = 1;
          v63 = ShieldProvider::UtilDuplicateThreat(
                  v10[v22],
                  (const struct tagMPTHREAT_INFO *)(*(_QWORD *)v23 + 32LL),
                  v26);
          v19 = v63;
          if ( v63 < 0 )
            goto LABEL_82;
          v28 = v10[v22];
          if ( *((_DWORD *)v28 + 36) == 1
            && !(unsigned __int8)ShieldProvider::IsThreatInAllowedList(&v57, *(_QWORD *)v28) )
          {
            *(_QWORD *)(*(_QWORD *)v23 + 16LL) |= 8uLL;
          }
          v29 = v10[v22];
          if ( *(_QWORD *)&GUID_NULL.Data1 != *((_QWORD *)v29 + 14)
            || *(_QWORD *)GUID_NULL.Data4 != *((_QWORD *)v29 + 15) )
          {
            v30 = *((_OWORD *)v29 + 7);
            v31 = 0;
            v32 = 0;
            v56 = v30;
            if ( v50 )
            {
              while ( !v31 )
              {
                v33 = *((_QWORD *)pv + v32);
                v34 = *(_QWORD *)(v33 + 112) - v56;
                if ( !v34 )
                  v34 = *(_QWORD *)(v33 + 120) - *((_QWORD *)&v56 + 1);
                if ( !v34 )
                  v31 = 1;
                v32 = (unsigned int)(v32 + 1);
                if ( (unsigned int)v32 >= v50 )
                {
                  if ( !v31 )
                    goto LABEL_57;
                  break;
                }
              }
              *(_QWORD *)(*(_QWORD *)v23 + 16LL) |= 4uLL;
            }
          }
LABEL_57:
          v22 = (unsigned int)((_DWORD)Base + 1);
          ++v21;
          LODWORD(Base) = v22;
          if ( (unsigned int)v22 >= v48 )
            goto LABEL_58;
        }
        *(_DWORD *)(v27 + 24) = 3;
LABEL_56:
        v63 = ShieldProvider::UtilDuplicateThreat(
                v10[v22],
                (const struct tagMPTHREAT_INFO *)(*(_QWORD *)v23 + 32LL),
                v26);
        v19 = v63;
        if ( v63 < 0 )
          goto LABEL_82;
        goto LABEL_57;
      }
LABEL_58:
      v35 = 0;
      if ( !v49 )
      {
LABEL_62:
        qsort(v4, (unsigned int)v18, 8u, ShieldProvider::CompareHistoryItem);
        *a2 = v18;
        *a3 = (struct HistoryItem **)v4;
        goto LABEL_63;
      }
      while ( 1 )
      {
        v36 = &v4[8 * v21];
        v63 = CommonUtil::UtilCoTaskMemAllocObject<HistoryItem>(v36);
        v19 = v63;
        if ( v63 < 0 )
          break;
        v37 = v54;
        **(_DWORD **)v36 = 2;
        *(_QWORD *)(*(_QWORD *)v36 + 8LL) = *((_QWORD *)v37[v35] + 23);
        *(_QWORD *)(*(_QWORD *)v36 + 16LL) = 1;
        *(_DWORD *)(*(_QWORD *)v36 + 24LL) = 1;
        v63 = ShieldProvider::UtilDuplicateThreat(
                v37[v35],
                (const struct tagMPTHREAT_INFO *)(*(_QWORD *)v36 + 32LL),
                v37);
        v19 = v63;
        if ( v63 < 0 )
          break;
        v35 = (unsigned int)(v35 + 1);
        ++v21;
        if ( (unsigned int)v35 >= v49 )
          goto LABEL_62;
      }
    }
  }
LABEL_82:
  if ( !v4 )
    goto LABEL_63;
  v46 = 0;
  do
  {
    v47 = *(_QWORD *)&v4[8 * v46];
    if ( !v47 )
      goto LABEL_91;
    if ( *(_DWORD *)(v47 + 24) == 1 )
    {
      ShieldProvider::FreeMpThreatInfo(*(ShieldProvider **)(v47 + 32), v14);
      goto LABEL_89;
    }
    if ( *(_DWORD *)(v47 + 24) == 2 )
    {
      ShieldProvider::FreeShieldAsrHistoryBlockedActionInfo(*(ShieldProvider **)(v47 + 32), v14);
LABEL_89:
      *(_QWORD *)(v47 + 32) = 0;
    }
    CoTaskMemFree((LPVOID)v47);
LABEL_91:
    v46 = (unsigned int)(v46 + 1);
  }
  while ( (unsigned int)v46 < (unsigned int)v18 );
  CoTaskMemFree(v4);
LABEL_63:
  v38 = (ShieldProvider **)pv;
  if ( pv )
  {
    v39 = v50;
    for ( i = 0; (unsigned int)i < v39; i = (unsigned int)(i + 1) )
      ShieldProvider::FreeMpThreatInfo(v38[i], v14);
    CoTaskMemFree(v38);
  }
  v41 = v54;
  if ( v54 )
  {
    v42 = v49;
    v43 = 0;
    if ( v49 )
    {
      do
      {
        ShieldProvider::FreeMpThreatInfo(v41[v43], v14);
        v43 = (unsigned int)(v43 + 1);
      }
      while ( (unsigned int)v43 < v42 );
      v19 = v63;
    }
    CoTaskMemFree(v41);
  }
  if ( v10 )
  {
    for ( j = 0; (unsigned int)j < v48; j = (unsigned int)(j + 1) )
      ShieldProvider::FreeMpThreatInfo(v10[j], v14);
    CoTaskMemFree(v10);
  }
  if ( v55 )
    CoTaskMemFree(v55);
  if ( (_QWORD)v57 )
    std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF8uLL);
  return v19;
}

```

## disassembly

```asm
0x180030440  mov     rax, rsp
0x180030443  mov     [rax+18h], r8
0x180030447  mov     [rax+10h], rdx
0x18003044b  mov     [rax+8], rcx
0x18003044f  push    rbp
0x180030450  push    rbx
0x180030451  push    rsi
0x180030452  push    rdi
0x180030453  push    r12
0x180030455  push    r13
0x180030457  push    r14
0x180030459  push    r15
0x18003045b  lea     rbp, [rax-5Fh]
0x18003045f  sub     rsp, 0C8h
0x180030466  mov     rax, r8
0x180030469  mov     rdi, rcx
0x18003046c  test    rdx, rdx
0x18003046f  jz      loc_180030B07
0x180030475  test    rax, rax
0x180030478  jz      loc_180030B07
0x18003047e  xorps   xmm0, xmm0
0x180030481  mov     dword ptr [rdx], 0
0x180030487  xor     r14d, r14d
0x18003048a  mov     qword ptr [r8], 0
0x180030491  lea     rcx, [rbp+57h+var_70]
0x180030495  mov     [rbp+57h+Base], r14
0x180030499  movdqu  [rbp+57h+var_70], xmm0
0x18003049e  mov     [rbp+57h+var_60], 0
0x1800304a6  mov     [rbp+57h+var_90], 0
0x1800304ae  mov     [rbp+57h+arg_18], 0
0x1800304b5  mov     [rbp+57h+var_98], 0
0x1800304bd  mov     [rbp+57h+var_B4], 0
0x1800304c4  mov     [rbp+57h+pv], 0
0x1800304cc  mov     [rbp+57h+var_B8], 0
0x1800304d3  mov     qword ptr [rbp+57h+var_80], 0
0x1800304db  mov     dword ptr [rbp+57h+var_B0], 0
0x1800304e2  call    ?GetAllowedThreatIdList@ShieldProvider@@YAJPEAV?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@@Z; ShieldProvider::GetAllowedThreatIdList(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> *)
0x1800304e7  lea     r15d, [r14+2]
0x1800304eb  lea     rbx, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x1800304f2  lea     r12, WPP_GLOBAL_Control
0x1800304f9  test    eax, eax
0x1800304fb  jns     short loc_180030523
0x1800304fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180030504  cmp     rcx, r12
0x180030507  jz      short loc_180030523
0x180030509  test    [rcx+1Ch], r15b
0x18003050d  jz      short loc_180030523
0x18003050f  mov     rcx, [rcx+10h]
0x180030513  mov     edx, 90h
0x180030518  mov     r9d, eax
0x18003051b  mov     r8, rbx
0x18003051e  call    WPP_SF_d
0x180030523  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003052a  lea     rax, [rbp+57h+var_90]
0x18003052e  mov     rcx, rdi
0x180030531  mov     [rsp+30h], rax
0x180030536  lea     r8, [rbp+57h+var_50]
0x18003053a  lea     rax, [rbp+57h+arg_18]
0x18003053e  mov     [rsp+100h+var_D8], rax
0x180030543  movdqu  [rbp+57h+var_50], xmm0
0x180030548  call    ?GetAsrBlockedActionInfos@QueryAndActionManager@ShieldProvider@@AEAAJ_NU_GUID@@W4tagMP_ASR_QUERY_ID@@KPEAKPEAPEAPEAUtagMP_ASR_HISTORY_BLOCKED_ACTION_INFO@@@Z; ShieldProvider::QueryAndActionManager::GetAsrBlockedActionInfos(bool,_GUID,tagMP_ASR_QUERY_ID,ulong,ulong *,tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO * * *)
0x18003054d  test    eax, eax
0x18003054f  jns     short loc_18003057F
0x180030551  mov     rcx, cs:WPP_GLOBAL_Control
0x180030558  cmp     rcx, r12
0x18003055b  jz      short loc_180030577
0x18003055d  test    [rcx+1Ch], r15b
0x180030561  jz      short loc_180030577
0x180030563  mov     rcx, [rcx+10h]
0x180030567  mov     edx, 91h
0x18003056c  mov     r9d, eax
0x18003056f  mov     r8, rbx
0x180030572  call    WPP_SF_d
0x180030577  xor     esi, esi
0x180030579  mov     [rbp+57h+var_90], rsi
0x18003057d  jmp     short loc_18003058A
0x18003057f  mov     rax, [rbp+57h+var_90]
0x180030583  mov     esi, [rbp+57h+arg_18]
0x180030586  mov     [rbp+57h+var_90], rax
0x18003058a  lea     r9, [rbp+57h+var_98]
0x18003058e  mov     [rbp+57h+var_BC], esi
0x180030591  lea     r8, [rbp+57h+var_B4]
0x180030595  mov     edx, r15d
0x180030598  mov     rcx, rdi
0x18003059b  call    ?GetThreats@QueryAndActionManager@ShieldProvider@@AEAAJW4tagMPTHREAT_SOURCE@@PEAKPEAPEAPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::QueryAndActionManager::GetThreats(tagMPTHREAT_SOURCE,ulong *,tagMPTHREAT_INFO * * *)
0x1800305a0  test    eax, eax
0x1800305a2  jns     short loc_1800305D2
0x1800305a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305ab  cmp     rcx, r12
0x1800305ae  jz      short loc_1800305CA
0x1800305b0  test    [rcx+1Ch], r15b
0x1800305b4  jz      short loc_1800305CA
0x1800305b6  mov     rcx, [rcx+10h]
0x1800305ba  mov     edx, 92h
0x1800305bf  mov     r9d, eax
0x1800305c2  mov     r8, rbx
0x1800305c5  call    WPP_SF_d
0x1800305ca  xor     r15d, r15d
0x1800305cd  xor     r13d, r13d
0x1800305d0  jmp     short loc_1800305DA
0x1800305d2  mov     r13, [rbp+57h+var_98]
0x1800305d6  mov     r15d, [rbp+57h+var_B4]
0x1800305da  lea     r8, [rbp+57h+pv]; struct tagMPTHREAT_INFO ***
0x1800305de  mov     [rbp+57h+var_C0], r15d
0x1800305e2  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x1800305e6  mov     rcx, rdi; this
0x1800305e9  call    ?GetOfflineThreats@QueryAndActionManager@ShieldProvider@@QEAAJPEAKPEAPEAPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::QueryAndActionManager::GetOfflineThreats(ulong *,tagMPTHREAT_INFO * * *)
0x1800305ee  test    eax, eax
0x1800305f0  jns     short loc_180030620
0x1800305f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305f9  cmp     rcx, r12
0x1800305fc  jz      short loc_180030618
0x1800305fe  test    byte ptr [rcx+1Ch], 2
0x180030602  jz      short loc_180030618
0x180030604  mov     rcx, [rcx+10h]
0x180030608  mov     edx, 93h
0x18003060d  mov     r9d, eax
0x180030610  mov     r8, rbx
0x180030613  call    WPP_SF_d
0x180030618  xor     ebx, ebx
0x18003061a  mov     [rbp+57h+var_98], rbx
0x18003061e  jmp     short loc_18003062B
0x180030620  mov     rax, [rbp+57h+pv]
0x180030624  mov     ebx, [rbp+57h+var_B8]
0x180030627  mov     [rbp+57h+var_98], rax
0x18003062b  lea     r9, [rbp+57h+var_80]
0x18003062f  mov     [rbp+57h+var_B8], ebx
0x180030632  lea     r8, [rbp+57h+var_B0]
0x180030636  mov     edx, 3
0x18003063b  mov     rcx, rdi
0x18003063e  call    ?GetThreats@QueryAndActionManager@ShieldProvider@@AEAAJW4tagMPTHREAT_SOURCE@@PEAKPEAPEAPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::QueryAndActionManager::GetThreats(tagMPTHREAT_SOURCE,ulong *,tagMPTHREAT_INFO * * *)
0x180030643  test    eax, eax
0x180030645  jns     short loc_18003067B
0x180030647  mov     rcx, cs:WPP_GLOBAL_Control
0x18003064e  cmp     rcx, r12
0x180030651  jz      short loc_180030671
0x180030653  test    byte ptr [rcx+1Ch], 2
0x180030657  jz      short loc_180030671
0x180030659  mov     rcx, [rcx+10h]
0x18003065d  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030664  mov     edx, 94h
0x180030669  mov     r9d, eax
0x18003066c  call    WPP_SF_d
0x180030671  mov     [rbp+57h+var_B4], r14d
0x180030675  mov     [rbp+57h+pv], r14
0x180030679  jmp     short loc_180030689
0x18003067b  mov     rax, qword ptr [rbp+57h+var_80]
0x18003067f  mov     [rbp+57h+pv], rax
0x180030683  mov     eax, dword ptr [rbp+57h+var_B0]
0x180030686  mov     [rbp+57h+var_B4], eax
0x180030689  lea     eax, [r15+rsi]
0x18003068d  mov     r12d, 1
0x180030693  cmp     eax, esi
0x180030695  jb      loc_180030AFA
0x18003069b  lea     r15d, [rax+rbx]
0x18003069f  cmp     r15d, eax
0x1800306a2  jb      loc_180030A85
0x1800306a8  test    r15d, r15d
0x1800306ab  jnz     short loc_1800306B8
0x1800306ad  mov     ebx, r12d
0x1800306b0  mov     [rbp+57h+arg_18], ebx
0x1800306b3  jmp     loc_1800309AE
0x1800306b8  lea     rdx, ds:0[r15*8]; void **
0x1800306c0  mov     r8b, r12b; unsigned __int64
0x1800306c3  lea     rcx, [rbp+57h+Base]; this
0x1800306c7  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x1800306cc  mov     r14, [rbp+57h+Base]
0x1800306d0  mov     ebx, eax
0x1800306d2  mov     [rbp+57h+arg_18], eax
0x1800306d5  test    eax, eax
0x1800306d7  js      loc_180030A99
0x1800306dd  xor     r12d, r12d
0x1800306e0  xor     edi, edi
0x1800306e2  test    esi, esi
0x1800306e4  jz      short loc_180030758
0x1800306e6  lea     rsi, [r14+rdi*8]
0x1800306ea  mov     rcx, rsi
0x1800306ed  call    ??$UtilCoTaskMemAllocObject@UHistoryItem@@@CommonUtil@@YAJPEAPEAUHistoryItem@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<HistoryItem>(HistoryItem * *,unsigned __int64,bool)
0x1800306f2  mov     [rbp+57h+arg_18], eax
0x1800306f5  mov     ebx, eax
0x1800306f7  test    eax, eax
0x1800306f9  js      loc_180030A93
0x1800306ff  mov     rax, [rsi]
0x180030702  mov     edx, 2
0x180030707  mov     r8, [rbp+57h+var_90]; struct tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO **
0x18003070b  mov     [rax], edx
0x18003070d  mov     rax, [r8+rdi*8]
0x180030711  mov     rcx, [rsi]
0x180030714  mov     rax, [rax+8]
0x180030718  mov     rax, [rax+10h]
0x18003071c  mov     [rcx+8], rax
0x180030720  mov     rax, [rsi]
0x180030723  mov     qword ptr [rax+10h], 0
0x18003072b  mov     rax, [rsi]
0x18003072e  mov     [rax+18h], edx
0x180030731  mov     rdx, [rsi]
0x180030734  mov     rcx, [r8+rdi*8]; this
0x180030738  add     rdx, 20h ; ' '; struct tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO *
0x18003073c  call    ?UtilDuplicateAsrHistoryBlockedActionInfo@ShieldProvider@@YAJPEBUtagMP_ASR_HISTORY_BLOCKED_ACTION_INFO@@PEAPEAU2@@Z; ShieldProvider::UtilDuplicateAsrHistoryBlockedActionInfo(tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO const *,tagMP_ASR_HISTORY_BLOCKED_ACTION_INFO * *)
0x180030741  mov     [rbp+57h+arg_18], eax
0x180030744  mov     ebx, eax
0x180030746  test    eax, eax
0x180030748  js      loc_180030A93
0x18003074e  inc     edi
0x180030750  mov     r12d, edi
0x180030753  cmp     edi, [rbp+57h+var_BC]
0x180030756  jb      short loc_1800306E6
0x180030758  xor     esi, esi
0x18003075a  mov     dword ptr [rbp+57h+Base], esi
0x18003075d  cmp     [rbp+57h+var_C0], esi
0x180030760  jbe     loc_180030904
0x180030766  mov     eax, r12d
0x180030769  lea     rdi, [r14+rax*8]
0x18003076d  mov     rcx, rdi
0x180030770  call    ??$UtilCoTaskMemAllocObject@UHistoryItem@@@CommonUtil@@YAJPEAPEAUHistoryItem@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<HistoryItem>(HistoryItem * *,unsigned __int64,bool)
0x180030775  mov     [rbp+57h+arg_18], eax
0x180030778  mov     ebx, eax
0x18003077a  test    eax, eax
0x18003077c  js      loc_180030A93
0x180030782  mov     rax, [rdi]
0x180030785  lea     r8, [rbp+57h+var_B0]; unsigned __int64
0x180030789  mov     dword ptr [rbp+57h+var_B0], 0
0x180030790  mov     dword ptr [rax], 2
0x180030796  mov     rax, [r13+rsi*8+0]
0x18003079b  mov     rcx, [rdi]
0x18003079e  mov     rax, [rax+0B8h]
0x1800307a5  mov     [rcx+8], rax
0x1800307a9  mov     rax, [rdi]
0x1800307ac  mov     qword ptr [rax+10h], 0
0x1800307b4  mov     rdx, [r13+rsi*8+0]
0x1800307b9  mov     rax, [rbp+57h+arg_0]
0x1800307bd  mov     rdx, [rdx]; struct tagMPCONTEXT *
0x1800307c0  mov     rcx, [rax+10h]; this
0x1800307c4  call    ?AssignHistoryItemType@ShieldProvider@@YAJPEAUtagMPCONTEXT@@_KPEAW4HistoryItemType@@@Z; ShieldProvider::AssignHistoryItemType(tagMPCONTEXT *,unsigned __int64,HistoryItemType *)
0x1800307c9  mov     [rbp+57h+arg_18], eax
0x1800307cc  mov     ebx, eax
0x1800307ce  test    eax, eax
0x1800307d0  js      loc_180030A93
0x1800307d6  mov     ecx, dword ptr [rbp+57h+var_B0]
0x1800307d9  mov     rax, [rdi]
0x1800307dc  sub     ecx, 3
0x1800307df  jz      loc_1800308C6
0x1800307e5  cmp     ecx, 1
0x1800307e8  jz      loc_1800308BD
0x1800307ee  mov     dword ptr [rax+18h], 1
0x1800307f5  mov     rdx, [rdi]
0x1800307f8  mov     rcx, [r13+rsi*8+0]; this
0x1800307fd  add     rdx, 20h ; ' '; struct tagMPTHREAT_INFO *
0x180030801  call    ?UtilDuplicateThreat@ShieldProvider@@YAJPEBUtagMPTHREAT_INFO@@PEAPEAU2@@Z; ShieldProvider::UtilDuplicateThreat(tagMPTHREAT_INFO const *,tagMPTHREAT_INFO * *)
0x180030806  mov     [rbp+57h+arg_18], eax
0x180030809  mov     ebx, eax
0x18003080b  test    eax, eax
0x18003080d  js      loc_180030A93
0x180030813  mov     rdx, [r13+rsi*8+0]
0x180030818  mov     r10d, 1
0x18003081e  cmp     [rdx+90h], r10d
0x180030825  jnz     short loc_180030845
0x180030827  mov     rdx, [rdx]
0x18003082a  lea     rcx, [rbp+57h+var_70]
0x18003082e  call    ?IsThreatInAllowedList@ShieldProvider@@YA_NPEAV?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@Z; ShieldProvider::IsThreatInAllowedList(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> *,unsigned __int64)
0x180030833  mov     r10d, 1
0x180030839  test    al, al
0x18003083b  jnz     short loc_180030845
0x18003083d  mov     rax, [rdi]
0x180030840  or      qword ptr [rax+10h], 8
0x180030845  mov     rcx, [r13+rsi*8+0]
0x18003084a  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180030851  cmp     rax, [rcx+70h]
0x180030855  jnz     short loc_180030868
0x180030857  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18003085e  cmp     rax, [rcx+78h]
0x180030862  jz      loc_1800308EB
0x180030868  movups  xmm0, xmmword ptr [rcx+70h]
0x18003086c  mov     r9d, [rbp+57h+var_B4]
0x180030870  xor     cl, cl
0x180030872  xor     r8d, r8d
0x180030875  movdqu  [rbp+57h+var_80], xmm0
0x18003087a  test    r9d, r9d
0x18003087d  jz      short loc_1800308EB
0x18003087f  test    cl, cl
0x180030881  jnz     short loc_1800308B3
0x180030883  mov     rdx, [rbp+57h+pv]
0x180030887  mov     rdx, [rdx+r8*8]
0x18003088b  mov     rax, [rdx+70h]
0x18003088f  sub     rax, qword ptr [rbp+57h+var_80]
0x180030893  jnz     short loc_18003089D
0x180030895  mov     rax, [rdx+78h]
0x180030899  sub     rax, qword ptr [rbp+57h+var_80+8]
0x18003089d  test    rax, rax
0x1800308a0  movzx   ecx, cl
0x1800308a3  cmovz   ecx, r10d
0x1800308a7  add     r8d, r10d
0x1800308aa  cmp     r8d, r9d
0x1800308ad  jb      short loc_18003087F
0x1800308af  test    cl, cl
0x1800308b1  jz      short loc_1800308EB
0x1800308b3  mov     rax, [rdi]
0x1800308b6  or      qword ptr [rax+10h], 4
0x1800308bb  jmp     short loc_1800308EB
0x1800308bd  mov     dword ptr [rax+18h], 4
  ... truncated ...
```
