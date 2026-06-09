# AslRegistryBuildUserPath

- ea: `0x18002ab0c`
- end: `0x18002ac03`
- name: `AslRegistryBuildUserPath`
- size: `247`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016910`

## callees

- `0x18000f114`
- `0x18002ab0c`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18002abc8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002abc8`
- `ntdll!RtlFreeUnicodeString` at `0x18002abad`
- `ntdll!RtlFreeUnicodeString` at `0x18002abad`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abd4`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abd4`
- `ntdll!RtlAllocateHeap` at `0x18002ab79`
- `ntdll!RtlAllocateHeap` at `0x18002ab79`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18002ab2a`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18002ab2a`

## string_xrefs

- `0x18002abdf`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x18002ab95`: `AslRegistryBuildUserPath`
- `0x18002abf0`: `AslRegistryBuildUserPath`

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
  if ( v4 < 0 )
  {
    AslLogCallPrintf(1, "AslRegistryBuildUserPath", 1638, "RtlFormatCurrentUserKeyPath failed [%x]", v4);
  }
  else
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
  RtlFreeUnicodeString(&KeyPath);
  return v5;
}

```

## disassembly

```asm
0x18002ab0c  push    rbx
0x18002ab0e  push    rbp
0x18002ab0f  push    rsi
0x18002ab10  push    rdi
0x18002ab11  push    r14
0x18002ab13  sub     rsp, 40h
0x18002ab17  mov     rdi, rcx
0x18002ab1a  xorps   xmm0, xmm0
0x18002ab1d  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x18002ab22  mov     rbp, rdx
0x18002ab25  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x18002ab2a  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18002ab30  xor     r14d, r14d
0x18002ab33  mov     ebx, eax
0x18002ab35  test    eax, eax
0x18002ab37  js      loc_18002ABDF
0x18002ab3d  mov     [rdi], r14w
0x18002ab41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ab45  inc     rax
0x18002ab48  cmp     [rbp+rax*2+0], r14w
0x18002ab4e  jnz     short loc_18002AB45
0x18002ab50  mov     esi, 1
0x18002ab55  add     ax, si
0x18002ab58  add     ax, ax
0x18002ab5b  add     ax, [rsp+68h+KeyPath.Length]
0x18002ab60  movzx   r8d, ax; Size
0x18002ab64  lea     edx, [rsi+7]; Flags
0x18002ab67  mov     [rdi+2], r8w
0x18002ab6c  mov     rcx, gs:60h
0x18002ab75  mov     rcx, [rcx+30h]; HeapHandle
0x18002ab79  call    cs:__imp_RtlAllocateHeap
0x18002ab7f  mov     [rdi+8], rax
0x18002ab83  test    rax, rax
0x18002ab86  jnz     short loc_18002ABC0
0x18002ab88  lea     r9, aOutOfMemory; "Out of memory"
0x18002ab8f  mov     r8d, 672h
0x18002ab95  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18002ab9c  mov     ecx, esi
0x18002ab9e  mov     ebx, 0C0000017h
0x18002aba3  call    AslLogCallPrintf
0x18002aba8  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x18002abad  call    cs:__imp_RtlFreeUnicodeString
0x18002abb3  mov     eax, ebx
0x18002abb5  add     rsp, 40h
0x18002abb9  pop     r14
0x18002abbb  pop     rdi
0x18002abbc  pop     rsi
0x18002abbd  pop     rbp
0x18002abbe  pop     rbx
0x18002abbf  retn
0x18002abc0  lea     rdx, [rsp+68h+KeyPath]; Source
0x18002abc5  mov     rcx, rdi; Destination
0x18002abc8  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002abce  mov     rdx, rbp; Source
0x18002abd1  mov     rcx, rdi; Destination
0x18002abd4  call    cs:__imp_RtlAppendUnicodeToString
0x18002abda  mov     ebx, r14d
0x18002abdd  jmp     short loc_18002ABA8
0x18002abdf  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x18002abe6  mov     [rsp+68h+var_48], eax
0x18002abea  mov     r8d, 666h
0x18002abf0  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18002abf7  mov     ecx, 1
0x18002abfc  call    AslLogCallPrintf
0x18002ac01  jmp     short loc_18002ABA8
```
