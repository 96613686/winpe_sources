# AslRegistryBuildUserPath

- ea: `0x14003c470`
- end: `0x14003c565`
- name: `AslRegistryBuildUserPath`
- size: `245`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14003c618`

## callees

- `0x14003bf18`
- `0x14003c470`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x14003c552`
- `ntdll!RtlFreeUnicodeString` at `0x14003c552`
- `ntdll!RtlAllocateHeap` at `0x14003c4ff`
- `ntdll!RtlAllocateHeap` at `0x14003c4ff`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c544`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c544`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x14003c48e`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x14003c48e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14003c538`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14003c538`

## string_xrefs

- `0x14003c4ae`: `AslRegistryBuildUserPath`
- `0x14003c51b`: `AslRegistryBuildUserPath`
- `0x14003c49d`: `RtlFormatCurrentUserKeyPath failed [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  USHORT v7; // ax
  WCHAR *Heap; // rax
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-38h] BYREF

  KeyPath = 0;
  v4 = RtlFormatCurrentUserKeyPath(&KeyPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Destination->Length = 0;
    v6 = -1;
    do
      ++v6;
    while ( Source[v6] );
    v7 = KeyPath.Length + 2 * (v6 + 1);
    Destination->MaximumLength = v7;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
    Destination->Buffer = Heap;
    if ( Heap )
    {
      RtlAppendUnicodeStringToString(Destination, &KeyPath);
      RtlAppendUnicodeToString(Destination, Source);
      v5 = 0;
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryBuildUserPath", 1650, "Out of memory");
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryBuildUserPath", 1638, "RtlFormatCurrentUserKeyPath failed [%x]", v4);
  }
  RtlFreeUnicodeString(&KeyPath);
  return v5;
}

```

## disassembly

```asm
0x14003c470  push    rbx
0x14003c472  push    rbp
0x14003c473  push    rsi
0x14003c474  push    rdi
0x14003c475  push    r14
0x14003c477  sub     rsp, 40h
0x14003c47b  mov     rdi, rcx
0x14003c47e  xorps   xmm0, xmm0
0x14003c481  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x14003c486  mov     rbp, rdx
0x14003c489  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x14003c48e  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x14003c494  xor     r14d, r14d
0x14003c497  mov     ebx, eax
0x14003c499  test    eax, eax
0x14003c49b  jns     short loc_14003C4C3
0x14003c49d  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x14003c4a4  mov     [rsp+68h+var_48], eax
0x14003c4a8  mov     r8d, 666h
0x14003c4ae  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x14003c4b5  lea     ecx, [r14+1]
0x14003c4b9  call    AslLogCallPrintf
0x14003c4be  jmp     loc_14003C54D
0x14003c4c3  mov     [rdi], r14w
0x14003c4c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003c4cb  inc     rax
0x14003c4ce  cmp     [rbp+rax*2+0], r14w
0x14003c4d4  jnz     short loc_14003C4CB
0x14003c4d6  mov     esi, 1
0x14003c4db  add     ax, si
0x14003c4de  add     ax, ax
0x14003c4e1  add     ax, [rsp+68h+KeyPath.Length]
0x14003c4e6  movzx   r8d, ax; Size
0x14003c4ea  lea     edx, [rsi+7]; Flags
0x14003c4ed  mov     [rdi+2], r8w
0x14003c4f2  mov     rcx, gs:60h
0x14003c4fb  mov     rcx, [rcx+30h]; HeapHandle
0x14003c4ff  call    cs:__imp_RtlAllocateHeap
0x14003c505  mov     [rdi+8], rax
0x14003c509  test    rax, rax
0x14003c50c  jnz     short loc_14003C530
0x14003c50e  lea     r9, aOutOfMemory; "Out of memory"
0x14003c515  mov     r8d, 672h
0x14003c51b  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x14003c522  mov     ecx, esi
0x14003c524  mov     ebx, 0C0000017h
0x14003c529  call    AslLogCallPrintf
0x14003c52e  jmp     short loc_14003C54D
0x14003c530  lea     rdx, [rsp+68h+KeyPath]; Source
0x14003c535  mov     rcx, rdi; Destination
0x14003c538  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003c53e  mov     rdx, rbp; Source
0x14003c541  mov     rcx, rdi; Destination
0x14003c544  call    cs:__imp_RtlAppendUnicodeToString
0x14003c54a  mov     ebx, r14d
0x14003c54d  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x14003c552  call    cs:__imp_RtlFreeUnicodeString
0x14003c558  mov     eax, ebx
0x14003c55a  add     rsp, 40h
0x14003c55e  pop     r14
0x14003c560  pop     rdi
0x14003c561  pop     rsi
0x14003c562  pop     rbp
0x14003c563  pop     rbx
0x14003c564  retn
```
