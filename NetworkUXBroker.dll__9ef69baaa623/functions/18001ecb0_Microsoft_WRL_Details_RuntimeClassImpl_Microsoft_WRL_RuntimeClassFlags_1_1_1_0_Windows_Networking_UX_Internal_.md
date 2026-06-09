# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ecb0`
- end: `0x18001ed1a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIRasThirdpartyAuthTokenInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ed20`

## callees

- `0x18001e820`
- `0x18001ecb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecd2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001ecb0  mov     [rsp+arg_0], rbx
0x18001ecb5  push    rdi
0x18001ecb6  sub     rsp, 20h
0x18001ecba  mov     qword ptr [r8], 0
0x18001ecc1  mov     ecx, 30h ; '0'; cb
0x18001ecc6  mov     dword ptr [rdx], 0
0x18001eccc  mov     rbx, r8
0x18001eccf  mov     rdi, rdx
0x18001ecd2  call    cs:__imp_CoTaskMemAlloc
0x18001ecd8  mov     r8, rax
0x18001ecdb  test    rax, rax
0x18001ecde  jnz     short loc_18001ECE7
0x18001ece0  mov     eax, 8007000Eh
0x18001ece5  jmp     short loc_18001ED0F
0x18001ece7  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001ecee  lea     rdx, [rsp+28h+arg_8]
0x18001ecf3  mov     [rsp+28h+arg_8], 1
0x18001ecfb  movdqu  xmmword ptr [rax], xmm0
0x18001ecff  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIRasThirdpartyAuthTokenInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001ed04  mov     dword ptr [rdi], 3
0x18001ed0a  xor     eax, eax
0x18001ed0c  mov     [rbx], r8
0x18001ed0f  mov     rbx, [rsp+28h+arg_0]
0x18001ed14  add     rsp, 20h
0x18001ed18  pop     rdi
0x18001ed19  retn
```
