# ConnectCallback(tagComCallData *)

- ea: `0x180038040`
- end: `0x1800382f5`
- name: `?ConnectCallback@@YAJPEAUtagComCallData@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008c2c`
- `0x18002e81c`
- `0x180038040`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800382b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800382b8`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180038291`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180038291`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180038145`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180038251`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180038145`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180038251`

## string_xrefs

- `0x180038058`: `COM connect callback received`
- `0x180038226`: `QI failed on the remediation agent factory. hr = 0x%08x`
- `0x180038117`: `QI failed on the WaaS Protected Settings agent factory. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConnectCallback(struct tagComCallData *a1)
{
  _QWORD *v1; // rax
  __int64 v2; // rcx
  const unsigned __int16 *v3; // rdx
  HRESULT v4; // ebx
  HRESULT v5; // eax
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  LPUNKNOWN v12; // [rsp+48h] [rbp+10h] BYREF
  LPUNKNOWN pUnk; // [rsp+50h] [rbp+18h] BYREF
  _QWORD *v14; // [rsp+58h] [rbp+20h]

  pUnk = 0;
  v12 = 0;
  LogLevelW(5u, L"COM connect callback received");
  v1 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v1;
  if ( v1 )
  {
    *v1 = &WaaSProtectedSettingsProviderClassFactory::`vftable';
    v1[1] = 0;
  }
  v2 = qword_1800A5AD0;
  qword_1800A5AD0 = (__int64)v1;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 40LL))(v2, 1);
    v1 = (_QWORD *)qword_1800A5AD0;
  }
  (*(void (__fastcall **)(_QWORD *))(*v1 + 8LL))(v1);
  if ( !qword_1800A5AD0 )
  {
    v3 = L"Failed to allocate WaaSProtectedSettingsProvider class factory";
LABEL_7:
    v4 = -2147024882;
    LogLevelW(2u, v3);
    goto LABEL_29;
  }
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))qword_1800A5AD0)(
         qword_1800A5AD0,
         &IID_IClassFactory,
         &pUnk);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = L"QI failed on the WaaS Protected Settings agent factory. hr = 0x%08x";
LABEL_28:
    LogLevelW(2u, v6, (unsigned int)v5);
    goto LABEL_29;
  }
  v4 = CoRegisterClassObject(&CLSID_WaaSProtectedSettingsProvider, pUnk, 4u, 5u, &dwRegister);
  if ( v4 >= 0 )
  {
    v8 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = &WaaSRemediationClassFactory::`vftable';
      v8[2] = 0;
    }
    v9 = qword_1800A5AC8;
    qword_1800A5AC8 = (__int64)v8;
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 40LL))(v9, 1);
      v8 = (_DWORD *)qword_1800A5AC8;
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( !qword_1800A5AC8 )
    {
      v3 = L"Failed to allocate WaaS remediation class factory";
      goto LABEL_7;
    }
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))qword_1800A5AC8)(
           qword_1800A5AC8,
           &IID_IClassFactory,
           &v12);
    v4 = v5;
    if ( v5 < 0 )
    {
      v6 = L"QI failed on the remediation agent factory. hr = 0x%08x";
      goto LABEL_28;
    }
    v4 = CoRegisterClassObject(&CLSID_WaaSRemediationAgent, v12, 4u, 5u, &dword_1800A568C);
    if ( v4 >= 0 )
    {
      v5 = CoResumeClassObjects();
      v4 = v5;
      if ( v5 >= 0 )
        goto LABEL_29;
      v6 = L"Failed to resume class objects. hr = 0x%08x";
      goto LABEL_28;
    }
    v10 = qword_1800A5AC8;
    qword_1800A5AC8 = 0;
    if ( v10 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 40LL))(v10, 1);
    LogLevelW(2u, L"Failed to register remediation class object. hr = 0x%08x", (unsigned int)v4);
  }
  else
  {
    v7 = qword_1800A5AD0;
    qword_1800A5AD0 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
    LogLevelW(2u, L"Failed to register WaaSProtectedSettingsProvder class object. hr = 0x%08x", (unsigned int)v4);
  }
LABEL_29:
  SetEvent(hEvent);
  if ( v12 )
    ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038040  push    rbx
0x180038042  sub     rsp, 30h
0x180038046  mov     [rsp+38h+pUnk], 0
0x18003804f  mov     [rsp+38h+arg_8], 0
0x180038058  lea     rdx, aComConnectCall; "COM connect callback received"
0x18003805f  mov     ecx, 5; unsigned __int8
0x180038064  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038069  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038070  mov     ecx, 10h; unsigned __int64
0x180038075  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003807a  mov     [rsp+38h+arg_18], rax
0x18003807f  test    rax, rax
0x180038082  jz      short loc_180038096
0x180038084  lea     rcx, ??_7WaaSProtectedSettingsProviderClassFactory@@6B@; const WaaSProtectedSettingsProviderClassFactory::`vftable'
0x18003808b  mov     [rax], rcx
0x18003808e  mov     qword ptr [rax+8], 0
0x180038096  mov     rcx, cs:qword_1800A5AD0
0x18003809d  mov     cs:qword_1800A5AD0, rax
0x1800380a4  test    rcx, rcx
0x1800380a7  jz      short loc_1800380C1
0x1800380a9  mov     rax, [rcx]
0x1800380ac  mov     edx, 1
0x1800380b1  mov     rax, [rax+28h]
0x1800380b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380ba  mov     rax, cs:qword_1800A5AD0
0x1800380c1  mov     rcx, [rax]
0x1800380c4  mov     rdx, [rcx+8]
0x1800380c8  mov     rcx, rax
0x1800380cb  mov     rax, rdx
0x1800380ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380d3  mov     rcx, cs:qword_1800A5AD0
0x1800380da  test    rcx, rcx
0x1800380dd  jnz     short loc_1800380FA
0x1800380df  lea     rdx, aFailedToAlloca_16; "Failed to allocate WaaSProtectedSetting"...
0x1800380e6  mov     ebx, 8007000Eh
0x1800380eb  mov     ecx, 2; unsigned __int8
0x1800380f0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800380f5  jmp     loc_1800382B1
0x1800380fa  mov     rax, [rcx]
0x1800380fd  lea     r8, [rsp+38h+pUnk]
0x180038102  lea     rdx, IID_IClassFactory
0x180038109  mov     rax, [rax]
0x18003810c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038111  mov     ebx, eax
0x180038113  test    eax, eax
0x180038115  jns     short loc_180038123
0x180038117  lea     rdx, aQiFailedOnTheW; "QI failed on the WaaS Protected Setting"...
0x18003811e  jmp     loc_1800382A4
0x180038123  lea     rax, dwRegister
0x18003812a  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x18003812f  mov     r9d, 5; flags
0x180038135  lea     r8d, [r9-1]; dwClsContext
0x180038139  mov     rdx, [rsp+38h+pUnk]; pUnk
0x18003813e  lea     rcx, CLSID_WaaSProtectedSettingsProvider; rclsid
0x180038145  call    cs:__imp_CoRegisterClassObject
0x18003814b  mov     ebx, eax
0x18003814d  test    eax, eax
0x18003814f  jns     short loc_180038188
0x180038151  mov     rcx, cs:qword_1800A5AD0
0x180038158  mov     cs:qword_1800A5AD0, 0
0x180038163  test    rcx, rcx
0x180038166  jz      short loc_180038179
0x180038168  mov     rax, [rcx]
0x18003816b  mov     edx, 1
0x180038170  mov     rax, [rax+28h]
0x180038174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038179  mov     r8d, ebx
0x18003817c  lea     rdx, aFailedToRegist; "Failed to register WaaSProtectedSetting"...
0x180038183  jmp     loc_1800382A7
0x180038188  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003818f  mov     ecx, 10h; unsigned __int64
0x180038194  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038199  mov     [rsp+38h+arg_18], rax
0x18003819e  test    rax, rax
0x1800381a1  jz      short loc_1800381B4
0x1800381a3  lea     rcx, ??_7WaaSRemediationClassFactory@@6B@; const WaaSRemediationClassFactory::`vftable'
0x1800381aa  mov     [rax], rcx
0x1800381ad  mov     dword ptr [rax+8], 0
0x1800381b4  mov     rcx, cs:qword_1800A5AC8
0x1800381bb  mov     cs:qword_1800A5AC8, rax
0x1800381c2  test    rcx, rcx
0x1800381c5  jz      short loc_1800381DF
0x1800381c7  mov     rax, [rcx]
0x1800381ca  mov     edx, 1
0x1800381cf  mov     rax, [rax+28h]
0x1800381d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381d8  mov     rax, cs:qword_1800A5AC8
0x1800381df  mov     rcx, [rax]
0x1800381e2  mov     rdx, [rcx+8]
0x1800381e6  mov     rcx, rax
0x1800381e9  mov     rax, rdx
0x1800381ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381f1  mov     rcx, cs:qword_1800A5AC8
0x1800381f8  test    rcx, rcx
0x1800381fb  jnz     short loc_180038209
0x1800381fd  lea     rdx, aFailedToAlloca_20; "Failed to allocate WaaS remediation cla"...
0x180038204  jmp     loc_1800380E6
0x180038209  mov     rax, [rcx]
0x18003820c  lea     r8, [rsp+38h+arg_8]
0x180038211  lea     rdx, IID_IClassFactory
0x180038218  mov     rax, [rax]
0x18003821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038220  mov     ebx, eax
0x180038222  test    eax, eax
0x180038224  jns     short loc_18003822F
0x180038226  lea     rdx, aQiFailedOnTheR; "QI failed on the remediation agent fact"...
0x18003822d  jmp     short loc_1800382A4
0x18003822f  lea     rax, dword_1800A568C
0x180038236  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x18003823b  mov     r9d, 5; flags
0x180038241  lea     r8d, [r9-1]; dwClsContext
0x180038245  mov     rdx, [rsp+38h+arg_8]; pUnk
0x18003824a  lea     rcx, CLSID_WaaSRemediationAgent; rclsid
0x180038251  call    cs:__imp_CoRegisterClassObject
0x180038257  mov     ebx, eax
0x180038259  test    eax, eax
0x18003825b  jns     short loc_180038291
0x18003825d  mov     rcx, cs:qword_1800A5AC8
0x180038264  mov     cs:qword_1800A5AC8, 0
0x18003826f  test    rcx, rcx
0x180038272  jz      short loc_180038285
0x180038274  mov     rax, [rcx]
0x180038277  mov     edx, 1
0x18003827c  mov     rax, [rax+28h]
0x180038280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038285  mov     r8d, ebx
0x180038288  lea     rdx, aFailedToRegist_1; "Failed to register remediation class ob"...
0x18003828f  jmp     short loc_1800382A7
0x180038291  call    cs:__imp_CoResumeClassObjects
0x180038297  mov     ebx, eax
0x180038299  test    eax, eax
0x18003829b  jns     short loc_1800382B1
0x18003829d  lea     rdx, aFailedToResume; "Failed to resume class objects. hr = 0x"...
0x1800382a4  mov     r8d, eax
0x1800382a7  mov     ecx, 2; unsigned __int8
0x1800382ac  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800382b1  mov     rcx, cs:hEvent; hEvent
0x1800382b8  call    cs:__imp_SetEvent
0x1800382be  nop
0x1800382bf  mov     rcx, [rsp+38h+arg_8]
0x1800382c4  test    rcx, rcx
0x1800382c7  jz      short loc_1800382D6
0x1800382c9  mov     rax, [rcx]
0x1800382cc  mov     rax, [rax+10h]
0x1800382d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382d5  nop
0x1800382d6  mov     rcx, [rsp+38h+pUnk]
0x1800382db  test    rcx, rcx
0x1800382de  jz      short loc_1800382ED
0x1800382e0  mov     rax, [rcx]
0x1800382e3  mov     rax, [rax+10h]
0x1800382e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382ec  nop
0x1800382ed  mov     eax, ebx
0x1800382ef  add     rsp, 30h
0x1800382f3  pop     rbx
0x1800382f4  retn
```
