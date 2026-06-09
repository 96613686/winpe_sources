# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ec30`
- end: `0x18001ec9a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIRasCredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eca0`

## callees

- `0x18001e7fc`
- `0x18001ec30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ec52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ec52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001ec30  mov     [rsp+arg_0], rbx
0x18001ec35  push    rdi
0x18001ec36  sub     rsp, 20h
0x18001ec3a  mov     qword ptr [r8], 0
0x18001ec41  mov     ecx, 30h ; '0'; cb
0x18001ec46  mov     dword ptr [rdx], 0
0x18001ec4c  mov     rbx, r8
0x18001ec4f  mov     rdi, rdx
0x18001ec52  call    cs:__imp_CoTaskMemAlloc
0x18001ec58  mov     r8, rax
0x18001ec5b  test    rax, rax
0x18001ec5e  jnz     short loc_18001EC67
0x18001ec60  mov     eax, 8007000Eh
0x18001ec65  jmp     short loc_18001EC8F
0x18001ec67  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001ec6e  lea     rdx, [rsp+28h+arg_8]
0x18001ec73  mov     [rsp+28h+arg_8], 1
0x18001ec7b  movdqu  xmmword ptr [rax], xmm0
0x18001ec7f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIRasCredUIInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001ec84  mov     dword ptr [rdi], 3
0x18001ec8a  xor     eax, eax
0x18001ec8c  mov     [rbx], r8
0x18001ec8f  mov     rbx, [rsp+28h+arg_0]
0x18001ec94  add     rsp, 20h
0x18001ec98  pop     rdi
0x18001ec99  retn
```
