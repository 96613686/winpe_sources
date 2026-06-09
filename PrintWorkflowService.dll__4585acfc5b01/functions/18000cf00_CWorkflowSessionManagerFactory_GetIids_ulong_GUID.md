# CWorkflowSessionManagerFactory::GetIids(ulong *,_GUID * *)

- ea: `0x18000cf00`
- end: `0x18000cf5f`
- name: `?GetIids@CWorkflowSessionManagerFactory@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CWorkflowSessionManagerFactory *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf70`

## callees

- `0x18000c210`
- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf22`

## pseudocode

```c
__int64 __fastcall CWorkflowSessionManagerFactory::GetIids(
        CWorkflowSessionManagerFactory *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManagerStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18000cf00  mov     [rsp+arg_0], rbx
0x18000cf05  push    rdi
0x18000cf06  sub     rsp, 20h
0x18000cf0a  mov     qword ptr [r8], 0
0x18000cf11  mov     ecx, 20h ; ' '; cb
0x18000cf16  mov     dword ptr [rdx], 0
0x18000cf1c  mov     rbx, r8
0x18000cf1f  mov     rdi, rdx
0x18000cf22  call    cs:__imp_CoTaskMemAlloc
0x18000cf28  mov     r8, rax
0x18000cf2b  test    rax, rax
0x18000cf2e  jnz     short loc_18000CF37
0x18000cf30  mov     eax, 8007000Eh
0x18000cf35  jmp     short loc_18000CF54
0x18000cf37  lea     rdx, [rsp+28h+arg_8]
0x18000cf3c  mov     [rsp+28h+arg_8], 0
0x18000cf44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIWorkflowSessionManagerStatics@Workflow@Printing@Internal@Graphics@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManagerStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000cf49  mov     dword ptr [rdi], 2
0x18000cf4f  xor     eax, eax
0x18000cf51  mov     [rbx], r8
0x18000cf54  mov     rbx, [rsp+28h+arg_0]
0x18000cf59  add     rsp, 20h
0x18000cf5d  pop     rdi
0x18000cf5e  retn
```
