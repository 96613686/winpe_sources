# KeyMachine::NegotiatingInactive::Activate(KeyMachine &,LicenseUsage,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &)

- ea: `0x18001db30`
- end: `0x18001dd96`
- name: `?Activate@NegotiatingInactive@KeyMachine@@UEBAXAEAV2@W4LicenseUsage@@AEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@AEBV?$ComPtr@UIKeyLicenseCallback@@@56@@Z`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b7fc`
- `0x180013b50`
- `0x180013ff0`
- `0x18001dad0`
- `0x18001db30`
- `0x18001dd9c`
- `0x18001de00`
- `0x180043a20`
- `0x1800767e0`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dd3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dd3d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001dccb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001dccb`

## string_xrefs

- `0x18001dbd8`: `BeginLicense: Operation %d, CachedLeaseOK %s, RequireServiceValidation %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KeyMachine::NegotiatingInactive::Activate(__int64 a1, __int64 a2, int a3, _QWORD *a4, _QWORD *a5)
{
  _QWORD *v7; // rdx
  int v8; // eax
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  const char *v11; // r9
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  DWORD CurrentThreadId; // eax
  int v16; // edx
  int v17; // ecx
  int v19; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  KeyMachine::DoSetIdentity(a2, a4);
  StateMachine<KeyMachine,KeyState>::AssertQueueThread(a2 + 32);
  if ( *a5 )
  {
    v7 = *(_QWORD **)(a2 + 144);
    if ( v7 == *(_QWORD **)(a2 + 152) )
    {
      std::vector<Microsoft::WRL::ComPtr<IKeyLicenseCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &>(
        a2 + 136,
        v7,
        a5);
    }
    else
    {
      *v7 = *a5;
      Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(v7);
      *(_QWORD *)(a2 + 144) += 8LL;
    }
  }
  StateMachine<KeyMachine,KeyState>::AssertQueueThread(a2 + 32);
  v8 = *(_DWORD *)(a2 + 256);
  if ( a3 > v8 )
    v8 = a3;
  *(_DWORD *)(a2 + 256) = v8;
  StateMachine<KeyMachine,KeyState>::AssertQueueThread(a2 + 32);
  v19 = 3;
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
    0x33Cu,
    "KeyMachine::DoBeginLicense",
    (wchar_t *)L"BeginLicense: Operation %d, CachedLeaseOK %s, RequireServiceValidation %s",
    v19,
    L"true",
    L"false");
  v9 = operator new(0x30u);
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  v9[3] = 0;
  v9[4] = 0;
  v9[5] = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v10 = v9[3];
    v9[3] = a2;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  *(_DWORD *)v9 = 3;
  *((_DWORD *)v9 + 1) = *(_DWORD *)(a2 + 256);
  *((_WORD *)v9 + 4) = 1;
  Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v9 + 4, a2 + 272);
  Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v9 + 5, a2 + 296);
  Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v9 + 2, a2 + 264);
  if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)KeyMachine::DoLicenseThreadProc, v9, 0x10u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      v11);
  StateMachine<KeyMachine,KeyState>::AssertQueueThread(a2 + 32);
  if ( (Microsoft_Windows_StoreEnableBits & 8) != 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a2 + 32) + 8LL))(a2 + 32);
    v13 = (*(__int64 (__fastcall **)(void **))KeyMachine::NegotiatingUnleased::Instance[0])(KeyMachine::NegotiatingUnleased::Instance);
    v14 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 40))(*(_QWORD *)(a2 + 40));
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0pqzzz_EtwEventWriteTransfer(v17, v16, 0, CurrentThreadId, v14, v13, v12);
  }
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a2 + 40) + 16LL))(*(_QWORD *)(a2 + 40), a2);
  *(_QWORD *)(a2 + 40) = KeyMachine::NegotiatingUnleased::Instance;
  return (*((__int64 (__fastcall **)(void **, __int64))KeyMachine::NegotiatingUnleased::Instance[0] + 1))(
           KeyMachine::NegotiatingUnleased::Instance,
           a2);
}

```

## disassembly

```asm
0x18001db30  push    rbx
0x18001db32  push    rbp
0x18001db33  push    rsi
0x18001db34  push    rdi
0x18001db35  push    r14
0x18001db37  push    r15
0x18001db39  sub     rsp, 48h
0x18001db3d  mov     edi, r8d
0x18001db40  mov     r14, rdx
0x18001db43  mov     rdx, r9
0x18001db46  mov     rcx, r14
0x18001db49  call    ?DoSetIdentity@KeyMachine@@IEAAXAEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@@Z; KeyMachine::DoSetIdentity(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)
0x18001db4e  lea     r15, [r14+20h]
0x18001db52  mov     rcx, r15
0x18001db55  call    ?AssertQueueThread@?$StateMachine@VKeyMachine@@VKeyState@@@@IEAAXXZ; StateMachine<KeyMachine,KeyState>::AssertQueueThread(void)
0x18001db5a  mov     r8, [rsp+78h+arg_20]
0x18001db62  mov     rax, [r8]
0x18001db65  test    rax, rax
0x18001db68  jz      short loc_18001DB95
0x18001db6a  lea     rbx, [r14+88h]
0x18001db71  mov     rdx, [rbx+8]
0x18001db75  cmp     rdx, [rbx+10h]
0x18001db79  jz      short loc_18001DB8D
0x18001db7b  mov     [rdx], rax
0x18001db7e  mov     rcx, rdx
0x18001db81  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18001db86  add     qword ptr [rbx+8], 8
0x18001db8b  jmp     short loc_18001DB95
0x18001db8d  mov     rcx, rbx
0x18001db90  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IKeyLicenseCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &>(Microsoft::WRL::ComPtr<IKeyLicenseCallback> * const,Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &)
0x18001db95  mov     rcx, r15
0x18001db98  call    ?AssertQueueThread@?$StateMachine@VKeyMachine@@VKeyState@@@@IEAAXXZ; StateMachine<KeyMachine,KeyState>::AssertQueueThread(void)
0x18001db9d  mov     eax, [r14+100h]
0x18001dba4  cmp     edi, eax
0x18001dba6  cmovg   eax, edi
0x18001dba9  mov     [r14+100h], eax
0x18001dbb0  mov     rcx, r15
0x18001dbb3  call    ?AssertQueueThread@?$StateMachine@VKeyMachine@@VKeyState@@@@IEAAXXZ; StateMachine<KeyMachine,KeyState>::AssertQueueThread(void)
0x18001dbb8  lea     rax, aFalse_0; "false"
0x18001dbbf  mov     [rsp+78h+var_40], rax
0x18001dbc4  lea     rax, aTrue; "true"
0x18001dbcb  mov     [rsp+78h+var_48], rax
0x18001dbd0  mov     dword ptr [rsp+78h+var_50], 3
0x18001dbd8  lea     rax, aBeginlicenseOp; "BeginLicense: Operation %d, CachedLease"...
0x18001dbdf  mov     [rsp+78h+Format], rax; Format
0x18001dbe4  lea     r9, aKeymachineDobe; "KeyMachine::DoBeginLicense"
0x18001dbeb  mov     r8d, 33Ch; unsigned int
0x18001dbf1  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001dbf8  mov     ecx, 3; unsigned int
0x18001dbfd  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18001dc02  mov     ecx, 30h ; '0'; Size
0x18001dc07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc0c  mov     rbx, rax
0x18001dc0f  mov     qword ptr [rax], 0
0x18001dc16  mov     qword ptr [rax+8], 0
0x18001dc1e  mov     qword ptr [rax+10h], 0
0x18001dc26  mov     qword ptr [rax+18h], 0
0x18001dc2e  mov     qword ptr [rax+20h], 0
0x18001dc36  mov     qword ptr [rax+28h], 0
0x18001dc3e  mov     [rsp+78h+arg_20], rax
0x18001dc46  test    r14, r14
0x18001dc49  jz      short loc_18001DC75
0x18001dc4b  mov     rax, [r14]
0x18001dc4e  mov     rcx, r14
0x18001dc51  mov     rax, [rax+8]
0x18001dc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc5a  nop
0x18001dc5b  mov     rcx, [rbx+18h]
0x18001dc5f  mov     [rbx+18h], r14
0x18001dc63  test    rcx, rcx
0x18001dc66  jz      short loc_18001DC75
0x18001dc68  mov     rax, [rcx]
0x18001dc6b  mov     rax, [rax+10h]
0x18001dc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc74  nop
0x18001dc75  mov     dword ptr [rbx], 3
0x18001dc7b  mov     eax, [r14+100h]
0x18001dc82  mov     [rbx+4], eax
0x18001dc85  mov     word ptr [rbx+8], 1
0x18001dc8b  lea     rdx, [r14+110h]
0x18001dc92  lea     rcx, [rbx+20h]
0x18001dc96  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18001dc9b  lea     rdx, [r14+128h]
0x18001dca2  lea     rcx, [rbx+28h]
0x18001dca6  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18001dcab  lea     rdx, [r14+108h]
0x18001dcb2  lea     rcx, [rbx+10h]
0x18001dcb6  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18001dcbb  mov     r8d, 10h; Flags
0x18001dcc1  mov     rdx, rbx; Context
0x18001dcc4  lea     rcx, ?DoLicenseThreadProc@KeyMachine@@KAKPEAX@Z; Function
0x18001dccb  call    cs:__imp_QueueUserWorkItem
0x18001dcd1  mov     rcx, [rsp+78h]; this
0x18001dcd6  test    eax, eax
0x18001dcd8  jnz     short loc_18001DCEC
0x18001dcda  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001dce1  mov     edx, 356h; void *
0x18001dce6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001dcec  mov     rcx, r15
0x18001dcef  call    ?AssertQueueThread@?$StateMachine@VKeyMachine@@VKeyState@@@@IEAAXXZ; StateMachine<KeyMachine,KeyState>::AssertQueueThread(void)
0x18001dcf4  lea     rbp, ?Instance@NegotiatingUnleased@KeyMachine@@2V12@A; KeyMachine::NegotiatingUnleased KeyMachine::NegotiatingUnleased::Instance
0x18001dcfb  test    cs:Microsoft_Windows_StoreEnableBits, 8
0x18001dd02  jz      short loc_18001DD5D
0x18001dd04  mov     rax, [r15]
0x18001dd07  mov     rcx, r15
0x18001dd0a  mov     rax, [rax+8]
0x18001dd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd13  mov     rsi, rax
0x18001dd16  mov     rcx, cs:?Instance@NegotiatingUnleased@KeyMachine@@2V12@A; KeyMachine::NegotiatingUnleased KeyMachine::NegotiatingUnleased::Instance
0x18001dd1d  mov     rax, [rcx]
0x18001dd20  mov     rcx, rbp
0x18001dd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd28  mov     rdi, rax
0x18001dd2b  mov     rcx, [r15+8]
0x18001dd2f  mov     rdx, [rcx]
0x18001dd32  mov     rax, [rdx]
0x18001dd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd3a  mov     rbx, rax
0x18001dd3d  call    cs:__imp_GetCurrentThreadId
0x18001dd43  mov     [rsp+78h+var_48], rsi
0x18001dd48  mov     [rsp+78h+var_50], rdi
0x18001dd4d  mov     [rsp+78h+Format], rbx
0x18001dd52  mov     r9d, eax
0x18001dd55  xor     r8d, r8d
0x18001dd58  call    McTemplateU0pqzzz_EtwEventWriteTransfer
0x18001dd5d  mov     rcx, [r15+8]
0x18001dd61  mov     rax, [rcx]
0x18001dd64  mov     rdx, r14
0x18001dd67  mov     rax, [rax+10h]
0x18001dd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd70  mov     [r15+8], rbp
0x18001dd74  mov     rax, cs:?Instance@NegotiatingUnleased@KeyMachine@@2V12@A; KeyMachine::NegotiatingUnleased KeyMachine::NegotiatingUnleased::Instance
0x18001dd7b  mov     rdx, r14
0x18001dd7e  mov     rcx, rbp
0x18001dd81  mov     rax, [rax+8]
0x18001dd85  add     rsp, 48h
0x18001dd89  pop     r15
0x18001dd8b  pop     r14
0x18001dd8d  pop     rdi
0x18001dd8e  pop     rsi
0x18001dd8f  pop     rbp
0x18001dd90  pop     rbx
0x18001dd91  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
