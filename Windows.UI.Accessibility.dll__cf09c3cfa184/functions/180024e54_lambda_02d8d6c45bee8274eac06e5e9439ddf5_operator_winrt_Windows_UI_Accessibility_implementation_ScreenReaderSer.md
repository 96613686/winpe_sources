# _lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const__

- ea: `0x180024e54`
- end: `0x180024f48`
- name: `_lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const__`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025da0`

## callees

- `0x180003980`
- `0x18000cf94`
- `0x1800156d0`
- `0x180020410`
- `0x180024e54`
- `0x180025058`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024ec9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024ec9`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024ee8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024ee8`

## string_xrefs

- `0x180024f11`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\screenreaderservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const__(
        __int64 *a1,
        __int128 *a2)
{
  __int64 v3; // rcx
  __int64 *v4; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  int v7; // eax
  int v8; // edi
  __int64 result; // rax
  const char *v10; // r9
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF
  __int128 v13; // [rsp+40h] [rbp-28h]
  int v14; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a1;
  v12 = v3;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v13 = *a2;
  v14 = *((_DWORD *)a2 + 4);
  v4 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_60e424b1f6dcac8034823862126b4bca_____lambda_60e424b1f6dcac8034823862126b4bca___(
                    &v11,
                    &v12);
  v5 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  try
  {
    v8 = v7;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\screenreaderservice.cpp",
        (const char *)(unsigned int)v8,
        v5);
    result = lambda_a5002306207cfcb53d179eafdcf275e5_::__lambda_a5002306207cfcb53d179eafdcf275e5_(&v12);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x1A,
             (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\screenreaderservice.cpp",
             v10);
  }
  return result;
}

```

## disassembly

```asm
0x180024e54  mov     [rsp+arg_0], rbx
0x180024e59  push    rdi
0x180024e5a  sub     rsp, 60h
0x180024e5e  mov     rax, cs:__security_cookie
0x180024e65  xor     rax, rsp
0x180024e68  mov     [rsp+68h+var_10], rax
0x180024e6d  mov     rbx, rdx
0x180024e70  mov     rcx, [rcx]
0x180024e73  mov     [rsp+68h+var_30], rcx
0x180024e78  test    rcx, rcx
0x180024e7b  jz      short loc_180024E89
0x180024e7d  mov     rax, [rcx]
0x180024e80  mov     rax, [rax+8]
0x180024e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e89  movups  xmm0, xmmword ptr [rbx]
0x180024e8c  movups  [rsp+68h+var_28], xmm0
0x180024e91  mov     eax, [rbx+10h]
0x180024e94  mov     [rsp+68h+var_18], eax
0x180024e98  lea     rdx, [rsp+68h+var_30]
0x180024e9d  lea     rcx, [rsp+68h+var_38]
0x180024ea2  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_60e424b1f6dcac8034823862126b4bca_____lambda_60e424b1f6dcac8034823862126b4bca___
0x180024ea7  mov     rbx, [rax]
0x180024eaa  mov     qword ptr [rax], 0
0x180024eb1  mov     rcx, [rsp+68h+var_38]
0x180024eb6  test    rcx, rcx
0x180024eb9  jz      short loc_180024EC9
0x180024ebb  mov     [rsp+68h+var_38], 0
0x180024ec4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180024ec9  call    cs:__imp_GetCurrentThreadId
0x180024ecf  mov     [rsp+68h+var_40], 0
0x180024ed8  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180024edd  xor     r9d, r9d
0x180024ee0  mov     r8d, eax
0x180024ee3  xor     edx, edx
0x180024ee5  lea     ecx, [rdx+3]
0x180024ee8  call    cs:__imp_SHTaskPoolQueueTask
0x180024eee  mov     edi, eax
0x180024ef0  test    rbx, rbx
0x180024ef3  jz      short loc_180024F05
0x180024ef5  mov     rdx, [rbx]
0x180024ef8  mov     rcx, rbx
0x180024efb  mov     rax, [rdx+10h]
0x180024eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f04  nop
0x180024f05  mov     rcx, [rsp+68h]; this
0x180024f0a  test    edi, edi
0x180024f0c  jns     short loc_180024F23
0x180024f0e  mov     r9d, edi; char *
0x180024f11  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\accessibletech\\ex"...
0x180024f18  mov     edx, 18h; void *
0x180024f1d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024f23  lea     rcx, [rsp+68h+var_30]
0x180024f28  call    _lambda_a5002306207cfcb53d179eafdcf275e5_____lambda_a5002306207cfcb53d179eafdcf275e5_
0x180024f2d  nop
0x180024f2e  jmp     short $+2
0x180024f30  mov     rcx, [rsp+68h+var_10]
0x180024f35  xor     rcx, rsp; StackCookie
0x180024f38  call    __security_check_cookie
0x180024f3d  mov     rbx, [rsp+68h+arg_0]
0x180024f42  add     rsp, 60h
0x180024f46  pop     rdi
0x180024f47  retn
```
