# Broker::ApplicationStateTable::State::State(Broker::ApplicationIdentity const &,std::vector<ulong,std::allocator<ulong>> const &)

- ea: `0x180013018`
- end: `0x1800130ac`
- name: `??0State@ApplicationStateTable@Broker@@QEAA@AEBUApplicationIdentity@2@AEBV?$vector@KV?$allocator@K@std@@@std@@@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007be0`

## callees

- `0x18000800c`
- `0x18000ba30`
- `0x180013018`
- `0x1800130b4`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180013097`
- `ntdll!RtlInitializeSRWLock` at `0x180013097`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Broker::ApplicationStateTable::State::State(
        __int64 a1,
        const struct Broker::ApplicationIdentity *a2,
        _QWORD *a3)
{
  __int64 v5; // rdx
  int v7; // [rsp+40h] [rbp+18h] BYREF

  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)a1, a2);
  std::vector<unsigned long>::vector<unsigned long>(a1 + 88, a3);
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  v7 = 0;
  v5 = (__int64)(a3[1] - *a3) >> 2;
  if ( v5 )
    std::vector<unsigned long>::_Resize_reallocate<unsigned long>(a1 + 112, v5, &v7);
  *(_WORD *)(a1 + 136) = 256;
  *(_DWORD *)(a1 + 140) = 0;
  RtlInitializeSRWLock(a1 + 144);
  return a1;
}

```

## disassembly

```asm
0x180013018  mov     [rsp+arg_8], rbx
0x18001301d  mov     [rsp+arg_0], rcx
0x180013022  push    rdi
0x180013023  sub     rsp, 20h
0x180013027  mov     rbx, r8
0x18001302a  mov     rdi, rcx
0x18001302d  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x180013032  nop
0x180013033  lea     rcx, [rdi+58h]
0x180013037  mov     rdx, rbx
0x18001303a  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@AEBV01@@Z; std::vector<ulong>::vector<ulong>(std::vector<ulong> const &)
0x18001303f  nop
0x180013040  lea     rcx, [rdi+70h]
0x180013044  mov     qword ptr [rcx], 0
0x18001304b  mov     qword ptr [rcx+8], 0
0x180013053  mov     qword ptr [rcx+10h], 0
0x18001305b  mov     [rsp+28h+arg_10], 0
0x180013063  mov     rdx, [rbx+8]
0x180013067  sub     rdx, [rbx]
0x18001306a  sar     rdx, 2
0x18001306e  test    rdx, rdx
0x180013071  jz      short loc_18001307D
0x180013073  lea     r8, [rsp+28h+arg_10]
0x180013078  call    ??$_Resize_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBK@Z; std::vector<ulong>::_Resize_reallocate<ulong>(unsigned __int64,ulong const &)
0x18001307d  mov     word ptr [rdi+88h], 100h
0x180013086  mov     dword ptr [rdi+8Ch], 0
0x180013090  lea     rcx, [rdi+90h]
0x180013097  call    cs:__imp_RtlInitializeSRWLock
0x18001309d  nop
0x18001309e  mov     rax, rdi
0x1800130a1  mov     rbx, [rsp+28h+arg_8]
0x1800130a6  add     rsp, 20h
0x1800130aa  pop     rdi
0x1800130ab  retn
```
