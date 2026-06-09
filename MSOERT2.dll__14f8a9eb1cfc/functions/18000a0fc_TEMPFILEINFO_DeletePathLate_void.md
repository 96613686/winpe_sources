# TEMPFILEINFO::_DeletePathLate(void)

- ea: `0x18000a0fc`
- end: `0x18000a217`
- name: `?_DeletePathLate@TEMPFILEINFO@@AEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(TEMPFILEINFO *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800093f0`

## callees

- `0x180001c80`
- `0x180007f80`
- `0x18000a0fc`
- `0x18000a374`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a184`
- `KERNEL32!GetLastError` at `0x18000a18f`
- `KERNEL32!GetLastError` at `0x18000a184`
- `KERNEL32!GetLastError` at `0x18000a18f`
- `KERNEL32!CloseHandle` at `0x18000a12a`
- `KERNEL32!CloseHandle` at `0x18000a12a`
- `KERNEL32!DeleteFileW` at `0x18000a174`
- `KERNEL32!DeleteFileW` at `0x18000a1c6`
- `KERNEL32!DeleteFileW` at `0x18000a174`
- `KERNEL32!DeleteFileW` at `0x18000a1c6`
- `KERNEL32!RemoveDirectoryW` at `0x18000a161`
- `KERNEL32!RemoveDirectoryW` at `0x18000a161`
- `KERNEL32!MoveFileExW` at `0x18000a1f1`
- `KERNEL32!MoveFileExW` at `0x18000a1f1`

## pseudocode

```c
__int64 __fastcall TEMPFILEINFO::_DeletePathLate(TEMPFILEINFO *this)
{
  __int64 result; // rax
  int LastError; // ebp
  const WCHAR *v4; // rdi
  int v5; // eax
  const WCHAR *v6; // rcx
  BOOL v7; // eax
  BOOL v8; // esi
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx

  if ( !*((_DWORD *)this + 132) )
    return 0;
  LastError = TEMPFILEINFO::_OpenDeleteHandle(this);
  if ( LastError >= 0 )
  {
    CloseHandle(*((HANDLE *)this + 71));
    *((_QWORD *)this + 71) = -1;
    return 0;
  }
  v4 = &ExistingFileName;
  v5 = *((_DWORD *)this + 132);
  v6 = &ExistingFileName;
  if ( *((_DWORD *)this + 140) )
  {
    if ( v5 )
      v6 = (const WCHAR *)*((_QWORD *)this + 67);
    v7 = RemoveDirectoryW(v6);
LABEL_19:
    v8 = v7;
    LastError = HrGetLastError();
    if ( !v8 )
    {
      if ( *((_DWORD *)this + 132) )
        v4 = (const WCHAR *)*((_QWORD *)this + 67);
      v8 = MoveFileExW(v4, 0, 4u);
      LastError = HrGetLastError();
    }
    goto LABEL_24;
  }
  if ( v5 )
    v6 = (const WCHAR *)*((_QWORD *)this + 67);
  v8 = DeleteFileW(v6);
  if ( v8 )
    goto LABEL_24;
  if ( GetLastError() != 3 && GetLastError() != 2 )
  {
    v9 = &ExistingFileName;
    if ( *((_DWORD *)this + 132) )
      v9 = (const WCHAR *)*((_QWORD *)this + 67);
    RemoveReadOnlyAttributeW(v9);
    v10 = &ExistingFileName;
    if ( *((_DWORD *)this + 132) )
      v10 = (const WCHAR *)*((_QWORD *)this + 67);
    v7 = DeleteFileW(v10);
    goto LABEL_19;
  }
  LastError = 0;
  v8 = 1;
LABEL_24:
  result = 0;
  if ( !v8 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x18000a0fc  push    rbx
0x18000a0fe  push    rbp
0x18000a0ff  push    rsi
0x18000a100  push    rdi
0x18000a101  sub     rsp, 28h
0x18000a105  cmp     dword ptr [rcx+210h], 0
0x18000a10c  mov     rbx, rcx
0x18000a10f  jnz     short loc_18000A118
0x18000a111  xor     eax, eax
0x18000a113  jmp     loc_18000A20E
0x18000a118  call    ?_OpenDeleteHandle@TEMPFILEINFO@@AEAAJXZ; TEMPFILEINFO::_OpenDeleteHandle(void)
0x18000a11d  mov     ebp, eax
0x18000a11f  test    eax, eax
0x18000a121  js      short loc_18000A13D
0x18000a123  mov     rcx, [rbx+238h]; hObject
0x18000a12a  call    cs:__imp_CloseHandle
0x18000a130  mov     qword ptr [rbx+238h], 0FFFFFFFFFFFFFFFFh
0x18000a13b  jmp     short loc_18000A111
0x18000a13d  cmp     dword ptr [rbx+230h], 0
0x18000a144  lea     rdi, ExistingFileName
0x18000a14b  mov     eax, [rbx+210h]
0x18000a151  mov     rcx, rdi
0x18000a154  jz      short loc_18000A169
0x18000a156  test    eax, eax
0x18000a158  jz      short loc_18000A161
0x18000a15a  mov     rcx, [rbx+218h]; lpPathName
0x18000a161  call    cs:__imp_RemoveDirectoryW
0x18000a167  jmp     short loc_18000A1CC
0x18000a169  test    eax, eax
0x18000a16b  jz      short loc_18000A174
0x18000a16d  mov     rcx, [rbx+218h]; lpFileName
0x18000a174  call    cs:__imp_DeleteFileW
0x18000a17a  mov     esi, eax
0x18000a17c  test    eax, eax
0x18000a17e  jnz     loc_18000A207
0x18000a184  call    cs:__imp_GetLastError
0x18000a18a  cmp     eax, 3
0x18000a18d  jz      short loc_18000A202
0x18000a18f  call    cs:__imp_GetLastError
0x18000a195  cmp     eax, 2
0x18000a198  jz      short loc_18000A202
0x18000a19a  mov     rcx, rdi
0x18000a19d  cmp     [rbx+210h], esi
0x18000a1a3  jz      short loc_18000A1AC
0x18000a1a5  mov     rcx, [rbx+218h]; lpFileName
0x18000a1ac  xor     edx, edx
0x18000a1ae  call    RemoveReadOnlyAttributeW
0x18000a1b3  cmp     dword ptr [rbx+210h], 0
0x18000a1ba  mov     rcx, rdi
0x18000a1bd  jz      short loc_18000A1C6
0x18000a1bf  mov     rcx, [rbx+218h]; lpFileName
0x18000a1c6  call    cs:__imp_DeleteFileW
0x18000a1cc  mov     esi, eax
0x18000a1ce  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000a1d3  mov     ebp, eax
0x18000a1d5  test    esi, esi
0x18000a1d7  jnz     short loc_18000A207
0x18000a1d9  cmp     [rbx+210h], esi
0x18000a1df  jz      short loc_18000A1E8
0x18000a1e1  mov     rdi, [rbx+218h]
0x18000a1e8  xor     edx, edx; lpNewFileName
0x18000a1ea  mov     rcx, rdi; lpExistingFileName
0x18000a1ed  lea     r8d, [rdx+4]; dwFlags
0x18000a1f1  call    cs:__imp_MoveFileExW
0x18000a1f7  mov     esi, eax
0x18000a1f9  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000a1fe  mov     ebp, eax
0x18000a200  jmp     short loc_18000A207
0x18000a202  xor     ebp, ebp
0x18000a204  lea     esi, [rbp+1]
0x18000a207  xor     eax, eax
0x18000a209  test    esi, esi
0x18000a20b  cmovz   eax, ebp
0x18000a20e  add     rsp, 28h
0x18000a212  pop     rdi
0x18000a213  pop     rsi
0x18000a214  pop     rbp
0x18000a215  pop     rbx
0x18000a216  retn
```
