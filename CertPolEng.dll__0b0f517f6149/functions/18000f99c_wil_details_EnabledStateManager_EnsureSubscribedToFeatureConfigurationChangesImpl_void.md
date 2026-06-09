# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000f99c`
- end: `0x18000fa53`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `183`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f974`

## callees

- `0x18000f99c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f9bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f9bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa49`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rsi
  unsigned int Ptr_high; // edi
  void (__fastcall *v6)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v3 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return Ptr_high;
  }
  v3->Ptr = 0;
  v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
    || (v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
  {
    v6(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
  }
  if ( !v3->Ptr )
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
0x18000f99c  mov     [rsp+arg_0], rbx
0x18000f9a1  mov     [rsp+arg_8], rsi
0x18000f9a6  push    rdi
0x18000f9a7  sub     rsp, 20h
0x18000f9ab  mov     rdi, rcx
0x18000f9ae  mov     eax, [rcx]
0x18000f9b0  test    eax, eax
0x18000f9b2  jz      short loc_18000FA26
0x18000f9b4  lea     rbx, [rcx+8]
0x18000f9b8  mov     rcx, rbx; SRWLock
0x18000f9bb  call    cs:__imp_AcquireSRWLockExclusive
0x18000f9c1  lea     rsi, [rdi+60h]
0x18000f9c5  cmp     qword ptr [rsi], 0
0x18000f9c9  jz      short loc_18000F9E1
0x18000f9cb  mov     edi, [rdi+1Ch]
0x18000f9ce  nop
0x18000f9cf  test    rbx, rbx
0x18000f9d2  jz      short loc_18000F9DD
0x18000f9d4  mov     rcx, rbx; SRWLock
0x18000f9d7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f9dd  mov     eax, edi
0x18000f9df  jmp     short loc_18000FA28
0x18000f9e1  mov     qword ptr [rsi], 0
0x18000f9e8  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000f9ef  test    rax, rax
0x18000f9f2  jnz     short loc_18000FA00
0x18000f9f4  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000f9fb  test    rax, rax
0x18000f9fe  jz      short loc_18000FA12
0x18000fa00  mov     r8, rdi
0x18000fa03  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000fa0a  mov     rcx, rsi
0x18000fa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa12  cmp     qword ptr [rsi], 0
0x18000fa16  jnz     short loc_18000FA38
0x18000fa18  test    rbx, rbx
0x18000fa1b  jz      short loc_18000FA26
0x18000fa1d  mov     rcx, rbx; SRWLock
0x18000fa20  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa26  xor     eax, eax
0x18000fa28  mov     rbx, [rsp+28h+arg_0]
0x18000fa2d  mov     rsi, [rsp+28h+arg_8]
0x18000fa32  add     rsp, 20h
0x18000fa36  pop     rdi
0x18000fa37  retn
0x18000fa38  nop
0x18000fa39  mov     esi, 1
0x18000fa3e  mov     [rdi+1Ch], esi
0x18000fa41  test    rbx, rbx
0x18000fa44  jz      short loc_18000FA4F
0x18000fa46  mov     rcx, rbx; SRWLock
0x18000fa49  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa4f  mov     eax, esi
0x18000fa51  jmp     short loc_18000FA28
```
