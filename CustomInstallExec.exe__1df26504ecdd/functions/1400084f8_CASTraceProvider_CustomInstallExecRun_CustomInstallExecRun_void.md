# CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun(void)

- ea: `0x1400084f8`
- end: `0x14000851d`
- name: `??1CustomInstallExecRun@CASTraceProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CASTraceProvider::CustomInstallExecRun *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000a8a8`
- `0x14000ed8e`

## callees

- `0x14000824c`
- `0x140008a1c`

## pseudocode

```c
void __fastcall CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun(
        CASTraceProvider::CustomInstallExecRun *this)
{
  *(_QWORD *)this = &CASTraceProvider::CustomInstallExecRun::`vftable';
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x1400084f8  push    rbx
0x1400084fa  sub     rsp, 20h
0x1400084fe  lea     rax, ??_7CustomInstallExecRun@CASTraceProvider@@6B@; const CASTraceProvider::CustomInstallExecRun::`vftable'
0x140008505  mov     rbx, rcx
0x140008508  mov     [rcx], rax
0x14000850b  call    ?Destroy@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140008510  mov     rcx, rbx
0x140008513  add     rsp, 20h
0x140008517  pop     rbx
0x140008518  jmp     ??1?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
