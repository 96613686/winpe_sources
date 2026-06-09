# AslRegistryBuildUserPath

- ea: `0x140051fcc`
- end: `0x1400520d4`
- name: `AslRegistryBuildUserPath`
- size: `264`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140046440`

## callees

- `0x140004553`
- `0x14003e364`
- `0x140051fcc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140052060`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140052060`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005204e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005204e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140052074`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140052074`
- `ntoskrnl!RtlFormatCurrentUserKeyPath` at `0x140051fea`
- `ntoskrnl!RtlFormatCurrentUserKeyPath` at `0x140051fea`

## string_xrefs

- `0x14005209b`: `AslRegistryBuildUserPath`
- `0x1400520c1`: `AslRegistryBuildUserPath`
- `0x1400520b0`: `RtlFormatCurrentUserKeyPath failed [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned __int16 v7; // ax
  wchar_t *Pool2_0; // rax
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
    Pool2_0 = (wchar_t *)ExAllocatePool2_0(256, v7, 1953517633);
    Destination->Buffer = Pool2_0;
    if ( Pool2_0 )
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
0x140051fcc  push    rbx
0x140051fce  push    rbp
0x140051fcf  push    rsi
0x140051fd0  push    rdi
0x140051fd1  push    r14
0x140051fd3  sub     rsp, 40h
0x140051fd7  mov     rdi, rcx
0x140051fda  xorps   xmm0, xmm0
0x140051fdd  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x140051fe2  mov     rbp, rdx
0x140051fe5  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x140051fea  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x140051ff1  nop     dword ptr [rax+rax+00h]
0x140051ff6  xor     r14d, r14d
0x140051ff9  mov     ebx, eax
0x140051ffb  test    eax, eax
0x140051ffd  js      loc_1400520B0
0x140052003  mov     [rdi], r14w
0x140052007  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005200b  inc     rax
0x14005200e  cmp     [rbp+rax*2+0], r14w
0x140052014  jnz     short loc_14005200B
0x140052016  mov     esi, 1
0x14005201b  mov     ecx, 100h
0x140052020  add     ax, si
0x140052023  mov     r8d, 74705041h
0x140052029  add     ax, ax
0x14005202c  add     ax, [rsp+68h+KeyPath.Length]
0x140052031  movzx   edx, ax
0x140052034  mov     [rdi+2], dx
0x140052038  call    ExAllocatePool2_0
0x14005203d  mov     [rdi+8], rax
0x140052041  test    rax, rax
0x140052044  jz      short loc_14005208E
0x140052046  lea     rdx, [rsp+68h+KeyPath]; Source
0x14005204b  mov     rcx, rdi; Destination
0x14005204e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140052055  nop     dword ptr [rax+rax+00h]
0x14005205a  mov     rdx, rbp; Source
0x14005205d  mov     rcx, rdi; Destination
0x140052060  call    cs:__imp_RtlAppendUnicodeToString
0x140052067  nop     dword ptr [rax+rax+00h]
0x14005206c  mov     ebx, r14d
0x14005206f  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x140052074  call    cs:__imp_RtlFreeUnicodeString
0x14005207b  nop     dword ptr [rax+rax+00h]
0x140052080  mov     eax, ebx
0x140052082  add     rsp, 40h
0x140052086  pop     r14
0x140052088  pop     rdi
0x140052089  pop     rsi
0x14005208a  pop     rbp
0x14005208b  pop     rbx
0x14005208c  retn
0x14005208e  lea     r9, aOutOfMemory; "Out of memory"
0x140052095  mov     r8d, 672h
0x14005209b  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x1400520a2  mov     ecx, esi
0x1400520a4  mov     ebx, 0C0000017h
0x1400520a9  call    AslLogCallPrintf
0x1400520ae  jmp     short loc_14005206F
0x1400520b0  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x1400520b7  mov     [rsp+68h+var_48], eax
0x1400520bb  mov     r8d, 666h
0x1400520c1  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x1400520c8  mov     ecx, 1
0x1400520cd  call    AslLogCallPrintf
0x1400520d2  jmp     short loc_14005206F
```
