# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a9e0`
- end: `0x18000aa90`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a8e4`
- `0x18000ad20`

## callees

- `0x18000a9e0`
- `0x18000afc4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aa5e`
- `msvcrt!memcpy_s` at `0x18000aa5e`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  char *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v8; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rdx
  __int64 v10; // rax
  _QWORD Source[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (char *)this + 40;
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
    Source[0] = a3;
    Source[1] = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v4, 0x10u) )
    {
      memcpy_s(
        *((void *const *)v4 + 1),
        (*((_QWORD *)v4 + 2) - *((_QWORD *)v4 + 1)) & -(__int64)(*((_QWORD *)v4 + 1) < *((_QWORD *)v4 + 2)),
        Source,
        0x10u);
      *((_QWORD *)v4 + 1) += 16LL;
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
    }
  }
}

```

## disassembly

```asm
0x18000a9e0  mov     [rsp+arg_0], rbx
0x18000a9e5  push    rdi
0x18000a9e6  sub     rsp, 30h
0x18000a9ea  lea     rbx, [rcx+28h]
0x18000a9ee  mov     qword ptr [rdx], 0
0x18000a9f5  mov     rcx, [rbx]
0x18000a9f8  xor     eax, eax
0x18000a9fa  mov     r10, [rbx+8]
0x18000a9fe  mov     rdi, rdx
0x18000aa01  sub     r10, rcx
0x18000aa04  shr     r10, 4
0x18000aa08  test    r10, r10
0x18000aa0b  jz      short loc_18000AA23
0x18000aa0d  lea     rdx, [rax+1]
0x18000aa11  add     rax, rax
0x18000aa14  cmp     qword ptr [rcx+rax*8], 0
0x18000aa19  jz      short loc_18000AA82
0x18000aa1b  mov     rax, rdx
0x18000aa1e  cmp     rdx, r10
0x18000aa21  jb      short loc_18000AA0D
0x18000aa23  mov     edx, 10h; unsigned __int64
0x18000aa28  mov     [rsp+38h+Source], r8
0x18000aa2d  mov     rcx, rbx; this
0x18000aa30  mov     [rsp+38h+var_10], r9
0x18000aa35  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aa3a  test    al, al
0x18000aa3c  jz      short loc_18000AA77
0x18000aa3e  mov     rcx, [rbx+8]; Destination
0x18000aa42  lea     r8, [rsp+38h+Source]; Source
0x18000aa47  mov     rax, [rbx+10h]
0x18000aa4b  mov     r9d, 10h; SourceSize
0x18000aa51  sub     rax, rcx
0x18000aa54  cmp     rcx, [rbx+10h]
0x18000aa58  sbb     rdx, rdx
0x18000aa5b  and     rdx, rax; DestinationSize
0x18000aa5e  call    cs:__imp_memcpy_s
0x18000aa64  add     qword ptr [rbx+8], 10h
0x18000aa69  mov     rax, [rbx+8]
0x18000aa6d  sub     rax, [rbx]
0x18000aa70  shr     rax, 4
0x18000aa74  mov     [rdi], rax
0x18000aa77  mov     rbx, [rsp+38h+arg_0]
0x18000aa7c  add     rsp, 30h
0x18000aa80  pop     rdi
0x18000aa81  retn
0x18000aa82  mov     [rcx+rax*8], r8
0x18000aa86  mov     [rcx+rax*8+8], r9
0x18000aa8b  mov     [rdi], rdx
0x18000aa8e  jmp     short loc_18000AA77
```
