# File::Read(void *,ulong,ulong *)

- ea: `0x1800029fc`
- end: `0x180002a7f`
- name: `?Read@File@@QEAAJPEAXKPEAK@Z`
- size: `131`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, void *, DWORD, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800019d4`
- `0x180001e9c`
- `0x18000228c`
- `0x180002474`

## callees

- `0x1800029fc`
- `0x1800044f4`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180002a22`
- `KERNEL32!ReadFile` at `0x180002a22`
- `KERNEL32!GetLastError` at `0x180002a2c`
- `KERNEL32!GetLastError` at `0x180002a2c`

## pseudocode

```c
__int64 __fastcall File::Read(const unsigned __int16 **this, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned __int16 *v6; // rcx
  signed int v7; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  v6 = (unsigned __int16 *)*this;
  v7 = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v6, a2, a3, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( a4 )
  {
    *a4 = NumberOfBytesRead;
  }
  else if ( NumberOfBytesRead != a3 )
  {
    v7 = -2147023900;
    goto LABEL_7;
  }
  if ( v7 < 0 )
LABEL_7:
    LogFileError(&WofTaskFileReadErrorEventId, this[1], 0, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800029fc  push    rbx
0x1800029fe  push    rsi
0x1800029ff  push    rdi
0x180002a00  push    r14
0x180002a02  sub     rsp, 38h
0x180002a06  mov     rdi, r9
0x180002a09  mov     r14, rcx
0x180002a0c  mov     rcx, [rcx]; hFile
0x180002a0f  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002a14  xor     ebx, ebx
0x180002a16  mov     esi, r8d
0x180002a19  mov     [rsp+58h+NumberOfBytesRead], ebx
0x180002a1d  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180002a22  call    cs:__imp_ReadFile
0x180002a28  test    eax, eax
0x180002a2a  jnz     short loc_180002A41
0x180002a2c  call    cs:__imp_GetLastError
0x180002a32  mov     ebx, eax
0x180002a34  test    eax, eax
0x180002a36  jle     short loc_180002A41
0x180002a38  movzx   ebx, ax
0x180002a3b  or      ebx, 80070000h
0x180002a41  test    rdi, rdi
0x180002a44  jz      short loc_180002A72
0x180002a46  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180002a4a  mov     [rdi], eax
0x180002a4c  test    ebx, ebx
0x180002a4e  jns     short loc_180002A66
0x180002a50  mov     rdx, [r14+8]; unsigned __int16 *
0x180002a54  lea     rcx, WofTaskFileReadErrorEventId; EventDescriptor
0x180002a5b  mov     r9d, ebx; int
0x180002a5e  xor     r8d, r8d; unsigned __int16 *
0x180002a61  call    ?LogFileError@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1H@Z; LogFileError(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,int)
0x180002a66  mov     eax, ebx
0x180002a68  add     rsp, 38h
0x180002a6c  pop     r14
0x180002a6e  pop     rdi
0x180002a6f  pop     rsi
0x180002a70  pop     rbx
0x180002a71  retn
0x180002a72  cmp     [rsp+58h+NumberOfBytesRead], esi
0x180002a76  jz      short loc_180002A4C
0x180002a78  mov     ebx, 800703E4h
0x180002a7d  jmp     short loc_180002A50
```
