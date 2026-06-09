# CMimeType::CopyMimeType(ushort * *)

- ea: `0x18000dd4c`
- end: `0x18000de16`
- name: `?CopyMimeType@CMimeType@@QEAAJPEAPEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(CMimeType *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018fb4`

## callees

- `0x18000dd4c`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ddeb`
- `msvcrt!wcscat_s` at `0x18000de00`
- `msvcrt!wcscat_s` at `0x18000ddeb`
- `msvcrt!wcscat_s` at `0x18000de00`
- `msvcrt!wcscpy_s` at `0x18000ddc3`
- `msvcrt!wcscpy_s` at `0x18000ddd8`
- `msvcrt!wcscpy_s` at `0x18000ddc3`
- `msvcrt!wcscpy_s` at `0x18000ddd8`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000dda1`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000dda1`

## pseudocode

```c
__int64 __fastcall CMimeType::CopyMimeType(CMimeType *this, unsigned __int16 **a2)
{
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  rsize_t v9; // rdi
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  const wchar_t *v12; // r8
  const wchar_t *v13; // r8

  if ( !a2 )
    return 1;
  v5 = *((_QWORD *)this + 4);
  LODWORD(v6) = 0;
  v7 = -1;
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
  }
  v8 = *((_QWORD *)this + 3);
  if ( v8 )
  {
    do
      ++v7;
    while ( *(_WORD *)(v8 + 2 * v7) );
    LODWORD(v6) = v7 + v6;
  }
  v9 = (unsigned int)(v6 + 2);
  v10 = (wchar_t *)AllocADsMem(2 * (int)v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  wcscpy_s(v10, v9, &psz);
  v12 = (const wchar_t *)*((_QWORD *)this + 4);
  if ( v12 )
    wcscpy_s(v11, v9, v12);
  wcscat_s(v11, v9, L",");
  v13 = (const wchar_t *)*((_QWORD *)this + 3);
  if ( v13 )
    wcscat_s(v11, v9, v13);
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x18000dd4c  push    rbx
0x18000dd4e  push    rbp
0x18000dd4f  push    rsi
0x18000dd50  push    rdi
0x18000dd51  push    r14
0x18000dd53  sub     rsp, 20h
0x18000dd57  xor     ebp, ebp
0x18000dd59  mov     r14, rdx
0x18000dd5c  mov     rsi, rcx
0x18000dd5f  test    rdx, rdx
0x18000dd62  jnz     short loc_18000DD6C
0x18000dd64  lea     eax, [rdx+1]
0x18000dd67  jmp     loc_18000DE0B
0x18000dd6c  mov     rdx, [rcx+20h]
0x18000dd70  mov     eax, ebp
0x18000dd72  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000dd76  test    rdx, rdx
0x18000dd79  jz      short loc_18000DD87
0x18000dd7b  mov     rax, rcx
0x18000dd7e  inc     rax
0x18000dd81  cmp     [rdx+rax*2], bp
0x18000dd85  jnz     short loc_18000DD7E
0x18000dd87  mov     rdx, [rsi+18h]
0x18000dd8b  test    rdx, rdx
0x18000dd8e  jz      short loc_18000DD9B
0x18000dd90  inc     rcx
0x18000dd93  cmp     [rdx+rcx*2], bp
0x18000dd97  jnz     short loc_18000DD90
0x18000dd99  add     eax, ecx
0x18000dd9b  lea     edi, [rax+2]
0x18000dd9e  lea     ecx, [rdi+rdi]; cb
0x18000dda1  call    cs:__imp_AllocADsMem
0x18000dda7  mov     rbx, rax
0x18000ddaa  test    rax, rax
0x18000ddad  jnz     short loc_18000DDB6
0x18000ddaf  mov     eax, 8007000Eh
0x18000ddb4  jmp     short loc_18000DE0B
0x18000ddb6  lea     r8, psz; Source
0x18000ddbd  mov     rdx, rdi; SizeInWords
0x18000ddc0  mov     rcx, rbx; Destination
0x18000ddc3  call    cs:__imp_wcscpy_s
0x18000ddc9  mov     r8, [rsi+20h]; Source
0x18000ddcd  test    r8, r8
0x18000ddd0  jz      short loc_18000DDDE
0x18000ddd2  mov     rdx, rdi; SizeInWords
0x18000ddd5  mov     rcx, rbx; Destination
0x18000ddd8  call    cs:__imp_wcscpy_s
0x18000ddde  lea     r8, Delimiter; ","
0x18000dde5  mov     rdx, rdi; SizeInWords
0x18000dde8  mov     rcx, rbx; Destination
0x18000ddeb  call    cs:__imp_wcscat_s
0x18000ddf1  mov     r8, [rsi+18h]; Source
0x18000ddf5  test    r8, r8
0x18000ddf8  jz      short loc_18000DE06
0x18000ddfa  mov     rdx, rdi; SizeInWords
0x18000ddfd  mov     rcx, rbx; Destination
0x18000de00  call    cs:__imp_wcscat_s
0x18000de06  mov     [r14], rbx
0x18000de09  mov     eax, ebp
0x18000de0b  add     rsp, 20h
0x18000de0f  pop     r14
0x18000de11  pop     rdi
0x18000de12  pop     rsi
0x18000de13  pop     rbp
0x18000de14  pop     rbx
0x18000de15  retn
```
