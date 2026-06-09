# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetResults(uchar *)

- ea: `0x18000b350`
- end: `0x18000b40a`
- name: `?GetResults@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAE@Z`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000b350`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000b3c4`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000b3c4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b402`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b402`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetResults(
        __int64 a1,
        _BYTE *a2)
{
  signed __int32 v4; // ecx
  int v5; // ebx
  signed __int32 v7; // [rsp+20h] [rbp-20h] BYREF
  signed __int32 v8; // [rsp+24h] [rbp-1Ch] BYREF
  signed __int32 v9; // [rsp+28h] [rbp-18h] BYREF

  *a2 = 0;
  v8 = -2;
  _InterlockedCompareExchange(&v8, *(_DWORD *)(a1 - 120), -2);
  if ( v8 != 3 )
  {
    if ( v8 != 1 )
    {
      v5 = -2147483634;
      RoOriginateError(2147483662LL);
      return (unsigned int)v5;
    }
    goto LABEL_8;
  }
  v9 = -2;
  v4 = *(_DWORD *)(a1 - 120);
  v7 = 0;
  _InterlockedCompareExchange(&v9, v4, -2);
  if ( v9 == 3 )
  {
    _InterlockedCompareExchange(&v7, *(_DWORD *)(a1 - 116), v7);
    if ( *(_QWORD *)(a1 - 128) )
      SetRestrictedErrorInfo();
    v5 = v7;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 >= 0 )
  {
LABEL_8:
    v5 = 0;
    *a2 = *(_BYTE *)(a1 + 120);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b350  mov     [rsp-18h+arg_10], rbx
0x18000b355  push    rbp
0x18000b356  push    rsi
0x18000b357  push    rdi
0x18000b358  mov     rbp, rsp
0x18000b35b  sub     rsp, 40h
0x18000b35f  mov     rax, cs:__security_cookie
0x18000b366  xor     rax, rsp
0x18000b369  mov     [rbp+var_10], rax
0x18000b36d  mov     rdi, rcx
0x18000b370  mov     byte ptr [rdx], 0
0x18000b373  mov     ecx, 0FFFFFFFEh
0x18000b378  mov     rsi, rdx
0x18000b37b  mov     [rbp+var_1C], ecx
0x18000b37e  mov     r8d, [rdi-78h]
0x18000b382  mov     eax, [rbp+var_1C]
0x18000b385  lock cmpxchg [rbp+var_1C], r8d
0x18000b38b  cmp     [rbp+var_1C], 3
0x18000b38f  jnz     short loc_18000B3F3
0x18000b391  mov     [rbp+var_18], ecx
0x18000b394  mov     ecx, [rdi-78h]
0x18000b397  mov     eax, [rbp+var_18]
0x18000b39a  mov     [rbp+var_20], 0
0x18000b3a1  lock cmpxchg [rbp+var_18], ecx
0x18000b3a6  cmp     [rbp+var_18], 3
0x18000b3aa  jz      short loc_18000B3B0
0x18000b3ac  xor     ebx, ebx
0x18000b3ae  jmp     short loc_18000B3CD
0x18000b3b0  mov     ecx, [rdi-74h]
0x18000b3b3  mov     eax, [rbp+var_20]
0x18000b3b6  lock cmpxchg [rbp+var_20], ecx
0x18000b3bb  mov     rcx, [rdi-80h]
0x18000b3bf  test    rcx, rcx
0x18000b3c2  jz      short loc_18000B3CA
0x18000b3c4  call    cs:__imp_SetRestrictedErrorInfo
0x18000b3ca  mov     ebx, [rbp+var_20]
0x18000b3cd  test    ebx, ebx
0x18000b3cf  js      short loc_18000B3D8
0x18000b3d1  mov     al, [rdi+78h]
0x18000b3d4  xor     ebx, ebx
0x18000b3d6  mov     [rsi], al
0x18000b3d8  mov     eax, ebx
0x18000b3da  mov     rcx, [rbp+var_10]
0x18000b3de  xor     rcx, rsp; StackCookie
0x18000b3e1  call    __security_check_cookie
0x18000b3e6  mov     rbx, [rsp+40h+arg_10]
0x18000b3eb  add     rsp, 40h
0x18000b3ef  pop     rdi
0x18000b3f0  pop     rsi
0x18000b3f1  pop     rbp
0x18000b3f2  retn
0x18000b3f3  cmp     [rbp+var_1C], 1
0x18000b3f7  jz      short loc_18000B3D1
0x18000b3f9  mov     ebx, 8000000Eh
0x18000b3fe  xor     edx, edx
0x18000b400  mov     ecx, ebx
0x18000b402  call    cs:__imp_RoOriginateError
0x18000b408  jmp     short loc_18000B3D8
```
