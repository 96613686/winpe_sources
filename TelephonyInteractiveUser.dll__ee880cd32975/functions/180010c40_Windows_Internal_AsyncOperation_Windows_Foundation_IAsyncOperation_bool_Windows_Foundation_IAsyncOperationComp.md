# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x180010c40`
- end: `0x180010d57`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cfb0`

## callees

- `0x180010478`
- `0x180010524`
- `0x180010c40`
- `0x180019010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  int v6; // eax
  __int64 v7; // rdx

  if ( (_DWORD)a2 == 2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) != 1 )
      return;
    v4 = a1 + 288;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
      *(_QWORD *)(a1 + 264),
      a2,
      a3,
      a1 + 288);
    v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
        *(_QWORD *)(a1 + 264),
        1,
        2147943623LL,
        v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) != 1 )
        return;
    }
    else if ( !v5 )
    {
      return;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
  }
  else if ( (_DWORD)a2 == 1 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
           *(_QWORD *)(a1 + 264),
           1,
           a3,
           a1 + 288);
    if ( v6 >= 0 && *(_BYTE *)(a1 + 297) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF) != 1 )
        return;
      v7 = *(unsigned int *)(a1 + 284);
    }
    else
    {
      v7 = (unsigned int)v6;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      (volatile signed __int32 *)a1,
      v7);
  }
}

```

## disassembly

```asm
0x180010c40  mov     [rsp+arg_0], rbx
0x180010c45  mov     [rsp+arg_8], rbp
0x180010c4a  push    rdi
0x180010c4b  sub     rsp, 30h
0x180010c4f  mov     rbx, rcx
0x180010c52  mov     edi, 1
0x180010c57  cmp     edx, 2
0x180010c5a  jnz     loc_180010CE9
0x180010c60  mov     eax, edi
0x180010c62  lock xadd [rcx+0FCh], eax
0x180010c6a  add     eax, edi
0x180010c6c  cmp     eax, edi
0x180010c6e  jnz     loc_180010D47
0x180010c74  lea     rbp, [rcx+120h]
0x180010c7b  mov     rcx, [rcx+108h]
0x180010c82  mov     r9, rbp
0x180010c85  mov     rax, [rcx]
0x180010c88  mov     rax, [rax+8]
0x180010c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c91  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x180010c99  setz    cl
0x180010c9c  mov     eax, edi
0x180010c9e  lock xadd [rbx+100h], eax
0x180010ca6  add     eax, edi
0x180010ca8  cmp     eax, edi
0x180010caa  jnz     short loc_180010CDB
0x180010cac  mov     rcx, [rbx+108h]
0x180010cb3  mov     r9, rbp
0x180010cb6  mov     r8d, 800704C7h
0x180010cbc  mov     edx, edi
0x180010cbe  mov     rax, [rcx]
0x180010cc1  mov     rax, [rax+8]
0x180010cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cca  or      eax, 0FFFFFFFFh
0x180010ccd  lock xadd [rbx+104h], eax
0x180010cd5  cmp     eax, edi
0x180010cd7  jnz     short loc_180010D47
0x180010cd9  jmp     short loc_180010CDF
0x180010cdb  test    cl, cl
0x180010cdd  jz      short loc_180010D47
0x180010cdf  mov     rcx, rbx
0x180010ce2  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x180010ce7  jmp     short loc_180010D47
0x180010ce9  cmp     edx, edi
0x180010ceb  jnz     short loc_180010D47
0x180010ced  mov     eax, edi
0x180010cef  lock xadd [rcx+100h], eax
0x180010cf7  add     eax, edi
0x180010cf9  cmp     eax, edi
0x180010cfb  jnz     short loc_180010D47
0x180010cfd  mov     rcx, [rcx+108h]
0x180010d04  lea     r9, [rbx+120h]
0x180010d0b  mov     edx, edi
0x180010d0d  mov     rax, [rcx]
0x180010d10  mov     rax, [rax+8]
0x180010d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d19  test    eax, eax
0x180010d1b  js      short loc_180010D3D
0x180010d1d  cmp     byte ptr [rbx+129h], 0
0x180010d24  jz      short loc_180010D3D
0x180010d26  or      eax, 0FFFFFFFFh
0x180010d29  lock xadd [rbx+118h], eax
0x180010d31  cmp     eax, edi
0x180010d33  jnz     short loc_180010D47
0x180010d35  mov     edx, [rbx+11Ch]
0x180010d3b  jmp     short loc_180010D3F
0x180010d3d  mov     edx, eax
0x180010d3f  mov     rcx, rbx
0x180010d42  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x180010d47  mov     rbx, [rsp+38h+arg_0]
0x180010d4c  mov     rbp, [rsp+38h+arg_8]
0x180010d51  add     rsp, 30h
0x180010d55  pop     rdi
0x180010d56  retn
```
