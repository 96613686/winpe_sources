# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140006944`
- end: `0x1400069cf`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `139`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a24`
- `0x14000681c`
- `0x1400068b4`

## callees

- `0x140006944`
- `0x1400073ac`

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
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v8; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rdx
  __int64 v10; // rax
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (wil::details_abi::SubscriptionList *)((char *)this + 40);
  *a2 = 0;
  v5 = *((_QWORD *)this + 5);
  v6 = 0;
  v8 = (unsigned __int64)(*((_QWORD *)v4 + 1) - v5) >> 4;
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((char *)v6 + 1);
      v10 = 2LL * (_QWORD)v6;
      if ( !*(_QWORD *)(v5 + 8 * v10) )
        break;
      v6 = v9;
      if ( (unsigned __int64)v9 >= v8 )
        goto LABEL_4;
    }
    *(_QWORD *)(v5 + 8 * v10) = a3;
    *(_QWORD *)(v5 + 8 * v10 + 8) = a4;
    *a2 = v9;
  }
  else
  {
LABEL_4:
    v11[0] = a3;
    v11[1] = a4;
    if ( wil::details_abi::heap_buffer::push_back(v4, v11, 0x10u) )
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
  }
}

```

## disassembly

```asm
0x140006944  mov     [rsp+arg_0], rbx
0x140006949  push    rdi
0x14000694a  sub     rsp, 30h
0x14000694e  lea     rbx, [rcx+28h]
0x140006952  mov     qword ptr [rdx], 0
0x140006959  mov     rcx, [rbx]
0x14000695c  xor     eax, eax
0x14000695e  mov     r10, [rbx+8]
0x140006962  mov     rdi, rdx
0x140006965  sub     r10, rcx
0x140006968  shr     r10, 4
0x14000696c  test    r10, r10
0x14000696f  jz      short loc_140006987
0x140006971  lea     rdx, [rax+1]
0x140006975  add     rax, rax
0x140006978  cmp     qword ptr [rcx+rax*8], 0
0x14000697d  jz      short loc_1400069C1
0x14000697f  mov     rax, rdx
0x140006982  cmp     rdx, r10
0x140006985  jb      short loc_140006971
0x140006987  mov     [rsp+38h+var_18], r8
0x14000698c  lea     rdx, [rsp+38h+var_18]; void *
0x140006991  mov     r8d, 10h; unsigned __int64
0x140006997  mov     [rsp+38h+var_10], r9
0x14000699c  mov     rcx, rbx; this
0x14000699f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400069a4  test    al, al
0x1400069a6  jz      short loc_1400069B6
0x1400069a8  mov     rax, [rbx+8]
0x1400069ac  sub     rax, [rbx]
0x1400069af  shr     rax, 4
0x1400069b3  mov     [rdi], rax
0x1400069b6  mov     rbx, [rsp+38h+arg_0]
0x1400069bb  add     rsp, 30h
0x1400069bf  pop     rdi
0x1400069c0  retn
0x1400069c1  mov     [rcx+rax*8], r8
0x1400069c5  mov     [rcx+rax*8+8], r9
0x1400069ca  mov     [rdi], rdx
0x1400069cd  jmp     short loc_1400069B6
```
