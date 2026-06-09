# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180008da0`
- end: `0x180008e79`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `217`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007de0`
- `0x180007f50`
- `0x1800083a0`
- `0x180008d78`

## callees

- `0x180008da0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ddc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ddc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008dc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008dc3`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  unsigned int Ptr_high; // edi
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return Ptr_high;
  }
  v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
  this[12].Ptr = 0;
  if ( v5
    || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
  {
    v5(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
  }
  if ( !this[12].Ptr )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  HIDWORD(this[3].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 1;
}

```

## disassembly

```asm
0x180008da0  mov     [rsp+arg_0], rbx
0x180008da5  mov     [rsp+arg_8], rsi
0x180008daa  push    rdi
0x180008dab  sub     rsp, 20h
0x180008daf  mov     eax, [rcx]
0x180008db1  mov     rdi, rcx
0x180008db4  test    eax, eax
0x180008db6  jz      loc_180008E3C
0x180008dbc  lea     rbx, [rcx+8]
0x180008dc0  mov     rcx, rbx; SRWLock
0x180008dc3  call    cs:__imp_AcquireSRWLockExclusive
0x180008dc9  cmp     qword ptr [rdi+60h], 0
0x180008dce  jz      short loc_180008DF4
0x180008dd0  mov     edi, [rdi+1Ch]
0x180008dd3  nop
0x180008dd4  test    rbx, rbx
0x180008dd7  jz      short loc_180008DE2
0x180008dd9  mov     rcx, rbx; SRWLock
0x180008ddc  call    cs:__imp_ReleaseSRWLockExclusive
0x180008de2  mov     eax, edi
0x180008de4  mov     rbx, [rsp+28h+arg_0]
0x180008de9  mov     rsi, [rsp+28h+arg_8]
0x180008dee  add     rsp, 20h
0x180008df2  pop     rdi
0x180008df3  retn
0x180008df4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008dfb  mov     qword ptr [rdi+60h], 0
0x180008e03  test    rax, rax
0x180008e06  jnz     short loc_180008E14
0x180008e08  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180008e0f  test    rax, rax
0x180008e12  jz      short loc_180008E27
0x180008e14  mov     r8, rdi
0x180008e17  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180008e1e  lea     rcx, [rdi+60h]
0x180008e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e27  cmp     qword ptr [rdi+60h], 0
0x180008e2c  jnz     short loc_180008E4E
0x180008e2e  test    rbx, rbx
0x180008e31  jz      short loc_180008E3C
0x180008e33  mov     rcx, rbx; SRWLock
0x180008e36  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e3c  xor     eax, eax
0x180008e3e  mov     rbx, [rsp+28h+arg_0]
0x180008e43  mov     rsi, [rsp+28h+arg_8]
0x180008e48  add     rsp, 20h
0x180008e4c  pop     rdi
0x180008e4d  retn
0x180008e4e  nop
0x180008e4f  mov     dword ptr [rdi+1Ch], 1
0x180008e56  test    rbx, rbx
0x180008e59  jz      short loc_180008E64
0x180008e5b  mov     rcx, rbx; SRWLock
0x180008e5e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e64  mov     rbx, [rsp+28h+arg_0]
0x180008e69  mov     eax, 1
0x180008e6e  mov     rsi, [rsp+28h+arg_8]
0x180008e73  add     rsp, 20h
0x180008e77  pop     rdi
0x180008e78  retn
```
