# VidCurrentProcessQueryToken

- ea: `0x140075c10`
- end: `0x140075c71`
- name: `VidCurrentProcessQueryToken`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400fa3ac`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140075c1d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140075c1d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075c2c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075c2c`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075c57`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075c57`
- `ntoskrnl!SeQueryInformationToken` at `0x140075c46`
- `ntoskrnl!SeQueryInformationToken` at `0x140075c46`

## pseudocode

```c
__int64 __fastcall VidCurrentProcessQueryToken(__int64 a1, PVOID *a2)
{
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v4; // rdi

  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v4 = PsReferencePrimaryToken(CurrentProcess);
  LODWORD(a2) = SeQueryInformationToken(v4, TokenOwner, a2);
  PsDereferencePrimaryToken(v4);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x140075c10  mov     [rsp+arg_0], rbx
0x140075c15  push    rdi
0x140075c16  sub     rsp, 20h
0x140075c1a  mov     rbx, rdx
0x140075c1d  call    cs:__imp_PsGetCurrentProcess
0x140075c24  nop     dword ptr [rax+rax+00h]
0x140075c29  mov     rcx, rax; Process
0x140075c2c  call    cs:__imp_PsReferencePrimaryToken
0x140075c33  nop     dword ptr [rax+rax+00h]
0x140075c38  mov     r8, rbx; TokenInformation
0x140075c3b  mov     edx, 4; TokenInformationClass
0x140075c40  mov     rcx, rax; Token
0x140075c43  mov     rdi, rax
0x140075c46  call    cs:__imp_SeQueryInformationToken
0x140075c4d  nop     dword ptr [rax+rax+00h]
0x140075c52  mov     rcx, rdi; PrimaryToken
0x140075c55  mov     ebx, eax
0x140075c57  call    cs:__imp_PsDereferencePrimaryToken
0x140075c5e  nop     dword ptr [rax+rax+00h]
0x140075c63  mov     eax, ebx
0x140075c65  mov     rbx, [rsp+28h+arg_0]
0x140075c6a  add     rsp, 20h
0x140075c6e  pop     rdi
0x140075c6f  retn
```
