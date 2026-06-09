# CloudExperienceHostBroker::Cortana::OOBECortanaManager::GetIids(ulong *,_GUID * *)

- ea: `0x1800315e0`
- end: `0x18003164a`
- name: `?GetIids@OOBECortanaManager@Cortana@CloudExperienceHostBroker@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana::OOBECortanaManager *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031650`

## callees

- `0x18001e018`
- `0x1800315e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031602`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManager::GetIids(
        CloudExperienceHostBroker::Cortana::OOBECortanaManager *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_4afc051c_427a_4779_a10e_dfc65c1546ad;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800315e0  mov     [rsp+arg_0], rbx
0x1800315e5  push    rdi
0x1800315e6  sub     rsp, 20h
0x1800315ea  mov     qword ptr [r8], 0
0x1800315f1  mov     ecx, 30h ; '0'; cb
0x1800315f6  mov     dword ptr [rdx], 0
0x1800315fc  mov     rbx, r8
0x1800315ff  mov     rdi, rdx
0x180031602  call    cs:__imp_CoTaskMemAlloc
0x180031608  mov     r8, rax
0x18003160b  test    rax, rax
0x18003160e  jnz     short loc_180031617
0x180031610  mov     eax, 8007000Eh
0x180031615  jmp     short loc_18003163F
0x180031617  movups  xmm0, xmmword ptr cs:_GUID_4afc051c_427a_4779_a10e_dfc65c1546ad.Data1
0x18003161e  lea     rdx, [rsp+28h+arg_8]
0x180031623  mov     [rsp+28h+arg_8], 1
0x18003162b  movdqu  xmmword ptr [rax], xmm0
0x18003162f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180031634  mov     dword ptr [rdi], 3
0x18003163a  xor     eax, eax
0x18003163c  mov     [rbx], r8
0x18003163f  mov     rbx, [rsp+28h+arg_0]
0x180031644  add     rsp, 20h
0x180031648  pop     rdi
0x180031649  retn
```
