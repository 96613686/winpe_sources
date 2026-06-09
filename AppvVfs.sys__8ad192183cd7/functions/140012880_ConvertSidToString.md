# ConvertSidToString

- ea: `0x140012880`
- end: `0x1400128ca`
- name: `ConvertSidToString`
- size: `74`
- prototype: `PUNICODE_STRING __fastcall(PSID Sid, PUNICODE_STRING UnicodeString)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140009784`
- `0x140009d44`

## callees

- `0x140012880`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140012896`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012896`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400128af`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400128af`

## pseudocode

```c
PUNICODE_STRING __fastcall ConvertSidToString(PSID Sid, PUNICODE_STRING UnicodeString)
{
  *UnicodeString = 0;
  if ( !KeGetCurrentIrql() )
    RtlConvertSidToUnicodeString(UnicodeString, Sid, 1u);
  return UnicodeString;
}

```

## disassembly

```asm
0x140012880  mov     [rsp+arg_0], rbx
0x140012885  push    rdi
0x140012886  sub     rsp, 20h
0x14001288a  xorps   xmm0, xmm0
0x14001288d  mov     rbx, rdx
0x140012890  movups  xmmword ptr [rdx], xmm0
0x140012893  mov     rdi, rcx
0x140012896  call    cs:__imp_KeGetCurrentIrql
0x14001289d  nop     dword ptr [rax+rax+00h]
0x1400128a2  test    al, al
0x1400128a4  jnz     short loc_1400128BB
0x1400128a6  mov     r8b, 1; AllocateDestinationString
0x1400128a9  mov     rdx, rdi; Sid
0x1400128ac  mov     rcx, rbx; UnicodeString
0x1400128af  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400128b6  nop     dword ptr [rax+rax+00h]
0x1400128bb  mov     rax, rbx
0x1400128be  mov     rbx, [rsp+28h+arg_0]
0x1400128c3  add     rsp, 20h
0x1400128c7  pop     rdi
0x1400128c8  retn
```
