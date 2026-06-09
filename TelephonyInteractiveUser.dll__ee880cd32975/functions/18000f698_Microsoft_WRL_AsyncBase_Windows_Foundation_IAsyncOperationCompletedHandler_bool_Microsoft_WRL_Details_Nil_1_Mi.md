# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState

- ea: `0x18000f698`
- end: `0x18000f719`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState`
- size: `129`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800089f0`
- `0x180008d50`
- `0x1800091c0`
- `0x180009570`
- `0x1800098d0`
- `0x18000f1c0`

## callees

- `0x180001dc0`
- `0x18000f698`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
        __int64 a1,
        signed __int32 a2)
{
  signed __int32 v2; // r8d
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+0h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v2, -2);
  switch ( a2 )
  {
    case 0:
      v4 = v6;
      if ( v6 != -1 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 1:
    case 2:
    case 3:
      v4 = v6;
      if ( v6 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 4:
      v4 = v6;
      if ( (unsigned int)(v6 - 1) <= 3 )
        return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f698  sub     rsp, 18h
0x18000f69c  mov     rax, cs:__security_cookie
0x18000f6a3  xor     rax, rsp
0x18000f6a6  mov     [rsp+18h+var_10], rax
0x18000f6ab  mov     r8d, [rcx+38h]
0x18000f6af  mov     r9, rcx
0x18000f6b2  mov     [rsp+18h+var_18], 0FFFFFFFEh
0x18000f6b9  mov     eax, [rsp+18h+var_18]
0x18000f6bc  lock cmpxchg [rsp+18h+var_18], r8d
0x18000f6c2  mov     eax, edx
0x18000f6c4  test    edx, edx
0x18000f6c6  jz      short loc_18000F70D
0x18000f6c8  sub     eax, 1
0x18000f6cb  jz      short loc_18000F704
0x18000f6cd  sub     eax, 1
0x18000f6d0  jz      short loc_18000F704
0x18000f6d2  sub     eax, 1
0x18000f6d5  jz      short loc_18000F704
0x18000f6d7  cmp     eax, 1
0x18000f6da  jnz     short loc_18000F715
0x18000f6dc  mov     ecx, [rsp+18h+var_18]
0x18000f6df  lea     eax, [rcx-1]
0x18000f6e2  cmp     eax, 3
0x18000f6e5  ja      short loc_18000F715
0x18000f6e7  mov     eax, ecx
0x18000f6e9  lock cmpxchg [r9+38h], edx
0x18000f6ef  setz    al
0x18000f6f2  mov     rcx, [rsp+18h+var_10]
0x18000f6f7  xor     rcx, rsp; StackCookie
0x18000f6fa  call    __security_check_cookie
0x18000f6ff  add     rsp, 18h
0x18000f703  retn
0x18000f704  mov     ecx, [rsp+18h+var_18]
0x18000f707  test    ecx, ecx
0x18000f709  jnz     short loc_18000F715
0x18000f70b  jmp     short loc_18000F6E7
0x18000f70d  mov     ecx, [rsp+18h+var_18]
0x18000f710  cmp     ecx, 0FFFFFFFFh
0x18000f713  jz      short loc_18000F6E7
0x18000f715  xor     al, al
0x18000f717  jmp     short loc_18000F6F2
```
