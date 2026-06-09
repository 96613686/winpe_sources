# LockOrderManagerImp<WalletLockOrder>::HasLock(WalletLockOrder)

- ea: `0x180018a60`
- end: `0x180018af2`
- name: `?HasLock@?$LockOrderManagerImp@W4WalletLockOrder@@@@UEAAHW4WalletLockOrder@@@Z`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800172b0`
- `0x180018a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018aae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018aae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ada`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a81`

## pseudocode

```c
__int64 __fastcall LockOrderManagerImp<enum WalletLockOrder>::HasLock(__int64 a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdi
  __int64 *i; // rax
  unsigned int v7; // edi
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  v3 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v3 += 8;
  CurrentThreadId = GetCurrentThreadId();
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
    v3,
    &v9,
    &CurrentThreadId);
  if ( v9 == v3 )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    for ( i = *(__int64 **)(v9 + 32); i != (__int64 *)(v9 + 32); i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 5) == a2 )
      {
        v7 = 1;
        goto LABEL_9;
      }
    }
    v7 = 0;
LABEL_9:
    LeaveCriticalSection(v2);
    return v7;
  }
}

```

## disassembly

```asm
0x180018a60  mov     [rsp+arg_8], rbx
0x180018a65  mov     [rsp+arg_18], rsi
0x180018a6a  push    rdi
0x180018a6b  sub     rsp, 20h
0x180018a6f  lea     rbx, [rcx+30h]
0x180018a73  mov     rdi, rcx
0x180018a76  mov     rcx, rbx; lpCriticalSection
0x180018a79  mov     esi, edx
0x180018a7b  call    cs:__imp_EnterCriticalSection
0x180018a81  call    cs:__imp_GetCurrentThreadId
0x180018a87  add     rdi, 8
0x180018a8b  lea     r8, [rsp+28h+arg_0]
0x180018a90  lea     rdx, [rsp+28h+arg_10]
0x180018a95  mov     [rsp+28h+arg_0], eax
0x180018a99  mov     rcx, rdi
0x180018a9c  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180018aa1  mov     rax, [rsp+28h+arg_10]
0x180018aa6  cmp     rax, rdi
0x180018aa9  jnz     short loc_180018AB8
0x180018aab  mov     rcx, rbx; lpCriticalSection
0x180018aae  call    cs:__imp_LeaveCriticalSection
0x180018ab4  xor     eax, eax
0x180018ab6  jmp     short loc_180018AE2
0x180018ab8  lea     rcx, [rax+20h]
0x180018abc  mov     rax, [rcx]
0x180018abf  cmp     rax, rcx
0x180018ac2  jz      short loc_180018AD5
0x180018ac4  cmp     [rax+14h], esi
0x180018ac7  jz      short loc_180018ACE
0x180018ac9  mov     rax, [rax]
0x180018acc  jmp     short loc_180018ABF
0x180018ace  mov     edi, 1
0x180018ad3  jmp     short loc_180018AD7
0x180018ad5  xor     edi, edi
0x180018ad7  mov     rcx, rbx; lpCriticalSection
0x180018ada  call    cs:__imp_LeaveCriticalSection
0x180018ae0  mov     eax, edi
0x180018ae2  mov     rbx, [rsp+28h+arg_8]
0x180018ae7  mov     rsi, [rsp+28h+arg_18]
0x180018aec  add     rsp, 20h
0x180018af0  pop     rdi
0x180018af1  retn
```
