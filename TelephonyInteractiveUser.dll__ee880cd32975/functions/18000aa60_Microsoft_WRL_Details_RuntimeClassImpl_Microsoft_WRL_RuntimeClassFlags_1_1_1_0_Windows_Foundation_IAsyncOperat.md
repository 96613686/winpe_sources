# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetIids

- ea: `0x18000aa60`
- end: `0x18000aacd`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetIids`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aa40`
- `0x18000aae0`

## callees

- `0x18000aa60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa82`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_00000036_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000aa60  mov     [rsp+arg_0], rbx
0x18000aa65  push    rdi
0x18000aa66  sub     rsp, 20h
0x18000aa6a  mov     qword ptr [r8], 0
0x18000aa71  mov     ecx, 30h ; '0'; cb
0x18000aa76  mov     dword ptr [rdx], 0
0x18000aa7c  mov     rbx, r8
0x18000aa7f  mov     rdi, rdx
0x18000aa82  call    cs:__imp_CoTaskMemAlloc
0x18000aa88  test    rax, rax
0x18000aa8b  jnz     short loc_18000AA94
0x18000aa8d  mov     eax, 8007000Eh
0x18000aa92  jmp     short loc_18000AAC2
0x18000aa94  movups  xmm0, xmmword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data1
0x18000aa9b  movdqu  xmmword ptr [rax], xmm0
0x18000aa9f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000aaa6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000aaab  movups  xmm0, xmmword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data1
0x18000aab2  movdqu  xmmword ptr [rax+20h], xmm0
0x18000aab7  mov     dword ptr [rdi], 3
0x18000aabd  mov     [rbx], rax
0x18000aac0  xor     eax, eax
0x18000aac2  mov     rbx, [rsp+28h+arg_0]
0x18000aac7  add     rsp, 20h
0x18000aacb  pop     rdi
0x18000aacc  retn
```
