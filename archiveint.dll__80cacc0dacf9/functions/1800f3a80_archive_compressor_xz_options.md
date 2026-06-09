# archive_compressor_xz_options

- ea: `0x1800f3a80`
- end: `0x1800f3b67`
- name: `archive_compressor_xz_options`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180026460`
- `0x1800f3a80`
- `0x180119956`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3b01`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3b24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3b01`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3b24`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1800f3b1b`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1800f3b1b`

## string_xrefs

- `0x1800f3a99`: `compression-level`
- `0x1800f3ae0`: `threads`

## pseudocode

```c
__int64 __fastcall archive_compressor_xz_options(__int64 a1, const char *a2, char *a3)
{
  int *v3; // rbx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  _BYTE *v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(int **)(a1 + 72);
  if ( !strcmp_0(a2, "compression-level") )
  {
    if ( a3 && (unsigned __int8)(*a3 - 48) <= 9u && !a3[1] )
    {
      v6 = *a3 - 48;
      *v3 = v6;
      if ( v6 > 9 )
        *v3 = 9;
      return 0;
    }
  }
  else if ( !strcmp_0(a2, "threads") )
  {
    v10 = 0;
    if ( a3 )
    {
      *(_DWORD *)_o__errno(v7) = 0;
      v3[1] = _o_strtoul(a3, &v10, 10);
      if ( !*(_DWORD *)_o__errno(v8) && !*v10 )
      {
        if ( !v3[1] )
          v3[1] = lzma_cputhreads();
        return 0;
      }
      v3[1] = 1;
    }
  }
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f3a80  mov     [rsp+arg_8], rbx
0x1800f3a85  mov     [rsp+arg_10], rsi
0x1800f3a8a  push    rdi
0x1800f3a8b  sub     rsp, 20h
0x1800f3a8f  mov     rbx, [rcx+48h]
0x1800f3a93  mov     rsi, rdx
0x1800f3a96  mov     rcx, rsi; Str1
0x1800f3a99  lea     rdx, aCompressionLev_0; "compression-level"
0x1800f3aa0  mov     rdi, r8
0x1800f3aa3  call    strcmp_0
0x1800f3aa8  test    eax, eax
0x1800f3aaa  jnz     short loc_1800F3AE0
0x1800f3aac  test    rdi, rdi
0x1800f3aaf  jz      loc_1800F3B52
0x1800f3ab5  mov     al, [rdi]
0x1800f3ab7  sub     al, 30h ; '0'
0x1800f3ab9  cmp     al, 9
0x1800f3abb  ja      loc_1800F3B52
0x1800f3ac1  cmp     byte ptr [rdi+1], 0
0x1800f3ac5  jnz     loc_1800F3B52
0x1800f3acb  movsx   eax, byte ptr [rdi]
0x1800f3ace  add     eax, 0FFFFFFD0h
0x1800f3ad1  mov     [rbx], eax
0x1800f3ad3  cmp     eax, 9
0x1800f3ad6  jle     short loc_1800F3B47
0x1800f3ad8  mov     dword ptr [rbx], 9
0x1800f3ade  jmp     short loc_1800F3B47
0x1800f3ae0  lea     rdx, aThreads; "threads"
0x1800f3ae7  mov     rcx, rsi; Str1
0x1800f3aea  call    strcmp_0
0x1800f3aef  test    eax, eax
0x1800f3af1  jnz     short loc_1800F3B52
0x1800f3af3  mov     [rsp+28h+arg_0], 0
0x1800f3afc  test    rdi, rdi
0x1800f3aff  jz      short loc_1800F3B52
0x1800f3b01  call    cs:__imp__o__errno
0x1800f3b07  mov     r8d, 0Ah
0x1800f3b0d  lea     rdx, [rsp+28h+arg_0]
0x1800f3b12  mov     rcx, rdi
0x1800f3b15  mov     dword ptr [rax], 0
0x1800f3b1b  call    cs:__imp__o_strtoul
0x1800f3b21  mov     [rbx+4], eax
0x1800f3b24  call    cs:__imp__o__errno
0x1800f3b2a  cmp     dword ptr [rax], 0
0x1800f3b2d  jnz     short loc_1800F3B4B
0x1800f3b2f  mov     rax, [rsp+28h+arg_0]
0x1800f3b34  cmp     byte ptr [rax], 0
0x1800f3b37  jnz     short loc_1800F3B4B
0x1800f3b39  cmp     dword ptr [rbx+4], 0
0x1800f3b3d  jnz     short loc_1800F3B47
0x1800f3b3f  call    lzma_cputhreads
0x1800f3b44  mov     [rbx+4], eax
0x1800f3b47  xor     eax, eax
0x1800f3b49  jmp     short loc_1800F3B57
0x1800f3b4b  mov     dword ptr [rbx+4], 1
0x1800f3b52  mov     eax, 0FFFFFFECh
0x1800f3b57  mov     rbx, [rsp+28h+arg_8]
0x1800f3b5c  mov     rsi, [rsp+28h+arg_10]
0x1800f3b61  add     rsp, 20h
0x1800f3b65  pop     rdi
0x1800f3b66  retn
```
