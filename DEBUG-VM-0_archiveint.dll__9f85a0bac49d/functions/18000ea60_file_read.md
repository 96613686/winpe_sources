# file_read

- ea: `0x18000ea60`
- end: `0x18000eaf3`
- name: `file_read`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006c00`
- `0x18000ea60`
- `0x18000eafc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea9e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eabd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eacc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea9e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eabd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eacc`

## string_xrefs

- `0x18000eaa4`: `Error reading stdin`
- `0x18000eac3`: `Error reading '%s'`
- `0x18000ead2`: `Error reading '%ls'`

## pseudocode

```c
__int64 __fastcall file_read(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbp
  unsigned int *v6; // rax
  unsigned int *v7; // rax
  unsigned int *v8; // rax

  *a3 = *(_QWORD *)(a2 + 16);
  while ( 1 )
  {
    v5 = _la_read(*(_DWORD *)a2, *(void **)(a2 + 16), *(_QWORD *)(a2 + 8));
    if ( v5 >= 0 )
      break;
    if ( *(_DWORD *)_o__errno() != 4 )
    {
      if ( *(_DWORD *)(a2 + 44) )
      {
        if ( *(_DWORD *)(a2 + 44) == 1 )
        {
          v7 = (unsigned int *)_o__errno();
          archive_set_error(a1, *v7, "Error reading '%s'", a2 + 48);
        }
        else
        {
          v8 = (unsigned int *)_o__errno();
          archive_set_error(a1, *v8, "Error reading '%ls'", a2 + 48);
        }
      }
      else
      {
        v6 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v6, "Error reading stdin");
      }
      return v5;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000ea60  push    rbx
0x18000ea62  push    rbp
0x18000ea63  push    rsi
0x18000ea64  push    rdi
0x18000ea65  sub     rsp, 28h
0x18000ea69  mov     rax, [rdx+10h]
0x18000ea6d  mov     rbx, rdx
0x18000ea70  mov     [r8], rax
0x18000ea73  mov     rsi, rcx
0x18000ea76  mov     r8, [rbx+8]
0x18000ea7a  mov     rdx, [rbx+10h]
0x18000ea7e  mov     ecx, [rbx]
0x18000ea80  call    __la_read
0x18000ea85  mov     rbp, rax
0x18000ea88  test    rax, rax
0x18000ea8b  jns     short loc_18000EAE7
0x18000ea8d  call    cs:__imp__o__errno
0x18000ea93  cmp     dword ptr [rax], 4
0x18000ea96  jz      short loc_18000EA76
0x18000ea98  cmp     dword ptr [rbx+2Ch], 0
0x18000ea9c  jnz     short loc_18000EAB7
0x18000ea9e  call    cs:__imp__o__errno
0x18000eaa4  lea     r8, aErrorReadingSt; "Error reading stdin"
0x18000eaab  mov     rcx, rsi
0x18000eaae  mov     edx, [rax]
0x18000eab0  call    archive_set_error
0x18000eab5  jmp     short loc_18000EAE7
0x18000eab7  cmp     dword ptr [rbx+2Ch], 1
0x18000eabb  jnz     short loc_18000EACC
0x18000eabd  call    cs:__imp__o__errno
0x18000eac3  lea     r8, aErrorReadingS; "Error reading '%s'"
0x18000eaca  jmp     short loc_18000EAD9
0x18000eacc  call    cs:__imp__o__errno
0x18000ead2  lea     r8, aErrorReadingLs; "Error reading '%ls'"
0x18000ead9  mov     edx, [rax]
0x18000eadb  lea     r9, [rbx+30h]
0x18000eadf  mov     rcx, rsi
0x18000eae2  call    archive_set_error
0x18000eae7  mov     rax, rbp
0x18000eaea  add     rsp, 28h
0x18000eaee  pop     rdi
0x18000eaef  pop     rsi
0x18000eaf0  pop     rbp
0x18000eaf1  pop     rbx
0x18000eaf2  retn
```
