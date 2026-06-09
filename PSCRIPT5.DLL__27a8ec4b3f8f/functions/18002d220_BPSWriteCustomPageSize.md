# BPSWriteCustomPageSize

- ea: `0x18002d220`
- end: `0x18002d39c`
- name: `BPSWriteCustomPageSize`
- size: `380`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e640`

## callees

- `0x18002d220`
- `0x18002d814`
- `0x180055440`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18002d307`
- `KERNEL32!MulDiv` at `0x18002d328`
- `KERNEL32!MulDiv` at `0x18002d34a`
- `KERNEL32!MulDiv` at `0x18002d36c`
- `KERNEL32!MulDiv` at `0x18002d307`
- `KERNEL32!MulDiv` at `0x18002d328`
- `KERNEL32!MulDiv` at `0x18002d34a`
- `KERNEL32!MulDiv` at `0x18002d36c`

## pseudocode

```c
__int64 __fastcall BPSWriteCustomPageSize(__int64 a1, __int64 a2, char *a3)
{
  char *v5; // rax
  int v6; // edx
  char *v7; // rax
  int v8; // edx
  char *v9; // rax
  int v10; // edx
  char *v11; // rax
  const char *v12; // r10
  const char *v13; // rcx
  char v14; // r11
  char **v15; // rdx
  __int64 v17; // rdi
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  int nNumber[18]; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)nNumber = 0;
  v5 = PReadUnsignedInt(a3, 0, nNumber);
  if ( !v5 )
    return 0;
  v7 = PReadUnsignedInt(v5, v6, &nNumber[1]);
  if ( !v7 )
    return 0;
  v9 = PReadUnsignedInt(v7, v8, &nNumber[2]);
  if ( !v9 )
    return 0;
  v11 = PReadUnsignedInt(v9, v10, &nNumber[3]);
  v12 = v11;
  if ( !v11 )
    return 0;
  v13 = "LongEdge";
  if ( !"LongEdge" )
    return 0;
  v14 = *v11;
  v15 = &off_180062120;
  while ( v14 != *v13 || strcmp(v12, v13) )
  {
    v15 += 2;
    v13 = *v15;
    if ( !*v15 )
      return 0;
  }
  if ( !v15 )
    return 0;
  v17 = *(unsigned __int16 *)(a2 + 68);
  v18 = nNumber[0];
  *(_WORD *)(v17 + a2 + 168) = *((_WORD *)v15 + 4);
  v19 = MulDiv(v18, 25400, 72);
  v20 = nNumber[1];
  *(_DWORD *)(v17 + a2 + 152) = v19;
  v21 = MulDiv(v20, 25400, 72);
  v22 = nNumber[2];
  *(_DWORD *)(v17 + a2 + 156) = v21;
  v23 = MulDiv(v22, 25400, 72);
  v24 = nNumber[3];
  *(_DWORD *)(v17 + a2 + 160) = v23;
  *(_DWORD *)(v17 + a2 + 164) = MulDiv(v24, 25400, 72);
  BValidateCustomPageSizeData(*(_QWORD *)(a1 + 328), (__int128 *)(v17 + a2 + 152));
  return 1;
}

```

## disassembly

```asm
0x18002d220  push    rbx
0x18002d222  push    rbp
0x18002d223  push    rsi
0x18002d224  push    rdi
0x18002d225  sub     rsp, 48h
0x18002d229  mov     rax, r8
0x18002d22c  mov     rbp, rcx
0x18002d22f  mov     rsi, rdx
0x18002d232  lea     r8, [rsp+68h+nNumber]
0x18002d237  xorps   xmm0, xmm0
0x18002d23a  mov     rcx, rax
0x18002d23d  xor     edx, edx
0x18002d23f  movups  xmmword ptr [rsp+68h+nNumber], xmm0
0x18002d244  call    PReadUnsignedInt
0x18002d249  test    rax, rax
0x18002d24c  jz      loc_18002D2D3
0x18002d252  lea     r8, [rsp+68h+nNumber+4]
0x18002d257  mov     rcx, rax
0x18002d25a  call    PReadUnsignedInt
0x18002d25f  test    rax, rax
0x18002d262  jz      short loc_18002D2D3
0x18002d264  lea     r8, [rsp+68h+nNumber+8]
0x18002d269  mov     rcx, rax
0x18002d26c  call    PReadUnsignedInt
0x18002d271  test    rax, rax
0x18002d274  jz      short loc_18002D2D3
0x18002d276  lea     r8, [rsp+68h+nNumber+0Ch]
0x18002d27b  mov     rcx, rax
0x18002d27e  call    PReadUnsignedInt
0x18002d283  mov     r10, rax
0x18002d286  test    rax, rax
0x18002d289  jz      short loc_18002D2D3
0x18002d28b  mov     rcx, cs:off_180062120; "LongEdge"
0x18002d292  test    rcx, rcx
0x18002d295  jz      short loc_18002D2D3
0x18002d297  mov     r11b, [rax]
0x18002d29a  lea     rdx, off_180062120; "LongEdge"
0x18002d2a1  cmp     r11b, [rcx]
0x18002d2a4  jnz     short loc_18002D2C7
0x18002d2a6  mov     rax, r10
0x18002d2a9  sub     rcx, r10
0x18002d2ac  movzx   r8d, byte ptr [rax]
0x18002d2b0  movzx   r9d, byte ptr [rax+rcx]
0x18002d2b5  sub     r8d, r9d
0x18002d2b8  jnz     short loc_18002D2C2
0x18002d2ba  inc     rax
0x18002d2bd  test    r9d, r9d
0x18002d2c0  jnz     short loc_18002D2AC
0x18002d2c2  test    r8d, r8d
0x18002d2c5  jz      short loc_18002D2DF
0x18002d2c7  add     rdx, 10h
0x18002d2cb  mov     rcx, [rdx]
0x18002d2ce  test    rcx, rcx
0x18002d2d1  jnz     short loc_18002D2A1
0x18002d2d3  xor     eax, eax
0x18002d2d5  add     rsp, 48h
0x18002d2d9  pop     rdi
0x18002d2da  pop     rsi
0x18002d2db  pop     rbp
0x18002d2dc  pop     rbx
0x18002d2dd  retn
0x18002d2df  test    rdx, rdx
0x18002d2e2  jz      short loc_18002D2D3
0x18002d2e4  movzx   edi, word ptr [rsi+44h]
0x18002d2e8  mov     r8d, 48h ; 'H'; nDenominator
0x18002d2ee  movzx   eax, word ptr [rdx+8]
0x18002d2f2  mov     edx, 6338h; nNumerator
0x18002d2f7  mov     ecx, [rsp+68h+nNumber]; nNumber
0x18002d2fb  mov     [rdi+rsi+0A8h], ax
0x18002d303  lea     rbx, [rdi+rsi]
0x18002d307  call    cs:__imp_MulDiv
0x18002d30e  nop     dword ptr [rax+rax+00h]
0x18002d313  mov     ecx, [rsp+68h+nNumber+4]; nNumber
0x18002d317  mov     edx, 6338h; nNumerator
0x18002d31c  mov     r8d, 48h ; 'H'; nDenominator
0x18002d322  mov     [rbx+98h], eax
0x18002d328  call    cs:__imp_MulDiv
0x18002d32f  nop     dword ptr [rax+rax+00h]
0x18002d334  mov     ecx, [rsp+68h+nNumber+8]; nNumber
0x18002d338  mov     edx, 6338h; nNumerator
0x18002d33d  mov     r8d, 48h ; 'H'; nDenominator
0x18002d343  mov     [rdi+rsi+9Ch], eax
0x18002d34a  call    cs:__imp_MulDiv
0x18002d351  nop     dword ptr [rax+rax+00h]
0x18002d356  mov     ecx, [rsp+68h+nNumber+0Ch]; nNumber
0x18002d35a  mov     edx, 6338h; nNumerator
0x18002d35f  mov     r8d, 48h ; 'H'; nDenominator
0x18002d365  mov     [rdi+rsi+0A0h], eax
0x18002d36c  call    cs:__imp_MulDiv
0x18002d373  nop     dword ptr [rax+rax+00h]
0x18002d378  mov     [rdi+rsi+0A4h], eax
0x18002d37f  lea     rdx, [rbx+98h]
0x18002d386  mov     rcx, [rbp+148h]
0x18002d38d  call    BValidateCustomPageSizeData
0x18002d392  mov     eax, 1
0x18002d397  jmp     loc_18002D2D5
```
