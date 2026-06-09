# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800111c0`
- end: `0x180011228`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014850`
- `0x180014a7c`

## callees

- `0x1800111c0`
- `0x1800146e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011200`
- `msvcrt!memcpy_s` at `0x180011200`

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
0x1800111c0  push    rbx
0x1800111c2  push    rbp
0x1800111c3  push    rsi
0x1800111c4  push    rdi
0x1800111c5  sub     rsp, 28h
0x1800111c9  xor     ebp, ebp
0x1800111cb  mov     rbx, r9
0x1800111ce  mov     r10, rdx
0x1800111d1  mov     rdi, rcx
0x1800111d4  cmp     rcx, rdx
0x1800111d7  jz      short loc_180011214
0x1800111d9  test    r8, r8
0x1800111dc  jz      short loc_180011214
0x1800111de  cmp     [r8], bp
0x1800111e2  jz      short loc_180011214
0x1800111e4  mov     rcx, r8; this
0x1800111e7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800111ec  sub     r10, rdi
0x1800111ef  mov     rsi, rax
0x1800111f2  cmp     r10, rax
0x1800111f5  jb      short loc_180011214
0x1800111f7  mov     r9, rax; SourceSize
0x1800111fa  mov     rdx, r10; DestinationSize
0x1800111fd  mov     rcx, rdi; Destination
0x180011200  call    cs:__imp_memcpy_s
0x180011206  test    rbx, rbx
0x180011209  jz      short loc_18001120E
0x18001120b  mov     [rbx], rdi
0x18001120e  lea     rax, [rsi+rdi]
0x180011212  jmp     short loc_18001121F
0x180011214  test    rbx, rbx
0x180011217  jz      short loc_18001121C
0x180011219  mov     [r9], rbp
0x18001121c  mov     rax, rdi
0x18001121f  add     rsp, 28h
0x180011223  pop     rdi
0x180011224  pop     rsi
0x180011225  pop     rbp
0x180011226  pop     rbx
0x180011227  retn
```
