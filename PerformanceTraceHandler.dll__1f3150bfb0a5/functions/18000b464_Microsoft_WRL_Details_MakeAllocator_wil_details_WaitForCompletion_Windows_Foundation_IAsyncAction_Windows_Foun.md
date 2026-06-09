# Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)

- ea: `0x18000b464`
- end: `0x18000b47a`
- name: `??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a7b4`
- `0x18000f038`

## callees

- `0x180003074`
- `0x18000b464`

## pseudocode

```c
void __fastcall Z::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>(
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
0x18000b464  sub     rsp, 28h
0x18000b468  mov     rcx, [rcx]; Block
0x18000b46b  test    rcx, rcx
0x18000b46e  jz      short loc_18000B475
0x18000b470  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b475  add     rsp, 28h
0x18000b479  retn
```
