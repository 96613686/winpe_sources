# GetConnectedIdentities(_IdentityType,_IDENTITY_ENTRY * *,ulong *)

- ea: `0x1800074dc`
- end: `0x180007a09`
- name: `?GetConnectedIdentities@@YAJW4_IdentityType@@PEAPEAU_IDENTITY_ENTRY@@PEAK@Z`
- size: `1325`
- prototype: `__int64 __fastcall(enum _IdentityType, LPVOID **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005000`

## callees

- `0x180003290`
- `0x180003560`
- `0x1800074dc`
- `0x1800081f0`
- `0x18000cc10`
- `0x18000dcf0`
- `0x18000dff0`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019722`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007578`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000764f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000764f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000780c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000780c`
- `ntdll!RtlLengthSid` at `0x18000762e`
- `ntdll!RtlLengthSid` at `0x18000762e`

## pseudocode

```c
__int64 __fastcall GetConnectedIdentities(enum _IdentityType a1, LPVOID **a2, unsigned int *a3)
{
  unsigned int j; // r14d
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  CIdentityProfileHandler *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int CallerTokenUserSid; // eax
  CIdentityProfileHandler *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, _QWORD, _QWORD, struct IConnectedUser **); // rbx
  _QWORD *v19; // rsi
  ULONG v20; // eax
  __int64 v21; // r9
  struct _IDENTITY_ENTRY *v22; // rax
  unsigned int i; // edi
  int v24; // eax
  struct _IDENTITY_ENTRY *v25; // rax
  int inited; // eax
  __int64 v27; // r8
  CIdentityProfileHandler *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned int v31; // ebx
  struct IConnectedUser *v33; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v35; // [rsp+40h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v37[2]; // [rsp+50h] [rbp-10h] BYREF
  int v38; // [rsp+98h] [rbp+38h] BYREF
  struct IConnectedUser *v39; // [rsp+A8h] [rbp+48h] BYREF

  v38 = 0;
  ppv = 0;
  v35 = 0;
  j = 0;
  v37[1] = "GetConnectedIdentities";
  v37[0] = &v38;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "GetConnectedIdentities");
  }
  *a2 = 0;
  v7 = CoCreateInstance(
         &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
         0,
         0x17u,
         &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
         &ppv);
  v38 = v7;
  if ( v7 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_72;
    }
    v11 = 106;
LABEL_8:
    v12 = (unsigned int)v7;
    goto LABEL_9;
  }
  if ( a1 == IDENTITIES_ME_ONLY )
  {
    pv = 0;
    v39 = 0;
    CallerTokenUserSid = GetCallerTokenUserSid((struct _TOKEN_USER **)&pv, v8, v9);
    v38 = CallerTokenUserSid;
    if ( CallerTokenUserSid >= 0 )
    {
      v17 = ppv;
      v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, struct IConnectedUser **))(*(_QWORD *)ppv + 56LL);
      v19 = pv;
      v20 = RtlLengthSid(*(PSID *)pv);
      v38 = v18(v17, *v19, v20, &v39);
      CoTaskMemFree(v19);
      v21 = (unsigned int)v38;
      if ( v38 < 0 )
      {
        if ( v38 == -805305819 )
        {
          v21 = 2147942659LL;
          v38 = -2147024637;
        }
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v21);
        }
        goto LABEL_17;
      }
      v22 = (struct _IDENTITY_ENTRY *)CoTaskMemAlloc(0x20u);
      *a2 = (LPVOID *)v22;
      if ( !v22 )
      {
        v38 = -2147024882;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_17;
        }
        v15 = 109;
        v16 = 2147942414LL;
        goto LABEL_16;
      }
      CallerTokenUserSid = InitIdentityEntry(v39, v22);
      v38 = CallerTokenUserSid;
      if ( CallerTokenUserSid >= 0 )
      {
        j = 1;
        goto LABEL_17;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_17;
      }
      v15 = 110;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_17;
      }
      v15 = 107;
    }
    v16 = (unsigned int)CallerTokenUserSid;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v16);
LABEL_17:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v39);
    goto LABEL_72;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, 0, &v35);
  v38 = v7;
  if ( v7 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_72;
    }
    v11 = 111;
    goto LABEL_8;
  }
  for ( i = 1; ; ++i )
  {
    v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, 1);
    v38 = v24;
    if ( v24 < 0 )
      break;
  }
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)v24);
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 40LL))(v35);
  v38 = v7;
  if ( v7 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_72;
    }
    v11 = 113;
    goto LABEL_8;
  }
  v25 = (struct _IDENTITY_ENTRY *)CoTaskMemAlloc(32LL * i);
  *a2 = (LPVOID *)v25;
  if ( !v25 )
  {
    v38 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_73;
    }
    v11 = 114;
    v12 = 2147942414LL;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v12);
    goto LABEL_72;
  }
  memset_0(v25, 0, 32LL * i);
  for ( j = 0; ; ++j )
  {
    pv = 0;
    v33 = 0;
    LODWORD(v39) = 0;
    inited = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, struct IConnectedUser **))(*(_QWORD *)v35 + 24LL))(
               v35,
               1,
               &pv,
               &v39);
    v38 = inited;
    if ( inited )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_71;
      }
      v29 = 115;
LABEL_69:
      v30 = (unsigned int)inited;
LABEL_70:
      WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v30);
      goto LABEL_71;
    }
    if ( j >= i )
    {
      v38 = -2147418113;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_71;
      }
      v29 = 116;
      v30 = 2147549183LL;
      goto LABEL_70;
    }
    ATL::CComQIPtr<IConnectedUser,&__s_GUID const _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d>::operator=(
      (__int64 *)&v33,
      (void (__fastcall ***)(_QWORD, GUID *, __int64 *))pv,
      v27);
    if ( !v33 )
    {
      v38 = -2147467262;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_71;
      }
      v29 = 117;
      v30 = 2147500034LL;
      goto LABEL_70;
    }
    inited = InitIdentityEntry(v33, (struct _IDENTITY_ENTRY *)&(*a2)[4 * j]);
    v38 = inited;
    if ( inited < 0 )
      break;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v33);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pv);
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v29 = 118;
    goto LABEL_69;
  }
LABEL_71:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pv);
LABEL_72:
  if ( v38 < 0 )
  {
LABEL_73:
    FreeIdentityEntries(*a2, j);
    *a2 = 0;
    j = 0;
  }
  *a3 = j;
  v31 = v38;
  if ( v38 >= 0 )
    v31 = 0;
  CLogBlock::~CLogBlock((CLogBlock *)v37, v8, v9);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v31;
}

```

## disassembly

```asm
0x1800074dc  mov     [rsp-28h+arg_0], rbx
0x1800074e1  mov     [rsp-28h+arg_10], rsi
0x1800074e6  push    rbp
0x1800074e7  push    rdi
0x1800074e8  push    r12
0x1800074ea  push    r14
0x1800074ec  push    r15
0x1800074ee  mov     rbp, rsp
0x1800074f1  sub     rsp, 60h
0x1800074f5  mov     r12, r8
0x1800074f8  mov     r15, rdx
0x1800074fb  mov     edi, ecx
0x1800074fd  mov     [rbp+arg_8], 0
0x180007504  mov     [rbp+var_18], 0
0x18000750c  mov     [rbp+var_20], 0
0x180007514  xor     r14d, r14d
0x180007517  lea     r9, aGetconnectedid; "GetConnectedIdentities"
0x18000751e  mov     [rbp+var_8], r9
0x180007522  lea     rax, [rbp+arg_8]
0x180007526  mov     [rbp+var_10], rax
0x18000752a  lea     rsi, WPP_GLOBAL_Control
0x180007531  mov     rcx, cs:WPP_GLOBAL_Control
0x180007538  cmp     rcx, rsi
0x18000753b  jz      short loc_180007554
0x18000753d  test    dword ptr [rcx+1Ch], 400h
0x180007544  jz      short loc_180007554
0x180007546  lea     edx, [r14+0Ah]
0x18000754a  mov     rcx, [rcx+10h]
0x18000754e  call    WPP_SF_s
0x180007553  nop
0x180007554  mov     qword ptr [r15], 0
0x18000755b  lea     rax, [rbp+var_18]
0x18000755f  mov     [rsp+60h+ppv], rax; ppv
0x180007564  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18000756b  xor     edx, edx; pUnkOuter
0x18000756d  lea     r8d, [rdx+17h]; dwClsContext
0x180007571  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180007578  call    cs:__imp_CoCreateInstance
0x18000757e  mov     [rbp+arg_8], eax
0x180007581  test    eax, eax
0x180007583  jns     short loc_1800075BC
0x180007585  mov     rcx, cs:WPP_GLOBAL_Control
0x18000758c  cmp     rcx, rsi
0x18000758f  jz      loc_18000798F
0x180007595  test    byte ptr [rcx+1Ch], 4
0x180007599  jz      loc_18000798F
0x18000759f  mov     edx, 6Ah ; 'j'
0x1800075a4  mov     r9d, eax
0x1800075a7  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800075ae  mov     rcx, [rcx+10h]
0x1800075b2  call    WPP_SF_d
0x1800075b7  jmp     loc_18000798F
0x1800075bc  cmp     edi, 1
0x1800075bf  jnz     loc_180007736
0x1800075c5  mov     [rbp+pv], 0
0x1800075cd  mov     [rbp+arg_18], 0
0x1800075d5  lea     rcx, [rbp+pv]; struct _TOKEN_USER **
0x1800075d9  call    ?GetCallerTokenUserSid@@YAJPEAPEAU_TOKEN_USER@@@Z; GetCallerTokenUserSid(_TOKEN_USER * *)
0x1800075de  mov     [rbp+arg_8], eax
0x1800075e1  test    eax, eax
0x1800075e3  jns     short loc_18000761C
0x1800075e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075ec  cmp     rcx, rsi
0x1800075ef  jz      short loc_18000760E
0x1800075f1  test    byte ptr [rcx+1Ch], 4
0x1800075f5  jz      short loc_18000760E
0x1800075f7  lea     edx, [rdi+6Ah]
0x1800075fa  mov     r9d, eax
0x1800075fd  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180007604  mov     rcx, [rcx+10h]
0x180007608  call    WPP_SF_d
0x18000760d  nop
0x18000760e  lea     rcx, [rbp+arg_18]
0x180007612  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007617  jmp     loc_18000798F
0x18000761c  mov     rdi, [rbp+var_18]
0x180007620  mov     rax, [rdi]
0x180007623  mov     rbx, [rax+38h]
0x180007627  mov     rsi, [rbp+pv]
0x18000762b  mov     rcx, [rsi]; Sid
0x18000762e  call    cs:__imp_RtlLengthSid
0x180007634  lea     r9, [rbp+arg_18]
0x180007638  mov     r8d, eax
0x18000763b  mov     rdx, [rsi]
0x18000763e  mov     rcx, rdi
0x180007641  mov     rax, rbx
0x180007644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007649  mov     [rbp+arg_8], eax
0x18000764c  mov     rcx, rsi; pv
0x18000764f  call    cs:__imp_CoTaskMemFree
0x180007655  mov     r9d, [rbp+arg_8]
0x180007659  test    r9d, r9d
0x18000765c  jns     short loc_1800076A4
0x18000765e  cmp     r9d, 0D0000225h
0x180007665  jnz     short loc_180007671
0x180007667  mov     r9d, 80070103h
0x18000766d  mov     [rbp+arg_8], r9d
0x180007671  mov     rcx, cs:WPP_GLOBAL_Control
0x180007678  lea     rdx, WPP_GLOBAL_Control
0x18000767f  cmp     rcx, rdx
0x180007682  jz      short loc_18000760E
0x180007684  test    byte ptr [rcx+1Ch], 4
0x180007688  jz      short loc_18000760E
0x18000768a  mov     edx, 6Ch ; 'l'
0x18000768f  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180007696  mov     rcx, [rcx+10h]
0x18000769a  call    WPP_SF_d
0x18000769f  jmp     loc_18000760E
0x1800076a4  mov     ecx, 20h ; ' '; cb
0x1800076a9  call    cs:__imp_CoTaskMemAlloc
0x1800076af  mov     [r15], rax
0x1800076b2  test    rax, rax
0x1800076b5  jnz     short loc_1800076ED
0x1800076b7  mov     [rbp+arg_8], 8007000Eh
0x1800076be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076c5  lea     rdx, WPP_GLOBAL_Control
0x1800076cc  cmp     rcx, rdx
0x1800076cf  jz      loc_18000760E
0x1800076d5  test    byte ptr [rcx+1Ch], 4
0x1800076d9  jz      loc_18000760E
0x1800076df  lea     edx, [rax+6Dh]
0x1800076e2  mov     r9d, 8007000Eh
0x1800076e8  jmp     loc_1800075FD
0x1800076ed  mov     rdx, rax; struct _IDENTITY_ENTRY *
0x1800076f0  mov     rcx, [rbp+arg_18]; struct IConnectedUser *
0x1800076f4  call    ?InitIdentityEntry@@YAJPEAUIConnectedUser@@PEAU_IDENTITY_ENTRY@@@Z; InitIdentityEntry(IConnectedUser *,_IDENTITY_ENTRY *)
0x1800076f9  mov     [rbp+arg_8], eax
0x1800076fc  test    eax, eax
0x1800076fe  jns     short loc_18000772B
0x180007700  mov     rcx, cs:WPP_GLOBAL_Control
0x180007707  lea     rdx, WPP_GLOBAL_Control
0x18000770e  cmp     rcx, rdx
0x180007711  jz      loc_18000760E
0x180007717  test    byte ptr [rcx+1Ch], 4
0x18000771b  jz      loc_18000760E
0x180007721  mov     edx, 6Eh ; 'n'
0x180007726  jmp     loc_1800075FA
0x18000772b  mov     r14d, 1
0x180007731  jmp     loc_18000760E
0x180007736  mov     rcx, [rbp+var_18]
0x18000773a  mov     rax, [rcx]
0x18000773d  lea     r9, [rbp+var_20]
0x180007741  xor     r8d, r8d
0x180007744  xor     edx, edx
0x180007746  mov     rax, [rax+18h]
0x18000774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774f  mov     [rbp+arg_8], eax
0x180007752  test    eax, eax
0x180007754  jns     short loc_18000777A
0x180007756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000775d  cmp     rcx, rsi
0x180007760  jz      loc_18000798F
0x180007766  test    byte ptr [rcx+1Ch], 4
0x18000776a  jz      loc_18000798F
0x180007770  mov     edx, 6Fh ; 'o'
0x180007775  jmp     loc_1800075A4
0x18000777a  mov     ebx, 1
0x18000777f  mov     edi, ebx
0x180007781  mov     rcx, [rbp+var_20]
0x180007785  mov     rax, [rcx]
0x180007788  mov     edx, ebx
0x18000778a  mov     rax, [rax+20h]
0x18000778e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007793  mov     [rbp+arg_8], eax
0x180007796  test    eax, eax
0x180007798  js      short loc_18000779E
0x18000779a  add     edi, ebx
0x18000779c  jmp     short loc_180007781
0x18000779e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a5  cmp     rcx, rsi
0x1800077a8  jz      short loc_1800077C8
0x1800077aa  test    byte ptr [rcx+1Ch], 4
0x1800077ae  jz      short loc_1800077C8
0x1800077b0  mov     edx, 70h ; 'p'
0x1800077b5  mov     r9d, eax
0x1800077b8  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800077bf  mov     rcx, [rcx+10h]
0x1800077c3  call    WPP_SF_d
0x1800077c8  mov     rcx, [rbp+var_20]
0x1800077cc  mov     rax, [rcx]
0x1800077cf  mov     rax, [rax+28h]
0x1800077d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d8  mov     [rbp+arg_8], eax
0x1800077db  test    eax, eax
0x1800077dd  jns     short loc_180007803
0x1800077df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077e6  cmp     rcx, rsi
0x1800077e9  jz      loc_18000798F
0x1800077ef  test    byte ptr [rcx+1Ch], 4
0x1800077f3  jz      loc_18000798F
0x1800077f9  mov     edx, 71h ; 'q'
0x1800077fe  jmp     loc_1800075A4
0x180007803  mov     ebx, edi
0x180007805  shl     rbx, 5
0x180007809  mov     rcx, rbx; cb
0x18000780c  call    cs:__imp_CoTaskMemAlloc
0x180007812  mov     [r15], rax
0x180007815  test    rax, rax
0x180007818  jnz     short loc_180007849
0x18000781a  mov     [rbp+arg_8], 8007000Eh
0x180007821  mov     rcx, cs:WPP_GLOBAL_Control
0x180007828  cmp     rcx, rsi
0x18000782b  jz      loc_180007995
0x180007831  test    byte ptr [rcx+1Ch], 4
0x180007835  jz      loc_180007995
0x18000783b  lea     edx, [rax+72h]
0x18000783e  mov     r9d, 8007000Eh
0x180007844  jmp     loc_1800075A7
0x180007849  mov     r8, rbx; Size
0x18000784c  xor     edx, edx; Val
0x18000784e  mov     rcx, rax; void *
0x180007851  call    memset_0
0x180007856  xor     r14d, r14d
0x180007859  mov     [rbp+pv], 0
0x180007861  mov     [rbp+var_30], 0
0x180007869  mov     dword ptr [rbp+arg_18], 0
0x180007870  mov     rcx, [rbp+var_20]
0x180007874  mov     rax, [rcx]
0x180007877  lea     r9, [rbp+arg_18]
0x18000787b  lea     r8, [rbp+pv]
0x18000787f  mov     edx, 1
0x180007884  mov     rax, [rax+18h]
0x180007888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788d  mov     [rbp+arg_8], eax
0x180007890  test    eax, eax
0x180007892  jnz     loc_180007951
0x180007898  cmp     r14d, edi
0x18000789b  jnb     loc_18000792B
0x1800078a1  mov     rdx, [rbp+pv]
0x1800078a5  lea     rcx, [rbp+var_30]
0x1800078a9  call    ??4?$CComQIPtr@UIConnectedUser@@$1?_GUID_9d5f2149_de8c_45f2_b313_6587a04f771d@@3U__s_GUID@@B@ATL@@QEAAPEAUIConnectedUser@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IConnectedUser,&__s_GUID const _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d>::operator=(IUnknown *)
0x1800078ae  mov     rcx, [rbp+var_30]; struct IConnectedUser *
0x1800078b2  test    rcx, rcx
0x1800078b5  jz      short loc_180007905
0x1800078b7  mov     edx, r14d
0x1800078ba  shl     rdx, 5
0x1800078be  add     rdx, [r15]; struct _IDENTITY_ENTRY *
0x1800078c1  call    ?InitIdentityEntry@@YAJPEAUIConnectedUser@@PEAU_IDENTITY_ENTRY@@@Z; InitIdentityEntry(IConnectedUser *,_IDENTITY_ENTRY *)
0x1800078c6  mov     [rbp+arg_8], eax
0x1800078c9  test    eax, eax
0x1800078cb  js      short loc_1800078E8
0x1800078cd  inc     r14d
0x1800078d0  lea     rcx, [rbp+var_30]
0x1800078d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800078d9  nop
0x1800078da  lea     rcx, [rbp+pv]
0x1800078de  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800078e3  jmp     loc_180007859
0x1800078e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078ef  cmp     rcx, rsi
0x1800078f2  jz      loc_18000797C
0x1800078f8  test    byte ptr [rcx+1Ch], 4
0x1800078fc  jz      short loc_18000797C
0x1800078fe  mov     edx, 76h ; 'v'
0x180007903  jmp     short loc_180007968
0x180007905  mov     [rbp+arg_8], 80004002h
0x18000790c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007913  cmp     rcx, rsi
0x180007916  jz      short loc_18000797C
0x180007918  test    byte ptr [rcx+1Ch], 4
0x18000791c  jz      short loc_18000797C
0x18000791e  mov     edx, 75h ; 'u'
0x180007923  mov     r9d, 80004002h
0x180007929  jmp     short loc_18000796B
0x18000792b  mov     [rbp+arg_8], 8000FFFFh
0x180007932  mov     rcx, cs:WPP_GLOBAL_Control
0x180007939  cmp     rcx, rsi
0x18000793c  jz      short loc_18000797C
0x18000793e  test    byte ptr [rcx+1Ch], 4
0x180007942  jz      short loc_18000797C
0x180007944  mov     edx, 74h ; 't'
0x180007949  mov     r9d, 8000FFFFh
0x18000794f  jmp     short loc_18000796B
0x180007951  mov     rcx, cs:WPP_GLOBAL_Control
0x180007958  cmp     rcx, rsi
0x18000795b  jz      short loc_18000797C
0x18000795d  test    byte ptr [rcx+1Ch], 4
0x180007961  jz      short loc_18000797C
0x180007963  mov     edx, 73h ; 's'
0x180007968  mov     r9d, eax
0x18000796b  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180007972  mov     rcx, [rcx+10h]
0x180007976  call    WPP_SF_d
0x18000797b  nop
0x18000797c  lea     rcx, [rbp+var_30]
0x180007980  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007985  nop
0x180007986  lea     rcx, [rbp+pv]
0x18000798a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000798f  cmp     [rbp+arg_8], 0
0x180007993  jge     short loc_1800079AA
0x180007995  mov     edx, r14d; unsigned int
0x180007998  mov     rcx, [r15]; pv
0x18000799b  call    ?FreeIdentityEntries@@YAXPEAU_IDENTITY_ENTRY@@K@Z; FreeIdentityEntries(_IDENTITY_ENTRY *,ulong)
0x1800079a0  mov     qword ptr [r15], 0
0x1800079a7  xor     r14d, r14d
0x1800079aa  mov     [r12], r14d
0x1800079ae  mov     ebx, [rbp+arg_8]
0x1800079b1  xor     eax, eax
0x1800079b3  test    ebx, ebx
  ... truncated ...
```
