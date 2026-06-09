# AppMon::MonitorInterface::AppMonReadPort(void *,uchar *,ulong,ulong *)

- ea: `0x1800071d0`
- end: `0x1800071da`
- name: `?AppMonReadPort@MonitorInterface@AppMon@@SAHPEAXPEAEKPEAK@Z`
- size: `10`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall AppMon::MonitorInterface::AppMonReadPort(
        void *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned int *a4)
{
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800071d0  mov     dword ptr [r9], 0
0x1800071d7  xor     eax, eax
0x1800071d9  retn
```
