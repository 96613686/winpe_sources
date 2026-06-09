# ProviderManager::GetProviderById(ulong,IMessageProvider * *)

- ea: `0x180063800`
- end: `0x180063c2a`
- name: `?GetProviderById@ProviderManager@@UEAAJKPEAPEAVIMessageProvider@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(ProviderManager *__hidden this, unsigned int, struct IMessageProvider **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x18000163c`
- `0x180005c50`
- `0x1800065c8`
- `0x1800079fc`
- `0x18003140c`
- `0x1800595d4`
- `0x18005be44`
- `0x180063300`
- `0x1800634d4`
- `0x180063798`
- `0x180063800`
- `0x1800640cc`
- `0x180064dd8`
- `0x1800650ac`
- `0x1800b4c98`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063b9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063c22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063b9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063c22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006388b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006388b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063988`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063aa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063988`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063aa2`

## pseudocode

```c
__int64 __fastcall ProviderManager::GetProviderById(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        struct IMessageProvider **a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  int ProviderById; // eax
  ULONG_PTR SpinCount; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  HRESULT Instance; // eax
  HRESULT HasEmbeddedModem; // eax
  int v15; // ecx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  volatile signed __int32 *v17; // rcx
  int ppv; // [rsp+20h] [rbp-59h]
  unsigned int v20; // [rsp+30h] [rbp-49h] BYREF
  int v21; // [rsp+38h] [rbp-41h] BYREF
  utl::_RefCountBase *v22[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-29h] BYREF
  int v24; // [rsp+58h] [rbp-21h] BYREF
  struct IMessageProvider *v25; // [rsp+60h] [rbp-19h] BYREF
  struct IUnknown *v26; // [rsp+68h] [rbp-11h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, struct IUnknown **); // [rsp+70h] [rbp-9h] BYREF
  unsigned int v28; // [rsp+78h] [rbp-1h] BYREF
  utl::_RefCountBase *v29[2]; // [rsp+80h] [rbp+7h] BYREF
  GUID v30; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v20 = a2;
  if ( a3 )
  {
    v7 = ProviderManager::_WaitForProviderInfoReady((ProviderManager *)this, "ProviderManager::GetProviderById");
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\base\\appmodel\\messagingom\\providers\\providermanager.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      return v6;
    }
    v25 = 0;
    EnterCriticalSection(this + 3);
    ProviderById = ProviderManager::_FindProviderById((ProviderManager *)this, a2, &v25);
    v6 = ProviderById;
    if ( ProviderById != -2147023728 )
    {
      if ( ProviderById < 0 )
      {
        Log_HREvent_40(ProviderById);
        goto LABEL_50;
      }
      goto LABEL_42;
    }
    v27 = 0;
    v30 = GUID_NULL;
    if ( (unsigned int)IsPhysicalProviderId(a2) )
    {
      if ( (unsigned int)PlatformDetector::GetType() == 2 )
      {
        SpinCount = this[5].SpinCount;
        v26 = 0;
        if ( (*(int (__fastcall **)(ULONG_PTR, _QWORD, _QWORD))(*(_QWORD *)SpinCount + 104LL))(SpinCount, a2, &v27) >= 0 )
        {
          v10 = (**v27)(v27, &GUID_d7a6f024_fa8b_4e7f_8dd8_63026888c3e8, &v26);
          if ( v10 >= 0 )
          {
            ((void (__fastcall *)(struct IUnknown *, GUID *))v26->lpVtbl[3].QueryInterface)(v26, &v30);
          }
          else
          {
            if ( (unsigned int)dword_1800FD5F0 > 4 )
            {
              v24 = v10;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)dword_1800FD5F0,
                (int)byte_1800ECE91,
                v11,
                v12,
                (__int64)&v24);
            }
            if ( v26 )
              ATL::AtlComPtrAssign(&v26, 0);
          }
        }
        Instance = CoCreateInstance(
                     &stru_1800DBE70,
                     0,
                     0x17u,
                     &GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb,
                     (LPVOID *)&v25);
        v6 = Instance;
        if ( Instance < 0
          || (Instance = (*(__int64 (__fastcall **)(struct IMessageProvider *, _QWORD, ULONG_PTR, struct IUnknown *))(*(_QWORD *)v25 + 24LL))(
                           v25,
                           a2,
                           this[2].SpinCount,
                           v26),
              v6 = Instance,
              Instance < 0) )
        {
          Log_HREvent_40(Instance);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
LABEL_47:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
LABEL_50:
          LeaveCriticalSection(this + 3);
          goto LABEL_43;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
        goto LABEL_19;
      }
      v24 = 0;
      HasEmbeddedModem = ModemDetector::HasEmbeddedModem(&v24);
      v6 = HasEmbeddedModem;
      if ( HasEmbeddedModem < 0 )
        goto LABEL_22;
      if ( v24 )
      {
        HasEmbeddedModem = CoCreateInstance(
                             &stru_1800DBE60,
                             0,
                             0x17u,
                             &GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb,
                             (LPVOID *)&v25);
        v6 = HasEmbeddedModem;
        if ( HasEmbeddedModem >= 0 )
        {
          HasEmbeddedModem = (*(__int64 (__fastcall **)(struct IMessageProvider *, _QWORD, ULONG_PTR, _QWORD))(*(_QWORD *)v25 + 24LL))(
                               v25,
                               a2,
                               this[2].SpinCount,
                               0);
          v6 = HasEmbeddedModem;
          if ( HasEmbeddedModem >= 0 )
          {
LABEL_19:
            v21 = 1;
            v23 = (unsigned __int64)&v30 & -(__int64)(v27 != 0);
            *(_OWORD *)v22 = 0;
            utl::make_shared<ProviderManagerProviderInfo,ATL::CComPtr<IMessageProvider> &,unsigned long const &,int,ATL::CComPtr<IUnknown> &,_GUID *>(
              (__int64 *)v22,
              (int)&v25,
              &v20,
              &v21,
              (__int64 *)&v27,
              (__int64 *)&v23);
            if ( !v22[0] )
            {
              v6 = -2147024882;
              Log_HREvent_40(-2147024882);
LABEL_34:
              if ( v22[1] )
                utl::_RefCountBase::_DecStrong(v22[1]);
              goto LABEL_47;
            }
            v28 = v20;
            *(_OWORD *)v29 = 0;
            utl::shared_ptr<ProviderManagerProviderInfo>::operator=(v29, v22);
            DebugInfo = this[2].DebugInfo;
            if ( DebugInfo == *(PRTL_CRITICAL_SECTION_DEBUG *)&this[2].LockCount )
            {
              if ( !(unsigned __int8)utl::vector<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>>,utl::allocator<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>>>>::_PushBackOne2<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>> const &>(
                                       &this[1].SpinCount,
                                       &v28) )
              {
                v6 = -2147024882;
                Log_HREvent_40(-2147024882);
                if ( v29[1] )
                  utl::_RefCountBase::_DecStrong(v29[1]);
                goto LABEL_34;
              }
              v17 = (volatile signed __int32 *)v29[1];
            }
            else
            {
              v17 = (volatile signed __int32 *)v29[1];
              *(_DWORD *)&DebugInfo->Type = v28;
              DebugInfo->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v29[0];
              DebugInfo->ProcessLocksList.Flink = (struct _LIST_ENTRY *)v17;
              if ( v17 )
                _InterlockedIncrement(v17 + 2);
              this[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)this[2].DebugInfo + 24);
            }
            if ( v17 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v17);
            if ( v22[1] )
              utl::_RefCountBase::_DecStrong(v22[1]);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
LABEL_42:
            LeaveCriticalSection(this + 3);
            v6 = 0;
            *a3 = v25;
            v25 = 0;
LABEL_43:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
            return v6;
          }
        }
LABEL_22:
        v15 = HasEmbeddedModem;
LABEL_46:
        Log_HREvent_40(v15);
        goto LABEL_47;
      }
    }
    v6 = -2147024809;
    v15 = -2147024809;
    goto LABEL_46;
  }
  v6 = -2147024809;
  Log_HREvent_40(-2147024809);
  return v6;
}

```

## disassembly

```asm
0x180063800  mov     [rsp-8+arg_18], rbx
0x180063805  push    rbp
0x180063806  push    rsi
0x180063807  push    rdi
0x180063808  push    r14
0x18006380a  push    r15
0x18006380c  lea     rbp, [rsp-37h]
0x180063811  sub     rsp, 0B0h
0x180063818  mov     rax, cs:__security_cookie
0x18006381f  xor     rax, rsp
0x180063822  mov     [rbp+57h+var_30], rax
0x180063826  mov     [rbp+57h+var_A0], edx
0x180063829  mov     r15, r8
0x18006382c  mov     esi, edx
0x18006382e  mov     rdi, rcx
0x180063831  test    r8, r8
0x180063834  jnz     short loc_18006384D
0x180063836  mov     ebx, 80070057h
0x18006383b  lea     r9d, [r8+5Ch]
0x18006383f  mov     ecx, ebx; int
0x180063841  xor     edx, edx
0x180063843  call    Log_HREvent_40
0x180063848  jmp     loc_180063BBD
0x18006384d  lea     rdx, aProvidermanage_0; "ProviderManager::GetProviderById"
0x180063854  call    ?_WaitForProviderInfoReady@ProviderManager@@AEAAJPEAD@Z; ProviderManager::_WaitForProviderInfoReady(char *)
0x180063859  mov     ebx, eax
0x18006385b  test    eax, eax
0x18006385d  jns     short loc_18006387C
0x18006385f  mov     rcx, [rbp+5Fh]; this
0x180063863  lea     r8, aOnecoreuapBase_82; "onecoreuap\\base\\appmodel\\messagingom"...
0x18006386a  mov     r9d, eax; char *
0x18006386d  mov     edx, 5Eh ; '^'; void *
0x180063872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063877  jmp     loc_180063BBD
0x18006387c  lea     r14, [rdi+78h]
0x180063880  mov     [rbp+57h+var_70], 0
0x180063888  mov     rcx, r14; lpCriticalSection
0x18006388b  call    cs:__imp_EnterCriticalSection
0x180063891  lea     r8, [rbp+57h+var_70]; struct IMessageProvider **
0x180063895  mov     edx, esi; unsigned int
0x180063897  mov     rcx, rdi; this
0x18006389a  call    ?_FindProviderById@ProviderManager@@AEAAJKPEAPEAVIMessageProvider@@@Z; ProviderManager::_FindProviderById(ulong,IMessageProvider * *)
0x18006389f  mov     ebx, eax
0x1800638a1  cmp     eax, 80070490h
0x1800638a6  jnz     loc_180063C09
0x1800638ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800638b3  mov     ecx, esi; unsigned int
0x1800638b5  mov     [rbp+57h+var_60], 0
0x1800638bd  movdqu  [rbp+57h+var_40], xmm0
0x1800638c2  call    ?IsPhysicalProviderId@@YAHK@Z; IsPhysicalProviderId(ulong)
0x1800638c7  test    eax, eax
0x1800638c9  jz      loc_180063BEA
0x1800638cf  call    ?GetType@PlatformDetector@@SA?AW4PlatformType@@XZ; PlatformDetector::GetType(void)
0x1800638d4  cmp     eax, 2
0x1800638d7  jnz     loc_180063A53
0x1800638dd  mov     rcx, [rdi+0E8h]
0x1800638e4  lea     r8, [rbp+57h+var_60]
0x1800638e8  mov     [rbp+57h+var_68], 0
0x1800638f0  mov     edx, esi
0x1800638f2  mov     rax, [rcx]
0x1800638f5  mov     rax, [rax+68h]
0x1800638f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638fe  test    eax, eax
0x180063900  js      short loc_18006396B
0x180063902  mov     rcx, [rbp+57h+var_60]
0x180063906  lea     r8, [rbp+57h+var_68]
0x18006390a  lea     rdx, _GUID_d7a6f024_fa8b_4e7f_8dd8_63026888c3e8
0x180063911  mov     rax, [rcx]
0x180063914  mov     rax, [rax]
0x180063917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006391c  test    eax, eax
0x18006391e  jns     short loc_180063957
0x180063920  mov     ecx, cs:dword_1800FD5F0
0x180063926  cmp     ecx, 4
0x180063929  jbe     short loc_180063943
0x18006392b  mov     [rbp+57h+var_78], eax
0x18006392e  lea     rdx, byte_1800ECE91
0x180063935  lea     rax, [rbp+57h+var_78]
0x180063939  mov     [rsp+0D0h+ppv], rax
0x18006393e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063943  cmp     [rbp+57h+var_68], 0
0x180063948  jz      short loc_18006396B
0x18006394a  xor     edx, edx; struct IUnknown *
0x18006394c  lea     rcx, [rbp+57h+var_68]; struct IUnknown **
0x180063950  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180063955  jmp     short loc_18006396B
0x180063957  mov     rcx, [rbp+57h+var_68]
0x18006395b  lea     rdx, [rbp+57h+var_40]
0x18006395f  mov     rax, [rcx]
0x180063962  mov     rax, [rax+48h]
0x180063966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006396b  xor     edx, edx; pUnkOuter
0x18006396d  lea     rax, [rbp+57h+var_70]
0x180063971  lea     r9, _GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb; riid
0x180063978  mov     [rsp+0D0h+ppv], rax; ppv
0x18006397d  lea     rcx, stru_1800DBE70; rclsid
0x180063984  lea     r8d, [rdx+17h]; dwClsContext
0x180063988  call    cs:__imp_CoCreateInstance
0x18006398e  mov     ebx, eax
0x180063990  test    eax, eax
0x180063992  jns     short loc_18006399C
0x180063994  mov     r9d, 87h
0x18006399a  jmp     short loc_1800639C2
0x18006399c  mov     rcx, [rbp+57h+var_70]
0x1800639a0  mov     edx, esi
0x1800639a2  mov     r9, [rbp+57h+var_68]
0x1800639a6  mov     r8, [rdi+70h]
0x1800639aa  mov     rax, [rcx]
0x1800639ad  mov     rax, [rax+18h]
0x1800639b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639b6  mov     ebx, eax
0x1800639b8  test    eax, eax
0x1800639ba  jns     short loc_1800639DC
0x1800639bc  mov     r9d, 88h
0x1800639c2  mov     edx, 1
0x1800639c7  mov     ecx, eax; int
0x1800639c9  call    Log_HREvent_40
0x1800639ce  lea     rcx, [rbp+57h+var_68]
0x1800639d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800639d7  jmp     loc_180063BFE
0x1800639dc  lea     rcx, [rbp+57h+var_68]
0x1800639e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800639e5  mov     rax, [rbp+57h+var_60]
0x1800639e9  lea     r9, [rbp+57h+var_98]
0x1800639ed  neg     rax
0x1800639f0  mov     [rbp+57h+var_98], 1
0x1800639f7  lea     rax, [rbp+57h+var_40]
0x1800639fb  xorps   xmm0, xmm0
0x1800639fe  sbb     rcx, rcx
0x180063a01  lea     r8, [rbp+57h+var_A0]
0x180063a05  and     rcx, rax
0x180063a08  lea     rdx, [rbp+57h+var_70]
0x180063a0c  lea     rax, [rbp+57h+var_80]
0x180063a10  mov     [rbp+57h+var_80], rcx
0x180063a14  mov     [rsp+0D0h+var_A8], rax
0x180063a19  lea     rcx, [rbp+57h+var_90]
0x180063a1d  lea     rax, [rbp+57h+var_60]
0x180063a21  mov     [rsp+0D0h+ppv], rax
0x180063a26  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180063a2a  call    ??$make_shared@VProviderManagerProviderInfo@@AEAV?$CComPtr@VIMessageProvider@@@ATL@@AEBKHAEAV?$CComPtr@UIUnknown@@@3@PEAU_GUID@@@utl@@YA?AV?$shared_ptr@VProviderManagerProviderInfo@@@0@AEAV?$CComPtr@VIMessageProvider@@@ATL@@AEBK$$QEAHAEAV?$CComPtr@UIUnknown@@@3@$$QEAPEAU_GUID@@@Z; utl::make_shared<ProviderManagerProviderInfo,ATL::CComPtr<IMessageProvider> &,ulong const &,int,ATL::CComPtr<IUnknown> &,_GUID *>(ATL::CComPtr<IMessageProvider> &,ulong const &,int &&,ATL::CComPtr<IUnknown> &,_GUID * &&)
0x180063a2f  cmp     [rbp+57h+var_90], 0
0x180063a34  jnz     loc_180063AE1
0x180063a3a  mov     ebx, 8007000Eh
0x180063a3f  xor     edx, edx
0x180063a41  mov     ecx, ebx; int
0x180063a43  mov     r9d, 0A7h
0x180063a49  call    Log_HREvent_40
0x180063a4e  jmp     loc_180063B5E
0x180063a53  lea     rcx, [rbp+57h+var_78]; int *
0x180063a57  mov     [rbp+57h+var_78], 0
0x180063a5e  call    ?HasEmbeddedModem@ModemDetector@@SAJPEAH@Z; ModemDetector::HasEmbeddedModem(int *)
0x180063a63  mov     ebx, eax
0x180063a65  test    eax, eax
0x180063a67  jns     short loc_180063A7B
0x180063a69  mov     r9d, 8Dh
0x180063a6f  mov     edx, 1
0x180063a74  mov     ecx, eax
0x180063a76  jmp     loc_180063BF9
0x180063a7b  cmp     [rbp+57h+var_78], 0
0x180063a7f  jz      loc_180063BE2
0x180063a85  xor     edx, edx; pUnkOuter
0x180063a87  lea     rax, [rbp+57h+var_70]
0x180063a8b  lea     r9, _GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb; riid
0x180063a92  mov     [rsp+0D0h+ppv], rax; ppv
0x180063a97  lea     rcx, stru_1800DBE60; rclsid
0x180063a9e  lea     r8d, [rdx+17h]; dwClsContext
0x180063aa2  call    cs:__imp_CoCreateInstance
0x180063aa8  mov     ebx, eax
0x180063aaa  test    eax, eax
0x180063aac  jns     short loc_180063AB6
0x180063aae  mov     r9d, 91h
0x180063ab4  jmp     short loc_180063A6F
0x180063ab6  mov     rcx, [rbp+57h+var_70]
0x180063aba  xor     r9d, r9d
0x180063abd  mov     r8, [rdi+70h]
0x180063ac1  mov     edx, esi
0x180063ac3  mov     rax, [rcx]
0x180063ac6  mov     rax, [rax+18h]
0x180063aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063acf  mov     ebx, eax
0x180063ad1  test    eax, eax
0x180063ad3  jns     loc_1800639E5
0x180063ad9  mov     r9d, 92h
0x180063adf  jmp     short loc_180063A6F
0x180063ae1  mov     eax, [rbp+57h+var_A0]
0x180063ae4  lea     rdx, [rbp+57h+var_90]
0x180063ae8  xorps   xmm0, xmm0
0x180063aeb  mov     [rbp+57h+var_58], eax
0x180063aee  lea     rcx, [rbp+57h+var_50]
0x180063af2  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x180063af7  call    ??4?$shared_ptr@VProviderManagerProviderInfo@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<ProviderManagerProviderInfo>::operator=(utl::shared_ptr<ProviderManagerProviderInfo> const &)
0x180063afc  mov     rdx, [rdi+50h]
0x180063b00  cmp     rdx, [rdi+58h]
0x180063b04  jz      short loc_180063B2B
0x180063b06  mov     eax, [rbp+57h+var_58]
0x180063b09  mov     rcx, [rbp+57h+var_50+8]
0x180063b0d  mov     [rdx], eax
0x180063b0f  mov     rax, [rbp+57h+var_50]
0x180063b13  mov     [rdx+8], rax
0x180063b17  mov     [rdx+10h], rcx
0x180063b1b  test    rcx, rcx
0x180063b1e  jz      short loc_180063B24
0x180063b20  lock inc dword ptr [rcx+8]
0x180063b24  add     qword ptr [rdi+50h], 18h
0x180063b29  jmp     short loc_180063B79
0x180063b2b  lea     rdx, [rbp+57h+var_58]
0x180063b2f  lea     rcx, [rdi+48h]
0x180063b33  call    ??$_PushBackOne2@AEBU?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@@?$vector@U?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@V?$allocator@U?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@@2@@utl@@AEAA_NAEBU?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@1@@Z; utl::vector<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>>,utl::allocator<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>>>>::_PushBackOne2<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>> const &>(utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>> const &)
0x180063b38  test    al, al
0x180063b3a  jnz     short loc_180063B75
0x180063b3c  mov     ebx, 8007000Eh
0x180063b41  xor     edx, edx
0x180063b43  mov     ecx, ebx; int
0x180063b45  mov     r9d, 0ADh
0x180063b4b  call    Log_HREvent_40
0x180063b50  mov     rcx, [rbp+57h+var_50+8]; this
0x180063b54  test    rcx, rcx
0x180063b57  jz      short loc_180063B5E
0x180063b59  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180063b5e  mov     rcx, [rbp+57h+var_90+8]; this
0x180063b62  test    rcx, rcx
0x180063b65  jz      loc_180063BFE
0x180063b6b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180063b70  jmp     loc_180063BFE
0x180063b75  mov     rcx, [rbp+57h+var_50+8]; this
0x180063b79  test    rcx, rcx
0x180063b7c  jz      short loc_180063B83
0x180063b7e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180063b83  mov     rcx, [rbp+57h+var_90+8]; this
0x180063b87  test    rcx, rcx
0x180063b8a  jz      short loc_180063B91
0x180063b8c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180063b91  lea     rcx, [rbp+57h+var_60]
0x180063b95  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180063b9a  mov     rcx, r14; lpCriticalSection
0x180063b9d  call    cs:__imp_LeaveCriticalSection
0x180063ba3  mov     rax, [rbp+57h+var_70]
0x180063ba7  xor     ebx, ebx
0x180063ba9  mov     [r15], rax
0x180063bac  mov     [rbp+57h+var_70], 0
0x180063bb4  lea     rcx, [rbp+57h+var_70]
0x180063bb8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180063bbd  mov     eax, ebx
0x180063bbf  mov     rcx, [rbp+57h+var_30]
0x180063bc3  xor     rcx, rsp; StackCookie
0x180063bc6  call    __security_check_cookie
0x180063bcb  mov     rbx, [rsp+0D0h+arg_18]
0x180063bd3  add     rsp, 0B0h
0x180063bda  pop     r15
0x180063bdc  pop     r14
0x180063bde  pop     rdi
0x180063bdf  pop     rsi
0x180063be0  pop     rbp
0x180063be1  retn
0x180063be2  mov     r9d, 96h
0x180063be8  jmp     short loc_180063BF0
0x180063bea  mov     r9d, 9Ch
0x180063bf0  mov     ebx, 80070057h
0x180063bf5  xor     edx, edx
0x180063bf7  mov     ecx, ebx; int
0x180063bf9  call    Log_HREvent_40
0x180063bfe  lea     rcx, [rbp+57h+var_60]
0x180063c02  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180063c07  jmp     short loc_180063C1F
0x180063c09  test    eax, eax
0x180063c0b  jns     short loc_180063B9A
0x180063c0d  mov     edx, 1
0x180063c12  mov     r9d, 0B2h
0x180063c18  mov     ecx, eax; int
0x180063c1a  call    Log_HREvent_40
0x180063c1f  mov     rcx, r14; lpCriticalSection
0x180063c22  call    cs:__imp_LeaveCriticalSection
0x180063c28  jmp     short loc_180063BB4
```
