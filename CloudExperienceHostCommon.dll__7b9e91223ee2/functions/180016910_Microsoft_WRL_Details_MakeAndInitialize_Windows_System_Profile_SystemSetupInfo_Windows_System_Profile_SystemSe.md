# Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Profile::SystemSetupInfo,Windows::System::Profile::SystemSetupInfo,>(Windows::System::Profile::SystemSetupInfo * *)

- ea: `0x180016910`
- end: `0x1800169c5`
- name: `??$MakeAndInitialize@VSystemSetupInfo@Profile@System@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVSystemSetupInfo@Profile@System@Windows@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004890`

## callees

- `0x1800039a0`
- `0x180014878`
- `0x180016910`
- `0x180017224`
- `0x180017330`
- `0x18001a94c`
- `0x1800c82bc`

## import_xrefs

- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18001697e`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x180016964`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Profile::SystemSetupInfo,Windows::System::Profile::SystemSetupInfo,>(
        _QWORD *a1)
{
  Windows::System::Profile::SystemSetupInfo *v2; // rax
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (Windows::System::Profile::SystemSetupInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v4 = Windows::System::Profile::SystemSetupInfo::SystemSetupInfo(v2);
  v7 = 0;
  Microsoft::WRL::ComPtr<Windows::System::Profile::SystemSetupInfo>::Attach(&v7, v4);
  v5 = v7;
  v6 = v7;
  v8 = 0;
  *(_QWORD *)(v7 + 168) = RegisterWaitUntilOOBECompleted;
  *(_QWORD *)(v6 + 176) = UnregisterWaitUntilOOBECompleted;
  *(_WORD *)(v6 + 184) = 256;
  *(_BYTE *)(v6 + 186) = 0;
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IScheduledTasksRegistrationManager>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::AddRef(v6);
  *a1 = v5;
  Microsoft::WRL::ComPtr<Windows::System::Profile::SystemSetupInfo>::InternalRelease(&v7);
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v8);
  return 0;
}

```

## disassembly

```asm
0x180016910  mov     [rsp+arg_10], rbx
0x180016915  push    rdi
0x180016916  sub     rsp, 20h
0x18001691a  mov     rdi, rcx
0x18001691d  mov     qword ptr [rcx], 0
0x180016924  mov     ecx, 0C0h; unsigned __int64
0x180016929  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016930  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016935  test    rax, rax
0x180016938  jnz     short loc_180016941
0x18001693a  mov     eax, 8007000Eh
0x18001693f  jmp     short loc_1800169BA
0x180016941  mov     rcx, rax; this
0x180016944  call    ??0SystemSetupInfo@Profile@System@Windows@@QEAA@XZ; Windows::System::Profile::SystemSetupInfo::SystemSetupInfo(void)
0x180016949  mov     rdx, rax
0x18001694c  mov     [rsp+28h+arg_0], 0
0x180016955  lea     rcx, [rsp+28h+arg_0]
0x18001695a  call    ?Attach@?$ComPtr@VSystemSetupInfo@Profile@System@Windows@@@WRL@Microsoft@@QEAAXPEAVSystemSetupInfo@Profile@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::Profile::SystemSetupInfo>::Attach(Windows::System::Profile::SystemSetupInfo *)
0x18001695f  mov     rbx, [rsp+28h+arg_0]
0x180016964  mov     rax, cs:__imp_RegisterWaitUntilOOBECompleted
0x18001696b  mov     rcx, rbx
0x18001696e  mov     [rsp+28h+arg_8], 0
0x180016977  mov     [rbx+0A8h], rax
0x18001697e  mov     rax, cs:__imp_UnregisterWaitUntilOOBECompleted
0x180016985  mov     [rbx+0B0h], rax
0x18001698c  mov     word ptr [rbx+0B8h], 100h
0x180016995  mov     byte ptr [rbx+0BAh], 0
0x18001699c  call    ?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIScheduledTasksRegistrationManager@CloudExperienceHostAPI@@@WRL@Microsoft@@VFtmBase@23@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IScheduledTasksRegistrationManager>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x1800169a1  lea     rcx, [rsp+28h+arg_0]
0x1800169a6  mov     [rdi], rbx
0x1800169a9  call    ?InternalRelease@?$ComPtr@VSystemSetupInfo@Profile@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::Profile::SystemSetupInfo>::InternalRelease(void)
0x1800169ae  lea     rcx, [rsp+28h+arg_8]
0x1800169b3  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800169b8  xor     eax, eax
0x1800169ba  mov     rbx, [rsp+28h+arg_10]
0x1800169bf  add     rsp, 20h
0x1800169c3  pop     rdi
0x1800169c4  retn
```
