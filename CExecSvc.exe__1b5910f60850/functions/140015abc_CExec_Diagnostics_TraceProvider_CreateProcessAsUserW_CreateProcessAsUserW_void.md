# CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::~CreateProcessAsUserW(void)

- ea: `0x140015abc`
- end: `0x140015ae1`
- name: `??1CreateProcessAsUserW@TraceProvider@Diagnostics@CExec@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140022f38`

## callees

- `0x1400155e4`
- `0x1400166ec`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::~CreateProcessAsUserW(
        CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *this)
{
  *(_QWORD *)this = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x140015abc  push    rbx
0x140015abe  sub     rsp, 20h
0x140015ac2  lea     rax, ??_7CreateProcessAsUserW@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable'
0x140015ac9  mov     rbx, rcx
0x140015acc  mov     [rcx], rax
0x140015acf  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140015ad4  mov     rcx, rbx
0x140015ad7  add     rsp, 20h
0x140015adb  pop     rbx
0x140015adc  jmp     ??1?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
