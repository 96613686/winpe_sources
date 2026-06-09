# DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)

- ea: `0x14000a278`
- end: `0x14000a295`
- name: `?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ`
- size: `29`
- prototype: `void(DiagHubCommon::LogStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001388`
- `0x140005120`
- `0x1400051d0`
- `0x140005400`
- `0x140005b70`
- `0x140006370`
- `0x140008a40`
- `0x14000f510`
- `0x14000f838`
- `0x14000f938`
- `0x140010a70`
- `0x140010d8c`
- `0x140010fc0`
- `0x140010ffc`
- `0x1400111ac`

## callees

- `0x140009f90`

## pseudocode

```c
void DiagHubCommon::LogStream::Write(
        DiagHubCommon::LogStream *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        ...)
{
  va_list va; // [rsp+48h] [rbp+20h] BYREF

  va_start(va, a3);
  DiagHubCommon::LogStream::Write(this, a2, a3, va);
}

```

## disassembly

```asm
0x14000a278  mov     [rsp+arg_10], r8
0x14000a27d  mov     qword ptr [rsp+arg_18], r9
0x14000a282  sub     rsp, 28h
0x14000a286  lea     r9, [rsp+28h+arg_18]; char *
0x14000a28b  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0PEAD@Z; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,char *)
0x14000a290  add     rsp, 28h
0x14000a294  retn
```
