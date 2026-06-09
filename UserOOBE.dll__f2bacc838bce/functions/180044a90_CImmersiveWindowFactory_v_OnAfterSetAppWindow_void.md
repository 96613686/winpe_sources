# CImmersiveWindowFactory::v_OnAfterSetAppWindow(void)

- ea: `0x180044a90`
- end: `0x180044bc1`
- name: `?v_OnAfterSetAppWindow@CImmersiveWindowFactory@@EEAAXXZ`
- size: `305`
- prototype: `void __fastcall(CImmersiveWindowFactory *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800067b0`
- `0x18002d2fc`
- `0x18002d3bc`
- `0x180044a90`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180044ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180044ad0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044aee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b4b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b4b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180044b04`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180044b04`

## pseudocode

```c
void __fastcall CImmersiveWindowFactory::v_OnAfterSetAppWindow(CImmersiveWindowFactory *this, __int64 a2)
{
  DWORD ProcessId; // ebx
  int CallingProcessHandle; // edi
  char *v5; // rcx
  LPVOID v6; // rdi
  int (__fastcall *v7)(LPVOID, GUID *, GUID *, HANDLE *); // rbx
  DWORD dwProcessId; // [rsp+50h] [rbp+20h] BYREF
  HANDLE Process; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  if ( !*((_DWORD *)this + 33) )
  {
    ProcessId = 0;
    dwProcessId = 0;
    Process = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(0x1000u, a2, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v5 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    if ( CallingProcessHandle >= 0
      && GetWindowThreadProcessId(*((HWND *)this + 12), &dwProcessId)
      && ProcessId == dwProcessId )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( CoCreateInstance(
             &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
             0,
             0x404u,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &ppv) >= 0 )
      {
        v6 = ppv;
        Process = 0;
        v7 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, HANDLE *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&Process);
        if ( v7(v6, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &Process) >= 0 )
          (*(void (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)Process + 40LL))(Process, *((_QWORD *)this + 12));
        Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&Process);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
}

```

## disassembly

```asm
0x180044a90  mov     [rsp-18h+arg_18], rbx
0x180044a95  push    rbp
0x180044a96  push    rsi
0x180044a97  push    rdi
0x180044a98  mov     rbp, rsp
0x180044a9b  sub     rsp, 30h
0x180044a9f  cmp     dword ptr [rcx+84h], 0
0x180044aa6  mov     rsi, rcx
0x180044aa9  jnz     loc_180044BB4
0x180044aaf  xor     ebx, ebx
0x180044ab1  lea     r8, [rbp+Process]
0x180044ab5  mov     ecx, 1000h
0x180044aba  mov     [rbp+dwProcessId], ebx
0x180044abd  mov     [rbp+Process], rbx
0x180044ac1  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180044ac6  mov     edi, eax
0x180044ac8  test    eax, eax
0x180044aca  js      short loc_180044AD8
0x180044acc  mov     rcx, [rbp+Process]; Process
0x180044ad0  call    cs:__imp_GetProcessId
0x180044ad6  mov     ebx, eax
0x180044ad8  mov     rcx, [rbp+Process]; hObject
0x180044adc  mov     [rbp+Process], 0
0x180044ae4  lea     rdx, [rcx-1]
0x180044ae8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180044aec  ja      short loc_180044AF4
0x180044aee  call    cs:__imp_CloseHandle
0x180044af4  test    edi, edi
0x180044af6  js      loc_180044BB4
0x180044afc  mov     rcx, [rsi+60h]; hWnd
0x180044b00  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180044b04  call    cs:__imp_GetWindowThreadProcessId
0x180044b0a  test    eax, eax
0x180044b0c  jz      loc_180044BB4
0x180044b12  cmp     ebx, [rbp+dwProcessId]
0x180044b15  jnz     loc_180044BB4
0x180044b1b  lea     rcx, [rbp+arg_10]
0x180044b1f  mov     [rbp+arg_10], 0
0x180044b27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044b2c  lea     rax, [rbp+arg_10]
0x180044b30  xor     edx, edx; pUnkOuter
0x180044b32  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180044b39  mov     [rsp+30h+ppv], rax; ppv
0x180044b3e  mov     r8d, 404h; dwClsContext
0x180044b44  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180044b4b  call    cs:__imp_CoCreateInstance
0x180044b51  test    eax, eax
0x180044b53  js      short loc_180044BAB
0x180044b55  mov     rdi, [rbp+arg_10]
0x180044b59  lea     rcx, [rbp+Process]
0x180044b5d  mov     [rbp+Process], 0
0x180044b65  mov     rax, [rdi]
0x180044b68  mov     rbx, [rax+18h]
0x180044b6c  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180044b71  lea     rdx, _GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b
0x180044b78  mov     rcx, rdi
0x180044b7b  mov     r8, rdx
0x180044b7e  lea     r9, [rbp+Process]
0x180044b82  mov     rax, rbx
0x180044b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b8a  test    eax, eax
0x180044b8c  js      short loc_180044BA2
0x180044b8e  mov     rcx, [rbp+Process]
0x180044b92  mov     rdx, [rsi+60h]
0x180044b96  mov     rax, [rcx]
0x180044b99  mov     rax, [rax+28h]
0x180044b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ba2  lea     rcx, [rbp+Process]
0x180044ba6  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180044bab  lea     rcx, [rbp+arg_10]
0x180044baf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044bb4  mov     rbx, [rsp+30h+arg_18]
0x180044bb9  add     rsp, 30h
0x180044bbd  pop     rdi
0x180044bbe  pop     rsi
0x180044bbf  pop     rbp
0x180044bc0  retn
```
