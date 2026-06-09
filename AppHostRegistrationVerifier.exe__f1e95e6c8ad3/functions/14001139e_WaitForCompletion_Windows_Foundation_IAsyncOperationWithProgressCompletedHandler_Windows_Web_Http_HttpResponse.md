# _WaitForCompletion_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress__Windows::Foundation::IAsyncOperationWithProgress_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress____::_1_::dtor$2

- ea: `0x14001139e`
- end: `0x1400113aa`
- name: `_WaitForCompletion_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress__Windows::Foundation::IAsyncOperationWithProgress_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress____::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall WaitForCompletion_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress__Windows::Foundation::IAsyncOperationWithProgress_Windows::Web::Http::HttpResponseMessage___Windows::Web::Http::HttpProgress____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 112);
}

```

## disassembly

```asm
0x14001139e  lea     rcx, [rdx+70h]
0x1400113a5  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
