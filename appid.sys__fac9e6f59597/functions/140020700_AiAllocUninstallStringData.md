# AiAllocUninstallStringData

- ea: `0x140020700`
- end: `0x140020788`
- name: `AiAllocUninstallStringData`
- size: `136`
- prototype: `struct _UNICODE_STRING *__fastcall(PCUNICODE_STRING StringIn, PCUNICODE_STRING)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140020700`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14002072f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140020748`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14002072f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140020748`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002075c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002075c`

## pseudocode

```c
struct _UNICODE_STRING *__fastcall AiAllocUninstallStringData(PCUNICODE_STRING StringIn, PCUNICODE_STRING a2)
{
  struct _UNICODE_STRING *v4; // rax
  struct _UNICODE_STRING *v5; // rbx

  v4 = (struct _UNICODE_STRING *)AiAlloc(0x30u);
  v5 = v4;
  if ( v4 )
  {
    if ( RtlDuplicateUnicodeString(1u, StringIn, v4 + 1) >= 0 )
    {
      if ( RtlDuplicateUnicodeString(1u, a2, v5 + 2) >= 0 )
      {
        v5->Buffer = &v5->Length;
        *(_QWORD *)&v5->Length = v5;
        return v5;
      }
      RtlFreeUnicodeString(v5 + 1);
    }
    AiFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140020700  push    rbx
0x140020702  push    rbp
0x140020703  push    rsi
0x140020704  push    rdi
0x140020705  sub     rsp, 28h
0x140020709  mov     rsi, rcx
0x14002070c  mov     rbp, rdx
0x14002070f  mov     ecx, 30h ; '0'
0x140020714  call    AiAlloc
0x140020719  mov     rbx, rax
0x14002071c  test    rax, rax
0x14002071f  jz      short loc_14002077B
0x140020721  mov     rdx, rsi; StringIn
0x140020724  lea     r8, [rax+10h]; StringOut
0x140020728  mov     esi, 1
0x14002072d  mov     ecx, esi; Flags
0x14002072f  call    cs:__imp_RtlDuplicateUnicodeString
0x140020736  nop     dword ptr [rax+rax+00h]
0x14002073b  test    eax, eax
0x14002073d  js      short loc_140020768
0x14002073f  lea     r8, [rbx+20h]; StringOut
0x140020743  mov     rdx, rbp; StringIn
0x140020746  mov     ecx, esi; Flags
0x140020748  call    cs:__imp_RtlDuplicateUnicodeString
0x14002074f  nop     dword ptr [rax+rax+00h]
0x140020754  test    eax, eax
0x140020756  jns     short loc_140020774
0x140020758  lea     rcx, [rbx+10h]; UnicodeString
0x14002075c  call    cs:__imp_RtlFreeUnicodeString
0x140020763  nop     dword ptr [rax+rax+00h]
0x140020768  mov     rcx, rbx
0x14002076b  call    AiFree
0x140020770  xor     ebx, ebx
0x140020772  jmp     short loc_14002077B
0x140020774  mov     [rbx+8], rbx
0x140020778  mov     [rbx], rbx
0x14002077b  mov     rax, rbx
0x14002077e  add     rsp, 28h
0x140020782  pop     rdi
0x140020783  pop     rsi
0x140020784  pop     rbp
0x140020785  pop     rbx
0x140020786  retn
```
