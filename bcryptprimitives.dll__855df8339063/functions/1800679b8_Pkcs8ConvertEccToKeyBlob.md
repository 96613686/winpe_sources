# Pkcs8ConvertEccToKeyBlob

- ea: `0x1800679b8`
- end: `0x180067c3a`
- name: `Pkcs8ConvertEccToKeyBlob`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180067c40`

## callees

- `0x18000ecb0`
- `0x180046658`
- `0x180063170`
- `0x180063180`
- `0x1800679b8`
- `0x180067dfc`
- `0x18006ccf0`
- `0x18007f790`

## string_xrefs

- `0x180067bfd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs8ConvertEccToKeyBlob(int a1, __int64 a2, unsigned int *a3, int *a4, int *a5, int *a6)
{
  int v9; // edx
  __int64 v10; // rcx
  int Values; // eax
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  size_t v15; // r12
  unsigned __int64 v16; // rsi
  unsigned int v17; // eax
  unsigned int v18; // edi
  int v19; // edx
  __int64 v20; // rcx
  int EccAlgId; // eax
  int v23; // [rsp+30h] [rbp-89h] BYREF
  int *v24; // [rsp+38h] [rbp-81h]
  _BYTE v25[16]; // [rsp+40h] [rbp-79h] BYREF
  int v26[4]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-59h] BYREF
  int v28; // [rsp+70h] [rbp-49h]
  size_t Size; // [rsp+90h] [rbp-29h]
  void *Src; // [rsp+98h] [rbp-21h]
  int v31[4]; // [rsp+A0h] [rbp-19h] BYREF
  int v32; // [rsp+B0h] [rbp-9h]
  _BYTE *v33; // [rsp+B8h] [rbp-1h]

  v24 = a6;
  if ( !a3 || !a4 || !a5 )
  {
    v13 = -1073741811;
    v12 = 368;
    v14 = 3221225485LL;
    goto LABEL_38;
  }
  v9 = *a4;
  v10 = *((_QWORD *)a4 + 1);
  v23 = 9;
  Values = MinAsn1ExtractValues(v10, v9, (unsigned int)&v23, (unsigned int)&qword_180087790, 6, (__int64)v27);
  if ( Values > 0 )
    Values = v28;
  if ( Values < 0 )
  {
    v12 = 377;
LABEL_8:
    v13 = -1073739509;
    v14 = 3221227787LL;
LABEL_38:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v12);
    return v13;
  }
  v15 = (unsigned int)Size;
  v16 = 2LL * (unsigned int)Size;
  if ( v16 > 0xFFFFFFFF )
  {
    v12 = 387;
    goto LABEL_12;
  }
  v17 = v16 + 8;
  if ( (unsigned int)v16 >= 0xFFFFFFF8 )
  {
    v12 = 393;
LABEL_12:
    v13 = -1073741675;
    v14 = 3221225621LL;
    goto LABEL_38;
  }
  v18 = v17 + Size;
  if ( v17 + (unsigned int)Size < v17 )
  {
    v12 = 399;
    goto LABEL_12;
  }
  v19 = *a5;
  v20 = *((_QWORD *)a5 + 1);
  v23 = 1;
  if ( (int)MinAsn1ExtractValues(v20, v19, (unsigned int)&v23, (unsigned int)&qword_180087780, 2, (__int64)v25) < 0 )
  {
    v12 = 407;
    goto LABEL_8;
  }
  if ( !a2 )
  {
    v13 = 0;
    goto LABEL_19;
  }
  if ( *a3 < v18 )
  {
    *a3 = v18;
    v13 = -1073741789;
    v12 = 423;
    v14 = 3221225507LL;
    goto LABEL_38;
  }
  EccAlgId = Pkcs8GetEccAlgId(a1, v31, v26, v24);
  v13 = EccAlgId;
  if ( EccAlgId < 0 )
  {
    v12 = 436;
LABEL_24:
    v14 = (unsigned int)EccAlgId;
    goto LABEL_38;
  }
  EccAlgId = MSCryptEcGetKeyMagicForAlgId(*v24, 0, a1 == 5, 1, a2);
  v13 = EccAlgId;
  if ( EccAlgId < 0 )
  {
    v12 = 448;
    goto LABEL_24;
  }
  if ( v32 && v33 )
  {
    if ( v32 != (_DWORD)v16 + 1 )
    {
      v12 = 458;
      goto LABEL_8;
    }
    if ( (unsigned __int8)(*v33 - 2) > 2u )
    {
      v12 = 469;
      goto LABEL_8;
    }
    v16 = (unsigned int)v16;
    memcpy_0((void *)(a2 + 8), v33 + 1, (unsigned int)v16);
  }
  else
  {
    v16 = (unsigned int)v16;
    memset_0((void *)(a2 + 8), 0, (unsigned int)v16);
  }
  memcpy_0((void *)(v16 + a2 + 8), Src, v15);
  *(_DWORD *)(a2 + 4) = Size;
LABEL_19:
  *a3 = v18;
  return v13;
}

```

## disassembly

```asm
0x1800679b8  mov     [rsp-8+arg_0], rbx
0x1800679bd  push    rbp
0x1800679be  push    rsi
0x1800679bf  push    rdi
0x1800679c0  push    r12
0x1800679c2  push    r13
0x1800679c4  push    r14
0x1800679c6  push    r15
0x1800679c8  lea     rbp, [rsp-17h]
0x1800679cd  sub     rsp, 0D0h
0x1800679d4  mov     rax, cs:__security_cookie
0x1800679db  xor     rax, rsp
0x1800679de  mov     [rbp+47h+var_40], rax
0x1800679e2  mov     rbx, [rbp+47h+arg_20]
0x1800679e6  mov     r15d, ecx
0x1800679e9  mov     rcx, [rbp+47h+arg_28]
0x1800679ed  mov     rax, r9
0x1800679f0  mov     [rsp+100h+var_C8], rcx
0x1800679f5  mov     r14, r8
0x1800679f8  mov     r13, rdx
0x1800679fb  test    r8, r8
0x1800679fe  jz      loc_180067BED
0x180067a04  test    rax, rax
0x180067a07  jz      loc_180067BED
0x180067a0d  test    rbx, rbx
0x180067a10  jz      loc_180067BED
0x180067a16  mov     edx, [rax]
0x180067a18  lea     rcx, [rbp+47h+var_A0]
0x180067a1c  mov     [rsp+100h+var_D8], rcx
0x180067a21  lea     r9, qword_180087790
0x180067a28  mov     rcx, [rax+8]
0x180067a2c  lea     r8, [rsp+100h+var_D0]
0x180067a31  mov     [rsp+100h+var_D0], 9
0x180067a39  mov     dword ptr [rsp+100h+var_E0], 6
0x180067a41  call    MinAsn1ExtractValues
0x180067a46  test    eax, eax
0x180067a48  cmovg   eax, [rbp+47h+var_90]
0x180067a4c  test    eax, eax
0x180067a4e  jns     short loc_180067A65
0x180067a50  mov     r9d, 179h
0x180067a56  mov     ebx, 0C000090Bh
0x180067a5b  mov     ecx, 0C000090Bh
0x180067a60  jmp     loc_180067BFD
0x180067a65  mov     r12d, dword ptr [rbp+47h+Size]
0x180067a69  mov     eax, 0FFFFFFFFh
0x180067a6e  lea     rsi, [r12+r12]
0x180067a72  cmp     rsi, rax
0x180067a75  ja      loc_180067BE2
0x180067a7b  lea     eax, [rsi+8]
0x180067a7e  cmp     eax, 8
0x180067a81  jnb     short loc_180067A98
0x180067a83  mov     r9d, 189h
0x180067a89  mov     ebx, 0C0000095h
0x180067a8e  mov     ecx, 0C0000095h
0x180067a93  jmp     loc_180067BFD
0x180067a98  lea     edi, [rax+r12]
0x180067a9c  cmp     edi, eax
0x180067a9e  jnb     short loc_180067AA8
0x180067aa0  mov     r9d, 18Fh
0x180067aa6  jmp     short loc_180067A89
0x180067aa8  mov     edx, [rbx]
0x180067aaa  lea     rax, [rbp+47h+var_C0]
0x180067aae  mov     rcx, [rbx+8]
0x180067ab2  lea     r9, qword_180087780
0x180067ab9  mov     [rsp+100h+var_D8], rax
0x180067abe  lea     r8, [rsp+100h+var_D0]
0x180067ac3  mov     dword ptr [rsp+100h+var_E0], 2
0x180067acb  mov     [rsp+100h+var_D0], 1
0x180067ad3  call    MinAsn1ExtractValues
0x180067ad8  test    eax, eax
0x180067ada  jns     short loc_180067AE7
0x180067adc  mov     r9d, 197h
0x180067ae2  jmp     loc_180067A56
0x180067ae7  test    r13, r13
0x180067aea  jnz     short loc_180067AF6
0x180067aec  xor     ebx, ebx
0x180067aee  mov     [r14], edi
0x180067af1  jmp     loc_180067C10
0x180067af6  cmp     [r14], edi
0x180067af9  jnb     short loc_180067B13
0x180067afb  mov     [r14], edi
0x180067afe  mov     ebx, 0C0000023h
0x180067b03  mov     r9d, 1A7h
0x180067b09  mov     ecx, 0C0000023h
0x180067b0e  jmp     loc_180067BFD
0x180067b13  mov     r9, [rsp+100h+var_C8]
0x180067b18  lea     r8, [rbp+47h+var_B0]
0x180067b1c  lea     rdx, [rbp+47h+var_60]
0x180067b20  mov     ecx, r15d
0x180067b23  call    Pkcs8GetEccAlgId
0x180067b28  mov     ebx, eax
0x180067b2a  test    eax, eax
0x180067b2c  jns     short loc_180067B3B
0x180067b2e  mov     r9d, 1B4h
0x180067b34  mov     ecx, eax
0x180067b36  jmp     loc_180067BFD
0x180067b3b  mov     rax, [rsp+100h+var_C8]
0x180067b40  xor     r8d, r8d
0x180067b43  cmp     r15d, 5
0x180067b47  mov     [rsp+100h+var_E0], r13
0x180067b4c  setz    r8b
0x180067b50  xor     edx, edx
0x180067b52  mov     ecx, [rax]
0x180067b54  lea     r9d, [rdx+1]
0x180067b58  call    MSCryptEcGetKeyMagicForAlgId
0x180067b5d  mov     ebx, eax
0x180067b5f  test    eax, eax
0x180067b61  jns     short loc_180067B6B
0x180067b63  mov     r9d, 1C0h
0x180067b69  jmp     short loc_180067B34
0x180067b6b  mov     ecx, [rbp+47h+var_50]
0x180067b6e  lea     r15, [r13+8]
0x180067b72  test    ecx, ecx
0x180067b74  jz      short loc_180067BB6
0x180067b76  mov     rdx, [rbp+47h+var_48]
0x180067b7a  test    rdx, rdx
0x180067b7d  jz      short loc_180067BB6
0x180067b7f  lea     eax, [rsi+1]
0x180067b82  cmp     ecx, eax
0x180067b84  jz      short loc_180067B91
0x180067b86  mov     r9d, 1CAh
0x180067b8c  jmp     loc_180067A56
0x180067b91  mov     al, [rdx]
0x180067b93  sub     al, 2
0x180067b95  cmp     al, 2
0x180067b97  jbe     short loc_180067BA4
0x180067b99  mov     r9d, 1D5h
0x180067b9f  jmp     loc_180067A56
0x180067ba4  mov     esi, esi
0x180067ba6  inc     rdx; Src
0x180067ba9  mov     r8d, esi; Size
0x180067bac  mov     rcx, r15; void *
0x180067baf  call    memcpy_0
0x180067bb4  jmp     short loc_180067BC5
0x180067bb6  mov     esi, esi
0x180067bb8  xor     edx, edx; Val
0x180067bba  mov     r8d, esi; Size
0x180067bbd  mov     rcx, r15; void *
0x180067bc0  call    memset_0
0x180067bc5  mov     rdx, [rbp+47h+Src]; Src
0x180067bc9  lea     rcx, [rsi+r15]; void *
0x180067bcd  mov     r8, r12; Size
0x180067bd0  call    memcpy_0
0x180067bd5  mov     rax, [rbp+47h+Size]
0x180067bd9  mov     [r13+4], eax
0x180067bdd  jmp     loc_180067AEE
0x180067be2  mov     r9d, 183h
0x180067be8  jmp     loc_180067A89
0x180067bed  mov     ebx, 0C000000Dh
0x180067bf2  mov     r9d, 170h
0x180067bf8  mov     ecx, 0C000000Dh
0x180067bfd  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067c04  lea     rdx, aStatus; "Status"
0x180067c0b  call    DebugTraceError
0x180067c10  mov     eax, ebx
0x180067c12  mov     rcx, [rbp+47h+var_40]
0x180067c16  xor     rcx, rsp; StackCookie
0x180067c19  call    __security_check_cookie
0x180067c1e  mov     rbx, [rsp+100h+arg_0]
0x180067c26  add     rsp, 0D0h
0x180067c2d  pop     r15
0x180067c2f  pop     r14
0x180067c31  pop     r13
0x180067c33  pop     r12
0x180067c35  pop     rdi
0x180067c36  pop     rsi
0x180067c37  pop     rbp
0x180067c38  retn
```
