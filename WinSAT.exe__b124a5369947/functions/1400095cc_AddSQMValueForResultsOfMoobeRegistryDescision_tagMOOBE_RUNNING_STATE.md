# AddSQMValueForResultsOfMoobeRegistryDescision(tagMOOBE_RUNNING_STATE)

- ea: `0x1400095cc`
- end: `0x14000963e`
- name: `?AddSQMValueForResultsOfMoobeRegistryDescision@@YAXW4tagMOOBE_RUNNING_STATE@@@Z`
- size: `114`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x14001a54c`

## callees

- `0x140113220`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140009626`
- `KERNEL32!WriteFile` at `0x140009626`
- `KERNEL32!GetStdHandle` at `0x140009604`
- `KERNEL32!GetStdHandle` at `0x140009604`

## pseudocode

```c
BOOL AddSQMValueForResultsOfMoobeRegistryDescision()
{
  HANDLE StdHandle; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF
  char Buffer[32]; // [rsp+38h] [rbp-30h] BYREF

  NumberOfBytesWritten = 0;
  strcpy(Buffer, "ERROR: Run of moobe skipped\r\n");
  StdHandle = GetStdHandle(0xFFFFFFF4);
  return WriteFile(StdHandle, Buffer, 0x1Eu, &NumberOfBytesWritten, 0);
}

```

## disassembly

```asm
0x1400095cc  sub     rsp, 68h
0x1400095d0  mov     rax, cs:__security_cookie
0x1400095d7  xor     rax, rsp
0x1400095da  mov     [rsp+68h+var_10], rax
0x1400095df  movups  xmm0, xmmword ptr cs:aErrorRunOfMoob; "ERROR: Run of moobe skipped\r\n"
0x1400095e6  mov     ecx, 0FFFFFFF4h; nStdHandle
0x1400095eb  mov     [rsp+68h+NumberOfBytesWritten], 0
0x1400095f3  movups  xmm1, xmmword ptr cs:aErrorRunOfMoob+0Eh; "moobe skipped\r\n"
0x1400095fa  movups  xmmword ptr [rsp+68h+Buffer], xmm0
0x1400095ff  movups  xmmword ptr [rsp+68h+Buffer+0Eh], xmm1
0x140009604  call    cs:__imp_GetStdHandle
0x14000960a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000960f  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x140009618  mov     rcx, rax; hFile
0x14000961b  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x140009620  mov     r8d, 1Eh; nNumberOfBytesToWrite
0x140009626  call    cs:__imp_WriteFile
0x14000962c  mov     rcx, [rsp+68h+var_10]
0x140009631  xor     rcx, rsp; StackCookie
0x140009634  call    __security_check_cookie
0x140009639  add     rsp, 68h
0x14000963d  retn
```
