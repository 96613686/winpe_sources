# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x180017628`
- end: `0x18001773f`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800160c0`
- `0x1800160f0`
- `0x180016b70`

## callees

- `0x18001740c`
- `0x180017478`
- `0x180017628`
- `0x18002b010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      a1,
      v7);
  }
}

```

## disassembly

```asm
0x180017628  mov     [rsp+arg_0], rbx
0x18001762d  mov     [rsp+arg_8], rbp
0x180017632  push    rdi
0x180017633  sub     rsp, 30h
0x180017637  mov     rbx, rcx
0x18001763a  mov     edi, 1
0x18001763f  cmp     edx, 2
0x180017642  jnz     loc_1800176D1
0x180017648  mov     eax, edi
0x18001764a  lock xadd [rcx+0FCh], eax
0x180017652  add     eax, edi
0x180017654  cmp     eax, edi
0x180017656  jnz     loc_18001772F
0x18001765c  lea     rbp, [rcx+120h]
0x180017663  mov     rcx, [rcx+108h]
0x18001766a  mov     r9, rbp
0x18001766d  mov     rax, [rcx]
0x180017670  mov     rax, [rax+8]
0x180017674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017679  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x180017681  setz    cl
0x180017684  mov     eax, edi
0x180017686  lock xadd [rbx+100h], eax
0x18001768e  add     eax, edi
0x180017690  cmp     eax, edi
0x180017692  jnz     short loc_1800176C3
0x180017694  mov     rcx, [rbx+108h]
0x18001769b  mov     r9, rbp
0x18001769e  mov     r8d, 800704C7h
0x1800176a4  mov     edx, edi
0x1800176a6  mov     rax, [rcx]
0x1800176a9  mov     rax, [rax+8]
0x1800176ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b2  or      eax, 0FFFFFFFFh
0x1800176b5  lock xadd [rbx+104h], eax
0x1800176bd  cmp     eax, edi
0x1800176bf  jnz     short loc_18001772F
0x1800176c1  jmp     short loc_1800176C7
0x1800176c3  test    cl, cl
0x1800176c5  jz      short loc_18001772F
0x1800176c7  mov     rcx, rbx
0x1800176ca  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x1800176cf  jmp     short loc_18001772F
0x1800176d1  cmp     edx, edi
0x1800176d3  jnz     short loc_18001772F
0x1800176d5  mov     eax, edi
0x1800176d7  lock xadd [rcx+100h], eax
0x1800176df  add     eax, edi
0x1800176e1  cmp     eax, edi
0x1800176e3  jnz     short loc_18001772F
0x1800176e5  mov     rcx, [rcx+108h]
0x1800176ec  lea     r9, [rbx+120h]
0x1800176f3  mov     edx, edi
0x1800176f5  mov     rax, [rcx]
0x1800176f8  mov     rax, [rax+8]
0x1800176fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017701  test    eax, eax
0x180017703  js      short loc_180017725
0x180017705  cmp     byte ptr [rbx+129h], 0
0x18001770c  jz      short loc_180017725
0x18001770e  or      eax, 0FFFFFFFFh
0x180017711  lock xadd [rbx+118h], eax
0x180017719  cmp     eax, edi
0x18001771b  jnz     short loc_18001772F
0x18001771d  mov     edx, [rbx+11Ch]
0x180017723  jmp     short loc_180017727
0x180017725  mov     edx, eax
0x180017727  mov     rcx, rbx
0x18001772a  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18001772f  mov     rbx, [rsp+38h+arg_0]
0x180017734  mov     rbp, [rsp+38h+arg_8]
0x180017739  add     rsp, 30h
0x18001773d  pop     rdi
0x18001773e  retn
```
