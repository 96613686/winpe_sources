# MDMPushProvider::CreatePushUpgradeScheduleActivity::~CreatePushUpgradeScheduleActivity(void)

- ea: `0x140012a60`
- end: `0x140012a85`
- name: `??1CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001464c`
- `0x140018e0f`

## callees

- `0x1400128dc`
- `0x140015ad4`

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
0x140012a60  push    rbx
0x140012a62  sub     rsp, 20h
0x140012a66  lea     rax, ??_7CreatePushUpgradeScheduleActivity@MDMPushProvider@@6B@; const MDMPushProvider::CreatePushUpgradeScheduleActivity::`vftable'
0x140012a6d  mov     rbx, rcx
0x140012a70  mov     [rcx], rax
0x140012a73  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140012a78  mov     rcx, rbx
0x140012a7b  add     rsp, 20h
0x140012a7f  pop     rbx
0x140012a80  jmp     ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
