# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_ErrorCode(long *)

- ea: `0x1800111d0`
- end: `0x18001127d`
- name: `?get_ErrorCode@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAJ@Z`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800111d0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18001125d`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18001125d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011217`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011217`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_ErrorCode(
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
0x1800111d0  mov     [rsp+arg_10], rbx
0x1800111d5  push    rdi
0x1800111d6  sub     rsp, 30h
0x1800111da  mov     rax, cs:__security_cookie
0x1800111e1  xor     rax, rsp
0x1800111e4  mov     [rsp+38h+var_10], rax
0x1800111e9  mov     rdi, rdx
0x1800111ec  mov     rdx, rcx
0x1800111ef  mov     ecx, 0FFFFFFFEh
0x1800111f4  mov     [rsp+38h+var_18], ecx
0x1800111f8  mov     r8d, [rdx+38h]
0x1800111fc  mov     eax, [rsp+38h+var_18]
0x180011200  lock cmpxchg [rsp+38h+var_18], r8d
0x180011207  cmp     [rsp+38h+var_18], 4
0x18001120c  jnz     short loc_18001121F
0x18001120e  mov     ebx, 8000000Eh
0x180011213  xor     edx, edx
0x180011215  mov     ecx, ebx
0x180011217  call    cs:__imp_RoOriginateError
0x18001121d  jmp     short loc_180011247
0x18001121f  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x180011224  jnz     short loc_18001122D
0x180011226  mov     ebx, 80000019h
0x18001122b  jmp     short loc_180011247
0x18001122d  mov     [rsp+38h+var_18], ecx
0x180011231  xor     ebx, ebx
0x180011233  mov     ecx, [rdx+38h]
0x180011236  mov     eax, [rsp+38h+var_18]
0x18001123a  lock cmpxchg [rsp+38h+var_18], ecx
0x180011240  cmp     [rsp+38h+var_18], 3
0x180011245  jz      short loc_18001124B
0x180011247  mov     [rdi], ebx
0x180011249  jmp     short loc_180011263
0x18001124b  mov     eax, [rdi]
0x18001124d  mov     ecx, [rdx+3Ch]
0x180011250  lock cmpxchg [rdi], ecx
0x180011254  mov     rcx, [rdx+30h]
0x180011258  test    rcx, rcx
0x18001125b  jz      short loc_180011263
0x18001125d  call    cs:__imp_SetRestrictedErrorInfo
0x180011263  mov     eax, ebx
0x180011265  mov     rcx, [rsp+38h+var_10]
0x18001126a  xor     rcx, rsp; StackCookie
0x18001126d  call    __security_check_cookie
0x180011272  mov     rbx, [rsp+38h+arg_10]
0x180011277  add     rsp, 30h
0x18001127b  pop     rdi
0x18001127c  retn
```
