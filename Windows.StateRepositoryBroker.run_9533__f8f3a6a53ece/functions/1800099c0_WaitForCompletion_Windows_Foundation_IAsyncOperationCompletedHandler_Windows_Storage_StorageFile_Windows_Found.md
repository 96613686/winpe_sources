# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`scalar deleting destructor'(uint)

- ea: `0x1800099c0`
- end: `0x1800099ef`
- name: `??_GFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002154`
- `0x180009920`
- `0x1800099c0`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::~FTMEventDelegate();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800099c0  mov     [rsp+arg_0], rbx
0x1800099c5  push    rdi
0x1800099c6  sub     rsp, 20h
0x1800099ca  mov     ebx, edx
0x1800099cc  mov     rdi, rcx
0x1800099cf  call    ??1FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::~FTMEventDelegate(void)
0x1800099d4  test    bl, 1
0x1800099d7  jz      short loc_1800099E1
0x1800099d9  mov     rcx, rdi; Block
0x1800099dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099e1  mov     rbx, [rsp+28h+arg_0]
0x1800099e6  mov     rax, rdi
0x1800099e9  add     rsp, 20h
0x1800099ed  pop     rdi
0x1800099ee  retn
```
