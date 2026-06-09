# LockOrderManagerImp<WalletLockOrder>::GetCurrentThreadLockOrder(void)

- ea: `0x180018430`
- end: `0x180018495`
- name: `?GetCurrentThreadLockOrder@?$LockOrderManagerImp@W4WalletLockOrder@@@@UEAA?AW4WalletLockOrder@@XZ`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800172b0`
- `0x180018430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018482`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001844a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001844a`

## pseudocode

```c
__int64 __fastcall LockOrderManagerImp<enum WalletLockOrder>::GetCurrentThreadLockOrder(__int64 a1)
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
    v3 = *(_DWORD *)(*(_QWORD *)(v6 + 40) + 20LL);
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180018430  mov     [rsp+arg_10], rbx
0x180018435  push    rdi
0x180018436  sub     rsp, 20h
0x18001843a  lea     rdi, [rcx+30h]
0x18001843e  mov     rbx, rcx
0x180018441  mov     rcx, rdi; lpCriticalSection
0x180018444  call    cs:__imp_EnterCriticalSection
0x18001844a  call    cs:__imp_GetCurrentThreadId
0x180018450  add     rbx, 8
0x180018454  lea     r8, [rsp+28h+arg_0]
0x180018459  lea     rdx, [rsp+28h+arg_8]
0x18001845e  mov     [rsp+28h+arg_0], eax
0x180018462  mov     rcx, rbx
0x180018465  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x18001846a  mov     rax, [rsp+28h+arg_8]
0x18001846f  cmp     rax, rbx
0x180018472  jnz     short loc_180018478
0x180018474  xor     ebx, ebx
0x180018476  jmp     short loc_18001847F
0x180018478  mov     rdx, [rax+28h]
0x18001847c  mov     ebx, [rdx+14h]
0x18001847f  mov     rcx, rdi; lpCriticalSection
0x180018482  call    cs:__imp_LeaveCriticalSection
0x180018488  mov     eax, ebx
0x18001848a  mov     rbx, [rsp+28h+arg_10]
0x18001848f  add     rsp, 20h
0x180018493  pop     rdi
0x180018494  retn
```
