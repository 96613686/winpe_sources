# MDMPushProvider::CreatePushLaunchScheduleActivity::~CreatePushLaunchScheduleActivity(void)

- ea: `0x140012a34`
- end: `0x140012a59`
- name: `??1CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012bd0`
- `0x140018c56`

## callees

- `0x1400128dc`
- `0x140015ad4`

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
0x140012a34  push    rbx
0x140012a36  sub     rsp, 20h
0x140012a3a  lea     rax, ??_7CreatePushLaunchScheduleActivity@MDMPushProvider@@6B@; const MDMPushProvider::CreatePushLaunchScheduleActivity::`vftable'
0x140012a41  mov     rbx, rcx
0x140012a44  mov     [rcx], rax
0x140012a47  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140012a4c  mov     rcx, rbx
0x140012a4f  add     rsp, 20h
0x140012a53  pop     rbx
0x140012a54  jmp     ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
