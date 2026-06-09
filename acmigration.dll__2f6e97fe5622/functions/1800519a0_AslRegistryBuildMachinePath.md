# AslRegistryBuildMachinePath

- ea: `0x1800519a0`
- end: `0x180051a7f`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180051a88`

## callees

- `0x1800519a0`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800519c3`
- `ntdll!RtlInitUnicodeString` at `0x1800519c3`
- `ntdll!RtlAllocateHeap` at `0x180051a04`
- `ntdll!RtlAllocateHeap` at `0x180051a04`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051a45`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051a45`
- `ntdll!RtlAppendUnicodeToString` at `0x180051a60`
- `ntdll!RtlAppendUnicodeToString` at `0x180051a6c`
- `ntdll!RtlAppendUnicodeToString` at `0x180051a60`
- `ntdll!RtlAppendUnicodeToString` at `0x180051a6c`

## string_xrefs

- `0x1800519b2`: `\Registry\Machine`
- `0x180051a28`: `AslRegistryBuildMachinePath`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildMachinePath(PUNICODE_STRING Destination, PCWSTR Source)
{
  __int64 v4; // rax
  USHORT v5; // ax
  WCHAR *Heap; // rax
  unsigned int v7; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine");
  Destination->Length = 0;
  v4 = -1;
  do
    ++v4;
  while ( Source[v4] );
  v5 = DestinationString.Length + 2 * (v4 + 1);
  Destination->MaximumLength = v5;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v5);
  Destination->Buffer = Heap;
  if ( Heap )
  {
    RtlAppendUnicodeStringToString(Destination, &DestinationString);
    if ( Source && *Source != 92 )
      RtlAppendUnicodeToString(Destination, L"\\");
    RtlAppendUnicodeToString(Destination, Source);
    return 0;
  }
  else
  {
    v7 = -1073741801;
    AslLogCallPrintf(
      1,
      "AslRegistryBuildMachinePath",
      1582,
      "Failed to allocate %d bytes for user key buffer",
      Destination->MaximumLength);
  }
  return v7;
}

```

## disassembly

```asm
0x1800519a0  push    rbx
0x1800519a2  push    rbp
0x1800519a3  push    rsi
0x1800519a4  push    rdi
0x1800519a5  sub     rsp, 48h
0x1800519a9  mov     rdi, rdx
0x1800519ac  mov     rbx, rcx
0x1800519af  xorps   xmm0, xmm0
0x1800519b2  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine"
0x1800519b9  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800519be  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800519c3  call    cs:__imp_RtlInitUnicodeString
0x1800519c9  xor     esi, esi
0x1800519cb  mov     [rbx], si
0x1800519ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800519d2  inc     rax
0x1800519d5  cmp     [rdi+rax*2], si
0x1800519d9  jnz     short loc_1800519D2
0x1800519db  mov     ebp, 1
0x1800519e0  add     ax, bp
0x1800519e3  add     ax, ax
0x1800519e6  add     ax, [rsp+68h+DestinationString.Length]
0x1800519eb  movzx   r8d, ax; Size
0x1800519ef  lea     edx, [rbp+7]; Flags
0x1800519f2  mov     [rbx+2], r8w
0x1800519f7  mov     rcx, gs:60h
0x180051a00  mov     rcx, [rcx+30h]; HeapHandle
0x180051a04  call    cs:__imp_RtlAllocateHeap
0x180051a0a  mov     [rbx+8], rax
0x180051a0e  test    rax, rax
0x180051a11  jnz     short loc_180051A3D
0x180051a13  movzx   eax, word ptr [rbx+2]
0x180051a17  lea     r9, aFailedToAlloca_17; "Failed to allocate %d bytes for user ke"...
0x180051a1e  mov     r8d, 62Eh
0x180051a24  mov     [rsp+68h+var_48], eax
0x180051a28  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x180051a2f  mov     ecx, ebp
0x180051a31  mov     edi, 0C0000017h
0x180051a36  call    AslLogCallPrintf
0x180051a3b  jmp     short loc_180051A74
0x180051a3d  lea     rdx, [rsp+68h+DestinationString]; Source
0x180051a42  mov     rcx, rbx; Destination
0x180051a45  call    cs:__imp_RtlAppendUnicodeStringToString
0x180051a4b  test    rdi, rdi
0x180051a4e  jz      short loc_180051A66
0x180051a50  cmp     word ptr [rdi], 5Ch ; '\'
0x180051a54  jz      short loc_180051A66
0x180051a56  lea     rdx, asc_18006E074; "\\"
0x180051a5d  mov     rcx, rbx; Destination
0x180051a60  call    cs:__imp_RtlAppendUnicodeToString
0x180051a66  mov     rdx, rdi; Source
0x180051a69  mov     rcx, rbx; Destination
0x180051a6c  call    cs:__imp_RtlAppendUnicodeToString
0x180051a72  mov     edi, esi
0x180051a74  mov     eax, edi
0x180051a76  add     rsp, 48h
0x180051a7a  pop     rdi
0x180051a7b  pop     rsi
0x180051a7c  pop     rbp
0x180051a7d  pop     rbx
0x180051a7e  retn
```
