# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400116a4`
- end: `0x140011754`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400115a8`
- `0x140011a60`

## callees

- `0x1400116a4`
- `0x140011fcc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011722`
- `msvcrt!memcpy_s` at `0x140011722`

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
0x1400116a4  mov     [rsp+arg_0], rbx
0x1400116a9  push    rdi
0x1400116aa  sub     rsp, 30h
0x1400116ae  lea     rbx, [rcx+28h]
0x1400116b2  mov     qword ptr [rdx], 0
0x1400116b9  mov     rcx, [rbx]
0x1400116bc  xor     eax, eax
0x1400116be  mov     r10, [rbx+8]
0x1400116c2  mov     rdi, rdx
0x1400116c5  sub     r10, rcx
0x1400116c8  shr     r10, 4
0x1400116cc  test    r10, r10
0x1400116cf  jz      short loc_1400116E7
0x1400116d1  lea     rdx, [rax+1]
0x1400116d5  add     rax, rax
0x1400116d8  cmp     qword ptr [rcx+rax*8], 0
0x1400116dd  jz      short loc_140011746
0x1400116df  mov     rax, rdx
0x1400116e2  cmp     rdx, r10
0x1400116e5  jb      short loc_1400116D1
0x1400116e7  mov     edx, 10h; unsigned __int64
0x1400116ec  mov     [rsp+38h+Source], r8
0x1400116f1  mov     rcx, rbx; this
0x1400116f4  mov     [rsp+38h+var_10], r9
0x1400116f9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400116fe  test    al, al
0x140011700  jz      short loc_14001173B
0x140011702  mov     rcx, [rbx+8]; Destination
0x140011706  lea     r8, [rsp+38h+Source]; Source
0x14001170b  mov     rax, [rbx+10h]
0x14001170f  mov     r9d, 10h; SourceSize
0x140011715  sub     rax, rcx
0x140011718  cmp     rcx, [rbx+10h]
0x14001171c  sbb     rdx, rdx
0x14001171f  and     rdx, rax; DestinationSize
0x140011722  call    cs:__imp_memcpy_s
0x140011728  add     qword ptr [rbx+8], 10h
0x14001172d  mov     rax, [rbx+8]
0x140011731  sub     rax, [rbx]
0x140011734  shr     rax, 4
0x140011738  mov     [rdi], rax
0x14001173b  mov     rbx, [rsp+38h+arg_0]
0x140011740  add     rsp, 30h
0x140011744  pop     rdi
0x140011745  retn
0x140011746  mov     [rcx+rax*8], r8
0x14001174a  mov     [rcx+rax*8+8], r9
0x14001174f  mov     [rdi], rdx
0x140011752  jmp     short loc_14001173B
```
