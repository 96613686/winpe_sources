# wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)

- ea: `0x140005128`
- end: `0x140005169`
- name: `?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ`
- size: `65`
- prototype: `__int64(wil::details::in1diag4 *this, void *, int, const char *, wil::details *, __int64, const char *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140005210`
- `0x140005590`
- `0x140006184`
- `0x14000628c`
- `0x140006428`
- `0x1400068c0`
- `0x1400070a0`
- `0x140007634`

## callees

- `0x140004ac0`

## pseudocode

```c
__int64 wil::details::in1diag4::Log_HrMsg(
        wil::details::in1diag4 *this,
        void *a2,
        int a3,
        const char *a4,
        wil::details *a5,
        __int64 a6,
        const char *a7,
        ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  wil::details *v9; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]

  LODWORD(v9) = (_DWORD)a5;
  wil::details::ReportFailure_HrMsg<2>((int)this, (int)a2, a3, (int)a4, v8, retaddr, v9, a6, (__int64)&a7);
  return (unsigned int)a5;
}

```

## disassembly

```asm
0x140005128  mov     r11, rsp
0x14000512b  push    rbx
0x14000512c  sub     rsp, 60h
0x140005130  mov     qword ptr [r11-18h], 0
0x140005138  lea     rax, [r11+38h]
0x14000513c  mov     r10, [rsp+68h]
0x140005141  mov     [r11-28h], rax
0x140005145  mov     rax, [r11+30h]
0x140005149  mov     [r11-30h], rax
0x14000514d  mov     ebx, dword ptr [rsp+68h+arg_20]
0x140005154  mov     dword ptr [rsp+68h+var_38], ebx; wil::details *
0x140005158  mov     [r11-40h], r10
0x14000515c  call    ??$ReportFailure_HrMsg@$01@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<2>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x140005161  mov     eax, ebx
0x140005163  add     rsp, 60h
0x140005167  pop     rbx
0x140005168  retn
```
