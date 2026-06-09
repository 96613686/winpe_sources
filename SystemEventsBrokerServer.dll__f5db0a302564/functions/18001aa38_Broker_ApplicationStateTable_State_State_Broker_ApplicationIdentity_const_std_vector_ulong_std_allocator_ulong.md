# Broker::ApplicationStateTable::State::State(Broker::ApplicationIdentity const &,std::vector<ulong,std::allocator<ulong>> const &)

- ea: `0x18001aa38`
- end: `0x18001ab03`
- name: `??0State@ApplicationStateTable@Broker@@QEAA@AEBUApplicationIdentity@2@AEBV?$vector@KV?$allocator@K@std@@@std@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, const struct Broker::ApplicationIdentity *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007880`

## callees

- `0x180001e40`
- `0x18000b168`
- `0x18001aa38`
- `0x18002156c`
- `0x18002163c`
- `0x180021690`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18001aae9`
- `ntdll!RtlInitializeSRWLock` at `0x18001aae9`

## pseudocode

```c
__int64 __fastcall Broker::ApplicationStateTable::State::State(
        __int64 a1,
        const struct Broker::ApplicationIdentity *a2,
        _QWORD *a3)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  __int64 v8; // rax
  int v10; // [rsp+40h] [rbp+18h] BYREF

  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)a1, a2);
  std::vector<unsigned long>::vector<unsigned long>(a1 + 88, a3);
  std::vector<_GUID>::vector<_GUID>((_QWORD *)(a1 + 112));
  v10 = 0;
  v5 = (__int64)(a3[1] - *a3) >> 2;
  v6 = *(_QWORD *)(a1 + 112);
  v7 = (*(_QWORD *)(a1 + 120) - v6) >> 2;
  if ( v5 < v7 )
  {
    v8 = v6 + 4 * v5;
LABEL_7:
    *(_QWORD *)(a1 + 120) = v8;
    goto LABEL_8;
  }
  if ( v5 > v7 )
  {
    if ( v5 <= (*(_QWORD *)(a1 + 128) - v6) >> 2 )
    {
      v8 = std::_Uninitialized_fill_n<std::allocator<unsigned long>>(*(_QWORD *)(a1 + 120), v5 - v7, &v10);
      goto LABEL_7;
    }
    std::vector<unsigned long>::_Resize_reallocate<unsigned long>(a1 + 112, v5, &v10);
  }
LABEL_8:
  *(_WORD *)(a1 + 136) = 256;
  *(_DWORD *)(a1 + 140) = 0;
  RtlInitializeSRWLock(a1 + 144);
  return a1;
}

```

## disassembly

```asm
0x18001aa38  mov     [rsp+arg_8], rbx
0x18001aa3d  mov     [rsp+arg_18], rsi
0x18001aa42  mov     [rsp+arg_0], rcx
0x18001aa47  push    rdi
0x18001aa48  sub     rsp, 20h
0x18001aa4c  mov     rbx, r8
0x18001aa4f  mov     rdi, rcx
0x18001aa52  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x18001aa57  nop
0x18001aa58  lea     rcx, [rdi+58h]
0x18001aa5c  mov     rdx, rbx
0x18001aa5f  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@AEBV01@@Z; std::vector<ulong>::vector<ulong>(std::vector<ulong> const &)
0x18001aa64  nop
0x18001aa65  lea     rsi, [rdi+70h]
0x18001aa69  mov     rcx, rsi
0x18001aa6c  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001aa71  nop
0x18001aa72  mov     [rsp+28h+arg_10], 0
0x18001aa7a  mov     rdx, [rbx+8]
0x18001aa7e  sub     rdx, [rbx]
0x18001aa81  sar     rdx, 2
0x18001aa85  mov     r8, [rsi]
0x18001aa88  mov     rcx, [rsi+8]
0x18001aa8c  sub     rcx, r8
0x18001aa8f  sar     rcx, 2
0x18001aa93  cmp     rdx, rcx
0x18001aa96  jnb     short loc_18001AA9E
0x18001aa98  lea     rax, [r8+rdx*4]
0x18001aa9c  jmp     short loc_18001AACB
0x18001aa9e  jbe     short loc_18001AACF
0x18001aaa0  mov     rax, [rsi+10h]
0x18001aaa4  sub     rax, r8
0x18001aaa7  sar     rax, 2
0x18001aaab  lea     r8, [rsp+28h+arg_10]
0x18001aab0  cmp     rdx, rax
0x18001aab3  jbe     short loc_18001AABF
0x18001aab5  mov     rcx, rsi
0x18001aab8  call    ??$_Resize_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBK@Z; std::vector<ulong>::_Resize_reallocate<ulong>(unsigned __int64,ulong const &)
0x18001aabd  jmp     short loc_18001AACF
0x18001aabf  sub     rdx, rcx
0x18001aac2  mov     rcx, [rsi+8]
0x18001aac6  call    ??$_Uninitialized_fill_n@V?$allocator@K@std@@@std@@YAPEAKPEAK_KAEBKAEAV?$allocator@K@0@@Z; std::_Uninitialized_fill_n<std::allocator<ulong>>(ulong *,unsigned __int64,ulong const &,std::allocator<ulong> &)
0x18001aacb  mov     [rsi+8], rax
0x18001aacf  mov     word ptr [rdi+88h], 100h
0x18001aad8  mov     dword ptr [rdi+8Ch], 0
0x18001aae2  lea     rcx, [rdi+90h]
0x18001aae9  call    cs:__imp_RtlInitializeSRWLock
0x18001aaef  nop
0x18001aaf0  mov     rax, rdi
0x18001aaf3  mov     rbx, [rsp+28h+arg_8]
0x18001aaf8  mov     rsi, [rsp+28h+arg_18]
0x18001aafd  add     rsp, 20h
0x18001ab01  pop     rdi
0x18001ab02  retn
```
