# CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo::GetIids(ulong *,_GUID * *)

- ea: `0x180034840`
- end: `0x18003489f`
- name: `?GetIids@ConfigureRetailDemo@RetailDemo@CloudExperienceHostBroker@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800348b0`

## callees

- `0x18003481c`
- `0x180034840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034862`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo::GetIids(
        CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostBroker::RetailDemo::IConfigureRetailDemo>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180034840  mov     [rsp+arg_0], rbx
0x180034845  push    rdi
0x180034846  sub     rsp, 20h
0x18003484a  mov     qword ptr [r8], 0
0x180034851  mov     ecx, 20h ; ' '; cb
0x180034856  mov     dword ptr [rdx], 0
0x18003485c  mov     rbx, r8
0x18003485f  mov     rdi, rdx
0x180034862  call    cs:__imp_CoTaskMemAlloc
0x180034868  mov     r8, rax
0x18003486b  test    rax, rax
0x18003486e  jnz     short loc_180034877
0x180034870  mov     eax, 8007000Eh
0x180034875  jmp     short loc_180034894
0x180034877  lea     rdx, [rsp+28h+arg_8]
0x18003487c  mov     [rsp+28h+arg_8], 0
0x180034884  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIConfigureRetailDemo@RetailDemo@CloudExperienceHostBroker@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostBroker::RetailDemo::IConfigureRetailDemo>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180034889  mov     dword ptr [rdi], 2
0x18003488f  xor     eax, eax
0x180034891  mov     [rbx], r8
0x180034894  mov     rbx, [rsp+28h+arg_0]
0x180034899  add     rsp, 20h
0x18003489d  pop     rdi
0x18003489e  retn
```
