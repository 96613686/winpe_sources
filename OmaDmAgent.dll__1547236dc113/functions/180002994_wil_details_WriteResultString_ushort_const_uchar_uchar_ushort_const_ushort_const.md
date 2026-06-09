# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002994`
- end: `0x180002a03`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000549c`
- `0x1800055e8`

## callees

- `0x180002994`
- `0x1800053cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800029d4`
- `msvcrt!memcpy_s` at `0x1800029d4`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x180002994  push    rbx
0x180002996  push    rbp
0x180002997  push    rsi
0x180002998  push    rdi
0x180002999  sub     rsp, 28h
0x18000299d  xor     ebp, ebp
0x18000299f  mov     rbx, r9
0x1800029a2  mov     r10, rdx
0x1800029a5  mov     rdi, rcx
0x1800029a8  cmp     rcx, rdx
0x1800029ab  jz      short loc_1800029EE
0x1800029ad  test    r8, r8
0x1800029b0  jz      short loc_1800029EE
0x1800029b2  cmp     [r8], bp
0x1800029b6  jz      short loc_1800029EE
0x1800029b8  mov     rcx, r8; this
0x1800029bb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800029c0  sub     r10, rdi
0x1800029c3  mov     rsi, rax
0x1800029c6  cmp     r10, rax
0x1800029c9  jb      short loc_1800029EE
0x1800029cb  mov     r9, rax; SourceSize
0x1800029ce  mov     rdx, r10; DestinationSize
0x1800029d1  mov     rcx, rdi; Destination
0x1800029d4  call    cs:__imp_memcpy_s
0x1800029db  nop     dword ptr [rax+rax+00h]
0x1800029e0  test    rbx, rbx
0x1800029e3  jz      short loc_1800029E8
0x1800029e5  mov     [rbx], rdi
0x1800029e8  lea     rax, [rsi+rdi]
0x1800029ec  jmp     short loc_1800029F9
0x1800029ee  test    rbx, rbx
0x1800029f1  jz      short loc_1800029F6
0x1800029f3  mov     [r9], rbp
0x1800029f6  mov     rax, rdi
0x1800029f9  add     rsp, 28h
0x1800029fd  pop     rdi
0x1800029fe  pop     rsi
0x1800029ff  pop     rbp
0x180002a00  pop     rbx
0x180002a01  retn
```
