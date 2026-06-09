# PathMatches(char const *,char const *)

- ea: `0x180001430`
- end: `0x18000149e`
- name: `?PathMatches@@YAHPEBD0@Z`
- size: `110`
- prototype: `__int64 __fastcall(const char *String1, const char *String2)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000120c`
- `0x1800014a0`

## callees

- `0x180001430`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180001448`
- `KERNEL32!lstrlenA` at `0x180001448`
- `ucrtbase_clr0400!_strnicmp` at `0x18000145a`
- `ucrtbase_clr0400!_strnicmp` at `0x18000145a`
- `ucrtbase_clr0400!isspace` at `0x180001472`
- `ucrtbase_clr0400!isspace` at `0x180001472`

## pseudocode

```c
__int64 __fastcall PathMatches(const char *String1, const char *String2)
{
  size_t v4; // rsi
  const char *i; // rbx
  char v6; // cl

  v4 = lstrlenA(String2);
  if ( _strnicmp(String1, String2, v4) )
    return 0;
  for ( i = &String1[v4]; ; ++i )
  {
    v6 = *i;
    if ( !*i || v6 == 47 )
      break;
    if ( !isspace(v6) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001430  mov     [rsp+arg_0], rbx
0x180001435  mov     [rsp+arg_8], rsi
0x18000143a  push    rdi
0x18000143b  sub     rsp, 20h
0x18000143f  mov     rdi, rcx
0x180001442  mov     rbx, rdx
0x180001445  mov     rcx, rdx; lpString
0x180001448  call    cs:__imp_lstrlenA
0x18000144e  movsxd  rsi, eax
0x180001451  mov     rdx, rbx; String2
0x180001454  mov     r8, rsi; MaxCount
0x180001457  mov     rcx, rdi; String1
0x18000145a  call    cs:__imp__strnicmp
0x180001460  test    eax, eax
0x180001462  jnz     short loc_18000148C
0x180001464  lea     rbx, [rsi+rdi]
0x180001468  jmp     short loc_18000147F
0x18000146a  cmp     cl, 2Fh ; '/'
0x18000146d  jz      short loc_180001485
0x18000146f  movsx   ecx, cl; C
0x180001472  call    cs:__imp_isspace
0x180001478  test    eax, eax
0x18000147a  jz      short loc_18000148C
0x18000147c  inc     rbx
0x18000147f  mov     cl, [rbx]
0x180001481  test    cl, cl
0x180001483  jnz     short loc_18000146A
0x180001485  mov     eax, 1
0x18000148a  jmp     short loc_18000148E
0x18000148c  xor     eax, eax
0x18000148e  mov     rbx, [rsp+28h+arg_0]
0x180001493  mov     rsi, [rsp+28h+arg_8]
0x180001498  add     rsp, 20h
0x18000149c  pop     rdi
0x18000149d  retn
```
