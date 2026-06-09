# CImmersiveWindowFactory::v_OnAfterSetAppWindow(void)

- ea: `0x180095f20`
- end: `0x180096053`
- name: `?v_OnAfterSetAppWindow@CImmersiveWindowFactory@@EEAAXXZ`
- size: `307`
- prototype: `void __fastcall(CImmersiveWindowFactory *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180010a34`
- `0x180011328`
- `0x1800234f8`
- `0x180095f20`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180095f62`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180095f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095f80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095f80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180095fdd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180095fdd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180095f96`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180095f96`

## pseudocode

```c
void __fastcall CImmersiveWindowFactory::v_OnAfterSetAppWindow(CImmersiveWindowFactory *this)
{
  DWORD ProcessId; // ebx
  int CallingProcessHandle; // edi
  char *v4; // rcx
  LPVOID v5; // rdi
  int (__fastcall *v6)(LPVOID, GUID *, GUID *, HANDLE *); // rbx
  DWORD dwProcessId; // [rsp+50h] [rbp+20h] BYREF
  HANDLE Process; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  if ( !*((_DWORD *)this + 33) )
  {
    ProcessId = 0;
    dwProcessId = 0;
    Process = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(4096, 0, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v4 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    if ( CallingProcessHandle >= 0
      && GetWindowThreadProcessId(*((HWND *)this + 12), &dwProcessId)
      && ProcessId == dwProcessId )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
      if ( CoCreateInstance(
             &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
             0,
             0x404u,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &ppv) >= 0 )
      {
        v5 = ppv;
        Process = 0;
        v6 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, HANDLE *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&Process);
        if ( v6(v5, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &Process) >= 0 )
          (*(void (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)Process + 40LL))(Process, *((_QWORD *)this + 12));
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&Process);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    }
  }
}

```

## disassembly

```asm
0x180095f20  mov     [rsp-18h+arg_18], rbx
0x180095f25  push    rbp
0x180095f26  push    rsi
0x180095f27  push    rdi
0x180095f28  mov     rbp, rsp
0x180095f2b  sub     rsp, 30h
0x180095f2f  cmp     dword ptr [rcx+84h], 0
0x180095f36  mov     rsi, rcx
0x180095f39  jnz     loc_180096046
0x180095f3f  xor     ebx, ebx
0x180095f41  lea     r8, [rbp+Process]
0x180095f45  xor     edx, edx
0x180095f47  mov     [rbp+dwProcessId], ebx
0x180095f4a  mov     ecx, 1000h
0x180095f4f  mov     [rbp+Process], rbx
0x180095f53  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180095f58  mov     edi, eax
0x180095f5a  test    eax, eax
0x180095f5c  js      short loc_180095F6A
0x180095f5e  mov     rcx, [rbp+Process]; Process
0x180095f62  call    cs:__imp_GetProcessId
0x180095f68  mov     ebx, eax
0x180095f6a  mov     rcx, [rbp+Process]; hObject
0x180095f6e  mov     [rbp+Process], 0
0x180095f76  lea     rdx, [rcx-1]
0x180095f7a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180095f7e  ja      short loc_180095F86
0x180095f80  call    cs:__imp_CloseHandle
0x180095f86  test    edi, edi
0x180095f88  js      loc_180096046
0x180095f8e  mov     rcx, [rsi+60h]; hWnd
0x180095f92  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180095f96  call    cs:__imp_GetWindowThreadProcessId
0x180095f9c  test    eax, eax
0x180095f9e  jz      loc_180096046
0x180095fa4  cmp     ebx, [rbp+dwProcessId]
0x180095fa7  jnz     loc_180096046
0x180095fad  lea     rcx, [rbp+arg_10]
0x180095fb1  mov     [rbp+arg_10], 0
0x180095fb9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095fbe  lea     rax, [rbp+arg_10]
0x180095fc2  xor     edx, edx; pUnkOuter
0x180095fc4  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180095fcb  mov     [rsp+30h+ppv], rax; ppv
0x180095fd0  mov     r8d, 404h; dwClsContext
0x180095fd6  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180095fdd  call    cs:__imp_CoCreateInstance
0x180095fe3  test    eax, eax
0x180095fe5  js      short loc_18009603D
0x180095fe7  mov     rdi, [rbp+arg_10]
0x180095feb  lea     rcx, [rbp+Process]
0x180095fef  mov     [rbp+Process], 0
0x180095ff7  mov     rax, [rdi]
0x180095ffa  mov     rbx, [rax+18h]
0x180095ffe  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180096003  lea     rdx, _GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b
0x18009600a  mov     rcx, rdi
0x18009600d  mov     r8, rdx
0x180096010  lea     r9, [rbp+Process]
0x180096014  mov     rax, rbx
0x180096017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009601c  test    eax, eax
0x18009601e  js      short loc_180096034
0x180096020  mov     rcx, [rbp+Process]
0x180096024  mov     rdx, [rsi+60h]
0x180096028  mov     rax, [rcx]
0x18009602b  mov     rax, [rax+28h]
0x18009602f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096034  lea     rcx, [rbp+Process]
0x180096038  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x18009603d  lea     rcx, [rbp+arg_10]
0x180096041  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180096046  mov     rbx, [rsp+30h+arg_18]
0x18009604b  add     rsp, 30h
0x18009604f  pop     rdi
0x180096050  pop     rsi
0x180096051  pop     rbp
0x180096052  retn
```
