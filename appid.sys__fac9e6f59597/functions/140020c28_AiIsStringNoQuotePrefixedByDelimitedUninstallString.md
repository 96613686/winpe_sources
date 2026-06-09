# AiIsStringNoQuotePrefixedByDelimitedUninstallString

- ea: `0x140020c28`
- end: `0x140020ced`
- name: `AiIsStringNoQuotePrefixedByDelimitedUninstallString`
- size: `197`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int128 *, char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14002061c`
- `0x140022d58`

## callees

- `0x140020820`
- `0x140020930`
- `0x140020c28`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020caa`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020caa`

## pseudocode

```c
__int64 __fastcall AiIsStringNoQuotePrefixedByDelimitedUninstallString(unsigned __int16 *a1, __int128 *a2, char *a3)
{
  char v4; // di
  int NextDelimitedUninstallString; // ebx
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 v10[12]; // [rsp+50h] [rbp-18h] BYREF

  v7 = *a2;
  v4 = 0;
  *(_OWORD *)v10 = 0;
  String2 = 0;
  String1 = 0;
  NextDelimitedUninstallString = AiCopyUnicodeStringWithoutQuotations(a1, (__int64)&String2);
  if ( NextDelimitedUninstallString >= 0 )
  {
    do
    {
      if ( !(_WORD)v7 )
        break;
      NextDelimitedUninstallString = AiGetNextDelimitedUninstallString((__int64)&v7, (__int64)v10, &v7);
      if ( NextDelimitedUninstallString < 0 )
        goto LABEL_9;
      NextDelimitedUninstallString = AiCopyUnicodeStringWithoutQuotations(v10, (__int64)&String1);
      if ( NextDelimitedUninstallString < 0 )
        goto LABEL_9;
      if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
        v4 = 1;
      AiFree(String1.Buffer);
    }
    while ( !v4 );
    *a3 = v4;
    NextDelimitedUninstallString = 0;
  }
LABEL_9:
  AiFree(String2.Buffer);
  return (unsigned int)NextDelimitedUninstallString;
}

```

## disassembly

```asm
0x140020c28  push    rbp
0x140020c2a  push    rbx
0x140020c2b  push    rsi
0x140020c2c  push    rdi
0x140020c2d  push    r14
0x140020c2f  push    r15
0x140020c31  mov     rbp, rsp
0x140020c34  sub     rsp, 68h
0x140020c38  movups  xmm0, xmmword ptr [rdx]
0x140020c3b  lea     rdx, [rbp+String2]
0x140020c3f  xor     r14d, r14d
0x140020c42  xorps   xmm1, xmm1
0x140020c45  mov     rsi, r8
0x140020c48  movdqu  [rbp+var_48], xmm0
0x140020c4d  mov     dil, r14b
0x140020c50  xorps   xmm0, xmm0
0x140020c53  movups  xmmword ptr [rbp+var_18], xmm0
0x140020c57  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140020c5b  movups  xmmword ptr [rbp+String1.Length], xmm1
0x140020c5f  call    AiCopyUnicodeStringWithoutQuotations
0x140020c64  mov     ebx, eax
0x140020c66  test    eax, eax
0x140020c68  js      short loc_140020CD4
0x140020c6a  lea     r15d, [r14+1]
0x140020c6e  cmp     word ptr [rbp+var_48], r14w
0x140020c73  jz      short loc_140020CCE
0x140020c75  lea     r8, [rbp+var_48]
0x140020c79  lea     rdx, [rbp+var_18]
0x140020c7d  lea     rcx, [rbp+var_48]
0x140020c81  call    AiGetNextDelimitedUninstallString
0x140020c86  mov     ebx, eax
0x140020c88  test    eax, eax
0x140020c8a  js      short loc_140020CD4
0x140020c8c  lea     rdx, [rbp+String1]
0x140020c90  lea     rcx, [rbp+var_18]
0x140020c94  call    AiCopyUnicodeStringWithoutQuotations
0x140020c99  mov     ebx, eax
0x140020c9b  test    eax, eax
0x140020c9d  js      short loc_140020CD4
0x140020c9f  mov     r8b, r15b; CaseInSensitive
0x140020ca2  lea     rdx, [rbp+String2]; String2
0x140020ca6  lea     rcx, [rbp+String1]; String1
0x140020caa  call    cs:__imp_RtlPrefixUnicodeString
0x140020cb1  nop     dword ptr [rax+rax+00h]
0x140020cb6  mov     rcx, [rbp+String1.Buffer]
0x140020cba  test    al, al
0x140020cbc  movzx   edi, dil
0x140020cc0  cmovnz  edi, r15d
0x140020cc4  call    AiFree
0x140020cc9  test    dil, dil
0x140020ccc  jz      short loc_140020C6E
0x140020cce  mov     [rsi], dil
0x140020cd1  mov     ebx, r14d
0x140020cd4  mov     rcx, [rbp+String2.Buffer]
0x140020cd8  call    AiFree
0x140020cdd  mov     eax, ebx
0x140020cdf  add     rsp, 68h
0x140020ce3  pop     r15
0x140020ce5  pop     r14
0x140020ce7  pop     rdi
0x140020ce8  pop     rsi
0x140020ce9  pop     rbx
0x140020cea  pop     rbp
0x140020ceb  retn
```
