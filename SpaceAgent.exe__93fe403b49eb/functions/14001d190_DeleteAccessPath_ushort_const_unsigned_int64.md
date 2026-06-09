# DeleteAccessPath(ushort const *,unsigned __int64)

- ea: `0x14001d190`
- end: `0x14001d1de`
- name: `?DeleteAccessPath@@YAHPEBG_K@Z`
- size: `78`
- prototype: `__int64 __fastcall(WCHAR *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001cde8`
- `0x14001d894`

## callees

- `0x14001d190`
- `0x14001d1e4`
- `0x14001d2d0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001d1cd`
- `KERNEL32!SetLastError` at `0x14001d1cd`
- `KERNEL32!GetLastError` at `0x14001d1a6`
- `KERNEL32!GetLastError` at `0x14001d1bf`
- `KERNEL32!GetLastError` at `0x14001d1a6`
- `KERNEL32!GetLastError` at `0x14001d1bf`

## pseudocode

```c
__int64 __fastcall DeleteAccessPath(WCHAR *a1, unsigned __int64 a2)
{
  int v4; // ebp
  DWORD LastError; // esi
  unsigned int v6; // ebx

  v4 = DeleteAccessPath_DeleteShares(a1, a2);
  LastError = GetLastError();
  v6 = DeleteAccessPath_DeletePath(a1, a2);
  if ( v4 )
    LastError = GetLastError();
  else
    v6 = 0;
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x14001d190  push    rbx
0x14001d192  push    rbp
0x14001d193  push    rsi
0x14001d194  push    rdi
0x14001d195  sub     rsp, 28h
0x14001d199  mov     rbx, rdx
0x14001d19c  mov     rdi, rcx
0x14001d19f  call    DeleteAccessPath_DeleteShares
0x14001d1a4  mov     ebp, eax
0x14001d1a6  call    cs:__imp_GetLastError
0x14001d1ac  mov     rdx, rbx; unsigned __int64
0x14001d1af  mov     rcx, rdi; unsigned __int16 *
0x14001d1b2  mov     esi, eax
0x14001d1b4  call    DeleteAccessPath_DeletePath
0x14001d1b9  mov     ebx, eax
0x14001d1bb  test    ebp, ebp
0x14001d1bd  jz      short loc_14001D1C9
0x14001d1bf  call    cs:__imp_GetLastError
0x14001d1c5  mov     esi, eax
0x14001d1c7  jmp     short loc_14001D1CB
0x14001d1c9  mov     ebx, ebp
0x14001d1cb  mov     ecx, esi; dwErrCode
0x14001d1cd  call    cs:__imp_SetLastError
0x14001d1d3  mov     eax, ebx
0x14001d1d5  add     rsp, 28h
0x14001d1d9  pop     rdi
0x14001d1da  pop     rsi
0x14001d1db  pop     rbp
0x14001d1dc  pop     rbx
0x14001d1dd  retn
```
