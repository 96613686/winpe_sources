# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)

- ea: `0x140004c40`
- end: `0x140004cd7`
- name: `?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z`
- size: `151`
- prototype: `_QWORD *__fastcall(_DWORD *, _QWORD *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b50`
- `0x140003c58`
- `0x14000d4bc`
- `0x140011bf8`
- `0x140011cb0`
- `0x140013850`

## callees

- `0x140004c40`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004cbb`

## pseudocode

```c
_QWORD *__fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v3; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r8
  volatile signed __int32 *v9; // rbx

  v3 = *(_QWORD **)a3;
  *a2 = *(_QWORD *)a3;
  *a2 = v3[3];
  v6 = *(_QWORD **)a3;
  v7 = *(_QWORD *)(*(_QWORD *)a3 + 16LL);
  v8 = *(_QWORD *)(*(_QWORD *)a3 + 24LL);
  *(_QWORD *)(v7 + 24) = v8;
  *(_QWORD *)(v8 + 16) = v7;
  if ( v6 )
  {
    v9 = (volatile signed __int32 *)v6[1];
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    ExFreePoolWithTag(v6, 0);
  }
  --*a1;
  return a2;
}

```

## disassembly

```asm
0x140004c40  push    rbx
0x140004c42  push    rsi
0x140004c43  push    rdi
0x140004c44  push    r14
0x140004c46  sub     rsp, 28h
0x140004c4a  mov     rax, [r8]
0x140004c4d  mov     r14, rdx
0x140004c50  mov     [rdx], rax
0x140004c53  mov     rsi, rcx
0x140004c56  mov     rax, [rax+18h]
0x140004c5a  mov     [rdx], rax
0x140004c5d  mov     rdi, [r8]
0x140004c60  mov     rax, [rdi+10h]
0x140004c64  mov     r8, [rdi+18h]
0x140004c68  mov     [rax+18h], r8
0x140004c6c  mov     [r8+10h], rax
0x140004c70  test    rdi, rdi
0x140004c73  jz      short loc_140004CC7
0x140004c75  mov     rbx, [rdi+8]
0x140004c79  test    rbx, rbx
0x140004c7c  jz      short loc_140004CB6
0x140004c7e  or      eax, 0FFFFFFFFh
0x140004c81  lock xadd [rbx+8], eax
0x140004c86  cmp     eax, 1
0x140004c89  jnz     short loc_140004CB6
0x140004c8b  mov     rax, [rbx]
0x140004c8e  mov     rcx, rbx
0x140004c91  mov     rax, [rax+8]
0x140004c95  call    _guard_dispatch_icall
0x140004c9a  or      eax, 0FFFFFFFFh
0x140004c9d  lock xadd [rbx+0Ch], eax
0x140004ca2  cmp     eax, 1
0x140004ca5  jnz     short loc_140004CB6
0x140004ca7  mov     rax, [rbx]
0x140004caa  mov     rcx, rbx
0x140004cad  mov     rax, [rax+10h]
0x140004cb1  call    _guard_dispatch_icall
0x140004cb6  xor     edx, edx; Tag
0x140004cb8  mov     rcx, rdi; P
0x140004cbb  call    cs:__imp_ExFreePoolWithTag
0x140004cc2  nop     dword ptr [rax+rax+00h]
0x140004cc7  dec     dword ptr [rsi]
0x140004cc9  mov     rax, r14
0x140004ccc  add     rsp, 28h
0x140004cd0  pop     r14
0x140004cd2  pop     rdi
0x140004cd3  pop     rsi
0x140004cd4  pop     rbx
0x140004cd5  retn
```
