# la_CreateFile

- ea: `0x1800ef930`
- end: `0x1800ef9e8`
- name: `la_CreateFile`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800ef1c8`

## callees

- `0x1800ef374`
- `0x1800ef930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef9ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef9ce`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ef969`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ef969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef975`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800ef9c2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800ef9c2`

## pseudocode

```c
__int64 __fastcall la_CreateFile(const CHAR *a1)
{
  __int64 result; // rax
  void *v3; // rdi
  __int64 v4; // rbx
  __int128 v5; // [rsp+40h] [rbp-28h] BYREF
  __int128 v6; // [rsp+50h] [rbp-18h]

  v5 = 0;
  v6 = 0;
  result = (__int64)CreateFileA(a1, 0, 1u, 0, 3u, 0x2000000u, 0);
  if ( result == -1 )
  {
    if ( GetLastError() == 3 && (v3 = (void *)_la_win_permissive_name(a1)) != 0 )
    {
      *(_QWORD *)&v5 = 32;
      *((_QWORD *)&v5 + 1) = 0x2000000;
      v6 = 0;
      v4 = CreateFile2(v3, 0, 1, 3, &v5);
      free(v3);
      return v4;
    }
    else
    {
      return -1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ef930  mov     rax, rsp
0x1800ef933  mov     [rax+8], rbx
0x1800ef937  push    rdi
0x1800ef938  sub     rsp, 60h
0x1800ef93c  xorps   xmm0, xmm0
0x1800ef93f  mov     qword ptr [rax-38h], 0
0x1800ef947  xor     r9d, r9d; lpSecurityAttributes
0x1800ef94a  mov     dword ptr [rax-40h], 2000000h
0x1800ef951  xor     edx, edx; dwDesiredAccess
0x1800ef953  mov     dword ptr [rax-48h], 3
0x1800ef95a  mov     rbx, rcx
0x1800ef95d  movups  xmmword ptr [rax-28h], xmm0
0x1800ef961  lea     r8d, [r9+1]; dwShareMode
0x1800ef965  movups  xmmword ptr [rax-18h], xmm0
0x1800ef969  call    cs:__imp_CreateFileA
0x1800ef96f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ef973  jnz     short loc_1800EF9DD
0x1800ef975  call    cs:__imp_GetLastError
0x1800ef97b  cmp     eax, 3
0x1800ef97e  jnz     short loc_1800EF9D9
0x1800ef980  mov     rcx, rbx
0x1800ef983  call    __la_win_permissive_name
0x1800ef988  mov     rdi, rax
0x1800ef98b  test    rax, rax
0x1800ef98e  jz      short loc_1800EF9D9
0x1800ef990  xor     edx, edx
0x1800ef992  mov     [rsp+68h+var_28], 20h ; ' '
0x1800ef99b  xorps   xmm0, xmm0
0x1800ef99e  mov     [rsp+68h+var_20], 2000000h
0x1800ef9a7  lea     rax, [rsp+68h+var_28]
0x1800ef9ac  mov     rcx, rdi
0x1800ef9af  movdqu  [rsp+68h+var_18], xmm0
0x1800ef9b5  lea     r9d, [rdx+3]
0x1800ef9b9  mov     [rsp+68h+var_48], rax
0x1800ef9be  lea     r8d, [rdx+1]
0x1800ef9c2  call    cs:__imp_CreateFile2
0x1800ef9c8  mov     rcx, rdi; Block
0x1800ef9cb  mov     rbx, rax
0x1800ef9ce  call    cs:__imp_free
0x1800ef9d4  mov     rax, rbx
0x1800ef9d7  jmp     short loc_1800EF9DD
0x1800ef9d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef9dd  mov     rbx, [rsp+68h+arg_0]
0x1800ef9e2  add     rsp, 60h
0x1800ef9e6  pop     rdi
0x1800ef9e7  retn
```
