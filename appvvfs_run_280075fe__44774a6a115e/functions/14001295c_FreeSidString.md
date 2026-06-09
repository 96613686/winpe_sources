# FreeSidString

- ea: `0x14001295c`
- end: `0x1400129ae`
- name: `FreeSidString`
- size: `82`
- prototype: `__int64 __fastcall(PUNICODE_STRING UnicodeString)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140009784`
- `0x140009d44`

## callees

- `0x14001295c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140012965`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012965`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012984`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012984`
- `ntoskrnl!DbgPrint` at `0x140012999`
- `ntoskrnl!DbgPrint` at `0x140012999`

## string_xrefs

- `0x140012992`: `FreeSidString() called at IRQL > PASSIVE_LEVEL. The caller should refactorthe log message so this method is only called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
void __fastcall FreeSidString(PUNICODE_STRING UnicodeString)
{
  if ( KeGetCurrentIrql() )
  {
    DbgPrint(
      "FreeSidString() called at IRQL > PASSIVE_LEVEL. The caller should refactorthe log message so this method is only c"
      "alled at IRQL == PASSIVE_LEVEL.");
    __int2c();
  }
  else if ( UnicodeString )
  {
    if ( UnicodeString->Buffer )
      RtlFreeUnicodeString(UnicodeString);
  }
}

```

## disassembly

```asm
0x14001295c  push    rbx
0x14001295e  sub     rsp, 20h
0x140012962  mov     rbx, rcx
0x140012965  call    cs:__imp_KeGetCurrentIrql
0x14001296c  nop     dword ptr [rax+rax+00h]
0x140012971  test    al, al
0x140012973  jnz     short loc_140012992
0x140012975  test    rbx, rbx
0x140012978  jz      short loc_1400129A7
0x14001297a  cmp     qword ptr [rbx+8], 0
0x14001297f  jz      short loc_1400129A7
0x140012981  mov     rcx, rbx; UnicodeString
0x140012984  call    cs:__imp_RtlFreeUnicodeString
0x14001298b  nop     dword ptr [rax+rax+00h]
0x140012990  jmp     short loc_1400129A7
0x140012992  lea     rcx, Format; "FreeSidString() called at IRQL > PASSIV"...
0x140012999  call    cs:__imp_DbgPrint
0x1400129a0  nop     dword ptr [rax+rax+00h]
0x1400129a5  int     2Ch; Windows NT - assertion failure
0x1400129a7  add     rsp, 20h
0x1400129ab  pop     rbx
0x1400129ac  retn
```
