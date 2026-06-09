# CRemoveDeviceContextHandler::ExecuteRemoveDeviceThreadProc(void *)

- ea: `0x180007a10`
- end: `0x180007f29`
- name: `?ExecuteRemoveDeviceThreadProc@CRemoveDeviceContextHandler@@SAKPEAX@Z`
- size: `1305`
- prototype: `__int64 __fastcall(char *lpThreadParameter, __int64, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001be0`
- `0x18000570c`
- `0x180005d1c`
- `0x180005ea4`
- `0x180006ee0`
- `0x180006fd8`
- `0x180007434`
- `0x180007a10`
- `0x180008750`
- `0x18000a3c4`
- `0x18000ae3c`
- `0x18000b514`
- `0x18000b968`
- `0x18000bbd0`
- `0x18000bcf4`
- `0x18000bdec`
- `0x18000be60`
- `0x18000c966`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180007ac6`
- `SHELL32!SHCreateItemFromIDList` at `0x180007ac6`
- `SHELL32!__imp_SHRestricted` at `0x180007b01`
- `SHELL32!__imp_SHRestricted` at `0x180007b01`
- `SHELL32!__imp_ILFree` at `0x180007e75`
- `SHELL32!__imp_ILFree` at `0x180007e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ea9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007eb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007eb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e33`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007a97`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007a97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007e90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007e90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007bf0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007bf0`
- `ole32!CoAllowSetForegroundWindow` at `0x180007ce5`
- `ole32!CoAllowSetForegroundWindow` at `0x180007ce5`
- `PROPSYS!PropVariantToString` at `0x180007ba8`
- `PROPSYS!PropVariantToString` at `0x180007ba8`
- `USER32!DestroyIcon` at `0x180007e6b`
- `USER32!DestroyIcon` at `0x180007e6b`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::ExecuteRemoveDeviceThreadProc(
        char *lpThreadParameter,
        __int64 a2,
        __int64 a3)
{
  int v4; // r15d
  HRESULT v5; // ebx
  const ITEMIDLIST *v6; // rcx
  HRESULT v7; // eax
  __int64 v8; // r8
  __int64 v9; // rsi
  HRESULT v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  HRESULT v13; // eax
  __int64 v14; // r8
  const struct _GUID *v15; // rdx
  const struct _GUID *v16; // r8
  HWND v17; // rcx
  __int64 *v18; // rsi
  int v19; // eax
  __int64 v20; // r8
  HRESULT InstanceAsAdmin; // eax
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  HICON v28; // rcx
  void *v29; // rbx
  HANDLE ProcessHeap; // rax
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *pUnk; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v35; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT propvar; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+94h] [rbp-6Ch]
  HINSTANCE v40; // [rsp+9Ch] [rbp-64h]
  int v41; // [rsp+A4h] [rbp-5Ch]
  int v42; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+ACh] [rbp-54h]
  __int64 v44; // [rsp+B4h] [rbp-4Ch]
  __int64 v45; // [rsp+BCh] [rbp-44h]
  LARGE_INTEGER hVal; // [rsp+C4h] [rbp-3Ch]
  int v47; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v48[16]; // [rsp+130h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+140h] [rbp+40h]
  char v50; // [rsp+148h] [rbp+48h]
  _BYTE v51[48]; // [rsp+150h] [rbp+50h] BYREF
  __int64 psz[10]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, lpThreadParameter);
  if ( lpThreadParameter && *((_QWORD *)lpThreadParameter + 1) )
  {
    wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
      (__int64)(lpThreadParameter + 24),
      (__int64)v48);
    v4 = 0;
    v5 = CoInitializeEx(0, 2u);
    if ( v5 < 0 )
    {
LABEL_48:
      v27 = 0;
      if ( v5 != -2147023673 )
        v27 = (unsigned int)v5;
      wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        lpThreadParameter + 24,
        v27);
      v28 = (HICON)*((_QWORD *)lpThreadParameter + 2);
      if ( v28 )
        DestroyIcon(v28);
      ILFree(*((LPITEMIDLIST *)lpThreadParameter + 1));
      DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)(lpThreadParameter + 24));
      operator delete(lpThreadParameter);
      if ( v4 )
        CoUninitialize();
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v51);
      if ( v50 )
      {
        v29 = lpMem;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v29);
        v50 = 0;
      }
      lpMem = 0;
      goto LABEL_57;
    }
    v6 = (const ITEMIDLIST *)*((_QWORD *)lpThreadParameter + 1);
    ppv = 0;
    v4 = 1;
    v7 = SHCreateItemFromIDList(v6, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x174, v8, (const char *)(unsigned int)v7);
      goto LABEL_46;
    }
    if ( (unsigned int)IsPrinterSI((struct IShellItem2 *)ppv) )
    {
      v9 = *(_QWORD *)lpThreadParameter;
      if ( SHRestricted(REST_NOPRINTERDELETE) )
      {
        IsolationAwareTaskDialog(v9);
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveRestricted((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)(lpThreadParameter + 24));
        goto LABEL_46;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
    memset(&propvar, 0, sizeof(propvar));
    v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
            ppv,
            &PKEY_Device_ContainerId,
            &propvar);
    v5 = v10;
    if ( v10 >= 0 )
    {
      if ( propvar.vt != 72 )
        goto LABEL_45;
      v10 = PropVariantToString(&propvar, (PWSTR)psz, 0x28u);
      v5 = v10;
      if ( v10 >= 0 )
      {
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveTargetDetermined<unsigned short (&)[40]>(
          (__int64)(lpThreadParameter + 24),
          psz);
        v35 = 0;
        v13 = CoCreateInstance(
                &GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8,
                0,
                1u,
                &GUID_46147e3d_0380_450d_b48e_cca7f77d1c69,
                &v35);
        v5 = v13;
        if ( v13 >= 0 )
        {
          v33 = 0;
          if ( (*(int (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v35 + 72LL))(v35, psz, &v33) >= 0 )
          {
            v17 = *(HWND *)lpThreadParameter;
            if ( (v33 & 1) != 0 )
            {
              v18 = (__int64 *)(lpThreadParameter + 16);
              v5 = ConfirmUninstall(v17, (struct IShellItem2 *)ppv, *((HICON *)lpThreadParameter + 2));
              if ( v5 < 0 )
              {
                DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::UserCancelled((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)(lpThreadParameter + 24));
              }
              else
              {
                v19 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v35 + 80LL))(v35, psz);
                v5 = v19;
                if ( v19 < 0 )
                  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x195, v20, (const char *)(unsigned int)v19);
              }
            }
            else
            {
              pUnk = 0;
              InstanceAsAdmin = CoCreateInstanceAsAdmin(v17, v15, v16, (void **)&pUnk);
              v5 = InstanceAsAdmin;
              if ( InstanceAsAdmin >= 0 )
              {
                CoAllowSetForegroundWindow(pUnk, 0);
                v18 = (__int64 *)(lpThreadParameter + 16);
                v23 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, void *, _QWORD, __int64 *))pUnk->lpVtbl[1].QueryInterface)(
                        pUnk,
                        *(_QWORD *)lpThreadParameter,
                        ppv,
                        *((_QWORD *)lpThreadParameter + 2),
                        psz);
                v5 = v23;
                if ( v23 < 0 )
                  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x1A5, v24, (const char *)(unsigned int)v23);
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1A1,
                  v22,
                  (const char *)(unsigned int)InstanceAsAdmin);
                v18 = (__int64 *)(lpThreadParameter + 16);
              }
              if ( pUnk )
                ((void (__fastcall *)(IUnknown *))pUnk->lpVtbl->Release)(pUnk);
            }
            if ( v5 == -2147024891 )
            {
              memset_0(&v38, 0, 0xA0u);
              v25 = *v18;
              v39 = *(_QWORD *)lpThreadParameter;
              v40 = g_hinst;
              v26 = v41;
              v44 = v25;
              if ( v25 )
                v26 = 2;
              v38 = 160;
              v41 = v26;
              v42 = 1;
              v47 = 200;
              v43 = 1001;
              v45 = 1010;
              memset(&pvar, 0, sizeof(pvar));
              if ( (*(int (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
                     ppv,
                     &PKEY_NAME,
                     &pvar) >= 0
                && pvar.vt == 31 )
              {
                hVal = pvar.hVal;
              }
              else
              {
                hVal.QuadPart = 1004;
              }
              IsolationAwareTaskDialogIndirect(&v38, 0);
              PropVariantClear(&pvar);
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x18A, v14, (const char *)(unsigned int)v13);
        }
        if ( v35 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
        goto LABEL_45;
      }
      v12 = 388;
    }
    else
    {
      v12 = 383;
    }
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)v12, v11, (const char *)(unsigned int)v10);
LABEL_45:
    PropVariantClear(&propvar);
LABEL_46:
    if ( ppv )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_48;
  }
LABEL_57:
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22);
  return 0;
}

```

## disassembly

```asm
0x180007a10  mov     [rsp-8+arg_8], rbx
0x180007a15  mov     [rsp-8+arg_10], rsi
0x180007a1a  push    rbp
0x180007a1b  push    rdi
0x180007a1c  push    r12
0x180007a1e  push    r14
0x180007a20  push    r15
0x180007a22  lea     rbp, [rsp-0E0h]
0x180007a2a  sub     rsp, 1E0h
0x180007a31  mov     rax, cs:__security_cookie
0x180007a38  xor     rax, rsp
0x180007a3b  mov     [rbp+100h+var_30], rax
0x180007a42  mov     rdi, rcx
0x180007a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a4c  lea     r12, WPP_GLOBAL_Control
0x180007a53  cmp     rcx, r12
0x180007a56  jz      short loc_180007A6A
0x180007a58  test    byte ptr [rcx+1Ch], 20h
0x180007a5c  jz      short loc_180007A6A
0x180007a5e  mov     rcx, [rcx+10h]
0x180007a62  mov     r9, rdi
0x180007a65  call    WPP_SF_q
0x180007a6a  test    rdi, rdi
0x180007a6d  jz      loc_180007EC9
0x180007a73  cmp     qword ptr [rdi+8], 0
0x180007a78  jz      loc_180007EC9
0x180007a7e  lea     r14, [rdi+18h]
0x180007a82  mov     rcx, r14
0x180007a85  lea     rdx, [rbp+100h+var_D0]
0x180007a89  call    ?ContinueOnCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180007a8e  xor     r15d, r15d
0x180007a91  xor     ecx, ecx; pvReserved
0x180007a93  lea     edx, [r15+2]; dwCoInit
0x180007a97  call    cs:__imp_CoInitializeEx
0x180007a9d  mov     ebx, eax
0x180007a9f  test    eax, eax
0x180007aa1  js      loc_180007E4F
0x180007aa7  mov     rcx, [rdi+8]; pidl
0x180007aab  lea     r8, [rsp+200h+ppv]; ppv
0x180007ab0  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180007ab7  mov     [rsp+200h+ppv], 0
0x180007ac0  mov     r15d, 1
0x180007ac6  call    cs:__imp_SHCreateItemFromIDList
0x180007acc  mov     ebx, eax
0x180007ace  test    eax, eax
0x180007ad0  jns     short loc_180007AEB
0x180007ad2  mov     rcx, [rbp+108h]; this
0x180007ad9  mov     r9d, eax; char *
0x180007adc  mov     edx, 174h; void *
0x180007ae1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007ae6  jmp     loc_180007E39
0x180007aeb  mov     rcx, [rsp+200h+ppv]; struct IShellItem2 *
0x180007af0  call    ?IsPrinterSI@@YAHPEAUIShellItem2@@@Z; IsPrinterSI(IShellItem2 *)
0x180007af5  test    eax, eax
0x180007af7  jz      short loc_180007B20
0x180007af9  mov     rsi, [rdi]
0x180007afc  mov     ecx, 8000h; rest
0x180007b01  call    cs:__imp_SHRestricted
0x180007b07  test    eax, eax
0x180007b09  jz      short loc_180007B20
0x180007b0b  mov     rcx, rsi
0x180007b0e  call    IsolationAwareTaskDialog
0x180007b13  mov     rcx, r14; this
0x180007b16  call    ?RemoveRestricted@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveRestricted(void)
0x180007b1b  jmp     loc_180007E39
0x180007b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b27  cmp     rcx, r12
0x180007b2a  jz      short loc_180007B40
0x180007b2c  test    byte ptr [rcx+1Ch], 8
0x180007b30  jz      short loc_180007B40
0x180007b32  mov     rcx, [rcx+10h]
0x180007b36  mov     edx, 15h
0x180007b3b  call    WPP_SF_
0x180007b40  mov     rcx, [rsp+200h+ppv]
0x180007b45  lea     r8, [rsp+200h+propvar]
0x180007b4a  xor     eax, eax
0x180007b4c  lea     rdx, PKEY_Device_ContainerId
0x180007b53  mov     qword ptr [rbp+100h+propvar+10h], rax
0x180007b57  xorps   xmm0, xmm0
0x180007b5a  movups  xmmword ptr [rsp+200h+propvar], xmm0
0x180007b5f  mov     rax, [rcx]
0x180007b62  mov     rax, [rax+68h]
0x180007b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b6b  mov     ebx, eax
0x180007b6d  test    eax, eax
0x180007b6f  jns     short loc_180007B8A
0x180007b71  mov     edx, 17Fh; void *
0x180007b76  mov     rcx, [rbp+108h]; this
0x180007b7d  mov     r9d, eax; char *
0x180007b80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007b85  jmp     loc_180007E2E
0x180007b8a  cmp     word ptr [rsp+200h+propvar], 48h ; 'H'
0x180007b90  jnz     loc_180007E2E
0x180007b96  mov     r8d, 28h ; '('; cch
0x180007b9c  lea     rdx, [rbp+100h+psz]; psz
0x180007ba3  lea     rcx, [rsp+200h+propvar]; propvar
0x180007ba8  call    cs:__imp_PropVariantToString
0x180007bae  mov     ebx, eax
0x180007bb0  test    eax, eax
0x180007bb2  jns     short loc_180007BBB
0x180007bb4  mov     edx, 184h
0x180007bb9  jmp     short loc_180007B76
0x180007bbb  lea     rdx, [rbp+100h+psz]
0x180007bc2  mov     rcx, r14
0x180007bc5  call    ??$RemoveTargetDetermined@AEAY0CI@G@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXAEAY0CI@G@Z; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveTargetDetermined<ushort (&)[40]>(ushort (&)[40])
0x180007bca  lea     rax, [rsp+200h+var_1A8]
0x180007bcf  mov     [rsp+200h+var_1A8], 0
0x180007bd8  lea     r9, _GUID_46147e3d_0380_450d_b48e_cca7f77d1c69; riid
0x180007bdf  mov     [rsp+200h+var_1E0], rax; int
0x180007be4  mov     r8d, r15d; dwClsContext
0x180007be7  lea     rcx, _GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8; rclsid
0x180007bee  xor     edx, edx; pUnkOuter
0x180007bf0  call    cs:__imp_CoCreateInstance
0x180007bf6  mov     ebx, eax
0x180007bf8  test    eax, eax
0x180007bfa  jns     short loc_180007C15
0x180007bfc  mov     rcx, [rbp+108h]; this
0x180007c03  mov     r9d, eax; char *
0x180007c06  mov     edx, 18Ah; void *
0x180007c0b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007c10  jmp     loc_180007E18
0x180007c15  mov     rcx, [rsp+200h+var_1A8]
0x180007c1a  lea     r8, [rsp+200h+var_1B8]
0x180007c1f  mov     [rsp+200h+var_1B8], 0
0x180007c27  lea     rdx, [rbp+100h+psz]
0x180007c2e  mov     rax, [rcx]
0x180007c31  mov     rax, [rax+48h]
0x180007c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3a  test    eax, eax
0x180007c3c  js      loc_180007E18
0x180007c42  mov     rcx, [rdi]; HWND
0x180007c45  test    byte ptr [rsp+200h+var_1B8], r15b
0x180007c4a  jz      short loc_180007CAB
0x180007c4c  mov     rdx, [rsp+200h+ppv]; struct IShellItem2 *
0x180007c51  lea     rsi, [rdi+10h]
0x180007c55  mov     r8, [rsi]; HICON
0x180007c58  call    ?ConfirmUninstall@@YAJPEAUHWND__@@PEAUIShellItem2@@PEAUHICON__@@@Z; ConfirmUninstall(HWND__ *,IShellItem2 *,HICON__ *)
0x180007c5d  mov     ebx, eax
0x180007c5f  test    eax, eax
0x180007c61  js      short loc_180007C9E
0x180007c63  mov     rcx, [rsp+200h+var_1A8]
0x180007c68  lea     rdx, [rbp+100h+psz]
0x180007c6f  mov     rax, [rcx]
0x180007c72  mov     rax, [rax+50h]
0x180007c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7b  mov     ebx, eax
0x180007c7d  test    eax, eax
0x180007c7f  jns     loc_180007D47
0x180007c85  mov     rcx, [rbp+108h]; this
0x180007c8c  mov     r9d, eax; char *
0x180007c8f  mov     edx, 195h; void *
0x180007c94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007c99  jmp     loc_180007D47
0x180007c9e  mov     rcx, r14; this
0x180007ca1  call    ?UserCancelled@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::UserCancelled(void)
0x180007ca6  jmp     loc_180007D47
0x180007cab  lea     r9, [rsp+200h+pUnk]; void **
0x180007cb0  mov     [rsp+200h+pUnk], 0
0x180007cb9  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180007cbe  mov     ebx, eax
0x180007cc0  test    eax, eax
0x180007cc2  jns     short loc_180007CDE
0x180007cc4  mov     rcx, [rbp+108h]; this
0x180007ccb  mov     r9d, eax; char *
0x180007cce  mov     edx, 1A1h; void *
0x180007cd3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007cd8  lea     rsi, [rdi+10h]
0x180007cdc  jmp     short loc_180007D31
0x180007cde  mov     rcx, [rsp+200h+pUnk]; pUnk
0x180007ce3  xor     edx, edx; lpvReserved
0x180007ce5  call    cs:__imp_CoAllowSetForegroundWindow
0x180007ceb  mov     rcx, [rsp+200h+pUnk]
0x180007cf0  lea     rdx, [rbp+100h+psz]
0x180007cf7  mov     r8, [rsp+200h+ppv]
0x180007cfc  lea     rsi, [rdi+10h]
0x180007d00  mov     r9, [rsi]
0x180007d03  mov     [rsp+200h+var_1E0], rdx; int
0x180007d08  mov     rax, [rcx]
0x180007d0b  mov     rdx, [rdi]
0x180007d0e  mov     rax, [rax+18h]
0x180007d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d17  mov     ebx, eax
0x180007d19  test    eax, eax
0x180007d1b  jns     short loc_180007D31
0x180007d1d  mov     rcx, [rbp+108h]; this
0x180007d24  mov     r9d, eax; char *
0x180007d27  mov     edx, 1A5h; void *
0x180007d2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007d31  mov     rcx, [rsp+200h+pUnk]
0x180007d36  test    rcx, rcx
0x180007d39  jz      short loc_180007D47
0x180007d3b  mov     rax, [rcx]
0x180007d3e  mov     rax, [rax+10h]
0x180007d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d47  cmp     ebx, 80070005h
0x180007d4d  jnz     loc_180007E18
0x180007d53  mov     r12d, 0A0h
0x180007d59  lea     rcx, [rbp+100h+var_170]; void *
0x180007d5d  mov     r8d, r12d; Size
0x180007d60  xor     edx, edx; Val
0x180007d62  call    memset_0
0x180007d67  mov     rcx, [rsi]
0x180007d6a  lea     r8, [rsp+200h+pvar]
0x180007d6f  mov     rax, [rdi]
0x180007d72  lea     rdx, PKEY_NAME
0x180007d79  mov     [rbp+100h+var_16C], rax
0x180007d7d  test    rcx, rcx
0x180007d80  mov     rax, cs:g_hinst
0x180007d87  xorps   xmm0, xmm0
0x180007d8a  mov     [rbp+100h+var_164], rax
0x180007d8e  mov     eax, [rbp+100h+var_15C]
0x180007d91  mov     [rbp+100h+var_14C], rcx
0x180007d95  mov     ecx, 2
0x180007d9a  cmovnz  eax, ecx
0x180007d9d  mov     [rbp+100h+var_170], r12d
0x180007da1  mov     rcx, [rsp+200h+ppv]
0x180007da6  mov     [rbp+100h+var_15C], eax
0x180007da9  xor     eax, eax
0x180007dab  mov     qword ptr [rsp+200h+pvar+10h], rax
0x180007db0  mov     [rbp+100h+var_158], r15d
0x180007db4  mov     [rbp+100h+var_D4], 0C8h
0x180007dbb  mov     [rbp+100h+var_154], 3E9h
0x180007dc3  mov     [rbp+100h+var_144], 3F2h
0x180007dcb  movups  xmmword ptr [rsp+200h+pvar], xmm0
0x180007dd0  mov     rax, [rcx]
0x180007dd3  mov     rax, [rax+68h]
0x180007dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ddc  test    eax, eax
0x180007dde  js      short loc_180007DF3
0x180007de0  cmp     word ptr [rsp+200h+pvar], 1Fh
0x180007de6  jnz     short loc_180007DF3
0x180007de8  mov     rax, qword ptr [rsp+200h+pvar+8]
0x180007ded  mov     [rbp+100h+var_13C], rax
0x180007df1  jmp     short loc_180007DFB
0x180007df3  mov     [rbp+100h+var_13C], 3ECh
0x180007dfb  xor     edx, edx
0x180007dfd  lea     rcx, [rbp+100h+var_170]
0x180007e01  call    IsolationAwareTaskDialogIndirect
0x180007e06  lea     rcx, [rsp+200h+pvar]; pvar
0x180007e0b  call    cs:__imp_PropVariantClear
0x180007e11  lea     r12, WPP_GLOBAL_Control
0x180007e18  mov     rcx, [rsp+200h+var_1A8]
0x180007e1d  test    rcx, rcx
0x180007e20  jz      short loc_180007E2E
0x180007e22  mov     rax, [rcx]
0x180007e25  mov     rax, [rax+10h]
0x180007e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2e  lea     rcx, [rsp+200h+propvar]; pvar
0x180007e33  call    cs:__imp_PropVariantClear
0x180007e39  mov     rcx, [rsp+200h+ppv]
0x180007e3e  test    rcx, rcx
0x180007e41  jz      short loc_180007E4F
0x180007e43  mov     rax, [rcx]
0x180007e46  mov     rax, [rax+10h]
0x180007e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4f  xor     edx, edx
0x180007e51  mov     rcx, r14
0x180007e54  cmp     ebx, 800704C7h
0x180007e5a  cmovnz  edx, ebx
0x180007e5d  call    ?Stop@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180007e62  mov     rcx, [rdi+10h]; hIcon
0x180007e66  test    rcx, rcx
0x180007e69  jz      short loc_180007E71
0x180007e6b  call    cs:__imp_DestroyIcon
0x180007e71  mov     rcx, [rdi+8]; pidl
0x180007e75  call    cs:__imp_ILFree
0x180007e7b  mov     rcx, r14; this
0x180007e7e  call    ??1RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAA@XZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(void)
0x180007e83  mov     rcx, rdi; Block
0x180007e86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e8b  test    r15d, r15d
0x180007e8e  jz      short loc_180007E96
0x180007e90  call    cs:__imp_CoUninitialize
0x180007e96  lea     rcx, [rbp+100h+var_B0]; this
0x180007e9a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180007e9f  cmp     [rbp+100h+var_B8], 0
0x180007ea3  jz      short loc_180007EC1
0x180007ea5  mov     rbx, [rbp+100h+lpMem]
0x180007ea9  call    cs:__imp_GetProcessHeap
0x180007eaf  mov     r8, rbx; lpMem
0x180007eb2  xor     edx, edx; dwFlags
0x180007eb4  mov     rcx, rax; hHeap
0x180007eb7  call    cs:__imp_HeapFree
0x180007ebd  mov     [rbp+100h+var_B8], 0
0x180007ec1  mov     [rbp+100h+lpMem], 0
0x180007ec9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ed0  mov     rax, [rcx]
0x180007ed3  mov     rax, [rax+10h]
0x180007ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ee3  cmp     rcx, r12
0x180007ee6  jz      short loc_180007EFC
0x180007ee8  test    byte ptr [rcx+1Ch], 20h
0x180007eec  jz      short loc_180007EFC
0x180007eee  mov     rcx, [rcx+10h]
0x180007ef2  mov     edx, 16h
0x180007ef7  call    WPP_SF_
0x180007efc  xor     eax, eax
0x180007efe  mov     rcx, [rbp+100h+var_30]
0x180007f05  xor     rcx, rsp; StackCookie
  ... truncated ...
```
