# la_CreateHardLinkW

- ea: `0x1800f6938`
- end: `0x1800f6a48`
- name: `la_CreateHardLinkW`
- size: `272`
- prototype: `__int64 __fastcall(wchar_t *String1, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1800f6098`

## callees

- `0x1800f6938`
- `0x18011997a`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6960`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6960`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800f6976`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800f6947`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800f6976`

## pseudocode

```c
int __fastcall la_CreateHardLinkW(wchar_t *String1, wchar_t *a2)
{
  wchar_t *v2; // rbx
  wchar_t *v3; // rdi
  int result; // eax

  v2 = a2;
  qword_180155C88 = (__int64)CreateHardLinkW;
  v3 = String1;
  if ( CreateHardLinkW )
  {
    result = CreateHardLinkW(String1, a2, 0);
    if ( !result )
    {
      if ( !wcsncmp_0(v3, L"\\\\?\\", 4u) )
      {
        v3 += 4;
        if ( ((*v3 - 85) & 0xFFDF) == 0 && ((v3[1] - 78) & 0xFFDF) == 0 && ((v3[2] - 67) & 0xFFDF) == 0 && v3[3] == 92 )
          v3 += 4;
      }
      if ( !wcsncmp_0(v2, L"\\\\?\\", 4u) )
      {
        v2 += 4;
        if ( ((*v2 - 85) & 0xFFDF) == 0 && ((v2[1] - 78) & 0xFFDF) == 0 && ((v2[2] - 67) & 0xFFDF) == 0 && v2[3] == 92 )
          v2 += 4;
      }
      return ((__int64 (__fastcall *)(wchar_t *, wchar_t *, _QWORD))qword_180155C88)(v3, v2, 0);
    }
  }
  else
  {
    *(_DWORD *)_o__errno() = 129;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800f6938  mov     [rsp+arg_0], rbx
0x1800f693d  mov     [rsp+arg_8], rsi
0x1800f6942  push    rdi
0x1800f6943  sub     rsp, 20h
0x1800f6947  mov     rax, cs:__imp_CreateHardLinkW
0x1800f694e  mov     rbx, rdx
0x1800f6951  mov     cs:qword_180155C88, rax
0x1800f6958  mov     rdi, rcx
0x1800f695b  test    rax, rax
0x1800f695e  jnz     short loc_1800F6973
0x1800f6960  call    cs:__imp__o__errno
0x1800f6966  mov     dword ptr [rax], 81h
0x1800f696c  xor     eax, eax
0x1800f696e  jmp     loc_1800F6A38
0x1800f6973  xor     r8d, r8d; lpSecurityAttributes
0x1800f6976  call    cs:__imp_CreateHardLinkW
0x1800f697c  test    eax, eax
0x1800f697e  jnz     loc_1800F6A38
0x1800f6984  lea     r8d, [rax+4]; MaxCount
0x1800f6988  mov     rcx, rdi; String1
0x1800f698b  lea     rdx, Source; "\\\\?\\"
0x1800f6992  call    wcsncmp_0
0x1800f6997  mov     esi, 0FFDFh
0x1800f699c  test    eax, eax
0x1800f699e  jnz     short loc_1800F69D5
0x1800f69a0  add     rdi, 8
0x1800f69a4  movzx   eax, word ptr [rdi]
0x1800f69a7  sub     ax, 55h ; 'U'
0x1800f69ab  test    si, ax
0x1800f69ae  jnz     short loc_1800F69D5
0x1800f69b0  movzx   eax, word ptr [rdi+2]
0x1800f69b4  sub     ax, 4Eh ; 'N'
0x1800f69b8  test    si, ax
0x1800f69bb  jnz     short loc_1800F69D5
0x1800f69bd  movzx   eax, word ptr [rdi+4]
0x1800f69c1  sub     ax, 43h ; 'C'
0x1800f69c5  test    si, ax
0x1800f69c8  jnz     short loc_1800F69D5
0x1800f69ca  cmp     word ptr [rdi+6], 5Ch ; '\'
0x1800f69cf  jnz     short loc_1800F69D5
0x1800f69d1  add     rdi, 8
0x1800f69d5  mov     r8d, 4; MaxCount
0x1800f69db  lea     rdx, Source; "\\\\?\\"
0x1800f69e2  mov     rcx, rbx; String1
0x1800f69e5  call    wcsncmp_0
0x1800f69ea  test    eax, eax
0x1800f69ec  jnz     short loc_1800F6A23
0x1800f69ee  add     rbx, 8
0x1800f69f2  movzx   eax, word ptr [rbx]
0x1800f69f5  sub     ax, 55h ; 'U'
0x1800f69f9  test    si, ax
0x1800f69fc  jnz     short loc_1800F6A23
0x1800f69fe  movzx   eax, word ptr [rbx+2]
0x1800f6a02  sub     ax, 4Eh ; 'N'
0x1800f6a06  test    si, ax
0x1800f6a09  jnz     short loc_1800F6A23
0x1800f6a0b  movzx   eax, word ptr [rbx+4]
0x1800f6a0f  sub     ax, 43h ; 'C'
0x1800f6a13  test    si, ax
0x1800f6a16  jnz     short loc_1800F6A23
0x1800f6a18  cmp     word ptr [rbx+6], 5Ch ; '\'
0x1800f6a1d  jnz     short loc_1800F6A23
0x1800f6a1f  add     rbx, 8
0x1800f6a23  mov     rax, cs:qword_180155C88
0x1800f6a2a  xor     r8d, r8d
0x1800f6a2d  mov     rdx, rbx
0x1800f6a30  mov     rcx, rdi
0x1800f6a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6a38  mov     rbx, [rsp+28h+arg_0]
0x1800f6a3d  mov     rsi, [rsp+28h+arg_8]
0x1800f6a42  add     rsp, 20h
0x1800f6a46  pop     rdi
0x1800f6a47  retn
```
