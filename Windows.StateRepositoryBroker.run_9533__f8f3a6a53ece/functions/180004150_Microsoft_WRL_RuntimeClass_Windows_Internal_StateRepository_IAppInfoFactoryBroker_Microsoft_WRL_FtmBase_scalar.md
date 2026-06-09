# Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x180004150`
- end: `0x180004184`
- name: `??_G?$RuntimeClass@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002160`
- `0x180003f30`
- `0x180004150`

## pseudocode

```c
void *__fastcall Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004150  mov     [rsp+arg_0], rbx
0x180004155  push    rdi
0x180004156  sub     rsp, 20h
0x18000415a  mov     ebx, edx
0x18000415c  mov     rdi, rcx
0x18000415f  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>(void)
0x180004164  test    bl, 1
0x180004167  jz      short loc_180004176
0x180004169  mov     edx, 40h ; '@'
0x18000416e  mov     rcx, rdi; Block
0x180004171  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004176  mov     rbx, [rsp+28h+arg_0]
0x18000417b  mov     rax, rdi
0x18000417e  add     rsp, 20h
0x180004182  pop     rdi
0x180004183  retn
```
