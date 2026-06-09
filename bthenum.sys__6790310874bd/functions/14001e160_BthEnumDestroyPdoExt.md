# BthEnumDestroyPdoExt

- ea: `0x14001e160`
- end: `0x14001e1d0`
- name: `BthEnumDestroyPdoExt`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a28`
- `0x140002b64`
- `0x14001ec38`

## callees

- `0x14001e160`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e1aa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e1bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e1aa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e1bd`
- `ntoskrnl!ExFreePool` at `0x14001e172`
- `ntoskrnl!ExFreePool` at `0x14001e18f`
- `ntoskrnl!ExFreePool` at `0x14001e172`
- `ntoskrnl!ExFreePool` at `0x14001e18f`

## pseudocode

```c
void __fastcall BthEnumDestroyPdoExt(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 72);
  if ( v2 )
  {
    ExFreePool(v2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v3 = *(void **)(a1 + 56);
  if ( v3 )
  {
    ExFreePool(v3);
    *(_QWORD *)(a1 + 56) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 2888));
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 2904));
}

```

## disassembly

```asm
0x14001e160  push    rbx
0x14001e162  sub     rsp, 20h
0x14001e166  mov     rbx, rcx
0x14001e169  mov     rcx, [rcx+48h]; P
0x14001e16d  test    rcx, rcx
0x14001e170  jz      short loc_14001E186
0x14001e172  call    cs:__imp_ExFreePool
0x14001e179  nop     dword ptr [rax+rax+00h]
0x14001e17e  mov     qword ptr [rbx+48h], 0
0x14001e186  mov     rcx, [rbx+38h]; P
0x14001e18a  test    rcx, rcx
0x14001e18d  jz      short loc_14001E1A3
0x14001e18f  call    cs:__imp_ExFreePool
0x14001e196  nop     dword ptr [rax+rax+00h]
0x14001e19b  mov     qword ptr [rbx+38h], 0
0x14001e1a3  lea     rcx, [rbx+0B48h]; UnicodeString
0x14001e1aa  call    cs:__imp_RtlFreeUnicodeString
0x14001e1b1  nop     dword ptr [rax+rax+00h]
0x14001e1b6  lea     rcx, [rbx+0B58h]; UnicodeString
0x14001e1bd  call    cs:__imp_RtlFreeUnicodeString
0x14001e1c4  nop     dword ptr [rax+rax+00h]
0x14001e1c9  add     rsp, 20h
0x14001e1cd  pop     rbx
0x14001e1ce  retn
```
