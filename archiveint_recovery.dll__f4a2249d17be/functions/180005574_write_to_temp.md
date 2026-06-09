# write_to_temp

- ea: `0x180005574`
- end: `0x180005602`
- name: `write_to_temp`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800044f4`
- `0x1800046f0`

## callees

- `0x180005574`
- `0x180006c00`
- `0x180006f5c`
- `0x18000fe9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055e8`

## string_xrefs

- `0x1800055ad`: `Couldn't create temporary file`
- `0x1800055ee`: `write function failed`

## pseudocode

```c
__int64 __fastcall write_to_temp(__int64 a1, char *a2, unsigned __int64 a3)
{
  __int64 v3; // rbx
  int v7; // eax
  __int64 v8; // rcx
  unsigned int *v9; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int *v13; // rax

  v3 = *(_QWORD *)(a1 + 248);
  if ( *(_DWORD *)v3 == -1 && (*(_QWORD *)(v3 + 8) = 0, v7 = _archive_mktempx(a1, 0), *(_DWORD *)v3 = v7, v7 < 0) )
  {
    v9 = (unsigned int *)_o__errno(v8);
    archive_set_error(a1, *v9, "Couldn't create temporary file");
    return 4294967266LL;
  }
  else
  {
    while ( a3 )
    {
      v11 = _la_write(*(_DWORD *)v3, a2, a3);
      if ( v11 < 0 )
      {
        v13 = (unsigned int *)_o__errno(v12);
        archive_set_error(a1, *v13, "write function failed");
        return 4294967266LL;
      }
      a3 -= v11;
      a2 += v11;
      *(_QWORD *)(v3 + 8) += v11;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180005574  push    rbx
0x180005576  push    rbp
0x180005577  push    rsi
0x180005578  push    rdi
0x180005579  sub     rsp, 28h
0x18000557d  mov     rbx, [rcx+0F8h]
0x180005584  mov     rdi, r8
0x180005587  mov     rsi, rdx
0x18000558a  mov     rbp, rcx
0x18000558d  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180005590  jnz     short loc_1800055C5
0x180005592  xor     edx, edx
0x180005594  mov     qword ptr [rbx+8], 0
0x18000559c  call    __archive_mktempx
0x1800055a1  mov     [rbx], eax
0x1800055a3  test    eax, eax
0x1800055a5  jns     short loc_1800055C5
0x1800055a7  call    cs:__imp__o__errno
0x1800055ad  lea     r8, aCouldnTCreateT; "Couldn't create temporary file"
0x1800055b4  mov     edx, [rax]
0x1800055b6  mov     rcx, rbp
0x1800055b9  call    archive_set_error
0x1800055be  mov     eax, 0FFFFFFE2h
0x1800055c3  jmp     short loc_1800055F9
0x1800055c5  test    rdi, rdi
0x1800055c8  jz      short loc_1800055F7
0x1800055ca  mov     ecx, [rbx]
0x1800055cc  mov     r8, rdi
0x1800055cf  mov     rdx, rsi
0x1800055d2  call    __la_write
0x1800055d7  test    rax, rax
0x1800055da  js      short loc_1800055E8
0x1800055dc  sub     rdi, rax
0x1800055df  add     rsi, rax
0x1800055e2  add     [rbx+8], rax
0x1800055e6  jmp     short loc_1800055C5
0x1800055e8  call    cs:__imp__o__errno
0x1800055ee  lea     r8, aWriteFunctionF; "write function failed"
0x1800055f5  jmp     short loc_1800055B4
0x1800055f7  xor     eax, eax
0x1800055f9  add     rsp, 28h
0x1800055fd  pop     rdi
0x1800055fe  pop     rsi
0x1800055ff  pop     rbp
0x180005600  pop     rbx
0x180005601  retn
```
