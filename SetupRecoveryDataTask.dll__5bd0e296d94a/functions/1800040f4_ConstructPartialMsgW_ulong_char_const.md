# ConstructPartialMsgW(ulong,char const *,...)

- ea: `0x1800040f4`
- end: `0x18000413a`
- name: `?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ`
- size: `70`
- prototype: `struct tagLOG_PARTIAL_MSG *(__int64, const char *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f60`
- `0x18000a210`
- `0x18000ca42`

## callees

- `0x18000c610`

## import_xrefs

- `WDSCORE!ConstructPartialMsgVW` at `0x180004122`
- `WDSCORE!ConstructPartialMsgVW` at `0x180004122`

## pseudocode

```c
struct tagLOG_PARTIAL_MSG *ConstructPartialMsgW(__int64 a1, const char *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  return (struct tagLOG_PARTIAL_MSG *)ConstructPartialMsgVW(a1, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x1800040f4  mov     r11, rsp
0x1800040f7  mov     [r11+10h], rdx
0x1800040fb  mov     [r11+18h], r8
0x1800040ff  mov     [r11+20h], r9
0x180004103  sub     rsp, 38h
0x180004107  mov     rax, cs:__security_cookie
0x18000410e  xor     rax, rsp
0x180004111  mov     [rsp+38h+var_10], rax
0x180004116  lea     r8, [r11+18h]
0x18000411a  mov     qword ptr [r11-18h], 0
0x180004122  call    cs:__imp_ConstructPartialMsgVW
0x180004128  mov     rcx, [rsp+38h+var_10]
0x18000412d  xor     rcx, rsp; StackCookie
0x180004130  call    __security_check_cookie
0x180004135  add     rsp, 38h
0x180004139  retn
```
