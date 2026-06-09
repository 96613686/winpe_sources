# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::put_Id

- ea: `0x180011530`
- end: `0x1800115c0`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::put_Id`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f6c`

## callees

- `0x180001dc0`
- `0x180011530`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001159f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001159f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001156c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001156c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::put_Id(
        __int64 a1,
        int a2)
{
  signed __int32 v3; // ecx
  signed __int32 v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+24h] [rbp-24h] BYREF
  wchar_t v6; // [rsp+28h] [rbp-20h]

  if ( a2 )
  {
    *(_DWORD *)(a1 + 64) = a2;
    v3 = *(_DWORD *)(a1 + 56);
    v4 = -2;
    _InterlockedCompareExchange(&v4, v3, -2);
    if ( v4 == -1 )
    {
      return 0;
    }
    else
    {
      RoOriginateError(2147483662LL);
      return 2147483662LL;
    }
  }
  else
  {
    v5 = *(_DWORD *)L"id";
    v6 = aId[2];
    RoOriginateErrorW(2147942487LL, 2, &v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180011530  sub     rsp, 48h
0x180011534  mov     rax, cs:__security_cookie
0x18001153b  xor     rax, rsp
0x18001153e  mov     [rsp+48h+var_18], rax
0x180011543  test    edx, edx
0x180011545  jnz     short loc_180011579
0x180011547  mov     eax, dword ptr cs:aId; "id"
0x18001154d  lea     r8, [rsp+48h+var_24]
0x180011552  mov     [rsp+48h+var_24], eax
0x180011556  mov     edx, 2
0x18001155b  movzx   eax, word ptr cs:aId+4; ""
0x180011562  mov     ecx, 80070057h
0x180011567  mov     [rsp+48h+var_20], ax
0x18001156c  call    cs:__imp_RoOriginateErrorW
0x180011572  mov     eax, 80070057h
0x180011577  jmp     short loc_1800115AE
0x180011579  mov     [rcx+40h], edx
0x18001157c  mov     ecx, [rcx+38h]
0x18001157f  mov     [rsp+48h+var_28], 0FFFFFFFEh
0x180011587  mov     eax, [rsp+48h+var_28]
0x18001158b  lock cmpxchg [rsp+48h+var_28], ecx
0x180011591  cmp     [rsp+48h+var_28], 0FFFFFFFFh
0x180011596  jz      short loc_1800115AC
0x180011598  xor     edx, edx
0x18001159a  mov     ecx, 8000000Eh
0x18001159f  call    cs:__imp_RoOriginateError
0x1800115a5  mov     eax, 8000000Eh
0x1800115aa  jmp     short loc_1800115AE
0x1800115ac  xor     eax, eax
0x1800115ae  mov     rcx, [rsp+48h+var_18]
0x1800115b3  xor     rcx, rsp; StackCookie
0x1800115b6  call    __security_check_cookie
0x1800115bb  add     rsp, 48h
0x1800115bf  retn
```
