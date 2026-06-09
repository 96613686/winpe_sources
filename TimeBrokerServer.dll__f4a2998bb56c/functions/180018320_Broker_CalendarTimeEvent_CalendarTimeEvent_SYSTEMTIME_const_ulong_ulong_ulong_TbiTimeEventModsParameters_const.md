# Broker::CalendarTimeEvent::CalendarTimeEvent(_SYSTEMTIME const &,ulong,ulong,ulong,_TbiTimeEventModsParameters const *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180018320`
- end: `0x1800183b2`
- name: `??0CalendarTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKKPEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int128 *, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x1800109bc`

## pseudocode

```c
__int64 __fastcall Broker::CalendarTimeEvent::CalendarTimeEvent(
        __int64 a1,
        __int128 *a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 result; // rax
  __int128 v11; // xmm0
  int v12; // [rsp+30h] [rbp-18h]

  Broker::TimeEvent::TimeEvent((Broker::TimeEvent *)a1, a6, 1, v12, a7);
  *(_QWORD *)a1 = &Broker::CalendarTimeEvent::`vftable';
  result = a1;
  v11 = *a2;
  *(_DWORD *)(a1 + 296) = a3;
  *(_OWORD *)(a1 + 280) = v11;
  return result;
}

```

## disassembly

```asm
0x180018320  mov     r11, rsp
0x180018323  mov     [r11+8], rbx
0x180018327  mov     [r11+10h], rsi
0x18001832b  push    rdi
0x18001832c  sub     rsp, 40h
0x180018330  mov     r10d, r8d
0x180018333  mov     rax, 0C92A69C000h
0x18001833d  imul    r10, rax
0x180018341  mov     eax, r9d
0x180018344  mov     rbx, rdx
0x180018347  mov     esi, r8d
0x18001834a  mov     r9, r10
0x18001834d  imul    r8, rax, 989680h
0x180018354  mov     eax, [rsp+48h+arg_20]
0x180018358  mov     rdi, rcx
0x18001835b  imul    rdx, rax, 23C34600h
0x180018362  mov     rax, [rsp+48h+arg_30]
0x18001836a  mov     [r11-10h], rax
0x18001836e  mov     rax, [rsp+48h+arg_28]
0x180018373  mov     [rsp+48h+var_20], 1; int
0x18001837b  mov     [r11-28h], rax
0x18001837f  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x180018384  lea     rax, ??_7CalendarTimeEvent@Broker@@6B@; const Broker::CalendarTimeEvent::`vftable'
0x18001838b  mov     [rdi], rax
0x18001838e  mov     rax, rdi
0x180018391  movups  xmm0, xmmword ptr [rbx]
0x180018394  mov     rbx, [rsp+48h+arg_0]
0x180018399  mov     [rdi+128h], esi
0x18001839f  mov     rsi, [rsp+48h+arg_8]
0x1800183a4  movdqu  xmmword ptr [rdi+118h], xmm0
0x1800183ac  add     rsp, 40h
0x1800183b0  pop     rdi
0x1800183b1  retn
```
