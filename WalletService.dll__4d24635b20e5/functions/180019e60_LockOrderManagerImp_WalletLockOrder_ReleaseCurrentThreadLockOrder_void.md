# LockOrderManagerImp<WalletLockOrder>::ReleaseCurrentThreadLockOrder(void)

- ea: `0x180019e60`
- end: `0x180019ef7`
- name: `?ReleaseCurrentThreadLockOrder@?$LockOrderManagerImp@W4WalletLockOrder@@@@UEAAXXZ`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002f70`
- `0x180016ff8`
- `0x1800172b0`
- `0x180019e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ef0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e80`

## pseudocode

```c
void __fastcall LockOrderManagerImp<enum WalletLockOrder>::ReleaseCurrentThreadLockOrder(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  __int64 v2; // rdi
  __int64 v3; // rbx
  _DWORD *v4; // rcx
  _QWORD *v5; // rdx
  __int64 v6; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  v2 = a1 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  CurrentThreadId = GetCurrentThreadId();
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
    v2,
    &v9,
    &CurrentThreadId);
  v3 = v9;
  if ( v9 != v2 )
  {
    v4 = *(_DWORD **)(v9 + 40);
    *(_DWORD *)(v9 + 56) = v4[4];
    v5 = (_QWORD *)*((_QWORD *)v4 + 1);
    v6 = *(_QWORD *)v4;
    *v5 = *(_QWORD *)v4;
    *(_QWORD *)(v6 + 8) = v5;
    operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
    if ( (*(_QWORD *)(v3 + 48))-- == 1 )
      utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::_EraseImpl<unsigned long>(
        v2,
        (__int64)&CurrentThreadId);
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180019e60  mov     [rsp+arg_10], rbx
0x180019e65  mov     [rsp+arg_18], rsi
0x180019e6a  push    rdi
0x180019e6b  sub     rsp, 20h
0x180019e6f  lea     rsi, [rcx+30h]
0x180019e73  lea     rdi, [rcx+8]
0x180019e77  mov     rcx, rsi; lpCriticalSection
0x180019e7a  call    cs:__imp_EnterCriticalSection
0x180019e80  call    cs:__imp_GetCurrentThreadId
0x180019e86  lea     r8, [rsp+28h+arg_0]
0x180019e8b  mov     rcx, rdi
0x180019e8e  lea     rdx, [rsp+28h+arg_8]
0x180019e93  mov     [rsp+28h+arg_0], eax
0x180019e97  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180019e9c  mov     rbx, [rsp+28h+arg_8]
0x180019ea1  cmp     rbx, rdi
0x180019ea4  jz      short loc_180019EDE
0x180019ea6  mov     rcx, [rbx+28h]; void *
0x180019eaa  mov     eax, [rcx+10h]
0x180019ead  mov     [rbx+38h], eax
0x180019eb0  mov     rdx, [rcx+8]
0x180019eb4  mov     rax, [rcx]
0x180019eb7  mov     [rdx], rax
0x180019eba  mov     [rax+8], rdx
0x180019ebe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019ec5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019eca  sub     qword ptr [rbx+30h], 1
0x180019ecf  jnz     short loc_180019EDE
0x180019ed1  lea     rdx, [rsp+28h+arg_0]
0x180019ed6  mov     rcx, rdi
0x180019ed9  call    ??$_EraseImpl@K@?$_HashTable@KU?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@2@$0A@@utl@@AEAA_KAEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>>,0>::_EraseImpl<ulong>(ulong const &)
0x180019ede  mov     rcx, rsi
0x180019ee1  mov     rbx, [rsp+28h+arg_10]
0x180019ee6  mov     rsi, [rsp+28h+arg_18]
0x180019eeb  add     rsp, 20h
0x180019eef  pop     rdi
0x180019ef0  jmp     cs:__imp_LeaveCriticalSection
```
