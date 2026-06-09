# BaseSrvEqualAppNameMappings

- ea: `0x18000c93c`
- end: `0x18000c9bc`
- name: `BaseSrvEqualAppNameMappings`
- size: `128`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c93c`
- `0x18000c9c4`

## callees

- `0x18000c93c`
- `0x18000ca28`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000c96a`
- `ntdll!RtlEqualUnicodeString` at `0x18000c96a`

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
0x18000c93c  mov     [rsp+arg_0], rbx
0x18000c941  push    rdi
0x18000c942  sub     rsp, 20h
0x18000c946  mov     rbx, rdx
0x18000c949  mov     rdi, rcx
0x18000c94c  test    rcx, rcx
0x18000c94f  jnz     short loc_18000C95A
0x18000c951  test    rdx, rdx
0x18000c954  jnz     short loc_18000C9AE
0x18000c956  mov     al, 1
0x18000c958  jmp     short loc_18000C9B0
0x18000c95a  test    rbx, rbx
0x18000c95d  jz      short loc_18000C9AE
0x18000c95f  add     rdx, 8; String2
0x18000c963  add     rcx, 8; String1
0x18000c967  mov     r8b, 1; CaseInsensitive
0x18000c96a  call    cs:__imp_RtlEqualUnicodeString
0x18000c971  nop     dword ptr [rax+rax+00h]
0x18000c976  test    al, al
0x18000c978  jz      short loc_18000C9AE
0x18000c97a  mov     rdx, [rbx+18h]
0x18000c97e  mov     rcx, [rdi+18h]
0x18000c982  call    BaseSrvEqualVarNameMappings
0x18000c987  test    al, al
0x18000c989  jz      short loc_18000C9AE
0x18000c98b  mov     rdx, [rbx+20h]
0x18000c98f  mov     rcx, [rdi+20h]
0x18000c993  call    BaseSrvEqualVarNameMappings
0x18000c998  test    al, al
0x18000c99a  jz      short loc_18000C9AE
0x18000c99c  mov     rdx, [rbx]
0x18000c99f  mov     rcx, [rdi]
0x18000c9a2  call    BaseSrvEqualAppNameMappings
0x18000c9a7  test    al, al
0x18000c9a9  setnz   al
0x18000c9ac  jmp     short loc_18000C9B0
0x18000c9ae  xor     al, al
0x18000c9b0  mov     rbx, [rsp+28h+arg_0]
0x18000c9b5  add     rsp, 20h
0x18000c9b9  pop     rdi
0x18000c9ba  retn
```
