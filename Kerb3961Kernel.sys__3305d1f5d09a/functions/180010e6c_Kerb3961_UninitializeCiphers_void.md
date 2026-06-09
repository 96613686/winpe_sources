# Kerb3961::UninitializeCiphers(void)

- ea: `0x180010e6c`
- end: `0x180010f38`
- name: `?UninitializeCiphers@Kerb3961@@YAXXZ`
- size: `204`
- prototype: `void __fastcall(Kerb3961 *__hidden this)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bcd0`
- `0x18000bdc0`
- `0x18000beb0`
- `0x18000c580`
- `0x18000c710`
- `0x18000cbd0`
- `0x18000cd60`
- `0x18000d000`

## callees

- `0x180003a38`
- `0x180006c38`
- `0x18000d128`
- `0x180010e6c`
- `0x180012240`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180010f0c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180010f0c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010f18`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010f18`

## pseudocode

```c
void __fastcall Kerb3961::UninitializeCiphers(Kerb3961 *this)
{
  const unsigned __int16 *v1; // rdx
  unsigned int v2; // eax
  __int64 i; // rbx
  __int64 v4; // rdx
  __int64 j; // rbx
  __int64 v6; // rdx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  wil::push_lock::acquire_exclusive(&Kerb3961::g_cipherLock, &v7);
  v2 = Kerb3961::g_ciphersInitialized;
  if ( !Kerb3961::g_ciphersInitialized )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Cannot uninitialize ciphers that are not initialized", v1);
  --Kerb3961::g_ciphersInitialized;
  if ( v2 == 1 )
  {
    for ( i = qword_18001A3C0;
          (_UNKNOWN **)i != &Kerb3961::g_encryptions;
          i = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(i, v4) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(i + 32) + 24LL))(*(_QWORD *)(i + 32));
      LOBYTE(v4) = 1;
    }
    for ( j = qword_18001A3E0;
          (_UNKNOWN **)j != &Kerb3961::g_checksums;
          j = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(j, v6) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(j + 32) + 24LL))(*(_QWORD *)(j + 32));
      LOBYTE(v6) = 1;
    }
  }
  if ( v7 )
  {
    ExReleasePushLockExclusiveEx(v7, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x180010e6c  push    rbx
0x180010e6e  sub     rsp, 20h
0x180010e72  lea     rdx, [rsp+28h+arg_8]
0x180010e77  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x180010e7e  call    ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x180010e83  mov     eax, cs:?g_ciphersInitialized@Kerb3961@@3IA; uint Kerb3961::g_ciphersInitialized
0x180010e89  test    eax, eax
0x180010e8b  jz      loc_180010F2B
0x180010e91  add     eax, 0FFFFFFFFh
0x180010e94  mov     cs:?g_ciphersInitialized@Kerb3961@@3IA, eax; uint Kerb3961::g_ciphersInitialized
0x180010e9a  jnz     short loc_180010F00
0x180010e9c  mov     rbx, cs:qword_18001A3C0
0x180010ea3  lea     rax, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x180010eaa  cmp     rbx, rax
0x180010ead  jz      short loc_180010ECE
0x180010eaf  mov     rcx, [rbx+20h]
0x180010eb3  mov     rax, [rcx]
0x180010eb6  mov     rax, [rax+18h]
0x180010eba  call    _guard_dispatch_icall
0x180010ebf  mov     dl, 1
0x180010ec1  mov     rcx, rbx
0x180010ec4  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x180010ec9  mov     rbx, rax
0x180010ecc  jmp     short loc_180010EA3
0x180010ece  mov     rbx, cs:qword_18001A3E0
0x180010ed5  lea     rax, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x180010edc  cmp     rbx, rax
0x180010edf  jz      short loc_180010F00
0x180010ee1  mov     rcx, [rbx+20h]
0x180010ee5  mov     rax, [rcx]
0x180010ee8  mov     rax, [rax+18h]
0x180010eec  call    _guard_dispatch_icall
0x180010ef1  mov     dl, 1
0x180010ef3  mov     rcx, rbx
0x180010ef6  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x180010efb  mov     rbx, rax
0x180010efe  jmp     short loc_180010ED5
0x180010f00  mov     rcx, [rsp+28h+arg_8]
0x180010f05  test    rcx, rcx
0x180010f08  jz      short loc_180010F24
0x180010f0a  xor     edx, edx
0x180010f0c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180010f13  nop     dword ptr [rax+rax+00h]
0x180010f18  call    cs:__imp_KeLeaveCriticalRegion
0x180010f1f  nop     dword ptr [rax+rax+00h]
0x180010f24  add     rsp, 20h
0x180010f28  pop     rbx
0x180010f29  retn
0x180010f2b  lea     rcx, aCannotUninitia; "Cannot uninitialize ciphers that are no"...
0x180010f32  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
