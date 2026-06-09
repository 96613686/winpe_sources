# CLightDismissClientStore::Register(LIGHT_DISMISS_POLICY,ILightDismissNotification *,ulong *)

- ea: `0x1800165d0`
- end: `0x180016b8e`
- name: `?Register@CLightDismissClientStore@@UEAAJULIGHT_DISMISS_POLICY@@PEAUILightDismissNotification@@PEAK@Z`
- size: `1470`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180015bcc`
- `0x180015e10`
- `0x180016110`
- `0x1800165d0`
- `0x180016b94`
- `0x180016c30`
- `0x180016d10`
- `0x1800173c0`
- `0x18001741c`
- `0x180017460`
- `0x1800174d4`
- `0x18001758c`
- `0x18001764c`
- `0x1800256d0`
- `0x18002ad60`
- `0x180030538`
- `0x180033e98`
- `0x180033ef0`
- `0x180033f0c`
- `0x18003aa84`
- `0x18003cc04`
- `0x18003dd2c`
- `0x1800441cc`
- `0x180046fd0`
- `0x18004a250`
- `0x180050ba0`
- `0x18005659c`
- `0x18007f814`
- `0x18007fe30`
- `0x18007fe94`
- `0x18007ff94`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001696d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001696d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800169ff`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800169ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a92`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180016a34`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180016a34`
- `USER32!GetPropW` at `0x180016833`
- `USER32!GetPropW` at `0x180016833`
- `USER32!GetWindow` at `0x18001681b`
- `USER32!GetWindow` at `0x18001681b`
- `USER32!DestroyWindow` at `0x180016af6`
- `USER32!DestroyWindow` at `0x180016af6`
- `USER32!GetWindowThreadProcessId` at `0x1800166e4`
- `USER32!GetWindowThreadProcessId` at `0x180016948`
- `USER32!GetWindowThreadProcessId` at `0x1800166e4`
- `USER32!GetWindowThreadProcessId` at `0x180016948`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::Register(__int64 a1, int *a2, __int64 a3, _DWORD *a4)
{
  int v8; // edx
  char *v9; // rax
  char *v10; // rdi
  __int64 v11; // rcx
  int v12; // r15d
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  int v15; // ecx
  int CallingProcessId; // ebx
  HWND *v17; // rbx
  __int64 i; // rbx
  unsigned int v19; // edx
  unsigned int v20; // r8d
  HWND v21; // rbx
  CLightDismissClientStore *v22; // rcx
  HWND Window; // r13
  unsigned __int64 v24; // rbx
  _QWORD *v25; // r15
  CLightDismissClientStore::CLIENT_INFO *v26; // r14
  struct CLightDismissClientStore::CLIENT_INFO *NodeInChain; // rax
  struct CLightDismissClientStore::CLIENT_INFO *v28; // r14
  __int64 v29; // rbx
  unsigned int v30; // edx
  struct CLightDismissClientStore::CLIENT_INFO **v31; // rax
  __int64 v32; // rdx
  char v33; // r14
  unsigned __int64 v34; // r15
  DWORD ProcessId; // eax
  DWORD v36; // r8d
  __int64 v37; // rdx
  __int64 v38; // rcx
  unsigned int v39; // r8d
  HANDLE v40; // rax
  void *v41; // r15
  __int64 v42; // r13
  __int64 v43; // rdx
  __int64 *v44; // rdx
  int v45; // eax
  DWORD dwProcessId[2]; // [rsp+30h] [rbp-D0h] BYREF
  HWND *v48; // [rsp+38h] [rbp-C8h]
  _DWORD *v49; // [rsp+40h] [rbp-C0h]
  _QWORD *v50; // [rsp+48h] [rbp-B8h]
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h]
  _DWORD *v53; // [rsp+60h] [rbp-A0h]
  void **v54; // [rsp+70h] [rbp-90h] BYREF
  char v55[272]; // [rsp+78h] [rbp-88h] BYREF
  char v56[8]; // [rsp+188h] [rbp+88h] BYREF
  char v57[48]; // [rsp+190h] [rbp+90h] BYREF

  v53 = a4;
  *a4 = 0;
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v54,
    "LightDismissRegister");
  v8 = *(_DWORD *)(a1 + 152);
  v54 = &LightDismissFrameworkTelemetry::LightDismissRegister::`vftable';
  LightDismissFrameworkTelemetry::LightDismissRegister::StartActivity(
    (LightDismissFrameworkTelemetry::LightDismissRegister *)&v54,
    v8);
  if ( !*(_DWORD *)(a1 + 152) )
  {
    CallingProcessId = 0;
    *a4 = 1;
    goto LABEL_81;
  }
  v9 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    CallingProcessId = -2147024882;
    goto LABEL_81;
  }
  v11 = *((_QWORD *)a2 + 1);
  v12 = *a2;
  *((_QWORD *)v9 + 4) = 0;
  *(_DWORD *)v9 = v12;
  v52 = v11;
  v48 = (HWND *)(v9 + 8);
  *((_QWORD *)v9 + 1) = v11;
  if ( *((_QWORD *)v9 + 4) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v13 = *((_QWORD *)v10 + 4);
    *((_QWORD *)v10 + 4) = a3;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *((_DWORD *)v10 + 4) = ++*(_DWORD *)(a1 + 48);
  v49 = v10 + 16;
  if ( GetWindowThreadProcessId(*v48, (LPDWORD)v10 + 5) )
  {
    CallingProcessId = anonymous_namespace_::GetCallingProcessId(v10 + 24);
    if ( CallingProcessId >= 0 )
    {
      v17 = v48;
      if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        McTemplateU0pdd_EventWriteTransfer(v15, (_DWORD)v14, (unsigned int)*v48, *((_DWORD *)v10 + 5), v12);
      LightDismissFrameworkTelemetry::LightDismissRegister::StartFlags<unsigned long &>(&v54, a2);
      *((_QWORD *)v10 + 6) = 0;
      *(_QWORD *)dwProcessId = v10 + 48;
      *((_QWORD *)v10 + 7) = 0;
      *(_DWORD *)(a1 + 24) = 5;
      *(_DWORD *)(a1 + 164) = 0;
      v50 = v10 + 56;
      if ( (*(_DWORD *)v10 & 4) != 0 )
      {
        for ( i = *(_QWORD *)(a1 + 96);
              (int)--i >= 0;
              CLightDismissClientStore::_FilterChain(
                (CLightDismissClientStore *)a1,
                *(struct CLightDismissClientStore::CLIENT_INFO **)(*(_QWORD *)(a1 + 88) + 8 * i),
                4u,
                0) )
        {
          ;
        }
        CLightDismissClientStore::_UpdateOverlayRegion((CLightDismissClientStore *)a1);
        CLightDismissClientStore::_DismissClients((CLightDismissClientStore *)a1, v19, v20);
        v17 = v48;
      }
      else if ( (*(_DWORD *)v10 & 8) != 0 )
      {
        CLightDismissClientStore::_HandleDialog((CLightDismissClientStore *)a1, *v17);
      }
      else if ( anonymous_namespace_::GetOwner(*v17) )
      {
        *(_DWORD *)(a1 + 24) = 2;
        CLightDismissClientStore::DismissAllInactiveClients((CLightDismissClientStore *)a1, *v17);
      }
      if ( (*(_DWORD *)v10 & 0x100) != 0 )
        *(_DWORD *)(a1 + 164) = 1;
      if ( (*(_DWORD *)v10 & 0x1000) != 0 )
        *(_DWORD *)(a1 + 168) = 18;
      else
        *(_DWORD *)(a1 + 168) = (*(_DWORD *)v10 & 0x200) != 0 ? 6 : 3;
      *(_DWORD *)(a1 + 156) = (*(_DWORD *)v10 >> 10) & 1;
      v21 = *v17;
      Window = GetWindow(v21, 4u);
      if ( !Window )
        Window = (HWND)GetPropW(v21, L"Shell_Logical_Owner_Window_Prop");
      v24 = 0;
      v25 = (_QWORD *)(a1 + 88);
      while ( 1 )
      {
        v26 = (CLightDismissClientStore::CLIENT_INFO *)v10;
        if ( v24 >= *(_QWORD *)(a1 + 96) )
          break;
        v25 = (_QWORD *)(a1 + 88);
        NodeInChain = CLightDismissClientStore::_GetNodeInChain(
                        v22,
                        *(struct CLightDismissClientStore::CLIENT_INFO **)(*(_QWORD *)(a1 + 88) + 8 * v24),
                        Window);
        v28 = NodeInChain;
        if ( NodeInChain )
        {
          v29 = *((_QWORD *)NodeInChain + 7);
          v51 = v29;
          if ( v29 )
          {
            if ( *(HWND *)(v29 + 8) == *v48 )
            {
              *v49 = *(_DWORD *)(v29 + 16);
              *v50 = *(_QWORD *)(v29 + 56);
              CTSimpleArray<CLightDismissClientStore::CLIENT_INFO *,4294967294,CTPolicyCoTaskMem<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardCompareHelper<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardMergeHelper<CLightDismissClientStore::CLIENT_INFO *>>::Remove(
                a1 + 88,
                &v51);
              CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(
                (CLightDismissClientStore::CLIENT_INFO *)v29,
                v30);
            }
            else
            {
              *(_DWORD *)(a1 + 24) = 5;
              CLightDismissClientStore::_RemoveChain(
                (CLightDismissClientStore *)a1,
                (struct CLightDismissClientStore::CLIENT_INFO *)v29);
            }
          }
          v31 = *(struct CLightDismissClientStore::CLIENT_INFO ***)dwProcessId;
          *((_QWORD *)v28 + 7) = v10;
          *v31 = v28;
          goto LABEL_43;
        }
        ++v24;
      }
      if ( **(_QWORD **)dwProcessId )
        goto LABEL_43;
      v32 = v25[1];
      CallingProcessId = 0;
      if ( v32 != v25[3]
        || (CallingProcessId = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>>::_EnsureCapacity(
                                 v25,
                                 v32 + 1),
            CallingProcessId >= 0) )
      {
        v14 = (_QWORD *)(*v25 + 8 * v25[1]++);
        if ( !v14 )
          goto LABEL_43;
        *v14 = v10;
      }
      if ( CallingProcessId < 0 )
        goto LABEL_72;
LABEL_43:
      CallingProcessId = CLightDismissClientStore::_CreateMessageWindow((CLightDismissClientStore *)a1);
      if ( CallingProcessId < 0 )
        goto LABEL_67;
      CallingProcessId = 0;
      dwProcessId[0] = 0;
      GetWindowThreadProcessId(*v48, dwProcessId);
      v33 = 0;
      v34 = 0;
      if ( *(_QWORD *)(a1 + 64) )
      {
        do
        {
          ProcessId = GetProcessId(*(HANDLE *)(*(_QWORD *)(a1 + 56) + 16 * v34 + 8));
          v36 = dwProcessId[0];
          if ( ProcessId == dwProcessId[0] )
            v33 = 1;
          ++v34;
        }
        while ( v34 < *(_QWORD *)(a1 + 64) );
        if ( v33 )
          goto LABEL_49;
      }
      else
      {
        v36 = dwProcessId[0];
      }
      v40 = OpenProcess(0x101000u, 0, v36);
      v41 = v40;
      if ( v40 )
      {
        v42 = RegisterWaitForSingleObjectEx(v40, anonymous_namespace_::WaitCallback, dwProcessId[0], 0xFFFFFFFFLL, 24);
        if ( v42 )
        {
          v43 = *(_QWORD *)(a1 + 64);
          if ( v43 != *(_QWORD *)(a1 + 80)
            || (CallingProcessId = CTSimpleArray<SmartXmlnsDefinition,4294967294,CTPolicyCoTaskMem<SmartXmlnsDefinition>,CSimpleArrayStandardCompareHelper<SmartXmlnsDefinition>,CSimpleArrayStandardMergeHelper<SmartXmlnsDefinition>>::_EnsureCapacity(
                                     a1 + 56,
                                     v43 + 1),
                CallingProcessId >= 0) )
          {
            ++*(_QWORD *)(a1 + 64);
            v44 = (__int64 *)(16LL * *(_QWORD *)(a1 + 64) + *(_QWORD *)(a1 + 56) - 16LL);
            if ( v44 )
            {
              *v44 = v42;
              v44[1] = (__int64)v41;
            }
          }
        }
        else
        {
          CallingProcessId = ResultFromKnownLastError();
        }
        if ( CallingProcessId < 0 )
        {
          CloseHandle(v41);
          goto LABEL_67;
        }
LABEL_50:
        CallingProcessId = CLightDismissClientStore::_CreateIMEWinEventHook((CLightDismissClientStore *)a1);
        if ( CallingProcessId >= 0 )
        {
          CallingProcessId = CLightDismissClientStore::_UpdateOverlayRegion((CLightDismissClientStore *)a1);
          if ( CallingProcessId >= 0 )
          {
            if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
              McTemplateU0p_EventWriteTransfer(v38, v37, v52);
            *v53 = *(_DWORD *)(a1 + 48);
            if ( (*v10 & 2) != 0 )
              CLightDismissClientStore::_HandleNewFocusLostObject(
                (CLightDismissClientStore *)a1,
                (struct CLightDismissClientStore::CLIENT_INFO *)v10);
            goto LABEL_78;
          }
        }
LABEL_67:
        if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(
            &MICROSOFT_WINDOWSUIIMMERSIVE_PUBLISHER_Context,
            Popup_LightDismiss_Failure,
            (unsigned int)CallingProcessId);
        v45 = 10;
        if ( CallingProcessId != -2147023496 )
          v45 = 1;
        *(_DWORD *)(a1 + 24) = v45;
        CLightDismissClientStore::_RemoveChain(
          (CLightDismissClientStore *)a1,
          (struct CLightDismissClientStore::CLIENT_INFO *)v10);
        v26 = 0;
LABEL_72:
        if ( v26 )
          goto LABEL_76;
        goto LABEL_77;
      }
      CallingProcessId = ResultFromKnownLastError();
LABEL_49:
      if ( CallingProcessId < 0 )
        goto LABEL_67;
      goto LABEL_50;
    }
  }
  else
  {
    CallingProcessId = -2147024809;
  }
  v26 = (CLightDismissClientStore::CLIENT_INFO *)v10;
LABEL_76:
  CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(v26, (unsigned int)v14);
LABEL_77:
  DestroyWindow(*(HWND *)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
LABEL_78:
  CLightDismissClientStore::_DismissClients((CLightDismissClientStore *)a1, v37, v39);
LABEL_81:
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v54,
    (unsigned int)CallingProcessId);
  v54 = &LightDismissFrameworkTelemetry::LightDismissRegister::`vftable';
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v57);
  wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v56);
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(v55);
  return (unsigned int)CallingProcessId;
}

```

## disassembly

```asm
0x1800165d0  mov     [rsp-8+arg_10], rbx
0x1800165d5  push    rbp
0x1800165d6  push    rsi
0x1800165d7  push    rdi
0x1800165d8  push    r12
0x1800165da  push    r13
0x1800165dc  push    r14
0x1800165de  push    r15
0x1800165e0  lea     rbp, [rsp-0D0h]
0x1800165e8  sub     rsp, 1D0h
0x1800165ef  mov     rax, cs:__security_cookie
0x1800165f6  xor     rax, rsp
0x1800165f9  mov     [rbp+100h+var_40], rax
0x180016600  mov     r14, rdx
0x180016603  mov     [rsp+200h+var_1A0], r9
0x180016608  mov     rsi, rcx
0x18001660b  lea     rdx, aLightdismissre; "LightDismissRegister"
0x180016612  xor     r12d, r12d
0x180016615  lea     rcx, [rsp+200h+var_190]
0x18001661a  mov     [r9], r12d
0x18001661d  mov     rdi, r9
0x180016620  mov     rbx, r8
0x180016623  call    ??0?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016628  mov     edx, [rsi+98h]; int
0x18001662e  lea     rax, ??_7LightDismissRegister@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissRegister::`vftable'
0x180016635  lea     rcx, [rsp+200h+var_190]; this
0x18001663a  mov     [rsp+200h+var_190], rax
0x18001663f  call    ?StartActivity@LightDismissRegister@LightDismissFrameworkTelemetry@@QEAAXH@Z; LightDismissFrameworkTelemetry::LightDismissRegister::StartActivity(int)
0x180016644  cmp     [rsi+98h], r12d
0x18001664b  jz      loc_180016B15
0x180016651  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016658  lea     ecx, [r12+40h]; unsigned __int64
0x18001665d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016662  mov     rdi, rax
0x180016665  test    rax, rax
0x180016668  jz      loc_180016B0E
0x18001666e  mov     rcx, [r14+8]
0x180016672  mov     r15d, [r14]
0x180016675  mov     [rax+20h], r12
0x180016679  mov     [rax], r15d
0x18001667c  add     rax, 8
0x180016680  mov     [rsp+200h+var_1A8], rcx
0x180016685  mov     [rsp+200h+var_1C8], rax
0x18001668a  mov     [rax], rcx
0x18001668d  cmp     [rdi+20h], rbx
0x180016691  jz      short loc_1800166C0
0x180016693  test    rbx, rbx
0x180016696  jz      short loc_1800166A7
0x180016698  mov     rax, [rbx]
0x18001669b  mov     rcx, rbx
0x18001669e  mov     rax, [rax+8]
0x1800166a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166a7  mov     rcx, [rdi+20h]
0x1800166ab  mov     [rdi+20h], rbx
0x1800166af  test    rcx, rcx
0x1800166b2  jz      short loc_1800166C0
0x1800166b4  mov     rax, [rcx]
0x1800166b7  mov     rax, [rax+10h]
0x1800166bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166c0  lea     rcx, [rdi+10h]
0x1800166c4  mov     r12d, 1
0x1800166ca  add     [rsi+30h], r12d
0x1800166ce  lea     rdx, [rdi+14h]; lpdwProcessId
0x1800166d2  mov     eax, [rsi+30h]
0x1800166d5  mov     [rcx], eax
0x1800166d7  mov     rax, [rsp+200h+var_1C8]
0x1800166dc  mov     [rsp+200h+var_1C0], rcx
0x1800166e1  mov     rcx, [rax]; hWnd
0x1800166e4  call    cs:__imp_GetWindowThreadProcessId
0x1800166ea  test    eax, eax
0x1800166ec  jz      loc_180016AE2
0x1800166f2  lea     rcx, [rdi+18h]
0x1800166f6  call    _anonymous_namespace___GetCallingProcessId
0x1800166fb  mov     ebx, eax
0x1800166fd  test    eax, eax
0x1800166ff  js      loc_180016AE7
0x180016705  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, r12b
0x18001670c  mov     rbx, [rsp+200h+var_1C8]
0x180016711  jz      short loc_180016724
0x180016713  mov     r9d, [rdi+14h]
0x180016717  mov     r8, [rbx]
0x18001671a  mov     [rsp+200h+var_1E0], r15d
0x18001671f  call    McTemplateU0pdd_EventWriteTransfer
0x180016724  mov     rdx, r14
0x180016727  lea     rcx, [rsp+200h+var_190]
0x18001672c  call    ??$StartFlags@AEAK@LightDismissRegister@LightDismissFrameworkTelemetry@@QEAAXAEAK@Z; LightDismissFrameworkTelemetry::LightDismissRegister::StartFlags<ulong &>(ulong &)
0x180016731  xor     r14d, r14d
0x180016734  lea     rax, [rdi+30h]
0x180016738  mov     [rax], r14
0x18001673b  mov     qword ptr [rsp+200h+dwProcessId], rax
0x180016740  lea     rax, [rdi+38h]
0x180016744  mov     [rax], r14
0x180016747  mov     dword ptr [rsi+18h], 5
0x18001674e  lea     r15d, [r14+4]
0x180016752  mov     [rsi+0A4h], r14d
0x180016759  mov     [rsp+200h+var_1B8], rax
0x18001675e  mov     eax, [rdi]
0x180016760  test    r15b, al
0x180016763  jz      short loc_18001679C
0x180016765  mov     rbx, [rsi+60h]
0x180016769  jmp     short loc_18001677E
0x18001676b  mov     rdx, [rsi+58h]
0x18001676f  xor     r9d, r9d; unsigned int
0x180016772  mov     r8d, r15d; unsigned int
0x180016775  mov     rdx, [rdx+rbx*8]; struct CLightDismissClientStore::CLIENT_INFO *
0x180016779  call    ?_FilterChain@CLightDismissClientStore@@AEAAXPEAUCLIENT_INFO@1@KK@Z; CLightDismissClientStore::_FilterChain(CLightDismissClientStore::CLIENT_INFO *,ulong,ulong)
0x18001677e  sub     rbx, r12
0x180016781  mov     rcx, rsi; this
0x180016784  test    ebx, ebx
0x180016786  jns     short loc_18001676B
0x180016788  call    ?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_UpdateOverlayRegion(void)
0x18001678d  mov     rcx, rsi; this
0x180016790  call    ?_DismissClients@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_DismissClients(void)
0x180016795  mov     rbx, [rsp+200h+var_1C8]
0x18001679a  jmp     short loc_1800167CC
0x18001679c  test    al, 8
0x18001679e  jz      short loc_1800167AD
0x1800167a0  mov     rdx, [rbx]; HWND
0x1800167a3  mov     rcx, rsi; this
0x1800167a6  call    ?_HandleDialog@CLightDismissClientStore@@AEAAXPEAUHWND__@@@Z; CLightDismissClientStore::_HandleDialog(HWND__ *)
0x1800167ab  jmp     short loc_1800167CC
0x1800167ad  mov     rcx, [rbx]; hWnd
0x1800167b0  call    _anonymous_namespace___GetOwner
0x1800167b5  test    rax, rax
0x1800167b8  jz      short loc_1800167CC
0x1800167ba  mov     dword ptr [rsi+18h], 2
0x1800167c1  mov     rcx, rsi; this
0x1800167c4  mov     rdx, [rbx]; HWND
0x1800167c7  call    ?DismissAllInactiveClients@CLightDismissClientStore@@IEAAJPEAUHWND__@@@Z; CLightDismissClientStore::DismissAllInactiveClients(HWND__ *)
0x1800167cc  test    dword ptr [rdi], 100h
0x1800167d2  jz      short loc_1800167DB
0x1800167d4  mov     [rsi+0A4h], r12d
0x1800167db  mov     eax, [rdi]
0x1800167dd  bt      eax, 0Ch
0x1800167e1  jnb     short loc_1800167EF
0x1800167e3  mov     dword ptr [rsi+0A8h], 12h
0x1800167ed  jmp     short loc_180016804
0x1800167ef  and     eax, 200h
0x1800167f4  neg     eax
0x1800167f6  sbb     eax, eax
0x1800167f8  and     eax, 3
0x1800167fb  add     eax, 3
0x1800167fe  mov     [rsi+0A8h], eax
0x180016804  mov     eax, [rdi]
0x180016806  mov     edx, r15d; uCmd
0x180016809  shr     eax, 0Ah
0x18001680c  and     eax, r12d
0x18001680f  mov     [rsi+9Ch], eax
0x180016815  mov     rbx, [rbx]
0x180016818  mov     rcx, rbx; hWnd
0x18001681b  call    cs:__imp_GetWindow
0x180016821  mov     r13, rax
0x180016824  test    rax, rax
0x180016827  jnz     short loc_18001683C
0x180016829  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x180016830  mov     rcx, rbx; hWnd
0x180016833  call    cs:__imp_GetPropW
0x180016839  mov     r13, rax
0x18001683c  mov     rbx, r14
0x18001683f  lea     r15, [rsi+58h]
0x180016843  mov     r14, rdi
0x180016846  cmp     rbx, [rsi+60h]
0x18001684a  jnb     loc_1800168D9
0x180016850  lea     r15, [rsi+58h]
0x180016854  mov     r8, r13; HWND
0x180016857  mov     rdx, [r15]
0x18001685a  mov     rdx, [rdx+rbx*8]; struct CLightDismissClientStore::CLIENT_INFO *
0x18001685e  call    ?_GetNodeInChain@CLightDismissClientStore@@AEBAPEAUCLIENT_INFO@1@PEAU21@PEAUHWND__@@@Z; CLightDismissClientStore::_GetNodeInChain(CLightDismissClientStore::CLIENT_INFO *,HWND__ *)
0x180016863  mov     r14, rax
0x180016866  test    rax, rax
0x180016869  jnz     short loc_180016870
0x18001686b  add     rbx, r12
0x18001686e  jmp     short loc_180016843
0x180016870  mov     rbx, [rax+38h]
0x180016874  mov     [rsp+200h+var_1B0], rbx
0x180016879  test    rbx, rbx
0x18001687c  jz      short loc_1800168CB
0x18001687e  mov     rax, [rsp+200h+var_1C8]
0x180016883  mov     rax, [rax]
0x180016886  cmp     [rbx+8], rax
0x18001688a  jnz     short loc_1800168B9
0x18001688c  mov     eax, [rbx+10h]
0x18001688f  lea     rdx, [rsp+200h+var_1B0]
0x180016894  mov     rcx, [rsp+200h+var_1C0]
0x180016899  mov     [rcx], eax
0x18001689b  mov     rcx, [rsp+200h+var_1B8]
0x1800168a0  mov     rax, [rbx+38h]
0x1800168a4  mov     [rcx], rax
0x1800168a7  mov     rcx, r15
0x1800168aa  call    ?Remove@?$CTSimpleArray@PEAUCLIENT_INFO@CLightDismissClientStore@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUCLIENT_INFO@CLightDismissClientStore@@@@V?$CSimpleArrayStandardCompareHelper@PEAUCLIENT_INFO@CLightDismissClientStore@@@@V?$CSimpleArrayStandardMergeHelper@PEAUCLIENT_INFO@CLightDismissClientStore@@@@@@QEAAJAEBQEAUCLIENT_INFO@CLightDismissClientStore@@PEA_K@Z; CTSimpleArray<CLightDismissClientStore::CLIENT_INFO *,4294967294,CTPolicyCoTaskMem<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardCompareHelper<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardMergeHelper<CLightDismissClientStore::CLIENT_INFO *>>::Remove(CLightDismissClientStore::CLIENT_INFO * const &,unsigned __int64 *)
0x1800168af  mov     rcx, rbx; this
0x1800168b2  call    ??_GCLIENT_INFO@CLightDismissClientStore@@QEAAPEAXI@Z; CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(uint)
0x1800168b7  jmp     short loc_1800168CB
0x1800168b9  mov     rdx, rbx; struct CLightDismissClientStore::CLIENT_INFO *
0x1800168bc  mov     dword ptr [rsi+18h], 5
0x1800168c3  mov     rcx, rsi; this
0x1800168c6  call    ?_RemoveChain@CLightDismissClientStore@@AEAAJPEAUCLIENT_INFO@1@@Z; CLightDismissClientStore::_RemoveChain(CLightDismissClientStore::CLIENT_INFO *)
0x1800168cb  mov     rax, qword ptr [rsp+200h+dwProcessId]
0x1800168d0  mov     [r14+38h], rdi
0x1800168d4  mov     [rax], r14
0x1800168d7  jmp     short loc_180016923
0x1800168d9  mov     rax, qword ptr [rsp+200h+dwProcessId]
0x1800168de  cmp     qword ptr [rax], 0
0x1800168e2  jnz     short loc_180016923
0x1800168e4  mov     rdx, [r15+8]
0x1800168e8  xor     ebx, ebx
0x1800168ea  cmp     rdx, [r15+18h]
0x1800168ee  jnz     short loc_180016901
0x1800168f0  inc     rdx
0x1800168f3  mov     rcx, r15
0x1800168f6  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800168fb  mov     ebx, eax
0x1800168fd  test    eax, eax
0x1800168ff  js      short loc_18001691B
0x180016901  add     [r15+8], r12
0x180016905  mov     rdx, [r15+8]
0x180016909  mov     rax, [r15]
0x18001690c  dec     rdx
0x18001690f  lea     rdx, [rax+rdx*8]
0x180016913  test    rdx, rdx
0x180016916  jz      short loc_180016923
0x180016918  mov     [rdx], rdi
0x18001691b  test    ebx, ebx
0x18001691d  js      loc_180016ADB
0x180016923  mov     rcx, rsi; this
0x180016926  call    ?_CreateMessageWindow@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateMessageWindow(void)
0x18001692b  mov     ebx, eax
0x18001692d  test    eax, eax
0x18001692f  js      loc_180016A98
0x180016935  mov     rax, [rsp+200h+var_1C8]
0x18001693a  lea     rdx, [rsp+200h+dwProcessId]; lpdwProcessId
0x18001693f  xor     ebx, ebx
0x180016941  mov     [rsp+200h+dwProcessId], ebx
0x180016945  mov     rcx, [rax]; hWnd
0x180016948  call    cs:__imp_GetWindowThreadProcessId
0x18001694e  xor     r14b, r14b
0x180016951  xor     r15d, r15d
0x180016954  cmp     [rsi+40h], rbx
0x180016958  jbe     loc_1800169F3
0x18001695e  mov     rax, [rsi+38h]
0x180016962  mov     rcx, r15
0x180016965  add     rcx, rcx
0x180016968  mov     rcx, [rax+rcx*8+8]; Process
0x18001696d  call    cs:__imp_GetProcessId
0x180016973  mov     r8d, [rsp+200h+dwProcessId]
0x180016978  cmp     eax, r8d
0x18001697b  movzx   r14d, r14b
0x18001697f  cmovz   r14d, r12d
0x180016983  add     r15, r12
0x180016986  cmp     r15, [rsi+40h]
0x18001698a  jb      short loc_18001695E
0x18001698c  test    r14b, r14b
0x18001698f  jz      short loc_1800169F8
0x180016991  test    ebx, ebx
0x180016993  js      loc_180016A98
0x180016999  mov     rcx, rsi; this
0x18001699c  call    ?_CreateIMEWinEventHook@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateIMEWinEventHook(void)
0x1800169a1  mov     ebx, eax
0x1800169a3  test    eax, eax
0x1800169a5  js      loc_180016A98
0x1800169ab  mov     rcx, rsi; this
0x1800169ae  call    ?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_UpdateOverlayRegion(void)
0x1800169b3  mov     ebx, eax
0x1800169b5  test    eax, eax
0x1800169b7  js      loc_180016A98
0x1800169bd  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, r12b
0x1800169c4  jz      short loc_1800169D0
0x1800169c6  mov     r8, [rsp+200h+var_1A8]
0x1800169cb  call    McTemplateU0p_EventWriteTransfer
0x1800169d0  mov     rcx, [rsp+200h+var_1A0]
0x1800169d5  mov     eax, [rsi+30h]
0x1800169d8  mov     [rcx], eax
0x1800169da  test    byte ptr [rdi], 2
0x1800169dd  jz      loc_180016B04
0x1800169e3  mov     rdx, rdi; struct CLightDismissClientStore::CLIENT_INFO *
0x1800169e6  mov     rcx, rsi; this
0x1800169e9  call    ?_HandleNewFocusLostObject@CLightDismissClientStore@@AEAAXPEAUCLIENT_INFO@1@@Z; CLightDismissClientStore::_HandleNewFocusLostObject(CLightDismissClientStore::CLIENT_INFO *)
0x1800169ee  jmp     loc_180016B04
0x1800169f3  mov     r8d, [rsp+200h+dwProcessId]; dwProcessId
0x1800169f8  xor     edx, edx; bInheritHandle
0x1800169fa  mov     ecx, 101000h; dwDesiredAccess
0x1800169ff  call    cs:__imp_OpenProcess
0x180016a05  mov     r15, rax
0x180016a08  test    rax, rax
0x180016a0b  jnz     short loc_180016A19
0x180016a0d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016a12  mov     ebx, eax
0x180016a14  jmp     loc_180016991
0x180016a19  mov     r8d, [rsp+200h+dwProcessId]
0x180016a1e  lea     rdx, _anonymous_namespace___WaitCallback
0x180016a25  or      r9d, 0FFFFFFFFh
0x180016a29  mov     [rsp+200h+var_1E0], 18h
0x180016a31  mov     rcx, r15
0x180016a34  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180016a3a  mov     r13, rax
0x180016a3d  test    rax, rax
0x180016a40  jnz     short loc_180016A4B
0x180016a42  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016a47  mov     ebx, eax
0x180016a49  jmp     short loc_180016A87
  ... truncated ...
```
