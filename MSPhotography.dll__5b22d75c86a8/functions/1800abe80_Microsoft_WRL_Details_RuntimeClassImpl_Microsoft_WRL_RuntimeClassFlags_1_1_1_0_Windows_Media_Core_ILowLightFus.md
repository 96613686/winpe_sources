# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::ILowLightFusionResult,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionResultInternal>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800abe80`
- end: `0x1800abeea`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UILowLightFusionResult@Core@Media@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UILowLightFusionResultInternal@Core@Media@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800abef0`
- `0x1800abf00`

## callees

- `0x18002b788`
- `0x1800abe80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800abea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800abea2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::ILowLightFusionResult,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionResultInternal>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_78edbe35_27a0_42e0_9cd3_738d2089de9c;
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
0x1800abe80  mov     [rsp+arg_0], rbx
0x1800abe85  push    rdi
0x1800abe86  sub     rsp, 20h
0x1800abe8a  mov     qword ptr [r8], 0
0x1800abe91  mov     ecx, 30h ; '0'; cb
0x1800abe96  mov     dword ptr [rdx], 0
0x1800abe9c  mov     rbx, r8
0x1800abe9f  mov     rdi, rdx
0x1800abea2  call    cs:__imp_CoTaskMemAlloc
0x1800abea8  mov     r8, rax
0x1800abeab  test    rax, rax
0x1800abeae  jnz     short loc_1800ABEB7
0x1800abeb0  mov     eax, 8007000Eh
0x1800abeb5  jmp     short loc_1800ABEDF
0x1800abeb7  movups  xmm0, xmmword ptr cs:_GUID_78edbe35_27a0_42e0_9cd3_738d2089de9c.Data1
0x1800abebe  lea     rdx, [rsp+28h+arg_8]
0x1800abec3  mov     [rsp+28h+arg_8], 1
0x1800abecb  movdqu  xmmword ptr [rax], xmm0
0x1800abecf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UILowLightFusionResultInternal@Core@Media@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionResultInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800abed4  mov     dword ptr [rdi], 3
0x1800abeda  xor     eax, eax
0x1800abedc  mov     [rbx], r8
0x1800abedf  mov     rbx, [rsp+28h+arg_0]
0x1800abee4  add     rsp, 20h
0x1800abee8  pop     rdi
0x1800abee9  retn
```
