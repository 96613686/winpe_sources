# Broker::CKeepAliveEvent::CKeepAliveEvent(_SYSTEMTIME const &,ulong,ulong,_TbiTimeEventModsParameters const *,bool,bool,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800169bc`
- end: `0x180016b34`
- name: `??0CKeepAliveEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKPEBU_TbiTimeEventModsParameters@@_N2AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, __int64, __int64, unsigned __int8, char, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x180003800`
- `0x180003840`
- `0x180009fc0`
- `0x18000a330`
- `0x1800109bc`
- `0x1800169bc`

## pseudocode

```c
__int64 __fastcall Broker::CKeepAliveEvent::CKeepAliveEvent(
        __int64 a1,
        _OWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int8 a6,
        char a7,
        __int64 a8)
{
  Broker::TimeEvent *v10; // rcx
  __int64 v11; // rax
  int v13; // [rsp+30h] [rbp-18h]

  Broker::TimeEvent::TimeEvent((Broker::TimeEvent *)a1, a5, 5, v13, a8);
  *(_QWORD *)a1 = &Broker::CKeepAliveEvent::`vftable';
  *(_OWORD *)(a1 + 280) = *a2;
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(_WORD *)(a1 + 312) = 0;
  *(_BYTE *)(a1 + 314) = a6;
  *(_BYTE *)(a1 + 315) = a7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids);
  *(_BYTE *)(a1 + 314) = a6;
  v10 = (Broker::TimeEvent *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, a6);
      v10 = (Broker::TimeEvent *)WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)v10 + 25) >= 4u )
      {
        v11 = Broker::TimeEvent::DueDateToUtcDueTime(v10, (const struct _SYSTEMTIME *)(a1 + 280), 0);
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, v11);
        v10 = (Broker::TimeEvent *)WPP_GLOBAL_Control;
      }
      if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
        WPP_SF_(*((_QWORD *)v10 + 2), 13, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800169bc  mov     r11, rsp
0x1800169bf  mov     [r11+10h], rbx
0x1800169c3  mov     [r11+18h], rsi
0x1800169c7  mov     [r11+8], rcx
0x1800169cb  push    rdi
0x1800169cc  sub     rsp, 40h
0x1800169d0  mov     r10d, r9d
0x1800169d3  mov     rbx, rdx
0x1800169d6  mov     rdi, rcx
0x1800169d9  mov     eax, r8d
0x1800169dc  imul    r9, rax, 989680h
0x1800169e3  imul    r8, r10, 989680h
0x1800169ea  mov     rax, [rsp+48h+arg_38]
0x1800169f2  mov     [r11-10h], rax
0x1800169f6  mov     [rsp+48h+var_20], 5; int
0x1800169fe  mov     rax, [rsp+48h+arg_20]
0x180016a03  mov     [r11-28h], rax
0x180016a07  mov     rdx, 3FFFFFFFFFFFFFFFh
0x180016a11  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x180016a16  nop
0x180016a17  lea     rax, ??_7CKeepAliveEvent@Broker@@6B@; const Broker::CKeepAliveEvent::`vftable'
0x180016a1e  mov     [rdi], rax
0x180016a21  lea     rsi, [rdi+118h]
0x180016a28  movups  xmm0, xmmword ptr [rbx]
0x180016a2b  movdqu  xmmword ptr [rsi], xmm0
0x180016a2f  xor     eax, eax
0x180016a31  mov     [rdi+128h], rax
0x180016a38  mov     [rdi+130h], rax
0x180016a3f  mov     [rdi+138h], ax
0x180016a46  movzx   ebx, [rsp+48h+arg_28]
0x180016a4b  mov     [rdi+13Ah], bl
0x180016a51  mov     al, [rsp+48h+arg_30]
0x180016a58  mov     [rdi+13Bh], al
0x180016a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a65  test    byte ptr [rcx+1Ch], 1
0x180016a69  jz      short loc_180016A86
0x180016a6b  cmp     byte ptr [rcx+19h], 4
0x180016a6f  jb      short loc_180016A86
0x180016a71  mov     edx, 0Ah
0x180016a76  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016a7d  mov     rcx, [rcx+10h]
0x180016a81  call    WPP_SF_
0x180016a86  mov     [rdi+13Ah], bl
0x180016a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a93  test    byte ptr [rcx+1Ch], 1
0x180016a97  jz      loc_180016B21
0x180016a9d  cmp     byte ptr [rcx+19h], 4
0x180016aa1  jb      short loc_180016AC2
0x180016aa3  mov     r9d, ebx
0x180016aa6  mov     edx, 0Bh
0x180016aab  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016ab2  mov     rcx, [rcx+10h]
0x180016ab6  call    WPP_SF_d
0x180016abb  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180016ac2  test    byte ptr [rcx+1Ch], 1
0x180016ac6  jz      short loc_180016B21
0x180016ac8  cmp     byte ptr [rcx+19h], 4
0x180016acc  jb      short loc_180016AFF
0x180016ace  xor     r8d, r8d; bool
0x180016ad1  mov     rdx, rsi; struct _SYSTEMTIME *
0x180016ad4  call    ?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z; Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)
0x180016ad9  mov     edx, 0Ch
0x180016ade  mov     r9, rax
0x180016ae1  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aef  mov     rcx, [rcx+10h]
0x180016af3  call    WPP_SF_i
0x180016af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aff  test    byte ptr [rcx+1Ch], 1
0x180016b03  jz      short loc_180016B21
0x180016b05  cmp     byte ptr [rcx+19h], 4
0x180016b09  jb      short loc_180016B21
0x180016b0b  mov     edx, 0Dh
0x180016b10  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016b17  mov     rcx, [rcx+10h]
0x180016b1b  call    WPP_SF_
0x180016b20  nop
0x180016b21  mov     rax, rdi
0x180016b24  mov     rbx, [rsp+48h+arg_8]
0x180016b29  mov     rsi, [rsp+48h+arg_10]
0x180016b2e  add     rsp, 40h
0x180016b32  pop     rdi
0x180016b33  retn
```
