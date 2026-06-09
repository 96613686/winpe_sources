# MDMPushProvider::CreatePushLaunchScheduleActivity::~CreatePushLaunchScheduleActivity(void)

- ea: `0x14001336c`
- end: `0x140013391`
- name: `??1CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001351c`
- `0x1400199b7`

## callees

- `0x1400131f8`
- `0x140016740`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::~CreatePushLaunchScheduleActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
{
  *(_QWORD *)this = &MDMPushProvider::CreatePushLaunchScheduleActivity::`vftable';
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x14001336c  push    rbx
0x14001336e  sub     rsp, 20h
0x140013372  lea     rax, ??_7CreatePushLaunchScheduleActivity@MDMPushProvider@@6B@; const MDMPushProvider::CreatePushLaunchScheduleActivity::`vftable'
0x140013379  mov     rbx, rcx
0x14001337c  mov     [rcx], rax
0x14001337f  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140013384  mov     rcx, rbx
0x140013387  add     rsp, 20h
0x14001338b  pop     rbx
0x14001338c  jmp     ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
