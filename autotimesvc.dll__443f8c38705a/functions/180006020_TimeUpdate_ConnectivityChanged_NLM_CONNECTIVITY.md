# TimeUpdate::ConnectivityChanged(NLM_CONNECTIVITY)

- ea: `0x180006020`
- end: `0x180006033`
- name: `?ConnectivityChanged@TimeUpdate@@EEAAJW4NLM_CONNECTIVITY@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, enum NLM_CONNECTIVITY)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005f40`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ConnectivityChanged(struct _RTL_CRITICAL_SECTION *this, enum NLM_CONNECTIVITY a2)
{
  TimeUpdate::ConnectivityChanged(this, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x180006020  sub     rsp, 28h
0x180006024  xor     r8d, r8d; bool
0x180006027  call    ?ConnectivityChanged@TimeUpdate@@AEAAXW4NLM_CONNECTIVITY@@_N@Z; TimeUpdate::ConnectivityChanged(NLM_CONNECTIVITY,bool)
0x18000602c  xor     eax, eax
0x18000602e  add     rsp, 28h
0x180006032  retn
```
