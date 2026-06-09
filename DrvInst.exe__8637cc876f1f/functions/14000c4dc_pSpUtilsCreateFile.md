# _pSpUtilsCreateFile

- ea: `0x14000c4dc`
- end: `0x14000c55b`
- name: `_pSpUtilsCreateFile`
- size: `127`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, __int64, __int64, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000cb60`

## callees

- `0x14000c4dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x14000c541`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x14000c541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c528`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c519`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c519`

## pseudocode

```c
DWORD __fastcall pSpUtilsCreateFile(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        _QWORD *a7)
{
  unsigned int v9; // ebx
  HANDLE FileW; // rax
  DWORD result; // eax

  v9 = 0;
  do
  {
    FileW = CreateFileW(lpFileName, dwDesiredAccess, 1u, 0, 4u, 0, 0);
    *a7 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result != 32 || v9 >= a6 )
        return result;
      SleepEx(0x32u, 0);
      v9 += 50;
    }
  }
  while ( *a7 == -1 );
  return 0;
}

```

## disassembly

```asm
0x14000c4dc  push    rbx
0x14000c4de  push    rbp
0x14000c4df  push    rsi
0x14000c4e0  push    rdi
0x14000c4e1  sub     rsp, 48h
0x14000c4e5  mov     rdi, [rsp+68h+arg_30]
0x14000c4ed  mov     esi, edx
0x14000c4ef  mov     rbp, rcx
0x14000c4f2  xor     ebx, ebx
0x14000c4f4  xor     r9d, r9d; lpSecurityAttributes
0x14000c4f7  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14000c500  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14000c508  mov     edx, esi; dwDesiredAccess
0x14000c50a  mov     rcx, rbp; lpFileName
0x14000c50d  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x14000c515  lea     r8d, [r9+1]; dwShareMode
0x14000c519  call    cs:__imp_CreateFileW
0x14000c51f  mov     [rdi], rax
0x14000c522  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c526  jnz     short loc_14000C54A
0x14000c528  call    cs:__imp_GetLastError
0x14000c52e  cmp     eax, 20h ; ' '
0x14000c531  jnz     short loc_14000C552
0x14000c533  cmp     ebx, [rsp+68h+arg_28]
0x14000c53a  jnb     short loc_14000C552
0x14000c53c  xor     edx, edx; bAlertable
0x14000c53e  lea     ecx, [rax+12h]; dwMilliseconds
0x14000c541  call    cs:__imp_SleepEx
0x14000c547  add     ebx, 32h ; '2'
0x14000c54a  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14000c54e  jz      short loc_14000C4F4
0x14000c550  xor     eax, eax
0x14000c552  add     rsp, 48h
0x14000c556  pop     rdi
0x14000c557  pop     rsi
0x14000c558  pop     rbp
0x14000c559  pop     rbx
0x14000c55a  retn
```
