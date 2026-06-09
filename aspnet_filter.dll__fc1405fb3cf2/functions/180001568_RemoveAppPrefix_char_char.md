# RemoveAppPrefix(char *,char *)

- ea: `0x180001568`
- end: `0x1800015e6`
- name: `?RemoveAppPrefix@@YAPEADPEAD0@Z`
- size: `126`
- prototype: `char *__fastcall(char *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000120c`

## callees

- `0x180001568`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800015d9`
- `KERNEL32!lstrlenA` at `0x1800015d9`
- `ucrtbase_clr0400!_strnicmp` at `0x180001588`
- `ucrtbase_clr0400!_strnicmp` at `0x1800015cb`
- `ucrtbase_clr0400!_strnicmp` at `0x180001588`
- `ucrtbase_clr0400!_strnicmp` at `0x1800015cb`
- `ucrtbase_clr0400!isdigit` at `0x1800015a3`
- `ucrtbase_clr0400!isdigit` at `0x1800015a3`

## pseudocode

```c
char *__fastcall RemoveAppPrefix(char *a1, char *a2)
{
  char *v4; // rbx

  if ( !_strnicmp(a2, "/LM/W3SVC/", 0xAu) )
  {
    v4 = a2 + 10;
    while ( isdigit((unsigned __int8)*v4) )
    {
      if ( *++v4 == 47 )
      {
        if ( _strnicmp(v4 + 1, "ROOT", 4u) )
          return 0;
        return &a1[lstrlenA(v4 + 5)];
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001568  mov     [rsp+arg_0], rbx
0x18000156d  push    rdi
0x18000156e  sub     rsp, 20h
0x180001572  mov     rbx, rdx
0x180001575  mov     rdi, rcx
0x180001578  mov     rcx, rbx; String1
0x18000157b  lea     rdx, String2; "/LM/W3SVC/"
0x180001582  mov     r8d, 0Ah; MaxCount
0x180001588  call    cs:__imp__strnicmp
0x18000158e  test    eax, eax
0x180001590  jnz     short loc_1800015AD
0x180001592  add     rbx, 0Ah
0x180001596  jmp     short loc_1800015A0
0x180001598  inc     rbx
0x18000159b  cmp     byte ptr [rbx], 2Fh ; '/'
0x18000159e  jz      short loc_1800015BA
0x1800015a0  movzx   ecx, byte ptr [rbx]; C
0x1800015a3  call    cs:__imp_isdigit
0x1800015a9  test    eax, eax
0x1800015ab  jnz     short loc_180001598
0x1800015ad  xor     eax, eax
0x1800015af  mov     rbx, [rsp+28h+arg_0]
0x1800015b4  add     rsp, 20h
0x1800015b8  pop     rdi
0x1800015b9  retn
0x1800015ba  mov     r8d, 4; MaxCount
0x1800015c0  lea     rdx, aRoot_0; "ROOT"
0x1800015c7  lea     rcx, [rbx+1]; String1
0x1800015cb  call    cs:__imp__strnicmp
0x1800015d1  test    eax, eax
0x1800015d3  jnz     short loc_1800015AD
0x1800015d5  lea     rcx, [rbx+5]; lpString
0x1800015d9  call    cs:__imp_lstrlenA
0x1800015df  cdqe
0x1800015e1  add     rax, rdi
0x1800015e4  jmp     short loc_1800015AF
```
