# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000f994`
- end: `0x18000fa04`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010f0c`

## callees

- `0x18000a182`
- `0x18000f994`
- `0x180010e80`

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
0x18000f994  mov     [rsp+arg_0], rbx
0x18000f999  mov     [rsp+arg_8], rsi
0x18000f99e  push    rdi
0x18000f99f  sub     rsp, 20h
0x18000f9a3  mov     rbx, r9
0x18000f9a6  mov     rdi, rcx
0x18000f9a9  cmp     rcx, rdx
0x18000f9ac  jz      short loc_18000F9E5
0x18000f9ae  test    r8, r8
0x18000f9b1  jz      short loc_18000F9E5
0x18000f9b3  cmp     byte ptr [r8], 0
0x18000f9b7  jz      short loc_18000F9E5
0x18000f9b9  mov     rcx, r8; this
0x18000f9bc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f9c1  sub     rdx, rdi; DestinationSize
0x18000f9c4  mov     rsi, rax
0x18000f9c7  cmp     rdx, rax
0x18000f9ca  jb      short loc_18000F9E5
0x18000f9cc  mov     r9, rax; SourceSize
0x18000f9cf  mov     rcx, rdi; Destination
0x18000f9d2  call    memcpy_s
0x18000f9d7  test    rbx, rbx
0x18000f9da  jz      short loc_18000F9DF
0x18000f9dc  mov     [rbx], rdi
0x18000f9df  lea     rax, [rsi+rdi]
0x18000f9e3  jmp     short loc_18000F9F4
0x18000f9e5  test    rbx, rbx
0x18000f9e8  jz      short loc_18000F9F1
0x18000f9ea  mov     qword ptr [r9], 0
0x18000f9f1  mov     rax, rdi
0x18000f9f4  mov     rbx, [rsp+28h+arg_0]
0x18000f9f9  mov     rsi, [rsp+28h+arg_8]
0x18000f9fe  add     rsp, 20h
0x18000fa02  pop     rdi
0x18000fa03  retn
```
