# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180006f40`
- end: `0x180006ff7`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `183`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d2c`
- `0x180006e2c`

## callees

- `0x180006f40`
- `0x180008360`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006fbe`
- `msvcrt!memcpy_s` at `0x180006fbe`

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
0x180006f40  mov     [rsp+arg_0], rbx
0x180006f45  push    rdi
0x180006f46  sub     rsp, 30h
0x180006f4a  lea     rbx, [rcx+28h]
0x180006f4e  mov     qword ptr [rdx], 0
0x180006f55  mov     rcx, [rbx]
0x180006f58  xor     eax, eax
0x180006f5a  mov     r10, [rbx+8]
0x180006f5e  mov     rdi, rdx
0x180006f61  sub     r10, rcx
0x180006f64  shr     r10, 4
0x180006f68  test    r10, r10
0x180006f6b  jz      short loc_180006F83
0x180006f6d  lea     rdx, [rax+1]
0x180006f71  add     rax, rax
0x180006f74  cmp     qword ptr [rcx+rax*8], 0
0x180006f79  jz      short loc_180006FE9
0x180006f7b  mov     rax, rdx
0x180006f7e  cmp     rdx, r10
0x180006f81  jb      short loc_180006F6D
0x180006f83  mov     edx, 10h; unsigned __int64
0x180006f88  mov     [rsp+38h+Source], r8
0x180006f8d  mov     rcx, rbx; this
0x180006f90  mov     [rsp+38h+var_10], r9
0x180006f95  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006f9a  test    al, al
0x180006f9c  jz      short loc_180006FDD
0x180006f9e  mov     rcx, [rbx+8]; Destination
0x180006fa2  lea     r8, [rsp+38h+Source]; Source
0x180006fa7  mov     rax, [rbx+10h]
0x180006fab  mov     r9d, 10h; SourceSize
0x180006fb1  sub     rax, rcx
0x180006fb4  cmp     rcx, [rbx+10h]
0x180006fb8  sbb     rdx, rdx
0x180006fbb  and     rdx, rax; DestinationSize
0x180006fbe  call    cs:__imp_memcpy_s
0x180006fc5  nop     dword ptr [rax+rax+00h]
0x180006fca  add     qword ptr [rbx+8], 10h
0x180006fcf  mov     rax, [rbx+8]
0x180006fd3  sub     rax, [rbx]
0x180006fd6  shr     rax, 4
0x180006fda  mov     [rdi], rax
0x180006fdd  mov     rbx, [rsp+38h+arg_0]
0x180006fe2  add     rsp, 30h
0x180006fe6  pop     rdi
0x180006fe7  retn
0x180006fe9  mov     [rcx+rax*8], r8
0x180006fed  mov     [rcx+rax*8+8], r9
0x180006ff2  mov     [rdi], rdx
0x180006ff5  jmp     short loc_180006FDD
```
