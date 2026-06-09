# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000686c`
- end: `0x1400068f4`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `136`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400066a8`
- `0x140006778`

## callees

- `0x14000686c`
- `0x14000715c`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  wil::details_abi::heap_buffer *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *i; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // rdx
  __int64 v9; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (wil::details_abi::SubscriptionList *)((char *)this + 40);
  *a2 = 0;
  v5 = *((_QWORD *)this + 5);
  for ( i = 0; (unsigned __int64)i < (unsigned __int64)(*((_QWORD *)v4 + 1) - v5) >> 4; i = v8 )
  {
    v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((char *)i + 1);
    v9 = 2LL * (_QWORD)i;
    if ( !*(_QWORD *)(v5 + 8 * v9) )
    {
      *(_QWORD *)(v5 + 8 * v9) = a3;
      *(_QWORD *)(v5 + 8 * v9 + 8) = a4;
      *a2 = v8;
      return;
    }
  }
  v10[0] = a3;
  v10[1] = a4;
  if ( wil::details_abi::heap_buffer::push_back(v4, v10, 0x10u) )
    *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
}

```

## disassembly

```asm
0x14000686c  mov     [rsp+arg_0], rbx
0x140006871  push    rdi
0x140006872  sub     rsp, 30h
0x140006876  lea     rbx, [rcx+28h]
0x14000687a  mov     qword ptr [rdx], 0
0x140006881  mov     rcx, [rbx]
0x140006884  xor     eax, eax
0x140006886  mov     r10, [rbx+8]
0x14000688a  mov     rdi, rdx
0x14000688d  sub     r10, rcx
0x140006890  shr     r10, 4
0x140006894  cmp     rax, r10
0x140006897  jnb     short loc_1400068BA
0x140006899  lea     rdx, [rax+1]
0x14000689d  add     rax, rax
0x1400068a0  cmp     qword ptr [rcx+rax*8], 0
0x1400068a5  jz      short loc_1400068AC
0x1400068a7  mov     rax, rdx
0x1400068aa  jmp     short loc_140006894
0x1400068ac  mov     [rcx+rax*8], r8
0x1400068b0  mov     [rcx+rax*8+8], r9
0x1400068b5  mov     [rdi], rdx
0x1400068b8  jmp     short loc_1400068E9
0x1400068ba  mov     [rsp+38h+var_18], r8
0x1400068bf  lea     rdx, [rsp+38h+var_18]; void *
0x1400068c4  mov     r8d, 10h; unsigned __int64
0x1400068ca  mov     [rsp+38h+var_10], r9
0x1400068cf  mov     rcx, rbx; this
0x1400068d2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400068d7  test    al, al
0x1400068d9  jz      short loc_1400068E9
0x1400068db  mov     rax, [rbx+8]
0x1400068df  sub     rax, [rbx]
0x1400068e2  shr     rax, 4
0x1400068e6  mov     [rdi], rax
0x1400068e9  mov     rbx, [rsp+38h+arg_0]
0x1400068ee  add     rsp, 30h
0x1400068f2  pop     rdi
0x1400068f3  retn
```
