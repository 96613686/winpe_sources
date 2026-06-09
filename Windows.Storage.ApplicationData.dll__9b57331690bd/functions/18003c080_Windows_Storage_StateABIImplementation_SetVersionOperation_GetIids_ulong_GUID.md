# Windows::Storage::StateABIImplementation::SetVersionOperation::GetIids(ulong *,_GUID * *)

- ea: `0x18003c080`
- end: `0x18003c0ea`
- name: `?GetIids@SetVersionOperation@StateABIImplementation@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::ClearOperation *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c0f0`

## callees

- `0x18003bdfc`
- `0x18003c080`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c0a2`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::SetVersionOperation::GetIids(
        Windows::Storage::StateABIImplementation::ClearOperation *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> >,Microsoft::WRL::FtmBase> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  index = 1;
  *v5 = GUID_5a648006_843a_4da9_865b_9d26e5dfad7b;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 3;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x18003c080  mov     [rsp+arg_0], rbx
0x18003c085  push    rdi
0x18003c086  sub     rsp, 20h
0x18003c08a  mov     qword ptr [iids], 0
0x18003c091  mov     ecx, 30h ; '0'; cb
0x18003c096  mov     dword ptr [iidCount], 0
0x18003c09c  mov     rbx, iids
0x18003c09f  mov     rdi, iidCount
0x18003c0a2  call    cs:__imp_CoTaskMemAlloc
0x18003c0a8  mov     iids, rax; iids
0x18003c0ab  test    rax, rax
0x18003c0ae  jnz     short loc_18003C0B7
0x18003c0b0  mov     eax, 8007000Eh
0x18003c0b5  jmp     short loc_18003C0DF
0x18003c0b7  movups  xmm0, xmmword ptr cs:_GUID_5a648006_843a_4da9_865b_9d26e5dfad7b.Data1
0x18003c0be  lea     iidCount, [rsp+28h+index]; index
0x18003c0c3  mov     [rsp+28h+index], 1
0x18003c0cb  movdqu  xmmword ptr [rax], xmm0
0x18003c0cf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetVersionAsyncOperationName@StateABIImplementation@Storage@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003c0d4  mov     dword ptr [rdi], 3
0x18003c0da  xor     eax, eax
0x18003c0dc  mov     [rbx], iids
0x18003c0df  mov     rbx, [rsp+28h+arg_0]
0x18003c0e4  add     rsp, 20h
0x18003c0e8  pop     rdi
0x18003c0e9  retn
```
