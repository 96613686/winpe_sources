# std::vector<std::shared_ptr<Broker::ApplicationStateTable::State>,std::allocator<std::shared_ptr<Broker::ApplicationStateTable::State>>>::_Change_array(std::shared_ptr<Broker::ApplicationStateTable::State> * const,unsigned __int64,unsigned __int64)

- ea: `0x180004b34`
- end: `0x180004bda`
- name: `?_Change_array@?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@VState@ApplicationStateTable@Broker@@@2@_K1@Z`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004700`
- `0x18001402c`

## callees

- `0x180002ae0`
- `0x180004b34`
- `0x180014898`
- `0x180015b58`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<Broker::ApplicationStateTable::State>>::_Change_array(
        void **a1,
        char *a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // rbx
  char *v9; // r14
  char *v10; // rcx
  signed __int64 v11; // rdx
  unsigned __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  void *v13; // [rsp+58h] [rbp+10h] BYREF

  v4 = (char *)*a1;
  if ( *a1 )
  {
    v9 = (char *)a1[1];
    while ( v4 != v9 )
    {
      std::shared_ptr<Broker::BILayer::WnfNotification>::`scalar deleting destructor'(v4);
      v4 += 16;
    }
    v10 = (char *)*a1;
    v11 = (_BYTE *)a1[2] - (_BYTE *)*a1;
    v13 = *a1;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    if ( (v11 & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v13, &v12);
      v10 = (char *)v13;
    }
    operator delete(v10);
  }
  *a1 = a2;
  a1[1] = &a2[16 * a3];
  a1[2] = &a2[16 * a4];
}

```

## disassembly

```asm
0x180004b34  mov     [rsp+arg_10], rbx
0x180004b39  push    rbp
0x180004b3a  push    rsi
0x180004b3b  push    rdi
0x180004b3c  push    r14
0x180004b3e  push    r15
0x180004b40  sub     rsp, 20h
0x180004b44  mov     rbx, [rcx]
0x180004b47  mov     rsi, r9
0x180004b4a  mov     rbp, r8
0x180004b4d  mov     r15, rdx
0x180004b50  mov     rdi, rcx
0x180004b53  test    rbx, rbx
0x180004b56  jz      short loc_180004B87
0x180004b58  mov     r14, [rcx+8]
0x180004b5c  cmp     rbx, r14
0x180004b5f  jnz     short loc_180004BB1
0x180004b61  mov     rcx, [rdi]; void *
0x180004b64  mov     rdx, [rdi+10h]
0x180004b68  sub     rdx, rcx
0x180004b6b  mov     [rsp+48h+arg_8], rcx
0x180004b70  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180004b74  mov     [rsp+48h+arg_0], rdx
0x180004b79  cmp     rdx, 1000h
0x180004b80  jnb     short loc_180004BBF
0x180004b82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004b87  mov     rbx, [rsp+48h+arg_10]
0x180004b8c  shl     rbp, 4
0x180004b90  add     rbp, r15
0x180004b93  mov     [rdi], r15
0x180004b96  shl     rsi, 4
0x180004b9a  add     rsi, r15
0x180004b9d  mov     [rdi+8], rbp
0x180004ba1  mov     [rdi+10h], rsi
0x180004ba5  add     rsp, 20h
0x180004ba9  pop     r15
0x180004bab  pop     r14
0x180004bad  pop     rdi
0x180004bae  pop     rsi
0x180004baf  pop     rbp
0x180004bb0  retn
0x180004bb1  mov     rcx, rbx
0x180004bb4  call    ??_G?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@QEAAPEAXI@Z; std::shared_ptr<Broker::BILayer::WnfNotification>::`scalar deleting destructor'(uint)
0x180004bb9  add     rbx, 10h
0x180004bbd  jmp     short loc_180004B5C
0x180004bbf  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x180004bc4  lea     rcx, [rsp+48h+arg_8]; void **
0x180004bc9  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180004bce  mov     rdx, [rsp+48h+arg_0]
0x180004bd3  mov     rcx, [rsp+48h+arg_8]
0x180004bd8  jmp     short loc_180004B82
```
