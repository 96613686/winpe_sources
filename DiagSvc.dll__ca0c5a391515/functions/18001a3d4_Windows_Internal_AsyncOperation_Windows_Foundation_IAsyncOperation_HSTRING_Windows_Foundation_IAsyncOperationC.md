# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x18001a3d4`
- end: `0x18001a4eb`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800187f0`
- `0x180018840`
- `0x1800196e0`

## callees

- `0x18001a178`
- `0x18001a1e4`
- `0x18001a3d4`
- `0x180027010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  int v6; // eax
  int v7; // edx

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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
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
      v7 = *(_DWORD *)(a1 + 284);
    }
    else
    {
      v7 = v6;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      (volatile signed __int32 *)a1,
      v7);
  }
}

```

## disassembly

```asm
0x18001a3d4  mov     [rsp+arg_0], rbx
0x18001a3d9  mov     [rsp+arg_8], rbp
0x18001a3de  push    rdi
0x18001a3df  sub     rsp, 30h
0x18001a3e3  mov     rbx, rcx
0x18001a3e6  mov     edi, 1
0x18001a3eb  cmp     edx, 2
0x18001a3ee  jnz     loc_18001A47D
0x18001a3f4  mov     eax, edi
0x18001a3f6  lock xadd [rcx+0FCh], eax
0x18001a3fe  add     eax, edi
0x18001a400  cmp     eax, edi
0x18001a402  jnz     loc_18001A4DB
0x18001a408  lea     rbp, [rcx+120h]
0x18001a40f  mov     rcx, [rcx+108h]
0x18001a416  mov     r9, rbp
0x18001a419  mov     rax, [rcx]
0x18001a41c  mov     rax, [rax+8]
0x18001a420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a425  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x18001a42d  setz    cl
0x18001a430  mov     eax, edi
0x18001a432  lock xadd [rbx+100h], eax
0x18001a43a  add     eax, edi
0x18001a43c  cmp     eax, edi
0x18001a43e  jnz     short loc_18001A46F
0x18001a440  mov     rcx, [rbx+108h]
0x18001a447  mov     r9, rbp
0x18001a44a  mov     r8d, 800704C7h
0x18001a450  mov     edx, edi
0x18001a452  mov     rax, [rcx]
0x18001a455  mov     rax, [rax+8]
0x18001a459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a45e  or      eax, 0FFFFFFFFh
0x18001a461  lock xadd [rbx+104h], eax
0x18001a469  cmp     eax, edi
0x18001a46b  jnz     short loc_18001A4DB
0x18001a46d  jmp     short loc_18001A473
0x18001a46f  test    cl, cl
0x18001a471  jz      short loc_18001A4DB
0x18001a473  mov     rcx, rbx
0x18001a476  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18001a47b  jmp     short loc_18001A4DB
0x18001a47d  cmp     edx, edi
0x18001a47f  jnz     short loc_18001A4DB
0x18001a481  mov     eax, edi
0x18001a483  lock xadd [rcx+100h], eax
0x18001a48b  add     eax, edi
0x18001a48d  cmp     eax, edi
0x18001a48f  jnz     short loc_18001A4DB
0x18001a491  mov     rcx, [rcx+108h]
0x18001a498  lea     r9, [rbx+120h]
0x18001a49f  mov     edx, edi
0x18001a4a1  mov     rax, [rcx]
0x18001a4a4  mov     rax, [rax+8]
0x18001a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ad  test    eax, eax
0x18001a4af  js      short loc_18001A4D1
0x18001a4b1  cmp     byte ptr [rbx+129h], 0
0x18001a4b8  jz      short loc_18001A4D1
0x18001a4ba  or      eax, 0FFFFFFFFh
0x18001a4bd  lock xadd [rbx+118h], eax
0x18001a4c5  cmp     eax, edi
0x18001a4c7  jnz     short loc_18001A4DB
0x18001a4c9  mov     edx, [rbx+11Ch]
0x18001a4cf  jmp     short loc_18001A4D3
0x18001a4d1  mov     edx, eax
0x18001a4d3  mov     rcx, rbx
0x18001a4d6  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18001a4db  mov     rbx, [rsp+38h+arg_0]
0x18001a4e0  mov     rbp, [rsp+38h+arg_8]
0x18001a4e5  add     rsp, 30h
0x18001a4e9  pop     rdi
0x18001a4ea  retn
```
