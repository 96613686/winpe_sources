# Concurrency::details::ThreadProxyFactory<Concurrency::details::FreeThreadProxy>::RequestProxy(uint,int)

- ea: `0x180320060`
- end: `0x180320111`
- name: `?RequestProxy@?$ThreadProxyFactory@VFreeThreadProxy@details@Concurrency@@@details@Concurrency@@UEAAPEAUIThreadProxy@3@IH@Z`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180320060`
- `0x180358070`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18032009f`
- `KERNEL32!InterlockedPopEntrySList` at `0x18032009f`

## pseudocode

```c
__int64 __fastcall Concurrency::details::ThreadProxyFactory<Concurrency::details::FreeThreadProxy>::RequestProxy(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  __int64 *v3; // rbp
  int v4; // esi
  PSLIST_ENTRY v8; // rax
  __int64 v9; // rbx

  v3 = Concurrency::details::ThreadProxyFactory<Concurrency::details::FreeThreadProxy>::s_proxyStackSize;
  v4 = 0;
  while ( 1 )
  {
    if ( a2 <= *(_DWORD *)v3 )
    {
      v8 = InterlockedPopEntrySList((PSLIST_HEADER)(a1 + 16 * (v4 + 1LL)));
      v9 = (unsigned __int64)&v8[-6] & -(__int64)(v8 != 0);
      if ( v9 )
        break;
    }
    ++v4;
    v3 = (__int64 *)((char *)v3 + 4);
    if ( v4 >= 4 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, a2);
      if ( !v9 )
        return v9;
      break;
    }
  }
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v9, a3);
  return v9;
}

```

## disassembly

```asm
0x180320060  mov     [rsp+arg_0], rbx
0x180320065  mov     [rsp+arg_8], rbp
0x18032006a  mov     [rsp+arg_10], rsi
0x18032006f  push    rdi
0x180320070  push    r14
0x180320072  push    r15
0x180320074  sub     rsp, 20h
0x180320078  xor     ebx, ebx
0x18032007a  lea     rbp, ?s_proxyStackSize@?$ThreadProxyFactory@VFreeThreadProxy@details@Concurrency@@@details@Concurrency@@1QBIB; uint const near * const Concurrency::details::ThreadProxyFactory<Concurrency::details::FreeThreadProxy>::s_proxyStackSize
0x180320081  xor     esi, esi
0x180320083  mov     r15d, r8d
0x180320086  mov     r14d, edx
0x180320089  mov     rdi, rcx
0x18032008c  cmp     r14d, [rbp+0]
0x180320090  ja      short loc_1803200B4
0x180320092  movsxd  rcx, esi
0x180320095  inc     rcx
0x180320098  shl     rcx, 4
0x18032009c  add     rcx, rdi; ListHead
0x18032009f  call    cs:__imp_InterlockedPopEntrySList
0x1803200a5  lea     rcx, [rax-60h]
0x1803200a9  neg     rax
0x1803200ac  sbb     rbx, rbx
0x1803200af  and     rbx, rcx
0x1803200b2  jnz     short loc_1803200DF
0x1803200b4  inc     esi
0x1803200b6  add     rbp, 4
0x1803200ba  cmp     esi, 4
0x1803200bd  jl      short loc_18032008C
0x1803200bf  test    rbx, rbx
0x1803200c2  jnz     short loc_1803200DF
0x1803200c4  mov     rax, [rdi]
0x1803200c7  mov     edx, r14d
0x1803200ca  mov     rcx, rdi
0x1803200cd  mov     rax, [rax+38h]
0x1803200d1  call    cs:__guard_dispatch_icall_fptr
0x1803200d7  mov     rbx, rax
0x1803200da  test    rax, rax
0x1803200dd  jz      short loc_1803200F5
0x1803200df  mov     rcx, [rdi]
0x1803200e2  mov     r8d, r15d
0x1803200e5  mov     rdx, rbx
0x1803200e8  mov     rax, [rcx+48h]
0x1803200ec  mov     rcx, rdi
0x1803200ef  call    cs:__guard_dispatch_icall_fptr
0x1803200f5  mov     rbp, [rsp+38h+arg_8]
0x1803200fa  mov     rax, rbx
0x1803200fd  mov     rbx, [rsp+38h+arg_0]
0x180320102  mov     rsi, [rsp+38h+arg_10]
0x180320107  add     rsp, 20h
0x18032010b  pop     r15
0x18032010d  pop     r14
0x18032010f  pop     rdi
0x180320110  retn
```
