# Pkcs8ConvertToKeyBlob

- ea: `0x180067c40`
- end: `0x180067df6`
- name: `Pkcs8ConvertToKeyBlob`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x18000ecb0`
- `0x180058e54`
- `0x1800679b8`
- `0x180067c40`
- `0x18006ccf0`
- `0x18007f790`

## string_xrefs

- `0x180067dc6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs8ConvertToKeyBlob(int a1, _DWORD *a2, unsigned int *a3, int a4, int a5, int *a6)
{
  int Values; // eax
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // ecx
  _DWORD v18[8]; // [rsp+30h] [rbp-A9h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-89h] BYREF
  int v20; // [rsp+60h] [rbp-79h]
  int v21; // [rsp+70h] [rbp-69h]
  __int64 v22; // [rsp+78h] [rbp-61h]
  int v23[4]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE v24[16]; // [rsp+90h] [rbp-49h] BYREF
  int v25; // [rsp+A0h] [rbp-39h]
  int v26; // [rsp+C0h] [rbp-19h]
  __int64 v27; // [rsp+C8h] [rbp-11h]
  int v28[8]; // [rsp+D0h] [rbp-9h] BYREF

  v18[0] = 5;
  Values = MinAsn1ExtractValues(a4, a5, (unsigned int)v18, (unsigned int)&qword_1800878D0, 6, (__int64)v24);
  if ( Values > 0 )
    Values = v25;
  if ( Values < 0 )
  {
    v10 = 511;
LABEL_25:
    v14 = -1073739509;
    v15 = 3221227787LL;
    goto LABEL_26;
  }
  v18[0] = 3;
  v11 = MinAsn1ExtractValues(v27, v26, (unsigned int)v18, (unsigned int)&qword_180087750, 4, (__int64)v19);
  if ( v11 > 0 )
    v11 = v20;
  if ( v11 < 0 )
  {
    v10 = 520;
    goto LABEL_25;
  }
  if ( v21 == 9 )
  {
    v12 = *(_QWORD *)v22 - 0x1010DF78648862ALL;
    if ( *(_QWORD *)v22 == 0x1010DF78648862ALL )
      v12 = *(unsigned __int8 *)(v22 + 8) - 1LL;
    if ( !v12 )
    {
      v13 = Pkcs8ConvertRsaToKeyBlob(a2, a3, v28);
      v14 = v13;
      if ( v13 < 0 )
      {
        v10 = 537;
LABEL_15:
        v15 = (unsigned int)v13;
LABEL_26:
        DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v10);
        return v14;
      }
      *a6 = 196609;
      return v14;
    }
LABEL_24:
    v10 = 561;
    goto LABEL_25;
  }
  if ( v21 != 7 )
    goto LABEL_24;
  v16 = *(_DWORD *)v22 + 834107862;
  if ( *(_DWORD *)v22 == -834107862 )
  {
    v16 = *(unsigned __int16 *)(v22 + 4) - 573;
    if ( *(_WORD *)(v22 + 4) == 573 )
      v16 = *(unsigned __int8 *)(v22 + 6) - 1;
  }
  if ( v16 )
    goto LABEL_24;
  v13 = Pkcs8ConvertEccToKeyBlob(a1, (__int64)a2, a3, v28, v23, a6);
  v14 = v13;
  if ( v13 < 0 )
  {
    v10 = 553;
    goto LABEL_15;
  }
  return v14;
}

```

## disassembly

```asm
0x180067c40  push    rbp
0x180067c42  push    rbx
0x180067c43  push    rsi
0x180067c44  push    rdi
0x180067c45  push    r14
0x180067c47  lea     rbp, [rsp-27h]
0x180067c4c  sub     rsp, 100h
0x180067c53  mov     rax, cs:__security_cookie
0x180067c5a  xor     rax, rsp
0x180067c5d  mov     [rbp+47h+var_30], rax
0x180067c61  mov     rdi, [rbp+47h+arg_28]
0x180067c65  mov     r14d, ecx
0x180067c68  mov     rax, r9
0x180067c6b  mov     [rsp+120h+var_F0], 5
0x180067c73  lea     rcx, [rbp+47h+var_90]
0x180067c77  mov     rsi, r8
0x180067c7a  mov     [rsp+120h+var_F8], rcx
0x180067c7f  lea     r9, qword_1800878D0
0x180067c86  mov     rbx, rdx
0x180067c89  mov     dword ptr [rsp+120h+var_100], 6
0x180067c91  mov     edx, [rbp+47h+arg_20]
0x180067c94  lea     r8, [rsp+120h+var_F0]
0x180067c99  mov     rcx, rax
0x180067c9c  call    MinAsn1ExtractValues
0x180067ca1  test    eax, eax
0x180067ca3  cmovg   eax, [rbp+47h+var_80]
0x180067ca7  test    eax, eax
0x180067ca9  jns     short loc_180067CB6
0x180067cab  mov     r9d, 1FFh
0x180067cb1  jmp     loc_180067DBC
0x180067cb6  mov     edx, [rbp+47h+var_60]
0x180067cb9  lea     rax, [rsp+120h+var_D0]
0x180067cbe  mov     rcx, [rbp+47h+var_58]
0x180067cc2  lea     r9, qword_180087750
0x180067cc9  mov     [rsp+120h+var_F8], rax
0x180067cce  lea     r8, [rsp+120h+var_F0]
0x180067cd3  mov     dword ptr [rsp+120h+var_100], 4
0x180067cdb  mov     [rsp+120h+var_F0], 3
0x180067ce3  call    MinAsn1ExtractValues
0x180067ce8  test    eax, eax
0x180067cea  cmovg   eax, [rbp+47h+var_C0]
0x180067cee  test    eax, eax
0x180067cf0  jns     short loc_180067CFD
0x180067cf2  mov     r9d, 208h
0x180067cf8  jmp     loc_180067DBC
0x180067cfd  cmp     [rbp+47h+var_B0], 9
0x180067d01  mov     r8, [rbp+47h+var_A8]
0x180067d05  jnz     short loc_180067D55
0x180067d07  mov     rcx, [r8]
0x180067d0a  sub     rcx, cs:qword_1800911F8
0x180067d11  jnz     short loc_180067D22
0x180067d13  movzx   ecx, byte ptr [r8+8]
0x180067d18  movzx   eax, cs:byte_180091200
0x180067d1f  sub     rcx, rax
0x180067d22  test    rcx, rcx
0x180067d25  jnz     loc_180067DB6
0x180067d2b  lea     r8, [rbp+47h+var_50]
0x180067d2f  mov     rdx, rsi
0x180067d32  mov     rcx, rbx
0x180067d35  call    Pkcs8ConvertRsaToKeyBlob
0x180067d3a  mov     ebx, eax
0x180067d3c  test    eax, eax
0x180067d3e  jns     short loc_180067D4A
0x180067d40  mov     r9d, 219h
0x180067d46  mov     ecx, eax
0x180067d48  jmp     short loc_180067DC6
0x180067d4a  mov     dword ptr [rdi], 30001h
0x180067d50  jmp     loc_180067DD9
0x180067d55  cmp     [rbp+47h+var_B0], 7
0x180067d59  jnz     short loc_180067DB6
0x180067d5b  mov     ecx, [r8]
0x180067d5e  sub     ecx, cs:dword_1800911E4
0x180067d64  jnz     short loc_180067D84
0x180067d66  movzx   ecx, word ptr [r8+4]
0x180067d6b  movzx   eax, cs:word_1800911E8
0x180067d72  sub     ecx, eax
0x180067d74  jnz     short loc_180067D84
0x180067d76  movzx   ecx, byte ptr [r8+6]
0x180067d7b  movzx   eax, cs:byte_1800911EA
0x180067d82  sub     ecx, eax
0x180067d84  test    ecx, ecx
0x180067d86  jnz     short loc_180067DB6
0x180067d88  lea     rax, [rbp+47h+var_A0]
0x180067d8c  mov     [rsp+120h+var_F8], rdi
0x180067d91  lea     r9, [rbp+47h+var_50]
0x180067d95  mov     [rsp+120h+var_100], rax
0x180067d9a  mov     r8, rsi
0x180067d9d  mov     rdx, rbx
0x180067da0  mov     ecx, r14d
0x180067da3  call    Pkcs8ConvertEccToKeyBlob
0x180067da8  mov     ebx, eax
0x180067daa  test    eax, eax
0x180067dac  jns     short loc_180067DD9
0x180067dae  mov     r9d, 229h
0x180067db4  jmp     short loc_180067D46
0x180067db6  mov     r9d, 231h
0x180067dbc  mov     ebx, 0C000090Bh
0x180067dc1  mov     ecx, 0C000090Bh
0x180067dc6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067dcd  lea     rdx, aStatus; "Status"
0x180067dd4  call    DebugTraceError
0x180067dd9  mov     eax, ebx
0x180067ddb  mov     rcx, [rbp+47h+var_30]
0x180067ddf  xor     rcx, rsp; StackCookie
0x180067de2  call    __security_check_cookie
0x180067de7  add     rsp, 100h
0x180067dee  pop     r14
0x180067df0  pop     rdi
0x180067df1  pop     rsi
0x180067df2  pop     rbx
0x180067df3  pop     rbp
0x180067df4  retn
```
