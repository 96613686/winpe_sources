# Windows::Networking::UX::Internal::CPasswordChangeInput::GetIids(ulong *,_GUID * *)

- ea: `0x18001ebb0`
- end: `0x18001ec1a`
- name: `?GetIids@CPasswordChangeInput@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CPasswordChangeInput *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ec20`

## callees

- `0x18001e7d8`
- `0x18001ebb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ebd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ebd2`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CPasswordChangeInput::GetIids(
        Windows::Networking::UX::Internal::CPasswordChangeInput *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IPasswordChangeInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001ebb0  mov     [rsp+arg_0], rbx
0x18001ebb5  push    rdi
0x18001ebb6  sub     rsp, 20h
0x18001ebba  mov     qword ptr [r8], 0
0x18001ebc1  mov     ecx, 30h ; '0'; cb
0x18001ebc6  mov     dword ptr [rdx], 0
0x18001ebcc  mov     rbx, r8
0x18001ebcf  mov     rdi, rdx
0x18001ebd2  call    cs:__imp_CoTaskMemAlloc
0x18001ebd8  mov     r8, rax
0x18001ebdb  test    rax, rax
0x18001ebde  jnz     short loc_18001EBE7
0x18001ebe0  mov     eax, 8007000Eh
0x18001ebe5  jmp     short loc_18001EC0F
0x18001ebe7  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18001ebee  lea     rdx, [rsp+28h+arg_8]
0x18001ebf3  mov     [rsp+28h+arg_8], 1
0x18001ebfb  movdqu  xmmword ptr [rax], xmm0
0x18001ebff  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIPasswordChangeInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IPasswordChangeInput,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001ec04  mov     dword ptr [rdi], 3
0x18001ec0a  xor     eax, eax
0x18001ec0c  mov     [rbx], r8
0x18001ec0f  mov     rbx, [rsp+28h+arg_0]
0x18001ec14  add     rsp, 20h
0x18001ec18  pop     rdi
0x18001ec19  retn
```
