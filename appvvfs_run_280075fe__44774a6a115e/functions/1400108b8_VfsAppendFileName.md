# VfsAppendFileName

- ea: `0x1400108b8`
- end: `0x1400109ec`
- name: `VfsAppendFileName`
- size: `308`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010cb4`

## callees

- `0x1400108b8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400109bd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400109bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010989`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010989`
- `ntoskrnl!ExAllocatePool2` at `0x140010948`
- `ntoskrnl!ExAllocatePool2` at `0x140010948`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010972`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010972`

## pseudocode

```c
__int64 __fastcall VfsAppendFileName(PUNICODE_STRING Destination, PCUNICODE_STRING Source)
{
  unsigned int Length; // edx
  wchar_t v5; // bp
  unsigned __int16 v6; // cx
  unsigned int v7; // edx
  unsigned __int16 v8; // si
  wchar_t *Buffer; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  Length = Destination->Length;
  if ( Length < 2 || Source->Length < 2u || *Source->Buffer == 92 )
    return 3221225485LL;
  v5 = Destination->Buffer[((unsigned __int64)Destination->Length >> 1) - 1];
  v6 = Source->Length + 2;
  if ( v5 == 92 )
    v6 = Source->Length;
  if ( (unsigned __int16)(Destination->MaximumLength - Length) < v6 )
  {
    v7 = v6 + Length;
    DestinationString = 0;
    if ( v7 > 0xFFFF )
      return 3221225734LL;
    v8 = v7;
    DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v7, 1951614550);
    if ( !DestinationString.Buffer )
      return 3221225626LL;
    DestinationString.MaximumLength = v8;
    DestinationString.Length = 0;
    RtlCopyUnicodeString(&DestinationString, Destination);
    Buffer = Destination->Buffer;
    if ( Buffer )
      ExFreePoolWithTag(Buffer, 0);
    *Destination = DestinationString;
  }
  if ( v5 != 92 )
  {
    Destination->Buffer[(unsigned __int64)Destination->Length >> 1] = 92;
    Destination->Length += 2;
  }
  RtlAppendUnicodeStringToString(Destination, Source);
  return 0;
}

```

## disassembly

```asm
0x1400108b8  push    rbx
0x1400108ba  push    rbp
0x1400108bb  push    rsi
0x1400108bc  push    rdi
0x1400108bd  push    r15
0x1400108bf  sub     rsp, 30h
0x1400108c3  mov     rdi, rdx
0x1400108c6  mov     rbx, rcx
0x1400108c9  movzx   edx, word ptr [rcx]
0x1400108cc  cmp     edx, 2
0x1400108cf  jb      loc_1400109DB
0x1400108d5  movzx   r8d, word ptr [rdi]
0x1400108d9  cmp     r8w, 2
0x1400108de  jb      loc_1400109DB
0x1400108e4  mov     rax, [rdi+8]
0x1400108e8  mov     r15d, 5Ch ; '\'
0x1400108ee  cmp     [rax], r15w
0x1400108f2  jz      loc_1400109DB
0x1400108f8  mov     rax, [rbx+8]
0x1400108fc  mov     ecx, edx
0x1400108fe  shr     rcx, 1
0x140010901  movzx   ebp, word ptr [rax+rcx*2-2]
0x140010906  lea     ecx, [r8+2]
0x14001090a  movzx   eax, word ptr [rbx+2]
0x14001090e  cmp     bp, r15w
0x140010912  cmovz   cx, r8w
0x140010917  sub     ax, dx
0x14001091a  cmp     ax, cx
0x14001091d  jnb     short loc_14001099E
0x14001091f  movzx   ecx, cx
0x140010922  xorps   xmm0, xmm0
0x140010925  add     edx, ecx
0x140010927  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14001092c  cmp     edx, 0FFFFh
0x140010932  ja      loc_1400109D4
0x140010938  movzx   esi, dx
0x14001093b  mov     ecx, 100h
0x140010940  mov     edx, esi
0x140010942  mov     r8d, 74534656h
0x140010948  call    cs:__imp_ExAllocatePool2
0x14001094f  nop     dword ptr [rax+rax+00h]
0x140010954  mov     [rsp+58h+DestinationString.Buffer], rax
0x140010959  test    rax, rax
0x14001095c  jz      short loc_1400109CD
0x14001095e  xor     eax, eax
0x140010960  mov     [rsp+58h+DestinationString.MaximumLength], si
0x140010965  mov     rdx, rbx; SourceString
0x140010968  mov     [rsp+58h+DestinationString.Length], ax
0x14001096d  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140010972  call    cs:__imp_RtlCopyUnicodeString
0x140010979  nop     dword ptr [rax+rax+00h]
0x14001097e  mov     rcx, [rbx+8]; P
0x140010982  test    rcx, rcx
0x140010985  jz      short loc_140010995
0x140010987  xor     edx, edx; Tag
0x140010989  call    cs:__imp_ExFreePoolWithTag
0x140010990  nop     dword ptr [rax+rax+00h]
0x140010995  movups  xmm0, xmmword ptr [rsp+58h+DestinationString.Length]
0x14001099a  movdqu  xmmword ptr [rbx], xmm0
0x14001099e  cmp     bp, r15w
0x1400109a2  jz      short loc_1400109B7
0x1400109a4  movzx   ecx, word ptr [rbx]
0x1400109a7  mov     rax, [rbx+8]
0x1400109ab  shr     rcx, 1
0x1400109ae  mov     [rax+rcx*2], r15w
0x1400109b3  add     word ptr [rbx], 2
0x1400109b7  mov     rdx, rdi; Source
0x1400109ba  mov     rcx, rbx; Destination
0x1400109bd  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400109c4  nop     dword ptr [rax+rax+00h]
0x1400109c9  xor     eax, eax
0x1400109cb  jmp     short loc_1400109E0
0x1400109cd  mov     eax, 0C000009Ah
0x1400109d2  jmp     short loc_1400109E0
0x1400109d4  mov     eax, 0C0000106h
0x1400109d9  jmp     short loc_1400109E0
0x1400109db  mov     eax, 0C000000Dh
0x1400109e0  add     rsp, 30h
0x1400109e4  pop     r15
0x1400109e6  pop     rdi
0x1400109e7  pop     rsi
0x1400109e8  pop     rbp
0x1400109e9  pop     rbx
0x1400109ea  retn
```
