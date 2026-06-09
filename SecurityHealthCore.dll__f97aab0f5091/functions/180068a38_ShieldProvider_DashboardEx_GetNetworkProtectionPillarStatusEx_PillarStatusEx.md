# ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatusEx(PillarStatusEx * *)

- ea: `0x180068a38`
- end: `0x180068c4e`
- name: `?GetNetworkProtectionPillarStatusEx@DashboardEx@ShieldProvider@@AEAAJPEAPEAUPillarStatusEx@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(ShieldProvider::DashboardEx *__hidden this, struct PillarStatusEx **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069000`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001b7d4`
- `0x180037d70`
- `0x180068a38`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180068b5b`
- `ole32!CoTaskMemFree` at `0x180068b6e`
- `ole32!CoTaskMemFree` at `0x180068b7b`
- `ole32!CoTaskMemFree` at `0x180068bd1`
- `ole32!CoTaskMemFree` at `0x180068be4`
- `ole32!CoTaskMemFree` at `0x180068bf1`
- `ole32!CoTaskMemFree` at `0x180068b5b`
- `ole32!CoTaskMemFree` at `0x180068b6e`
- `ole32!CoTaskMemFree` at `0x180068b7b`
- `ole32!CoTaskMemFree` at `0x180068bd1`
- `ole32!CoTaskMemFree` at `0x180068be4`
- `ole32!CoTaskMemFree` at `0x180068bf1`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatusEx(
        ShieldProvider::DashboardEx *this,
        LPVOID *a2)
{
  __int64 v5; // rcx
  int v6; // edi
  int v7; // eax
  struct PillarStatusEx *v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rbx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v17[24]; // [rsp+28h] [rbp-18h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned int)ShieldProvider::IsShieldProviderSvcStopPending(this) )
    return 2147942421LL;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_9a072a55361f3902b023016d7eb82632_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v17,
    (char *)this + 112);
  v5 = *((_QWORD *)this + 22);
  if ( v5 )
  {
    v18 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 96LL))(v5, &v18);
    pv = 0;
    if ( v7 >= 0 && v18 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 22) + 168LL))(*((_QWORD *)this + 22), &pv);
      if ( v6 >= 0 )
      {
        v8 = (struct PillarStatusEx *)pv;
        v9 = 0;
        pv = 0;
        *a2 = v8;
        goto LABEL_24;
      }
    }
    else
    {
      v10 = *((_QWORD *)this + 22);
      v16 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 144LL))(v10, &v16);
      if ( v6 >= 0 )
      {
        v11 = pv;
        if ( pv )
        {
          v12 = (void *)*((_QWORD *)pv + 1);
          if ( v12 )
          {
            CoTaskMemFree(v12);
            v11[1] = 0;
          }
          v13 = (void *)v11[2];
          if ( v13 )
          {
            CoTaskMemFree(v13);
            v11[2] = 0;
          }
          CoTaskMemFree(v11);
          pv = 0;
        }
        v6 = CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(&pv);
        if ( v6 >= 0 )
        {
          v9 = 0;
          *(_QWORD *)pv = v16;
          *((_QWORD *)pv + 1) = 0;
          *((_QWORD *)pv + 2) = 0;
          *a2 = pv;
          pv = 0;
          goto LABEL_24;
        }
      }
    }
    v9 = pv;
LABEL_24:
    if ( v9 )
    {
      v14 = (void *)v9[1];
      if ( v14 )
      {
        CoTaskMemFree(v14);
        v9[1] = 0;
      }
      v15 = (void *)v9[2];
      if ( v15 )
      {
        CoTaskMemFree(v15);
        v9[2] = 0;
      }
      CoTaskMemFree(v9);
    }
    goto LABEL_30;
  }
  v6 = -2147024875;
LABEL_30:
  v17[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v17);
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_9a072a55361f3902b023016d7eb82632_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180068a38  mov     [rsp-18h+arg_0], rbx
0x180068a3d  mov     [rsp-18h+arg_8], rsi
0x180068a42  push    rbp
0x180068a43  push    rdi
0x180068a44  push    r14
0x180068a46  mov     rbp, rsp
0x180068a49  sub     rsp, 40h
0x180068a4d  mov     rsi, rdx
0x180068a50  mov     rbx, rcx
0x180068a53  call    ?IsShieldProviderSvcStopPending@ShieldProvider@@YAHXZ; ShieldProvider::IsShieldProviderSvcStopPending(void)
0x180068a58  xor     r14d, r14d
0x180068a5b  test    eax, eax
0x180068a5d  jz      short loc_180068A69
0x180068a5f  mov     eax, 80070015h
0x180068a64  jmp     loc_180068C3B
0x180068a69  test    rsi, rsi
0x180068a6c  jnz     short loc_180068AA9
0x180068a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a75  lea     rax, WPP_GLOBAL_Control
0x180068a7c  mov     ebx, 80070057h
0x180068a81  cmp     rcx, rax
0x180068a84  jz      short loc_180068AA2
0x180068a86  test    byte ptr [rcx+1Ch], 1
0x180068a8a  jz      short loc_180068AA2
0x180068a8c  mov     rcx, [rcx+10h]
0x180068a90  lea     edx, [rsi+3Dh]
0x180068a93  mov     r9d, ebx
0x180068a96  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x180068a9d  call    WPP_SF_d
0x180068aa2  mov     eax, ebx
0x180068aa4  jmp     loc_180068C3B
0x180068aa9  lea     rdx, [rbx+70h]
0x180068aad  lea     rcx, [rbp+var_18]
0x180068ab1  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180068ab6  mov     rcx, [rbx+0B0h]
0x180068abd  test    rcx, rcx
0x180068ac0  jnz     short loc_180068ACC
0x180068ac2  mov     edi, 80070015h
0x180068ac7  jmp     loc_180068BF7
0x180068acc  mov     [rbp+arg_10], r14d
0x180068ad0  lea     rdx, [rbp+arg_10]
0x180068ad4  mov     rax, [rcx]
0x180068ad7  mov     rax, [rax+60h]
0x180068adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ae0  mov     [rbp+pv], r14
0x180068ae4  test    eax, eax
0x180068ae6  js      short loc_180068B25
0x180068ae8  cmp     [rbp+arg_10], r14d
0x180068aec  jz      short loc_180068B25
0x180068aee  mov     rcx, [rbx+0B0h]
0x180068af5  lea     rdx, [rbp+pv]
0x180068af9  mov     rax, [rcx]
0x180068afc  mov     rax, [rax+0A8h]
0x180068b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b08  mov     edi, eax
0x180068b0a  test    eax, eax
0x180068b0c  js      loc_180068BBF
0x180068b12  mov     rcx, [rbp+pv]
0x180068b16  mov     rbx, r14
0x180068b19  mov     [rbp+pv], rbx
0x180068b1d  mov     [rsi], rcx
0x180068b20  jmp     loc_180068BC3
0x180068b25  mov     rcx, [rbx+0B0h]
0x180068b2c  lea     rdx, [rbp+var_20]
0x180068b30  mov     [rbp+var_20], r14
0x180068b34  mov     rax, [rcx]
0x180068b37  mov     rax, [rax+90h]
0x180068b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b43  mov     edi, eax
0x180068b45  test    eax, eax
0x180068b47  js      short loc_180068BBF
0x180068b49  mov     rbx, [rbp+pv]
0x180068b4d  test    rbx, rbx
0x180068b50  jz      short loc_180068B85
0x180068b52  mov     rcx, [rbx+8]; pv
0x180068b56  test    rcx, rcx
0x180068b59  jz      short loc_180068B65
0x180068b5b  call    cs:__imp_CoTaskMemFree
0x180068b61  mov     [rbx+8], r14
0x180068b65  mov     rcx, [rbx+10h]; pv
0x180068b69  test    rcx, rcx
0x180068b6c  jz      short loc_180068B78
0x180068b6e  call    cs:__imp_CoTaskMemFree
0x180068b74  mov     [rbx+10h], r14
0x180068b78  mov     rcx, rbx; pv
0x180068b7b  call    cs:__imp_CoTaskMemFree
0x180068b81  mov     [rbp+pv], r14
0x180068b85  lea     rcx, [rbp+pv]
0x180068b89  call    ??$UtilCoTaskMemAllocObject@UPillarStatusEx@@@CommonUtil@@YAJPEAPEAUPillarStatusEx@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(PillarStatusEx * *,unsigned __int64,bool)
0x180068b8e  mov     edi, eax
0x180068b90  test    eax, eax
0x180068b92  js      short loc_180068BBF
0x180068b94  mov     rcx, [rbp+pv]
0x180068b98  mov     rbx, r14
0x180068b9b  mov     rax, [rbp+var_20]
0x180068b9f  mov     [rcx], rax
0x180068ba2  mov     rax, [rbp+pv]
0x180068ba6  mov     [rax+8], r14
0x180068baa  mov     rax, [rbp+pv]
0x180068bae  mov     [rax+10h], r14
0x180068bb2  mov     rax, [rbp+pv]
0x180068bb6  mov     [rsi], rax
0x180068bb9  mov     [rbp+pv], rbx
0x180068bbd  jmp     short loc_180068BC3
0x180068bbf  mov     rbx, [rbp+pv]
0x180068bc3  test    rbx, rbx
0x180068bc6  jz      short loc_180068BF7
0x180068bc8  mov     rcx, [rbx+8]; pv
0x180068bcc  test    rcx, rcx
0x180068bcf  jz      short loc_180068BDB
0x180068bd1  call    cs:__imp_CoTaskMemFree
0x180068bd7  mov     [rbx+8], r14
0x180068bdb  mov     rcx, [rbx+10h]; pv
0x180068bdf  test    rcx, rcx
0x180068be2  jz      short loc_180068BEE
0x180068be4  call    cs:__imp_CoTaskMemFree
0x180068bea  mov     [rbx+10h], r14
0x180068bee  mov     rcx, rbx; pv
0x180068bf1  call    cs:__imp_CoTaskMemFree
0x180068bf7  lea     rcx, [rbp+var_18]
0x180068bfb  mov     [rbp+var_8], r14b
0x180068bff  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180068c04  test    edi, edi
0x180068c06  jns     short loc_180068C39
0x180068c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c0f  lea     rax, WPP_GLOBAL_Control
0x180068c16  cmp     rcx, rax
0x180068c19  jz      short loc_180068C39
0x180068c1b  test    byte ptr [rcx+1Ch], 1
0x180068c1f  jz      short loc_180068C39
0x180068c21  mov     rcx, [rcx+10h]
0x180068c25  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x180068c2c  mov     edx, 3Eh ; '>'
0x180068c31  mov     r9d, edi
0x180068c34  call    WPP_SF_d
0x180068c39  mov     eax, edi
0x180068c3b  mov     rbx, [rsp+40h+arg_0]
0x180068c40  mov     rsi, [rsp+40h+arg_8]
0x180068c45  add     rsp, 40h
0x180068c49  pop     r14
0x180068c4b  pop     rdi
0x180068c4c  pop     rbp
0x180068c4d  retn
```
