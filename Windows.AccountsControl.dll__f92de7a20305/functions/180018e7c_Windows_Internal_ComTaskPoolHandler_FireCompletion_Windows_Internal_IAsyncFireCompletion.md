# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180018e7c`
- end: `0x180018f88`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f1c0`

## callees

- `0x1800092ac`
- `0x18000e910`
- `0x18000fc00`
- `0x180011e84`
- `0x180011f64`
- `0x180015850`
- `0x180018e7c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018eea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018eea`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180018f09`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180018f09`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // edi
  bool v7; // di
  struct Windows::Internal::IAsyncFireCompletion *v9; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  struct Windows::Internal::IAsyncFireCompletion *v11; // [rsp+78h] [rbp+20h] BYREF

  if ( (int)Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  v2 = 0;
  v11 = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v11);
  v9 = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v9);
  v3 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v10,
                    &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v7 = v6 >= 0;
  if ( v9 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v7 )
  {
LABEL_11:
    Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth();
    v2 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth();
  }
  return v2;
}

```

## disassembly

```asm
0x180018e7c  mov     [rsp+arg_0], rbx
0x180018e81  push    rbp
0x180018e82  push    rsi
0x180018e83  push    rdi
0x180018e84  sub     rsp, 40h
0x180018e88  mov     rbx, rcx
0x180018e8b  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x180018e90  cmp     eax, 4
0x180018e93  jle     loc_180018F5E
0x180018e99  xor     ebp, ebp
0x180018e9b  mov     [rsp+58h+arg_18], rbx
0x180018ea0  lea     rcx, [rsp+58h+arg_18]
0x180018ea5  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180018eaa  nop
0x180018eab  mov     [rsp+58h+arg_8], rbx
0x180018eb0  lea     rcx, [rsp+58h+arg_8]
0x180018eb5  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180018eba  nop
0x180018ebb  lea     rdx, [rsp+58h+arg_8]
0x180018ec0  lea     rcx, [rsp+58h+arg_10]
0x180018ec5  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x180018eca  mov     rsi, [rax]
0x180018ecd  mov     [rsp+58h+var_28], rsi
0x180018ed2  mov     [rax], rbp
0x180018ed5  mov     rcx, [rsp+58h+arg_10]
0x180018eda  test    rcx, rcx
0x180018edd  jz      short loc_180018EEA
0x180018edf  mov     [rsp+58h+arg_10], rbp
0x180018ee4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release(void)
0x180018ee9  nop
0x180018eea  call    cs:__imp_GetCurrentThreadId
0x180018ef0  mov     [rsp+58h+var_30], 0
0x180018ef9  mov     [rsp+58h+var_38], rsi
0x180018efe  xor     r9d, r9d
0x180018f01  mov     r8d, eax
0x180018f04  xor     edx, edx
0x180018f06  lea     ecx, [rdx+3]
0x180018f09  call    cs:__imp_SHTaskPoolQueueTask
0x180018f0f  mov     edi, eax
0x180018f11  test    rsi, rsi
0x180018f14  jz      short loc_180018F26
0x180018f16  mov     rdx, [rsi]
0x180018f19  mov     rcx, rsi
0x180018f1c  mov     rax, [rdx+10h]
0x180018f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f25  nop
0x180018f26  shr     edi, 1Fh
0x180018f29  xor     dil, 1
0x180018f2d  mov     rcx, [rsp+58h+arg_8]
0x180018f32  test    rcx, rcx
0x180018f35  jz      short loc_180018F44
0x180018f37  mov     rax, [rcx]
0x180018f3a  mov     rax, [rax+10h]
0x180018f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f43  nop
0x180018f44  test    rbx, rbx
0x180018f47  jz      short loc_180018F59
0x180018f49  mov     rax, [rbx]
0x180018f4c  mov     rcx, rbx
0x180018f4f  mov     rax, [rax+10h]
0x180018f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f58  nop
0x180018f59  test    dil, dil
0x180018f5c  jnz     short loc_180018F79
0x180018f5e  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x180018f63  mov     rax, [rbx]
0x180018f66  mov     rcx, rbx
0x180018f69  mov     rax, [rax+18h]
0x180018f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f72  mov     ebp, eax
0x180018f74  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x180018f79  mov     eax, ebp
0x180018f7b  mov     rbx, [rsp+58h+arg_0]
0x180018f80  add     rsp, 40h
0x180018f84  pop     rdi
0x180018f85  pop     rsi
0x180018f86  pop     rbp
0x180018f87  retn
```
