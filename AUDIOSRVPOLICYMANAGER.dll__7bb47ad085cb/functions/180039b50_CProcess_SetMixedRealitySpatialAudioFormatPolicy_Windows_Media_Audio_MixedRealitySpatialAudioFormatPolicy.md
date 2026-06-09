# CProcess::SetMixedRealitySpatialAudioFormatPolicy(Windows::Media::Audio::MixedRealitySpatialAudioFormatPolicy)

- ea: `0x180039b50`
- end: `0x180039c48`
- name: `?SetMixedRealitySpatialAudioFormatPolicy@CProcess@@UEAAXW4MixedRealitySpatialAudioFormatPolicy@Audio@Media@Windows@@@Z`
- size: `248`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18003753c`
- `0x180039500`
- `0x180039b50`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039b71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039b71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039bdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039bdf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180039bfe`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180039bfe`

## pseudocode

```c
void __fastcall CProcess::SetMixedRealitySpatialAudioFormatPolicy(__int64 a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 *v5; // rbx
  __int64 *v6; // rbp
  __int64 *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 712);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 712));
  if ( *(_DWORD *)(a1 + 752) != a2 )
  {
    *(_DWORD *)(a1 + 752) = a2;
    v5 = *(__int64 **)(a1 + 760);
    v6 = *(__int64 **)(a1 + 768);
    while ( v5 != v6 )
    {
      v11 = *v5;
      v12 = *(_DWORD *)(a1 + 160);
      v7 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_2b6e7f78b65f10010076d2e207bfb9e0_____lambda_2b6e7f78b65f10010076d2e207bfb9e0___(
                        &v13,
                        &v11);
      v8 = *v7;
      *v7 = 0;
      v9 = v13;
      if ( v13 )
      {
        v13 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v9);
      }
      CurrentThreadId = GetCurrentThreadId();
      SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v8, 0);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      ++v5;
    }
  }
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180039b50  mov     [rsp+arg_8], rbx
0x180039b55  mov     [rsp+arg_10], rbp
0x180039b5a  push    rsi
0x180039b5b  push    rdi
0x180039b5c  push    r14
0x180039b5e  sub     rsp, 40h
0x180039b62  mov     ebx, edx
0x180039b64  mov     rdi, rcx
0x180039b67  lea     rsi, [rcx+2C8h]
0x180039b6e  mov     rcx, rsi; lpCriticalSection
0x180039b71  call    cs:__imp_EnterCriticalSection
0x180039b77  cmp     [rdi+2F0h], ebx
0x180039b7d  jz      loc_180039C27
0x180039b83  mov     [rdi+2F0h], ebx
0x180039b89  mov     rbx, [rdi+2F8h]
0x180039b90  mov     rbp, [rdi+300h]
0x180039b97  jmp     loc_180039C1E
0x180039b9c  mov     rax, [rbx]
0x180039b9f  mov     [rsp+58h+var_28], rax
0x180039ba4  mov     eax, [rdi+0A0h]
0x180039baa  mov     [rsp+58h+var_20], eax
0x180039bae  lea     rdx, [rsp+58h+var_28]
0x180039bb3  lea     rcx, [rsp+58h+arg_0]
0x180039bb8  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_2b6e7f78b65f10010076d2e207bfb9e0_____lambda_2b6e7f78b65f10010076d2e207bfb9e0___
0x180039bbd  mov     r14, [rax]
0x180039bc0  mov     qword ptr [rax], 0
0x180039bc7  mov     rcx, [rsp+58h+arg_0]
0x180039bcc  test    rcx, rcx
0x180039bcf  jz      short loc_180039BDF
0x180039bd1  mov     [rsp+58h+arg_0], 0
0x180039bda  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180039bdf  call    cs:__imp_GetCurrentThreadId
0x180039be5  mov     [rsp+58h+var_30], 0
0x180039bee  mov     [rsp+58h+var_38], r14
0x180039bf3  xor     r9d, r9d
0x180039bf6  mov     r8d, eax
0x180039bf9  xor     edx, edx
0x180039bfb  lea     ecx, [rdx+3]
0x180039bfe  call    cs:__imp_SHTaskPoolQueueTask
0x180039c04  nop
0x180039c05  test    r14, r14
0x180039c08  jz      short loc_180039C1A
0x180039c0a  mov     rax, [r14]
0x180039c0d  mov     rcx, r14
0x180039c10  mov     rax, [rax+10h]
0x180039c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c19  nop
0x180039c1a  add     rbx, 8
0x180039c1e  cmp     rbx, rbp
0x180039c21  jnz     loc_180039B9C
0x180039c27  test    rsi, rsi
0x180039c2a  jz      short loc_180039C35
0x180039c2c  mov     rcx, rsi; lpCriticalSection
0x180039c2f  call    cs:__imp_LeaveCriticalSection
0x180039c35  mov     rbx, [rsp+58h+arg_8]
0x180039c3a  mov     rbp, [rsp+58h+arg_10]
0x180039c3f  add     rsp, 40h
0x180039c43  pop     r14
0x180039c45  pop     rdi
0x180039c46  pop     rsi
0x180039c47  retn
```
