# ApplicationInstanceInfo::~ApplicationInstanceInfo(void)

- ea: `0x18000df48`
- end: `0x18000dff3`
- name: `??1ApplicationInstanceInfo@@UEAA@XZ`
- size: `171`
- prototype: `void __fastcall(ApplicationInstanceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e990`

## callees

- `0x18000cbc0`
- `0x18000df48`
- `0x18000dffc`
- `0x180011328`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dfb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dfb0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000df68`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000df68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ApplicationInstanceInfo::~ApplicationInstanceInfo(ApplicationInstanceInfo *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &ApplicationInstanceInfo::`vftable';
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 7) = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 112);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 104);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 88);
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 40);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000df48  push    rbx
0x18000df4a  sub     rsp, 20h
0x18000df4e  mov     rbx, rcx
0x18000df51  lea     rax, ??_7ApplicationInstanceInfo@@6B@; const ApplicationInstanceInfo::`vftable'
0x18000df58  mov     [rcx], rax
0x18000df5b  mov     rcx, [rcx+38h]; WaitHandle
0x18000df5f  test    rcx, rcx
0x18000df62  jz      short loc_18000DF76
0x18000df64  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000df68  call    cs:__imp_UnregisterWaitEx
0x18000df6e  mov     qword ptr [rbx+38h], 0
0x18000df76  lea     rcx, [rbx+78h]
0x18000df7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000df7f  lea     rcx, [rbx+70h]
0x18000df83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000df88  lea     rcx, [rbx+68h]
0x18000df8c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000df91  lea     rcx, [rbx+58h]
0x18000df95  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000df9a  mov     rcx, [rbx+50h]; string
0x18000df9e  call    cs:__imp_WindowsDeleteString
0x18000dfa4  mov     qword ptr [rbx+50h], 0
0x18000dfac  mov     rcx, [rbx+48h]; string
0x18000dfb0  call    cs:__imp_WindowsDeleteString
0x18000dfb6  mov     qword ptr [rbx+48h], 0
0x18000dfbe  lea     rcx, [rbx+28h]
0x18000dfc2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dfc7  nop
0x18000dfc8  mov     rcx, [rbx+18h]
0x18000dfcc  test    rcx, rcx
0x18000dfcf  jz      short loc_18000DFE6
0x18000dfd1  mov     qword ptr [rbx+18h], 0
0x18000dfd9  mov     rax, [rcx]
0x18000dfdc  mov     rax, [rax+10h]
0x18000dfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfe5  nop
0x18000dfe6  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000dfed  add     rsp, 20h
0x18000dff1  pop     rbx
0x18000dff2  retn
```
