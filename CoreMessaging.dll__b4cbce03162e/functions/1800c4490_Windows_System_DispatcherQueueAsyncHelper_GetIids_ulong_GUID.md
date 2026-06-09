# Windows::System::DispatcherQueueAsyncHelper::GetIids(ulong *,_GUID * *)

- ea: `0x1800c4490`
- end: `0x1800c44fa`
- name: `?GetIids@DispatcherQueueAsyncHelper@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::System::DispatcherQueueAsyncHelper *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4500`

## callees

- `0x1800c4164`
- `0x1800c4490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c44b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c44b2`

## pseudocode

```c
__int64 __fastcall Windows::System::DispatcherQueueAsyncHelper::GetIids(
        Windows::System::DispatcherQueueAsyncHelper *this,
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
  *v5 = GUID_5a648006_843a_4da9_865b_9d26e5dfad7b;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
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
0x1800c4490  mov     [rsp+arg_0], rbx
0x1800c4495  push    rdi
0x1800c4496  sub     rsp, 20h
0x1800c449a  mov     qword ptr [r8], 0
0x1800c44a1  mov     ecx, 30h ; '0'; cb
0x1800c44a6  mov     dword ptr [rdx], 0
0x1800c44ac  mov     rbx, r8
0x1800c44af  mov     rdi, rdx
0x1800c44b2  call    cs:__imp_CoTaskMemAlloc
0x1800c44b8  mov     r8, rax
0x1800c44bb  test    rax, rax
0x1800c44be  jnz     short loc_1800C44C7
0x1800c44c0  mov     eax, 8007000Eh
0x1800c44c5  jmp     short loc_1800C44EF
0x1800c44c7  movups  xmm0, xmmword ptr cs:_GUID_5a648006_843a_4da9_865b_9d26e5dfad7b.Data1
0x1800c44ce  lea     rdx, [rsp+28h+arg_8]
0x1800c44d3  mov     [rsp+28h+arg_8], 1
0x1800c44db  movdqu  xmmword ptr [rax], xmm0
0x1800c44df  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x1800c44e4  mov     dword ptr [rdi], 3
0x1800c44ea  xor     eax, eax
0x1800c44ec  mov     [rbx], r8
0x1800c44ef  mov     rbx, [rsp+28h+arg_0]
0x1800c44f4  add     rsp, 20h
0x1800c44f8  pop     rdi
0x1800c44f9  retn
```
