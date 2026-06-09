# `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vector deleting destructor'(uint)

- ea: `0x14000a7d0`
- end: `0x14000a804`
- name: `??_EFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140002504`
- `0x14000a2ec`
- `0x14000a7d0`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::`vector deleting destructor'(
        void *a1,
        char a2)
{
  `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::~FTMEventDelegate((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000a7d0  mov     [rsp+arg_0], rbx
0x14000a7d5  push    rdi
0x14000a7d6  sub     rsp, 20h
0x14000a7da  mov     ebx, edx
0x14000a7dc  mov     rdi, rcx
0x14000a7df  call    ??1FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::~FTMEventDelegate(void)
0x14000a7e4  test    bl, 1
0x14000a7e7  jz      short loc_14000A7F6
0x14000a7e9  mov     edx, 40h ; '@'; unsigned __int64
0x14000a7ee  mov     rcx, rdi; void *
0x14000a7f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a7f6  mov     rbx, [rsp+28h+arg_0]
0x14000a7fb  mov     rax, rdi
0x14000a7fe  add     rsp, 20h
0x14000a802  pop     rdi
0x14000a803  retn
```
