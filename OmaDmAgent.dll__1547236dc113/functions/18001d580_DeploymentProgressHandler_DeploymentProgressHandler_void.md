# DeploymentProgressHandler::DeploymentProgressHandler(void)

- ea: `0x18001d580`
- end: `0x18001d687`
- name: `??0DeploymentProgressHandler@@QEAA@XZ`
- size: `263`
- prototype: `DeploymentProgressHandler *__fastcall(DeploymentProgressHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800179a8`

## callees

- `0x18000a2c0`
- `0x18000b588`
- `0x180011098`
- `0x18001d580`
- `0x180021010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18001d624`
- `KERNEL32!CreateEventW` at `0x18001d624`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DeploymentProgressHandler *__fastcall DeploymentProgressHandler::DeploymentProgressHandler(
        DeploymentProgressHandler *this)
{
  HANDLE EventW; // rax
  unsigned int Error; // eax

  *(_QWORD *)this = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable';
  *((_QWORD *)this + 1) = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable';
  *((_DWORD *)this + 5) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vftable'{for `Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &DeploymentProgressHandler::`vftable'{for `Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'};
  *((_QWORD *)this + 1) = &DeploymentProgressHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>'};
  *((_QWORD *)this + 8) = 7;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 20) = 0;
  _DeployJob::_DeployJob((DeploymentProgressHandler *)((char *)this + 80));
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 9) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    Error = ResultFromLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids, Error);
  }
  return this;
}

```

## disassembly

```asm
0x18001d580  mov     [rsp+arg_0], rcx
0x18001d585  push    rbx
0x18001d586  sub     rsp, 20h
0x18001d58a  mov     rbx, rcx
0x18001d58d  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x18001d594  mov     [rcx], rax
0x18001d597  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x18001d59e  mov     [rcx+8], rax
0x18001d5a2  mov     dword ptr [rcx+14h], 1
0x18001d5a9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@WRL@Microsoft@@6B?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vftable'{for `Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x18001d5b0  mov     [rcx], rax
0x18001d5b3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>'}
0x18001d5ba  mov     [rcx+8], rax
0x18001d5be  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001d5c5  test    rcx, rcx
0x18001d5c8  jz      short loc_18001D5D7
0x18001d5ca  mov     rax, [rcx]
0x18001d5cd  mov     rax, [rax+8]
0x18001d5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d6  nop
0x18001d5d7  lea     rax, ??_7DeploymentProgressHandler@@6B?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@; const DeploymentProgressHandler::`vftable'{for `Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x18001d5de  mov     [rbx], rax
0x18001d5e1  lea     rax, ??_7DeploymentProgressHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@Details@WRL@Microsoft@@@; const DeploymentProgressHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>'}
0x18001d5e8  mov     [rbx+8], rax
0x18001d5ec  mov     qword ptr [rbx+40h], 7
0x18001d5f4  mov     qword ptr [rbx+38h], 0
0x18001d5fc  xor     eax, eax
0x18001d5fe  mov     [rbx+28h], ax
0x18001d602  lea     rcx, [rbx+50h]; this
0x18001d606  call    ??0_DeployJob@@QEAA@XZ; _DeployJob::_DeployJob(void)
0x18001d60b  mov     qword ptr [rbx+18h], 0
0x18001d613  mov     dword ptr [rbx+20h], 0
0x18001d61a  xor     r9d, r9d; lpName
0x18001d61d  xor     r8d, r8d; bInitialState
0x18001d620  xor     edx, edx; bManualReset
0x18001d622  xor     ecx, ecx; lpEventAttributes
0x18001d624  call    cs:__imp_CreateEventW
0x18001d62b  nop     dword ptr [rax+rax+00h]
0x18001d630  mov     [rbx+48h], rax
0x18001d634  inc     rax
0x18001d637  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d63d  jnz     short loc_18001D67D
0x18001d63f  lea     rcx, WPP_GLOBAL_Control
0x18001d646  mov     rax, cs:WPP_GLOBAL_Control
0x18001d64d  cmp     rax, rcx
0x18001d650  jz      short loc_18001D67D
0x18001d652  test    byte ptr [rax+1Ch], 4
0x18001d656  jz      short loc_18001D67D
0x18001d658  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d65d  mov     edx, 0Ah
0x18001d662  mov     r9d, eax
0x18001d665  lea     r8, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids
0x18001d66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d673  mov     rcx, [rcx+10h]
0x18001d677  call    WPP_SF_d
0x18001d67c  nop
0x18001d67d  mov     rax, rbx
0x18001d680  add     rsp, 20h
0x18001d684  pop     rbx
0x18001d685  retn
```
