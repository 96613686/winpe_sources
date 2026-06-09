# Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)

- ea: `0x140009e54`
- end: `0x140009e6a`
- name: `??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140008850`
- `0x140008984`

## callees

- `0x140002b7c`
- `0x140009e54`

## pseudocode

```c
void __fastcall __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140009e54  sub     rsp, 28h
0x140009e58  mov     rcx, [rcx]; Block
0x140009e5b  test    rcx, rcx
0x140009e5e  jz      short loc_140009E65
0x140009e60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140009e65  add     rsp, 28h
0x140009e69  retn
```
