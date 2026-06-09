# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002b40`
- end: `0x180002bb8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e6c`
- `0x180004fb8`

## callees

- `0x180002b40`
- `0x180004d58`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002b7e`
- `msvcrt!memcpy_s` at `0x180002b7e`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x180002b40  mov     [rsp+arg_0], rbx
0x180002b45  mov     [rsp+arg_8], rsi
0x180002b4a  push    rdi
0x180002b4b  sub     rsp, 20h
0x180002b4f  mov     rbx, r9
0x180002b52  mov     rdi, rcx
0x180002b55  cmp     rcx, rdx
0x180002b58  jz      short loc_180002B98
0x180002b5a  test    r8, r8
0x180002b5d  jz      short loc_180002B98
0x180002b5f  cmp     byte ptr [r8], 0
0x180002b63  jz      short loc_180002B98
0x180002b65  mov     rcx, r8; this
0x180002b68  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002b6d  sub     rdx, rdi; DestinationSize
0x180002b70  mov     rsi, rax
0x180002b73  cmp     rdx, rax
0x180002b76  jb      short loc_180002B98
0x180002b78  mov     r9, rax; SourceSize
0x180002b7b  mov     rcx, rdi; Destination
0x180002b7e  call    cs:__imp_memcpy_s
0x180002b85  nop     dword ptr [rax+rax+00h]
0x180002b8a  test    rbx, rbx
0x180002b8d  jz      short loc_180002B92
0x180002b8f  mov     [rbx], rdi
0x180002b92  lea     rax, [rsi+rdi]
0x180002b96  jmp     short loc_180002BA7
0x180002b98  test    rbx, rbx
0x180002b9b  jz      short loc_180002BA4
0x180002b9d  mov     qword ptr [r9], 0
0x180002ba4  mov     rax, rdi
0x180002ba7  mov     rbx, [rsp+28h+arg_0]
0x180002bac  mov     rsi, [rsp+28h+arg_8]
0x180002bb1  add     rsp, 20h
0x180002bb5  pop     rdi
0x180002bb6  retn
```
