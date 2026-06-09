# File::Write(void *,ulong)

- ea: `0x180002a88`
- end: `0x180002b0e`
- name: `?Write@File@@QEAAJPEAXK@Z`
- size: `134`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, void *, DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800019d4`
- `0x180001cdc`
- `0x18000228c`
- `0x180002474`

## callees

- `0x180002a88`
- `0x1800044f4`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180002ab4`
- `KERNEL32!WriteFile` at `0x180002ab4`
- `KERNEL32!GetLastError` at `0x180002abe`
- `KERNEL32!GetLastError` at `0x180002abe`

## pseudocode

```c
__int64 __fastcall File::Write(const unsigned __int16 **this, void *a2, DWORD a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  if ( WriteFile((HANDLE)*this, a2, a3, &v8, 0) )
  {
    v6 = 0;
    if ( v8 != a3 )
    {
      v6 = -2147023900;
LABEL_8:
      LogFileError(&WofTaskFileWriteErrorEventId, this[1], 0, v6);
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_8;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002a88  mov     rax, rsp
0x180002a8b  mov     [rax+10h], rbx
0x180002a8f  mov     [rax+18h], rsi
0x180002a93  push    rdi
0x180002a94  sub     rsp, 30h
0x180002a98  mov     rsi, rcx
0x180002a9b  mov     dword ptr [rax+8], 0
0x180002aa2  mov     rcx, [rcx]; hFile
0x180002aa5  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x180002aa9  mov     edi, r8d
0x180002aac  mov     qword ptr [rax-18h], 0
0x180002ab4  call    cs:__imp_WriteFile
0x180002aba  test    eax, eax
0x180002abc  jnz     short loc_180002AD9
0x180002abe  call    cs:__imp_GetLastError
0x180002ac4  mov     ebx, eax
0x180002ac6  test    eax, eax
0x180002ac8  jle     short loc_180002AD3
0x180002aca  movzx   ebx, ax
0x180002acd  or      ebx, 80070000h
0x180002ad3  test    ebx, ebx
0x180002ad5  jns     short loc_180002AFC
0x180002ad7  jmp     short loc_180002AE6
0x180002ad9  xor     ebx, ebx
0x180002adb  cmp     [rsp+38h+arg_0], edi
0x180002adf  jz      short loc_180002AFC
0x180002ae1  mov     ebx, 800703E4h
0x180002ae6  mov     rdx, [rsi+8]; unsigned __int16 *
0x180002aea  lea     rcx, WofTaskFileWriteErrorEventId; EventDescriptor
0x180002af1  mov     r9d, ebx; int
0x180002af4  xor     r8d, r8d; unsigned __int16 *
0x180002af7  call    ?LogFileError@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1H@Z; LogFileError(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,int)
0x180002afc  mov     rsi, [rsp+38h+arg_10]
0x180002b01  mov     eax, ebx
0x180002b03  mov     rbx, [rsp+38h+arg_8]
0x180002b08  add     rsp, 30h
0x180002b0c  pop     rdi
0x180002b0d  retn
```
