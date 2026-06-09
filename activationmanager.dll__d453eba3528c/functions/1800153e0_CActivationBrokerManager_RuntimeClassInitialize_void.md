# CActivationBrokerManager::RuntimeClassInitialize(void)

- ea: `0x1800153e0`
- end: `0x180015a82`
- name: `?RuntimeClassInitialize@CActivationBrokerManager@@QEAAJXZ`
- size: `1698`
- prototype: `__int64 __fastcall(CActivationBrokerManager *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014548`

## callees

- `0x180009d60`
- `0x180011328`
- `0x180014f20`
- `0x1800153e0`
- `0x180015a88`
- `0x180015b7c`
- `0x180015ba0`
- `0x180015c7c`
- `0x180015d2c`
- `0x180015d9c`
- `0x1800165a0`
- `0x18001672c`
- `0x18001baa4`
- `0x18001e3c4`
- `0x18001e5ac`
- `0x180036148`
- `0x18003b9a4`
- `0x18003cee8`
- `0x18004b350`
- `0x18004be80`
- `0x18004bedc`
- `0x18004c6c8`
- `0x1800507c0`
- `0x180050ef0`
- `0x18005ae90`
- `0x18005b37c`
- `0x180067e64`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015450`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800154a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800154d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015450`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800154a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800154d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547a`

## string_xrefs

- `0x180015983`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180015410`: `SiHostComponentCreation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CActivationBrokerManager::RuntimeClassInitialize(RTL_SRWLOCK *this)
{
  _DWORD *v2; // rbx
  __int64 v3; // rdi
  HANDLE EventW; // rsi
  RTL_SRWLOCK *v5; // r14
  signed int LastError; // eax
  CActivationBrokerManager *v7; // rcx
  signed int v8; // esi
  HANDLE Ptr; // rsi
  RTL_SRWLOCK *v10; // r14
  HANDLE v11; // rsi
  RTL_SRWLOCK *v12; // r14
  __int64 *v13; // rax
  __int64 v14; // r12
  _OWORD *v15; // rbx
  char *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  _DWORD *v19; // r14
  RTL_SRWLOCK *v20; // r15
  char *v21; // rdx
  PVOID v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rsi
  _OWORD *v26; // rbx
  char *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  _DWORD *v30; // r12
  _DWORD *v31; // r14
  char *v32; // rdx
  PVOID v33; // rcx
  __int64 *v34; // rax
  _OWORD *v35; // rsi
  char *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  _DWORD *v39; // r14
  char *v40; // rdx
  PVOID v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  int v45; // eax
  char *v46; // rax
  __int64 v47; // rax
  _QWORD v49[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v50[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v51[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v51,
    "SiHostComponentCreation");
  v51[0] = &AAMTraceProvider::SiHostComponentCreation::`vftable';
  AAMTraceProvider::SiHostComponentCreation::StartActivity((AAMTraceProvider::SiHostComponentCreation *)v51);
  v2 = 0;
  v3 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = this + 31;
  if ( EventW == this[31].Ptr )
  {
    EventW = v5->Ptr;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&this[31]);
    v5->Ptr = EventW;
  }
  if ( !EventW )
    goto LABEL_5;
  Ptr = CreateEventW(0, 1, 0, 0);
  v10 = this + 32;
  if ( Ptr == this[32].Ptr )
  {
    Ptr = v10->Ptr;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&this[32]);
    v10->Ptr = Ptr;
  }
  if ( Ptr
    && ((v11 = CreateEventW(0, 1, 0, 0), v12 = this + 33, v11 == this[33].Ptr)
      ? (v11 = v12->Ptr)
      : (tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&this[33]), v12->Ptr = v11),
        v11) )
  {
    v13 = (__int64 *)Microsoft::WRL::Details::Make<CLaunchActivationPlugin,>(v49);
    v14 = *v13;
    *v13 = 0;
    v3 = v14;
    v7 = (CActivationBrokerManager *)v49[0];
    if ( v49[0] )
    {
      v49[0] = 0;
      (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( !v14 )
      goto LABEL_18;
    v15 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v14 + 24LL))(v14, v50);
    v16 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v16;
    if ( v16 )
    {
      *(_OWORD *)(v16 + 8) = *v15;
      *(GUID *)(v16 + 24) = GUID_NULL;
      *((_QWORD *)v16 + 5) = v14;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v16 + 40, v17, v18);
      *(_QWORD *)v19 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
      v19[12] = 0;
    }
    else
    {
      v19 = 0;
    }
    if ( v19 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 8LL))(v19);
    v2 = v19;
    if ( !v19 )
      goto LABEL_18;
    v20 = this + 22;
    v49[0] = v19;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 8LL))(v19);
    v8 = 0;
    v21 = (char *)this[23].Ptr;
    if ( v21 != this[25].Ptr
      || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                 &this[22],
                 v21 + 1),
          v8 >= 0) )
    {
      v22 = this[23].Ptr;
      this[23].Ptr = (char *)v22 + 1;
      v23 = (__int64)v20->Ptr + 8 * (_QWORD)v22;
      if ( v23 )
        Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
          v23,
          v49);
    }
    v7 = (CActivationBrokerManager *)v49[0];
    if ( v49[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49[0] + 16LL))(v49[0]);
    if ( v8 >= 0 )
    {
      v24 = (_QWORD *)Microsoft::WRL::Details::Make<CLaunchWithTileActivationPlugin,>(v49);
      v50[0] = *v24;
      v25 = v50[0];
      *v24 = 0;
      v3 = v25;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v7 = (CActivationBrokerManager *)v49[0];
      if ( v49[0] )
      {
        v49[0] = 0;
        (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      if ( !v25 )
        goto LABEL_18;
      v26 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v25 + 24LL))(v25, v49);
      v27 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v30 = v27;
      if ( v27 )
      {
        *(_OWORD *)(v27 + 8) = *v26;
        *(GUID *)(v27 + 24) = GUID_NULL;
        *((_QWORD *)v27 + 5) = v25;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v27 + 40, v28, v29);
        *(_QWORD *)v30 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
        v30[12] = 0;
      }
      else
      {
        v30 = 0;
      }
      if ( v30 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v30 + 8LL))(v30);
      v2 = v30;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( !v30 )
        goto LABEL_18;
      v31 = v30;
      v49[0] = v30;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v30 + 8LL))(v30);
      v8 = 0;
      v32 = (char *)this[23].Ptr;
      if ( v32 != this[25].Ptr
        || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                   &this[22],
                   v32 + 1),
            v8 >= 0) )
      {
        v33 = this[23].Ptr;
        this[23].Ptr = (char *)v33 + 1;
        v7 = (CActivationBrokerManager *)((char *)v20->Ptr + 8 * (_QWORD)v33);
        if ( v7 )
        {
          Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
            v7,
            v49);
          v31 = (_DWORD *)v49[0];
        }
      }
      if ( v31 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v8 >= 0 )
      {
        v34 = (__int64 *)Microsoft::WRL::Details::Make<CLaunchChildActivationPlugin,>(v49);
        v3 = *v34;
        *v34 = 0;
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50[0] + 16LL))(v50[0]);
        v7 = (CActivationBrokerManager *)v49[0];
        if ( v49[0] )
        {
          v49[0] = 0;
          (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
        }
        if ( v3 )
        {
          v35 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 24LL))(v3, v50);
          v36 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
          v2 = v36;
          if ( v36 )
          {
            *(_OWORD *)(v36 + 8) = *v35;
            *(GUID *)(v36 + 24) = GUID_NULL;
            *((_QWORD *)v36 + 5) = v3;
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v36 + 40, v37, v38);
            *(_QWORD *)v2 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
            v2[12] = 0;
          }
          else
          {
            v2 = 0;
          }
          if ( v2 )
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v2 )
          {
            v39 = v2;
            v49[0] = v2;
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
            v8 = 0;
            v40 = (char *)this[23].Ptr;
            if ( v40 != this[25].Ptr
              || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                         &this[22],
                         v40 + 1),
                  v8 >= 0) )
            {
              v41 = this[23].Ptr;
              this[23].Ptr = (char *)v41 + 1;
              v7 = (CActivationBrokerManager *)((char *)v20->Ptr + 8 * (_QWORD)v41);
              if ( v7 )
              {
                Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
                  v7,
                  v49);
                v39 = (_DWORD *)v49[0];
              }
            }
            if ( v39 )
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v39 + 16LL))(v39);
            if ( v8 >= 0 )
            {
              CActivationBrokerManager::_AddAndRegisterActivationPlugins(this);
              if ( byte_1800D1F02 < 0 )
                McTemplateU0qq_EventWriteTransfer(
                  v43,
                  ActivationBroker_PluginsCreated,
                  LODWORD(this[23].Ptr),
                  LODWORD(this[23].Ptr));
              ReadKeyHKLMDword(v43, v42, v44, &this[41]);
              v8 = ActivationManagerShimFactory_Initialize();
              if ( v8 >= 0 )
              {
                v45 = CActivationBrokerManager::_EnsureMutablePackagesOnline(v7);
                if ( v45 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x117,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
                    (const char *)(unsigned int)v45,
                    (int)v2);
                v8 = CServiceHostComponent::RegisterServiceInformation(
                       (CServiceHostComponent *)&this[9],
                       &IID_ActivationBrokerManager);
                if ( v8 >= 0 )
                {
                  v46 = this ? (char *)&this[17] : 0LL;
                  v50[0] = v46;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&this[40]);
                  v8 = Microsoft::WRL::Details::MakeAndInitialize<CApplicationActivationBroker,CApplicationActivationBroker,IActivationBrokerManager *>(
                         &this[40],
                         v50);
                  if ( v8 >= 0 )
                  {
                    v47 = Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create();
                    v8 = Microsoft::WRL::Details::RegisterObjects<2>(v47);
                  }
                }
              }
            }
            goto LABEL_75;
          }
        }
LABEL_18:
        v8 = -2147467259;
      }
    }
  }
  else
  {
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_75:
  if ( byte_1800D1F02 < 0 )
    McTemplateU0q_EventWriteTransfer(v7, ActivationBroker_Initialize, (unsigned int)v8);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v2 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 16LL))(v2);
  v51[0] = &AAMTraceProvider::SiHostComponentCreation::`vftable';
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v51);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800153e0  push    rbp
0x1800153e2  push    rbx
0x1800153e3  push    rsi
0x1800153e4  push    rdi
0x1800153e5  push    r12
0x1800153e7  push    r13
0x1800153e9  push    r14
0x1800153eb  push    r15
0x1800153ed  lea     rbp, [rsp-0B8h]
0x1800153f5  sub     rsp, 1B8h
0x1800153fc  mov     rax, cs:__security_cookie
0x180015403  xor     rax, rsp
0x180015406  mov     [rbp+0F0h+var_50], rax
0x18001540d  mov     r13, rcx
0x180015410  lea     rdx, aSihostcomponen; "SiHostComponentCreation"
0x180015417  lea     rcx, [rsp+1F0h+var_1A0]
0x18001541c  call    ??0?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015421  lea     r12, ??_7SiHostComponentCreation@AAMTraceProvider@@6B@; const AAMTraceProvider::SiHostComponentCreation::`vftable'
0x180015428  mov     [rsp+1F0h+var_1A0], r12
0x18001542d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180015432  call    ?StartActivity@SiHostComponentCreation@AAMTraceProvider@@QEAAXXZ; AAMTraceProvider::SiHostComponentCreation::StartActivity(void)
0x180015437  nop
0x180015438  xor     ebx, ebx
0x18001543a  mov     qword ptr [rsp+1F0h+var_1D0], rbx
0x18001543f  xor     edi, edi
0x180015441  xor     r9d, r9d; lpName
0x180015444  xor     r8d, r8d; bInitialState
0x180015447  lea     r15d, [rbx+1]
0x18001544b  mov     edx, r15d; bManualReset
0x18001544e  xor     ecx, ecx; lpEventAttributes
0x180015450  call    cs:__imp_CreateEventW
0x180015456  mov     rsi, rax
0x180015459  lea     r14, [r13+0F8h]
0x180015460  cmp     rax, [r14]
0x180015463  jz      short loc_180015472
0x180015465  mov     rcx, r14
0x180015468  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001546d  mov     [r14], rsi
0x180015470  jmp     short loc_180015475
0x180015472  mov     rsi, [r14]
0x180015475  test    rsi, rsi
0x180015478  jnz     short loc_180015498
0x18001547a  call    cs:__imp_GetLastError
0x180015480  mov     esi, eax
0x180015482  test    eax, eax
0x180015484  jle     loc_1800159F7
0x18001548a  movzx   esi, ax
0x18001548d  or      esi, 80070000h
0x180015493  jmp     loc_1800159F7
0x180015498  xor     r9d, r9d; lpName
0x18001549b  xor     r8d, r8d; bInitialState
0x18001549e  mov     edx, r15d; bManualReset
0x1800154a1  xor     ecx, ecx; lpEventAttributes
0x1800154a3  call    cs:__imp_CreateEventW
0x1800154a9  mov     rsi, rax
0x1800154ac  lea     r14, [r13+100h]
0x1800154b3  cmp     rax, [r14]
0x1800154b6  jz      short loc_1800154C5
0x1800154b8  mov     rcx, r14
0x1800154bb  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800154c0  mov     [r14], rsi
0x1800154c3  jmp     short loc_1800154C8
0x1800154c5  mov     rsi, [r14]
0x1800154c8  test    rsi, rsi
0x1800154cb  jz      short loc_18001547A
0x1800154cd  xor     r9d, r9d; lpName
0x1800154d0  xor     r8d, r8d; bInitialState
0x1800154d3  mov     edx, r15d; bManualReset
0x1800154d6  xor     ecx, ecx; lpEventAttributes
0x1800154d8  call    cs:__imp_CreateEventW
0x1800154de  mov     rsi, rax
0x1800154e1  lea     r14, [r13+108h]
0x1800154e8  cmp     rax, [r14]
0x1800154eb  jz      short loc_1800154FA
0x1800154ed  mov     rcx, r14
0x1800154f0  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800154f5  mov     [r14], rsi
0x1800154f8  jmp     short loc_1800154FD
0x1800154fa  mov     rsi, [r14]
0x1800154fd  test    rsi, rsi
0x180015500  jz      loc_18001547A
0x180015506  lea     rcx, [rsp+1F0h+var_1C0]
0x18001550b  call    ??$Make@VCLaunchActivationPlugin@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLaunchActivationPlugin@@@12@XZ; Microsoft::WRL::Details::Make<CLaunchActivationPlugin,>(void)
0x180015510  mov     r12, [rax]
0x180015513  mov     qword ptr [rax], 0
0x18001551a  mov     rdi, r12
0x18001551d  mov     [rsp+1F0h+var_1C8], r12
0x180015522  mov     rcx, [rsp+1F0h+var_1C0]
0x180015527  test    rcx, rcx
0x18001552a  jz      short loc_180015542
0x18001552c  mov     [rsp+1F0h+var_1C0], 0
0x180015535  mov     rax, [rcx]
0x180015538  mov     rax, [rax+10h]
0x18001553c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015541  nop
0x180015542  test    r12, r12
0x180015545  jnz     short loc_180015551
0x180015547  mov     esi, 80004005h
0x18001554c  jmp     loc_1800159F0
0x180015551  mov     rax, [r12]
0x180015555  lea     rdx, [rsp+1F0h+var_1B0]
0x18001555a  mov     rcx, r12
0x18001555d  mov     rax, [rax+18h]
0x180015561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015566  mov     rbx, rax
0x180015569  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015570  mov     ecx, 38h ; '8'; unsigned __int64
0x180015575  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001557a  mov     r14, rax
0x18001557d  lea     rsi, ??_7?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@6B@; const CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable'
0x180015584  test    rax, rax
0x180015587  jz      short loc_1800155B6
0x180015589  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180015590  movups  xmm0, xmmword ptr [rbx]
0x180015593  movdqu  xmmword ptr [rax+8], xmm0
0x180015598  movdqu  xmmword ptr [rax+18h], xmm1
0x18001559d  lea     rcx, [rax+28h]
0x1800155a1  mov     [rcx], r12
0x1800155a4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800155a9  mov     [r14], rsi
0x1800155ac  mov     dword ptr [r14+30h], 0
0x1800155b4  jmp     short loc_1800155B9
0x1800155b6  xor     r14d, r14d
0x1800155b9  test    r14, r14
0x1800155bc  jz      short loc_1800155CE
0x1800155be  mov     rax, [r14]
0x1800155c1  mov     rcx, r14
0x1800155c4  mov     rax, [rax+8]
0x1800155c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155cd  nop
0x1800155ce  mov     rbx, r14
0x1800155d1  mov     qword ptr [rsp+1F0h+var_1D0], rbx
0x1800155d6  test    r14, r14
0x1800155d9  jz      loc_180015547
0x1800155df  lea     r15, [r13+0B0h]
0x1800155e6  mov     [rsp+1F0h+var_1C0], r14
0x1800155eb  mov     rax, [r14]
0x1800155ee  mov     rcx, r14
0x1800155f1  mov     rax, [rax+8]
0x1800155f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155fa  nop
0x1800155fb  xor     esi, esi
0x1800155fd  mov     rdx, [r15+8]
0x180015601  cmp     rdx, [r15+18h]
0x180015605  jnz     short loc_180015618
0x180015607  inc     rdx
0x18001560a  mov     rcx, r15
0x18001560d  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180015612  mov     esi, eax
0x180015614  test    eax, eax
0x180015616  js      short loc_18001563B
0x180015618  mov     rcx, [r15+8]
0x18001561c  lea     rax, [rcx+1]
0x180015620  mov     [r15+8], rax
0x180015624  mov     rax, [r15]
0x180015627  lea     rcx, [rax+rcx*8]
0x18001562b  test    rcx, rcx
0x18001562e  jz      short loc_18001563B
0x180015630  lea     rdx, [rsp+1F0h+var_1C0]
0x180015635  call    ??0?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>> &&)
0x18001563a  nop
0x18001563b  mov     rcx, [rsp+1F0h+var_1C0]
0x180015640  test    rcx, rcx
0x180015643  jz      short loc_180015652
0x180015645  mov     rax, [rcx]
0x180015648  mov     rax, [rax+10h]
0x18001564c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015651  nop
0x180015652  test    esi, esi
0x180015654  js      loc_1800159F0
0x18001565a  lea     rcx, [rsp+1F0h+var_1C0]
0x18001565f  call    ??$Make@VCLaunchWithTileActivationPlugin@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLaunchWithTileActivationPlugin@@@12@XZ; Microsoft::WRL::Details::Make<CLaunchWithTileActivationPlugin,>(void)
0x180015664  mov     rsi, [rax]
0x180015667  mov     [rsp+1F0h+var_1B0], rsi
0x18001566c  mov     qword ptr [rax], 0
0x180015673  mov     rdi, rsi
0x180015676  mov     [rsp+1F0h+var_1C8], rsi
0x18001567b  mov     rax, [r12]
0x18001567f  mov     rcx, r12
0x180015682  mov     rax, [rax+10h]
0x180015686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568b  nop
0x18001568c  mov     rcx, [rsp+1F0h+var_1C0]
0x180015691  test    rcx, rcx
0x180015694  jz      short loc_1800156AC
0x180015696  mov     [rsp+1F0h+var_1C0], 0
0x18001569f  mov     rax, [rcx]
0x1800156a2  mov     rax, [rax+10h]
0x1800156a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ab  nop
0x1800156ac  test    rsi, rsi
0x1800156af  jz      loc_180015547
0x1800156b5  mov     rax, [rsi]
0x1800156b8  lea     rdx, [rsp+1F0h+var_1C0]
0x1800156bd  mov     rcx, rsi
0x1800156c0  mov     rax, [rax+18h]
0x1800156c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c9  mov     rbx, rax
0x1800156cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800156d3  mov     ecx, 38h ; '8'; unsigned __int64
0x1800156d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800156dd  mov     r12, rax
0x1800156e0  test    rax, rax
0x1800156e3  jz      short loc_18001571B
0x1800156e5  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800156ec  movups  xmm0, xmmword ptr [rbx]
0x1800156ef  movdqu  xmmword ptr [rax+8], xmm0
0x1800156f4  movdqu  xmmword ptr [rax+18h], xmm1
0x1800156f9  lea     rcx, [rax+28h]
0x1800156fd  mov     [rcx], rsi
0x180015700  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180015705  lea     rax, ??_7?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@6B@; const CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable'
0x18001570c  mov     [r12], rax
0x180015710  mov     dword ptr [r12+30h], 0
0x180015719  jmp     short loc_18001571E
0x18001571b  xor     r12d, r12d
0x18001571e  test    r12, r12
0x180015721  jz      short loc_180015734
0x180015723  mov     rax, [r12]
0x180015727  mov     rcx, r12
0x18001572a  mov     rax, [rax+8]
0x18001572e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015733  nop
0x180015734  mov     rbx, r12
0x180015737  mov     qword ptr [rsp+1F0h+var_1D0], rbx
0x18001573c  mov     rax, [r14]
0x18001573f  mov     rcx, r14
0x180015742  mov     rax, [rax+10h]
0x180015746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001574b  nop
0x18001574c  test    r12, r12
0x18001574f  jz      loc_180015547
0x180015755  mov     r14, r12
0x180015758  mov     [rsp+1F0h+var_1C0], r12
0x18001575d  mov     rax, [r12]
0x180015761  mov     rcx, r12
0x180015764  mov     rax, [rax+8]
0x180015768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576d  nop
0x18001576e  xor     esi, esi
0x180015770  mov     rdx, [r15+8]
0x180015774  cmp     rdx, [r15+18h]
0x180015778  jnz     short loc_18001578B
0x18001577a  inc     rdx
0x18001577d  mov     rcx, r15
0x180015780  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180015785  mov     esi, eax
0x180015787  test    eax, eax
0x180015789  js      short loc_1800157B2
0x18001578b  mov     rcx, [r15+8]
0x18001578f  lea     rax, [rcx+1]
0x180015793  mov     [r15+8], rax
0x180015797  mov     rax, [r15]
0x18001579a  lea     rcx, [rax+rcx*8]
0x18001579e  test    rcx, rcx
0x1800157a1  jz      short loc_1800157B2
0x1800157a3  lea     rdx, [rsp+1F0h+var_1C0]
0x1800157a8  call    ??0?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>> &&)
0x1800157ad  mov     r14, [rsp+1F0h+var_1C0]
0x1800157b2  test    r14, r14
0x1800157b5  jz      short loc_1800157C7
0x1800157b7  mov     rax, [r14]
0x1800157ba  mov     rcx, r14
0x1800157bd  mov     rax, [rax+10h]
0x1800157c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c6  nop
0x1800157c7  xor     r14d, r14d
0x1800157ca  test    esi, esi
0x1800157cc  js      loc_1800159F0
0x1800157d2  lea     rcx, [rsp+1F0h+var_1C0]
0x1800157d7  call    ??$Make@VCLaunchChildActivationPlugin@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLaunchChildActivationPlugin@@@12@XZ; Microsoft::WRL::Details::Make<CLaunchChildActivationPlugin,>(void)
0x1800157dc  mov     rdi, [rax]
0x1800157df  mov     [rax], r14
0x1800157e2  mov     [rsp+1F0h+var_1C8], rdi
0x1800157e7  mov     rcx, [rsp+1F0h+var_1B0]
0x1800157ec  mov     rax, [rcx]
0x1800157ef  mov     rax, [rax+10h]
0x1800157f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f8  nop
0x1800157f9  mov     rcx, [rsp+1F0h+var_1C0]
0x1800157fe  test    rcx, rcx
0x180015801  jz      short loc_180015815
0x180015803  mov     [rsp+1F0h+var_1C0], r14
0x180015808  mov     rax, [rcx]
0x18001580b  mov     rax, [rax+10h]
0x18001580f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015814  nop
0x180015815  test    rdi, rdi
0x180015818  jz      loc_180015547
0x18001581e  mov     rax, [rdi]
0x180015821  lea     rdx, [rsp+1F0h+var_1B0]
0x180015826  mov     rcx, rdi
0x180015829  mov     rax, [rax+18h]
0x18001582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015832  mov     rsi, rax
0x180015835  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001583c  mov     ecx, 38h ; '8'; unsigned __int64
0x180015841  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015846  mov     rbx, rax
0x180015849  test    rax, rax
  ... truncated ...
```
