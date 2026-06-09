# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001de30`
- end: `0x18001de99`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPrintWorkflowUIActivatedEventArgs@Workflow@Printing@Graphics@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dea0`
- `0x18001deb0`
- `0x18001dec0`
- `0x18001ded0`

## callees

- `0x18001db84`
- `0x18001dc18`
- `0x18001de30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001de52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001de52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  v10 = 0;
  Microsoft::WRL::Implements<Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v10,
    v6);
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v8,
    &v10);
  *a2 = 4;
  result = 0;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18001de30  mov     [rsp+arg_0], rbx
0x18001de35  push    rdi
0x18001de36  sub     rsp, 20h
0x18001de3a  mov     qword ptr [r8], 0
0x18001de41  mov     ecx, 40h ; '@'; cb
0x18001de46  mov     dword ptr [rdx], 0
0x18001de4c  mov     rbx, r8
0x18001de4f  mov     rdi, rdx
0x18001de52  call    cs:__imp_CoTaskMemAlloc
0x18001de58  mov     r8, rax
0x18001de5b  test    rax, rax
0x18001de5e  jnz     short loc_18001DE67
0x18001de60  mov     eax, 8007000Eh
0x18001de65  jmp     short loc_18001DE8E
0x18001de67  lea     rdx, [rsp+28h+arg_8]
0x18001de6c  mov     [rsp+28h+arg_8], 0
0x18001de74  call    ?FillArrayWithIid@?$Implements@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@UIActivatedEventArgsWithUser@234@U?$CloakedIid@UIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@78@VFtmBase@78@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001de79  lea     rdx, [rsp+28h+arg_8]
0x18001de7e  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIPrintWorkflowUIActivatedEventArgs@Workflow@Printing@Graphics@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001de83  mov     dword ptr [rdi], 4
0x18001de89  xor     eax, eax
0x18001de8b  mov     [rbx], r8
0x18001de8e  mov     rbx, [rsp+28h+arg_0]
0x18001de93  add     rsp, 20h
0x18001de97  pop     rdi
0x18001de98  retn
```
