# VfsCreateMappingPrefixTable

- ea: `0x140008910`
- end: `0x1400089fb`
- name: `VfsCreateMappingPrefixTable`
- size: `235`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140008fb0`

## callees

- `0x140008910`
- `0x140008a04`
- `0x140012414`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400089a4`
- `ntoskrnl!ExAllocatePool2` at `0x1400089a4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400089d3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400089d3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140008935`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140008935`

## pseudocode

```c
__int64 __fastcall VfsCreateMappingPrefixTable(PCUNICODE_STRING SourceString, _QWORD *a2)
{
  char *v4; // rdi
  int v6; // ebx
  unsigned __int16 Length; // bx
  __int64 Pool2; // rax

  v4 = (char *)ExAllocateFromPagedLookasideList(&stru_14001FA80);
  if ( !v4 )
    return 3221225626LL;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 4) = 0;
  v6 = VfsPrefixTreeCreate(v4 + 32);
  if ( v6 >= 0 )
  {
    Length = SourceString->Length;
    Pool2 = ExAllocatePool2(256, SourceString->Length, 1851147862);
    *((_QWORD *)v4 + 3) = Pool2;
    if ( Pool2 )
    {
      *((_WORD *)v4 + 8) = 0;
      *((_WORD *)v4 + 9) = Length;
      v6 = 0;
      RtlCopyUnicodeString((PUNICODE_STRING)v4 + 1, SourceString);
    }
    else
    {
      v6 = -1073741670;
    }
  }
  if ( v6 < 0 )
    VfsDeleteMappingPrefixTable(v4);
  else
    *a2 = v4;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140008910  mov     [rsp+arg_0], rbx
0x140008915  mov     [rsp+arg_18], rsi
0x14000891a  mov     [rsp+arg_8], rdx
0x14000891f  push    rdi
0x140008920  push    r14
0x140008922  push    r15
0x140008924  sub     rsp, 30h
0x140008928  mov     r14, rdx
0x14000892b  mov     r15, rcx
0x14000892e  lea     rcx, stru_14001FA80; Lookaside
0x140008935  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000893c  nop     dword ptr [rax+rax+00h]
0x140008941  mov     rdi, rax
0x140008944  mov     [rsp+48h+arg_10], rax
0x140008949  test    rax, rax
0x14000894c  jnz     short loc_140008968
0x14000894e  mov     eax, 0C000009Ah
0x140008953  mov     rbx, [rsp+48h+arg_0]
0x140008958  mov     rsi, [rsp+48h+arg_18]
0x14000895d  add     rsp, 30h
0x140008961  pop     r15
0x140008963  pop     r14
0x140008965  pop     rdi
0x140008966  retn
0x140008968  mov     [rsp+48h+var_28], 0
0x140008970  xorps   xmm0, xmm0
0x140008973  xor     eax, eax
0x140008975  movups  xmmword ptr [rdi], xmm0
0x140008978  movups  xmmword ptr [rdi+10h], xmm0
0x14000897c  mov     [rdi+20h], rax
0x140008980  lea     rcx, [rdi+20h]
0x140008984  call    VfsPrefixTreeCreate
0x140008989  mov     ebx, eax
0x14000898b  mov     [rsp+48h+var_28], eax
0x14000898f  test    eax, eax
0x140008991  js      short loc_1400089E3
0x140008993  movzx   ebx, word ptr [r15]
0x140008997  mov     edx, ebx
0x140008999  mov     ecx, 100h
0x14000899e  mov     r8d, 6E564656h
0x1400089a4  call    cs:__imp_ExAllocatePool2
0x1400089ab  nop     dword ptr [rax+rax+00h]
0x1400089b0  mov     [rdi+18h], rax
0x1400089b4  test    rax, rax
0x1400089b7  jnz     short loc_1400089C0
0x1400089b9  mov     ebx, 0C000009Ah
0x1400089be  jmp     short loc_1400089DF
0x1400089c0  xor     eax, eax
0x1400089c2  mov     [rdi+10h], ax
0x1400089c6  mov     [rdi+12h], bx
0x1400089ca  xor     ebx, ebx
0x1400089cc  mov     rdx, r15; SourceString
0x1400089cf  lea     rcx, [rdi+10h]; DestinationString
0x1400089d3  call    cs:__imp_RtlCopyUnicodeString
0x1400089da  nop     dword ptr [rax+rax+00h]
0x1400089df  mov     [rsp+48h+var_28], ebx
0x1400089e3  test    ebx, ebx
0x1400089e5  js      short loc_1400089EC
0x1400089e7  mov     [r14], rdi
0x1400089ea  jmp     short loc_1400089F4
0x1400089ec  mov     rcx, rdi; Entry
0x1400089ef  call    VfsDeleteMappingPrefixTable
0x1400089f4  mov     eax, ebx
0x1400089f6  jmp     loc_140008953
0x140014d4d  push    rbp
0x140014d4f  sub     rsp, 20h
0x140014d53  mov     rbp, rdx
0x140014d56  cmp     dword ptr [rbp+20h], 0
0x140014d5a  jl      short loc_140014D69
0x140014d5c  mov     rcx, [rbp+58h]
0x140014d60  mov     rax, [rbp+60h]
0x140014d64  mov     [rcx], rax
0x140014d67  jmp     short loc_140014D73
0x140014d69  mov     rcx, [rbp+60h]; Entry
0x140014d6d  call    VfsDeleteMappingPrefixTable
0x140014d72  nop
0x140014d73  add     rsp, 20h
0x140014d77  pop     rbp
0x140014d78  retn
```
