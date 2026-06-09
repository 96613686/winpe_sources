# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_ErrorCode

- ea: `0x180011110`
- end: `0x1800111bd`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_ErrorCode`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180011110`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18001119d`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18001119d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011157`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011157`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::get_ErrorCode(
        __int64 a1,
        volatile signed __int32 *a2)
{
  unsigned int v3; // ebx
  signed __int32 v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = -2;
  _InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 56), -2);
  if ( v5 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL);
LABEL_6:
    *a2 = v3;
    return v3;
  }
  if ( v5 == -1 )
  {
    v3 = -2147483623;
    goto LABEL_6;
  }
  v5 = -2;
  v3 = 0;
  _InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 56), -2);
  if ( v5 != 3 )
    goto LABEL_6;
  _InterlockedCompareExchange(a2, *(_DWORD *)(a1 + 60), *a2);
  if ( *(_QWORD *)(a1 + 48) )
    SetRestrictedErrorInfo();
  return v3;
}

```

## disassembly

```asm
0x180011110  mov     [rsp+arg_10], rbx
0x180011115  push    rdi
0x180011116  sub     rsp, 30h
0x18001111a  mov     rax, cs:__security_cookie
0x180011121  xor     rax, rsp
0x180011124  mov     [rsp+38h+var_10], rax
0x180011129  mov     rdi, rdx
0x18001112c  mov     rdx, rcx
0x18001112f  mov     ecx, 0FFFFFFFEh
0x180011134  mov     [rsp+38h+var_18], ecx
0x180011138  mov     r8d, [rdx+38h]
0x18001113c  mov     eax, [rsp+38h+var_18]
0x180011140  lock cmpxchg [rsp+38h+var_18], r8d
0x180011147  cmp     [rsp+38h+var_18], 4
0x18001114c  jnz     short loc_18001115F
0x18001114e  mov     ebx, 8000000Eh
0x180011153  xor     edx, edx
0x180011155  mov     ecx, ebx
0x180011157  call    cs:__imp_RoOriginateError
0x18001115d  jmp     short loc_180011187
0x18001115f  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x180011164  jnz     short loc_18001116D
0x180011166  mov     ebx, 80000019h
0x18001116b  jmp     short loc_180011187
0x18001116d  mov     [rsp+38h+var_18], ecx
0x180011171  xor     ebx, ebx
0x180011173  mov     ecx, [rdx+38h]
0x180011176  mov     eax, [rsp+38h+var_18]
0x18001117a  lock cmpxchg [rsp+38h+var_18], ecx
0x180011180  cmp     [rsp+38h+var_18], 3
0x180011185  jz      short loc_18001118B
0x180011187  mov     [rdi], ebx
0x180011189  jmp     short loc_1800111A3
0x18001118b  mov     eax, [rdi]
0x18001118d  mov     ecx, [rdx+3Ch]
0x180011190  lock cmpxchg [rdi], ecx
0x180011194  mov     rcx, [rdx+30h]
0x180011198  test    rcx, rcx
0x18001119b  jz      short loc_1800111A3
0x18001119d  call    cs:__imp_SetRestrictedErrorInfo
0x1800111a3  mov     eax, ebx
0x1800111a5  mov     rcx, [rsp+38h+var_10]
0x1800111aa  xor     rcx, rsp; StackCookie
0x1800111ad  call    __security_check_cookie
0x1800111b2  mov     rbx, [rsp+38h+arg_10]
0x1800111b7  add     rsp, 30h
0x1800111bb  pop     rdi
0x1800111bc  retn
```
