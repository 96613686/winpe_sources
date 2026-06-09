# BoxOpenFromPath

- ea: `0x140054ac8`
- end: `0x140054bce`
- name: `BoxOpenFromPath`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140016fa8`
- `0x140019830`
- `0x14001a000`
- `0x14001a670`
- `0x14001e1b0`
- `0x14001e7b0`
- `0x14001ec90`

## callees

- `0x14005300c`
- `0x140053ba0`
- `0x140053c68`
- `0x140054ac8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140054b74`
- `KERNEL32!CloseHandle` at `0x140054b74`
- `KERNEL32!HeapAlloc` at `0x140054b58`
- `KERNEL32!HeapAlloc` at `0x140054b58`
- `KERNEL32!GetProcessHeap` at `0x140054b40`
- `KERNEL32!GetProcessHeap` at `0x140054b40`
- `KERNEL32!GetLastError` at `0x140054b1a`
- `KERNEL32!GetLastError` at `0x140054b1a`
- `KERNEL32!CreateFileW` at `0x140054b05`
- `KERNEL32!CreateFileW` at `0x140054b05`

## pseudocode

```c
__int64 __fastcall BoxOpenFromPath(const WCHAR *a1, _QWORD *a2)
{
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int BoxHeaderIntoHandle; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  void *v10; // rcx

  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x8000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    BoxHeaderIntoHandle = LastError;
    if ( LastError > 0 )
      BoxHeaderIntoHandle = (unsigned __int16)LastError | 0x80070000;
    if ( BoxHeaderIntoHandle >= 0 )
      return (unsigned int)-2147467259;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x20u);
    v9 = v8;
    if ( v8 )
    {
      *v8 = FileW;
      BoxHeaderIntoHandle = StrAllocString(v8 + 1, a1, 0);
      v10 = v9;
      if ( BoxHeaderIntoHandle < 0
        || (BoxHeaderIntoHandle = LoadBoxHeaderIntoHandle(v9), v10 = v9, BoxHeaderIntoHandle < 0) )
      {
        FreeBoxFileHandle(v10);
      }
      else
      {
        *a2 = v9;
      }
    }
    else
    {
      BoxHeaderIntoHandle = -2147024882;
      CloseHandle(FileW);
    }
  }
  return (unsigned int)BoxHeaderIntoHandle;
}

```

## disassembly

```asm
0x140054ac8  mov     rax, rsp
0x140054acb  mov     [rax+8], rbx
0x140054acf  mov     [rax+10h], rsi
0x140054ad3  mov     [rax+18h], rdi
0x140054ad7  push    r14
0x140054ad9  sub     rsp, 40h
0x140054add  mov     qword ptr [rax-18h], 0
0x140054ae5  xor     r9d, r9d; lpSecurityAttributes
0x140054ae8  mov     r14, rdx
0x140054aeb  mov     dword ptr [rax-20h], 8000080h
0x140054af2  mov     edx, 80000000h; dwDesiredAccess
0x140054af7  mov     dword ptr [rax-28h], 3
0x140054afe  mov     rbx, rcx
0x140054b01  lea     r8d, [r9+7]; dwShareMode
0x140054b05  call    cs:__imp_CreateFileW
0x140054b0c  nop     dword ptr [rax+rax+00h]
0x140054b11  mov     rsi, rax
0x140054b14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140054b18  jnz     short loc_140054B40
0x140054b1a  call    cs:__imp_GetLastError
0x140054b21  nop     dword ptr [rax+rax+00h]
0x140054b26  mov     ebx, eax
0x140054b28  test    eax, eax
0x140054b2a  jle     short loc_140054B35
0x140054b2c  movzx   ebx, ax
0x140054b2f  or      ebx, 80070000h
0x140054b35  test    ebx, ebx
0x140054b37  js      short loc_140054BB5
0x140054b39  mov     ebx, 80004005h
0x140054b3e  jmp     short loc_140054BB5
0x140054b40  call    cs:__imp_GetProcessHeap
0x140054b47  nop     dword ptr [rax+rax+00h]
0x140054b4c  mov     edx, 8; dwFlags
0x140054b51  mov     rcx, rax; hHeap
0x140054b54  lea     r8d, [rdx+18h]; dwBytes
0x140054b58  call    cs:__imp_HeapAlloc
0x140054b5f  nop     dword ptr [rax+rax+00h]
0x140054b64  mov     rdi, rax
0x140054b67  test    rax, rax
0x140054b6a  jnz     short loc_140054B82
0x140054b6c  mov     rcx, rsi; hObject
0x140054b6f  mov     ebx, 8007000Eh
0x140054b74  call    cs:__imp_CloseHandle
0x140054b7b  nop     dword ptr [rax+rax+00h]
0x140054b80  jmp     short loc_140054BB5
0x140054b82  lea     rcx, [rax+8]
0x140054b86  mov     [rax], rsi
0x140054b89  xor     r8d, r8d
0x140054b8c  mov     rdx, rbx
0x140054b8f  call    StrAllocString
0x140054b94  mov     ebx, eax
0x140054b96  mov     rcx, rdi; lpMem
0x140054b99  test    eax, eax
0x140054b9b  js      short loc_140054BB0
0x140054b9d  call    LoadBoxHeaderIntoHandle
0x140054ba2  mov     ebx, eax
0x140054ba4  mov     rcx, rdi
0x140054ba7  test    eax, eax
0x140054ba9  js      short loc_140054BB0
0x140054bab  mov     [r14], rdi
0x140054bae  jmp     short loc_140054BB5
0x140054bb0  call    FreeBoxFileHandle
0x140054bb5  mov     rsi, [rsp+48h+arg_8]
0x140054bba  mov     eax, ebx
0x140054bbc  mov     rbx, [rsp+48h+arg_0]
0x140054bc1  mov     rdi, [rsp+48h+arg_10]
0x140054bc6  add     rsp, 40h
0x140054bca  pop     r14
0x140054bcc  retn
```
