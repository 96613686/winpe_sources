# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::AddRef(void)

- ea: `0x1800166b0`
- end: `0x1800166f7`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016700`
- `0x180016710`
- `0x180016730`
- `0x180016750`
- `0x180016770`
- `0x180016790`
- `0x1800167b0`

## callees

- `0x180010bec`
- `0x1800166b0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::AddRef(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  signed __int64 v3; // rtt

  v2 = *(_QWORD *)(a1 + 224);
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
    {
      LODWORD(a2) = 0x7FFFFFFF;
      return (unsigned int)a2;
    }
    a2 = (volatile int *)(v2 + 1);
    v3 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v2 + 1, v2);
    if ( v3 == v2 )
      return (unsigned int)a2;
  }
  LODWORD(a2) = Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x1800166b0  sub     rsp, 28h
0x1800166b4  mov     rax, [rcx+0E0h]
0x1800166bb  mov     r8d, 7FFFFFFFh
0x1800166c1  test    rax, rax
0x1800166c4  js      short loc_1800166E1
0x1800166c6  cmp     eax, r8d
0x1800166c9  jz      short loc_1800166DC
0x1800166cb  lea     rdx, [rax+1]
0x1800166cf  lock cmpxchg [rcx+0E0h], rdx
0x1800166d8  jnz     short loc_1800166C1
0x1800166da  jmp     short loc_1800166F0
0x1800166dc  mov     edx, r8d; volatile int *
0x1800166df  jmp     short loc_1800166F0
0x1800166e1  lea     rcx, ds:10h[rax*2]; this
0x1800166e9  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800166ee  mov     edx, eax
0x1800166f0  mov     eax, edx
0x1800166f2  add     rsp, 28h
0x1800166f6  retn
```
