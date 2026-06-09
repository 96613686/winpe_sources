# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x14000740c`
- end: `0x140007474`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000c038`
- `0x14000c250`

## callees

- `0x14000740c`
- `0x14000be0c`

## import_xrefs

- `ntdll!memcpy_s` at `0x14000744c`
- `ntdll!memcpy_s` at `0x14000744c`

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
0x14000740c  push    rbx
0x14000740e  push    rbp
0x14000740f  push    rsi
0x140007410  push    rdi
0x140007411  sub     rsp, 28h
0x140007415  xor     ebp, ebp
0x140007417  mov     rbx, r9
0x14000741a  mov     r10, rdx
0x14000741d  mov     rdi, rcx
0x140007420  cmp     rcx, rdx
0x140007423  jz      short loc_140007460
0x140007425  test    r8, r8
0x140007428  jz      short loc_140007460
0x14000742a  cmp     [r8], bp
0x14000742e  jz      short loc_140007460
0x140007430  mov     rcx, r8; this
0x140007433  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140007438  sub     r10, rdi
0x14000743b  mov     rsi, rax
0x14000743e  cmp     r10, rax
0x140007441  jb      short loc_140007460
0x140007443  mov     r9, rax; SourceSize
0x140007446  mov     rdx, r10; DestinationSize
0x140007449  mov     rcx, rdi; Destination
0x14000744c  call    cs:__imp_memcpy_s
0x140007452  test    rbx, rbx
0x140007455  jz      short loc_14000745A
0x140007457  mov     [rbx], rdi
0x14000745a  lea     rax, [rsi+rdi]
0x14000745e  jmp     short loc_14000746B
0x140007460  test    rbx, rbx
0x140007463  jz      short loc_140007468
0x140007465  mov     [r9], rbp
0x140007468  mov     rax, rdi
0x14000746b  add     rsp, 28h
0x14000746f  pop     rdi
0x140007470  pop     rsi
0x140007471  pop     rbp
0x140007472  pop     rbx
0x140007473  retn
```
