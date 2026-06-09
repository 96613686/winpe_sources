# AslRegistryBuildUserPath

- ea: `0x18006c764`
- end: `0x18006c859`
- name: `AslRegistryBuildUserPath`
- size: `245`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180027118`

## callees

- `0x1800197d4`
- `0x18006c764`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006c846`
- `ntdll!RtlFreeUnicodeString` at `0x18006c846`
- `ntdll!RtlAppendUnicodeToString` at `0x18006c838`
- `ntdll!RtlAppendUnicodeToString` at `0x18006c838`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18006c82c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18006c82c`
- `ntdll!RtlAllocateHeap` at `0x18006c7f3`
- `ntdll!RtlAllocateHeap` at `0x18006c7f3`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18006c782`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18006c782`

## string_xrefs

- `0x18006c791`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x18006c7a2`: `AslRegistryBuildUserPath`
- `0x18006c80f`: `AslRegistryBuildUserPath`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  USHORT v6; // ax
  WCHAR *Heap; // rax
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-38h] BYREF

  KeyPath = 0;
  v4 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v4 >= 0 )
  {
    Destination->Length = 0;
    v5 = -1;
    do
      ++v5;
    while ( Source[v5] );
    v6 = KeyPath.Length + 2 * (v5 + 1);
    Destination->MaximumLength = v6;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6);
    Destination->Buffer = Heap;
    if ( Heap )
    {
      RtlAppendUnicodeStringToString(Destination, &KeyPath);
      RtlAppendUnicodeToString(Destination, Source);
      v4 = 0;
    }
    else
    {
      v4 = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"AslRegistryBuildUserPath", 1650, (unsigned int)"Out of memory");
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslRegistryBuildUserPath",
      1638,
      (unsigned int)"RtlFormatCurrentUserKeyPath failed [%x]");
  }
  RtlFreeUnicodeString(&KeyPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006c764  push    rbx
0x18006c766  push    rbp
0x18006c767  push    rsi
0x18006c768  push    rdi
0x18006c769  push    r14
0x18006c76b  sub     rsp, 40h
0x18006c76f  mov     rdi, rcx
0x18006c772  xorps   xmm0, xmm0
0x18006c775  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x18006c77a  mov     rbp, rdx
0x18006c77d  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x18006c782  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18006c788  xor     r14d, r14d
0x18006c78b  mov     ebx, eax
0x18006c78d  test    eax, eax
0x18006c78f  jns     short loc_18006C7B7
0x18006c791  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x18006c798  mov     [rsp+68h+var_48], eax
0x18006c79c  mov     r8d, 666h
0x18006c7a2  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18006c7a9  lea     ecx, [r14+1]
0x18006c7ad  call    AslLogCallPrintf
0x18006c7b2  jmp     loc_18006C841
0x18006c7b7  mov     [rdi], r14w
0x18006c7bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c7bf  inc     rax
0x18006c7c2  cmp     [rbp+rax*2+0], r14w
0x18006c7c8  jnz     short loc_18006C7BF
0x18006c7ca  mov     esi, 1
0x18006c7cf  add     ax, si
0x18006c7d2  add     ax, ax
0x18006c7d5  add     ax, [rsp+68h+KeyPath.Length]
0x18006c7da  movzx   r8d, ax; Size
0x18006c7de  lea     edx, [rsi+7]; Flags
0x18006c7e1  mov     [rdi+2], r8w
0x18006c7e6  mov     rcx, gs:60h
0x18006c7ef  mov     rcx, [rcx+30h]; HeapHandle
0x18006c7f3  call    cs:__imp_RtlAllocateHeap
0x18006c7f9  mov     [rdi+8], rax
0x18006c7fd  test    rax, rax
0x18006c800  jnz     short loc_18006C824
0x18006c802  lea     r9, aOutOfMemory_0; "Out of memory"
0x18006c809  mov     r8d, 672h
0x18006c80f  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18006c816  mov     ecx, esi
0x18006c818  mov     ebx, 0C0000017h
0x18006c81d  call    AslLogCallPrintf
0x18006c822  jmp     short loc_18006C841
0x18006c824  lea     rdx, [rsp+68h+KeyPath]; Source
0x18006c829  mov     rcx, rdi; Destination
0x18006c82c  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006c832  mov     rdx, rbp; Source
0x18006c835  mov     rcx, rdi; Destination
0x18006c838  call    cs:__imp_RtlAppendUnicodeToString
0x18006c83e  mov     ebx, r14d
0x18006c841  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x18006c846  call    cs:__imp_RtlFreeUnicodeString
0x18006c84c  mov     eax, ebx
0x18006c84e  add     rsp, 40h
0x18006c852  pop     r14
0x18006c854  pop     rdi
0x18006c855  pop     rsi
0x18006c856  pop     rbp
0x18006c857  pop     rbx
0x18006c858  retn
```
