# std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>::_Tidy(void)

- ea: `0x180002614`
- end: `0x1800026ad`
- name: `?_Tidy@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAXXZ`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002218`
- `0x1800026b4`
- `0x18000c970`
- `0x180014dc8`

## callees

- `0x180002614`
- `0x180002ae0`
- `0x180014898`
- `0x180015b58`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(void **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rcx
  signed __int64 v5; // rdx
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = (char *)*a1;
  if ( *a1 )
  {
    v3 = (char *)a1[1];
    while ( v1 != v3 )
    {
      std::shared_ptr<Broker::BILayer::WnfNotification>::`scalar deleting destructor'(v1);
      v1 += 16;
    }
    v4 = (char *)*a1;
    v5 = (_BYTE *)a1[2] - (_BYTE *)*a1;
    v7 = *a1;
    v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
    if ( (v5 & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v7, &v6);
      v4 = (char *)v7;
    }
    operator delete(v4);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180002614  mov     [rsp+arg_10], rbx
0x180002619  mov     [rsp+arg_18], rsi
0x18000261e  push    rdi
0x18000261f  sub     rsp, 20h
0x180002623  mov     rbx, [rcx]
0x180002626  mov     rdi, rcx
0x180002629  test    rbx, rbx
0x18000262c  jz      short loc_180002674
0x18000262e  mov     rsi, [rcx+8]
0x180002632  cmp     rbx, rsi
0x180002635  jnz     short loc_180002684
0x180002637  mov     rcx, [rdi]; void *
0x18000263a  mov     rdx, [rdi+10h]
0x18000263e  sub     rdx, rcx
0x180002641  mov     [rsp+28h+arg_8], rcx
0x180002646  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18000264a  mov     [rsp+28h+arg_0], rdx
0x18000264f  cmp     rdx, 1000h
0x180002656  jnb     short loc_180002692
0x180002658  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000265d  mov     qword ptr [rdi], 0
0x180002664  mov     qword ptr [rdi+8], 0
0x18000266c  mov     qword ptr [rdi+10h], 0
0x180002674  mov     rbx, [rsp+28h+arg_10]
0x180002679  mov     rsi, [rsp+28h+arg_18]
0x18000267e  add     rsp, 20h
0x180002682  pop     rdi
0x180002683  retn
0x180002684  mov     rcx, rbx
0x180002687  call    ??_G?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@QEAAPEAXI@Z; std::shared_ptr<Broker::BILayer::WnfNotification>::`scalar deleting destructor'(uint)
0x18000268c  add     rbx, 10h
0x180002690  jmp     short loc_180002632
0x180002692  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x180002697  lea     rcx, [rsp+28h+arg_8]; void **
0x18000269c  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800026a1  mov     rdx, [rsp+28h+arg_0]
0x1800026a6  mov     rcx, [rsp+28h+arg_8]
0x1800026ab  jmp     short loc_180002658
```
