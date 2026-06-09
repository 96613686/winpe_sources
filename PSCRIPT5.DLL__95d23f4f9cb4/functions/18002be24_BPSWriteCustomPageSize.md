# BPSWriteCustomPageSize

- ea: `0x18002be24`
- end: `0x18002bf87`
- name: `BPSWriteCustomPageSize`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d220`

## callees

- `0x18002be24`
- `0x18002c3e8`
- `0x180053aa0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18002bf0a`
- `KERNEL32!MulDiv` at `0x18002bf25`
- `KERNEL32!MulDiv` at `0x18002bf41`
- `KERNEL32!MulDiv` at `0x18002bf5d`
- `KERNEL32!MulDiv` at `0x18002bf0a`
- `KERNEL32!MulDiv` at `0x18002bf25`
- `KERNEL32!MulDiv` at `0x18002bf41`
- `KERNEL32!MulDiv` at `0x18002bf5d`

## pseudocode

```c
__int64 __fastcall BPSWriteCustomPageSize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r9
  const char *v15; // rax
  const char *v16; // r10
  const char *v17; // rcx
  char v18; // r11
  char **v19; // rdx
  __int64 v21; // rdi
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  __int64 v29; // r8
  __int64 v30; // r9
  int nNumber[18]; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)nNumber = 0;
  v6 = PReadUnsignedInt(a3, 0, nNumber, a4);
  if ( !v6 )
    return 0;
  v9 = PReadUnsignedInt(v6, v7, &nNumber[1], v8);
  if ( !v9 )
    return 0;
  v12 = PReadUnsignedInt(v9, v10, &nNumber[2], v11);
  if ( !v12 )
    return 0;
  v15 = (const char *)PReadUnsignedInt(v12, v13, &nNumber[3], v14);
  v16 = v15;
  if ( !v15 )
    return 0;
  v17 = "LongEdge";
  if ( !"LongEdge" )
    return 0;
  v18 = *v15;
  v19 = &off_180060120;
  while ( v18 != *v17 || strcmp(v16, v17) )
  {
    v19 += 2;
    v17 = *v19;
    if ( !*v19 )
      return 0;
  }
  if ( !v19 )
    return 0;
  v21 = *(unsigned __int16 *)(a2 + 68);
  v22 = nNumber[0];
  *(_WORD *)(v21 + a2 + 168) = *((_WORD *)v19 + 4);
  v23 = MulDiv(v22, 25400, 72);
  v24 = nNumber[1];
  *(_DWORD *)(v21 + a2 + 152) = v23;
  v25 = MulDiv(v24, 25400, 72);
  v26 = nNumber[2];
  *(_DWORD *)(v21 + a2 + 156) = v25;
  v27 = MulDiv(v26, 25400, 72);
  v28 = nNumber[3];
  *(_DWORD *)(v21 + a2 + 160) = v27;
  *(_DWORD *)(v21 + a2 + 164) = MulDiv(v28, 25400, 72);
  BValidateCustomPageSizeData(*(_QWORD *)(a1 + 328), v21 + a2 + 152, v29, v30);
  return 1;
}

```

## disassembly

```asm
0x18002be24  push    rbx
0x18002be26  push    rbp
0x18002be27  push    rsi
0x18002be28  push    rdi
0x18002be29  sub     rsp, 48h
0x18002be2d  mov     rax, r8
0x18002be30  mov     rbp, rcx
0x18002be33  mov     rsi, rdx
0x18002be36  lea     r8, [rsp+68h+nNumber]
0x18002be3b  xorps   xmm0, xmm0
0x18002be3e  mov     rcx, rax
0x18002be41  xor     edx, edx
0x18002be43  movups  xmmword ptr [rsp+68h+nNumber], xmm0
0x18002be48  call    PReadUnsignedInt
0x18002be4d  test    rax, rax
0x18002be50  jz      loc_18002BED7
0x18002be56  lea     r8, [rsp+68h+nNumber+4]
0x18002be5b  mov     rcx, rax
0x18002be5e  call    PReadUnsignedInt
0x18002be63  test    rax, rax
0x18002be66  jz      short loc_18002BED7
0x18002be68  lea     r8, [rsp+68h+nNumber+8]
0x18002be6d  mov     rcx, rax
0x18002be70  call    PReadUnsignedInt
0x18002be75  test    rax, rax
0x18002be78  jz      short loc_18002BED7
0x18002be7a  lea     r8, [rsp+68h+nNumber+0Ch]
0x18002be7f  mov     rcx, rax
0x18002be82  call    PReadUnsignedInt
0x18002be87  mov     r10, rax
0x18002be8a  test    rax, rax
0x18002be8d  jz      short loc_18002BED7
0x18002be8f  mov     rcx, cs:off_180060120; "LongEdge"
0x18002be96  test    rcx, rcx
0x18002be99  jz      short loc_18002BED7
0x18002be9b  mov     r11b, [rax]
0x18002be9e  lea     rdx, off_180060120; "LongEdge"
0x18002bea5  cmp     r11b, [rcx]
0x18002bea8  jnz     short loc_18002BECB
0x18002beaa  mov     rax, r10
0x18002bead  sub     rcx, r10
0x18002beb0  movzx   r8d, byte ptr [rax]
0x18002beb4  movzx   r9d, byte ptr [rax+rcx]
0x18002beb9  sub     r8d, r9d
0x18002bebc  jnz     short loc_18002BEC6
0x18002bebe  inc     rax
0x18002bec1  test    r9d, r9d
0x18002bec4  jnz     short loc_18002BEB0
0x18002bec6  test    r8d, r8d
0x18002bec9  jz      short loc_18002BEE2
0x18002becb  add     rdx, 10h
0x18002becf  mov     rcx, [rdx]
0x18002bed2  test    rcx, rcx
0x18002bed5  jnz     short loc_18002BEA5
0x18002bed7  xor     eax, eax
0x18002bed9  add     rsp, 48h
0x18002bedd  pop     rdi
0x18002bede  pop     rsi
0x18002bedf  pop     rbp
0x18002bee0  pop     rbx
0x18002bee1  retn
0x18002bee2  test    rdx, rdx
0x18002bee5  jz      short loc_18002BED7
0x18002bee7  movzx   edi, word ptr [rsi+44h]
0x18002beeb  mov     r8d, 48h ; 'H'; nDenominator
0x18002bef1  movzx   eax, word ptr [rdx+8]
0x18002bef5  mov     edx, 6338h; nNumerator
0x18002befa  mov     ecx, [rsp+68h+nNumber]; nNumber
0x18002befe  mov     [rdi+rsi+0A8h], ax
0x18002bf06  lea     rbx, [rdi+rsi]
0x18002bf0a  call    cs:__imp_MulDiv
0x18002bf10  mov     ecx, [rsp+68h+nNumber+4]; nNumber
0x18002bf14  mov     edx, 6338h; nNumerator
0x18002bf19  mov     r8d, 48h ; 'H'; nDenominator
0x18002bf1f  mov     [rbx+98h], eax
0x18002bf25  call    cs:__imp_MulDiv
0x18002bf2b  mov     ecx, [rsp+68h+nNumber+8]; nNumber
0x18002bf2f  mov     edx, 6338h; nNumerator
0x18002bf34  mov     r8d, 48h ; 'H'; nDenominator
0x18002bf3a  mov     [rdi+rsi+9Ch], eax
0x18002bf41  call    cs:__imp_MulDiv
0x18002bf47  mov     ecx, [rsp+68h+nNumber+0Ch]; nNumber
0x18002bf4b  mov     edx, 6338h; nNumerator
0x18002bf50  mov     r8d, 48h ; 'H'; nDenominator
0x18002bf56  mov     [rdi+rsi+0A0h], eax
0x18002bf5d  call    cs:__imp_MulDiv
0x18002bf63  mov     [rdi+rsi+0A4h], eax
0x18002bf6a  lea     rdx, [rbx+98h]
0x18002bf71  mov     rcx, [rbp+148h]
0x18002bf78  call    BValidateCustomPageSizeData
0x18002bf7d  mov     eax, 1
0x18002bf82  jmp     loc_18002BED9
```
