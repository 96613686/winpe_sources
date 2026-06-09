# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetWeakReference(IWeakReference * *)

- ea: `0x18000bf50`
- end: `0x18000c047`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001984`
- `0x1800090d8`
- `0x18000bf50`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetWeakReference(
        __int64 a1,
        struct IUnknown *a2)
{
  signed __int64 v2; // rdi
  __int64 v5; // r8
  signed __int32 v6; // eax
  __int64 WeakReference; // rax
  __int64 v8; // rdx
  unsigned __int64 v10; // r8
  bool i; // zf
  signed __int64 v12; // rax
  signed __int64 v13; // rdi
  signed __int32 v14; // eax

  v2 = *(_QWORD *)(a1 + 56);
  a2->lpVtbl = 0;
  if ( v2 >= 0 )
  {
    WeakReference = (__int64)Microsoft::WRL::Details::CreateWeakReference((Microsoft::WRL::Details *)(a1 - 168), a2);
    v8 = WeakReference;
    if ( !WeakReference )
      return 2147942414LL;
    *(_DWORD *)(WeakReference + 16) = v2;
    v10 = (WeakReference >> 1) | 0x8000000000000000uLL;
    v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), v10, v2);
    for ( i = v2 == v12; ; i = v12 == v13 )
    {
      v13 = v12;
      if ( i )
        break;
      if ( v12 < 0 )
      {
        *(_QWORD *)v8 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
        *(_DWORD *)(v8 + 16) = -1073741823;
        *(_DWORD *)(v8 + 12) = -1073741823;
        operator delete((void *)v8);
        v8 = 2 * v13;
        do
          v14 = *(_DWORD *)(2 * v13 + 0xC);
        while ( v14 != 0x7FFFFFFF
             && v14 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 12), v14 + 1, v14) );
        break;
      }
      *(_DWORD *)(v8 + 16) = v12;
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), v10, v12);
    }
    a2->lpVtbl = (struct IUnknownVtbl *)v8;
  }
  else
  {
    v5 = 2 * v2;
    do
      v6 = *(_DWORD *)(2 * v2 + 0xC);
    while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 12), v6 + 1, v6) );
    a2->lpVtbl = (struct IUnknownVtbl *)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000bf50  mov     [rsp+arg_10], rbx
0x18000bf55  mov     [rsp+arg_18], rsi
0x18000bf5a  push    rdi
0x18000bf5b  sub     rsp, 20h
0x18000bf5f  mov     rdi, [rcx+38h]
0x18000bf63  mov     rbx, rdx
0x18000bf66  mov     qword ptr [rdx], 0
0x18000bf6d  mov     rsi, rcx
0x18000bf70  test    rdi, rdi
0x18000bf73  jns     short loc_18000BF9D
0x18000bf75  lea     r8, [rdi+rdi]
0x18000bf79  mov     r9d, 7FFFFFFFh
0x18000bf7f  jmp     short loc_18000BF8C
0x18000bf81  lea     ecx, [rax+1]
0x18000bf84  lock cmpxchg [r8+0Ch], ecx
0x18000bf8a  jz      short loc_18000BF95
0x18000bf8c  mov     eax, [r8+0Ch]
0x18000bf90  cmp     eax, r9d
0x18000bf93  jnz     short loc_18000BF81
0x18000bf95  mov     [rdx], r8
0x18000bf98  jmp     loc_18000C035
0x18000bf9d  add     rcx, 0FFFFFFFFFFFFFF58h; this
0x18000bfa4  call    ?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z; Microsoft::WRL::Details::CreateWeakReference(IUnknown *)
0x18000bfa9  mov     rdx, rax
0x18000bfac  test    rax, rax
0x18000bfaf  jnz     short loc_18000BFB8
0x18000bfb1  mov     eax, 8007000Eh
0x18000bfb6  jmp     short loc_18000C037
0x18000bfb8  mov     rax, 8000000000000000h
0x18000bfc2  mov     [rdx+10h], edi
0x18000bfc5  mov     r8, rdx
0x18000bfc8  sar     r8, 1
0x18000bfcb  or      r8, rax
0x18000bfce  mov     rax, rdi
0x18000bfd1  lock cmpxchg [rsi+38h], r8
0x18000bfd7  jmp     short loc_18000BFF0
0x18000bfd9  test    rdi, rdi
0x18000bfdc  js      short loc_18000BFF7
0x18000bfde  mov     rcx, rdi
0x18000bfe1  mov     [rdx+10h], edi
0x18000bfe4  mov     rax, rdi
0x18000bfe7  lock cmpxchg [rsi+38h], r8
0x18000bfed  cmp     rax, rcx
0x18000bff0  mov     rdi, rax
0x18000bff3  jnz     short loc_18000BFD9
0x18000bff5  jmp     short loc_18000C032
0x18000bff7  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000bffe  mov     rcx, rdx; Block
0x18000c001  mov     [rdx], rax
0x18000c004  mov     eax, 0C0000001h
0x18000c009  mov     [rdx+10h], eax
0x18000c00c  mov     [rdx+0Ch], eax
0x18000c00f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c014  lea     rdx, [rdi+rdi]
0x18000c018  mov     r9d, 7FFFFFFFh
0x18000c01e  jmp     short loc_18000C02A
0x18000c020  lea     ecx, [rax+1]
0x18000c023  lock cmpxchg [rdx+0Ch], ecx
0x18000c028  jz      short loc_18000C032
0x18000c02a  mov     eax, [rdx+0Ch]
0x18000c02d  cmp     eax, r9d
0x18000c030  jnz     short loc_18000C020
0x18000c032  mov     [rbx], rdx
0x18000c035  xor     eax, eax
0x18000c037  mov     rbx, [rsp+28h+arg_10]
0x18000c03c  mov     rsi, [rsp+28h+arg_18]
0x18000c041  add     rsp, 20h
0x18000c045  pop     rdi
0x18000c046  retn
```
