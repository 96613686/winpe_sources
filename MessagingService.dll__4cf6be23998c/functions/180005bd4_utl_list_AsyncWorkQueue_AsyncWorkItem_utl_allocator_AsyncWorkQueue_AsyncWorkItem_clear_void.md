# utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(void)

- ea: `0x180005bd4`
- end: `0x180005c61`
- name: `?clear@?$list@UAsyncWorkItem@AsyncWorkQueue@@V?$allocator@UAsyncWorkItem@AsyncWorkQueue@@@utl@@@utl@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000547c`
- `0x1800058c8`

## callees

- `0x18000266c`
- `0x180003da4`
- `0x180005bd4`
- `0x18000aa50`
- `0x18000c010`

## pseudocode

```c
void __fastcall utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(
        __int64 a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx

  while ( 1 )
  {
    v2 = *(__int64 **)a1;
    if ( *(_QWORD *)a1 == a1 )
      break;
    v3 = (__int64 *)v2[1];
    v4 = *v2;
    *v3 = *v2;
    *(_QWORD *)(v4 + 8) = v3;
    v5 = v2[3];
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(v2 + 2);
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180005bd4  mov     [rsp+arg_8], rbx
0x180005bd9  mov     [rsp+arg_10], rsi
0x180005bde  push    rdi
0x180005bdf  sub     rsp, 30h
0x180005be3  mov     rax, cs:__security_cookie
0x180005bea  xor     rax, rsp
0x180005bed  mov     [rsp+38h+var_18], rax
0x180005bf2  mov     rdi, rcx
0x180005bf5  mov     rbx, [rdi]
0x180005bf8  cmp     rbx, rdi
0x180005bfb  jz      short loc_180005C3C
0x180005bfd  mov     rdx, [rbx+8]
0x180005c01  mov     rax, [rbx]
0x180005c04  mov     [rdx], rax
0x180005c07  mov     [rax+8], rdx
0x180005c0b  mov     rcx, [rbx+18h]
0x180005c0f  test    rcx, rcx
0x180005c12  jz      short loc_180005C21
0x180005c14  mov     rax, [rcx]
0x180005c17  mov     rax, [rax+10h]
0x180005c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c20  nop
0x180005c21  lea     rcx, [rbx+10h]
0x180005c25  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005c2a  nop
0x180005c2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c32  mov     rcx, rbx; void *
0x180005c35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005c3a  jmp     short loc_180005BF5
0x180005c3c  mov     qword ptr [rdi+10h], 0
0x180005c44  mov     rcx, [rsp+38h+var_18]
0x180005c49  xor     rcx, rsp; StackCookie
0x180005c4c  call    __security_check_cookie
0x180005c51  mov     rbx, [rsp+38h+arg_8]
0x180005c56  mov     rsi, [rsp+38h+arg_10]
0x180005c5b  add     rsp, 30h
0x180005c5f  pop     rdi
0x180005c60  retn
```
