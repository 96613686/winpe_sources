# Broker::ConvenientTimeEvent::ConvenientTimeEvent(_SYSTEMTIME const &,ulong,ulong,ulong,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18000a9e4`
- end: `0x18000aa7f`
- name: `??0ConvenientTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKKAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `155`
- prototype: `Broker::TimeEvent *__fastcall(Broker::TimeEvent *this, __int128 *, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x1800109bc`

## pseudocode

```c
Broker::TimeEvent *__fastcall Broker::ConvenientTimeEvent::ConvenientTimeEvent(
        Broker::TimeEvent *this,
        __int128 *a2,
        int a3,
        int a4,
        int a5,
        __int64 a6)
{
  __int128 v10; // xmm0
  Broker::TimeEvent *result; // rax
  int v12; // [rsp+30h] [rbp-38h]

  Broker::TimeEvent::TimeEvent(this, 0, 2, v12, a6);
  *(_QWORD *)this = &Broker::ConvenientTimeEvent::`vftable';
  v10 = *a2;
  *((_DWORD *)this + 76) = a5;
  result = this;
  *(_OWORD *)((char *)this + 280) = v10;
  *((_DWORD *)this + 74) = a3;
  *((_DWORD *)this + 75) = a4;
  return result;
}

```

## disassembly

```asm
0x18000a9e4  push    rbx
0x18000a9e6  push    rsi
0x18000a9e7  push    rdi
0x18000a9e8  push    r14
0x18000a9ea  sub     rsp, 48h
0x18000a9ee  mov     esi, r9d
0x18000a9f1  mov     edi, r8d
0x18000a9f4  mov     r14, rcx
0x18000a9f7  mov     eax, esi
0x18000a9f9  mov     ecx, 0Fh
0x18000a9fe  mov     rbx, rdx
0x18000aa01  imul    r9, rdi, 23C34600h
0x18000aa08  cmp     esi, ecx
0x18000aa0a  mov     r8d, 989680h
0x18000aa10  cmovbe  eax, ecx
0x18000aa13  mov     rcx, r14; this
0x18000aa16  imul    rdx, rax, 23C34600h
0x18000aa1d  mov     rax, [rsp+68h+arg_28]
0x18000aa25  mov     [rsp+68h+var_30], rax; __int64
0x18000aa2a  mov     [rsp+68h+var_40], 2; int
0x18000aa32  mov     [rsp+68h+var_48], 0; __int64
0x18000aa3b  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x18000aa40  lea     rax, ??_7ConvenientTimeEvent@Broker@@6B@; const Broker::ConvenientTimeEvent::`vftable'
0x18000aa47  mov     [r14], rax
0x18000aa4a  movups  xmm0, xmmword ptr [rbx]
0x18000aa4d  mov     eax, [rsp+68h+arg_20]
0x18000aa54  mov     [r14+130h], eax
0x18000aa5b  mov     rax, r14
0x18000aa5e  movdqu  xmmword ptr [r14+118h], xmm0
0x18000aa67  mov     [r14+128h], edi
0x18000aa6e  mov     [r14+12Ch], esi
0x18000aa75  add     rsp, 48h
0x18000aa79  pop     r14
0x18000aa7b  pop     rdi
0x18000aa7c  pop     rsi
0x18000aa7d  pop     rbx
0x18000aa7e  retn
```
