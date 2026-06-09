# Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)

- ea: `0x18000bb20`
- end: `0x18000bb92`
- name: `?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z`
- size: `114`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bcd0`
- `0x18000bdc0`
- `0x18000beb0`
- `0x18000c580`
- `0x18000c710`
- `0x18000cbd0`
- `0x18000cd60`

## callees

- `0x180003a38`
- `0x180006c38`
- `0x18000bb20`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000bb5b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000bb5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000bb67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000bb67`

## pseudocode

```c
_BYTE *__fastcall Kerb3961::CipherPolicyImpl::EnsureInitialization(__int64 a1, _BYTE *a2, __int64 a3)
{
  const unsigned __int16 *v5; // rdx
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = a3;
  if ( !*(_DWORD *)(a1 + 8) )
  {
    wil::push_lock::acquire_exclusive(a1 + 16, &v7);
    if ( !*(_DWORD *)(a1 + 8) )
      Kerb3961::ConsistencyFail((Kerb3961 *)L"Kernel cannot use last-resort initialization", v5);
    if ( v7 )
    {
      ExReleasePushLockExclusiveEx(v7, 0);
      KeLeaveCriticalRegion();
    }
  }
  *a2 = 0;
  return a2;
}

```

## disassembly

```asm
0x18000bb20  mov     [rsp+arg_0], rbx
0x18000bb25  mov     [rsp+arg_10], r8
0x18000bb2a  push    rdi
0x18000bb2b  sub     rsp, 20h
0x18000bb2f  cmp     dword ptr [rcx+8], 0
0x18000bb33  mov     rbx, rdx
0x18000bb36  mov     rdi, rcx
0x18000bb39  jnz     short loc_18000BB73
0x18000bb3b  add     rcx, 10h
0x18000bb3f  lea     rdx, [rsp+28h+arg_10]
0x18000bb44  call    ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18000bb49  cmp     dword ptr [rdi+8], 0
0x18000bb4d  jz      short loc_18000BB85
0x18000bb4f  mov     rcx, [rsp+28h+arg_10]
0x18000bb54  test    rcx, rcx
0x18000bb57  jz      short loc_18000BB73
0x18000bb59  xor     edx, edx
0x18000bb5b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18000bb62  nop     dword ptr [rax+rax+00h]
0x18000bb67  call    cs:__imp_KeLeaveCriticalRegion
0x18000bb6e  nop     dword ptr [rax+rax+00h]
0x18000bb73  mov     byte ptr [rbx], 0
0x18000bb76  mov     rax, rbx
0x18000bb79  mov     rbx, [rsp+28h+arg_0]
0x18000bb7e  add     rsp, 20h
0x18000bb82  pop     rdi
0x18000bb83  retn
0x18000bb85  lea     rcx, aKernelCannotUs; "Kernel cannot use last-resort initializ"...
0x18000bb8c  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
