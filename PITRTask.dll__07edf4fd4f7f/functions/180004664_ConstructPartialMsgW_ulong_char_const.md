# ConstructPartialMsgW(ulong,char const *,...)

- ea: `0x180004664`
- end: `0x1800046aa`
- name: `?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ`
- size: `70`
- prototype: `struct tagLOG_PARTIAL_MSG *(__int64, const char *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a4f0`
- `0x18000da94`
- `0x18000df6c`
- `0x18000e16c`
- `0x18000f180`
- `0x18000f624`

## callees

- `0x1800107c0`

## import_xrefs

- `WDSCORE!ConstructPartialMsgVW` at `0x180004692`
- `WDSCORE!ConstructPartialMsgVW` at `0x180004692`

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
0x180004664  mov     r11, rsp
0x180004667  mov     [r11+10h], rdx
0x18000466b  mov     [r11+18h], r8
0x18000466f  mov     [r11+20h], r9
0x180004673  sub     rsp, 38h
0x180004677  mov     rax, cs:__security_cookie
0x18000467e  xor     rax, rsp
0x180004681  mov     [rsp+38h+var_10], rax
0x180004686  lea     r8, [r11+18h]
0x18000468a  mov     qword ptr [r11-18h], 0
0x180004692  call    cs:__imp_ConstructPartialMsgVW
0x180004698  mov     rcx, [rsp+38h+var_10]
0x18000469d  xor     rcx, rsp; StackCookie
0x1800046a0  call    __security_check_cookie
0x1800046a5  add     rsp, 38h
0x1800046a9  retn
```
