# FaxSetReceiptsConfigurationA

- ea: `0x180013d30`
- end: `0x180014027`
- name: `FaxSetReceiptsConfigurationA`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x180013d30`
- `0x180014030`
- `0x18002bb58`
- `0x18002bc50`
- `0x18003d4ca`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013dbd`
- `KERNEL32!SetLastError` at `0x180013dff`
- `KERNEL32!SetLastError` at `0x180013fde`
- `KERNEL32!SetLastError` at `0x180013dbd`
- `KERNEL32!SetLastError` at `0x180013dff`
- `KERNEL32!SetLastError` at `0x180013fde`

## pseudocode

```c
__int64 __fastcall FaxSetReceiptsConfigurationA(_DWORD *a1, __int128 *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  const CHAR *v6; // rcx
  unsigned int v7; // esi
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const CHAR *v11; // rcx
  const CHAR *v12; // rcx
  const CHAR *v13; // rcx
  _BYTE *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int128 v18; // [rsp+20h] [rbp-58h] BYREF
  LPVOID lpMem[2]; // [rsp+30h] [rbp-48h]
  LPVOID v20[2]; // [rsp+40h] [rbp-38h]
  LPVOID v21[2]; // [rsp+50h] [rbp-28h]
  int v22; // [rsp+60h] [rbp-18h]
  int v23; // [rsp+64h] [rbp-14h]

  memset_0(&v18, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 120;
    goto LABEL_55;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 121;
LABEL_55:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( *(_DWORD *)a2 != 72 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 122;
    goto LABEL_55;
  }
  v6 = (const CHAR *)*((_QWORD *)a2 + 3);
  v7 = 0;
  v8 = *((_DWORD *)a2 + 16);
  v18 = *a2;
  LODWORD(v18) = 72;
  *(_OWORD *)v20 = a2[2];
  v23 = HIDWORD(*((_QWORD *)a2 + 8));
  *(_OWORD *)v21 = 0;
  v22 = v8;
  v20[1] = 0;
  lpMem[1] = 0;
  lpMem[0] = 0;
  if ( v6 )
  {
    lpMem[1] = AnsiStringToUnicodeString(v6);
    if ( !lpMem[1] )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v10 = 123;
      goto LABEL_24;
    }
  }
  v11 = (const CHAR *)*((_QWORD *)a2 + 5);
  if ( v11 )
  {
    v20[1] = AnsiStringToUnicodeString(v11);
    if ( !v20[1] )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v10 = 124;
      goto LABEL_24;
    }
  }
  v12 = (const CHAR *)*((_QWORD *)a2 + 6);
  if ( v12 )
  {
    v21[0] = AnsiStringToUnicodeString(v12);
    if ( !v21[0] )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v10 = 125;
      goto LABEL_24;
    }
  }
  v13 = (const CHAR *)*((_QWORD *)a2 + 7);
  if ( v13 )
  {
    v21[1] = AnsiStringToUnicodeString(v13);
    if ( !v21[1] )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v10 = 126;
LABEL_24:
      WPP_SF_(v9[2], v10, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      goto LABEL_44;
    }
  }
  v7 = FaxSetReceiptsConfigurationW(a1, &v18);
LABEL_44:
  pMemFree(lpMem[1]);
  pMemFree(v20[1]);
  pMemFree(v21[0]);
  v14 = v21[1];
  if ( v21[1] )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v21[1] + v15) );
    v16 = 2 * v15;
    if ( v16 )
    {
      do
      {
        *v14++ = 0;
        --v16;
      }
      while ( v16 );
      v14 = v21[1];
    }
  }
  pMemFree(v14);
  return v7;
}

```

## disassembly

```asm
0x180013d30  push    rbp
0x180013d32  push    rbx
0x180013d33  push    rsi
0x180013d34  push    rdi
0x180013d35  push    r12
0x180013d37  push    r13
0x180013d39  push    r14
0x180013d3b  push    r15
0x180013d3d  mov     rbp, rsp
0x180013d40  sub     rsp, 78h
0x180013d44  mov     rbx, rdx
0x180013d47  mov     rdi, rcx
0x180013d4a  xor     edx, edx; Val
0x180013d4c  lea     rcx, [rbp+var_58]; void *
0x180013d50  lea     r8d, [rdx+48h]; Size
0x180013d54  call    memset_0
0x180013d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d60  lea     r12, WPP_GLOBAL_Control
0x180013d67  lea     r13, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180013d6e  mov     r15d, 1000h
0x180013d74  cmp     rcx, r12
0x180013d77  jz      short loc_180013D96
0x180013d79  test    [rcx+1Ch], r15d
0x180013d7d  jz      short loc_180013D96
0x180013d7f  cmp     byte ptr [rcx+19h], 5
0x180013d83  jb      short loc_180013D96
0x180013d85  mov     rcx, [rcx+10h]
0x180013d89  mov     edx, 77h ; 'w'
0x180013d8e  mov     r8, r13
0x180013d91  call    WPP_SF_
0x180013d96  xor     r14d, r14d
0x180013d99  test    rdi, rdi
0x180013d9c  jz      loc_180013FD9
0x180013da2  cmp     [rdi], r14d
0x180013da5  jz      loc_180013FD9
0x180013dab  cmp     [rdi+10h], r14d
0x180013daf  jnz     loc_180013FD9
0x180013db5  test    rbx, rbx
0x180013db8  jnz     short loc_180013DF5
0x180013dba  lea     ecx, [rbx+57h]; dwErrCode
0x180013dbd  call    cs:__imp_SetLastError
0x180013dc4  nop     dword ptr [rax+rax+00h]
0x180013dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dd0  cmp     rcx, r12
0x180013dd3  jz      loc_180014013
0x180013dd9  test    [rcx+1Ch], r15d
0x180013ddd  jz      loc_180014013
0x180013de3  cmp     byte ptr [rcx+19h], 2
0x180013de7  jb      loc_180014013
0x180013ded  lea     edx, [rbx+79h]
0x180013df0  jmp     loc_180014007
0x180013df5  cmp     dword ptr [rbx], 48h ; 'H'
0x180013df8  jz      short loc_180013E39
0x180013dfa  mov     ecx, 57h ; 'W'; dwErrCode
0x180013dff  call    cs:__imp_SetLastError
0x180013e06  nop     dword ptr [rax+rax+00h]
0x180013e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e12  cmp     rcx, r12
0x180013e15  jz      loc_180014013
0x180013e1b  test    [rcx+1Ch], r15d
0x180013e1f  jz      loc_180014013
0x180013e25  cmp     byte ptr [rcx+19h], 2
0x180013e29  jb      loc_180014013
0x180013e2f  mov     edx, 7Ah ; 'z'
0x180013e34  jmp     loc_180014007
0x180013e39  movups  xmm0, xmmword ptr [rbx]
0x180013e3c  mov     rcx, [rbx+18h]; lpMultiByteStr
0x180013e40  mov     esi, r14d
0x180013e43  mov     eax, [rbx+40h]
0x180013e46  movaps  [rbp+var_58], xmm0
0x180013e4a  mov     dword ptr [rbp+var_58], 48h ; 'H'
0x180013e51  movups  xmm0, xmmword ptr [rbx+20h]
0x180013e55  movups  xmm1, xmmword ptr [rbx+10h]
0x180013e59  movaps  xmmword ptr [rbp+var_38], xmm0
0x180013e5d  movsd   xmm0, qword ptr [rbx+40h]
0x180013e62  movsd   qword ptr [rbp+var_18], xmm0
0x180013e67  xorps   xmm0, xmm0
0x180013e6a  movaps  xmmword ptr [rbp+lpMem], xmm1
0x180013e6e  movdqa  xmmword ptr [rbp+var_28], xmm0
0x180013e73  mov     [rbp+var_18], eax
0x180013e76  mov     [rbp+var_38+8], r14
0x180013e7a  mov     [rbp+lpMem+8], r14
0x180013e7e  mov     [rbp+lpMem], r14
0x180013e82  test    rcx, rcx
0x180013e85  jz      short loc_180013ECD
0x180013e87  call    AnsiStringToUnicodeString
0x180013e8c  mov     [rbp+lpMem+8], rax
0x180013e90  test    rax, rax
0x180013e93  jnz     short loc_180013ECD
0x180013e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e9c  cmp     rcx, r12
0x180013e9f  jz      loc_180013F89
0x180013ea5  test    [rcx+1Ch], r15d
0x180013ea9  jz      loc_180013F89
0x180013eaf  cmp     byte ptr [rcx+19h], 2
0x180013eb3  jb      loc_180013F89
0x180013eb9  lea     edx, [rax+7Bh]
0x180013ebc  mov     rcx, [rcx+10h]
0x180013ec0  mov     r8, r13
0x180013ec3  call    WPP_SF_
0x180013ec8  jmp     loc_180013F89
0x180013ecd  mov     rcx, [rbx+28h]; lpMultiByteStr
0x180013ed1  test    rcx, rcx
0x180013ed4  jz      short loc_180013F0D
0x180013ed6  call    AnsiStringToUnicodeString
0x180013edb  mov     [rbp+var_38+8], rax
0x180013edf  test    rax, rax
0x180013ee2  jnz     short loc_180013F0D
0x180013ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eeb  cmp     rcx, r12
0x180013eee  jz      loc_180013F89
0x180013ef4  test    [rcx+1Ch], r15d
0x180013ef8  jz      loc_180013F89
0x180013efe  cmp     byte ptr [rcx+19h], 2
0x180013f02  jb      loc_180013F89
0x180013f08  lea     edx, [rax+7Ch]
0x180013f0b  jmp     short loc_180013EBC
0x180013f0d  mov     rcx, [rbx+30h]; lpMultiByteStr
0x180013f11  test    rcx, rcx
0x180013f14  jz      short loc_180013F44
0x180013f16  call    AnsiStringToUnicodeString
0x180013f1b  mov     [rbp+var_28], rax
0x180013f1f  test    rax, rax
0x180013f22  jnz     short loc_180013F44
0x180013f24  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f2b  cmp     rcx, r12
0x180013f2e  jz      short loc_180013F89
0x180013f30  test    [rcx+1Ch], r15d
0x180013f34  jz      short loc_180013F89
0x180013f36  cmp     byte ptr [rcx+19h], 2
0x180013f3a  jb      short loc_180013F89
0x180013f3c  lea     edx, [rax+7Dh]
0x180013f3f  jmp     loc_180013EBC
0x180013f44  mov     rcx, [rbx+38h]; lpMultiByteStr
0x180013f48  test    rcx, rcx
0x180013f4b  jz      short loc_180013F7B
0x180013f4d  call    AnsiStringToUnicodeString
0x180013f52  mov     [rbp+var_28+8], rax
0x180013f56  test    rax, rax
0x180013f59  jnz     short loc_180013F7B
0x180013f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f62  cmp     rcx, r12
0x180013f65  jz      short loc_180013F89
0x180013f67  test    [rcx+1Ch], r15d
0x180013f6b  jz      short loc_180013F89
0x180013f6d  cmp     byte ptr [rcx+19h], 2
0x180013f71  jb      short loc_180013F89
0x180013f73  lea     edx, [rax+7Eh]
0x180013f76  jmp     loc_180013EBC
0x180013f7b  lea     rdx, [rbp+var_58]
0x180013f7f  mov     rcx, rdi
0x180013f82  call    FaxSetReceiptsConfigurationW
0x180013f87  mov     esi, eax
0x180013f89  mov     rcx, [rbp+lpMem+8]; lpMem
0x180013f8d  call    pMemFree
0x180013f92  mov     rcx, [rbp+var_38+8]; lpMem
0x180013f96  call    pMemFree
0x180013f9b  mov     rcx, [rbp+var_28]; lpMem
0x180013f9f  call    pMemFree
0x180013fa4  mov     rcx, [rbp+var_28+8]
0x180013fa8  test    rcx, rcx
0x180013fab  jz      short loc_180013FD0
0x180013fad  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013fb1  inc     rax
0x180013fb4  cmp     [rcx+rax*2], r14w
0x180013fb9  jnz     short loc_180013FB1
0x180013fbb  add     rax, rax
0x180013fbe  jz      short loc_180013FD0
0x180013fc0  mov     [rcx], r14b
0x180013fc3  inc     rcx
0x180013fc6  sub     rax, 1
0x180013fca  jnz     short loc_180013FC0
0x180013fcc  mov     rcx, [rbp+var_28+8]; lpMem
0x180013fd0  call    pMemFree
0x180013fd5  mov     eax, esi
0x180013fd7  jmp     short loc_180014015
0x180013fd9  mov     ecx, 6; dwErrCode
0x180013fde  call    cs:__imp_SetLastError
0x180013fe5  nop     dword ptr [rax+rax+00h]
0x180013fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ff1  cmp     rcx, r12
0x180013ff4  jz      short loc_180014013
0x180013ff6  test    [rcx+1Ch], r15d
0x180013ffa  jz      short loc_180014013
0x180013ffc  cmp     byte ptr [rcx+19h], 2
0x180014000  jb      short loc_180014013
0x180014002  mov     edx, 78h ; 'x'
0x180014007  mov     rcx, [rcx+10h]
0x18001400b  mov     r8, r13
0x18001400e  call    WPP_SF_
0x180014013  xor     eax, eax
0x180014015  add     rsp, 78h
0x180014019  pop     r15
0x18001401b  pop     r14
0x18001401d  pop     r13
0x18001401f  pop     r12
0x180014021  pop     rdi
0x180014022  pop     rsi
0x180014023  pop     rbx
0x180014024  pop     rbp
0x180014025  retn
```
