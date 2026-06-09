# std::_Yarn<char>::operator=(char const *)

- ea: `0x180031b64`
- end: `0x180031be1`
- name: `??4?$_Yarn@D@std@@QEAAAEAV01@PEBD@Z`
- size: `125`
- prototype: `void **__fastcall(void **, _BYTE *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180002458`
- `0x18000259c`
- `0x1800026d8`
- `0x1800027ac`
- `0x1800060cc`
- `0x18000915c`
- `0x18001cb44`
- `0x18003158c`

## callees

- `0x180026796`
- `0x180031b64`

## import_xrefs

- `msvcrt!malloc` at `0x180031bb2`
- `msvcrt!malloc` at `0x180031bb2`
- `msvcrt!free` at `0x180031b86`
- `msvcrt!free` at `0x180031b86`

## pseudocode

```c
void **__fastcall std::_Yarn<char>::operator=(void **a1, _BYTE *a2)
{
  _BYTE *v4; // rcx
  _BYTE *i; // rax
  size_t v6; // rsi
  void *v7; // rax

  v4 = *a1;
  if ( v4 != a2 )
  {
    if ( v4 )
      free(v4);
    *a1 = 0;
    if ( a2 )
    {
      for ( i = a2; *i; ++i )
        ;
      v6 = i - a2 + 1;
      v7 = malloc(v6);
      *a1 = v7;
      if ( v7 )
        memcpy_0(v7, a2, v6);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180031b64  mov     [rsp+arg_0], rbx
0x180031b69  mov     [rsp+arg_8], rsi
0x180031b6e  push    rdi
0x180031b6f  sub     rsp, 20h
0x180031b73  mov     rdi, rcx
0x180031b76  mov     rbx, rdx
0x180031b79  mov     rcx, [rcx]; Block
0x180031b7c  cmp     rcx, rdx
0x180031b7f  jz      short loc_180031BCE
0x180031b81  test    rcx, rcx
0x180031b84  jz      short loc_180031B8C
0x180031b86  call    cs:__imp_free
0x180031b8c  mov     qword ptr [rdi], 0
0x180031b93  test    rbx, rbx
0x180031b96  jz      short loc_180031BCE
0x180031b98  cmp     byte ptr [rbx], 0
0x180031b9b  mov     rax, rbx
0x180031b9e  jz      short loc_180031BA8
0x180031ba0  inc     rax
0x180031ba3  cmp     byte ptr [rax], 0
0x180031ba6  jnz     short loc_180031BA0
0x180031ba8  sub     rax, rbx
0x180031bab  lea     rsi, [rax+1]
0x180031baf  mov     rcx, rsi; Size
0x180031bb2  call    cs:__imp_malloc
0x180031bb8  mov     [rdi], rax
0x180031bbb  test    rax, rax
0x180031bbe  jz      short loc_180031BCE
0x180031bc0  mov     r8, rsi; Size
0x180031bc3  mov     rdx, rbx; Src
0x180031bc6  mov     rcx, rax; void *
0x180031bc9  call    memcpy_0
0x180031bce  mov     rbx, [rsp+28h+arg_0]
0x180031bd3  mov     rax, rdi
0x180031bd6  mov     rsi, [rsp+28h+arg_8]
0x180031bdb  add     rsp, 20h
0x180031bdf  pop     rdi
0x180031be0  retn
```
