# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::~CompletionDelegate(void)

- ea: `0x180010b28`
- end: `0x180010b4f`
- name: `??1CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAA@XZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010ec0`

## callees

- `0x1800049b0`
- `0x180006324`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::~CompletionDelegate(
        __int64 a1,
        void *a2)
{
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)(a1 + 56),
    a2);
  *(_DWORD *)(a1 + 44) = -1073741823;
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 32);
}

```

## disassembly

```asm
0x180010b28  push    rbx
0x180010b2a  sub     rsp, 20h
0x180010b2e  mov     rbx, rcx
0x180010b31  add     rcx, 38h ; '8'
0x180010b35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010b3a  lea     rcx, [rbx+20h]
0x180010b3e  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180010b45  add     rsp, 20h
0x180010b49  pop     rbx
0x180010b4a  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
