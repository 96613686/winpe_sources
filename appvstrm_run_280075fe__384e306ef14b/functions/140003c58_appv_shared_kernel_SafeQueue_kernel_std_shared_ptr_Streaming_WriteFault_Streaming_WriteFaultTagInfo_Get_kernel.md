# appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)

- ea: `0x140003c58`
- end: `0x140003d3a`
- name: `?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z`
- size: `226`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044a0`
- `0x1400048a8`
- `0x140006c08`
- `0x140006fe0`
- `0x1400073b8`
- `0x14000e7f8`
- `0x14000ebd0`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x140004c40`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003cc1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003d1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003cc1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003d1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003cb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003d11`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003cb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003d11`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003c8c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003c8c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003c79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003c79`

## pseudocode

```c
char __fastcall appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
        __int64 a1,
        _QWORD *a2)
{
  bool v2; // di
  struct _ERESOURCE *v5; // rcx
  _QWORD *v7; // rdx
  struct _ERESOURCE *v8; // rcx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( *(_QWORD *)(a1 + 48) )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 48), 1u) == 1;
  }
  if ( *(_DWORD *)a1 )
  {
    v7 = *(_QWORD **)(a1 + 32);
    *a2 = *v7;
    kernel_std::detail::shared_count::operator=(a2 + 1, v7 + 1);
    v9 = *(_QWORD *)(a1 + 32);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
      a1,
      &v10,
      &v9);
    if ( v2 )
    {
      v8 = *(struct _ERESOURCE **)(a1 + 48);
      if ( v8 )
      {
        ExReleaseResourceLite(v8);
        KeLeaveCriticalRegion();
      }
    }
    return 1;
  }
  else
  {
    if ( v2 )
    {
      v5 = *(struct _ERESOURCE **)(a1 + 48);
      if ( v5 )
      {
        ExReleaseResourceLite(v5);
        KeLeaveCriticalRegion();
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140003c58  mov     [rsp+arg_8], rbx
0x140003c5d  push    rbp
0x140003c5e  push    rsi
0x140003c5f  push    rdi
0x140003c60  sub     rsp, 20h
0x140003c64  xor     dil, dil
0x140003c67  mov     rsi, rdx
0x140003c6a  cmp     qword ptr [rcx+30h], 0
0x140003c6f  mov     rbx, rcx
0x140003c72  mov     ebp, 1
0x140003c77  jz      short loc_140003CA2
0x140003c79  call    cs:__imp_KeEnterCriticalRegion
0x140003c80  nop     dword ptr [rax+rax+00h]
0x140003c85  mov     rcx, [rbx+30h]; Resource
0x140003c89  mov     dl, bpl; Wait
0x140003c8c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003c93  nop     dword ptr [rax+rax+00h]
0x140003c98  cmp     al, bpl
0x140003c9b  movzx   edi, dil
0x140003c9f  cmovz   edi, ebp
0x140003ca2  cmp     dword ptr [rbx], 0
0x140003ca5  jnz     short loc_140003CD1
0x140003ca7  test    dil, dil
0x140003caa  jz      short loc_140003CCD
0x140003cac  mov     rcx, [rbx+30h]; Resource
0x140003cb0  test    rcx, rcx
0x140003cb3  jz      short loc_140003CCD
0x140003cb5  call    cs:__imp_ExReleaseResourceLite
0x140003cbc  nop     dword ptr [rax+rax+00h]
0x140003cc1  call    cs:__imp_KeLeaveCriticalRegion
0x140003cc8  nop     dword ptr [rax+rax+00h]
0x140003ccd  xor     al, al
0x140003ccf  jmp     short loc_140003D2C
0x140003cd1  mov     rdx, [rbx+20h]
0x140003cd5  lea     rcx, [rsi+8]
0x140003cd9  mov     rax, [rdx]
0x140003cdc  add     rdx, 8
0x140003ce0  mov     [rsi], rax
0x140003ce3  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140003ce8  mov     rax, [rbx+20h]
0x140003cec  lea     r8, [rsp+38h+arg_0]
0x140003cf1  lea     rdx, [rsp+38h+arg_10]
0x140003cf6  mov     [rsp+38h+arg_0], rax
0x140003cfb  mov     rcx, rbx
0x140003cfe  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x140003d03  test    dil, dil
0x140003d06  jz      short loc_140003D29
0x140003d08  mov     rcx, [rbx+30h]; Resource
0x140003d0c  test    rcx, rcx
0x140003d0f  jz      short loc_140003D29
0x140003d11  call    cs:__imp_ExReleaseResourceLite
0x140003d18  nop     dword ptr [rax+rax+00h]
0x140003d1d  call    cs:__imp_KeLeaveCriticalRegion
0x140003d24  nop     dword ptr [rax+rax+00h]
0x140003d29  mov     al, bpl
0x140003d2c  mov     rbx, [rsp+38h+arg_8]
0x140003d31  add     rsp, 20h
0x140003d35  pop     rdi
0x140003d36  pop     rsi
0x140003d37  pop     rbp
0x140003d38  retn
```
