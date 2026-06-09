# MF::AsyncOperation<Windows::Graphics::Imaging::SoftwareBitmap *>::GetIids(ulong *,_GUID * *)

- ea: `0x180033070`
- end: `0x1800330da`
- name: `?GetIids@?$AsyncOperation@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@MF@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800330e0`

## callees

- `0x180032f20`
- `0x180033070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033092`

## pseudocode

```c
__int64 __fastcall MF::AsyncOperation<Windows::Graphics::Imaging::SoftwareBitmap *>::GetIids(
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
  *v5 = GUID_c4a10980_714b_5501_8da2_dbdacce70f73;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>>::FillArrayWithIid(
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
0x180033070  mov     [rsp+arg_0], rbx
0x180033075  push    rdi
0x180033076  sub     rsp, 20h
0x18003307a  mov     qword ptr [r8], 0
0x180033081  mov     ecx, 30h ; '0'; cb
0x180033086  mov     dword ptr [rdx], 0
0x18003308c  mov     rbx, r8
0x18003308f  mov     rdi, rdx
0x180033092  call    cs:__imp_CoTaskMemAlloc
0x180033098  mov     r8, rax
0x18003309b  test    rax, rax
0x18003309e  jnz     short loc_1800330A7
0x1800330a0  mov     eax, 8007000Eh
0x1800330a5  jmp     short loc_1800330CF
0x1800330a7  movups  xmm0, xmmword ptr cs:_GUID_c4a10980_714b_5501_8da2_dbdacce70f73.Data1
0x1800330ae  lea     rdx, [rsp+28h+arg_8]
0x1800330b3  mov     [rsp+28h+arg_8], 1
0x1800330bb  movdqu  xmmword ptr [rax], xmm0
0x1800330bf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>>::FillArrayWithIid(ulong *,_GUID *)
0x1800330c4  mov     dword ptr [rdi], 3
0x1800330ca  xor     eax, eax
0x1800330cc  mov     [rbx], r8
0x1800330cf  mov     rbx, [rsp+28h+arg_0]
0x1800330d4  add     rsp, 20h
0x1800330d8  pop     rdi
0x1800330d9  retn
```
