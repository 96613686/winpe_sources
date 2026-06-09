# _GenerateGmsaPassword(uchar * const,ulong,_KEK_KEY_INFO *,uchar *,ulong,uchar * *,ulong *,uchar *,ulong)

- ea: `0x180016b30`
- end: `0x180016de9`
- name: `?_GenerateGmsaPassword@@YAJQEAEKPEAU_KEK_KEY_INFO@@PEAEKPEAPEAEPEAK2K@Z`
- size: `697`
- prototype: `__int64 __usercall@<rax>(struct _SID_KEY_HEADER *@<rcx>, unsigned int@<edx>, struct _KEK_KEY_INFO *@<r8>, unsigned __int8 *@<r9>, DWORD, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016df0`
- `0x180017030`

## callees

- `0x180001630`
- `0x18000d6a0`
- `0x180010920`
- `0x180016b30`
- `0x180018298`
- `0x18001a214`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x180016be9`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`

## pseudocode

```c
__int64 __fastcall _GenerateGmsaPassword(
        struct _SID_KEY_HEADER *a1,
        unsigned int a2,
        struct _KEK_KEY_INFO *a3,
        unsigned __int8 *a4,
        DWORD offset,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned __int8 *a8)
{
  DWORD derivedKeyLength; // r13d
  unsigned int v9; // r14d
  int DerivedKey; // eax
  unsigned int v13; // ebx
  unsigned int v14; // r9d
  unsigned int v15; // ecx
  DWORD v16; // edx
  unsigned int v17; // r14d
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // rsi
  unsigned int *v20; // rax
  BYTE *pNonce; // [rsp+20h] [rbp-E0h]
  PBYTE *ppKey; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v26; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v27; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int8 *v28[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v29; // [rsp+90h] [rbp-70h]
  unsigned __int8 cbNonce[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v31[64]; // [rsp+E0h] [rbp-20h] BYREF

  derivedKeyLength = (unsigned int)a4;
  v9 = *((_DWORD *)a1 + 11);
  v29 = a7;
  v28[1] = a8;
  v25 = 0;
  v24 = 0;
  v27 = 0;
  v26 = 0;
  v28[0] = 0;
  DerivedKey = ParseSidKeyResult(a1, a2, a3, v31, &v25, &v27, cbNonce, &v24, &v26, v28);
  v13 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v14 = 122;
LABEL_3:
    v15 = DerivedKey;
    goto LABEL_4;
  }
  if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
  {
    v13 = -2146893792;
    v14 = 133;
    v15 = -2146893792;
    goto LABEL_4;
  }
  if ( v25 > 0 || v24 > 0 )
  {
    DerivedKey = ClientComputeL2Key(
                   a1,
                   a3,
                   (struct _INFORMATIONCARD_CRYPTO_HANDLE *)((char *)a1 + 80),
                   v31,
                   cbNonce,
                   v25,
                   v27,
                   v24,
                   v26);
    v13 = DerivedKey;
    if ( DerivedKey < 0 )
    {
      v14 = 152;
      goto LABEL_3;
    }
  }
  v16 = 0;
  if ( v9 )
    v16 = (_DWORD)a1 + *((_DWORD *)a1 + 10) + 80;
  LODWORD(ppKey) = 28;
  LODWORD(pNonce) = 64;
  DerivedKey = GenerateDerivedKey(
                 (PINFORMATIONCARD_CRYPTO_HANDLE)((char *)a1 + 80),
                 v16,
                 (PBYTE)v9,
                 (DWORD)cbNonce,
                 pNonce,
                 derivedKeyLength,
                 offset,
                 0,
                 (DWORD *)L"GMSA PASSWORD",
                 ppKey);
  v13 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v14 = 181;
    goto LABEL_3;
  }
  if ( !a6 )
    return v13;
  v17 = *((_DWORD *)a1 + 18) + 52 + *((_DWORD *)a1 + 19);
  v18 = (unsigned __int8 *)SIDKeyProvAlloc(v17);
  v19 = v18;
  if ( v18 )
  {
    *((_DWORD *)v18 + 10) = 0;
    *(_OWORD *)v18 = *(_OWORD *)a1;
    *((_OWORD *)v18 + 1) = *((_OWORD *)a1 + 1);
    *((_QWORD *)v18 + 4) = *((_QWORD *)a1 + 4);
    memcpy_0(
      v18 + 52,
      (char *)a1
    + *((unsigned int *)a1 + 10)
    + *((unsigned int *)a1 + 12)
    + (unsigned __int64)*((unsigned int *)a1 + 13)
    + *((unsigned int *)a1 + 11)
    + 80,
      *((unsigned int *)a1 + 18));
    *((_DWORD *)v19 + 11) = *((_DWORD *)a1 + 18);
    memcpy_0(
      &v19[*((unsigned int *)a1 + 18) + 52],
      (char *)a1
    + *((unsigned int *)a1 + 11)
    + *((unsigned int *)a1 + 18)
    + (unsigned __int64)*((unsigned int *)a1 + 10)
    + *((unsigned int *)a1 + 12)
    + *((unsigned int *)a1 + 13)
    + 80,
      *((unsigned int *)a1 + 19));
    *((_DWORD *)v19 + 12) = *((_DWORD *)a1 + 19);
    v20 = v29;
    *a6 = v19;
    *v20 = v17;
    return v13;
  }
  v13 = -2147024882;
  v14 = 197;
  v15 = -2147024882;
LABEL_4:
  SidKeyDebugTraceError(v15, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx", v14);
  return v13;
}

```

## disassembly

```asm
0x180016b30  mov     [rsp-8+arg_8], rbx
0x180016b35  push    rbp
0x180016b36  push    rsi
0x180016b37  push    rdi
0x180016b38  push    r12
0x180016b3a  push    r13
0x180016b3c  push    r14
0x180016b3e  push    r15
0x180016b40  lea     rbp, [rsp-30h]
0x180016b45  sub     rsp, 130h
0x180016b4c  mov     rax, cs:__security_cookie
0x180016b53  xor     rax, rsp
0x180016b56  mov     [rbp+60h+var_40], rax
0x180016b5a  mov     rax, [rbp+60h+arg_30]
0x180016b61  xor     esi, esi
0x180016b63  mov     r12, [rbp+60h+arg_28]
0x180016b6a  mov     r13, r9
0x180016b6d  mov     r14d, [rcx+2Ch]
0x180016b71  lea     r9, [rbp+60h+var_80]; unsigned __int8 *
0x180016b75  mov     [rbp+60h+var_D0], rax
0x180016b79  mov     r15, r8
0x180016b7c  mov     rax, [rbp+60h+arg_38]
0x180016b83  mov     rdi, rcx
0x180016b86  mov     [rbp+60h+var_D8], rax
0x180016b8a  lea     rax, [rbp+60h+var_E0]
0x180016b8e  mov     [rsp+160h+ppKey], rax; unsigned __int8 **
0x180016b93  lea     rax, [rsp+160h+var_E8]
0x180016b98  mov     [rsp+160h+pcbKey], rax; unsigned int *
0x180016b9d  lea     rax, [rsp+160h+var_F0]
0x180016ba2  mov     [rsp+160h+algId], rax; int *
0x180016ba7  lea     rax, [rbp+60h+cbNonce]
0x180016bab  mov     qword ptr [rsp+160h+offset], rax; unsigned __int8 *
0x180016bb0  lea     rax, [rsp+160h+var_E4]
0x180016bb5  mov     qword ptr [rsp+160h+derivedKeyLength], rax; unsigned int *
0x180016bba  lea     rax, [rsp+160h+var_EC]
0x180016bbf  mov     [rsp+160h+pNonce], rax; int *
0x180016bc4  mov     [rsp+160h+var_EC], esi
0x180016bc8  mov     [rsp+160h+var_F0], esi
0x180016bcc  mov     [rsp+160h+var_E4], esi
0x180016bd0  mov     [rsp+160h+var_E8], esi
0x180016bd4  mov     [rbp+60h+var_E0], rsi
0x180016bd8  call    ?ParseSidKeyResult@@YAJPEBU_SID_KEY_HEADER@@KPEAU_KEK_KEY_INFO@@QEAEPEAJPEAK234PEAPEAE@Z; ParseSidKeyResult(_SID_KEY_HEADER const *,ulong,_KEK_KEY_INFO *,uchar * const,long *,ulong *,uchar * const,long *,ulong *,uchar * *)
0x180016bdd  mov     ebx, eax
0x180016bdf  test    eax, eax
0x180016be1  jns     short loc_180016C01
0x180016be3  lea     r9d, [rsi+7Ah]; unsigned int
0x180016be7  mov     ecx, eax; unsigned int
0x180016be9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180016bf0  lea     rdx, aHr; "hr"
0x180016bf7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180016bfc  jmp     loc_180016DC0
0x180016c01  test    byte ptr [rdi+8], 1
0x180016c05  jz      short loc_180016C19
0x180016c07  mov     ebx, 80090020h
0x180016c0c  mov     r9d, 85h
0x180016c12  mov     ecx, 80090020h
0x180016c17  jmp     short loc_180016BE9
0x180016c19  mov     r8d, [rsp+160h+var_EC]
0x180016c1e  mov     ecx, [rsp+160h+var_F0]
0x180016c22  test    r8d, r8d
0x180016c25  jg      short loc_180016C2B
0x180016c27  test    ecx, ecx
0x180016c29  jle     short loc_180016C71
0x180016c2b  mov     eax, [rsp+160h+var_E8]
0x180016c2f  lea     r9, [rbp+60h+var_80]; unsigned __int8 *
0x180016c33  mov     dword ptr [rsp+160h+pcbKey], eax; unsigned int
0x180016c37  mov     rdx, r15; struct _KEK_KEY_INFO *
0x180016c3a  mov     eax, [rsp+160h+var_E4]
0x180016c3e  mov     dword ptr [rsp+160h+algId], ecx; int
0x180016c42  mov     rcx, rdi; struct _SID_KEY_HEADER *
0x180016c45  mov     [rsp+160h+offset], eax; unsigned int
0x180016c49  lea     rax, [rbp+60h+cbNonce]
0x180016c4d  mov     [rsp+160h+derivedKeyLength], r8d; int
0x180016c52  lea     r8, [rdi+50h]; unsigned __int16 *
0x180016c56  mov     [rsp+160h+pNonce], rax; unsigned __int8 *
0x180016c5b  call    ?ClientComputeL2Key@@YAJPEAU_SID_KEY_HEADER@@PEAU_KEK_KEY_INFO@@PEAGQEAE3JKJK@Z; ClientComputeL2Key(_SID_KEY_HEADER *,_KEK_KEY_INFO *,ushort *,uchar * const,uchar * const,long,ulong,long,ulong)
0x180016c60  mov     ebx, eax
0x180016c62  test    eax, eax
0x180016c64  jns     short loc_180016C71
0x180016c66  mov     r9d, 98h
0x180016c6c  jmp     loc_180016BE7
0x180016c71  xor     edx, edx
0x180016c73  test    r14d, r14d
0x180016c76  jz      short loc_180016C82
0x180016c78  mov     edx, [rdi+28h]
0x180016c7b  add     rdx, 50h ; 'P'
0x180016c7f  add     rdx, rdi; cbLabel
0x180016c82  mov     eax, [rbp+60h+arg_40]
0x180016c88  lea     r9, [rbp+60h+cbNonce]; cbNonce
0x180016c8c  mov     [rsp+160h+var_F8], rsi
0x180016c91  lea     rcx, [rdi+50h]; hCrypto
0x180016c95  mov     [rsp+160h+var_100], eax
0x180016c99  mov     r8d, r14d; pLabel
0x180016c9c  mov     rax, [rbp+60h+var_D8]
0x180016ca0  mov     [rsp+160h+var_108], rax
0x180016ca5  lea     rax, pcbKey; "GMSA PASSWORD"
0x180016cac  mov     [rsp+160h+var_110], 1
0x180016cb4  mov     dword ptr [rsp+160h+ppKey], 1Ch; ppKey
0x180016cbc  mov     [rsp+160h+pcbKey], rax; pcbKey
0x180016cc1  mov     eax, [rbp+60h+arg_20]
0x180016cc7  mov     [rsp+160h+algId], rsi; algId
0x180016ccc  mov     [rsp+160h+offset], eax; offset
0x180016cd0  mov     qword ptr [rsp+160h+derivedKeyLength], r13; derivedKeyLength
0x180016cd5  mov     dword ptr [rsp+160h+pNonce], 40h ; '@'; pNonce
0x180016cdd  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180016ce2  mov     ebx, eax
0x180016ce4  test    eax, eax
0x180016ce6  jns     short loc_180016CF3
0x180016ce8  mov     r9d, 0B5h
0x180016cee  jmp     loc_180016BE7
0x180016cf3  test    r12, r12
0x180016cf6  jz      loc_180016DC0
0x180016cfc  mov     ecx, [rdi+48h]
0x180016cff  mov     r14d, [rdi+4Ch]
0x180016d03  add     ecx, 34h ; '4'
0x180016d06  add     r14d, ecx
0x180016d09  mov     ecx, r14d; unsigned __int64
0x180016d0c  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180016d11  mov     rsi, rax
0x180016d14  test    rax, rax
0x180016d17  jnz     short loc_180016D2E
0x180016d19  mov     ebx, 8007000Eh
0x180016d1e  mov     r9d, 0C5h
0x180016d24  mov     ecx, 8007000Eh
0x180016d29  jmp     loc_180016BE9
0x180016d2e  mov     dword ptr [rax+28h], 0
0x180016d35  movups  xmm0, xmmword ptr [rdi]
0x180016d38  movups  xmmword ptr [rax], xmm0
0x180016d3b  movups  xmm1, xmmword ptr [rdi+10h]
0x180016d3f  movups  xmmword ptr [rax+10h], xmm1
0x180016d43  movsd   xmm0, qword ptr [rdi+20h]
0x180016d48  movsd   qword ptr [rax+20h], xmm0
0x180016d4d  mov     eax, [rdi+30h]
0x180016d50  mov     edx, [rdi+34h]
0x180016d53  mov     ecx, [rdi+28h]
0x180016d56  add     rdx, rax
0x180016d59  mov     eax, [rdi+2Ch]
0x180016d5c  add     rcx, rdi
0x180016d5f  mov     r8d, [rdi+48h]; Size
0x180016d63  add     rdx, rcx
0x180016d66  add     rax, 50h ; 'P'
0x180016d6a  lea     rcx, [rsi+34h]; void *
0x180016d6e  add     rdx, rax; Src
0x180016d71  call    memcpy_0
0x180016d76  mov     eax, [rdi+48h]
0x180016d79  mov     [rsi+2Ch], eax
0x180016d7c  mov     eax, [rdi+30h]
0x180016d7f  mov     r9d, [rdi+48h]
0x180016d83  mov     edx, [rdi+34h]
0x180016d86  mov     ecx, [rdi+28h]
0x180016d89  add     rdx, rax
0x180016d8c  mov     eax, [rdi+2Ch]
0x180016d8f  add     rcx, r9
0x180016d92  mov     r8d, [rdi+4Ch]; Size
0x180016d96  add     rdx, rcx
0x180016d99  add     rax, 50h ; 'P'
0x180016d9d  lea     rcx, [r9+34h]
0x180016da1  add     rdx, rax
0x180016da4  add     rcx, rsi; void *
0x180016da7  add     rdx, rdi; Src
0x180016daa  call    memcpy_0
0x180016daf  mov     eax, [rdi+4Ch]
0x180016db2  mov     [rsi+30h], eax
0x180016db5  mov     rax, [rbp+60h+var_D0]
0x180016db9  mov     [r12], rsi
0x180016dbd  mov     [rax], r14d
0x180016dc0  mov     eax, ebx
0x180016dc2  mov     rcx, [rbp+60h+var_40]
0x180016dc6  xor     rcx, rsp; StackCookie
0x180016dc9  call    __security_check_cookie
0x180016dce  mov     rbx, [rsp+160h+arg_8]
0x180016dd6  add     rsp, 130h
0x180016ddd  pop     r15
0x180016ddf  pop     r14
0x180016de1  pop     r13
0x180016de3  pop     r12
0x180016de5  pop     rdi
0x180016de6  pop     rsi
0x180016de7  pop     rbp
0x180016de8  retn
```
