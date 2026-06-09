# WriteStringToFile(ushort const *,ushort const *)

- ea: `0x18001be88`
- end: `0x18001bf67`
- name: `?WriteStringToFile@@YAJPEBG0@Z`
- size: `223`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b7f8`

## callees

- `0x18001a6dc`
- `0x18001be88`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf40`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001bf16`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001bf16`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001bee8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001bee8`

## pseudocode

```c
__int64 __fastcall WriteStringToFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v3; // ebx
  const WCHAR *v4; // r11
  HANDLE FileW; // rax
  void *v6; // rdi
  signed int v7; // eax
  signed int LastError; // eax
  unsigned __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v3 = StringCchLengthW(a2, 0x104u, &v10);
  if ( v3 >= 0 )
  {
    FileW = CreateFileW(v4, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v6 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      if ( !WriteFile(FileW, a2, 2 * v10 + 2, 0, 0) )
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      CloseHandle(v6);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001be88  mov     rax, rsp
0x18001be8b  mov     [rax+8], rbx
0x18001be8f  mov     [rax+10h], rsi
0x18001be93  push    rdi
0x18001be94  sub     rsp, 40h
0x18001be98  mov     rsi, rdx
0x18001be9b  mov     qword ptr [rax+18h], 0
0x18001bea3  mov     r11, rcx
0x18001bea6  lea     r8, [rax+18h]; unsigned __int64 *
0x18001beaa  mov     rcx, rsi; unsigned __int16 *
0x18001bead  mov     edx, 104h; unsigned __int64
0x18001beb2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001beb7  mov     ebx, eax
0x18001beb9  test    eax, eax
0x18001bebb  js      loc_18001BF55
0x18001bec1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001beca  xor     r9d, r9d; lpSecurityAttributes
0x18001becd  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001bed5  xor     r8d, r8d; dwShareMode
0x18001bed8  mov     edx, 40000000h; dwDesiredAccess
0x18001bedd  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18001bee5  mov     rcx, r11; lpFileName
0x18001bee8  call    cs:__imp_CreateFileW
0x18001beee  mov     rdi, rax
0x18001bef1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bef5  jz      short loc_18001BF40
0x18001bef7  mov     r8d, dword ptr [rsp+48h+arg_10]
0x18001befc  xor     r9d, r9d; lpNumberOfBytesWritten
0x18001beff  mov     rdx, rsi; lpBuffer
0x18001bf02  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18001bf0b  mov     rcx, rax; hFile
0x18001bf0e  lea     r8d, ds:2[r8*2]; nNumberOfBytesToWrite
0x18001bf16  call    cs:__imp_WriteFile
0x18001bf1c  test    eax, eax
0x18001bf1e  jnz     short loc_18001BF35
0x18001bf20  call    cs:__imp_GetLastError
0x18001bf26  mov     ebx, eax
0x18001bf28  test    eax, eax
0x18001bf2a  jle     short loc_18001BF35
0x18001bf2c  movzx   ebx, ax
0x18001bf2f  or      ebx, 80070000h
0x18001bf35  mov     rcx, rdi; hObject
0x18001bf38  call    cs:__imp_CloseHandle
0x18001bf3e  jmp     short loc_18001BF55
0x18001bf40  call    cs:__imp_GetLastError
0x18001bf46  mov     ebx, eax
0x18001bf48  test    eax, eax
0x18001bf4a  jle     short loc_18001BF55
0x18001bf4c  movzx   ebx, ax
0x18001bf4f  or      ebx, 80070000h
0x18001bf55  mov     rsi, [rsp+48h+arg_8]
0x18001bf5a  mov     eax, ebx
0x18001bf5c  mov     rbx, [rsp+48h+arg_0]
0x18001bf61  add     rsp, 40h
0x18001bf65  pop     rdi
0x18001bf66  retn
```
