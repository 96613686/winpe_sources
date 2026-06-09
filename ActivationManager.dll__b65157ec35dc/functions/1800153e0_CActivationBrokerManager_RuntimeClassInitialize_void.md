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
__int64 __fastcall CActivationBrokerManager::RuntimeClassInitialize(CActivationBrokerManager *this)
{
  _DWORD *v2; // rbx
  __int64 v3; // rdi
  HANDLE EventW; // rsi
  HANDLE *v5; // r14
  signed int LastError; // eax
  CActivationBrokerManager *v7; // rcx
  int v8; // esi
  HANDLE v9; // rsi
  HANDLE *v10; // r14
  HANDLE v11; // rsi
  HANDLE *v12; // r14
  __int64 *v13; // rax
  __int64 v14; // r12
  _OWORD *v15; // rbx
  char *v16; // rax
  _DWORD *v17; // r14
  _QWORD *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rsi
  _OWORD *v24; // rbx
  char *v25; // rax
  _DWORD *v26; // r12
  _DWORD *v27; // r14
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 *v30; // rax
  _OWORD *v31; // rsi
  char *v32; // rax
  _DWORD *v33; // r14
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  int v39; // eax
  char *v40; // rax
  __int64 v41; // rax
  _QWORD v43[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v45[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "SiHostComponentCreation");
  v45[0] = &AAMTraceProvider::SiHostComponentCreation::`vftable';
  AAMTraceProvider::SiHostComponentCreation::StartActivity((AAMTraceProvider::SiHostComponentCreation *)v45);
  v2 = 0;
  v3 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (HANDLE *)((char *)this + 248);
  if ( EventW == *((HANDLE *)this + 31) )
  {
    EventW = *v5;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 248);
    *v5 = EventW;
  }
  if ( !EventW )
    goto LABEL_5;
  v9 = CreateEventW(0, 1, 0, 0);
  v10 = (HANDLE *)((char *)this + 256);
  if ( v9 == *((HANDLE *)this + 32) )
  {
    v9 = *v10;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 256);
    *v10 = v9;
  }
  if ( v9
    && ((v11 = CreateEventW(0, 1, 0, 0), v12 = (HANDLE *)((char *)this + 264), v11 == *((HANDLE *)this + 33))
      ? (v11 = *v12)
      : (tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 264), *v12 = v11),
        v11) )
  {
    v13 = Microsoft::WRL::Details::Make<CLaunchActivationPlugin,>(v43);
    v14 = *v13;
    *v13 = 0;
    v3 = v14;
    v7 = (CActivationBrokerManager *)v43[0];
    if ( v43[0] )
    {
      v43[0] = 0;
      (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( !v14 )
      goto LABEL_18;
    v15 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 24LL))(v14, v44);
    v16 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
    {
      *(_OWORD *)(v16 + 8) = *v15;
      *(GUID *)(v16 + 24) = GUID_NULL;
      *((_QWORD *)v16 + 5) = v14;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v16 + 40);
      *(_QWORD *)v17 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
      v17[12] = 0;
    }
    else
    {
      v17 = 0;
    }
    if ( v17 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 8LL))(v17);
    v2 = v17;
    if ( !v17 )
      goto LABEL_18;
    v18 = (_QWORD *)((char *)this + 176);
    v43[0] = v17;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 8LL))(v17);
    v8 = 0;
    v19 = *((_QWORD *)this + 23);
    if ( v19 != *((_QWORD *)this + 25)
      || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                 (char *)this + 176,
                 v19 + 1),
          v8 >= 0) )
    {
      v20 = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = v20 + 1;
      v21 = (_QWORD *)(*v18 + 8 * v20);
      if ( v21 )
        Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
          v21,
          v43);
    }
    v7 = (CActivationBrokerManager *)v43[0];
    if ( v43[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43[0] + 16LL))(v43[0]);
    if ( v8 >= 0 )
    {
      v22 = Microsoft::WRL::Details::Make<CLaunchWithTileActivationPlugin,>(v43);
      v44[0] = *v22;
      v23 = v44[0];
      *v22 = 0;
      v3 = v23;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v7 = (CActivationBrokerManager *)v43[0];
      if ( v43[0] )
      {
        v43[0] = 0;
        (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      if ( !v23 )
        goto LABEL_18;
      v24 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v23 + 24LL))(v23, v43);
      v25 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v26 = v25;
      if ( v25 )
      {
        *(_OWORD *)(v25 + 8) = *v24;
        *(GUID *)(v25 + 24) = GUID_NULL;
        *((_QWORD *)v25 + 5) = v23;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v25 + 40);
        *(_QWORD *)v26 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
        v26[12] = 0;
      }
      else
      {
        v26 = 0;
      }
      if ( v26 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v26 + 8LL))(v26);
      v2 = v26;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( !v26 )
        goto LABEL_18;
      v27 = v26;
      v43[0] = v26;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v26 + 8LL))(v26);
      v8 = 0;
      v28 = *((_QWORD *)this + 23);
      if ( v28 != *((_QWORD *)this + 25)
        || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                   (char *)this + 176,
                   v28 + 1),
            v8 >= 0) )
      {
        v29 = *((_QWORD *)this + 23);
        *((_QWORD *)this + 23) = v29 + 1;
        v7 = (CActivationBrokerManager *)(*v18 + 8 * v29);
        if ( v7 )
        {
          Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
            v7,
            v43);
          v27 = (_DWORD *)v43[0];
        }
      }
      if ( v27 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v8 >= 0 )
      {
        v30 = Microsoft::WRL::Details::Make<CLaunchChildActivationPlugin,>(v43);
        v3 = *v30;
        *v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44[0] + 16LL))(v44[0]);
        v7 = (CActivationBrokerManager *)v43[0];
        if ( v43[0] )
        {
          v43[0] = 0;
          (*(void (__fastcall **)(CActivationBrokerManager *))(*(_QWORD *)v7 + 16LL))(v7);
        }
        if ( v3 )
        {
          v31 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 24LL))(v3, v44);
          v32 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
          v2 = v32;
          if ( v32 )
          {
            *(_OWORD *)(v32 + 8) = *v31;
            *(GUID *)(v32 + 24) = GUID_NULL;
            *((_QWORD *)v32 + 5) = v3;
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v32 + 40);
            *(_QWORD *)v2 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
            v2[12] = 0;
          }
          else
          {
            v2 = 0;
          }
          if ( v2 )
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v2 )
          {
            v33 = v2;
            v43[0] = v2;
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
            v8 = 0;
            v34 = *((_QWORD *)this + 23);
            if ( v34 != *((_QWORD *)this + 25)
              || (v8 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                         (char *)this + 176,
                         v34 + 1),
                  v8 >= 0) )
            {
              v35 = *((_QWORD *)this + 23);
              *((_QWORD *)this + 23) = v35 + 1;
              v7 = (CActivationBrokerManager *)(*v18 + 8 * v35);
              if ( v7 )
              {
                Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>(
                  v7,
                  v43);
                v33 = (_DWORD *)v43[0];
              }
            }
            if ( v33 )
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v33 + 16LL))(v33);
            if ( v8 >= 0 )
            {
              CActivationBrokerManager::_AddAndRegisterActivationPlugins((RTL_SRWLOCK *)this);
              if ( byte_1800D1F02 < 0 )
                McTemplateU0qq_EventWriteTransfer(
                  v37,
                  ActivationBroker_PluginsCreated,
                  *((unsigned int *)this + 46),
                  *((unsigned int *)this + 46));
              ReadKeyHKLMDword(v37, v36, v38, (char *)this + 328);
              v8 = ActivationManagerShimFactory_Initialize();
              if ( v8 >= 0 )
              {
                v39 = CActivationBrokerManager::_EnsureMutablePackagesOnline(v7);
                if ( v39 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x117,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
                    (const char *)(unsigned int)v39,
                    (int)v2);
                v8 = CServiceHostComponent::RegisterServiceInformation(
                       (CActivationBrokerManager *)((char *)this + 72),
                       &IID_ActivationBrokerManager);
                if ( v8 >= 0 )
                {
                  v40 = this ? (char *)this + 136 : 0LL;
                  v44[0] = (__int64)v40;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 320);
                  v8 = Microsoft::WRL::Details::MakeAndInitialize<CApplicationActivationBroker,CApplicationActivationBroker,IActivationBrokerManager *>(
                         (CApplicationActivationBroker **)this + 40,
                         v44);
                  if ( v8 >= 0 )
                  {
                    v41 = Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create();
                    v8 = Microsoft::WRL::Details::RegisterObjects<2>(v41);
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
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v2 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 16LL))(v2);
  v45[0] = &AAMTraceProvider::SiHostComponentCreation::`vftable';
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v45);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v45);
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
