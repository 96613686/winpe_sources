# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002cd8`
- end: `0x140002d50`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000667c`
- `0x1400067c8`

## callees

- `0x140002cd8`
- `0x140006558`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002d16`
- `msvcrt!memcpy_s` at `0x140002d16`

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
0x140002cd8  mov     [rsp+arg_0], rbx
0x140002cdd  mov     [rsp+arg_8], rsi
0x140002ce2  push    rdi
0x140002ce3  sub     rsp, 20h
0x140002ce7  mov     rbx, r9
0x140002cea  mov     rdi, rcx
0x140002ced  cmp     rcx, rdx
0x140002cf0  jz      short loc_140002D30
0x140002cf2  test    r8, r8
0x140002cf5  jz      short loc_140002D30
0x140002cf7  cmp     byte ptr [r8], 0
0x140002cfb  jz      short loc_140002D30
0x140002cfd  mov     rcx, r8; this
0x140002d00  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140002d05  sub     rdx, rdi; DestinationSize
0x140002d08  mov     rsi, rax
0x140002d0b  cmp     rdx, rax
0x140002d0e  jb      short loc_140002D30
0x140002d10  mov     r9, rax; SourceSize
0x140002d13  mov     rcx, rdi; Destination
0x140002d16  call    cs:__imp_memcpy_s
0x140002d1d  nop     dword ptr [rax+rax+00h]
0x140002d22  test    rbx, rbx
0x140002d25  jz      short loc_140002D2A
0x140002d27  mov     [rbx], rdi
0x140002d2a  lea     rax, [rsi+rdi]
0x140002d2e  jmp     short loc_140002D3F
0x140002d30  test    rbx, rbx
0x140002d33  jz      short loc_140002D3C
0x140002d35  mov     qword ptr [r9], 0
0x140002d3c  mov     rax, rdi
0x140002d3f  mov     rbx, [rsp+28h+arg_0]
0x140002d44  mov     rsi, [rsp+28h+arg_8]
0x140002d49  add     rsp, 20h
0x140002d4d  pop     rdi
0x140002d4e  retn
```
