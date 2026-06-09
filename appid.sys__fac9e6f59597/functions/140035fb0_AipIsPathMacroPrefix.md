# AipIsPathMacroPrefix

- ea: `0x140035fb0`
- end: `0x14003600e`
- name: `AipIsPathMacroPrefix`
- size: `94`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400283d0`
- `0x140037ac0`

## callees

- `0x140035fb0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140035ff9`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140035ff9`

## pseudocode

```c
__int64 __fastcall AipIsPathMacroPrefix(PCUNICODE_STRING String2, PCUNICODE_STRING String1)
{
  unsigned __int64 Length; // rax
  unsigned int v4; // r8d
  WCHAR v6; // dx

  Length = String1->Length;
  v4 = String2->Length;
  if ( (unsigned __int16)v4 < (unsigned __int16)Length )
    return 0;
  if ( v4 > (int)Length + 1 && (v6 = String2->Buffer[Length >> 1], v6 != 92) && v6 )
    return 0;
  else
    return RtlPrefixUnicodeString(String1, String2, 1u);
}

```

## disassembly

```asm
0x140035fb0  sub     rsp, 28h
0x140035fb4  movzx   eax, word ptr [rdx]
0x140035fb7  mov     r10, rdx
0x140035fba  movzx   r8d, word ptr [rcx]
0x140035fbe  mov     r9, rcx
0x140035fc1  cmp     r8w, ax
0x140035fc5  jnb     short loc_140035FCF
0x140035fc7  xor     eax, eax
0x140035fc9  add     rsp, 28h
0x140035fcd  retn
0x140035fcf  lea     edx, [rax+1]
0x140035fd2  cmp     r8d, edx
0x140035fd5  jbe     short loc_140035FF0
0x140035fd7  mov     rcx, rax
0x140035fda  mov     rax, [r9+8]
0x140035fde  shr     rcx, 1
0x140035fe1  movzx   edx, word ptr [rax+rcx*2]
0x140035fe5  cmp     dx, 5Ch ; '\'
0x140035fe9  jz      short loc_140035FF0
0x140035feb  test    dx, dx
0x140035fee  jnz     short loc_140035FC7
0x140035ff0  mov     r8b, 1; CaseInSensitive
0x140035ff3  mov     rdx, r9; String2
0x140035ff6  mov     rcx, r10; String1
0x140035ff9  call    cs:__imp_RtlPrefixUnicodeString
0x140036000  nop     dword ptr [rax+rax+00h]
0x140036005  movzx   eax, al
0x140036008  add     rsp, 28h
0x14003600c  retn
```
