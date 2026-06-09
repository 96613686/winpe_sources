# AllocateTestMemory(unsigned __int64)

- ea: `0x18000eddc`
- end: `0x18000ee0a`
- name: `?AllocateTestMemory@@YAPEAX_K@Z`
- size: `46`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002974`
- `0x180004864`
- `0x18000a060`
- `0x18000c7a8`
- `0x18000c854`
- `0x18000c914`
- `0x18000c990`
- `0x18000ca40`
- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000e594`
- `0x18000e6a8`
- `0x18000ea24`
- `0x18000eb74`

## callees

- `0x18000257c`
- `0x18000eddc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ede0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ede0`

## pseudocode

```c
LPVOID __fastcall AllocateTestMemory(SIZE_T a1)
{
  LPVOID result; // rax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  result = CoTaskMemAlloc(a1);
  if ( !result )
  {
    pExceptionObject = 0;
    throw (TestException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000eddc  sub     rsp, 28h
0x18000ede0  call    cs:__imp_CoTaskMemAlloc
0x18000ede6  test    rax, rax
0x18000ede9  jz      short loc_18000EDF0
0x18000edeb  add     rsp, 28h
0x18000edef  retn
0x18000edf0  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000edf7  mov     [rsp+28h+pExceptionObject], 0
0x18000edff  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000ee04  call    _CxxThrowException_0
```
