# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18002f04c`
- end: `0x18002f149`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `253`
- prototype: `__int64 __fastcall(Windows::Internal::IAsyncFireCompletion *pFireCompletion)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e130`

## callees

- `0x18000648c`
- `0x18001c230`
- `0x18002d518`
- `0x18002df18`
- `0x18002e364`
- `0x18002e8a4`
- `0x18002f04c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0b2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002f0cd`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002f0cd`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        Windows::Internal::IAsyncFireCompletion *pFireCompletion)
{
  unsigned int v2; // ebp
  Microsoft::WRL::ComPtr<Windows::Internal::ComTaskPool::CTaskWrapper<<lambda_c2fd7731c5ae0d37e65ea73be67c0f1b> > > *v3; // rax
  Windows::Internal::ComTaskPool::CTaskWrapper<<lambda_c2fd7731c5ae0d37e65ea73be67c0f1b> > *ptr; // rsi
  Windows::Internal::ComTaskPool::CTaskWrapper<<lambda_c2fd7731c5ae0d37e65ea73be67c0f1b> > *v5; // rcx
  DWORD CurrentThreadId; // eax
  int v7; // edi
  bool v8; // di
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion> spFireCompletion; // [rsp+58h] [rbp+10h] BYREF
  Microsoft::WRL::ComPtr<Windows::Internal::ComTaskPool::CTaskWrapper<<lambda_c2fd7731c5ae0d37e65ea73be67c0f1b> > > result; // [rsp+60h] [rbp+18h] BYREF

  if ( Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  spFireCompletion.ptr_ = pFireCompletion;
  v2 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&spFireCompletion);
  spFireCompletion.ptr_ = pFireCompletion;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&spFireCompletion);
  v3 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
         &result,
         (Windows::Internal::ComTaskPoolHandler::_FireCompletion::__l5::<lambda_c2fd7731c5ae0d37e65ea73be67c0f1b> *)&spFireCompletion);
  ptr = v3->ptr_;
  v3->ptr_ = 0;
  v5 = result.ptr_;
  if ( result.ptr_ )
  {
    result.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, ptr, 0);
  if ( ptr )
    ptr->Release(ptr);
  v8 = v7 >= 0;
  if ( spFireCompletion.ptr_ )
    spFireCompletion.ptr_->Release(spFireCompletion.ptr_);
  if ( pFireCompletion )
    pFireCompletion->Release(pFireCompletion);
  if ( !v8 )
  {
LABEL_11:
    Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth();
    v2 = pFireCompletion->InvokeFireCompletion(pFireCompletion);
    Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth();
  }
  return v2;
}

```

## disassembly

```asm
0x18002f04c  mov     [rsp+arg_0], rbx
0x18002f051  push    rbp
0x18002f052  push    rsi
0x18002f053  push    rdi
0x18002f054  sub     rsp, 30h
0x18002f058  mov     rbx, pFireCompletion
0x18002f05b  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18002f060  cmp     eax, 4
0x18002f063  jle     loc_18002F11F
0x18002f069  lea     pFireCompletion, [rsp+48h+spFireCompletion]; this
0x18002f06e  mov     [rsp+48h+spFireCompletion.ptr_], rbx
0x18002f073  xor     ebp, ebp
0x18002f075  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef(void)
0x18002f07a  lea     pFireCompletion, [rsp+48h+spFireCompletion]; this
0x18002f07f  mov     [rsp+48h+spFireCompletion.ptr_], rbx
0x18002f084  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef(void)
0x18002f089  lea     rdx, [rsp+48h+spFireCompletion]; <args_0>
0x18002f08e  lea     pFireCompletion, [rsp+48h+result]; result
0x18002f093  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18002f098  mov     rsi, [rax]
0x18002f09b  mov     [rax], rbp
0x18002f09e  mov     pFireCompletion, [rsp+48h+result.ptr_]; this
0x18002f0a3  test    pFireCompletion, pFireCompletion
0x18002f0a6  jz      short loc_18002F0B2
0x18002f0a8  mov     [rsp+48h+result.ptr_], rbp
0x18002f0ad  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002f0b2  call    cs:__imp_GetCurrentThreadId
0x18002f0b8  xor     edx, edx
0x18002f0ba  mov     [rsp+48h+var_20], rbp
0x18002f0bf  xor     r9d, r9d
0x18002f0c2  mov     [rsp+48h+var_28], rsi
0x18002f0c7  mov     r8d, eax
0x18002f0ca  lea     ecx, [rdx+3]
0x18002f0cd  call    cs:__imp_SHTaskPoolQueueTask
0x18002f0d3  mov     edi, eax
0x18002f0d5  test    rsi, rsi
0x18002f0d8  jz      short loc_18002F0E9
0x18002f0da  mov     rdx, [rsi]
0x18002f0dd  mov     pFireCompletion, rsi
0x18002f0e0  mov     rax, [rdx+10h]
0x18002f0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0e9  mov     pFireCompletion, [rsp+48h+spFireCompletion.ptr_]
0x18002f0ee  shr     edi, 1Fh
0x18002f0f1  xor     dil, 1
0x18002f0f5  test    pFireCompletion, pFireCompletion
0x18002f0f8  jz      short loc_18002F106
0x18002f0fa  mov     rax, [pFireCompletion]
0x18002f0fd  mov     rax, [rax+10h]
0x18002f101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f106  test    rbx, rbx
0x18002f109  jz      short loc_18002F11A
0x18002f10b  mov     rax, [rbx]
0x18002f10e  mov     pFireCompletion, rbx
0x18002f111  mov     rax, [rax+10h]
0x18002f115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f11a  test    dil, dil
0x18002f11d  jnz     short loc_18002F13A
0x18002f11f  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18002f124  mov     rax, [rbx]
0x18002f127  mov     pFireCompletion, rbx
0x18002f12a  mov     rax, [rax+18h]
0x18002f12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f133  mov     ebp, eax
0x18002f135  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18002f13a  mov     rbx, [rsp+48h+arg_0]
0x18002f13f  mov     eax, ebp
0x18002f141  add     rsp, 30h
0x18002f145  pop     rdi
0x18002f146  pop     rsi
0x18002f147  pop     rbp
0x18002f148  retn
```
