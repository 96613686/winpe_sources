# stristr(char *,char *)

- ea: `0x180003100`
- end: `0x18000318b`
- name: `?stristr@@YAPEADPEAD0@Z`
- size: `139`
- prototype: `char *(char *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800014a0`

## callees

- `0x180003100`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18000312e`
- `KERNEL32!lstrlenA` at `0x18000312e`
- `ucrtbase_clr0400!_strnicmp` at `0x18000315f`
- `ucrtbase_clr0400!_strnicmp` at `0x18000315f`
- `ucrtbase_clr0400!tolower` at `0x180003122`
- `ucrtbase_clr0400!tolower` at `0x180003145`
- `ucrtbase_clr0400!tolower` at `0x180003122`
- `ucrtbase_clr0400!tolower` at `0x180003145`

## pseudocode

```c
char *__fastcall stristr(char *a1, char *a2)
{
  int v4; // esi
  int v5; // r14d

  v4 = (char)tolower(*a2);
  v5 = lstrlenA(a2) - 1;
  while ( tolower(*a1) != v4 )
  {
    if ( !*a1 )
      return 0;
LABEL_3:
    ++a1;
  }
  if ( *a1 )
  {
    if ( !_strnicmp(a1 + 1, a2 + 1, v5) )
      return a1;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180003100  mov     rax, rsp
0x180003103  mov     [rax+8], rbx
0x180003107  mov     [rax+10h], rbp
0x18000310b  mov     [rax+18h], rsi
0x18000310f  mov     [rax+20h], rdi
0x180003113  push    r14
0x180003115  sub     rsp, 20h
0x180003119  mov     rdi, rcx
0x18000311c  mov     rbp, rdx
0x18000311f  movsx   ecx, byte ptr [rdx]; C
0x180003122  call    cs:__imp_tolower
0x180003128  mov     rcx, rbp; lpString
0x18000312b  movsx   esi, al
0x18000312e  call    cs:__imp_lstrlenA
0x180003134  lea     r14d, [rax-1]
0x180003138  jmp     short loc_180003142
0x18000313a  cmp     byte ptr [rdi], 0
0x18000313d  jz      short loc_18000316E
0x18000313f  inc     rdi
0x180003142  movsx   ecx, byte ptr [rdi]; C
0x180003145  call    cs:__imp_tolower
0x18000314b  cmp     eax, esi
0x18000314d  jnz     short loc_18000313A
0x18000314f  cmp     byte ptr [rdi], 0
0x180003152  jz      short loc_18000316E
0x180003154  movsxd  r8, r14d; MaxCount
0x180003157  lea     rdx, [rbp+1]; String2
0x18000315b  lea     rcx, [rdi+1]; String1
0x18000315f  call    cs:__imp__strnicmp
0x180003165  test    eax, eax
0x180003167  jnz     short loc_18000313F
0x180003169  mov     rax, rdi
0x18000316c  jmp     short loc_180003170
0x18000316e  xor     eax, eax
0x180003170  mov     rbx, [rsp+28h+arg_0]
0x180003175  mov     rbp, [rsp+28h+arg_8]
0x18000317a  mov     rsi, [rsp+28h+arg_10]
0x18000317f  mov     rdi, [rsp+28h+arg_18]
0x180003184  add     rsp, 20h
0x180003188  pop     r14
0x18000318a  retn
```
