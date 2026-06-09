# MDMPushProvider::CreatePushUpgradeScheduleActivity::~CreatePushUpgradeScheduleActivity(void)

- ea: `0x140013398`
- end: `0x1400133bd`
- name: `??1CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400151d8`
- `0x140019b70`

## callees

- `0x1400131f8`
- `0x140016740`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::~CreatePushUpgradeScheduleActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
{
  *(_QWORD *)this = &MDMPushProvider::CreatePushUpgradeScheduleActivity::`vftable';
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x140013398  push    rbx
0x14001339a  sub     rsp, 20h
0x14001339e  lea     rax, ??_7CreatePushUpgradeScheduleActivity@MDMPushProvider@@6B@; const MDMPushProvider::CreatePushUpgradeScheduleActivity::`vftable'
0x1400133a5  mov     rbx, rcx
0x1400133a8  mov     [rcx], rax
0x1400133ab  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400133b0  mov     rcx, rbx
0x1400133b3  add     rsp, 20h
0x1400133b7  pop     rbx
0x1400133b8  jmp     ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
