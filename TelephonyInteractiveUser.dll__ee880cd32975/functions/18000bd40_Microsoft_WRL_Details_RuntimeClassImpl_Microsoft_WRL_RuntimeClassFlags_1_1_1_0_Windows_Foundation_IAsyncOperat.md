# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetWeakReference

- ea: `0x18000bd40`
- end: `0x18000be40`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetWeakReference`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001984`
- `0x1800090d8`
- `0x18000bd40`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::GetWeakReference(
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

  v2 = *(_QWORD *)(a1 + 160);
  a2->lpVtbl = 0;
  if ( v2 >= 0 )
  {
    WeakReference = (__int64)Microsoft::WRL::Details::CreateWeakReference((Microsoft::WRL::Details *)(a1 - 8), a2);
    v8 = WeakReference;
    if ( !WeakReference )
      return 2147942414LL;
    *(_DWORD *)(WeakReference + 16) = v2;
    v10 = (WeakReference >> 1) | 0x8000000000000000uLL;
    v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 160), v10, v2);
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
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 160), v10, v12);
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
0x18000bd40  mov     [rsp+arg_10], rbx
0x18000bd45  mov     [rsp+arg_18], rsi
0x18000bd4a  push    rdi
0x18000bd4b  sub     rsp, 20h
0x18000bd4f  mov     rdi, [rcx+0A0h]
0x18000bd56  mov     rbx, rdx
0x18000bd59  mov     qword ptr [rdx], 0
0x18000bd60  mov     rsi, rcx
0x18000bd63  test    rdi, rdi
0x18000bd66  jns     short loc_18000BD90
0x18000bd68  lea     r8, [rdi+rdi]
0x18000bd6c  mov     r9d, 7FFFFFFFh
0x18000bd72  jmp     short loc_18000BD7F
0x18000bd74  lea     ecx, [rax+1]
0x18000bd77  lock cmpxchg [r8+0Ch], ecx
0x18000bd7d  jz      short loc_18000BD88
0x18000bd7f  mov     eax, [r8+0Ch]
0x18000bd83  cmp     eax, r9d
0x18000bd86  jnz     short loc_18000BD74
0x18000bd88  mov     [rdx], r8
0x18000bd8b  jmp     loc_18000BE2E
0x18000bd90  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18000bd94  call    ?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z; Microsoft::WRL::Details::CreateWeakReference(IUnknown *)
0x18000bd99  mov     rdx, rax
0x18000bd9c  test    rax, rax
0x18000bd9f  jnz     short loc_18000BDAB
0x18000bda1  mov     eax, 8007000Eh
0x18000bda6  jmp     loc_18000BE30
0x18000bdab  mov     rax, 8000000000000000h
0x18000bdb5  mov     [rdx+10h], edi
0x18000bdb8  mov     r8, rdx
0x18000bdbb  sar     r8, 1
0x18000bdbe  or      r8, rax
0x18000bdc1  mov     rax, rdi
0x18000bdc4  lock cmpxchg [rsi+0A0h], r8
0x18000bdcd  jmp     short loc_18000BDE9
0x18000bdcf  test    rdi, rdi
0x18000bdd2  js      short loc_18000BDF0
0x18000bdd4  mov     rcx, rdi
0x18000bdd7  mov     [rdx+10h], edi
0x18000bdda  mov     rax, rdi
0x18000bddd  lock cmpxchg [rsi+0A0h], r8
0x18000bde6  cmp     rax, rcx
0x18000bde9  mov     rdi, rax
0x18000bdec  jnz     short loc_18000BDCF
0x18000bdee  jmp     short loc_18000BE2B
0x18000bdf0  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000bdf7  mov     rcx, rdx; Block
0x18000bdfa  mov     [rdx], rax
0x18000bdfd  mov     eax, 0C0000001h
0x18000be02  mov     [rdx+10h], eax
0x18000be05  mov     [rdx+0Ch], eax
0x18000be08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be0d  lea     rdx, [rdi+rdi]
0x18000be11  mov     r9d, 7FFFFFFFh
0x18000be17  jmp     short loc_18000BE23
0x18000be19  lea     ecx, [rax+1]
0x18000be1c  lock cmpxchg [rdx+0Ch], ecx
0x18000be21  jz      short loc_18000BE2B
0x18000be23  mov     eax, [rdx+0Ch]
0x18000be26  cmp     eax, r9d
0x18000be29  jnz     short loc_18000BE19
0x18000be2b  mov     [rbx], rdx
0x18000be2e  xor     eax, eax
0x18000be30  mov     rbx, [rsp+28h+arg_10]
0x18000be35  mov     rsi, [rsp+28h+arg_18]
0x18000be3a  add     rsp, 20h
0x18000be3e  pop     rdi
0x18000be3f  retn
```
