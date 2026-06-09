# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete

- ea: `0x18000ae80`
- end: `0x18000af52`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000ae80`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000aed2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000aed2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v3; // r8d
  unsigned int v5; // edi
  __int64 result; // rax
  int v7; // ett
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed __int32 v10; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)(a1 + 56);
  v10 = -2;
  _InterlockedCompareExchange(&v10, v3, -2);
  if ( v10 == 4 )
  {
    v5 = -2147483634;
    RoOriginateError(2147483662LL);
    return v5;
  }
  else
  {
    result = *(unsigned int *)(a1 + 32);
    while ( (_DWORD)result )
    {
      v7 = result;
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 32), result + 1, result);
      if ( v7 == (_DWORD)result )
      {
        v8 = *(_QWORD *)(a1 + 24);
        v5 = 0;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        *a2 = *(_QWORD *)(a1 + 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        {
          v9 = *(_QWORD *)(a1 + 24);
          if ( v9 )
          {
            *(_QWORD *)(a1 + 24) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
        return v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ae80  mov     [rsp+arg_10], rbx
0x18000ae85  mov     [rsp+arg_18], rsi
0x18000ae8a  push    rdi
0x18000ae8b  sub     rsp, 30h
0x18000ae8f  mov     rax, cs:__security_cookie
0x18000ae96  xor     rax, rsp
0x18000ae99  mov     [rsp+38h+var_10], rax
0x18000ae9e  mov     qword ptr [rdx], 0
0x18000aea5  mov     rsi, rdx
0x18000aea8  mov     r8d, [rcx+38h]
0x18000aeac  mov     rbx, rcx
0x18000aeaf  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x18000aeb7  mov     eax, [rsp+38h+var_18]
0x18000aebb  lock cmpxchg [rsp+38h+var_18], r8d
0x18000aec2  cmp     [rsp+38h+var_18], 4
0x18000aec7  jnz     short loc_18000AEDA
0x18000aec9  mov     edi, 8000000Eh
0x18000aece  xor     edx, edx
0x18000aed0  mov     ecx, edi
0x18000aed2  call    cs:__imp_RoOriginateError
0x18000aed8  jmp     short loc_18000AF4E
0x18000aeda  mov     eax, [rcx+20h]
0x18000aedd  jmp     short loc_18000AEE9
0x18000aedf  lea     ecx, [rax+1]
0x18000aee2  lock cmpxchg [rbx+20h], ecx
0x18000aee7  jz      short loc_18000AF0A
0x18000aee9  test    eax, eax
0x18000aeeb  jnz     short loc_18000AEDF
0x18000aeed  mov     rcx, [rsp+38h+var_10]
0x18000aef2  xor     rcx, rsp; StackCookie
0x18000aef5  call    __security_check_cookie
0x18000aefa  mov     rbx, [rsp+38h+arg_10]
0x18000aeff  mov     rsi, [rsp+38h+arg_18]
0x18000af04  add     rsp, 30h
0x18000af08  pop     rdi
0x18000af09  retn
0x18000af0a  mov     rcx, [rbx+18h]
0x18000af0e  xor     edi, edi
0x18000af10  test    rcx, rcx
0x18000af13  jz      short loc_18000AF21
0x18000af15  mov     rax, [rcx]
0x18000af18  mov     rax, [rax+8]
0x18000af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af21  mov     rax, [rbx+18h]
0x18000af25  mov     [rsi], rax
0x18000af28  or      eax, 0FFFFFFFFh
0x18000af2b  lock xadd [rbx+20h], eax
0x18000af30  cmp     eax, 1
0x18000af33  jnz     short loc_18000AF4E
0x18000af35  mov     rcx, [rbx+18h]
0x18000af39  test    rcx, rcx
0x18000af3c  jz      short loc_18000AF4E
0x18000af3e  mov     [rbx+18h], rdi
0x18000af42  mov     rdx, [rcx]
0x18000af45  mov     rax, [rdx+10h]
0x18000af49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af4e  mov     eax, edi
0x18000af50  jmp     short loc_18000AEED
```
