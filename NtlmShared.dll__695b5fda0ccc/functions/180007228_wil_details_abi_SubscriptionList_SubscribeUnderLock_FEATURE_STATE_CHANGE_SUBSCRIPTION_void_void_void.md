# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007228`
- end: `0x1800072d8`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000712c`
- `0x180007850`

## callees

- `0x180007228`
- `0x180007cdc`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800072a6`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800072a6`

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
0x180007228  mov     [rsp+arg_0], rbx
0x18000722d  push    rdi
0x18000722e  sub     rsp, 30h
0x180007232  lea     rbx, [rcx+28h]
0x180007236  mov     qword ptr [rdx], 0
0x18000723d  mov     rcx, [rbx]
0x180007240  xor     eax, eax
0x180007242  mov     r10, [rbx+8]
0x180007246  mov     rdi, rdx
0x180007249  sub     r10, rcx
0x18000724c  shr     r10, 4
0x180007250  test    r10, r10
0x180007253  jz      short loc_18000726B
0x180007255  lea     rdx, [rax+1]
0x180007259  add     rax, rax
0x18000725c  cmp     qword ptr [rcx+rax*8], 0
0x180007261  jz      short loc_1800072CA
0x180007263  mov     rax, rdx
0x180007266  cmp     rdx, r10
0x180007269  jb      short loc_180007255
0x18000726b  mov     edx, 10h; unsigned __int64
0x180007270  mov     [rsp+38h+Source], r8
0x180007275  mov     rcx, rbx; this
0x180007278  mov     [rsp+38h+var_10], r9
0x18000727d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007282  test    al, al
0x180007284  jz      short loc_1800072BF
0x180007286  mov     rcx, [rbx+8]; Destination
0x18000728a  lea     r8, [rsp+38h+Source]; Source
0x18000728f  mov     rax, [rbx+10h]
0x180007293  mov     r9d, 10h; SourceSize
0x180007299  sub     rax, rcx
0x18000729c  cmp     rcx, [rbx+10h]
0x1800072a0  sbb     rdx, rdx
0x1800072a3  and     rdx, rax; DestinationSize
0x1800072a6  call    cs:__imp_memcpy_s
0x1800072ac  add     qword ptr [rbx+8], 10h
0x1800072b1  mov     rax, [rbx+8]
0x1800072b5  sub     rax, [rbx]
0x1800072b8  shr     rax, 4
0x1800072bc  mov     [rdi], rax
0x1800072bf  mov     rbx, [rsp+38h+arg_0]
0x1800072c4  add     rsp, 30h
0x1800072c8  pop     rdi
0x1800072c9  retn
0x1800072ca  mov     [rcx+rax*8], r8
0x1800072ce  mov     [rcx+rax*8+8], r9
0x1800072d3  mov     [rdi], rdx
0x1800072d6  jmp     short loc_1800072BF
```
