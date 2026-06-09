# file_seek

- ea: `0x1800c0830`
- end: `0x1800c08b2`
- name: `file_seek`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006c00`
- `0x1800c0830`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0856`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0863`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0886`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0856`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0863`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c0886`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x1800c084b`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x1800c084b`

## string_xrefs

- `0x1800c086c`: `A file descriptor(%d) is not seekable(PIPE)`
- `0x1800c088f`: `Error seeking in a file descriptor(%d)`

## pseudocode

```c
__int64 __fastcall file_seek(__int64 a1, int *a2, __int64 a3, int a4)
{
  __int64 result; // rax
  __int64 v7; // rcx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  unsigned int *v11; // rax
  unsigned int *v12; // rax

  result = _lseeki64(*a2, a3, a4);
  if ( result < 0 )
  {
    v8 = (_DWORD *)_o__errno(v7);
    v10 = *a2;
    if ( *v8 == 29 )
    {
      v11 = (unsigned int *)_o__errno(v9);
      archive_set_error(a1, *v11, "A file descriptor(%d) is not seekable(PIPE)", v10);
      return -25;
    }
    else
    {
      v12 = (unsigned int *)_o__errno(v9);
      archive_set_error(a1, *v12, "Error seeking in a file descriptor(%d)", v10);
      return -30;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c0830  mov     [rsp+arg_0], rbx
0x1800c0835  push    rdi
0x1800c0836  sub     rsp, 20h
0x1800c083a  mov     rbx, rdx
0x1800c083d  mov     rax, r8
0x1800c0840  mov     rdi, rcx
0x1800c0843  mov     r8d, r9d; Origin
0x1800c0846  mov     rdx, rax; Offset
0x1800c0849  mov     ecx, [rbx]; FileHandle
0x1800c084b  call    cs:__imp__lseeki64
0x1800c0851  test    rax, rax
0x1800c0854  jns     short loc_1800C08A7
0x1800c0856  call    cs:__imp__o__errno
0x1800c085c  mov     ebx, [rbx]
0x1800c085e  cmp     dword ptr [rax], 1Dh
0x1800c0861  jnz     short loc_1800C0886
0x1800c0863  call    cs:__imp__o__errno
0x1800c0869  mov     r9d, ebx
0x1800c086c  lea     r8, aAFileDescripto; "A file descriptor(%d) is not seekable(P"...
0x1800c0873  mov     rcx, rdi
0x1800c0876  mov     edx, [rax]
0x1800c0878  call    archive_set_error
0x1800c087d  mov     rax, 0FFFFFFFFFFFFFFE7h
0x1800c0884  jmp     short loc_1800C08A7
0x1800c0886  call    cs:__imp__o__errno
0x1800c088c  mov     r9d, ebx
0x1800c088f  lea     r8, aErrorSeekingIn_0; "Error seeking in a file descriptor(%d)"
0x1800c0896  mov     rcx, rdi
0x1800c0899  mov     edx, [rax]
0x1800c089b  call    archive_set_error
0x1800c08a0  mov     rax, 0FFFFFFFFFFFFFFE2h
0x1800c08a7  mov     rbx, [rsp+28h+arg_0]
0x1800c08ac  add     rsp, 20h
0x1800c08b0  pop     rdi
0x1800c08b1  retn
```
