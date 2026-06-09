# VfsGenerateMappedName

- ea: `0x140008aa8`
- end: `0x140008bfb`
- name: `VfsGenerateMappedName`
- size: `339`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000437c`
- `0x140008c04`

## callees

- `0x140008aa8`
- `0x14001187c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008b8a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008bd4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008b8a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008bd4`
- `ntoskrnl!ExAllocatePool2` at `0x140008b52`
- `ntoskrnl!ExAllocatePool2` at `0x140008b52`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140008b77`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140008b77`

## pseudocode

```c
__int64 __fastcall VfsGenerateMappedName(__int64 a1, const UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  bool v6; // si
  unsigned __int8 v7; // bp
  __int64 result; // rax
  unsigned int v9; // ecx
  unsigned __int16 v10; // r15
  __int64 Pool2; // rax
  char v12; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  v12 = 0;
  v7 = 0;
  if ( a2->Length )
    v6 = *a2->Buffer != 92;
  if ( (*(_DWORD *)(a1 + 4) & 2) != 0 )
  {
    result = IsProcessElevated(&v12);
    if ( (int)result < 0 )
      return result;
    if ( v12 )
      v7 = 1;
  }
  v9 = a2->Length + *(unsigned __int16 *)(a1 + 24) + **(unsigned __int16 **)(a1 + 56) + 2 * (v6 + v7);
  if ( v9 > 0xFFFE )
    return 3221225734LL;
  v10 = a2->Length + *(_WORD *)(a1 + 24) + **(_WORD **)(a1 + 56) + 2 * (v6 + v7);
  Pool2 = ExAllocatePool2(256, (unsigned __int16)v9, 1951614550);
  a3->Buffer = (wchar_t *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  a3->Length = 0;
  a3->MaximumLength = v10;
  RtlCopyUnicodeString(a3, (PCUNICODE_STRING)(a1 + 24));
  RtlAppendUnicodeStringToString(a3, *(PCUNICODE_STRING *)(a1 + 56));
  if ( v7 )
  {
    a3->Buffer[(unsigned __int64)a3->Length >> 1] = 83;
    a3->Length += 2;
  }
  if ( v6 )
  {
    a3->Buffer[(unsigned __int64)a3->Length >> 1] = 92;
    a3->Length += 2;
  }
  if ( a2->Length )
    RtlAppendUnicodeStringToString(a3, a2);
  return 0;
}

```

## disassembly

```asm
0x140008aa8  push    rbx
0x140008aaa  push    rbp
0x140008aab  push    rsi
0x140008aac  push    rdi
0x140008aad  push    r12
0x140008aaf  push    r13
0x140008ab1  push    r14
0x140008ab3  push    r15
0x140008ab5  sub     rsp, 28h
0x140008ab9  xor     r13d, r13d
0x140008abc  mov     r14, rcx
0x140008abf  mov     rbx, r8
0x140008ac2  mov     rdi, rdx
0x140008ac5  movzx   esi, r13b
0x140008ac9  mov     [rsp+68h+arg_0], r13b
0x140008ace  lea     ecx, [r13+5Ch]
0x140008ad2  movzx   ebp, r13b
0x140008ad6  lea     r15d, [r13+1]
0x140008ada  cmp     [rdx], r13w
0x140008ade  jbe     short loc_140008AEB
0x140008ae0  mov     rax, [rdx+8]
0x140008ae4  cmp     [rax], cx
0x140008ae7  cmovnz  esi, r15d
0x140008aeb  mov     eax, [r14+4]
0x140008aef  test    al, 2
0x140008af1  jz      short loc_140008B0E
0x140008af3  lea     rcx, [rsp+68h+arg_0]
0x140008af8  call    IsProcessElevated
0x140008afd  test    eax, eax
0x140008aff  js      loc_140008BE9
0x140008b05  cmp     [rsp+68h+arg_0], r13b
0x140008b0a  cmovnz  ebp, r15d
0x140008b0e  movzx   eax, sil
0x140008b12  movzx   edx, bpl
0x140008b16  add     edx, eax
0x140008b18  mov     rax, [r14+38h]
0x140008b1c  movzx   ecx, word ptr [rax]
0x140008b1f  movzx   eax, word ptr [r14+18h]
0x140008b24  lea     ecx, [rcx+rdx*2]
0x140008b27  add     ecx, eax
0x140008b29  movzx   eax, word ptr [rdi]
0x140008b2c  add     ecx, eax
0x140008b2e  cmp     ecx, 0FFFEh
0x140008b34  jbe     short loc_140008B40
0x140008b36  mov     eax, 0C0000106h
0x140008b3b  jmp     loc_140008BE9
0x140008b40  movzx   r15d, cx
0x140008b44  mov     r8d, 74534656h
0x140008b4a  mov     edx, r15d
0x140008b4d  mov     ecx, 100h
0x140008b52  call    cs:__imp_ExAllocatePool2
0x140008b59  nop     dword ptr [rax+rax+00h]
0x140008b5e  mov     [rbx+8], rax
0x140008b62  test    rax, rax
0x140008b65  jz      short loc_140008BE4
0x140008b67  lea     rdx, [r14+18h]; SourceString
0x140008b6b  mov     [rbx], r13w
0x140008b6f  mov     rcx, rbx; DestinationString
0x140008b72  mov     [rbx+2], r15w
0x140008b77  call    cs:__imp_RtlCopyUnicodeString
0x140008b7e  nop     dword ptr [rax+rax+00h]
0x140008b83  mov     rdx, [r14+38h]; Source
0x140008b87  mov     rcx, rbx; Destination
0x140008b8a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140008b91  nop     dword ptr [rax+rax+00h]
0x140008b96  test    bpl, bpl
0x140008b99  jz      short loc_140008BAF
0x140008b9b  movzx   ecx, word ptr [rbx]
0x140008b9e  mov     rax, [rbx+8]
0x140008ba2  shr     rcx, 1
0x140008ba5  mov     word ptr [rax+rcx*2], 53h ; 'S'
0x140008bab  add     word ptr [rbx], 2
0x140008baf  test    sil, sil
0x140008bb2  jz      short loc_140008BC8
0x140008bb4  movzx   ecx, word ptr [rbx]
0x140008bb7  mov     rax, [rbx+8]
0x140008bbb  shr     rcx, 1
0x140008bbe  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x140008bc4  add     word ptr [rbx], 2
0x140008bc8  cmp     [rdi], r13w
0x140008bcc  jbe     short loc_140008BE0
0x140008bce  mov     rdx, rdi; Source
0x140008bd1  mov     rcx, rbx; Destination
0x140008bd4  call    cs:__imp_RtlAppendUnicodeStringToString
0x140008bdb  nop     dword ptr [rax+rax+00h]
0x140008be0  xor     eax, eax
0x140008be2  jmp     short loc_140008BE9
0x140008be4  mov     eax, 0C000009Ah
0x140008be9  add     rsp, 28h
0x140008bed  pop     r15
0x140008bef  pop     r14
0x140008bf1  pop     r13
0x140008bf3  pop     r12
0x140008bf5  pop     rdi
0x140008bf6  pop     rsi
0x140008bf7  pop     rbp
0x140008bf8  pop     rbx
0x140008bf9  retn
```
