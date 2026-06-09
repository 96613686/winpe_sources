# HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled(void)

- ea: `0x14000a3f0`
- end: `0x14000a415`
- name: `??1VerifyAllInstalled@HostNameVerifierProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyAllInstalled *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000ed9c`
- `0x140011b69`

## callees

- `0x140009da8`
- `0x14000ac68`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled(
        HostNameVerifierProvider::VerifyAllInstalled *this)
{
  *(_QWORD *)this = &HostNameVerifierProvider::VerifyAllInstalled::`vftable';
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x14000a3f0  push    rbx
0x14000a3f2  sub     rsp, 20h
0x14000a3f6  lea     rax, ??_7VerifyAllInstalled@HostNameVerifierProvider@@6B@; const HostNameVerifierProvider::VerifyAllInstalled::`vftable'
0x14000a3fd  mov     rbx, rcx
0x14000a400  mov     [rcx], rax
0x14000a403  call    ?Destroy@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14000a408  mov     rcx, rbx
0x14000a40b  add     rsp, 20h
0x14000a40f  pop     rbx
0x14000a410  jmp     ??1?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
