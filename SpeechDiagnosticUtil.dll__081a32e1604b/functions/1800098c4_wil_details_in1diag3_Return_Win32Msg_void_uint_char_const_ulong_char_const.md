# wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)

- ea: `0x1800098c4`
- end: `0x1800098fc`
- name: `?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ`
- size: `56`
- prototype: `__int64(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int, const char *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800084a0`
- `0x180008948`
- `0x180008a9c`
- `0x1800095fc`

## callees

- `0x180007378`

## pseudocode

```c
__int64 wil::details::in1diag3::Return_Win32Msg(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        __int64 a5,
        const char *a6,
        ...)
{
  int v7; // [rsp+20h] [rbp-48h]
  wil::details *v8; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]

  LODWORD(v8) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32Msg<1>((int)this, (int)a2, a3, (int)a4, v7, retaddr, v8, a5, (va_list)&a6);
}

```

## disassembly

```asm
0x1800098c4  mov     r11, rsp
0x1800098c7  sub     rsp, 68h
0x1800098cb  mov     qword ptr [r11-18h], 0
0x1800098d3  lea     rax, [r11+30h]
0x1800098d7  mov     r10, [rsp+68h]
0x1800098dc  mov     [r11-28h], rax
0x1800098e0  mov     rax, [r11+28h]
0x1800098e4  mov     [r11-30h], rax
0x1800098e8  mov     [r11-38h], r9d
0x1800098ec  mov     [r11-40h], r10
0x1800098f0  call    ??$ReportFailure_Win32Msg@$00@details@wil@@YAJPEAXIPEBD110K1PEAD@Z; wil::details::ReportFailure_Win32Msg<1>(void *,uint,char const *,char const *,char const *,void *,ulong,char const *,char *)
0x1800098f5  nop
0x1800098f6  add     rsp, 68h
0x1800098fa  retn
```
