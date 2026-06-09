# CleanDisk(ushort const *,int,int)

- ea: `0x140019d88`
- end: `0x140019e11`
- name: `?CleanDisk@@YAHPEBGHH@Z`
- size: `137`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140015e10`

## callees

- `0x140019d88`
- `0x140019e18`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140019de9`
- `KERNEL32!CloseHandle` at `0x140019de9`
- `KERNEL32!SetLastError` at `0x140019df9`
- `KERNEL32!SetLastError` at `0x140019df9`
- `KERNEL32!GetLastError` at `0x140019dca`
- `KERNEL32!GetLastError` at `0x140019dde`
- `KERNEL32!GetLastError` at `0x140019dca`
- `KERNEL32!GetLastError` at `0x140019dde`
- `KERNEL32!CreateFileW` at `0x140019db9`
- `KERNEL32!CreateFileW` at `0x140019db9`

## pseudocode

```c
__int64 __fastcall CleanDisk(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  int v2; // edx
  int v3; // r8d
  void *v4; // rbx
  unsigned int v5; // ebx
  DWORD LastError; // edi
  int v7; // esi

  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
  }
  else
  {
    v7 = CleanDiskByHandle(FileW, v2, v3);
    LastError = GetLastError();
    v5 = CloseHandle(v4);
    if ( !v7 )
    {
      v5 = 0;
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
LABEL_6:
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x140019d88  mov     rax, rsp
0x140019d8b  mov     [rax+8], rbx
0x140019d8f  mov     [rax+10h], rsi
0x140019d93  push    rdi
0x140019d94  sub     rsp, 40h
0x140019d98  mov     qword ptr [rax-18h], 0
0x140019da0  mov     r8d, 3; dwShareMode
0x140019da6  mov     dword ptr [rax-20h], 0
0x140019dad  xor     r9d, r9d; lpSecurityAttributes
0x140019db0  mov     edx, 0C0000000h; dwDesiredAccess
0x140019db5  mov     [rax-28h], r8d
0x140019db9  call    cs:__imp_CreateFileW
0x140019dbf  mov     rbx, rax
0x140019dc2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140019dc6  jnz     short loc_140019DD4
0x140019dc8  xor     ebx, ebx
0x140019dca  call    cs:__imp_GetLastError
0x140019dd0  mov     edi, eax
0x140019dd2  jmp     short loc_140019DF7
0x140019dd4  mov     rcx, rbx; hDevice
0x140019dd7  call    ?CleanDiskByHandle@@YAHPEAXHH@Z; CleanDiskByHandle(void *,int,int)
0x140019ddc  mov     esi, eax
0x140019dde  call    cs:__imp_GetLastError
0x140019de4  mov     rcx, rbx; hObject
0x140019de7  mov     edi, eax
0x140019de9  call    cs:__imp_CloseHandle
0x140019def  mov     ebx, eax
0x140019df1  test    esi, esi
0x140019df3  jnz     short loc_140019DCA
0x140019df5  mov     ebx, esi
0x140019df7  mov     ecx, edi; dwErrCode
0x140019df9  call    cs:__imp_SetLastError
0x140019dff  mov     rsi, [rsp+48h+arg_8]
0x140019e04  mov     eax, ebx
0x140019e06  mov     rbx, [rsp+48h+arg_0]
0x140019e0b  add     rsp, 40h
0x140019e0f  pop     rdi
0x140019e10  retn
```
