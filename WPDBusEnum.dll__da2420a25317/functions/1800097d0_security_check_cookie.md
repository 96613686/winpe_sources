# __security_check_cookie

- ea: `0x1800097d0`
- end: `0x1800097ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001210`
- `0x1800018c0`
- `0x1800022c0`
- `0x1800027c0`
- `0x180002c70`
- `0x180002fa0`
- `0x180004050`
- `0x180004390`
- `0x180004f10`
- `0x180005420`
- `0x1800067c0`
- `0x1800069d0`
- `0x18000704c`
- `0x180007880`
- `0x180007f68`
- `0x180008128`
- `0x18000b2fc`
- `0x18000b3f0`
- `0x18000b998`
- `0x18000bb60`
- `0x18000bf54`
- `0x18000c280`
- `0x18000d4b8`
- `0x18000daa0`
- `0x18000dc3c`
- `0x18000de4c`
- `0x18000e5d0`
- `0x18000eda4`
- `0x18000f390`
- `0x18000fd14`
- `0x1800101cc`
- `0x180010464`
- `0x1800106e0`
- `0x180010bc0`
- `0x180010d74`
- `0x180010f60`
- `0x180011008`
- `0x1800114a4`
- `0x180012058`
- `0x1800124c0`
- `0x1800127ec`
- `0x180013038`
- `0x18001396c`
- `0x18001425c`
- `0x1800153ac`

## callees

- `0x1800097d0`
- `0x180009bd0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x1800097d0  cmp     rcx, cs:__security_cookie
0x1800097d7  jnz     short ReportFailure
0x1800097d9  rol     rcx, 10h
0x1800097dd  test    cx, 0FFFFh
0x1800097e2  jnz     short RestoreRcx
0x1800097e4  retn
0x1800097e5  ror     rcx, 10h; StackCookie
0x1800097e9  jmp     __report_gsfailure
```
