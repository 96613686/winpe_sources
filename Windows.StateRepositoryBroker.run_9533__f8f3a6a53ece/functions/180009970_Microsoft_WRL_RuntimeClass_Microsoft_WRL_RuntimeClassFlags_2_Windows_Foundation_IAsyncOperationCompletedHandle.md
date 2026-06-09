# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x180009970`
- end: `0x1800099ab`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `59`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002154`
- `0x18000539c`
- `0x180009970`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  *((_DWORD *)Block + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)Block + 4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009970  mov     [rsp+arg_0], rbx
0x180009975  push    rdi
0x180009976  sub     rsp, 20h
0x18000997a  mov     ebx, edx
0x18000997c  mov     rdi, rcx
0x18000997f  mov     dword ptr [rcx+2Ch], 0C0000001h
0x180009986  add     rcx, 20h ; ' '
0x18000998a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000998f  nop
0x180009990  test    bl, 1
0x180009993  jz      short loc_18000999D
0x180009995  mov     rcx, rdi; Block
0x180009998  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000999d  mov     rax, rdi
0x1800099a0  mov     rbx, [rsp+28h+arg_0]
0x1800099a5  add     rsp, 20h
0x1800099a9  pop     rdi
0x1800099aa  retn
```
