# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001e8b0`
- end: `0x18001e91a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e920`

## callees

- `0x18001e700`
- `0x18001e8b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_70dba485_cd56_4f15_9f82_86b1460e09a8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001e8b0  mov     [rsp+arg_0], rbx
0x18001e8b5  push    rdi
0x18001e8b6  sub     rsp, 20h
0x18001e8ba  mov     qword ptr [r8], 0
0x18001e8c1  mov     ecx, 30h ; '0'; cb
0x18001e8c6  mov     dword ptr [rdx], 0
0x18001e8cc  mov     rbx, r8
0x18001e8cf  mov     rdi, rdx
0x18001e8d2  call    cs:__imp_CoTaskMemAlloc
0x18001e8d8  mov     r8, rax
0x18001e8db  test    rax, rax
0x18001e8de  jnz     short loc_18001E8E7
0x18001e8e0  mov     eax, 8007000Eh
0x18001e8e5  jmp     short loc_18001E90F
0x18001e8e7  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001e8ee  lea     rdx, [rsp+28h+arg_8]
0x18001e8f3  mov     [rsp+28h+arg_8], 1
0x18001e8fb  movdqu  xmmword ptr [rax], xmm0
0x18001e8ff  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIDACredUIInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001e904  mov     dword ptr [rdi], 3
0x18001e90a  xor     eax, eax
0x18001e90c  mov     [rbx], r8
0x18001e90f  mov     rbx, [rsp+28h+arg_0]
0x18001e914  add     rsp, 20h
0x18001e918  pop     rdi
0x18001e919  retn
```
