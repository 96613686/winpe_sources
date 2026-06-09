# GetShellProcessHandle(ulong,void * *)

- ea: `0x1800226b4`
- end: `0x18002271d`
- name: `?GetShellProcessHandle@@YAJKPEAPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180021d44`

## callees

- `0x1800226b4`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x1800226f8`
- `KERNEL32!OpenProcess` at `0x1800226f8`
- `USER32!GetWindowThreadProcessId` at `0x1800226e2`
- `USER32!GetWindowThreadProcessId` at `0x1800226e2`
- `USER32!GetShellWindow` at `0x1800226c7`
- `USER32!GetShellWindow` at `0x1800226c7`

## pseudocode

```c
__int64 __fastcall GetShellProcessHandle(DWORD a1, void **a2)
{
  HWND ShellWindow; // rax
  HANDLE v4; // rax
  unsigned int v5; // ecx
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  dwProcessId = a1;
  *a2 = 0;
  ShellWindow = GetShellWindow();
  if ( !ShellWindow )
    return 2147500037LL;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(ShellWindow, &dwProcessId) )
    return 2147500037LL;
  v4 = OpenProcess(0x80u, 0, dwProcessId);
  v5 = 0;
  *a2 = v4;
  if ( !v4 )
    return (unsigned int)-2147467259;
  return v5;
}

```

## disassembly

```asm
0x1800226b4  mov     [rsp+dwProcessId], ecx
0x1800226b8  push    rbx
0x1800226b9  sub     rsp, 20h
0x1800226bd  mov     rbx, rdx
0x1800226c0  mov     qword ptr [rdx], 0
0x1800226c7  call    cs:__imp_GetShellWindow
0x1800226cd  test    rax, rax
0x1800226d0  jz      short loc_180022712
0x1800226d2  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x1800226d7  mov     [rsp+28h+dwProcessId], 0
0x1800226df  mov     rcx, rax; hWnd
0x1800226e2  call    cs:__imp_GetWindowThreadProcessId
0x1800226e8  test    eax, eax
0x1800226ea  jz      short loc_180022712
0x1800226ec  mov     r8d, [rsp+28h+dwProcessId]; dwProcessId
0x1800226f1  xor     edx, edx; bInheritHandle
0x1800226f3  mov     ecx, 80h; dwDesiredAccess
0x1800226f8  call    cs:__imp_OpenProcess
0x1800226fe  xor     ecx, ecx
0x180022700  mov     edx, 80004005h
0x180022705  test    rax, rax
0x180022708  mov     [rbx], rax
0x18002270b  cmovz   ecx, edx
0x18002270e  mov     eax, ecx
0x180022710  jmp     short loc_180022717
0x180022712  mov     eax, 80004005h
0x180022717  add     rsp, 20h
0x18002271b  pop     rbx
0x18002271c  retn
```
