# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180009eb0`
- end: `0x180009f03`
- name: `?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009bc0`
- `0x180009eb0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  __int64 v2; // rcx
  signed __int32 v4[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( *(int *)(a1 + 160) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 160), 0xFFFFFFFF) == 1 )
  {
    _InterlockedOr(v4, 0);
    v2 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 144) = 0;
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1);
}

```

## disassembly

```asm
0x180009eb0  push    rbx
0x180009eb2  sub     rsp, 20h
0x180009eb6  xor     edx, edx
0x180009eb8  mov     rbx, rcx
0x180009ebb  cmp     [rcx+0A0h], edx
0x180009ec1  jle     short loc_180009EF6
0x180009ec3  or      eax, 0FFFFFFFFh
0x180009ec6  lock xadd [rcx+0A0h], eax
0x180009ece  cmp     eax, 1
0x180009ed1  jnz     short loc_180009EF6
0x180009ed3  lock or [rsp+28h+var_28], edx
0x180009ed7  mov     rcx, [rcx+90h]
0x180009ede  mov     [rbx+90h], rdx
0x180009ee5  test    rcx, rcx
0x180009ee8  jz      short loc_180009EF6
0x180009eea  mov     rax, [rcx]
0x180009eed  mov     rax, [rax+10h]
0x180009ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef6  mov     rcx, rbx
0x180009ef9  add     rsp, 20h
0x180009efd  pop     rbx
0x180009efe  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
