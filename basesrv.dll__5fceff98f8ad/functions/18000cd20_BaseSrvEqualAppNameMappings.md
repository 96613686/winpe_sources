# BaseSrvEqualAppNameMappings

- ea: `0x18000cd20`
- end: `0x18000cda0`
- name: `BaseSrvEqualAppNameMappings`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cd20`
- `0x18000cda8`

## callees

- `0x18000cd20`
- `0x18000ce0c`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000cd4e`
- `ntdll!RtlEqualUnicodeString` at `0x18000cd4e`

## pseudocode

```c
bool __fastcall BaseSrvEqualAppNameMappings(__int64 a1, __int64 a2)
{
  if ( a1 )
  {
    if ( a2
      && RtlEqualUnicodeString((PCUNICODE_STRING)(a1 + 8), (PCUNICODE_STRING)(a2 + 8), 1u)
      && (unsigned __int8)BaseSrvEqualVarNameMappings(*(_QWORD *)(a1 + 24), *(_QWORD *)(a2 + 24))
      && (unsigned __int8)BaseSrvEqualVarNameMappings(*(_QWORD *)(a1 + 32), *(_QWORD *)(a2 + 32)) )
    {
      return (unsigned __int8)BaseSrvEqualAppNameMappings(*(_QWORD *)a1, *(_QWORD *)a2) != 0;
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
0x18000cd20  mov     [rsp+arg_0], rbx
0x18000cd25  push    rdi
0x18000cd26  sub     rsp, 20h
0x18000cd2a  mov     rbx, rdx
0x18000cd2d  mov     rdi, rcx
0x18000cd30  test    rcx, rcx
0x18000cd33  jnz     short loc_18000CD3E
0x18000cd35  test    rdx, rdx
0x18000cd38  jnz     short loc_18000CD92
0x18000cd3a  mov     al, 1
0x18000cd3c  jmp     short loc_18000CD94
0x18000cd3e  test    rbx, rbx
0x18000cd41  jz      short loc_18000CD92
0x18000cd43  add     rdx, 8; String2
0x18000cd47  add     rcx, 8; String1
0x18000cd4b  mov     r8b, 1; CaseInsensitive
0x18000cd4e  call    cs:__imp_RtlEqualUnicodeString
0x18000cd55  nop     dword ptr [rax+rax+00h]
0x18000cd5a  test    al, al
0x18000cd5c  jz      short loc_18000CD92
0x18000cd5e  mov     rdx, [rbx+18h]
0x18000cd62  mov     rcx, [rdi+18h]
0x18000cd66  call    BaseSrvEqualVarNameMappings
0x18000cd6b  test    al, al
0x18000cd6d  jz      short loc_18000CD92
0x18000cd6f  mov     rdx, [rbx+20h]
0x18000cd73  mov     rcx, [rdi+20h]
0x18000cd77  call    BaseSrvEqualVarNameMappings
0x18000cd7c  test    al, al
0x18000cd7e  jz      short loc_18000CD92
0x18000cd80  mov     rdx, [rbx]
0x18000cd83  mov     rcx, [rdi]
0x18000cd86  call    BaseSrvEqualAppNameMappings
0x18000cd8b  test    al, al
0x18000cd8d  setnz   al
0x18000cd90  jmp     short loc_18000CD94
0x18000cd92  xor     al, al
0x18000cd94  mov     rbx, [rsp+28h+arg_0]
0x18000cd99  add     rsp, 20h
0x18000cd9d  pop     rdi
0x18000cd9e  retn
```
