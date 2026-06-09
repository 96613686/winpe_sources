# console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d_

- ea: `0x1800216c4`
- end: `0x18002176e`
- name: `console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d___`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800216c4`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x1800216e9`
- `KERNEL32!WriteConsoleW` at `0x180021759`
- `KERNEL32!WriteConsoleW` at `0x1800216e9`
- `KERNEL32!WriteConsoleW` at `0x180021759`
- `KERNEL32!CloseHandle` at `0x18002170d`
- `KERNEL32!CloseHandle` at `0x18002170d`
- `KERNEL32!CreateFileW` at `0x180021738`
- `KERNEL32!CreateFileW` at `0x180021738`
- `KERNEL32!GetLastError` at `0x1800216f5`
- `KERNEL32!GetLastError` at `0x1800216f5`

## pseudocode

```c
__int64 __fastcall console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d_(__int64 a1)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  DWORD *v4; // r9
  DWORD v5; // r8d
  const void *v6; // rdx

  v2 = WriteConsoleW(hObject, *(const void **)a1, *(_DWORD *)(a1 + 8), *(LPDWORD *)(a1 + 16), 0);
  if ( !v2 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    FileW = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    v4 = *(DWORD **)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 8);
    v6 = *(const void **)a1;
    hObject = FileW;
    return WriteConsoleW(FileW, v6, v5, v4, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x1800216c4  mov     [rsp+arg_0], rbx
0x1800216c9  push    rdi
0x1800216ca  sub     rsp, 40h
0x1800216ce  mov     r9, [rcx+10h]; lpNumberOfCharsWritten
0x1800216d2  mov     rbx, rcx
0x1800216d5  mov     r8d, [rcx+8]; nNumberOfCharsToWrite
0x1800216d9  mov     rdx, [rcx]; lpBuffer
0x1800216dc  mov     rcx, cs:hObject; hConsoleOutput
0x1800216e3  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x1800216e9  call    cs:__imp_WriteConsoleW
0x1800216ef  mov     edi, eax
0x1800216f1  test    eax, eax
0x1800216f3  jnz     short loc_180021761
0x1800216f5  call    cs:__imp_GetLastError
0x1800216fb  cmp     eax, 6
0x1800216fe  jnz     short loc_180021761
0x180021700  mov     rcx, cs:hObject; hObject
0x180021707  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002170b  ja      short loc_180021713
0x18002170d  call    cs:__imp_CloseHandle
0x180021713  and     [rsp+48h+var_18], 0
0x180021719  lea     rcx, FileName; "CONOUT$"
0x180021720  and     [rsp+48h+var_20], 0
0x180021725  mov     r8d, 3; dwShareMode
0x18002172b  xor     r9d, r9d; lpSecurityAttributes
0x18002172e  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x180021733  mov     edx, 40000000h; dwDesiredAccess
0x180021738  call    cs:__imp_CreateFileW
0x18002173e  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180021744  mov     rcx, rax; hConsoleOutput
0x180021747  mov     r9, [rbx+10h]; lpNumberOfCharsWritten
0x18002174b  mov     r8d, [rbx+8]; nNumberOfCharsToWrite
0x18002174f  mov     rdx, [rbx]; lpBuffer
0x180021752  mov     cs:hObject, rax
0x180021759  call    cs:__imp_WriteConsoleW
0x18002175f  mov     edi, eax
0x180021761  mov     rbx, [rsp+48h+arg_0]
0x180021766  mov     eax, edi
0x180021768  add     rsp, 40h
0x18002176c  pop     rdi
0x18002176d  retn
```
