# BaseSrvEqualVarNameMappings

- ea: `0x18000ce0c`
- end: `0x18000ce7c`
- name: `BaseSrvEqualVarNameMappings`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cd20`
- `0x18000ce0c`

## callees

- `0x18000ce0c`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000ce3a`
- `ntdll!RtlEqualUnicodeString` at `0x18000ce3a`

## pseudocode

```c
bool __fastcall BaseSrvEqualVarNameMappings(__int64 a1, __int64 a2)
{
  if ( a1 )
  {
    if ( a2
      && RtlEqualUnicodeString((PCUNICODE_STRING)(a1 + 8), (PCUNICODE_STRING)(a2 + 8), 1u)
      && *(_DWORD *)(a1 + 24) == *(_DWORD *)(a2 + 24)
      && *(_QWORD *)(a1 + 32) == *(_QWORD *)(a2 + 32) )
    {
      return (unsigned __int8)BaseSrvEqualVarNameMappings(*(_QWORD *)a1, *(_QWORD *)a2) != 0;
    }
  }
  else if ( !a2 )
  {
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce0c  mov     [rsp+arg_0], rbx
0x18000ce11  push    rdi
0x18000ce12  sub     rsp, 20h
0x18000ce16  mov     rbx, rdx
0x18000ce19  mov     rdi, rcx
0x18000ce1c  test    rcx, rcx
0x18000ce1f  jnz     short loc_18000CE2A
0x18000ce21  test    rdx, rdx
0x18000ce24  jnz     short loc_18000CE6E
0x18000ce26  mov     al, 1
0x18000ce28  jmp     short loc_18000CE70
0x18000ce2a  test    rbx, rbx
0x18000ce2d  jz      short loc_18000CE6E
0x18000ce2f  add     rdx, 8; String2
0x18000ce33  add     rcx, 8; String1
0x18000ce37  mov     r8b, 1; CaseInsensitive
0x18000ce3a  call    cs:__imp_RtlEqualUnicodeString
0x18000ce41  nop     dword ptr [rax+rax+00h]
0x18000ce46  test    al, al
0x18000ce48  jz      short loc_18000CE6E
0x18000ce4a  mov     eax, [rbx+18h]
0x18000ce4d  cmp     [rdi+18h], eax
0x18000ce50  jnz     short loc_18000CE6E
0x18000ce52  mov     rax, [rbx+20h]
0x18000ce56  cmp     [rdi+20h], rax
0x18000ce5a  jnz     short loc_18000CE6E
0x18000ce5c  mov     rdx, [rbx]
0x18000ce5f  mov     rcx, [rdi]
0x18000ce62  call    BaseSrvEqualVarNameMappings
0x18000ce67  test    al, al
0x18000ce69  setnz   al
0x18000ce6c  jmp     short loc_18000CE70
0x18000ce6e  xor     al, al
0x18000ce70  mov     rbx, [rsp+28h+arg_0]
0x18000ce75  add     rsp, 20h
0x18000ce79  pop     rdi
0x18000ce7a  retn
```
