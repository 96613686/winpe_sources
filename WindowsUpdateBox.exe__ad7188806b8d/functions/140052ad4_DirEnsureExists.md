# DirEnsureExists

- ea: `0x140052ad4`
- end: `0x140052bf2`
- name: `DirEnsureExists`
- size: `286`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140013894`
- `0x14001ac60`
- `0x140052ad4`
- `0x140053648`
- `0x140054c20`

## callees

- `0x140052ad4`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x140052b12`
- `KERNEL32!CreateDirectoryW` at `0x140052b90`
- `KERNEL32!CreateDirectoryW` at `0x140052b12`
- `KERNEL32!CreateDirectoryW` at `0x140052b90`
- `KERNEL32!GetLastError` at `0x140052b26`
- `KERNEL32!GetLastError` at `0x140052ba0`
- `KERNEL32!GetLastError` at `0x140052b26`
- `KERNEL32!GetLastError` at `0x140052ba0`
- `KERNEL32!GetFileAttributesW` at `0x140052af4`
- `KERNEL32!GetFileAttributesW` at `0x140052af4`

## pseudocode

```c
__int64 __fastcall DirEnsureExists(LPCWSTR lpPathName)
{
  unsigned int v2; // ebx
  DWORD FileAttributesW; // eax
  WCHAR v4; // cx
  _WORD *v5; // rsi
  LPCWSTR v6; // rdx
  _WORD *v7; // rax
  int v8; // eax
  signed int LastError; // eax

  v2 = 0;
  FileAttributesW = GetFileAttributesW(lpPathName);
  if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0)
    && !CreateDirectoryW(lpPathName, 0)
    && GetLastError() != 183 )
  {
    v4 = *lpPathName;
    v5 = 0;
    v6 = lpPathName;
    if ( !*lpPathName )
      return (unsigned int)-2147024893;
    do
    {
      v7 = v6;
      if ( v4 != 92 )
        v7 = v5;
      ++v6;
      v5 = v7;
      v4 = *v6;
    }
    while ( *v6 );
    if ( v7 )
    {
      *v7 = 0;
      v8 = DirEnsureExists(lpPathName);
      *v5 = 92;
      v2 = v8;
      if ( v8 >= 0 )
      {
        if ( CreateDirectoryW(lpPathName, 0) )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError == 183 )
          {
            return 1;
          }
          else if ( LastError > 0 )
          {
            return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024893;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140052ad4  mov     rax, rsp
0x140052ad7  mov     [rax+8], rbx
0x140052adb  mov     [rax+10h], rbp
0x140052adf  mov     [rax+18h], rsi
0x140052ae3  mov     [rax+20h], rdi
0x140052ae7  push    r15
0x140052ae9  sub     rsp, 20h
0x140052aed  xor     ebp, ebp
0x140052aef  mov     rdi, rcx
0x140052af2  mov     ebx, ebp
0x140052af4  call    cs:__imp_GetFileAttributesW
0x140052afb  nop     dword ptr [rax+rax+00h]
0x140052b00  cmp     eax, 0FFFFFFFFh
0x140052b03  jz      short loc_140052B0D
0x140052b05  test    al, 10h
0x140052b07  jnz     loc_140052BD4
0x140052b0d  xor     edx, edx; lpSecurityAttributes
0x140052b0f  mov     rcx, rdi; lpPathName
0x140052b12  call    cs:__imp_CreateDirectoryW
0x140052b19  nop     dword ptr [rax+rax+00h]
0x140052b1e  test    eax, eax
0x140052b20  jnz     loc_140052BD4
0x140052b26  call    cs:__imp_GetLastError
0x140052b2d  nop     dword ptr [rax+rax+00h]
0x140052b32  cmp     eax, 0B7h
0x140052b37  jz      loc_140052BD4
0x140052b3d  movzx   ecx, word ptr [rdi]
0x140052b40  mov     rsi, rbp
0x140052b43  mov     rdx, rdi
0x140052b46  test    cx, cx
0x140052b49  jz      loc_140052BCF
0x140052b4f  mov     r15d, 5Ch ; '\'
0x140052b55  cmp     cx, r15w
0x140052b59  mov     rax, rdx
0x140052b5c  cmovnz  rax, rsi
0x140052b60  add     rdx, 2
0x140052b64  mov     rsi, rax
0x140052b67  movzx   ecx, word ptr [rdx]
0x140052b6a  test    cx, cx
0x140052b6d  jnz     short loc_140052B55
0x140052b6f  test    rax, rax
0x140052b72  jz      short loc_140052BCF
0x140052b74  xor     edx, edx
0x140052b76  mov     [rax], bp
0x140052b79  mov     rcx, rdi; lpPathName
0x140052b7c  call    DirEnsureExists
0x140052b81  mov     [rsi], r15w
0x140052b85  mov     ebx, eax
0x140052b87  test    eax, eax
0x140052b89  js      short loc_140052BD4
0x140052b8b  xor     edx, edx; lpSecurityAttributes
0x140052b8d  mov     rcx, rdi; lpPathName
0x140052b90  call    cs:__imp_CreateDirectoryW
0x140052b97  nop     dword ptr [rax+rax+00h]
0x140052b9c  test    eax, eax
0x140052b9e  jnz     short loc_140052BCB
0x140052ba0  call    cs:__imp_GetLastError
0x140052ba7  nop     dword ptr [rax+rax+00h]
0x140052bac  mov     ebx, eax
0x140052bae  cmp     eax, 0B7h
0x140052bb3  jnz     short loc_140052BBC
0x140052bb5  mov     ebx, 1
0x140052bba  jmp     short loc_140052BD4
0x140052bbc  test    eax, eax
0x140052bbe  jle     short loc_140052BD4
0x140052bc0  movzx   ebx, ax
0x140052bc3  or      ebx, 80070000h
0x140052bc9  jmp     short loc_140052BD4
0x140052bcb  mov     ebx, ebp
0x140052bcd  jmp     short loc_140052BD4
0x140052bcf  mov     ebx, 80070003h
0x140052bd4  mov     rbp, [rsp+28h+arg_8]
0x140052bd9  mov     eax, ebx
0x140052bdb  mov     rbx, [rsp+28h+arg_0]
0x140052be0  mov     rsi, [rsp+28h+arg_10]
0x140052be5  mov     rdi, [rsp+28h+arg_18]
0x140052bea  add     rsp, 20h
0x140052bee  pop     r15
0x140052bf0  retn
```
