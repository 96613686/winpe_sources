# IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)

- ea: `0x18000e43c`
- end: `0x18000e470`
- name: `?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ`
- size: `52`
- prototype: `void(IPxlatPolicyMgrLogger *this, int, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d550`
- `0x18000d75c`
- `0x18000da20`
- `0x18000dc28`
- `0x18000dcc8`
- `0x18000e180`

## callees

- `0x18000e2f4`

## pseudocode

```c
void IPxlatPolicyMgrLogger::LogError(IPxlatPolicyMgrLogger *this, int a2, const unsigned __int16 *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  IPxlatPolicyMgrLogger::Log((__int64)this, 1, a2, a3, va);
}

```

## disassembly

```asm
0x18000e43c  mov     r11, rsp
0x18000e43f  mov     [r11+18h], r8
0x18000e443  mov     [r11+20h], r9
0x18000e447  sub     rsp, 48h
0x18000e44b  mov     r9, r8
0x18000e44e  mov     qword ptr [r11-18h], 0
0x18000e456  mov     r8d, edx
0x18000e459  lea     rax, [r11+20h]
0x18000e45d  mov     edx, 1
0x18000e462  mov     [r11-28h], rax
0x18000e466  call    ?Log@IPxlatPolicyMgrLogger@@AEAAXW4_TRACE_LEVEL@1@IPEBGPEAD@Z; IPxlatPolicyMgrLogger::Log(IPxlatPolicyMgrLogger::_TRACE_LEVEL,uint,ushort const *,char *)
0x18000e46b  add     rsp, 48h
0x18000e46f  retn
```
