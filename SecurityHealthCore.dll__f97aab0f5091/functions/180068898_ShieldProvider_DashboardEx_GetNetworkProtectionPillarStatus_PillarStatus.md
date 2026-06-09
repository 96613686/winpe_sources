# ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatus(PillarStatus *)

- ea: `0x180068898`
- end: `0x180068a31`
- name: `?GetNetworkProtectionPillarStatus@DashboardEx@ShieldProvider@@AEAAJPEAUPillarStatus@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(ShieldProvider::DashboardEx *__hidden this, struct PillarStatus *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180068df0`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001b7d4`
- `0x180068898`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180068969`
- `ole32!CoTaskMemFree` at `0x180068980`
- `ole32!CoTaskMemFree` at `0x180068991`
- `ole32!CoTaskMemFree` at `0x180068969`
- `ole32!CoTaskMemFree` at `0x180068980`
- `ole32!CoTaskMemFree` at `0x180068991`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatus(
        ShieldProvider::DashboardEx *this,
        struct PillarStatus *a2)
{
  int v5; // edi
  char i; // al
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  int *v10; // rbx
  int v11; // eax
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  _BYTE v15[32]; // [rsp+20h] [rbp-20h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned int)ShieldProvider::IsShieldProviderSvcStopPending(this) )
    return 2147942421LL;
  v5 = 0;
  v16 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v15,
    (char *)this + 112);
  for ( i = 1; ; i = 0 )
  {
    v15[16] = i;
    if ( !i )
      break;
    v7 = *((_QWORD *)this + 22);
    if ( !v7 )
    {
      v5 = -2147024875;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_9a072a55361f3902b023016d7eb82632_Traceguids, 2147942421LL);
      break;
    }
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 96LL))(v7, &v16) >= 0 && v16 )
    {
      v8 = *((_QWORD *)this + 22);
      pv = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 168LL))(v8, &pv);
      v10 = (int *)pv;
      v5 = v9;
      if ( v9 < 0 )
      {
        *((_DWORD *)a2 + 1) = 1;
        v11 = 23;
      }
      else
      {
        *((_DWORD *)a2 + 1) = *((_DWORD *)pv + 1);
        v11 = *v10;
      }
      *(_DWORD *)a2 = v11;
      if ( v10 )
      {
        v12 = (void *)*((_QWORD *)v10 + 1);
        if ( v12 )
        {
          CoTaskMemFree(v12);
          *((_QWORD *)v10 + 1) = 0;
        }
        v13 = (void *)*((_QWORD *)v10 + 2);
        if ( v13 )
        {
          CoTaskMemFree(v13);
          *((_QWORD *)v10 + 2) = 0;
        }
        CoTaskMemFree(v10);
      }
    }
    else
    {
      v14 = *((_QWORD *)this + 22);
      pv = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 144LL))(v14, &pv);
      if ( v5 < 0 )
        pv = (LPVOID)0x100000017LL;
      *(_QWORD *)a2 = pv;
    }
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180068898  mov     [rsp-18h+arg_0], rbx
0x18006889d  mov     [rsp-18h+arg_8], rsi
0x1800688a2  push    rbp
0x1800688a3  push    rdi
0x1800688a4  push    r14
0x1800688a6  mov     rbp, rsp
0x1800688a9  sub     rsp, 40h
0x1800688ad  mov     rsi, rdx
0x1800688b0  mov     r14, rcx
0x1800688b3  call    ?IsShieldProviderSvcStopPending@ShieldProvider@@YAHXZ; ShieldProvider::IsShieldProviderSvcStopPending(void)
0x1800688b8  test    eax, eax
0x1800688ba  jz      short loc_1800688C6
0x1800688bc  mov     eax, 80070015h
0x1800688c1  jmp     loc_180068A1E
0x1800688c6  xor     edi, edi
0x1800688c8  lea     rdx, [r14+70h]
0x1800688cc  lea     rcx, [rbp+var_20]
0x1800688d0  mov     [rbp+arg_10], edi
0x1800688d3  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800688d8  mov     al, 1
0x1800688da  mov     [rbp+var_10], al
0x1800688dd  test    al, al
0x1800688df  jz      loc_180068A13
0x1800688e5  mov     rcx, [r14+0B0h]
0x1800688ec  test    rcx, rcx
0x1800688ef  jz      loc_1800689DD
0x1800688f5  mov     rax, [rcx]
0x1800688f8  lea     rdx, [rbp+arg_10]
0x1800688fc  mov     rax, [rax+60h]
0x180068900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068905  test    eax, eax
0x180068907  js      loc_180068999
0x18006890d  cmp     [rbp+arg_10], 0
0x180068911  jz      loc_180068999
0x180068917  mov     rcx, [r14+0B0h]
0x18006891e  lea     rdx, [rbp+pv]
0x180068922  mov     [rbp+pv], 0
0x18006892a  mov     rax, [rcx]
0x18006892d  mov     rax, [rax+0A8h]
0x180068934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068939  mov     rbx, [rbp+pv]
0x18006893d  mov     edi, eax
0x18006893f  test    eax, eax
0x180068941  js      short loc_18006894D
0x180068943  mov     ecx, [rbx+4]
0x180068946  mov     [rsi+4], ecx
0x180068949  mov     eax, [rbx]
0x18006894b  jmp     short loc_180068959
0x18006894d  mov     dword ptr [rsi+4], 1
0x180068954  mov     eax, 17h
0x180068959  mov     [rsi], eax
0x18006895b  test    rbx, rbx
0x18006895e  jz      short loc_1800689D6
0x180068960  mov     rcx, [rbx+8]; pv
0x180068964  test    rcx, rcx
0x180068967  jz      short loc_180068977
0x180068969  call    cs:__imp_CoTaskMemFree
0x18006896f  mov     qword ptr [rbx+8], 0
0x180068977  mov     rcx, [rbx+10h]; pv
0x18006897b  test    rcx, rcx
0x18006897e  jz      short loc_18006898E
0x180068980  call    cs:__imp_CoTaskMemFree
0x180068986  mov     qword ptr [rbx+10h], 0
0x18006898e  mov     rcx, rbx; pv
0x180068991  call    cs:__imp_CoTaskMemFree
0x180068997  jmp     short loc_1800689D6
0x180068999  mov     rcx, [r14+0B0h]
0x1800689a0  lea     rdx, [rbp+pv]
0x1800689a4  mov     [rbp+pv], 0
0x1800689ac  mov     rax, [rcx]
0x1800689af  mov     rax, [rax+90h]
0x1800689b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689bb  mov     edi, eax
0x1800689bd  test    eax, eax
0x1800689bf  jns     short loc_1800689CF
0x1800689c1  mov     dword ptr [rbp+pv], 17h
0x1800689c8  mov     dword ptr [rbp+pv+4], 1
0x1800689cf  mov     rax, [rbp+pv]
0x1800689d3  mov     [rsi], rax
0x1800689d6  xor     al, al
0x1800689d8  jmp     loc_1800688DA
0x1800689dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800689e4  lea     rax, WPP_GLOBAL_Control
0x1800689eb  mov     edi, 80070015h
0x1800689f0  cmp     rcx, rax
0x1800689f3  jz      short loc_180068A13
0x1800689f5  test    byte ptr [rcx+1Ch], 1
0x1800689f9  jz      short loc_180068A13
0x1800689fb  mov     rcx, [rcx+10h]
0x1800689ff  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x180068a06  mov     edx, 3Bh ; ';'
0x180068a0b  mov     r9d, edi
0x180068a0e  call    WPP_SF_d
0x180068a13  lea     rcx, [rbp+var_20]
0x180068a17  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180068a1c  mov     eax, edi
0x180068a1e  mov     rbx, [rsp+40h+arg_0]
0x180068a23  mov     rsi, [rsp+40h+arg_8]
0x180068a28  add     rsp, 40h
0x180068a2c  pop     r14
0x180068a2e  pop     rdi
0x180068a2f  pop     rbp
0x180068a30  retn
```
