# ShieldProvider::WscManager::GetSecurityProducts(_WSC_SECURITY_PROVIDER,tagWSC_PRODUCT_INFO * *,int *)

- ea: `0x1800442d0`
- end: `0x18004477f`
- name: `?GetSecurityProducts@WscManager@ShieldProvider@@SAJW4_WSC_SECURITY_PROVIDER@@PEAPEAUtagWSC_PRODUCT_INFO@@PEAH@Z`
- size: `1199`
- prototype: `__int64 __fastcall(enum _WSC_SECURITY_PROVIDER, struct tagWSC_PRODUCT_INFO **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044278`
- `0x1800462a0`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x1800442d0`
- `0x1800e16e4`
- `0x1800e1764`
- `0x1800e17e8`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800444d9`
- `ole32!CoTaskMemFree` at `0x1800444e8`
- `ole32!CoTaskMemFree` at `0x1800444f1`
- `ole32!CoTaskMemFree` at `0x1800444d9`
- `ole32!CoTaskMemFree` at `0x1800444e8`
- `ole32!CoTaskMemFree` at `0x1800444f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800445c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004465e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800446a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800446b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800445c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004465e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800446a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800446b1`

## pseudocode

```c
__int64 __fastcall ShieldProvider::WscManager::GetSecurityProducts(
        unsigned int a1,
        struct tagWSC_PRODUCT_INFO **a2,
        int *a3)
{
  char *v5; // rbx
  int v6; // eax
  int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int i; // esi
  int v11; // eax
  unsigned __int64 v12; // r8
  bool v13; // r9
  int v14; // eax
  void *v15; // rcx
  void *v16; // rcx
  int v17; // eax
  unsigned __int16 *v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 *v21; // r8
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  unsigned int v27; // [rsp+20h] [rbp-30h]
  struct IUnknown *v28; // [rsp+28h] [rbp-28h]
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  BSTR v31; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  int v33; // [rsp+88h] [rbp+38h] BYREF
  int *v34; // [rsp+90h] [rbp+40h] BYREF
  __int64 v35; // [rsp+98h] [rbp+48h] BYREF

  v34 = a3;
  if ( !a2 || a1 != 1 && a1 != 4 )
    return 2147942487LL;
  if ( !g_fIsWscSvcPresent )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, 2147942450LL);
    return 2147942450LL;
  }
  v5 = 0;
  pv = 0;
  ppv = 0;
  v6 = CommonUtil::UtilCoCreateInstanceImpl(
         &ppv,
         &GUID_17072f7b_9abe_4a74_a261_1eb76b55107a,
         &GUID_722a338c_6e8e_4e72_ac27_1417fb0c81c2,
         1u,
         v27,
         v28);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_76;
    v9 = 22;
LABEL_13:
    WPP_SF_d(v8[2], v9, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, (unsigned int)v6);
LABEL_76:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
    return (unsigned int)v7;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_76;
    v9 = 23;
    goto LABEL_13;
  }
  v33 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 64LL))(ppv, &v33);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_76;
    v9 = 24;
    goto LABEL_13;
  }
  for ( i = 0; ; ++i )
  {
    if ( (int)i >= v33 )
      goto LABEL_67;
    v35 = 0;
    v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, i, &v35);
    v7 = v11;
    if ( v11 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_75;
      v25 = 25;
      goto LABEL_74;
    }
    LODWORD(v34) = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int **))(*(_QWORD *)v35 + 64LL))(v35, &v34);
    v7 = v11;
    if ( v11 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_75;
      v25 = 26;
LABEL_74:
      WPP_SF_d(v24[2], v25, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, (unsigned int)v11);
LABEL_75:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v35);
      goto LABEL_76;
    }
    if ( ((unsigned int)v34 & 0xFFFFFFFD) == 0 )
      break;
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v35);
  }
  LOBYTE(v12) = 1;
  v14 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&pv, (void **)0x20, v12, v13);
  v7 = v14;
  if ( v14 >= 0 )
  {
    v5 = (char *)pv;
    *(_DWORD *)pv = (_DWORD)v34;
    v17 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v35 + 72LL))(v35, v5 + 4);
    v7 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids,
          (unsigned int)v17);
LABEL_39:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v35);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
      goto LABEL_29;
    }
    bstrString = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 56LL))(v35, &bstrString);
    if ( v7 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 29;
LABEL_44:
        WPP_SF_d(v19[2], v20, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, (unsigned int)v7);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    v7 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v5 + 8), (unsigned __int16 **)bstrString, v18);
    if ( v7 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 30;
        goto LABEL_44;
      }
LABEL_45:
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_39;
    }
    v31 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 80LL))(v35, &v31);
    if ( v7 >= 0 )
    {
      v7 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v5 + 16), (unsigned __int16 **)v31, v21);
      if ( v7 >= 0 )
      {
        if ( v31 )
          SysFreeString(v31);
        if ( bstrString )
          SysFreeString(bstrString);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v35);
LABEL_67:
        *a2 = (struct tagWSC_PRODUCT_INFO *)v5;
        goto LABEL_76;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_56;
      v23 = 32;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_56:
        if ( v31 )
          SysFreeString(v31);
        goto LABEL_45;
      }
      v23 = 31;
    }
    WPP_SF_d(v22[2], v23, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, (unsigned int)v7);
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids,
      (unsigned int)v14);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v35);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
  v5 = (char *)pv;
LABEL_29:
  if ( v5 )
  {
    v15 = (void *)*((_QWORD *)v5 + 1);
    if ( v15 )
      CoTaskMemFree(v15);
    v16 = (void *)*((_QWORD *)v5 + 2);
    if ( v16 )
      CoTaskMemFree(v16);
    CoTaskMemFree(v5);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800442d0  mov     [rsp-28h+arg_0], rbx
0x1800442d5  mov     [rsp-28h+arg_10], r8
0x1800442da  push    rbp
0x1800442db  push    rsi
0x1800442dc  push    rdi
0x1800442dd  push    r12
0x1800442df  push    r14
0x1800442e1  mov     rbp, rsp
0x1800442e4  sub     rsp, 50h
0x1800442e8  mov     r14, rdx
0x1800442eb  mov     esi, ecx
0x1800442ed  test    rdx, rdx
0x1800442f0  jz      loc_180044766
0x1800442f6  mov     r12d, 1
0x1800442fc  cmp     ecx, r12d
0x1800442ff  jz      short loc_18004430A
0x180044301  cmp     ecx, 4
0x180044304  jnz     loc_180044766
0x18004430a  cmp     cs:?g_fIsWscSvcPresent@@3_NA, 0; bool g_fIsWscSvcPresent
0x180044311  jz      loc_18004472C
0x180044317  xor     ebx, ebx
0x180044319  lea     r8, _GUID_722a338c_6e8e_4e72_ac27_1417fb0c81c2; riid
0x180044320  mov     r9d, r12d; dwClsContext
0x180044323  mov     [rbp+pv], rbx
0x180044327  lea     rdx, _GUID_17072f7b_9abe_4a74_a261_1eb76b55107a; rclsid
0x18004432e  mov     [rbp+ppv], rbx
0x180044332  lea     rcx, [rbp+ppv]; ppv
0x180044336  call    ?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z; CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)
0x18004433b  mov     edi, eax
0x18004433d  test    eax, eax
0x18004433f  jns     short loc_180044367
0x180044341  mov     rcx, cs:WPP_GLOBAL_Control
0x180044348  lea     rdx, WPP_GLOBAL_Control
0x18004434f  cmp     rcx, rdx
0x180044352  jz      loc_18004471F
0x180044358  test    [rcx+1Ch], r12b
0x18004435c  jz      loc_18004471F
0x180044362  lea     edx, [rbx+16h]
0x180044365  jmp     short loc_1800443A5
0x180044367  mov     rcx, [rbp+ppv]
0x18004436b  mov     edx, esi
0x18004436d  mov     rax, [rcx]
0x180044370  mov     rax, [rax+38h]
0x180044374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044379  mov     edi, eax
0x18004437b  test    eax, eax
0x18004437d  jns     short loc_1800443BD
0x18004437f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044386  lea     rdx, WPP_GLOBAL_Control
0x18004438d  cmp     rcx, rdx
0x180044390  jz      loc_18004471F
0x180044396  test    [rcx+1Ch], r12b
0x18004439a  jz      loc_18004471F
0x1800443a0  mov     edx, 17h
0x1800443a5  mov     rcx, [rcx+10h]
0x1800443a9  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x1800443b0  mov     r9d, eax
0x1800443b3  call    WPP_SF_d
0x1800443b8  jmp     loc_18004471F
0x1800443bd  mov     rcx, [rbp+ppv]
0x1800443c1  lea     rdx, [rbp+arg_8]
0x1800443c5  mov     [rbp+arg_8], ebx
0x1800443c8  mov     rax, [rcx]
0x1800443cb  mov     rax, [rax+40h]
0x1800443cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443d4  mov     edi, eax
0x1800443d6  test    eax, eax
0x1800443d8  jns     short loc_180044402
0x1800443da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443e1  lea     rdx, WPP_GLOBAL_Control
0x1800443e8  cmp     rcx, rdx
0x1800443eb  jz      loc_18004471F
0x1800443f1  test    [rcx+1Ch], r12b
0x1800443f5  jz      loc_18004471F
0x1800443fb  mov     edx, 18h
0x180044400  jmp     short loc_1800443A5
0x180044402  xor     esi, esi
0x180044404  cmp     esi, [rbp+arg_8]
0x180044407  jge     loc_1800446C0
0x18004440d  mov     rcx, [rbp+ppv]
0x180044411  lea     r8, [rbp+arg_18]
0x180044415  mov     [rbp+arg_18], rbx
0x180044419  mov     edx, esi
0x18004441b  mov     rax, [rcx]
0x18004441e  mov     rax, [rax+48h]
0x180044422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044427  mov     edi, eax
0x180044429  test    eax, eax
0x18004442b  js      loc_1800446E5
0x180044431  mov     rcx, [rbp+arg_18]
0x180044435  lea     rdx, [rbp+arg_10]
0x180044439  mov     dword ptr [rbp+arg_10], ebx
0x18004443c  mov     rax, [rcx]
0x18004443f  mov     rax, [rax+40h]
0x180044443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044448  mov     edi, eax
0x18004444a  test    eax, eax
0x18004444c  js      loc_1800446C5
0x180044452  test    dword ptr [rbp+arg_10], 0FFFFFFFDh
0x180044459  jz      short loc_180044469
0x18004445b  lea     rcx, [rbp+arg_18]
0x18004445f  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180044464  add     esi, r12d
0x180044467  jmp     short loc_180044404
0x180044469  mov     esi, 20h ; ' '
0x18004446e  lea     rcx, [rbp+pv]; this
0x180044472  mov     edx, esi; void **
0x180044474  mov     r8b, r12b; unsigned __int64
0x180044477  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x18004447c  mov     edi, eax
0x18004447e  test    eax, eax
0x180044480  jns     short loc_1800444FC
0x180044482  mov     rcx, cs:WPP_GLOBAL_Control
0x180044489  lea     rdx, WPP_GLOBAL_Control
0x180044490  cmp     rcx, rdx
0x180044493  jz      short loc_1800444B1
0x180044495  test    [rcx+1Ch], r12b
0x180044499  jz      short loc_1800444B1
0x18004449b  mov     rcx, [rcx+10h]
0x18004449f  lea     edx, [rsi-5]
0x1800444a2  mov     r9d, eax
0x1800444a5  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x1800444ac  call    WPP_SF_d
0x1800444b1  lea     rcx, [rbp+arg_18]
0x1800444b5  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800444ba  lea     rcx, [rbp+ppv]
0x1800444be  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800444c3  mov     rbx, [rbp+pv]
0x1800444c7  test    rbx, rbx
0x1800444ca  jz      loc_180044728
0x1800444d0  mov     rcx, [rbx+8]; pv
0x1800444d4  test    rcx, rcx
0x1800444d7  jz      short loc_1800444DF
0x1800444d9  call    cs:__imp_CoTaskMemFree
0x1800444df  mov     rcx, [rbx+10h]; pv
0x1800444e3  test    rcx, rcx
0x1800444e6  jz      short loc_1800444EE
0x1800444e8  call    cs:__imp_CoTaskMemFree
0x1800444ee  mov     rcx, rbx; pv
0x1800444f1  call    cs:__imp_CoTaskMemFree
0x1800444f7  jmp     loc_180044728
0x1800444fc  mov     eax, dword ptr [rbp+arg_10]
0x1800444ff  mov     rbx, [rbp+pv]
0x180044503  mov     [rbx], eax
0x180044505  lea     rdx, [rbx+4]
0x180044509  mov     rcx, [rbp+arg_18]
0x18004450d  mov     rax, [rcx]
0x180044510  mov     rax, [rax+48h]
0x180044514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044519  mov     edi, eax
0x18004451b  test    eax, eax
0x18004451d  jns     short loc_180044567
0x18004451f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044526  lea     rdx, WPP_GLOBAL_Control
0x18004452d  cmp     rcx, rdx
0x180044530  jz      short loc_180044550
0x180044532  test    [rcx+1Ch], r12b
0x180044536  jz      short loc_180044550
0x180044538  mov     rcx, [rcx+10h]
0x18004453c  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x180044543  mov     edx, 1Ch
0x180044548  mov     r9d, eax
0x18004454b  call    WPP_SF_d
0x180044550  lea     rcx, [rbp+arg_18]
0x180044554  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180044559  lea     rcx, [rbp+ppv]
0x18004455d  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180044562  jmp     loc_1800444C7
0x180044567  mov     rcx, [rbp+arg_18]
0x18004456b  lea     rdx, [rbp+bstrString]
0x18004456f  mov     [rbp+bstrString], 0
0x180044577  mov     rax, [rcx]
0x18004457a  mov     rax, [rax+38h]
0x18004457e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044583  mov     edi, eax
0x180044585  test    eax, eax
0x180044587  jns     short loc_1800445CB
0x180044589  mov     rcx, cs:WPP_GLOBAL_Control
0x180044590  lea     rdx, WPP_GLOBAL_Control
0x180044597  cmp     rcx, rdx
0x18004459a  jz      short loc_1800445BA
0x18004459c  test    [rcx+1Ch], r12b
0x1800445a0  jz      short loc_1800445BA
0x1800445a2  mov     edx, 1Dh
0x1800445a7  mov     rcx, [rcx+10h]
0x1800445ab  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x1800445b2  mov     r9d, edi
0x1800445b5  call    WPP_SF_d
0x1800445ba  mov     rcx, [rbp+bstrString]; bstrString
0x1800445be  test    rcx, rcx
0x1800445c1  jz      short loc_180044550
0x1800445c3  call    cs:__imp_SysFreeString
0x1800445c9  jmp     short loc_180044550
0x1800445cb  mov     rdx, [rbp+bstrString]; unsigned __int16 **
0x1800445cf  lea     rcx, [rbx+8]; this
0x1800445d3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800445d8  mov     edi, eax
0x1800445da  test    eax, eax
0x1800445dc  jns     short loc_1800445FE
0x1800445de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445e5  lea     rdx, WPP_GLOBAL_Control
0x1800445ec  cmp     rcx, rdx
0x1800445ef  jz      short loc_1800445BA
0x1800445f1  test    [rcx+1Ch], r12b
0x1800445f5  jz      short loc_1800445BA
0x1800445f7  mov     edx, 1Eh
0x1800445fc  jmp     short loc_1800445A7
0x1800445fe  mov     rcx, [rbp+arg_18]
0x180044602  lea     rdx, [rbp+var_10]
0x180044606  mov     [rbp+var_10], 0
0x18004460e  mov     rax, [rcx]
0x180044611  mov     rax, [rax+50h]
0x180044615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004461a  mov     edi, eax
0x18004461c  test    eax, eax
0x18004461e  jns     short loc_180044669
0x180044620  mov     rcx, cs:WPP_GLOBAL_Control
0x180044627  lea     rdx, WPP_GLOBAL_Control
0x18004462e  cmp     rcx, rdx
0x180044631  jz      short loc_180044651
0x180044633  test    [rcx+1Ch], r12b
0x180044637  jz      short loc_180044651
0x180044639  mov     edx, 1Fh
0x18004463e  mov     rcx, [rcx+10h]
0x180044642  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x180044649  mov     r9d, edi
0x18004464c  call    WPP_SF_d
0x180044651  mov     rcx, [rbp+var_10]; bstrString
0x180044655  test    rcx, rcx
0x180044658  jz      loc_1800445BA
0x18004465e  call    cs:__imp_SysFreeString
0x180044664  jmp     loc_1800445BA
0x180044669  mov     rdx, [rbp+var_10]; unsigned __int16 **
0x18004466d  lea     rcx, [rbx+10h]; this
0x180044671  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180044676  mov     edi, eax
0x180044678  test    eax, eax
0x18004467a  jns     short loc_180044699
0x18004467c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044683  lea     rdx, WPP_GLOBAL_Control
0x18004468a  cmp     rcx, rdx
0x18004468d  jz      short loc_180044651
0x18004468f  test    [rcx+1Ch], r12b
0x180044693  jz      short loc_180044651
0x180044695  mov     edx, esi
0x180044697  jmp     short loc_18004463E
0x180044699  mov     rcx, [rbp+var_10]; bstrString
0x18004469d  test    rcx, rcx
0x1800446a0  jz      short loc_1800446A8
0x1800446a2  call    cs:__imp_SysFreeString
0x1800446a8  mov     rcx, [rbp+bstrString]; bstrString
0x1800446ac  test    rcx, rcx
0x1800446af  jz      short loc_1800446B7
0x1800446b1  call    cs:__imp_SysFreeString
0x1800446b7  lea     rcx, [rbp+arg_18]
0x1800446bb  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800446c0  mov     [r14], rbx
0x1800446c3  jmp     short loc_18004471F
0x1800446c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446cc  lea     rdx, WPP_GLOBAL_Control
0x1800446d3  cmp     rcx, rdx
0x1800446d6  jz      short loc_180044716
0x1800446d8  test    [rcx+1Ch], r12b
0x1800446dc  jz      short loc_180044716
0x1800446de  mov     edx, 1Ah
0x1800446e3  jmp     short loc_180044703
0x1800446e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446ec  lea     rdx, WPP_GLOBAL_Control
0x1800446f3  cmp     rcx, rdx
0x1800446f6  jz      short loc_180044716
0x1800446f8  test    [rcx+1Ch], r12b
0x1800446fc  jz      short loc_180044716
0x1800446fe  mov     edx, 19h
0x180044703  mov     rcx, [rcx+10h]
0x180044707  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x18004470e  mov     r9d, eax
0x180044711  call    WPP_SF_d
0x180044716  lea     rcx, [rbp+arg_18]
0x18004471a  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18004471f  lea     rcx, [rbp+ppv]
0x180044723  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180044728  mov     eax, edi
0x18004472a  jmp     short loc_18004476B
0x18004472c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044733  lea     rdx, WPP_GLOBAL_Control
0x18004473a  mov     ebx, 80070032h
0x18004473f  cmp     rcx, rdx
0x180044742  jz      short loc_180044762
0x180044744  test    [rcx+1Ch], r12b
0x180044748  jz      short loc_180044762
0x18004474a  mov     rcx, [rcx+10h]
0x18004474e  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x180044755  mov     edx, 15h
0x18004475a  mov     r9d, ebx
0x18004475d  call    WPP_SF_d
0x180044762  mov     eax, ebx
0x180044764  jmp     short loc_18004476B
0x180044766  mov     eax, 80070057h
0x18004476b  mov     rbx, [rsp+50h+arg_0]
0x180044773  add     rsp, 50h
  ... truncated ...
```
