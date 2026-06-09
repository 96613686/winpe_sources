# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::Release

- ea: `0x18000e660`
- end: `0x18000e6f7`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::Release`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e490`
- `0x18000e700`
- `0x18000e710`
- `0x18000e720`

## callees

- `0x18000e660`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::Release(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *(_QWORD *)(a1 + 168);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 168), v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 16) + 88LL))(a1 + 16, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e660  push    rbx
0x18000e662  sub     rsp, 20h
0x18000e666  mov     rdx, [rcx+0A8h]
0x18000e66d  mov     r9, rcx
0x18000e670  mov     r10d, 7FFFFFFFh
0x18000e676  test    rdx, rdx
0x18000e679  js      short loc_18000E6AD
0x18000e67b  cmp     edx, r10d
0x18000e67e  jz      short loc_18000E697
0x18000e680  lea     rbx, [rdx-1]
0x18000e684  mov     rax, rdx
0x18000e687  lock cmpxchg [rcx+0A8h], rbx
0x18000e690  mov     rdx, rax
0x18000e693  jnz     short loc_18000E676
0x18000e695  jmp     short loc_18000E6BB
0x18000e697  mov     ebx, 7FFFFFFEh
0x18000e69c  jmp     short loc_18000E6EF
0x18000e69e  lea     ecx, [r8-1]
0x18000e6a2  mov     eax, r8d
0x18000e6a5  lock cmpxchg [rdx+rdx+10h], ecx
0x18000e6ab  jz      short loc_18000E6B7
0x18000e6ad  mov     r8d, [rdx+rdx+10h]
0x18000e6b2  cmp     r8d, r10d
0x18000e6b5  jnz     short loc_18000E69E
0x18000e6b7  lea     ebx, [r8-1]
0x18000e6bb  test    ebx, ebx
0x18000e6bd  jnz     short loc_18000E6EF
0x18000e6bf  test    r9, r9
0x18000e6c2  jz      short loc_18000E6D7
0x18000e6c4  lea     rcx, [r9+10h]
0x18000e6c8  mov     rax, [rcx]
0x18000e6cb  lea     edx, [rbx+1]
0x18000e6ce  mov     rax, [rax+58h]
0x18000e6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e6de  test    rcx, rcx
0x18000e6e1  jz      short loc_18000E6EF
0x18000e6e3  mov     rdx, [rcx]
0x18000e6e6  mov     rax, [rdx+10h]
0x18000e6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ef  mov     eax, ebx
0x18000e6f1  add     rsp, 20h
0x18000e6f5  pop     rbx
0x18000e6f6  retn
```
