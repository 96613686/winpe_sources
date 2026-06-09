# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Id

- ea: `0x180011290`
- end: `0x1800112fb`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Id`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180011290`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800112cf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800112cf`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Id(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // ecx
  unsigned int v3; // ebx
  signed __int32 v5; // [rsp+20h] [rbp-18h] BYREF

  *a2 = *(_DWORD *)(a1 + 64);
  v2 = *(_DWORD *)(a1 + 56);
  v5 = -2;
  _InterlockedCompareExchange(&v5, v2, -2);
  if ( v5 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v3 = 0;
    if ( v5 == -1 )
      return (unsigned int)-2147483623;
  }
  return v3;
}

```

## disassembly

```asm
0x180011290  push    rbx
0x180011292  sub     rsp, 30h
0x180011296  mov     rax, cs:__security_cookie
0x18001129d  xor     rax, rsp
0x1800112a0  mov     [rsp+38h+var_10], rax
0x1800112a5  mov     eax, [rcx+40h]
0x1800112a8  mov     [rdx], eax
0x1800112aa  mov     ecx, [rcx+38h]
0x1800112ad  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x1800112b5  mov     eax, [rsp+38h+var_18]
0x1800112b9  lock cmpxchg [rsp+38h+var_18], ecx
0x1800112bf  cmp     [rsp+38h+var_18], 4
0x1800112c4  jnz     short loc_1800112D7
0x1800112c6  mov     ebx, 8000000Eh
0x1800112cb  xor     edx, edx
0x1800112cd  mov     ecx, ebx
0x1800112cf  call    cs:__imp_RoOriginateError
0x1800112d5  jmp     short loc_1800112E6
0x1800112d7  xor     ebx, ebx
0x1800112d9  mov     eax, 80000019h
0x1800112de  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x1800112e3  cmovz   ebx, eax
0x1800112e6  mov     eax, ebx
0x1800112e8  mov     rcx, [rsp+38h+var_10]
0x1800112ed  xor     rcx, rsp; StackCookie
0x1800112f0  call    __security_check_cookie
0x1800112f5  add     rsp, 30h
0x1800112f9  pop     rbx
0x1800112fa  retn
```
