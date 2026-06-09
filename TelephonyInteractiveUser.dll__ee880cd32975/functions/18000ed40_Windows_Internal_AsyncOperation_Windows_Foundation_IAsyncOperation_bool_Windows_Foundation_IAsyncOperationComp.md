# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Run(void)

- ea: `0x18000ed40`
- end: `0x18000ee4d`
- name: `?Run@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAXXZ`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000ed40`
- `0x180010524`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000edb2`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000edb2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Run(
        __int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // rbx
  __int64 result; // rax
  int v5; // eax
  __int64 v6; // rdx
  signed __int32 v7; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int32 v8; // [rsp+34h] [rbp-Ch] BYREF

  v8 = 0;
  v7 = -2;
  _InterlockedCompareExchange(&v7, *(_DWORD *)(a1 - 144), -2);
  if ( v7 )
  {
    v7 = -2;
    _InterlockedCompareExchange(&v7, *(_DWORD *)(a1 - 144), -2);
    if ( v7 != 3 )
      goto LABEL_6;
    _InterlockedCompareExchange((volatile signed __int32 *)&v8, *(_DWORD *)(a1 - 140), v8);
    if ( *(_QWORD *)(a1 - 152) )
      SetRestrictedErrorInfo();
    v2 = v8;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_6:
      v2 = 2147943623LL;
      v8 = -2147023673;
    }
  }
  else
  {
    v2 = v8;
  }
  v3 = a1 - 208;
  result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v3 + 256));
  if ( (_DWORD)result == 1 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v3 + 264) + 8LL))(
           *(_QWORD *)(v3 + 264),
           1,
           v2,
           v3 + 288);
    if ( v5 >= 0 && *(_BYTE *)(v3 + 297) )
    {
      result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF);
      if ( (_DWORD)result != 1 )
        return result;
      v6 = *(unsigned int *)(v3 + 284);
    }
    else
    {
      v6 = (unsigned int)v5;
    }
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
             (volatile signed __int32 *)v3,
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp-8+arg_8], rbx
0x18000ed45  push    rbp
0x18000ed46  mov     rbp, rsp
0x18000ed49  sub     rsp, 40h
0x18000ed4d  mov     rax, cs:__security_cookie
0x18000ed54  xor     rax, rsp
0x18000ed57  mov     [rbp+var_8], rax
0x18000ed5b  mov     rbx, rcx
0x18000ed5e  mov     [rbp+var_C], 0
0x18000ed65  mov     ecx, 0FFFFFFFEh
0x18000ed6a  mov     [rbp+var_10], ecx
0x18000ed6d  mov     edx, [rbx-90h]
0x18000ed73  mov     eax, [rbp+var_10]
0x18000ed76  lock cmpxchg [rbp+var_10], edx
0x18000ed7b  cmp     [rbp+var_10], 0
0x18000ed7f  jz      short loc_18000EDCD
0x18000ed81  mov     [rbp+var_10], ecx
0x18000ed84  mov     ecx, [rbx-90h]
0x18000ed8a  mov     eax, [rbp+var_10]
0x18000ed8d  lock cmpxchg [rbp+var_10], ecx
0x18000ed92  cmp     [rbp+var_10], 3
0x18000ed96  jnz     short loc_18000EDC1
0x18000ed98  mov     ecx, [rbx-8Ch]
0x18000ed9e  mov     eax, [rbp+var_C]
0x18000eda1  lock cmpxchg [rbp+var_C], ecx
0x18000eda6  mov     rcx, [rbx-98h]
0x18000edad  test    rcx, rcx
0x18000edb0  jz      short loc_18000EDB8
0x18000edb2  call    cs:__imp_SetRestrictedErrorInfo
0x18000edb8  mov     r8d, [rbp+var_C]
0x18000edbc  test    r8d, r8d
0x18000edbf  js      short loc_18000EDD1
0x18000edc1  mov     r8d, 800704C7h
0x18000edc7  mov     [rbp+var_C], r8d
0x18000edcb  jmp     short loc_18000EDD1
0x18000edcd  mov     r8d, [rbp+var_C]
0x18000edd1  mov     edx, 1
0x18000edd6  add     rbx, 0FFFFFFFFFFFFFF30h
0x18000eddd  mov     eax, edx
0x18000eddf  lock xadd [rbx+100h], eax
0x18000ede7  add     eax, edx
0x18000ede9  cmp     eax, edx
0x18000edeb  jnz     short loc_18000EE36
0x18000eded  mov     rcx, [rbx+108h]
0x18000edf4  lea     r9, [rbx+120h]
0x18000edfb  mov     rax, [rcx]
0x18000edfe  mov     rax, [rax+8]
0x18000ee02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee07  test    eax, eax
0x18000ee09  js      short loc_18000EE2C
0x18000ee0b  cmp     byte ptr [rbx+129h], 0
0x18000ee12  jz      short loc_18000EE2C
0x18000ee14  or      eax, 0FFFFFFFFh
0x18000ee17  lock xadd [rbx+118h], eax
0x18000ee1f  cmp     eax, 1
0x18000ee22  jnz     short loc_18000EE36
0x18000ee24  mov     edx, [rbx+11Ch]
0x18000ee2a  jmp     short loc_18000EE2E
0x18000ee2c  mov     edx, eax
0x18000ee2e  mov     rcx, rbx
0x18000ee31  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18000ee36  mov     rcx, [rbp+var_8]
0x18000ee3a  xor     rcx, rsp; StackCookie
0x18000ee3d  call    __security_check_cookie
0x18000ee42  mov     rbx, [rsp+40h+arg_8]
0x18000ee47  add     rsp, 40h
0x18000ee4b  pop     rbp
0x18000ee4c  retn
```
