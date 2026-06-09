# LockOrderManagerImp<WalletLockOrder>::GetHighestLockOrder(void)

- ea: `0x180018520`
- end: `0x180018581`
- name: `?GetHighestLockOrder@?$LockOrderManagerImp@W4WalletLockOrder@@@@UEAA?AW4WalletLockOrder@@XZ`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800172b0`
- `0x180018520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001856e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001856e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001853a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001853a`

## pseudocode

```c
__int64 __fastcall LockOrderManagerImp<enum WalletLockOrder>::GetHighestLockOrder(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rbx
  unsigned int v3; // ebx
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  v2 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 += 8;
  CurrentThreadId = GetCurrentThreadId();
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
    v2,
    &v6,
    &CurrentThreadId);
  if ( v6 == v2 )
    v3 = 0;
  else
    v3 = *(_DWORD *)(v6 + 56);
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180018520  mov     [rsp+arg_10], rbx
0x180018525  push    rdi
0x180018526  sub     rsp, 20h
0x18001852a  lea     rdi, [rcx+30h]
0x18001852e  mov     rbx, rcx
0x180018531  mov     rcx, rdi; lpCriticalSection
0x180018534  call    cs:__imp_EnterCriticalSection
0x18001853a  call    cs:__imp_GetCurrentThreadId
0x180018540  add     rbx, 8
0x180018544  lea     r8, [rsp+28h+arg_0]
0x180018549  lea     rdx, [rsp+28h+arg_8]
0x18001854e  mov     [rsp+28h+arg_0], eax
0x180018552  mov     rcx, rbx
0x180018555  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x18001855a  mov     rax, [rsp+28h+arg_8]
0x18001855f  cmp     rax, rbx
0x180018562  jnz     short loc_180018568
0x180018564  xor     ebx, ebx
0x180018566  jmp     short loc_18001856B
0x180018568  mov     ebx, [rax+38h]
0x18001856b  mov     rcx, rdi; lpCriticalSection
0x18001856e  call    cs:__imp_LeaveCriticalSection
0x180018574  mov     eax, ebx
0x180018576  mov     rbx, [rsp+28h+arg_10]
0x18001857b  add     rsp, 20h
0x18001857f  pop     rdi
0x180018580  retn
```
