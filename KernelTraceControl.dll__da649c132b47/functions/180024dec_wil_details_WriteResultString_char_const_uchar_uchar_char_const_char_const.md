# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180024dec`
- end: `0x180024e85`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f568`
- `0x1800206b0`

## callees

- `0x180024dec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180024e43`
- `msvcrt!memcpy_s` at `0x180024e43`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, __int64 a2, char *a3, _QWORD *a4)
{
  char *v4; // rax
  unsigned __int64 v7; // rbx
  __int64 v8; // rbx
  rsize_t v9; // rdx
  rsize_t v10; // rdi
  char *v11; // rax
  char v13; // [rsp+30h] [rbp+8h] BYREF

  v13 = 0;
  v4 = &v13;
  if ( a3 )
    v4 = a3;
  if ( v4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v4[v8] );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 1;
  }
  v9 = a2 - (_QWORD)a1;
  v10 = v9;
  if ( v7 < v9 )
    v10 = v7;
  memcpy_s(a1, v9, v4, v10);
  if ( a4 )
  {
    v11 = 0;
    if ( v10 > 1 )
      v11 = a1;
    *a4 = v11;
  }
  if ( v10 < v7 && v10 )
    a1[v10 - 1] = 0;
  return &a1[v10];
}

```

## disassembly

```asm
0x180024dec  mov     rax, rsp
0x180024def  mov     [rax+10h], rbx
0x180024df3  mov     [rax+18h], rsi
0x180024df7  mov     [rax+20h], rdi
0x180024dfb  push    r14
0x180024dfd  sub     rsp, 20h
0x180024e01  mov     byte ptr [rax+8], 0
0x180024e05  lea     rax, [rax+8]
0x180024e09  test    r8, r8
0x180024e0c  mov     r14, r9
0x180024e0f  mov     rsi, rcx
0x180024e12  cmovnz  rax, r8
0x180024e16  test    rax, rax
0x180024e19  jnz     short loc_180024E20
0x180024e1b  lea     ebx, [rax+1]
0x180024e1e  jmp     short loc_180024E30
0x180024e20  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024e24  inc     rbx
0x180024e27  cmp     byte ptr [rax+rbx], 0
0x180024e2b  jnz     short loc_180024E24
0x180024e2d  inc     rbx
0x180024e30  sub     rdx, rsi; DestinationSize
0x180024e33  mov     r8, rax; Source
0x180024e36  cmp     rbx, rdx
0x180024e39  mov     rdi, rdx
0x180024e3c  cmovb   rdi, rbx
0x180024e40  mov     r9, rdi; SourceSize
0x180024e43  call    cs:__imp_memcpy_s
0x180024e49  test    r14, r14
0x180024e4c  jz      short loc_180024E5B
0x180024e4e  xor     eax, eax
0x180024e50  cmp     rdi, 1
0x180024e54  cmova   rax, rsi
0x180024e58  mov     [r14], rax
0x180024e5b  cmp     rdi, rbx
0x180024e5e  jnb     short loc_180024E6B
0x180024e60  test    rdi, rdi
0x180024e63  jz      short loc_180024E6B
0x180024e65  xor     eax, eax
0x180024e67  mov     [rdi+rsi-1], al
0x180024e6b  mov     rbx, [rsp+28h+arg_8]
0x180024e70  lea     rax, [rdi+rsi]
0x180024e74  mov     rsi, [rsp+28h+arg_10]
0x180024e79  mov     rdi, [rsp+28h+arg_18]
0x180024e7e  add     rsp, 20h
0x180024e82  pop     r14
0x180024e84  retn
```
