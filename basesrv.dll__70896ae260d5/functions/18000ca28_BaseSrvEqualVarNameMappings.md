# BaseSrvEqualVarNameMappings

- ea: `0x18000ca28`
- end: `0x18000ca98`
- name: `BaseSrvEqualVarNameMappings`
- size: `112`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c93c`
- `0x18000ca28`

## callees

- `0x18000ca28`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000ca56`
- `ntdll!RtlEqualUnicodeString` at `0x18000ca56`

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
0x18000ca28  mov     [rsp+arg_0], rbx
0x18000ca2d  push    rdi
0x18000ca2e  sub     rsp, 20h
0x18000ca32  mov     rbx, rdx
0x18000ca35  mov     rdi, rcx
0x18000ca38  test    rcx, rcx
0x18000ca3b  jnz     short loc_18000CA46
0x18000ca3d  test    rdx, rdx
0x18000ca40  jnz     short loc_18000CA8A
0x18000ca42  mov     al, 1
0x18000ca44  jmp     short loc_18000CA8C
0x18000ca46  test    rbx, rbx
0x18000ca49  jz      short loc_18000CA8A
0x18000ca4b  add     rdx, 8; String2
0x18000ca4f  add     rcx, 8; String1
0x18000ca53  mov     r8b, 1; CaseInsensitive
0x18000ca56  call    cs:__imp_RtlEqualUnicodeString
0x18000ca5d  nop     dword ptr [rax+rax+00h]
0x18000ca62  test    al, al
0x18000ca64  jz      short loc_18000CA8A
0x18000ca66  mov     eax, [rbx+18h]
0x18000ca69  cmp     [rdi+18h], eax
0x18000ca6c  jnz     short loc_18000CA8A
0x18000ca6e  mov     rax, [rbx+20h]
0x18000ca72  cmp     [rdi+20h], rax
0x18000ca76  jnz     short loc_18000CA8A
0x18000ca78  mov     rdx, [rbx]
0x18000ca7b  mov     rcx, [rdi]
0x18000ca7e  call    BaseSrvEqualVarNameMappings
0x18000ca83  test    al, al
0x18000ca85  setnz   al
0x18000ca88  jmp     short loc_18000CA8C
0x18000ca8a  xor     al, al
0x18000ca8c  mov     rbx, [rsp+28h+arg_0]
0x18000ca91  add     rsp, 20h
0x18000ca95  pop     rdi
0x18000ca96  retn
```
