# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Close

- ea: `0x180008d50`
- end: `0x180008dd0`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Close`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180008d50`
- `0x18000f698`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008db5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008db5`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Close(
        __int64 a1)
{
  int v1; // edx
  _DWORD *v2; // r10
  unsigned int v3; // ebx
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
         a1,
         4) )
  {
    v3 = 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 144LL))(v2);
  }
  else
  {
    v4 = v2[14];
    v6 = -2;
    _InterlockedCompareExchange(&v6, v4, -2);
    if ( v6 == v1 )
    {
      return 0;
    }
    else
    {
      v3 = -2147483635;
      RoOriginateError(2147483661LL);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180008d50  push    rbx
0x180008d52  sub     rsp, 30h
0x180008d56  mov     rax, cs:__security_cookie
0x180008d5d  xor     rax, rsp
0x180008d60  mov     [rsp+38h+var_10], rax
0x180008d65  mov     edx, 4
0x180008d6a  mov     r10, rcx
0x180008d6d  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TransitionToState
0x180008d72  test    al, al
0x180008d74  jz      short loc_180008D8C
0x180008d76  mov     rax, [r10]
0x180008d79  xor     ebx, ebx
0x180008d7b  mov     rcx, r10
0x180008d7e  mov     rax, [rax+90h]
0x180008d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d8a  jmp     short loc_180008DBB
0x180008d8c  mov     ecx, [r10+38h]
0x180008d90  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x180008d98  mov     eax, [rsp+38h+var_18]
0x180008d9c  lock cmpxchg [rsp+38h+var_18], ecx
0x180008da2  cmp     [rsp+38h+var_18], edx
0x180008da6  jnz     short loc_180008DAC
0x180008da8  xor     ebx, ebx
0x180008daa  jmp     short loc_180008DBB
0x180008dac  mov     ebx, 8000000Dh
0x180008db1  xor     edx, edx
0x180008db3  mov     ecx, ebx
0x180008db5  call    cs:__imp_RoOriginateError
0x180008dbb  mov     eax, ebx
0x180008dbd  mov     rcx, [rsp+38h+var_10]
0x180008dc2  xor     rcx, rsp; StackCookie
0x180008dc5  call    __security_check_cookie
0x180008dca  add     rsp, 30h
0x180008dce  pop     rbx
0x180008dcf  retn
```
