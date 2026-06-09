# Broker::AlarmTimeEvent::AlarmTimeEvent(_SYSTEMTIME const &,bool,ulong,_TB_IRREGULAR_SCHEDULE,ulong,ulong,_TbiTimeEventModsParameters const *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180018b0c`
- end: `0x180018bb1`
- name: `??0AlarmTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@_NKU_TB_IRREGULAR_SCHEDULE@@KKPEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int128 *, char, int, _OWORD *, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x1800109bc`

## pseudocode

```c
__int64 __fastcall Broker::AlarmTimeEvent::AlarmTimeEvent(
        __int64 a1,
        __int128 *a2,
        char a3,
        int a4,
        _OWORD *a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  __int128 v13; // xmm0
  __int64 result; // rax
  int v15; // [rsp+30h] [rbp-38h]

  Broker::TimeEvent::TimeEvent((Broker::TimeEvent *)a1, a8, 0, v15, a9);
  *(_QWORD *)a1 = &Broker::AlarmTimeEvent::`vftable';
  v13 = *a2;
  *(_DWORD *)(a1 + 296) = a4;
  *(_OWORD *)(a1 + 280) = v13;
  *(_BYTE *)(a1 + 300) = a3;
  result = a1;
  *(_OWORD *)(a1 + 304) = *a5;
  return result;
}

```

## disassembly

```asm
0x180018b0c  push    rbx
0x180018b0e  push    rsi
0x180018b0f  push    rdi
0x180018b10  push    r14
0x180018b12  sub     rsp, 48h
0x180018b16  mov     eax, [rsp+68h+arg_28]
0x180018b1d  mov     sil, r8b
0x180018b20  imul    r8, rax, 989680h
0x180018b27  mov     eax, [rsp+68h+arg_30]
0x180018b2e  mov     rbx, rdx
0x180018b31  imul    rdx, rax, 23C34600h
0x180018b38  mov     rax, [rsp+68h+arg_40]
0x180018b40  mov     r14, rcx
0x180018b43  mov     [rsp+68h+var_30], rax; __int64
0x180018b48  mov     rax, [rsp+68h+arg_38]
0x180018b50  mov     edi, r9d
0x180018b53  imul    r9, rdi, 989680h
0x180018b5a  mov     [rsp+68h+var_40], 0; int
0x180018b62  mov     [rsp+68h+var_48], rax; __int64
0x180018b67  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x180018b6c  lea     rax, ??_7AlarmTimeEvent@Broker@@6B@; const Broker::AlarmTimeEvent::`vftable'
0x180018b73  mov     [r14], rax
0x180018b76  movups  xmm0, xmmword ptr [rbx]
0x180018b79  mov     rax, [rsp+68h+arg_20]
0x180018b81  mov     [r14+128h], edi
0x180018b88  movdqu  xmmword ptr [r14+118h], xmm0
0x180018b91  mov     [r14+12Ch], sil
0x180018b98  movaps  xmm0, xmmword ptr [rax]
0x180018b9b  mov     rax, r14
0x180018b9e  movdqu  xmmword ptr [r14+130h], xmm0
0x180018ba7  add     rsp, 48h
0x180018bab  pop     r14
0x180018bad  pop     rdi
0x180018bae  pop     rsi
0x180018baf  pop     rbx
0x180018bb0  retn
```
