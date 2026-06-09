# CImmersiveWindowFactory::v_OnAfterSetAppWindow(void)

- ea: `0x1800402e0`
- end: `0x1800403fc`
- name: `?v_OnAfterSetAppWindow@CImmersiveWindowFactory@@EEAAXXZ`
- size: `284`
- prototype: `void __fastcall(CImmersiveWindowFactory *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800164a4`
- `0x18003de0c`
- `0x18003e0d4`
- `0x1800402e0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004031d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004031d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040386`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040386`
- `USER32!GetWindowThreadProcessId` at `0x18004033f`
- `USER32!GetWindowThreadProcessId` at `0x18004033f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CImmersiveWindowFactory::v_OnAfterSetAppWindow(HWND *this)
{
  DWORD ProcessId; // ebx
  int CallingProcessHandle; // edi
  LPVOID v4; // rdi
  int (__fastcall *v5)(LPVOID, GUID *, GUID *, HANDLE *); // rbx
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
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&Process);
    if ( CallingProcessHandle >= 0 && GetWindowThreadProcessId(this[12], &dwProcessId) && ProcessId == dwProcessId )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      if ( CoCreateInstance(
             &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
             0,
             0x404u,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &ppv) >= 0 )
      {
        Process = 0;
        v4 = ppv;
        v5 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, HANDLE *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&Process);
        if ( v5(v4, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b, &Process) >= 0 )
          (*(void (__fastcall **)(HANDLE, HWND))(*(_QWORD *)Process + 40LL))(Process, this[12]);
        Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&Process);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    }
  }
}

```

## disassembly

```asm
0x1800402e0  mov     [rsp-18h+arg_18], rbx
0x1800402e5  push    rbp
0x1800402e6  push    rsi
0x1800402e7  push    rdi
0x1800402e8  mov     rbp, rsp
0x1800402eb  sub     rsp, 30h
0x1800402ef  mov     rsi, rcx
0x1800402f2  cmp     dword ptr [rcx+84h], 0
0x1800402f9  jnz     loc_1800403EF
0x1800402ff  xor     ebx, ebx
0x180040301  mov     [rbp+dwProcessId], ebx
0x180040304  mov     [rbp+Process], rbx
0x180040308  lea     r8, [rbp+Process]
0x18004030c  xor     edx, edx
0x18004030e  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180040313  mov     edi, eax
0x180040315  test    eax, eax
0x180040317  js      short loc_180040325
0x180040319  mov     rcx, [rbp+Process]; Process
0x18004031d  call    cs:__imp_GetProcessId
0x180040323  mov     ebx, eax
0x180040325  lea     rcx, [rbp+Process]
0x180040329  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18004032e  nop
0x18004032f  test    edi, edi
0x180040331  js      loc_1800403EF
0x180040337  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18004033b  mov     rcx, [rsi+60h]; hWnd
0x18004033f  call    cs:__imp_GetWindowThreadProcessId
0x180040345  test    eax, eax
0x180040347  jz      loc_1800403EF
0x18004034d  cmp     ebx, [rbp+dwProcessId]
0x180040350  jnz     loc_1800403EF
0x180040356  mov     [rbp+arg_10], 0
0x18004035e  lea     rcx, [rbp+arg_10]
0x180040362  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180040367  lea     rax, [rbp+arg_10]
0x18004036b  mov     [rsp+30h+ppv], rax; ppv
0x180040370  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180040377  xor     edx, edx; pUnkOuter
0x180040379  mov     r8d, 404h; dwClsContext
0x18004037f  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180040386  call    cs:__imp_CoCreateInstance
0x18004038c  test    eax, eax
0x18004038e  js      short loc_1800403E6
0x180040390  mov     [rbp+Process], 0
0x180040398  mov     rdi, [rbp+arg_10]
0x18004039c  mov     rax, [rdi]
0x18004039f  mov     rbx, [rax+18h]
0x1800403a3  lea     rcx, [rbp+Process]
0x1800403a7  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x1800403ac  lea     r9, [rbp+Process]
0x1800403b0  lea     rdx, _GUID_203e0af6_3e82_4224_9e81_1cd9a6fe638b
0x1800403b7  mov     r8, rdx
0x1800403ba  mov     rcx, rdi
0x1800403bd  mov     rax, rbx
0x1800403c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403c5  test    eax, eax
0x1800403c7  js      short loc_1800403DD
0x1800403c9  mov     rcx, [rbp+Process]
0x1800403cd  mov     rax, [rcx]
0x1800403d0  mov     rdx, [rsi+60h]
0x1800403d4  mov     rax, [rax+28h]
0x1800403d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403dd  lea     rcx, [rbp+Process]
0x1800403e1  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x1800403e6  lea     rcx, [rbp+arg_10]
0x1800403ea  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800403ef  mov     rbx, [rsp+30h+arg_18]
0x1800403f4  add     rsp, 30h
0x1800403f8  pop     rdi
0x1800403f9  pop     rsi
0x1800403fa  pop     rbp
0x1800403fb  retn
```
