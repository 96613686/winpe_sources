# Logger::TraceCritical(ushort const *,...)

- ea: `0x180019bd8`
- end: `0x180019c0d`
- name: `?TraceCritical@Logger@@SAJPEBGZZ`
- size: `53`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ef0`
- `0x18000ad2c`
- `0x180019024`
- `0x1800191fc`
- `0x180019618`
- `0x1800197a0`
- `0x18001995c`
- `0x180019e18`

## callees

- `0x180009424`

## pseudocode

```c
__int64 Logger::TraceCritical(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(4, a1, (__int64 *)va);
}

```

## disassembly

```asm
0x180019bd8  mov     rax, rsp
0x180019bdb  mov     [rax+8], rcx
0x180019bdf  mov     [rax+10h], rdx
0x180019be3  mov     [rax+18h], r8
0x180019be7  mov     [rax+20h], r9
0x180019beb  sub     rsp, 38h
0x180019bef  mov     rdx, rcx
0x180019bf2  mov     qword ptr [rax-18h], 0
0x180019bfa  mov     ecx, 4
0x180019bff  lea     r8, [rax+10h]
0x180019c03  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x180019c08  add     rsp, 38h
0x180019c0c  retn
```
