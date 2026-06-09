# std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Delete_this

- ea: `0x18000bdb0`
- end: `0x18000bdf3`
- name: `std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Delete_this`
- size: `67`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800029b4`
- `0x180007d70`
- `0x18000bdb0`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const___::_Delete_this(
        _QWORD *Block,
        char a2)
{
  volatile signed __int32 *v4; // rcx

  v4 = (volatile signed __int32 *)Block[1];
  if ( v4 )
  {
    Block[1] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(v4);
  }
  if ( a2 )
    operator delete(Block);
}

```

## disassembly

```asm
0x18000bdb0  mov     [rsp+arg_0], rbx
0x18000bdb5  push    rdi
0x18000bdb6  sub     rsp, 20h
0x18000bdba  mov     rbx, rcx
0x18000bdbd  mov     dil, dl
0x18000bdc0  mov     rcx, [rcx+8]
0x18000bdc4  test    rcx, rcx
0x18000bdc7  jz      short loc_18000BDD6
0x18000bdc9  mov     qword ptr [rbx+8], 0
0x18000bdd1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000bdd6  test    dil, dil
0x18000bdd9  jz      short loc_18000BDE8
0x18000bddb  mov     edx, 10h
0x18000bde0  mov     rcx, rbx; Block
0x18000bde3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bde8  mov     rbx, [rsp+28h+arg_0]
0x18000bded  add     rsp, 20h
0x18000bdf1  pop     rdi
0x18000bdf2  retn
```
