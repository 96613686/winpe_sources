# CSurrogate::LoadDllServer(_GUID const &)

- ea: `0x1400043d0`
- end: `0x140004772`
- name: `?LoadDllServer@CSurrogate@@UEAAJAEBU_GUID@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(CSurrogate *this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001a40`
- `0x140001aa8`
- `0x140003040`
- `0x140003a80`
- `0x140003ed8`
- `0x1400043d0`
- `0x140004880`
- `0x140011010`

## import_xrefs

- `ole32!CoRegisterClassObject` at `0x140004508`
- `ole32!CoRegisterClassObject` at `0x140004508`
- `ole32!CoRevokeClassObject` at `0x1400045ae`
- `ole32!CoRevokeClassObject` at `0x1400045ae`
- `KERNEL32!LeaveCriticalSection` at `0x1400045f9`
- `KERNEL32!LeaveCriticalSection` at `0x140004607`
- `KERNEL32!LeaveCriticalSection` at `0x1400045f9`
- `KERNEL32!LeaveCriticalSection` at `0x140004607`
- `KERNEL32!EnterCriticalSection` at `0x14000458a`
- `KERNEL32!EnterCriticalSection` at `0x14000458a`

## pseudocode

```c
__int64 __fastcall CSurrogate::LoadDllServer(CSurrogate *this, const struct _GUID *a2)
{
  char v4; // al
  __int64 v5; // r8
  GUID *v6; // rdx
  __int64 v7; // rcx
  int Instance; // edi
  HRESULT v10; // ebx
  LPUNKNOWN v11; // rax
  __int128 v12; // [rsp+30h] [rbp-30h] BYREF
  char *v13; // [rsp+40h] [rbp-20h]
  char v14; // [rsp+48h] [rbp-18h]
  char v15; // [rsp+50h] [rbp-10h]
  DWORD dwRegister; // [rsp+90h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+98h] [rbp+38h] BYREF

  if ( __TSS0__1__IsClsidInAllowList_CSurrogate__AEAA_NAEBU_GUID___Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsClsidInAllowList_CSurrogate__AEAA_NAEBU_GUID___Z_4HA);
    if ( __TSS0__1__IsClsidInAllowList_CSurrogate__AEAA_NAEBU_GUID___Z_4HA == -1 )
    {
      `CSurrogate::IsClsidInAllowList'::`2'::rgrclsidAllowedList = GUID_06622d85_6856_4460_8de1_a81921b41c4b;
      xmmword_140018EC0 = (__int128)CLSID_ShieldProviderUserSessionAgent;
      xmmword_140018ED0 = (__int128)CLSID_ShieldElevationBroker;
      xmmword_140018EE0 = (__int128)CLSID_DefenderShieldBroker;
      xmmword_140018EF0 = (__int128)CLSID_DefenderPuaShieldBroker;
      xmmword_140018F00 = (__int128)CLSID_NetworkProtectionShieldBroker;
      xmmword_140018F10 = (__int128)CLSID_ShieldProcessLauncherBroker;
      xmmword_140018F20 = (__int128)CLSID_AppAndBrowserShieldBroker;
      xmmword_140018F30 = (__int128)CLSID_DashboardBroker;
      xmmword_140018F40 = (__int128)CLSID_ExploitShieldBroker;
      xmmword_140018F50 = (__int128)CLSID_AccountProtectionShieldBroker;
      xmmword_140018F60 = (__int128)CLSID_HardwareShieldBroker;
      xmmword_140018F70 = (__int128)CLSID_OSProtectionShieldBroker;
      xmmword_140018F80 = (__int128)CLSID_DataProtectionShieldBroker;
      xmmword_140018F90 = (__int128)CLSID_ForceFieldWebProtectionShieldBroker;
      xmmword_140018FA0 = (__int128)CLSID_ApplicationGuardShieldBroker;
      xmmword_140018FB0 = (__int128)CLSID_ManagementShieldBroker;
      xmmword_140018FC0 = (__int128)CLSID_HealthAdvisorShieldBroker;
      Init_thread_footer(&__TSS0__1__IsClsidInAllowList_CSurrogate__AEAA_NAEBU_GUID___Z_4HA);
    }
  }
  v4 = 0;
  LODWORD(v5) = 0;
  while ( !v4 )
  {
    v6 = &`CSurrogate::IsClsidInAllowList'::`2'::rgrclsidAllowedList + (unsigned int)v5;
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&v6->Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&v6->Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)v6->Data4;
    if ( !v7 )
      v4 = 1;
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= 0x12 )
    {
      if ( !v4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v5, a2);
        return 2147942405LL;
      }
      break;
    }
  }
  pUnk = 0;
  Instance = CClassFactory_CreateInstance(a2, (struct IClassFactory **)&pUnk);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_1b9472ab152333716498c740fcb4c194_Traceguids,
        (unsigned int)Instance);
LABEL_18:
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return (unsigned int)Instance;
  }
  dwRegister = 0;
  v10 = CoRegisterClassObject(a2, pUnk, 4u, 8u, &dwRegister);
  if ( v10 >= 0 )
  {
    v11 = pUnk;
    pUnk = 0;
    *((_QWORD *)&v12 + 1) = v11;
    *(_QWORD *)&v12 = dwRegister;
    v13 = (char *)this + 16;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v14 = 1;
    v15 = 1;
    Instance = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>>,ClassFactoryRecord>(
                 (__int64)this + 56,
                 &v12);
    if ( Instance < 0 )
    {
      CoRevokeClassObject(v12);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v12 + 1) + 16LL))(*((_QWORD *)&v12 + 1));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_1b9472ab152333716498c740fcb4c194_Traceguids,
          (unsigned int)Instance);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_18;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_1b9472ab152333716498c740fcb4c194_Traceguids,
        (unsigned int)v10);
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x1400043d0  mov     [rsp-18h+arg_0], rbx
0x1400043d5  mov     [rsp-18h+arg_8], rsi
0x1400043da  push    rbp
0x1400043db  push    rdi
0x1400043dc  push    r15
0x1400043de  mov     rbp, rsp
0x1400043e1  sub     rsp, 60h
0x1400043e5  mov     rbx, rdx
0x1400043e8  mov     rsi, rcx
0x1400043eb  mov     ecx, 4
0x1400043f0  mov     rax, gs:58h
0x1400043f9  mov     rax, [rax]
0x1400043fc  mov     eax, [rcx+rax]
0x1400043ff  cmp     cs:?$TSS0@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4HA, eax
0x140004405  jg      loc_14000463A
0x14000440b  xor     al, al
0x14000440d  xor     r8d, r8d
0x140004410  lea     r15d, [r8+1]
0x140004414  test    al, al
0x140004416  jnz     short loc_14000447F
0x140004418  mov     edx, r8d
0x14000441b  shl     rdx, 4
0x14000441f  lea     rcx, ?rgrclsidAllowedList@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4QBU3@B; _GUID const near * const `CSurrogate::IsClsidInAllowList(_GUID const &)'::`2'::rgrclsidAllowedList
0x140004426  add     rdx, rcx
0x140004429  mov     rcx, [rbx]
0x14000442c  sub     rcx, [rdx]
0x14000442f  jnz     short loc_140004439
0x140004431  mov     rcx, [rbx+8]
0x140004435  sub     rcx, [rdx+8]
0x140004439  movzx   eax, al
0x14000443c  test    rcx, rcx
0x14000443f  cmovz   eax, r15d
0x140004443  add     r8d, r15d
0x140004446  cmp     r8d, 12h
0x14000444a  jb      short loc_140004414
0x14000444c  test    al, al
0x14000444e  jnz     short loc_14000447F
0x140004450  lea     rax, WPP_GLOBAL_Control
0x140004457  mov     rcx, cs:WPP_GLOBAL_Control
0x14000445e  cmp     rcx, rax
0x140004461  jz      short loc_140004475
0x140004463  test    [rcx+1Ch], r15b
0x140004467  jz      short loc_140004475
0x140004469  mov     r9, rbx
0x14000446c  mov     rcx, [rcx+10h]
0x140004470  call    WPP_SF__guid_
0x140004475  mov     eax, 80070005h
0x14000447a  jmp     loc_140004625
0x14000447f  mov     [rbp+pUnk], 0
0x140004487  lea     rdx, [rbp+pUnk]; struct IClassFactory **
0x14000448b  mov     rcx, rbx; struct _GUID *
0x14000448e  call    ?CClassFactory_CreateInstance@@YAJAEBU_GUID@@PEAPEAUIClassFactory@@@Z; CClassFactory_CreateInstance(_GUID const &,IClassFactory * *)
0x140004493  mov     edi, eax
0x140004495  test    eax, eax
0x140004497  jns     short loc_1400044E7
0x140004499  lea     rax, WPP_GLOBAL_Control
0x1400044a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044a7  cmp     rcx, rax
0x1400044aa  jz      short loc_1400044CB
0x1400044ac  test    [rcx+1Ch], r15b
0x1400044b0  jz      short loc_1400044CB
0x1400044b2  mov     edx, 0Ch
0x1400044b7  mov     r9d, edi
0x1400044ba  lea     r8, WPP_1b9472ab152333716498c740fcb4c194_Traceguids
0x1400044c1  mov     rcx, [rcx+10h]
0x1400044c5  call    WPP_SF_d
0x1400044ca  nop
0x1400044cb  mov     rcx, [rbp+pUnk]
0x1400044cf  test    rcx, rcx
0x1400044d2  jz      short loc_1400044E0
0x1400044d4  mov     rax, [rcx]
0x1400044d7  mov     rax, [rax+10h]
0x1400044db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044e0  mov     eax, edi
0x1400044e2  jmp     loc_140004625
0x1400044e7  mov     [rbp+dwRegister], 0
0x1400044ee  lea     rax, [rbp+dwRegister]
0x1400044f2  mov     [rsp+60h+lpdwRegister], rax; lpdwRegister
0x1400044f7  mov     r9d, 8; flags
0x1400044fd  lea     r8d, [r9-4]; dwClsContext
0x140004501  mov     rdx, [rbp+pUnk]; pUnk
0x140004505  mov     rcx, rbx; rclsid
0x140004508  call    cs:__imp_CoRegisterClassObject
0x14000450e  mov     ebx, eax
0x140004510  test    eax, eax
0x140004512  jns     short loc_140004562
0x140004514  lea     rax, WPP_GLOBAL_Control
0x14000451b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004522  cmp     rcx, rax
0x140004525  jz      short loc_140004546
0x140004527  test    [rcx+1Ch], r15b
0x14000452b  jz      short loc_140004546
0x14000452d  mov     edx, 0Dh
0x140004532  mov     r9d, ebx
0x140004535  lea     r8, WPP_1b9472ab152333716498c740fcb4c194_Traceguids
0x14000453c  mov     rcx, [rcx+10h]
0x140004540  call    WPP_SF_d
0x140004545  nop
0x140004546  mov     rcx, [rbp+pUnk]
0x14000454a  test    rcx, rcx
0x14000454d  jz      short loc_14000455B
0x14000454f  mov     rax, [rcx]
0x140004552  mov     rax, [rax+10h]
0x140004556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000455b  mov     eax, ebx
0x14000455d  jmp     loc_140004625
0x140004562  mov     [rbp+var_2C], 0
0x140004569  mov     rax, [rbp+pUnk]
0x14000456d  mov     [rbp+pUnk], 0
0x140004575  mov     [rbp+var_28], rax
0x140004579  mov     eax, [rbp+dwRegister]
0x14000457c  mov     [rbp+var_30], eax
0x14000457f  lea     rbx, [rsi+10h]
0x140004583  mov     [rbp+var_20], rbx
0x140004587  mov     rcx, rbx; lpCriticalSection
0x14000458a  call    cs:__imp_EnterCriticalSection
0x140004590  mov     [rbp+var_18], r15b
0x140004594  mov     [rbp+var_10], r15b
0x140004598  lea     rcx, [rsi+38h]
0x14000459c  lea     rdx, [rbp+var_30]
0x1400045a0  call    ??$HrStdPushBack@V?$CStdVector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@CommonUtil@@UClassFactoryRecord@@@CommonUtil@@YAJAEAV?$CStdVector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@0@AEBUClassFactoryRecord@@@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>>,ClassFactoryRecord>(CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>> &,ClassFactoryRecord const &)
0x1400045a5  mov     edi, eax
0x1400045a7  test    eax, eax
0x1400045a9  jns     short loc_140004604
0x1400045ab  mov     ecx, [rbp+var_30]; dwRegister
0x1400045ae  call    cs:__imp_CoRevokeClassObject
0x1400045b4  mov     rcx, [rbp+var_28]
0x1400045b8  mov     rdx, [rcx]
0x1400045bb  mov     rax, [rdx+10h]
0x1400045bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045c4  lea     rax, WPP_GLOBAL_Control
0x1400045cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045d2  cmp     rcx, rax
0x1400045d5  jz      short loc_1400045F6
0x1400045d7  test    [rcx+1Ch], r15b
0x1400045db  jz      short loc_1400045F6
0x1400045dd  mov     edx, 0Eh
0x1400045e2  mov     r9d, edi
0x1400045e5  lea     r8, WPP_1b9472ab152333716498c740fcb4c194_Traceguids
0x1400045ec  mov     rcx, [rcx+10h]
0x1400045f0  call    WPP_SF_d
0x1400045f5  nop
0x1400045f6  mov     rcx, rbx; lpCriticalSection
0x1400045f9  call    cs:__imp_LeaveCriticalSection
0x1400045ff  jmp     loc_1400044CB
0x140004604  mov     rcx, rbx; lpCriticalSection
0x140004607  call    cs:__imp_LeaveCriticalSection
0x14000460d  nop
0x14000460e  mov     rcx, [rbp+pUnk]
0x140004612  test    rcx, rcx
0x140004615  jz      short loc_140004623
0x140004617  mov     rax, [rcx]
0x14000461a  mov     rax, [rax+10h]
0x14000461e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004623  xor     eax, eax
0x140004625  lea     r11, [rsp+60h+var_s0]
0x14000462a  mov     rbx, [r11+20h]
0x14000462e  mov     rsi, [r11+28h]
0x140004632  mov     rsp, r11
0x140004635  pop     r15
0x140004637  pop     rdi
0x140004638  pop     rbp
0x140004639  retn
0x14000463a  lea     rcx, ?$TSS0@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4HA
0x140004641  call    _Init_thread_header
0x140004646  cmp     cs:?$TSS0@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4HA, 0FFFFFFFFh
0x14000464d  jnz     loc_14000440B
0x140004653  movups  xmm0, xmmword ptr cs:_GUID_06622d85_6856_4460_8de1_a81921b41c4b.Data1
0x14000465a  movdqu  xmmword ptr cs:?rgrclsidAllowedList@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4QBU3@B.Data1, xmm0; _GUID const near * const `CSurrogate::IsClsidInAllowList(_GUID const &)'::`2'::rgrclsidAllowedList ...
0x140004662  movups  xmm1, xmmword ptr cs:CLSID_ShieldProviderUserSessionAgent.Data1
0x140004669  movdqu  cs:xmmword_140018EC0, xmm1
0x140004671  movups  xmm0, xmmword ptr cs:CLSID_ShieldElevationBroker.Data1
0x140004678  movdqu  cs:xmmword_140018ED0, xmm0
0x140004680  movups  xmm1, xmmword ptr cs:CLSID_DefenderShieldBroker.Data1
0x140004687  movdqu  cs:xmmword_140018EE0, xmm1
0x14000468f  movups  xmm0, xmmword ptr cs:CLSID_DefenderPuaShieldBroker.Data1
0x140004696  movdqu  cs:xmmword_140018EF0, xmm0
0x14000469e  movups  xmm1, xmmword ptr cs:CLSID_NetworkProtectionShieldBroker.Data1
0x1400046a5  movdqu  cs:xmmword_140018F00, xmm1
0x1400046ad  movups  xmm0, xmmword ptr cs:CLSID_ShieldProcessLauncherBroker.Data1
0x1400046b4  movdqu  cs:xmmword_140018F10, xmm0
0x1400046bc  movups  xmm1, xmmword ptr cs:CLSID_AppAndBrowserShieldBroker.Data1
0x1400046c3  movdqu  cs:xmmword_140018F20, xmm1
0x1400046cb  movups  xmm0, xmmword ptr cs:CLSID_DashboardBroker.Data1
0x1400046d2  movdqu  cs:xmmword_140018F30, xmm0
0x1400046da  movups  xmm1, xmmword ptr cs:CLSID_ExploitShieldBroker.Data1
0x1400046e1  movdqu  cs:xmmword_140018F40, xmm1
0x1400046e9  movups  xmm0, xmmword ptr cs:CLSID_AccountProtectionShieldBroker.Data1
0x1400046f0  movdqu  cs:xmmword_140018F50, xmm0
0x1400046f8  movups  xmm1, xmmword ptr cs:CLSID_HardwareShieldBroker.Data1
0x1400046ff  movdqu  cs:xmmword_140018F60, xmm1
0x140004707  movups  xmm0, xmmword ptr cs:CLSID_OSProtectionShieldBroker.Data1
0x14000470e  movdqu  cs:xmmword_140018F70, xmm0
0x140004716  movups  xmm1, xmmword ptr cs:CLSID_DataProtectionShieldBroker.Data1
0x14000471d  movdqu  cs:xmmword_140018F80, xmm1
0x140004725  movups  xmm0, xmmword ptr cs:CLSID_ForceFieldWebProtectionShieldBroker.Data1
0x14000472c  movdqu  cs:xmmword_140018F90, xmm0
0x140004734  movups  xmm1, xmmword ptr cs:CLSID_ApplicationGuardShieldBroker.Data1
0x14000473b  movdqu  cs:xmmword_140018FA0, xmm1
0x140004743  movups  xmm0, xmmword ptr cs:CLSID_ManagementShieldBroker.Data1
0x14000474a  movdqu  cs:xmmword_140018FB0, xmm0
0x140004752  movups  xmm1, xmmword ptr cs:CLSID_HealthAdvisorShieldBroker.Data1
0x140004759  movdqu  cs:xmmword_140018FC0, xmm1
0x140004761  lea     rcx, ?$TSS0@?1??IsClsidInAllowList@CSurrogate@@AEAA_NAEBU_GUID@@@Z@4HA
0x140004768  call    _Init_thread_footer
0x14000476d  jmp     loc_14000440B
```
