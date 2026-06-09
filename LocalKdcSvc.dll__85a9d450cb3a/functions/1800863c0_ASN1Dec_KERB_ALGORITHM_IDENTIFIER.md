# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x1800863c0`
- end: `0x180086475`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `181`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180087108`
- `0x18008da88`
- `0x18008ded8`
- `0x18008f3e4`
- `0x180090460`

## callees

- `0x1800863c0`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x180086457`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180086457`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008642a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008642a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800863fc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800863fc`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180086416`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180086416`
- `MSASN1!ASN1BERDecOpenType2` at `0x180086440`
- `MSASN1!ASN1BERDecOpenType2` at `0x180086440`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecObjectIdentifier(v5, 6, a3 + 8))
    && (!(unsigned int)ASN1BERDecPeekTag(v10, &v9)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1BERDecOpenType2(v6, a3 + 16))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800863c0  mov     r11, rsp
0x1800863c3  mov     [r11+8], rbx
0x1800863c7  push    rdi
0x1800863c8  sub     rsp, 30h
0x1800863cc  test    edx, edx
0x1800863ce  mov     qword ptr [r11+20h], 0
0x1800863d6  mov     eax, 10h
0x1800863db  mov     qword ptr [r11-18h], 0
0x1800863e3  mov     rbx, r8
0x1800863e6  mov     [rsp+38h+arg_8], 0
0x1800863ee  cmovz   edx, eax
0x1800863f1  lea     r9, [r11-18h]
0x1800863f5  lea     r8, [r11+20h]
0x1800863f9  mov     rdi, rcx
0x1800863fc  call    cs:__imp_ASN1BERDecExplicitTag
0x180086402  test    eax, eax
0x180086404  jz      short loc_180086468
0x180086406  mov     rcx, [rsp+38h+arg_18]
0x18008640b  lea     r8, [rbx+8]
0x18008640f  xor     eax, eax
0x180086411  mov     [rbx], al
0x180086413  lea     edx, [rax+6]
0x180086416  call    cs:__imp_ASN1BERDecObjectIdentifier
0x18008641c  test    eax, eax
0x18008641e  jz      short loc_180086468
0x180086420  mov     rcx, [rsp+38h+arg_18]
0x180086425  lea     rdx, [rsp+38h+arg_8]
0x18008642a  call    cs:__imp_ASN1BERDecPeekTag
0x180086430  test    eax, eax
0x180086432  jz      short loc_18008644A
0x180086434  mov     rcx, [rsp+38h+arg_18]
0x180086439  lea     rdx, [rbx+10h]
0x18008643d  or      byte ptr [rbx], 80h
0x180086440  call    cs:__imp_ASN1BERDecOpenType2
0x180086446  test    eax, eax
0x180086448  jz      short loc_180086468
0x18008644a  mov     r8, [rsp+38h+var_18]
0x18008644f  mov     rcx, rdi
0x180086452  mov     rdx, [rsp+38h+arg_18]
0x180086457  call    cs:__imp_ASN1BERDecEndOfContents
0x18008645d  xor     ecx, ecx
0x18008645f  test    eax, eax
0x180086461  setnz   cl
0x180086464  mov     eax, ecx
0x180086466  jmp     short loc_18008646A
0x180086468  xor     eax, eax
0x18008646a  mov     rbx, [rsp+38h+arg_0]
0x18008646f  add     rsp, 30h
0x180086473  pop     rdi
0x180086474  retn
```
