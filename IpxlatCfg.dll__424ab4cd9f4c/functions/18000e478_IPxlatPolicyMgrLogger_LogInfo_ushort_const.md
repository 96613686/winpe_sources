# IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)

- ea: `0x18000e478`
- end: `0x18000e4ad`
- name: `?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ`
- size: `53`
- prototype: `void(IPxlatPolicyMgrLogger *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d4e0`
- `0x18000d550`
- `0x18000d75c`
- `0x18000da20`
- `0x18000dcc8`

## callees

- `0x18000e2f4`

## pseudocode

```c
void IPxlatPolicyMgrLogger::LogInfo(IPxlatPolicyMgrLogger *this, const unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, a2);
  IPxlatPolicyMgrLogger::Log((__int64)this, 0, 0, a2, va);
}

```

## disassembly

```asm
0x18000e478  mov     r11, rsp
0x18000e47b  mov     [r11+10h], rdx
0x18000e47f  mov     [r11+18h], r8
0x18000e483  mov     [r11+20h], r9
0x18000e487  sub     rsp, 48h
0x18000e48b  lea     rax, [r11+18h]
0x18000e48f  mov     qword ptr [r11-18h], 0
0x18000e497  mov     r9, rdx
0x18000e49a  mov     [r11-28h], rax
0x18000e49e  xor     edx, edx
0x18000e4a0  xor     r8d, r8d
0x18000e4a3  call    ?Log@IPxlatPolicyMgrLogger@@AEAAXW4_TRACE_LEVEL@1@IPEBGPEAD@Z; IPxlatPolicyMgrLogger::Log(IPxlatPolicyMgrLogger::_TRACE_LEVEL,uint,ushort const *,char *)
0x18000e4a8  add     rsp, 48h
0x18000e4ac  retn
```
