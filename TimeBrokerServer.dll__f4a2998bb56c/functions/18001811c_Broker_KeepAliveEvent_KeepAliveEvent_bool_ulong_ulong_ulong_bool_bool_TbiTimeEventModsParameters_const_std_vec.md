# Broker::KeepAliveEvent::KeepAliveEvent(bool,ulong,ulong,ulong,bool,bool,_TbiTimeEventModsParameters const *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18001811c`
- end: `0x1800181d2`
- name: `??0KeepAliveEvent@Broker@@QEAA@_NKKK00PEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `182`
- prototype: `Broker::TimeEvent *__fastcall(Broker::TimeEvent *this, char, unsigned int, unsigned int, int, char, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x18000cd58`
- `0x1800109bc`

## pseudocode

```c
Broker::TimeEvent *__fastcall Broker::KeepAliveEvent::KeepAliveEvent(
        Broker::TimeEvent *this,
        char a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        char a6,
        char a7,
        __int64 a8,
        __int64 a9)
{
  Broker::TimeEvent *result; // rax
  int v13; // [rsp+30h] [rbp-38h]

  Broker::KeepAliveEvent::GetEventWindow(a4, a3);
  Broker::TimeEvent::TimeEvent(this, a8, 3, v13, a9);
  *((_DWORD *)this + 70) = a3;
  *(_QWORD *)this = &Broker::KeepAliveEvent::`vftable';
  *((_BYTE *)this + 286) = a7;
  *((_BYTE *)this + 284) = 0;
  *((_BYTE *)this + 92) = a6 ^ 1;
  result = this;
  *((_BYTE *)this + 285) = a2;
  *((_BYTE *)this + 21) = 1;
  return result;
}

```

## disassembly

```asm
0x18001811c  push    rbx
0x18001811e  push    rsi
0x18001811f  push    rdi
0x180018120  push    r14
0x180018122  sub     rsp, 48h
0x180018126  mov     edi, r8d
0x180018129  mov     sil, dl
0x18001812c  mov     r14, rcx
0x18001812f  mov     edx, r8d; unsigned int
0x180018132  mov     ecx, r9d; unsigned int
0x180018135  imul    rbx, rdi, 989680h
0x18001813c  call    ?GetEventWindow@KeepAliveEvent@Broker@@CAKKK@Z; Broker::KeepAliveEvent::GetEventWindow(ulong,ulong)
0x180018141  mov     eax, eax
0x180018143  mov     r9, rbx
0x180018146  imul    r8, rax, 989680h
0x18001814d  mov     eax, [rsp+68h+arg_20]
0x180018154  mov     rcx, r14; this
0x180018157  imul    rdx, rax, 989680h
0x18001815e  mov     rax, [rsp+68h+arg_40]
0x180018166  mov     [rsp+68h+var_30], rax; __int64
0x18001816b  mov     rax, [rsp+68h+arg_38]
0x180018173  mov     [rsp+68h+var_40], 3; int
0x18001817b  mov     [rsp+68h+var_48], rax; __int64
0x180018180  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x180018185  lea     rax, ??_7KeepAliveEvent@Broker@@6B@; const Broker::KeepAliveEvent::`vftable'
0x18001818c  mov     [r14+118h], edi
0x180018193  mov     [r14], rax
0x180018196  mov     al, [rsp+68h+arg_30]
0x18001819d  mov     [r14+11Eh], al
0x1800181a4  mov     al, [rsp+68h+arg_28]
0x1800181ab  xor     al, 1
0x1800181ad  mov     byte ptr [r14+11Ch], 0
0x1800181b5  mov     [r14+5Ch], al
0x1800181b9  mov     rax, r14
0x1800181bc  mov     [r14+11Dh], sil
0x1800181c3  mov     byte ptr [r14+15h], 1
0x1800181c8  add     rsp, 48h
0x1800181cc  pop     r14
0x1800181ce  pop     rdi
0x1800181cf  pop     rsi
0x1800181d0  pop     rbx
0x1800181d1  retn
```
