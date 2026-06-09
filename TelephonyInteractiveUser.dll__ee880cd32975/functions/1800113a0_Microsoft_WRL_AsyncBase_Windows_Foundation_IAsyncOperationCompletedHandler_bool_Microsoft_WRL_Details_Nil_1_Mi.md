# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Status

- ea: `0x1800113a0`
- end: `0x180011423`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Status`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800113a0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800113f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800113f7`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_Status(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // r8d
  signed __int32 v3; // ecx
  unsigned int v4; // ebx
  signed __int32 v6; // [rsp+20h] [rbp-18h] BYREF
  signed __int32 v7; // [rsp+24h] [rbp-14h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v7 = -2;
  _InterlockedCompareExchange(&v7, v2, -2);
  *a2 = v7;
  v3 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v3, -2);
  if ( v6 == 4 )
  {
    v4 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v4 = 0;
    if ( v6 == -1 )
      return (unsigned int)-2147483623;
  }
  return v4;
}

```

## disassembly

```asm
0x1800113a0  mov     r11, rsp
0x1800113a3  push    rbx
0x1800113a4  sub     rsp, 30h
0x1800113a8  mov     rax, cs:__security_cookie
0x1800113af  xor     rax, rsp
0x1800113b2  mov     [rsp+38h+var_10], rax
0x1800113b7  mov     r8d, [rcx+38h]
0x1800113bb  mov     r9d, 0FFFFFFFEh
0x1800113c1  mov     [r11-14h], r9d
0x1800113c5  mov     eax, [rsp+38h+var_14]
0x1800113c9  lock cmpxchg [r11-14h], r8d
0x1800113cf  mov     r8d, [r11-14h]
0x1800113d3  mov     [rdx], r8d
0x1800113d6  mov     ecx, [rcx+38h]
0x1800113d9  mov     [r11-18h], r9d
0x1800113dd  mov     eax, [rsp+38h+var_18]
0x1800113e1  lock cmpxchg [rsp+38h+var_18], ecx
0x1800113e7  cmp     [rsp+38h+var_18], 4
0x1800113ec  jnz     short loc_1800113FF
0x1800113ee  mov     ebx, 8000000Eh
0x1800113f3  xor     edx, edx
0x1800113f5  mov     ecx, ebx
0x1800113f7  call    cs:__imp_RoOriginateError
0x1800113fd  jmp     short loc_18001140E
0x1800113ff  xor     ebx, ebx
0x180011401  mov     eax, 80000019h
0x180011406  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x18001140b  cmovz   ebx, eax
0x18001140e  mov     eax, ebx
0x180011410  mov     rcx, [rsp+38h+var_10]
0x180011415  xor     rcx, rsp; StackCookie
0x180011418  call    __security_check_cookie
0x18001141d  add     rsp, 30h
0x180011421  pop     rbx
0x180011422  retn
```
