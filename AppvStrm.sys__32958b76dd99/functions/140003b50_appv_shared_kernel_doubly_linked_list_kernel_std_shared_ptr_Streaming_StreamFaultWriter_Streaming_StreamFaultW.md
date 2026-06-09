# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)

- ea: `0x140003b50`
- end: `0x140003bd2`
- name: `??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003aa8`
- `0x14000528c`
- `0x1400062bc`
- `0x140007bc0`
- `0x1400133f4`

## callees

- `0x140003b50`
- `0x140004c40`
- `0x140015b30`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdi
  volatile signed __int32 *v4; // rbx
  signed __int32 v5; // eax
  bool v6; // zf
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+38h] [rbp+10h] BYREF

  result = *(_QWORD *)(a1 + 32);
  v2 = a1 + 8;
  while ( result != v2 )
  {
    v7 = result;
    result = *(_QWORD *)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
                          a1,
                          &v8,
                          &v7);
  }
  v4 = *(volatile signed __int32 **)(a1 + 16);
  if ( v4 )
  {
    v5 = _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF);
    v6 = v5 == 1;
    result = (unsigned int)(v5 - 1);
    if ( v6 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      result = (unsigned int)_InterlockedDecrement(v4 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003b50  mov     [rsp+arg_10], rbx
0x140003b55  push    rdi
0x140003b56  sub     rsp, 20h
0x140003b5a  mov     rax, [rcx+20h]
0x140003b5e  lea     rdi, [rcx+8]
0x140003b62  mov     rbx, rcx
0x140003b65  cmp     rax, rdi
0x140003b68  jz      short loc_140003B86
0x140003b6a  lea     r8, [rsp+28h+arg_0]
0x140003b6f  mov     [rsp+28h+arg_0], rax
0x140003b74  lea     rdx, [rsp+28h+arg_8]
0x140003b79  mov     rcx, rbx
0x140003b7c  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x140003b81  mov     rax, [rax]
0x140003b84  jmp     short loc_140003B65
0x140003b86  mov     rbx, [rbx+10h]
0x140003b8a  test    rbx, rbx
0x140003b8d  jz      short loc_140003BC6
0x140003b8f  or      edi, 0FFFFFFFFh
0x140003b92  mov     eax, edi
0x140003b94  lock xadd [rbx+8], eax
0x140003b99  add     eax, edi
0x140003b9b  jnz     short loc_140003BC6
0x140003b9d  mov     rax, [rbx]
0x140003ba0  mov     rcx, rbx
0x140003ba3  mov     rax, [rax+8]
0x140003ba7  call    _guard_dispatch_icall
0x140003bac  mov     eax, edi
0x140003bae  lock xadd [rbx+0Ch], eax
0x140003bb3  add     eax, edi
0x140003bb5  jnz     short loc_140003BC6
0x140003bb7  mov     rax, [rbx]
0x140003bba  mov     rcx, rbx
0x140003bbd  mov     rax, [rax+10h]
0x140003bc1  call    _guard_dispatch_icall
0x140003bc6  mov     rbx, [rsp+28h+arg_10]
0x140003bcb  add     rsp, 20h
0x140003bcf  pop     rdi
0x140003bd0  retn
```
