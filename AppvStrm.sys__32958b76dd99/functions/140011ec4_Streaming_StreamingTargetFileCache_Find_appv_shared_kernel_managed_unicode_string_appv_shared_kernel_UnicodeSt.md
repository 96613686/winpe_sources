# Streaming::StreamingTargetFileCache::Find(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)

- ea: `0x140011ec4`
- end: `0x140011f2a`
- name: `?Find@StreamingTargetFileCache@Streaming@@AEAAJAEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011cb0`
- `0x140011f30`

## callees

- `0x140003bd8`
- `0x140011ec4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140011eee`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011eee`

## pseudocode

```c
__int64 __fastcall Streaming::StreamingTargetFileCache::Find(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rsi

  v3 = *(_QWORD *)(a1 + 48);
  v4 = a1 + 24;
  while ( v3 != v4 )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)v3 + 40LL), a2 + 1, 1u) )
    {
      *(_QWORD *)a3 = *(_QWORD *)v3;
      kernel_std::detail::shared_count::operator=(
        (volatile signed __int32 **)(a3 + 8),
        (volatile signed __int32 **)(v3 + 8));
      return 0;
    }
    v3 = *(_QWORD *)(v3 + 24);
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140011ec4  push    rbx
0x140011ec6  push    rbp
0x140011ec7  push    rsi
0x140011ec8  push    rdi
0x140011ec9  sub     rsp, 28h
0x140011ecd  mov     rbx, [rcx+30h]
0x140011ed1  lea     rsi, [rcx+18h]
0x140011ed5  mov     rdi, r8
0x140011ed8  mov     rbp, rdx
0x140011edb  cmp     rbx, rsi
0x140011ede  jz      short loc_140011F1B
0x140011ee0  mov     rcx, [rbx]
0x140011ee3  lea     rdx, [rbp+10h]; String2
0x140011ee7  add     rcx, 28h ; '('; String1
0x140011eeb  mov     r8b, 1; CaseInSensitive
0x140011eee  call    cs:__imp_RtlCompareUnicodeString
0x140011ef5  nop     dword ptr [rax+rax+00h]
0x140011efa  test    eax, eax
0x140011efc  jz      short loc_140011F04
0x140011efe  mov     rbx, [rbx+18h]
0x140011f02  jmp     short loc_140011EDB
0x140011f04  mov     rax, [rbx]
0x140011f07  lea     rdx, [rbx+8]
0x140011f0b  lea     rcx, [rdi+8]
0x140011f0f  mov     [rdi], rax
0x140011f12  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140011f17  xor     eax, eax
0x140011f19  jmp     short loc_140011F20
0x140011f1b  mov     eax, 0C0000225h
0x140011f20  add     rsp, 28h
0x140011f24  pop     rdi
0x140011f25  pop     rsi
0x140011f26  pop     rbp
0x140011f27  pop     rbx
0x140011f28  retn
```
