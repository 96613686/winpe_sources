# PartitionDisk(ushort const *,int,int)

- ea: `0x14001b830`
- end: `0x14001b8bd`
- name: `?PartitionDisk@@YAHPEBGHH@Z`
- size: `141`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140015bfc`
- `0x14001a714`

## callees

- `0x14001b830`
- `0x14001b8c4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001b895`
- `KERNEL32!CloseHandle` at `0x14001b895`
- `KERNEL32!SetLastError` at `0x14001b8a5`
- `KERNEL32!SetLastError` at `0x14001b8a5`
- `KERNEL32!GetLastError` at `0x14001b874`
- `KERNEL32!GetLastError` at `0x14001b88a`
- `KERNEL32!GetLastError` at `0x14001b874`
- `KERNEL32!GetLastError` at `0x14001b88a`
- `KERNEL32!CreateFileW` at `0x14001b863`
- `KERNEL32!CreateFileW` at `0x14001b863`

## pseudocode

```c
__int64 __fastcall PartitionDisk(const unsigned __int16 *a1, int a2)
{
  HANDLE FileW; // rax
  int v4; // r8d
  void *v5; // rbx
  unsigned int v6; // ebx
  DWORD LastError; // edi
  int v8; // esi

  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 0;
  }
  else
  {
    v8 = PartitionDiskByHandle(FileW, a2, v4);
    LastError = GetLastError();
    v6 = CloseHandle(v5);
    if ( !v8 )
    {
      v6 = 0;
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
LABEL_6:
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x14001b830  mov     rax, rsp
0x14001b833  mov     [rax+8], rbx
0x14001b837  mov     [rax+10h], rsi
0x14001b83b  push    rdi
0x14001b83c  sub     rsp, 40h
0x14001b840  mov     qword ptr [rax-18h], 0
0x14001b848  mov     edi, edx
0x14001b84a  mov     r8d, 3; dwShareMode
0x14001b850  mov     dword ptr [rax-20h], 0
0x14001b857  mov     edx, 0C0000000h; dwDesiredAccess
0x14001b85c  mov     [rax-28h], r8d
0x14001b860  xor     r9d, r9d; lpSecurityAttributes
0x14001b863  call    cs:__imp_CreateFileW
0x14001b869  mov     rbx, rax
0x14001b86c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b870  jnz     short loc_14001B87E
0x14001b872  xor     ebx, ebx
0x14001b874  call    cs:__imp_GetLastError
0x14001b87a  mov     edi, eax
0x14001b87c  jmp     short loc_14001B8A3
0x14001b87e  mov     edx, edi; int
0x14001b880  mov     rcx, rbx; hFile
0x14001b883  call    ?PartitionDiskByHandle@@YAHPEAXHH@Z; PartitionDiskByHandle(void *,int,int)
0x14001b888  mov     esi, eax
0x14001b88a  call    cs:__imp_GetLastError
0x14001b890  mov     rcx, rbx; hObject
0x14001b893  mov     edi, eax
0x14001b895  call    cs:__imp_CloseHandle
0x14001b89b  mov     ebx, eax
0x14001b89d  test    esi, esi
0x14001b89f  jnz     short loc_14001B874
0x14001b8a1  mov     ebx, esi
0x14001b8a3  mov     ecx, edi; dwErrCode
0x14001b8a5  call    cs:__imp_SetLastError
0x14001b8ab  mov     rsi, [rsp+48h+arg_8]
0x14001b8b0  mov     eax, ebx
0x14001b8b2  mov     rbx, [rsp+48h+arg_0]
0x14001b8b7  add     rsp, 40h
0x14001b8bb  pop     rdi
0x14001b8bc  retn
```
