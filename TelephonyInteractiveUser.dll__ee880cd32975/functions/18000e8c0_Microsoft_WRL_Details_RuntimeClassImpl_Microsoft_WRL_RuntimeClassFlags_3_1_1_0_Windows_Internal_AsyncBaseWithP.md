# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x18000e8c0`
- end: `0x18000e956`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `150`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e3b0`
- `0x18000e960`
- `0x18000e970`
- `0x18000e990`
- `0x18000e9b0`
- `0x18000e9d0`
- `0x18000e9f0`
- `0x18000ea10`

## callees

- `0x18000e8c0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v2; // rcx
  unsigned __int32 v3; // ebx
  bool v4; // zf
  signed __int64 v5; // rax
  signed __int32 v6; // r8d

  v2 = *((_QWORD *)a1 + 28);
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v3 = v2 - 1;
    v5 = _InterlockedCompareExchange64(a1 + 28, v2 - 1, v2);
    v4 = v2 == v5;
    v2 = v5;
    if ( v4 )
      goto LABEL_10;
  }
  do
    v6 = *(_DWORD *)(2 * v2 + 0x10);
  while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v2 + 16), v6 - 1, v6) );
  v3 = v6 - 1;
LABEL_10:
  if ( !v3 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 88))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e8c0  push    rbx
0x18000e8c2  sub     rsp, 20h
0x18000e8c6  mov     r9, rcx
0x18000e8c9  mov     r10d, 7FFFFFFFh
0x18000e8cf  mov     rcx, [rcx+0E0h]
0x18000e8d6  test    rcx, rcx
0x18000e8d9  js      short loc_18000E90D
0x18000e8db  cmp     ecx, r10d
0x18000e8de  jz      short loc_18000E8F7
0x18000e8e0  lea     rbx, [rcx-1]
0x18000e8e4  mov     rax, rcx
0x18000e8e7  lock cmpxchg [r9+0E0h], rbx
0x18000e8f0  mov     rcx, rax
0x18000e8f3  jnz     short loc_18000E8D6
0x18000e8f5  jmp     short loc_18000E91B
0x18000e8f7  mov     ebx, 7FFFFFFEh
0x18000e8fc  jmp     short loc_18000E94E
0x18000e8fe  lea     edx, [r8-1]
0x18000e902  mov     eax, r8d
0x18000e905  lock cmpxchg [rcx+rcx+10h], edx
0x18000e90b  jz      short loc_18000E917
0x18000e90d  mov     r8d, [rcx+rcx+10h]
0x18000e912  cmp     r8d, r10d
0x18000e915  jnz     short loc_18000E8FE
0x18000e917  lea     ebx, [r8-1]
0x18000e91b  test    ebx, ebx
0x18000e91d  jnz     short loc_18000E94E
0x18000e91f  test    r9, r9
0x18000e922  jz      short loc_18000E936
0x18000e924  mov     rax, [r9]
0x18000e927  lea     edx, [rbx+1]
0x18000e92a  mov     rcx, r9
0x18000e92d  mov     rax, [rax+58h]
0x18000e931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e936  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e93d  test    rcx, rcx
0x18000e940  jz      short loc_18000E94E
0x18000e942  mov     rdx, [rcx]
0x18000e945  mov     rax, [rdx+10h]
0x18000e949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94e  mov     eax, ebx
0x18000e950  add     rsp, 20h
0x18000e954  pop     rbx
0x18000e955  retn
```
