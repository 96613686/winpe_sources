# CImmersiveWindowFactory::v_OnAfterSetAppWindow(void)

- ea: `0x180054bc0`
- end: `0x180054cee`
- name: `?v_OnAfterSetAppWindow@CImmersiveWindowFactory@@EEAAXXZ`
- size: `302`
- prototype: `void __fastcall(CImmersiveWindowFactory *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800542a0`
- `0x180054bc0`
- `0x180055a34`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054c78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054c78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180054bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180054bfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c1b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180054c31`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180054c31`

## pseudocode

```c
void __fastcall CImmersiveWindowFactory::v_OnAfterSetAppWindow(HWND *this)
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
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, 0, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v4 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    if ( CallingProcessHandle >= 0 && GetWindowThreadProcessId(this[12], &dwProcessId) && ProcessId == dwProcessId )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppv);
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
        Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&Process);
        if ( v6(v5, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &Process) >= 0 )
          (*(void (__fastcall **)(HANDLE, HWND))(*(_QWORD *)Process + 40LL))(Process, this[12]);
        Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&Process);
      }
      Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppv);
    }
  }
}

```

## disassembly

```asm
0x180054bc0  mov     [rsp-18h+arg_18], rbx
0x180054bc5  push    rbp
0x180054bc6  push    rsi
0x180054bc7  push    rdi
0x180054bc8  mov     rbp, rsp
0x180054bcb  sub     rsp, 30h
0x180054bcf  cmp     dword ptr [rcx+84h], 0
0x180054bd6  mov     rsi, rcx
0x180054bd9  jnz     loc_180054CE1
0x180054bdf  xor     ebx, ebx
0x180054be1  lea     r8, [rbp+Process]
0x180054be5  xor     edx, edx
0x180054be7  mov     [rbp+dwProcessId], ebx
0x180054bea  mov     [rbp+Process], rbx
0x180054bee  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180054bf3  mov     edi, eax
0x180054bf5  test    eax, eax
0x180054bf7  js      short loc_180054C05
0x180054bf9  mov     rcx, [rbp+Process]; Process
0x180054bfd  call    cs:__imp_GetProcessId
0x180054c03  mov     ebx, eax
0x180054c05  mov     rcx, [rbp+Process]; hObject
0x180054c09  mov     [rbp+Process], 0
0x180054c11  lea     rdx, [rcx-1]
0x180054c15  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180054c19  ja      short loc_180054C21
0x180054c1b  call    cs:__imp_CloseHandle
0x180054c21  test    edi, edi
0x180054c23  js      loc_180054CE1
0x180054c29  mov     rcx, [rsi+60h]; hWnd
0x180054c2d  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180054c31  call    cs:__imp_GetWindowThreadProcessId
0x180054c37  test    eax, eax
0x180054c39  jz      loc_180054CE1
0x180054c3f  cmp     ebx, [rbp+dwProcessId]
0x180054c42  jnz     loc_180054CE1
0x180054c48  lea     rcx, [rbp+arg_10]
0x180054c4c  mov     [rbp+arg_10], 0
0x180054c54  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180054c59  lea     rax, [rbp+arg_10]
0x180054c5d  xor     edx, edx; pUnkOuter
0x180054c5f  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180054c66  mov     [rsp+30h+ppv], rax; ppv
0x180054c6b  mov     r8d, 404h; dwClsContext
0x180054c71  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180054c78  call    cs:__imp_CoCreateInstance
0x180054c7e  test    eax, eax
0x180054c80  js      short loc_180054CD8
0x180054c82  mov     rdi, [rbp+arg_10]
0x180054c86  lea     rcx, [rbp+Process]
0x180054c8a  mov     [rbp+Process], 0
0x180054c92  mov     rax, [rdi]
0x180054c95  mov     rbx, [rax+18h]
0x180054c99  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180054c9e  lea     rdx, _GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b
0x180054ca5  mov     rcx, rdi
0x180054ca8  mov     r8, rdx
0x180054cab  lea     r9, [rbp+Process]
0x180054caf  mov     rax, rbx
0x180054cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cb7  test    eax, eax
0x180054cb9  js      short loc_180054CCF
0x180054cbb  mov     rcx, [rbp+Process]
0x180054cbf  mov     rdx, [rsi+60h]
0x180054cc3  mov     rax, [rcx]
0x180054cc6  mov     rax, [rax+28h]
0x180054cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ccf  lea     rcx, [rbp+Process]
0x180054cd3  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180054cd8  lea     rcx, [rbp+arg_10]
0x180054cdc  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180054ce1  mov     rbx, [rsp+30h+arg_18]
0x180054ce6  add     rsp, 30h
0x180054cea  pop     rdi
0x180054ceb  pop     rsi
0x180054cec  pop     rbp
0x180054ced  retn
```
