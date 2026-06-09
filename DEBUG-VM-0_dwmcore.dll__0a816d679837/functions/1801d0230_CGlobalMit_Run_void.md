# CGlobalMit::Run(void)

- ea: `0x1801d0230`
- end: `0x1801d0552`
- name: `?Run@CGlobalMit@@MEAAKXZ`
- size: `802`
- prototype: `unsigned int __fastcall(CGlobalMit *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008934`
- `0x180009d98`
- `0x180042de0`
- `0x1800d5880`
- `0x1801d0230`
- `0x1801d0558`
- `0x180228860`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801d03ac`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801d03ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d0246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d0246`
- `win32u!NtMITDeactivateInputProcessing` at `0x1801d0414`
- `win32u!NtMITDeactivateInputProcessing` at `0x1801d0414`
- `win32u!NtMITActivateInputProcessing` at `0x1801d034a`
- `win32u!NtMITActivateInputProcessing` at `0x1801d034a`
- `CoreMessaging!CoreUICreateEx` at `0x1801d0297`
- `CoreMessaging!CoreUICreateEx` at `0x1801d0297`
- `ext-ms-win-mininput-systeminputhost-l1-2-0!CreateSystemInputHost` at `0x1801d0313`
- `ext-ms-win-mininput-systeminputhost-l1-2-0!CreateSystemInputHost` at `0x1801d0313`
- `ext-ms-win-ntuser-mit-l1-1-0!MITGetCursorUpdateHandle` at `0x1801d0323`
- `ext-ms-win-ntuser-mit-l1-1-0!MITGetCursorUpdateHandle` at `0x1801d0323`

## pseudocode

```c
__int64 __fastcall CGlobalMit::Run(CGlobalMit *this)
{
  _QWORD *v2; // rax
  unsigned int v3; // edi
  int v4; // r9d
  int SystemInputHost; // eax
  __int64 updated; // rax
  __int64 v7; // rbx
  void (*i)(void); // rax
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  int v10; // eax
  void *v11; // rcx
  __int64 result; // rax
  unsigned int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  GetCurrentThreadId();
  v2 = operator new(8u);
  if ( v2 )
    *v2 = &CInputProxy::`vftable';
  else
    v2 = 0;
  *((_QWORD *)this + 5) = v2;
  if ( !v2 )
  {
    v3 = -2147024882;
    v13 = 131;
LABEL_6:
    v4 = v3;
LABEL_29:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180343A78, 2u, v4, v13, 0);
    goto LABEL_30;
  }
  SystemInputHost = CoreUICreateEx(1, &CMit::s_pMessageSession);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 137;
    goto LABEL_28;
  }
  SystemInputHost = (*(__int64 (__fastcall **)(struct IMessageSession *, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), CGlobalMit *))(*(_QWORD *)CMit::s_pMessageSession + 272LL))(
                      CMit::s_pMessageSession,
                      *((_QWORD *)this + 3),
                      CGlobalMit::OnResetEvent,
                      this);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 139;
    goto LABEL_28;
  }
  SystemInputHost = (*(__int64 (__fastcall **)(struct IMessageSession *, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), CGlobalMit *))(*(_QWORD *)CMit::s_pMessageSession + 272LL))(
                      CMit::s_pMessageSession,
                      *((_QWORD *)this + 17),
                      CGlobalMit::OnResetEvent,
                      this);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 140;
    goto LABEL_28;
  }
  SystemInputHost = CreateSystemInputHost(*((_QWORD *)this + 5), 0, &CMit::s_pSystemInputHost);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 145;
LABEL_28:
    v4 = SystemInputHost;
    goto LABEL_29;
  }
  updated = MITGetCursorUpdateHandle();
  if ( updated != -1 )
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 144,
      updated);
  if ( !(unsigned int)NtMITActivateInputProcessing(CGlobalMit::s_HitTestRequest, &v15) )
  {
    v3 = -2147467259;
    v13 = 158;
    goto LABEL_6;
  }
  v7 = v15;
  v3 = 0;
  v14 = 0;
  (*(void (__fastcall **)(struct IMessageSession *, __int64 *))(*(_QWORD *)CMit::s_pMessageSession + 40LL))(
    CMit::s_pMessageSession,
    &v14);
  (*(void (__fastcall **)(__int64, __int64, __int64 (__fastcall *)(void *, void *, void *), _QWORD))(*(_QWORD *)v14 + 64LL))(
    v14,
    v7,
    CGlobalMit::CompletionHandler,
    0);
  for ( i = *(void (**)(void))(*(_QWORD *)v14 + 16LL); ; i = *(void (**)(void))(*(_QWORD *)CMit::s_pMessageSession
                                                                              + 232LL) )
  {
    i();
    if ( *((_BYTE *)this + 32) )
      break;
    ResetEvent(*((HANDLE *)this + 3));
    if ( *((_BYTE *)this + 32) )
      break;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
    if ( *(_BYTE *)(*((_QWORD *)this + 1) + 808LL) )
    {
      v10 = CMmcssTask::Apply(v9, 1);
      if ( v10 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0xF4u, 0);
    }
    else
    {
      CMmcssTask::Revert((CMmcssTask *)v9);
    }
  }
  NtMITDeactivateInputProcessing();
LABEL_30:
  if ( CMit::s_pSystemInputHost )
  {
    (*(void (__fastcall **)(struct ISystemInputHost *))(*(_QWORD *)CMit::s_pSystemInputHost + 16LL))(CMit::s_pSystemInputHost);
    CMit::s_pSystemInputHost = 0;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    operator delete(v11, 8u);
    *((_QWORD *)this + 5) = 0;
  }
  if ( CMit::s_pMessageCallSendHost )
  {
    (*(void (__fastcall **)(struct IMessageCallSendHost *))(*(_QWORD *)CMit::s_pMessageCallSendHost + 16LL))(CMit::s_pMessageCallSendHost);
    CMit::s_pMessageCallSendHost = 0;
  }
  if ( CMit::s_pMessageSession )
  {
    (*(void (__fastcall **)(struct IMessageSession *, _QWORD))(*(_QWORD *)CMit::s_pMessageSession + 280LL))(
      CMit::s_pMessageSession,
      *((_QWORD *)this + 17));
    (*(void (__fastcall **)(struct IMessageSession *, _QWORD))(*(_QWORD *)CMit::s_pMessageSession + 280LL))(
      CMit::s_pMessageSession,
      *((_QWORD *)this + 3));
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)CMit::s_pMessageSession + 16LL))(CMit::s_pMessageSession);
    CMit::s_pMessageSession = 0;
  }
  result = (unsigned __int16)v3;
  if ( (v3 & 0x1FFF0000) != 0x70000 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x1801d0230  mov     [rsp+arg_10], rbx
0x1801d0235  push    rbp
0x1801d0236  push    rsi
0x1801d0237  push    rdi
0x1801d0238  sub     rsp, 30h
0x1801d023c  xor     ebp, ebp
0x1801d023e  mov     rsi, rcx
0x1801d0241  mov     [rsp+48h+arg_8], rbp
0x1801d0246  call    cs:__imp_GetCurrentThreadId
0x1801d024c  lea     ecx, [rbp+8]; dwBytes
0x1801d024f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801d0254  test    rax, rax
0x1801d0257  jz      short loc_1801D0265
0x1801d0259  lea     rcx, ??_7CInputProxy@@6B@; const CInputProxy::`vftable'
0x1801d0260  mov     [rax], rcx
0x1801d0263  jmp     short loc_1801D0268
0x1801d0265  mov     rax, rbp
0x1801d0268  mov     [rsi+28h], rax
0x1801d026c  test    rax, rax
0x1801d026f  jnz     short loc_1801D028B
0x1801d0271  mov     [rsp+48h+var_20], rbp
0x1801d0276  mov     edi, 8007000Eh
0x1801d027b  mov     [rsp+48h+var_28], 83h
0x1801d0283  mov     r9d, edi
0x1801d0286  jmp     loc_1801D0470
0x1801d028b  lea     rdx, ?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d0292  mov     ecx, 1
0x1801d0297  call    cs:__imp_CoreUICreateEx
0x1801d029d  mov     edi, eax
0x1801d029f  test    eax, eax
0x1801d02a1  js      loc_1801D0460
0x1801d02a7  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d02ae  lea     r8, ?OnResetEvent@CGlobalMit@@CAJPEAXK0@Z; CGlobalMit::OnResetEvent(void *,ulong,void *)
0x1801d02b5  mov     rdx, [rsi+18h]
0x1801d02b9  mov     r9, rsi
0x1801d02bc  mov     rax, [rcx]
0x1801d02bf  mov     rax, [rax+110h]
0x1801d02c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d02cb  mov     edi, eax
0x1801d02cd  test    eax, eax
0x1801d02cf  js      loc_1801D0451
0x1801d02d5  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d02dc  lea     r8, ?OnResetEvent@CGlobalMit@@CAJPEAXK0@Z; CGlobalMit::OnResetEvent(void *,ulong,void *)
0x1801d02e3  mov     rdx, [rsi+88h]
0x1801d02ea  mov     r9, rsi
0x1801d02ed  mov     rax, [rcx]
0x1801d02f0  mov     rax, [rax+110h]
0x1801d02f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d02fc  mov     edi, eax
0x1801d02fe  test    eax, eax
0x1801d0300  js      loc_1801D0442
0x1801d0306  mov     rcx, [rsi+28h]
0x1801d030a  lea     r8, ?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA; ISystemInputHost * CMit::s_pSystemInputHost
0x1801d0311  xor     edx, edx
0x1801d0313  call    cs:__imp_CreateSystemInputHost
0x1801d0319  mov     edi, eax
0x1801d031b  test    eax, eax
0x1801d031d  js      loc_1801D0433
0x1801d0323  call    cs:__imp_MITGetCursorUpdateHandle
0x1801d0329  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d032d  jz      short loc_1801D033E
0x1801d032f  lea     rcx, [rsi+90h]
0x1801d0336  mov     rdx, rax
0x1801d0339  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801d033e  lea     rdx, [rsp+48h+arg_8]
0x1801d0343  lea     rcx, ?s_HitTestRequest@CGlobalMit@@SAHPEAU_InputHitTestRequest@@PEAU_InputHitTestResult@@@Z; CGlobalMit::s_HitTestRequest(_InputHitTestRequest *,_InputHitTestResult *)
0x1801d034a  call    cs:__imp_NtMITActivateInputProcessing
0x1801d0350  test    eax, eax
0x1801d0352  jz      loc_1801D041C
0x1801d0358  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d035f  lea     rdx, [rsp+48h+arg_0]
0x1801d0364  mov     rbx, [rsp+48h+arg_8]
0x1801d0369  mov     edi, ebp
0x1801d036b  mov     [rsp+48h+arg_0], rbp
0x1801d0370  mov     rax, [rcx]
0x1801d0373  mov     rax, [rax+28h]
0x1801d0377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d037c  mov     rcx, [rsp+48h+arg_0]
0x1801d0381  lea     r8, ?CompletionHandler@CGlobalMit@@CAJPEAX00@Z; CGlobalMit::CompletionHandler(void *,void *,void *)
0x1801d0388  xor     r9d, r9d
0x1801d038b  mov     rdx, rbx
0x1801d038e  mov     rax, [rcx]
0x1801d0391  mov     rax, [rax+40h]
0x1801d0395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d039a  mov     rcx, [rsp+48h+arg_0]
0x1801d039f  mov     rax, [rcx]
0x1801d03a2  mov     rax, [rax+10h]
0x1801d03a6  jmp     short loc_1801D0409
0x1801d03a8  mov     rcx, [rsi+18h]; hEvent
0x1801d03ac  call    cs:__imp_ResetEvent
0x1801d03b2  cmp     [rsi+20h], bpl
0x1801d03b6  jnz     short loc_1801D0414
0x1801d03b8  mov     rax, [rsi+8]
0x1801d03bc  lea     rcx, [rsi+30h]; this
0x1801d03c0  cmp     [rax+328h], bpl
0x1801d03c7  jz      short loc_1801D03F3
0x1801d03c9  mov     dl, 1; bool
0x1801d03cb  call    ?Apply@CMmcssTask@@QEAAJ_N@Z; CMmcssTask::Apply(bool)
0x1801d03d0  test    eax, eax
0x1801d03d2  jns     short loc_1801D03F8
0x1801d03d4  xor     edx, edx; int *
0x1801d03d6  mov     [rsp+48h+var_20], rbp; void *
0x1801d03db  mov     r9d, eax; int
0x1801d03de  mov     [rsp+48h+var_28], 0F4h; unsigned int
0x1801d03e6  xor     r8d, r8d; unsigned int
0x1801d03e9  lea     ecx, [rdx+14h]; unsigned int
0x1801d03ec  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801d03f1  jmp     short loc_1801D03F8
0x1801d03f3  call    ?Revert@CMmcssTask@@QEAAXXZ; CMmcssTask::Revert(void)
0x1801d03f8  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d03ff  mov     rax, [rcx]
0x1801d0402  mov     rax, [rax+0E8h]
0x1801d0409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d040e  cmp     [rsi+20h], bpl
0x1801d0412  jz      short loc_1801D03A8
0x1801d0414  call    cs:__imp_NtMITDeactivateInputProcessing
0x1801d041a  jmp     short loc_1801D0486
0x1801d041c  mov     [rsp+48h+var_20], rbp
0x1801d0421  mov     edi, 80004005h
0x1801d0426  mov     [rsp+48h+var_28], 9Eh
0x1801d042e  jmp     loc_1801D0283
0x1801d0433  mov     [rsp+48h+var_20], rbp
0x1801d0438  mov     [rsp+48h+var_28], 91h
0x1801d0440  jmp     short loc_1801D046D
0x1801d0442  mov     [rsp+48h+var_20], rbp
0x1801d0447  mov     [rsp+48h+var_28], 8Ch
0x1801d044f  jmp     short loc_1801D046D
0x1801d0451  mov     [rsp+48h+var_20], rbp
0x1801d0456  mov     [rsp+48h+var_28], 8Bh
0x1801d045e  jmp     short loc_1801D046D
0x1801d0460  mov     [rsp+48h+var_20], rbp; void *
0x1801d0465  mov     [rsp+48h+var_28], 89h; unsigned int
0x1801d046d  mov     r9d, eax; int
0x1801d0470  mov     r8d, 2; unsigned int
0x1801d0476  lea     rdx, dword_180343A78; int *
0x1801d047d  lea     ecx, [r8+12h]; unsigned int
0x1801d0481  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801d0486  mov     rcx, cs:?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA; ISystemInputHost * CMit::s_pSystemInputHost
0x1801d048d  test    rcx, rcx
0x1801d0490  jz      short loc_1801D04A5
0x1801d0492  mov     rax, [rcx]
0x1801d0495  mov     rax, [rax+10h]
0x1801d0499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d049e  mov     cs:?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA, rbp; ISystemInputHost * CMit::s_pSystemInputHost
0x1801d04a5  mov     rcx, [rsi+28h]; void *
0x1801d04a9  test    rcx, rcx
0x1801d04ac  jz      short loc_1801D04BC
0x1801d04ae  mov     edx, 8; unsigned __int64
0x1801d04b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801d04b8  mov     [rsi+28h], rbp
0x1801d04bc  mov     rcx, cs:?s_pMessageCallSendHost@CMit@@1PEAUIMessageCallSendHost@@EA; IMessageCallSendHost * CMit::s_pMessageCallSendHost
0x1801d04c3  test    rcx, rcx
0x1801d04c6  jz      short loc_1801D04DB
0x1801d04c8  mov     rax, [rcx]
0x1801d04cb  mov     rax, [rax+10h]
0x1801d04cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d04d4  mov     cs:?s_pMessageCallSendHost@CMit@@1PEAUIMessageCallSendHost@@EA, rbp; IMessageCallSendHost * CMit::s_pMessageCallSendHost
0x1801d04db  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d04e2  test    rcx, rcx
0x1801d04e5  jz      short loc_1801D0531
0x1801d04e7  mov     rax, [rcx]
0x1801d04ea  mov     rdx, [rsi+88h]
0x1801d04f1  mov     rax, [rax+118h]
0x1801d04f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d04fd  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d0504  mov     rdx, [rsi+18h]
0x1801d0508  mov     rax, [rcx]
0x1801d050b  mov     rax, [rax+118h]
0x1801d0512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0517  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x1801d051e  mov     rax, [rcx]
0x1801d0521  mov     rax, [rax+10h]
0x1801d0525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d052a  mov     cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA, rbp; IMessageSession * CMit::s_pMessageSession
0x1801d0531  mov     rbx, [rsp+48h+arg_10]
0x1801d0536  mov     ecx, edi
0x1801d0538  and     ecx, 1FFF0000h
0x1801d053e  movzx   eax, di
0x1801d0541  cmp     ecx, 70000h
0x1801d0547  cmovnz  eax, edi
0x1801d054a  add     rsp, 30h
0x1801d054e  pop     rdi
0x1801d054f  pop     rsi
0x1801d0550  pop     rbp
0x1801d0551  retn
```
