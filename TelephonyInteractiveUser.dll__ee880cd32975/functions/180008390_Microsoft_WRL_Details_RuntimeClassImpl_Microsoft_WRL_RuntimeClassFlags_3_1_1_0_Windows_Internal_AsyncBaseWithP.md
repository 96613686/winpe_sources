# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::AddRef(void)

- ea: `0x180008390`
- end: `0x1800083e6`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `86`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800083f0`
- `0x180008400`
- `0x180008420`
- `0x180008440`
- `0x180008460`
- `0x180008480`
- `0x1800084a0`

## callees

- `0x180008390`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  bool v5; // zf
  signed __int64 v6; // rax
  signed __int32 v7; // r9d

  v1 = *(_QWORD *)(a1 + 224);
  v3 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v3;
    v4 = v1 + 1;
    v6 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v1 + 1, v1);
    v5 = v1 == v6;
    v1 = v6;
    if ( v5 )
      return v4;
  }
  while ( 1 )
  {
    v7 = *(_DWORD *)(2 * v1 + 0x10);
    if ( v7 == 0x7FFFFFFF )
      break;
    if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v7 + 1, v7) )
      return (unsigned int)(v7 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x180008390  mov     rdx, [rcx+0E0h]
0x180008397  mov     r9, rcx
0x18000839a  mov     r8d, 7FFFFFFFh
0x1800083a0  test    rdx, rdx
0x1800083a3  js      short loc_1800083D0
0x1800083a5  cmp     edx, r8d
0x1800083a8  jz      short loc_1800083E0
0x1800083aa  lea     rcx, [rdx+1]
0x1800083ae  mov     rax, rdx
0x1800083b1  lock cmpxchg [r9+0E0h], rcx
0x1800083ba  mov     rdx, rax
0x1800083bd  jnz     short loc_1800083A0
0x1800083bf  jmp     short loc_1800083E3
0x1800083c1  lea     ecx, [r9+1]
0x1800083c5  mov     eax, r9d
0x1800083c8  lock cmpxchg [rdx+rdx+10h], ecx
0x1800083ce  jz      short loc_1800083DC
0x1800083d0  mov     r9d, [rdx+rdx+10h]
0x1800083d5  cmp     r9d, r8d
0x1800083d8  jnz     short loc_1800083C1
0x1800083da  jmp     short loc_1800083E0
0x1800083dc  lea     r8d, [r9+1]
0x1800083e0  mov     ecx, r8d
0x1800083e3  mov     eax, ecx
0x1800083e5  retn
```
