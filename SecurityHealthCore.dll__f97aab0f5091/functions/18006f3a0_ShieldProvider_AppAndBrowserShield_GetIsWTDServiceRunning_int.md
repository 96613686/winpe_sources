# ShieldProvider::AppAndBrowserShield::GetIsWTDServiceRunning(int *)

- ea: `0x18006f3a0`
- end: `0x18006f6da`
- name: `?GetIsWTDServiceRunning@AppAndBrowserShield@ShieldProvider@@AEAAJPEAH@Z`
- size: `826`
- prototype: `__int64 __fastcall(ShieldProvider::AppAndBrowserShield *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071ff0`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18006f3a0`
- `0x180070b6c`
- `0x180075730`
- `0x1800e1a1c`
- `0x1800e1a88`
- `0x1800e1b08`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f4cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f4e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f527`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f535`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f594`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f606`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f618`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f67e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f68c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f6ab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f6b9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f4cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f4e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f527`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f535`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f594`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f606`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f618`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f67e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f68c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f6ab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f6b9`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AppAndBrowserShield::GetIsWTDServiceRunning(
        ShieldProvider::AppAndBrowserShield *this,
        int *a2)
{
  struct SC_HANDLE__ **v3; // rdx
  unsigned int v4; // r8d
  const unsigned __int16 *v5; // r9
  unsigned int v6; // edi
  PVOID *v7; // rax
  SC_HANDLE v8; // rcx
  SC_HANDLE v9; // rbx
  struct SC_HANDLE__ **v10; // rdx
  unsigned int v11; // r8d
  const unsigned __int16 *v12; // r9
  int v13; // esi
  int v15; // eax
  unsigned int v16; // ebx
  SC_HANDLE v17; // rbx
  int v18; // eax
  struct SC_HANDLE__ *v19; // r8
  SC_HANDLE v20; // rdi
  int v21; // eax
  unsigned int v22; // r14d
  SC_HANDLE hService; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE hSCObject; // [rsp+28h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl'::`2'::impl)
    && !IsActiveSessionCountLimited() )
  {
    return 0;
  }
  v6 = CommonUtil::HrOpenSCManager((CommonUtil *)&hService, v3, v4, v5, 0);
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v6);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = hService;
    if ( !hService )
      goto LABEL_21;
    goto LABEL_20;
  }
  v9 = hService;
  hSCObject = 0;
  v6 = CommonUtil::HrOpenService(
         (CommonUtil *)&hSCObject,
         (struct SC_HANDLE__ **)hService,
         (struct SC_HANDLE__ *)&stru_1800FD090,
         (const unsigned __int16 *)4,
         (unsigned int)hService);
  if ( v6 == -2147023836 )
  {
    v13 = 0;
  }
  else if ( v6 )
  {
    v13 = 0;
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v6);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( hSCObject )
      {
        CloseServiceHandle(hSCObject);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v9 )
        goto LABEL_21;
      v8 = v9;
LABEL_20:
      CloseServiceHandle(v8);
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
        WPP_SF_d(v7[2], 135, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v6);
      return v6;
    }
  }
  else
  {
    v13 = 1;
  }
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( !v13 )
    return 0;
  hSCObject = 0;
  v15 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, v10, v11, v12, (const unsigned __int16 *)hService);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        136,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v15);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v16;
  }
  v17 = hSCObject;
  v18 = CommonUtil::HrOpenService(
          (CommonUtil *)&hService,
          (struct SC_HANDLE__ **)hSCObject,
          (struct SC_HANDLE__ *)&stru_1800FD090,
          (const unsigned __int16 *)4,
          0);
  v6 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v18);
    if ( hService )
      CloseServiceHandle(hService);
    if ( v17 )
      CloseServiceHandle(v17);
    return v6;
  }
  v20 = hService;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v21 = CommonUtil::HrQueryServiceStatus(&ServiceStatus, hService, v19);
  v22 = v21;
  if ( v21 >= 0 )
  {
    *a2 = ServiceStatus.dwCurrentState == 4;
    if ( v20 )
      CloseServiceHandle(v20);
    if ( v17 )
      CloseServiceHandle(v17);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      138,
      WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
      (unsigned int)v21);
  if ( v20 )
    CloseServiceHandle(v20);
  if ( v17 )
    CloseServiceHandle(v17);
  return v22;
}

```

## disassembly

```asm
0x18006f3a0  push    rbp
0x18006f3a2  push    rbx
0x18006f3a3  push    rsi
0x18006f3a4  push    rdi
0x18006f3a5  push    r14
0x18006f3a7  push    r15
0x18006f3a9  mov     rbp, rsp
0x18006f3ac  sub     rsp, 68h
0x18006f3b0  mov     rax, cs:__security_cookie
0x18006f3b7  xor     rax, rsp
0x18006f3ba  mov     [rbp+var_18], rax
0x18006f3be  mov     r15, rdx
0x18006f3c1  mov     dword ptr [rdx], 0
0x18006f3c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix> `wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl(void)'::`2'::impl
0x18006f3ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(void)
0x18006f3d3  test    al, al
0x18006f3d5  jz      short loc_18006F3E4
0x18006f3d7  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x18006f3dc  test    al, al
0x18006f3de  jz      loc_18006F6BF
0x18006f3e4  lea     rcx, [rbp+hService]; this
0x18006f3e8  mov     [rbp+hService], 0
0x18006f3f0  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18006f3f5  mov     edi, eax
0x18006f3f7  test    eax, eax
0x18006f3f9  jns     short loc_18006F445
0x18006f3fb  mov     rax, cs:WPP_GLOBAL_Control
0x18006f402  lea     rsi, WPP_GLOBAL_Control
0x18006f409  cmp     rax, rsi
0x18006f40c  jz      short loc_18006F433
0x18006f40e  test    byte ptr [rax+1Ch], 1
0x18006f412  jz      short loc_18006F433
0x18006f414  mov     rcx, [rax+10h]
0x18006f418  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f41f  mov     edx, 85h
0x18006f424  mov     r9d, edi
0x18006f427  call    WPP_SF_d
0x18006f42c  mov     rax, cs:WPP_GLOBAL_Control
0x18006f433  mov     rcx, [rbp+hService]
0x18006f437  test    rcx, rcx
0x18006f43a  jz      loc_18006F4EF
0x18006f440  jmp     loc_18006F4E2
0x18006f445  mov     rbx, [rbp+hService]
0x18006f449  lea     r8, stru_1800FD090; struct SC_HANDLE__ *
0x18006f450  mov     rdx, rbx; struct SC_HANDLE__ **
0x18006f453  mov     [rbp+hSCObject], 0
0x18006f45b  mov     r9d, 4; unsigned __int16 *
0x18006f461  lea     rcx, [rbp+hSCObject]; this
0x18006f465  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18006f46a  mov     edi, eax
0x18006f46c  cmp     eax, 80070424h
0x18006f471  jnz     short loc_18006F47A
0x18006f473  xor     esi, esi
0x18006f475  jmp     loc_18006F51E
0x18006f47a  test    edi, edi
0x18006f47c  jz      loc_18006F519
0x18006f482  xor     esi, esi
0x18006f484  test    edi, edi
0x18006f486  jns     loc_18006F51E
0x18006f48c  mov     rax, cs:WPP_GLOBAL_Control
0x18006f493  lea     rsi, WPP_GLOBAL_Control
0x18006f49a  cmp     rax, rsi
0x18006f49d  jz      short loc_18006F4C4
0x18006f49f  test    byte ptr [rax+1Ch], 1
0x18006f4a3  jz      short loc_18006F4C4
0x18006f4a5  mov     rcx, [rax+10h]
0x18006f4a9  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f4b0  mov     edx, 86h
0x18006f4b5  mov     r9d, edi
0x18006f4b8  call    WPP_SF_d
0x18006f4bd  mov     rax, cs:WPP_GLOBAL_Control
0x18006f4c4  mov     rcx, [rbp+hSCObject]; hSCObject
0x18006f4c8  test    rcx, rcx
0x18006f4cb  jz      short loc_18006F4DA
0x18006f4cd  call    cs:__imp_CloseServiceHandle
0x18006f4d3  mov     rax, cs:WPP_GLOBAL_Control
0x18006f4da  test    rbx, rbx
0x18006f4dd  jz      short loc_18006F4EF
0x18006f4df  mov     rcx, rbx; hSCObject
0x18006f4e2  call    cs:__imp_CloseServiceHandle
0x18006f4e8  mov     rax, cs:WPP_GLOBAL_Control
0x18006f4ef  cmp     rax, rsi
0x18006f4f2  jz      short loc_18006F512
0x18006f4f4  test    byte ptr [rax+1Ch], 1
0x18006f4f8  jz      short loc_18006F512
0x18006f4fa  mov     rcx, [rax+10h]
0x18006f4fe  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f505  mov     edx, 87h
0x18006f50a  mov     r9d, edi
0x18006f50d  call    WPP_SF_d
0x18006f512  mov     eax, edi
0x18006f514  jmp     loc_18006F6C1
0x18006f519  mov     esi, 1
0x18006f51e  mov     rcx, [rbp+hSCObject]; hSCObject
0x18006f522  test    rcx, rcx
0x18006f525  jz      short loc_18006F52D
0x18006f527  call    cs:__imp_CloseServiceHandle
0x18006f52d  test    rbx, rbx
0x18006f530  jz      short loc_18006F53B
0x18006f532  mov     rcx, rbx; hSCObject
0x18006f535  call    cs:__imp_CloseServiceHandle
0x18006f53b  test    esi, esi
0x18006f53d  jz      loc_18006F6BF
0x18006f543  lea     rcx, [rbp+hSCObject]; this
0x18006f547  mov     [rbp+hSCObject], 0
0x18006f54f  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18006f554  mov     ebx, eax
0x18006f556  test    eax, eax
0x18006f558  jns     short loc_18006F5A1
0x18006f55a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f561  lea     rsi, WPP_GLOBAL_Control
0x18006f568  cmp     rcx, rsi
0x18006f56b  jz      short loc_18006F58B
0x18006f56d  test    byte ptr [rcx+1Ch], 1
0x18006f571  jz      short loc_18006F58B
0x18006f573  mov     rcx, [rcx+10h]
0x18006f577  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f57e  mov     edx, 88h
0x18006f583  mov     r9d, eax
0x18006f586  call    WPP_SF_d
0x18006f58b  mov     rcx, [rbp+hSCObject]; hSCObject
0x18006f58f  test    rcx, rcx
0x18006f592  jz      short loc_18006F59A
0x18006f594  call    cs:__imp_CloseServiceHandle
0x18006f59a  mov     eax, ebx
0x18006f59c  jmp     loc_18006F6C1
0x18006f5a1  mov     rbx, [rbp+hSCObject]
0x18006f5a5  lea     r8, stru_1800FD090; struct SC_HANDLE__ *
0x18006f5ac  mov     rdx, rbx; struct SC_HANDLE__ **
0x18006f5af  mov     [rbp+hService], 0
0x18006f5b7  mov     r9d, 4; unsigned __int16 *
0x18006f5bd  lea     rcx, [rbp+hService]; this
0x18006f5c1  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18006f5c6  mov     edi, eax
0x18006f5c8  test    eax, eax
0x18006f5ca  jns     short loc_18006F623
0x18006f5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5d3  lea     rsi, WPP_GLOBAL_Control
0x18006f5da  cmp     rcx, rsi
0x18006f5dd  jz      short loc_18006F5FD
0x18006f5df  test    byte ptr [rcx+1Ch], 1
0x18006f5e3  jz      short loc_18006F5FD
0x18006f5e5  mov     rcx, [rcx+10h]
0x18006f5e9  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f5f0  mov     edx, 89h
0x18006f5f5  mov     r9d, eax
0x18006f5f8  call    WPP_SF_d
0x18006f5fd  mov     rcx, [rbp+hService]; hSCObject
0x18006f601  test    rcx, rcx
0x18006f604  jz      short loc_18006F60C
0x18006f606  call    cs:__imp_CloseServiceHandle
0x18006f60c  test    rbx, rbx
0x18006f60f  jz      loc_18006F512
0x18006f615  mov     rcx, rbx; hSCObject
0x18006f618  call    cs:__imp_CloseServiceHandle
0x18006f61e  jmp     loc_18006F512
0x18006f623  mov     rdi, [rbp+hService]
0x18006f627  lea     rcx, [rbp+ServiceStatus]; lpServiceStatus
0x18006f62b  xorps   xmm0, xmm0
0x18006f62e  mov     rdx, rdi; hService
0x18006f631  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18006f635  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18006f639  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x18006f63e  mov     r14d, eax
0x18006f641  test    eax, eax
0x18006f643  jns     short loc_18006F697
0x18006f645  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f64c  lea     rsi, WPP_GLOBAL_Control
0x18006f653  cmp     rcx, rsi
0x18006f656  jz      short loc_18006F676
0x18006f658  test    byte ptr [rcx+1Ch], 1
0x18006f65c  jz      short loc_18006F676
0x18006f65e  mov     rcx, [rcx+10h]
0x18006f662  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006f669  mov     edx, 8Ah
0x18006f66e  mov     r9d, eax
0x18006f671  call    WPP_SF_d
0x18006f676  test    rdi, rdi
0x18006f679  jz      short loc_18006F684
0x18006f67b  mov     rcx, rdi; hSCObject
0x18006f67e  call    cs:__imp_CloseServiceHandle
0x18006f684  test    rbx, rbx
0x18006f687  jz      short loc_18006F692
0x18006f689  mov     rcx, rbx; hSCObject
0x18006f68c  call    cs:__imp_CloseServiceHandle
0x18006f692  mov     eax, r14d
0x18006f695  jmp     short loc_18006F6C1
0x18006f697  xor     eax, eax
0x18006f699  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x18006f69d  setz    al
0x18006f6a0  mov     [r15], eax
0x18006f6a3  test    rdi, rdi
0x18006f6a6  jz      short loc_18006F6B1
0x18006f6a8  mov     rcx, rdi; hSCObject
0x18006f6ab  call    cs:__imp_CloseServiceHandle
0x18006f6b1  test    rbx, rbx
0x18006f6b4  jz      short loc_18006F6BF
0x18006f6b6  mov     rcx, rbx; hSCObject
0x18006f6b9  call    cs:__imp_CloseServiceHandle
0x18006f6bf  xor     eax, eax
0x18006f6c1  mov     rcx, [rbp+var_18]
0x18006f6c5  xor     rcx, rsp; StackCookie
0x18006f6c8  call    __security_check_cookie
0x18006f6cd  add     rsp, 68h
0x18006f6d1  pop     r15
0x18006f6d3  pop     r14
0x18006f6d5  pop     rdi
0x18006f6d6  pop     rsi
0x18006f6d7  pop     rbx
0x18006f6d8  pop     rbp
0x18006f6d9  retn
```
