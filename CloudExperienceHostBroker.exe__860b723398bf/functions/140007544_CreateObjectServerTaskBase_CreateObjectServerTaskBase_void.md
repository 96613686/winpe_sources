# CreateObjectServerTaskBase::~CreateObjectServerTaskBase(void)

- ea: `0x140007544`
- end: `0x14000756d`
- name: `??1CreateObjectServerTaskBase@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(wil::details **this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007840`

## callees

- `0x14000330c`
- `0x140004340`

## pseudocode

```c
void __fastcall CreateObjectServerTaskBase::~CreateObjectServerTaskBase(wil::details **this, void *a2)
{
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this + 11,
    a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 5);
}

```

## disassembly

```asm
0x140007544  push    rbx
0x140007546  sub     rsp, 20h
0x14000754a  mov     rbx, rcx
0x14000754d  add     rcx, 58h ; 'X'
0x140007551  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007556  lea     rcx, [rbx+50h]
0x14000755a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000755f  lea     rcx, [rbx+28h]
0x140007563  add     rsp, 20h
0x140007567  pop     rbx
0x140007568  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
