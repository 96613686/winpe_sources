# Windows::Networking::UX::Internal::CEAPGenericIdentityInput::GetIids(ulong *,_GUID * *)

- ea: `0x18001e930`
- end: `0x18001e99a`
- name: `?GetIids@CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CEAPGenericIdentityInput *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e9a0`

## callees

- `0x18001e724`
- `0x18001e930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e952`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CEAPGenericIdentityInput::GetIids(
        Windows::Networking::UX::Internal::CEAPGenericIdentityInput *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001e930  mov     [rsp+arg_0], rbx
0x18001e935  push    rdi
0x18001e936  sub     rsp, 20h
0x18001e93a  mov     qword ptr [r8], 0
0x18001e941  mov     ecx, 30h ; '0'; cb
0x18001e946  mov     dword ptr [rdx], 0
0x18001e94c  mov     rbx, r8
0x18001e94f  mov     rdi, rdx
0x18001e952  call    cs:__imp_CoTaskMemAlloc
0x18001e958  mov     r8, rax
0x18001e95b  test    rax, rax
0x18001e95e  jnz     short loc_18001E967
0x18001e960  mov     eax, 8007000Eh
0x18001e965  jmp     short loc_18001E98F
0x18001e967  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001e96e  lea     rdx, [rsp+28h+arg_8]
0x18001e973  mov     [rsp+28h+arg_8], 1
0x18001e97b  movdqu  xmmword ptr [rax], xmm0
0x18001e97f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIEAPGenericIdentityInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001e984  mov     dword ptr [rdi], 3
0x18001e98a  xor     eax, eax
0x18001e98c  mov     [rbx], r8
0x18001e98f  mov     rbx, [rsp+28h+arg_0]
0x18001e994  add     rsp, 20h
0x18001e998  pop     rdi
0x18001e999  retn
```
