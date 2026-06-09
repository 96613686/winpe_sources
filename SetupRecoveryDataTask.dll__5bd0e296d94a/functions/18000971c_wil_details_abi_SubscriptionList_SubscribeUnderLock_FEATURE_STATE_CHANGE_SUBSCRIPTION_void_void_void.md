# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000971c`
- end: `0x1800097cc`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009618`
- `0x180009e50`

## callees

- `0x18000971c`
- `0x18000af9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000979a`
- `msvcrt!memcpy_s` at `0x18000979a`

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
0x18000971c  mov     [rsp+arg_0], rbx
0x180009721  push    rdi
0x180009722  sub     rsp, 30h
0x180009726  lea     rbx, [rcx+28h]
0x18000972a  mov     qword ptr [rdx], 0
0x180009731  mov     rcx, [rbx]
0x180009734  xor     eax, eax
0x180009736  mov     r10, [rbx+8]
0x18000973a  mov     rdi, rdx
0x18000973d  sub     r10, rcx
0x180009740  shr     r10, 4
0x180009744  test    r10, r10
0x180009747  jz      short loc_18000975F
0x180009749  lea     rdx, [rax+1]
0x18000974d  add     rax, rax
0x180009750  cmp     qword ptr [rcx+rax*8], 0
0x180009755  jz      short loc_1800097BE
0x180009757  mov     rax, rdx
0x18000975a  cmp     rdx, r10
0x18000975d  jb      short loc_180009749
0x18000975f  mov     edx, 10h; unsigned __int64
0x180009764  mov     [rsp+38h+Source], r8
0x180009769  mov     rcx, rbx; this
0x18000976c  mov     [rsp+38h+var_10], r9
0x180009771  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009776  test    al, al
0x180009778  jz      short loc_1800097B3
0x18000977a  mov     rcx, [rbx+8]; Destination
0x18000977e  lea     r8, [rsp+38h+Source]; Source
0x180009783  mov     rax, [rbx+10h]
0x180009787  mov     r9d, 10h; SourceSize
0x18000978d  sub     rax, rcx
0x180009790  cmp     rcx, [rbx+10h]
0x180009794  sbb     rdx, rdx
0x180009797  and     rdx, rax; DestinationSize
0x18000979a  call    cs:__imp_memcpy_s
0x1800097a0  add     qword ptr [rbx+8], 10h
0x1800097a5  mov     rax, [rbx+8]
0x1800097a9  sub     rax, [rbx]
0x1800097ac  shr     rax, 4
0x1800097b0  mov     [rdi], rax
0x1800097b3  mov     rbx, [rsp+38h+arg_0]
0x1800097b8  add     rsp, 30h
0x1800097bc  pop     rdi
0x1800097bd  retn
0x1800097be  mov     [rcx+rax*8], r8
0x1800097c2  mov     [rcx+rax*8+8], r9
0x1800097c7  mov     [rdi], rdx
0x1800097ca  jmp     short loc_1800097B3
```
