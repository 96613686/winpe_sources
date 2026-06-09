# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x18001a1e4`
- end: `0x18001a284`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `160`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016bc0`
- `0x18001a3d4`

## callees

- `0x180019c70`
- `0x180019d04`
- `0x18001a178`
- `0x18001a1e4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
        volatile signed __int32 *a1,
        int a2)
{
  bool v4; // di
  volatile signed __int32 *v5; // rcx
  signed __int32 v6; // edx
  __int64 result; // rax
  signed __int32 v8; // edx
  signed __int32 v9; // [rsp+38h] [rbp+10h] BYREF

  v4 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  if ( _InterlockedIncrement(a1 + 63) == 1 )
    v4 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  v5 = a1 + 2;
  if ( a2 >= 0 )
  {
    result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(v5);
    if ( !(_BYTE)result )
      result = (unsigned int)_InterlockedCompareExchange(a1 + 16, v8, 2);
  }
  else
  {
    v6 = *((_DWORD *)a1 + 16);
    v9 = -2;
    result = (unsigned int)_InterlockedCompareExchange(&v9, v6, -2);
    if ( v9 != 2 )
      result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
                 v5,
                 (unsigned int)a2);
  }
  if ( v4 )
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete((__int64)a1);
  return result;
}

```

## disassembly

```asm
0x18001a1e4  mov     [rsp+arg_0], rbx
0x18001a1e9  push    rdi
0x18001a1ea  sub     rsp, 20h
0x18001a1ee  mov     rbx, rcx
0x18001a1f1  mov     r8d, edx
0x18001a1f4  or      ecx, 0FFFFFFFFh
0x18001a1f7  mov     eax, ecx
0x18001a1f9  lock xadd [rbx+104h], eax
0x18001a201  add     eax, ecx
0x18001a203  lea     edx, [rcx+2]
0x18001a206  mov     eax, edx
0x18001a208  setz    dil
0x18001a20c  lock xadd [rbx+0FCh], eax
0x18001a214  add     eax, edx
0x18001a216  cmp     eax, edx
0x18001a218  jnz     short loc_18001A22A
0x18001a21a  mov     eax, ecx
0x18001a21c  lock xadd [rbx+104h], eax
0x18001a224  add     eax, ecx
0x18001a226  setz    dil
0x18001a22a  lea     rcx, [rbx+8]
0x18001a22e  test    r8d, r8d
0x18001a231  jns     short loc_18001A259
0x18001a233  mov     edx, [rcx+38h]
0x18001a236  mov     [rsp+28h+arg_8], 0FFFFFFFEh
0x18001a23e  mov     eax, [rsp+28h+arg_8]
0x18001a242  lock cmpxchg [rsp+28h+arg_8], edx
0x18001a248  cmp     [rsp+28h+arg_8], 2
0x18001a24d  jz      short loc_18001A26C
0x18001a24f  mov     edx, r8d
0x18001a252  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001a257  jmp     short loc_18001A26C
0x18001a259  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18001a25e  test    al, al
0x18001a260  jnz     short loc_18001A26C
0x18001a262  mov     eax, 2
0x18001a267  lock cmpxchg [rbx+40h], edx
0x18001a26c  test    dil, dil
0x18001a26f  jz      short loc_18001A279
0x18001a271  mov     rcx, rbx
0x18001a274  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18001a279  mov     rbx, [rsp+28h+arg_0]
0x18001a27e  add     rsp, 20h
0x18001a282  pop     rdi
0x18001a283  retn
```
