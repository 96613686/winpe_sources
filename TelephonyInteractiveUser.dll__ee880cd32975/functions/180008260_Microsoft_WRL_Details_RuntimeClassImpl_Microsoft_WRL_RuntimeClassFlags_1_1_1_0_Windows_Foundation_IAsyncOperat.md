# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::AddRef

- ea: `0x180008260`
- end: `0x1800082b6`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::AddRef`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800082c0`
- `0x1800082d0`
- `0x1800082e0`

## callees

- `0x180008260`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  bool v5; // zf
  signed __int64 v6; // rax
  signed __int32 v7; // r9d

  v1 = *(_QWORD *)(a1 + 168);
  v3 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v3;
    v4 = v1 + 1;
    v6 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 168), v1 + 1, v1);
    v5 = v1 == v6;
    v1 = v6;
    if ( v5 )
      return v4;
  }
  while ( 1 )
  {
    v7 = *(_DWORD *)(2 * v1 + 0x10);
    if ( v7 == 0x7FFFFFFF )
      break;
    if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v7 + 1, v7) )
      return (unsigned int)(v7 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x180008260  mov     rdx, [rcx+0A8h]
0x180008267  mov     r9, rcx
0x18000826a  mov     r8d, 7FFFFFFFh
0x180008270  test    rdx, rdx
0x180008273  js      short loc_1800082A0
0x180008275  cmp     edx, r8d
0x180008278  jz      short loc_1800082B0
0x18000827a  lea     rcx, [rdx+1]
0x18000827e  mov     rax, rdx
0x180008281  lock cmpxchg [r9+0A8h], rcx
0x18000828a  mov     rdx, rax
0x18000828d  jnz     short loc_180008270
0x18000828f  jmp     short loc_1800082B3
0x180008291  lea     ecx, [r9+1]
0x180008295  mov     eax, r9d
0x180008298  lock cmpxchg [rdx+rdx+10h], ecx
0x18000829e  jz      short loc_1800082AC
0x1800082a0  mov     r9d, [rdx+rdx+10h]
0x1800082a5  cmp     r9d, r8d
0x1800082a8  jnz     short loc_180008291
0x1800082aa  jmp     short loc_1800082B0
0x1800082ac  lea     r8d, [r9+1]
0x1800082b0  mov     ecx, r8d
0x1800082b3  mov     eax, ecx
0x1800082b5  retn
```
