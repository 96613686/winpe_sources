# Windows::Networking::UX::Internal::CNetworkLocationInput::GetIids(ulong *,_GUID * *)

- ea: `0x18001eb30`
- end: `0x18001eb9a`
- name: `?GetIids@CNetworkLocationInput@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CNetworkLocationInput *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eba0`

## callees

- `0x18001e7b4`
- `0x18001eb30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eb52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eb52`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CNetworkLocationInput::GetIids(
        Windows::Networking::UX::Internal::CNetworkLocationInput *this,
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
  *v5 = GUID_70dba485_cd56_4f15_9f82_86b1460e09a8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::INetworkLocationInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001eb30  mov     [rsp+arg_0], rbx
0x18001eb35  push    rdi
0x18001eb36  sub     rsp, 20h
0x18001eb3a  mov     qword ptr [r8], 0
0x18001eb41  mov     ecx, 30h ; '0'; cb
0x18001eb46  mov     dword ptr [rdx], 0
0x18001eb4c  mov     rbx, r8
0x18001eb4f  mov     rdi, rdx
0x18001eb52  call    cs:__imp_CoTaskMemAlloc
0x18001eb58  mov     r8, rax
0x18001eb5b  test    rax, rax
0x18001eb5e  jnz     short loc_18001EB67
0x18001eb60  mov     eax, 8007000Eh
0x18001eb65  jmp     short loc_18001EB8F
0x18001eb67  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001eb6e  lea     rdx, [rsp+28h+arg_8]
0x18001eb73  mov     [rsp+28h+arg_8], 1
0x18001eb7b  movdqu  xmmword ptr [rax], xmm0
0x18001eb7f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UINetworkLocationInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::INetworkLocationInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001eb84  mov     dword ptr [rdi], 3
0x18001eb8a  xor     eax, eax
0x18001eb8c  mov     [rbx], r8
0x18001eb8f  mov     rbx, [rsp+28h+arg_0]
0x18001eb94  add     rsp, 20h
0x18001eb98  pop     rdi
0x18001eb99  retn
```
