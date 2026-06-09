# LowLightFusionImpl::GetIids(ulong *,_GUID * *)

- ea: `0x1800a63a0`
- end: `0x1800a63ff`
- name: `?GetIids@LowLightFusionImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(LowLightFusionImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a6410`

## callees

- `0x1800a5660`
- `0x1800a63a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a63c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a63c2`

## pseudocode

```c
__int64 __fastcall LowLightFusionImpl::GetIids(LowLightFusionImpl *this, unsigned int *a2, struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionInternal>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionInternal2>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 1;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800a63a0  mov     [rsp+arg_0], rbx
0x1800a63a5  push    rdi
0x1800a63a6  sub     rsp, 20h
0x1800a63aa  mov     qword ptr [r8], 0
0x1800a63b1  mov     ecx, 10h; cb
0x1800a63b6  mov     dword ptr [rdx], 0
0x1800a63bc  mov     rbx, r8
0x1800a63bf  mov     rdi, rdx
0x1800a63c2  call    cs:__imp_CoTaskMemAlloc
0x1800a63c8  mov     r8, rax
0x1800a63cb  test    rax, rax
0x1800a63ce  jnz     short loc_1800A63D7
0x1800a63d0  mov     eax, 8007000Eh
0x1800a63d5  jmp     short loc_1800A63F4
0x1800a63d7  lea     rdx, [rsp+28h+arg_8]
0x1800a63dc  mov     [rsp+28h+arg_8], 0
0x1800a63e4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$CloakedIid@UILowLightFusionInternal@Core@Media@Windows@@@23@UIWeakReferenceSource@@U?$CloakedIid@UILowLightFusionInternal2@Core@Media@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionInternal>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Media::Core::ILowLightFusionInternal2>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800a63e9  mov     dword ptr [rdi], 1
0x1800a63ef  xor     eax, eax
0x1800a63f1  mov     [rbx], r8
0x1800a63f4  mov     rbx, [rsp+28h+arg_0]
0x1800a63f9  add     rsp, 20h
0x1800a63fd  pop     rdi
0x1800a63fe  retn
```
