# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004d60`
- end: `0x180004dd0`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d40`
- `0x180006e7c`

## callees

- `0x180004d60`
- `0x180006c08`
- `0x180007b30`

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
0x180004d60  mov     [rsp+arg_0], rbx
0x180004d65  mov     [rsp+arg_8], rsi
0x180004d6a  push    rdi
0x180004d6b  sub     rsp, 20h
0x180004d6f  mov     rbx, r9
0x180004d72  mov     rdi, rcx
0x180004d75  cmp     rcx, rdx
0x180004d78  jz      short loc_180004DB1
0x180004d7a  test    r8, r8
0x180004d7d  jz      short loc_180004DB1
0x180004d7f  cmp     byte ptr [r8], 0
0x180004d83  jz      short loc_180004DB1
0x180004d85  mov     rcx, r8; this
0x180004d88  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004d8d  sub     rdx, rdi; DestinationSize
0x180004d90  mov     rsi, rax
0x180004d93  cmp     rdx, rax
0x180004d96  jb      short loc_180004DB1
0x180004d98  mov     r9, rax; SourceSize
0x180004d9b  mov     rcx, rdi; Destination
0x180004d9e  call    memcpy_s
0x180004da3  test    rbx, rbx
0x180004da6  jz      short loc_180004DAB
0x180004da8  mov     [rbx], rdi
0x180004dab  lea     rax, [rsi+rdi]
0x180004daf  jmp     short loc_180004DC0
0x180004db1  test    rbx, rbx
0x180004db4  jz      short loc_180004DBD
0x180004db6  mov     qword ptr [r9], 0
0x180004dbd  mov     rax, rdi
0x180004dc0  mov     rbx, [rsp+28h+arg_0]
0x180004dc5  mov     rsi, [rsp+28h+arg_8]
0x180004dca  add     rsp, 20h
0x180004dce  pop     rdi
0x180004dcf  retn
```
