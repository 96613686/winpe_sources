# ParallelTasks::GetLogicalCoreCount(void)

- ea: `0x1800a3a94`
- end: `0x1800a3ac7`
- name: `?GetLogicalCoreCount@ParallelTasks@@QEAAHXZ`
- size: `51`
- prototype: `__int64 __fastcall(ParallelTasks *__hidden this)`
- caller_count: `42`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180031bd0`
- `0x180031e18`
- `0x180032060`
- `0x1800322a8`
- `0x1800324f0`
- `0x180032738`
- `0x180032f34`
- `0x180077a44`
- `0x180077b20`
- `0x180080dd8`
- `0x180080f88`
- `0x18008113c`
- `0x180081bf8`
- `0x180082544`
- `0x1800826cc`
- `0x180084d3c`
- `0x1800857e4`
- `0x180089090`
- `0x18008ae34`
- `0x18008af20`
- `0x18008b00c`
- `0x18008b0f8`
- `0x18008b990`
- `0x18008ba44`
- `0x18008bd0c`
- `0x18008bec0`
- `0x18008c074`
- `0x18008c228`
- `0x18008c470`
- `0x18008c6b8`
- `0x18008c900`
- `0x18008da4c`
- `0x18008db20`
- `0x18008dbf4`
- `0x18008dcc8`
- `0x18008dd9c`
- `0x18008de70`
- `0x18008df44`
- `0x18008e018`
- `0x180090e9c`
- `0x18013b658`
- `0x18013b6fc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800a3aae`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800a3aae`

## pseudocode

```c
__int64 __fastcall ParallelTasks::GetLogicalCoreCount(ParallelTasks *this)
{
  __int64 result; // rax
  struct _SYSTEM_INFO v2; // [rsp+20h] [rbp-38h] BYREF

  memset(&v2, 0, sizeof(v2));
  GetNativeSystemInfo(&v2);
  result = 64;
  if ( (int)v2.dwNumberOfProcessors < 64 )
    return v2.dwNumberOfProcessors;
  return result;
}

```

## disassembly

```asm
0x1800a3a94  mov     rax, rsp
0x1800a3a97  sub     rsp, 58h
0x1800a3a9b  xorps   xmm0, xmm0
0x1800a3a9e  lea     rcx, [rax-38h]; lpSystemInfo
0x1800a3aa2  movups  xmmword ptr [rax-38h], xmm0
0x1800a3aa6  movups  xmmword ptr [rax-28h], xmm0
0x1800a3aaa  movups  xmmword ptr [rax-18h], xmm0
0x1800a3aae  call    cs:__imp_GetNativeSystemInfo
0x1800a3ab4  mov     eax, 40h ; '@'
0x1800a3ab9  cmp     [rsp+58h+var_18], eax
0x1800a3abd  cmovl   eax, [rsp+58h+var_18]
0x1800a3ac2  add     rsp, 58h
0x1800a3ac6  retn
```
