# AeComputeProgramIdentityHash

- ea: `0x180037ac0`
- end: `0x180038076`
- name: `AeComputeProgramIdentityHash`
- size: `1462`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180014f00`
- `0x1800d0e00`
- `0x1800e2b80`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb74`
- `0x180036e7c`
- `0x180036f30`
- `0x180037ac0`
- `0x1800380e4`
- `0x180038160`
- `0x1800381c4`
- `0x1800382d4`
- `0x180038968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180037e04`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180037e04`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180037e9f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180037e9f`

## string_xrefs

- `0x180038000`: `AeComputeProgramIdentityHash`
- `0x18003802b`: `AeComputeProgramIdentityHash`

## pseudocode

```c
__int64 __fastcall AeComputeProgramIdentityHash(unsigned __int16 **a1, __int64 a2)
{
  int v4; // r8d
  wchar_t *v5; // r15
  const unsigned __int16 *v6; // rax
  unsigned int v7; // edi
  int v8; // r8d
  __int64 v9; // r11
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // rax
  __int64 v14; // r11
  unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // rax
  __int64 v17; // r11
  unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // rax
  __int64 v20; // r11
  unsigned __int16 *v21; // r9
  int v22; // eax
  _QWORD *v23; // rcx
  int v24; // edx
  unsigned int v25; // esi
  __int64 i; // rdi
  int v27; // eax
  int v28; // edx
  int v29; // edi
  const wchar_t *v30; // rsi
  int v31; // r8d
  unsigned int v32; // eax
  int v33; // r9d
  _QWORD *v34; // rcx
  unsigned __int16 *v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *EndPtr; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v40[784]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v40, 0, sizeof(v40));
  v5 = 0;
  v37 = 0;
  EndPtr = 0;
  memset(v39, 0, 22);
  if ( !a1 || !*a1 || !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v4, (unsigned int)"AeComputeProgramIdentityHash", 133);
    return (unsigned int)-2147024809;
  }
  v6 = AeTrimString(*a1);
  *a1 = (unsigned __int16 *)v6;
  v7 = StringCchLengthW(v6, 0x7FFFFFFFu, &v37);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 56;
LABEL_8:
      WPP_SF_sdD(v10[2], v11);
      return v7;
    }
    return v7;
  }
  if ( v37 > 0x104 )
    *(_WORD *)(v9 + 520) = 0;
  v12 = a1[3];
  if ( !v12 )
  {
LABEL_18:
    v15 = a1[2];
    if ( v15 )
    {
      v16 = AeTrimString(v15);
      a1[2] = (unsigned __int16 *)v16;
      v7 = StringCchLengthW(v16, 0x7FFFFFFFu, &v37);
      if ( (v7 & 0x80000000) != 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 58;
          goto LABEL_8;
        }
        return v7;
      }
      if ( v37 > 0x104 )
        *(_WORD *)(v17 + 520) = 0;
    }
    v18 = a1[1];
    if ( v18 )
    {
      v19 = AeTrimString(v18);
      a1[1] = (unsigned __int16 *)v19;
      v7 = StringCchLengthW(v19, 0x7FFFFFFFu, &v37);
      if ( (v7 & 0x80000000) != 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 59;
          goto LABEL_8;
        }
        return v7;
      }
      if ( v37 > 0x104 )
        *(_WORD *)(v20 + 520) = 0;
    }
    v21 = *a1;
    EndPtr = 0;
    if ( !v21 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v8, (unsigned int)"FormatNPVString", 100);
        v23 = WPP_GLOBAL_Control;
      }
      v7 = -2147024809;
      goto LABEL_75;
    }
    v36 = a1[1];
    v22 = StringCchPrintfW(v40, 0x310u, L"p%s_%s_%s");
    v7 = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_75;
      v24 = 65;
LABEL_37:
      WPP_SF_sd(v23[2], v24, v8, (unsigned int)"FormatNPVString", v22);
      v23 = WPP_GLOBAL_Control;
LABEL_75:
      if ( v23 == &WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 1) == 0 )
        return v7;
      LOBYTE(v27) = v7;
      v28 = 60;
      goto LABEL_78;
    }
    v22 = StringCchLengthW(v40, 0x310u, (unsigned __int64 *)&EndPtr);
    v7 = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_75;
      v24 = 66;
      goto LABEL_37;
    }
    v25 = (unsigned int)EndPtr;
    for ( i = 0; (unsigned int)i < v25; i = (unsigned int)(i + 1) )
    {
      if ( !HIBYTE(v40[i]) )
        v40[i] = _o_towlower();
    }
    v27 = ComputeMd5Hash(v40, 2 * v25, (char *)v39 + 2);
    v7 = v27;
    if ( v27 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v28 = 61;
      goto LABEL_78;
    }
    v29 = -1;
    if ( !v5 )
    {
LABEL_56:
      *(_DWORD *)((char *)&v39[1] + 2) = v29 << 16;
      LOWORD(v39[0]) = 0;
      v27 = FormatAeHashString(v39, a2);
      v7 = v27;
      if ( v27 >= 0 )
        return 0;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v28 = 63;
LABEL_78:
      WPP_SF_sd(v23[2], v28, v8, (unsigned int)"AeComputeProgramIdentityHash", v27);
      return v7;
    }
    v30 = a1[3];
    EndPtr = 0;
    v37 = 0;
    if ( (int)StringCchLengthW(v30, 0x104u, &v37) < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, v31, (unsigned int)"StringToDword", 200);
        goto LABEL_66;
      }
    }
    else
    {
      v32 = wcstoul(v30, &EndPtr, 10);
      if ( EndPtr && !*EndPtr && v32 != -1 )
      {
        v29 = v32;
        goto LABEL_56;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)EndPtr, v31, v33, (_DWORD)v36, (__int64)v30);
LABEL_66:
        v34 = WPP_GLOBAL_Control;
      }
    }
    v7 = -2147024809;
    if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 )
      WPP_SF_sd(v34[2], 62, v31, (unsigned int)"AeComputeProgramIdentityHash", 87);
    return v7;
  }
  v13 = AeTrimString(v12);
  a1[3] = (unsigned __int16 *)v13;
  v7 = StringCchLengthW(v13, 0x7FFFFFFFu, (unsigned __int64 *)&EndPtr);
  if ( (v7 & 0x80000000) == 0 )
  {
    v5 = EndPtr;
    if ( (unsigned __int64)EndPtr > 0x104 )
      *(_WORD *)(v14 + 520) = 0;
    goto LABEL_18;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 57;
    goto LABEL_8;
  }
  return v7;
}

```

## disassembly

```asm
0x180037ac0  mov     [rsp-8+arg_10], rbx
0x180037ac5  mov     [rsp-8+arg_18], rsi
0x180037aca  push    rbp
0x180037acb  push    rdi
0x180037acc  push    r12
0x180037ace  push    r14
0x180037ad0  push    r15
0x180037ad2  lea     rbp, [rsp-590h]
0x180037ada  sub     rsp, 690h
0x180037ae1  mov     rax, cs:__security_cookie
0x180037ae8  xor     rax, rsp
0x180037aeb  mov     [rbp+5B0h+var_30], rax
0x180037af2  mov     r12, rdx
0x180037af5  mov     rbx, rcx
0x180037af8  xor     edx, edx; Val
0x180037afa  lea     rcx, [rsp+6B0h+var_650]; void *
0x180037aff  mov     r8d, 620h; Size
0x180037b05  call    memset_0
0x180037b0a  xor     eax, eax
0x180037b0c  xor     r15d, r15d
0x180037b0f  mov     [rsp+6B0h+var_680], rax
0x180037b14  xorps   xmm0, xmm0
0x180037b17  mov     [rsp+6B0h+EndPtr], r15
0x180037b1c  movups  [rsp+6B0h+var_670], xmm0
0x180037b21  mov     qword ptr [rsp+6B0h+var_670+0Eh], rax
0x180037b26  test    rbx, rbx
0x180037b29  jz      loc_18003800E
0x180037b2f  mov     rcx, [rbx]; unsigned __int16 *
0x180037b32  test    rcx, rcx
0x180037b35  jz      loc_18003800E
0x180037b3b  test    r12, r12
0x180037b3e  jz      loc_18003800E
0x180037b44  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180037b49  mov     esi, 7FFFFFFFh
0x180037b4e  mov     [rbx], rax
0x180037b51  mov     edx, esi; unsigned __int64
0x180037b53  lea     r8, [rsp+6B0h+var_680]; unsigned __int64 *
0x180037b58  mov     rcx, rax; unsigned __int16 *
0x180037b5b  mov     r11, rax
0x180037b5e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037b63  mov     edi, eax
0x180037b65  test    eax, eax
0x180037b67  jns     short loc_180037BA8
0x180037b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b70  lea     rbx, WPP_GLOBAL_Control
0x180037b77  cmp     rcx, rbx
0x180037b7a  jz      loc_180038049
0x180037b80  test    byte ptr [rcx+1Ch], 1
0x180037b84  jz      loc_180038049
0x180037b8a  mov     dword ptr [rsp+6B0h+var_688], eax
0x180037b8e  lea     edx, [r15+38h]
0x180037b92  mov     dword ptr [rsp+6B0h+var_690], 598h
0x180037b9a  mov     rcx, [rcx+10h]
0x180037b9e  call    WPP_SF_sdD
0x180037ba3  jmp     loc_180038049
0x180037ba8  mov     r14d, 104h
0x180037bae  cmp     [rsp+6B0h+var_680], r14
0x180037bb3  jbe     short loc_180037BBF
0x180037bb5  xor     eax, eax
0x180037bb7  mov     [r11+208h], ax
0x180037bbf  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180037bc3  test    rcx, rcx
0x180037bc6  jz      short loc_180037C35
0x180037bc8  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180037bcd  lea     r8, [rsp+6B0h+EndPtr]; unsigned __int64 *
0x180037bd2  mov     [rbx+18h], rax
0x180037bd6  mov     rdx, rsi; unsigned __int64
0x180037bd9  mov     rcx, rax; unsigned __int16 *
0x180037bdc  mov     r11, rax
0x180037bdf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037be4  mov     edi, eax
0x180037be6  test    eax, eax
0x180037be8  jns     short loc_180037C21
0x180037bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bf1  lea     rbx, WPP_GLOBAL_Control
0x180037bf8  cmp     rcx, rbx
0x180037bfb  jz      loc_180038049
0x180037c01  test    byte ptr [rcx+1Ch], 1
0x180037c05  jz      loc_180038049
0x180037c0b  mov     dword ptr [rsp+6B0h+var_688], eax
0x180037c0f  mov     edx, 39h ; '9'
0x180037c14  mov     dword ptr [rsp+6B0h+var_690], 5ACh
0x180037c1c  jmp     loc_180037B9A
0x180037c21  mov     r15, [rsp+6B0h+EndPtr]
0x180037c26  cmp     r15, r14
0x180037c29  jbe     short loc_180037C35
0x180037c2b  xor     eax, eax
0x180037c2d  mov     [r11+208h], ax
0x180037c35  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180037c39  test    rcx, rcx
0x180037c3c  jz      short loc_180037CA8
0x180037c3e  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180037c43  lea     r8, [rsp+6B0h+var_680]; unsigned __int64 *
0x180037c48  mov     [rbx+10h], rax
0x180037c4c  mov     rdx, rsi; unsigned __int64
0x180037c4f  mov     rcx, rax; unsigned __int16 *
0x180037c52  mov     r11, rax
0x180037c55  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037c5a  mov     edi, eax
0x180037c5c  test    eax, eax
0x180037c5e  jns     short loc_180037C97
0x180037c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c67  lea     rbx, WPP_GLOBAL_Control
0x180037c6e  cmp     rcx, rbx
0x180037c71  jz      loc_180038049
0x180037c77  test    byte ptr [rcx+1Ch], 1
0x180037c7b  jz      loc_180038049
0x180037c81  mov     dword ptr [rsp+6B0h+var_688], eax
0x180037c85  mov     edx, 3Ah ; ':'
0x180037c8a  mov     dword ptr [rsp+6B0h+var_690], 5C1h
0x180037c92  jmp     loc_180037B9A
0x180037c97  cmp     [rsp+6B0h+var_680], r14
0x180037c9c  jbe     short loc_180037CA8
0x180037c9e  xor     eax, eax
0x180037ca0  mov     [r11+208h], ax
0x180037ca8  mov     rcx, [rbx+8]; unsigned __int16 *
0x180037cac  test    rcx, rcx
0x180037caf  jz      short loc_180037D1B
0x180037cb1  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180037cb6  lea     r8, [rsp+6B0h+var_680]; unsigned __int64 *
0x180037cbb  mov     [rbx+8], rax
0x180037cbf  mov     rdx, rsi; unsigned __int64
0x180037cc2  mov     rcx, rax; unsigned __int16 *
0x180037cc5  mov     r11, rax
0x180037cc8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037ccd  mov     edi, eax
0x180037ccf  test    eax, eax
0x180037cd1  jns     short loc_180037D0A
0x180037cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180037cda  lea     rbx, WPP_GLOBAL_Control
0x180037ce1  cmp     rcx, rbx
0x180037ce4  jz      loc_180038049
0x180037cea  test    byte ptr [rcx+1Ch], 1
0x180037cee  jz      loc_180038049
0x180037cf4  mov     dword ptr [rsp+6B0h+var_688], eax
0x180037cf8  mov     edx, 3Bh ; ';'
0x180037cfd  mov     dword ptr [rsp+6B0h+var_690], 5D6h
0x180037d05  jmp     loc_180037B9A
0x180037d0a  cmp     [rsp+6B0h+var_680], r14
0x180037d0f  jbe     short loc_180037D1B
0x180037d11  xor     eax, eax
0x180037d13  mov     [r11+208h], ax
0x180037d1b  mov     r9, [rbx]
0x180037d1e  mov     [rsp+6B0h+EndPtr], 0
0x180037d27  test    r9, r9
0x180037d2a  jz      loc_180037FA3
0x180037d30  mov     rax, [rbx+10h]
0x180037d34  lea     r8, aPSSS; "p%s_%s_%s"
0x180037d3b  mov     [rsp+6B0h+var_688], rax
0x180037d40  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x180037d45  mov     rax, [rbx+8]
0x180037d49  mov     esi, 310h
0x180037d4e  mov     edx, esi; unsigned __int64
0x180037d50  mov     [rsp+6B0h+var_690], rax
0x180037d55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037d5a  mov     edi, eax
0x180037d5c  test    eax, eax
0x180037d5e  jns     short loc_180037DA9
0x180037d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d67  lea     rbx, WPP_GLOBAL_Control
0x180037d6e  cmp     rcx, rbx
0x180037d71  jz      loc_180038049
0x180037d77  test    byte ptr [rcx+1Ch], 1
0x180037d7b  jz      loc_180037FE5
0x180037d81  mov     edx, 41h ; 'A'
0x180037d86  mov     rcx, [rcx+10h]
0x180037d8a  lea     r9, aFormatnpvstrin; "FormatNPVString"
0x180037d91  movzx   eax, ax
0x180037d94  mov     dword ptr [rsp+6B0h+var_690], eax
0x180037d98  call    WPP_SF_sd
0x180037d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037da4  jmp     loc_180037FE5
0x180037da9  lea     r8, [rsp+6B0h+EndPtr]; unsigned __int64 *
0x180037dae  mov     rdx, rsi; unsigned __int64
0x180037db1  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x180037db6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037dbb  mov     edi, eax
0x180037dbd  test    eax, eax
0x180037dbf  jns     short loc_180037DE9
0x180037dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037dc8  lea     rbx, WPP_GLOBAL_Control
0x180037dcf  cmp     rcx, rbx
0x180037dd2  jz      loc_180038049
0x180037dd8  test    byte ptr [rcx+1Ch], 1
0x180037ddc  jz      loc_180037FE5
0x180037de2  mov     edx, 42h ; 'B'
0x180037de7  jmp     short loc_180037D86
0x180037de9  mov     rsi, [rsp+6B0h+EndPtr]
0x180037dee  xor     edi, edi
0x180037df0  test    esi, esi
0x180037df2  jz      short loc_180037E15
0x180037df4  movzx   ecx, [rsp+rdi*2+6B0h+var_650]
0x180037df9  movzx   eax, cx
0x180037dfc  shr     ax, 8
0x180037e00  test    al, al
0x180037e02  jnz     short loc_180037E0F
0x180037e04  call    cs:__imp__o_towlower
0x180037e0a  mov     [rsp+rdi*2+6B0h+var_650], ax
0x180037e0f  inc     edi
0x180037e11  cmp     edi, esi
0x180037e13  jb      short loc_180037DF4
0x180037e15  lea     edx, [rsi+rsi]
0x180037e18  lea     r8, [rsp+6B0h+var_670+2]
0x180037e1d  lea     rcx, [rsp+6B0h+var_650]
0x180037e22  call    ComputeMd5Hash
0x180037e27  mov     edi, eax
0x180037e29  test    eax, eax
0x180037e2b  jns     short loc_180037E5B
0x180037e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e34  lea     rbx, WPP_GLOBAL_Control
0x180037e3b  cmp     rcx, rbx
0x180037e3e  jz      loc_180038049
0x180037e44  test    byte ptr [rcx+1Ch], 1
0x180037e48  jz      loc_180038049
0x180037e4e  movzx   eax, ax
0x180037e51  mov     edx, 3Dh ; '='
0x180037e56  jmp     loc_180037FF8
0x180037e5b  or      edi, 0FFFFFFFFh
0x180037e5e  test    r15, r15
0x180037e61  jz      short loc_180037EBC
0x180037e63  mov     rsi, [rbx+18h]
0x180037e67  lea     r8, [rsp+6B0h+var_680]; unsigned __int64 *
0x180037e6c  mov     rcx, rsi; unsigned __int16 *
0x180037e6f  mov     [rsp+6B0h+EndPtr], 0
0x180037e78  mov     rdx, r14; unsigned __int64
0x180037e7b  mov     [rsp+6B0h+var_680], 0
0x180037e84  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037e89  test    eax, eax
0x180037e8b  js      loc_180037F38
0x180037e91  mov     r8d, 0Ah; Radix
0x180037e97  lea     rdx, [rsp+6B0h+EndPtr]; EndPtr
0x180037e9c  mov     rcx, rsi; String
0x180037e9f  call    cs:__imp_wcstoul
0x180037ea5  mov     rdx, [rsp+6B0h+EndPtr]
0x180037eaa  test    rdx, rdx
0x180037ead  jz      short loc_180037F0F
0x180037eaf  xor     ecx, ecx
0x180037eb1  cmp     cx, [rdx]
0x180037eb4  jnz     short loc_180037F0F
0x180037eb6  cmp     eax, edi
0x180037eb8  jz      short loc_180037F0F
0x180037eba  mov     edi, eax
0x180037ebc  shl     edi, 10h
0x180037ebf  lea     rcx, [rsp+6B0h+var_670]
0x180037ec4  mov     rdx, r12
0x180037ec7  mov     [rsp+6B0h+var_65E], edi
0x180037ecb  mov     word ptr [rsp+6B0h+var_670], 0
0x180037ed2  call    FormatAeHashString
0x180037ed7  mov     edi, eax
0x180037ed9  test    eax, eax
0x180037edb  jns     loc_180037F9C
0x180037ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ee8  lea     rbx, WPP_GLOBAL_Control
0x180037eef  cmp     rcx, rbx
0x180037ef2  jz      loc_180038049
0x180037ef8  test    byte ptr [rcx+1Ch], 1
0x180037efc  jz      loc_180038049
0x180037f02  movzx   eax, ax
0x180037f05  mov     edx, 3Fh ; '?'
0x180037f0a  jmp     loc_180037FF8
0x180037f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f16  lea     rbx, WPP_GLOBAL_Control
0x180037f1d  cmp     rcx, rbx
0x180037f20  jz      short loc_180037F75
0x180037f22  test    byte ptr [rcx+1Ch], 1
0x180037f26  jz      short loc_180037F75
0x180037f28  mov     rcx, [rcx+10h]
0x180037f2c  mov     [rsp+6B0h+var_688], rsi
0x180037f31  call    WPP_SF_sdS
0x180037f36  jmp     short loc_180037F6E
0x180037f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f3f  lea     rbx, WPP_GLOBAL_Control
0x180037f46  cmp     rcx, rbx
0x180037f49  jz      short loc_180037F75
0x180037f4b  test    byte ptr [rcx+1Ch], 1
0x180037f4f  jz      short loc_180037F75
0x180037f51  mov     rcx, [rcx+10h]
0x180037f55  lea     r9, aStringtodword; "StringToDword"
0x180037f5c  mov     edx, 43h ; 'C'
0x180037f61  mov     dword ptr [rsp+6B0h+var_690], 6C8h
0x180037f69  call    WPP_SF_sd
0x180037f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f75  mov     edi, 80070057h
0x180037f7a  cmp     rcx, rbx
0x180037f7d  jz      loc_180038049
0x180037f83  test    byte ptr [rcx+1Ch], 1
0x180037f87  jz      loc_180038049
0x180037f8d  mov     edx, 3Eh ; '>'
0x180037f92  mov     dword ptr [rsp+6B0h+var_690], 57h ; 'W'
0x180037f9a  jmp     short loc_180037FFC
0x180037f9c  xor     edi, edi
0x180037f9e  jmp     loc_180038049
0x180037fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180037faa  lea     rbx, WPP_GLOBAL_Control
0x180037fb1  cmp     rcx, rbx
0x180037fb4  jz      short loc_180037FE0
0x180037fb6  test    byte ptr [rcx+1Ch], 1
0x180037fba  jz      short loc_180037FE0
0x180037fbc  mov     rcx, [rcx+10h]
0x180037fc0  lea     r9, aFormatnpvstrin; "FormatNPVString"
  ... truncated ...
```
