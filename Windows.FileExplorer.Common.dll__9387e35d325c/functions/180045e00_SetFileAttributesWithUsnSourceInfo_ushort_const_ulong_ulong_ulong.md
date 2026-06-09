# SetFileAttributesWithUsnSourceInfo(ushort const *,ulong,ulong,ulong)

- ea: `0x180045e00`
- end: `0x180045e8a`
- name: `?SetFileAttributesWithUsnSourceInfo@@YAJPEBGKKK@Z`
- size: `138`
- prototype: `int(const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180044f64`

## callees

- `0x180045dd0`
- `0x180045e00`
- `0x180045e90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045e39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045e39`

## pseudocode

```c
__int64 __fastcall SetFileAttributesWithUsnSourceInfo(const unsigned __int16 *a1, int a2, __int64 a3, unsigned int a4)
{
  HANDLE FileW; // rax
  int v7; // eax
  char *v8; // rbx
  unsigned int v9; // edi
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF

  hObject = 0;
  FileW = CreateFileW(a1, 0x180u, 0, 0, 3u, 0x2200000u, 0);
  v7 = ResultFromWin32Handle(FileW, &hObject);
  v8 = (char *)hObject;
  v9 = v7;
  if ( v7 >= 0 )
    v9 = SetFileAttributesWithUsnSourceInfoByHandle(hObject, a2, 1, a4);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return v9;
}

```

## disassembly

```asm
0x180045e00  mov     rax, rsp
0x180045e03  push    rbx
0x180045e04  push    rbp
0x180045e05  push    rsi
0x180045e06  push    rdi
0x180045e07  sub     rsp, 58h
0x180045e0b  mov     qword ptr [rax-48h], 0
0x180045e13  mov     esi, r9d
0x180045e16  mov     ebp, edx
0x180045e18  mov     dword ptr [rax-50h], 2200000h
0x180045e1f  xor     r9d, r9d; lpSecurityAttributes
0x180045e22  mov     dword ptr [rax-58h], 3
0x180045e29  mov     edx, 180h; dwDesiredAccess
0x180045e2e  mov     qword ptr [rax-38h], 0
0x180045e36  xor     r8d, r8d; dwShareMode
0x180045e39  call    cs:__imp_CreateFileW
0x180045e3f  mov     rcx, rax; void *
0x180045e42  lea     rdx, [rsp+78h+hObject]; void **
0x180045e47  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180045e4c  mov     rbx, [rsp+78h+hObject]
0x180045e51  mov     edi, eax
0x180045e53  test    eax, eax
0x180045e55  js      short loc_180045E6C
0x180045e57  mov     r9d, esi; unsigned int
0x180045e5a  mov     r8d, 1; unsigned int
0x180045e60  mov     edx, ebp; unsigned int
0x180045e62  mov     rcx, rbx; void *
0x180045e65  call    ?SetFileAttributesWithUsnSourceInfoByHandle@@YAJPEAXKKK@Z; SetFileAttributesWithUsnSourceInfoByHandle(void *,ulong,ulong,ulong)
0x180045e6a  mov     edi, eax
0x180045e6c  lea     rax, [rbx-1]
0x180045e70  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045e74  ja      short loc_180045E7F
0x180045e76  mov     rcx, rbx; hObject
0x180045e79  call    cs:__imp_CloseHandle
0x180045e7f  mov     eax, edi
0x180045e81  add     rsp, 58h
0x180045e85  pop     rdi
0x180045e86  pop     rsi
0x180045e87  pop     rbp
0x180045e88  pop     rbx
0x180045e89  retn
```
