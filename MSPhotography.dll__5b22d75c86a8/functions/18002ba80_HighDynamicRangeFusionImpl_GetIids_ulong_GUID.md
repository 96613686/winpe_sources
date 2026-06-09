# HighDynamicRangeFusionImpl::GetIids(ulong *,_GUID * *)

- ea: `0x18002ba80`
- end: `0x18002baea`
- name: `?GetIids@HighDynamicRangeFusionImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(HighDynamicRangeFusionImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002baf0`

## callees

- `0x18002b788`
- `0x18002ba80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002baa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002baa2`

## pseudocode

```c
__int64 __fastcall HighDynamicRangeFusionImpl::GetIids(
        HighDynamicRangeFusionImpl *this,
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
  *v5 = GUID_f8c0817a_38f7_4188_8753_68e56896f072;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionResultInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18002ba80  mov     [rsp+arg_0], rbx
0x18002ba85  push    rdi
0x18002ba86  sub     rsp, 20h
0x18002ba8a  mov     qword ptr [r8], 0
0x18002ba91  mov     ecx, 30h ; '0'; cb
0x18002ba96  mov     dword ptr [rdx], 0
0x18002ba9c  mov     rbx, r8
0x18002ba9f  mov     rdi, rdx
0x18002baa2  call    cs:__imp_CoTaskMemAlloc
0x18002baa8  mov     r8, rax
0x18002baab  test    rax, rax
0x18002baae  jnz     short loc_18002BAB7
0x18002bab0  mov     eax, 8007000Eh
0x18002bab5  jmp     short loc_18002BADF
0x18002bab7  movups  xmm0, xmmword ptr cs:_GUID_f8c0817a_38f7_4188_8753_68e56896f072.Data1
0x18002babe  lea     rdx, [rsp+28h+arg_8]
0x18002bac3  mov     [rsp+28h+arg_8], 1
0x18002bacb  movdqu  xmmword ptr [rax], xmm0
0x18002bacf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UILowLightFusionResultInternal@Core@Media@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionResultInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18002bad4  mov     dword ptr [rdi], 3
0x18002bada  xor     eax, eax
0x18002badc  mov     [rbx], r8
0x18002badf  mov     rbx, [rsp+28h+arg_0]
0x18002bae4  add     rsp, 20h
0x18002bae8  pop     rdi
0x18002bae9  retn
```
