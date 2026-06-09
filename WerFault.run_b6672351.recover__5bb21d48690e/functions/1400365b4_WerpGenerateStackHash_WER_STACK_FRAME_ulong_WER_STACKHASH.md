# WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)

- ea: `0x1400365b4`
- end: `0x1400368bf`
- name: `?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(struct _WER_STACK_FRAME *, unsigned int, struct WER_STACKHASH *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140035de0`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b580`
- `0x1400365b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036866`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14003669a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14003669a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140036726`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140036726`
- `bcrypt!BCryptFinishHash` at `0x1400367f9`
- `bcrypt!BCryptFinishHash` at `0x140036892`
- `bcrypt!BCryptFinishHash` at `0x1400367f9`
- `bcrypt!BCryptFinishHash` at `0x140036892`
- `bcrypt!BCryptDestroyHash` at `0x140036815`
- `bcrypt!BCryptDestroyHash` at `0x1400368ae`
- `bcrypt!BCryptDestroyHash` at `0x140036815`
- `bcrypt!BCryptDestroyHash` at `0x1400368ae`
- `bcrypt!BCryptCreateHash` at `0x140036647`
- `bcrypt!BCryptCreateHash` at `0x140036647`
- `bcrypt!BCryptHashData` at `0x1400366c6`
- `bcrypt!BCryptHashData` at `0x1400367c1`
- `bcrypt!BCryptHashData` at `0x1400366c6`
- `bcrypt!BCryptHashData` at `0x1400367c1`

## pseudocode

```c
__int64 __fastcall WerpGenerateStackHash(struct _WER_STACK_FRAME *a1, unsigned int a2, struct WER_STACKHASH *a3)
{
  unsigned int v6; // esi
  unsigned int v8; // r14d
  const WCHAR *v9; // r15
  int v10; // r8d
  __int64 v11; // rbx
  const WCHAR *v12; // r8
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  WCHAR *v16; // rax
  __int16 v17; // cx
  __int64 v18; // rax
  signed int LastError; // eax
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  WCHAR DestStr[264]; // [rsp+60h] [rbp-A0h] BYREF

  v21 = 0;
  *(_OWORD *)phHash = 0;
  memset_0(DestStr, 0, 0x208u);
  v6 = 0;
  if ( !a2 )
    return 0;
  if ( *(_DWORD *)a3 > 1u )
    return 2147942487LL;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  v8 = 0;
  while ( 1 )
  {
    v9 = (const WCHAR *)((char *)a1 + 1048 * v8);
    v10 = LCMapStringW(0x7Fu, 0x100u, v9, -1, DestStr, 260);
    if ( !v10 )
      break;
    if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * v10 - 2, 0) < 0 )
      __fastfail(7u);
    if ( *(_DWORD *)a3 == 1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v9[v11] );
      do
      {
        v12 = `_werDetail::IsInExcludeList'::`2'::ExcludeModList[v6];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( v11 == v13 && CompareStringOrdinal(v9, v11, v12, v11, 1) == 2 )
        {
          v6 = 0;
          goto LABEL_27;
        }
        ++v6;
      }
      while ( v6 < 0xA );
      v6 = 0;
      v14 = StringCchPrintfW(DestStr, 0x104u, L"%0I64x", *((_QWORD *)v9 + 130));
      if ( (v14 & 0x80000000) != 0 )
        goto LABEL_34;
      v15 = 260;
      v16 = DestStr;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v14 = v15 == 0 ? 0x80070057 : 0;
      if ( !v15 )
        goto LABEL_34;
      if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * (v15 != 0 ? 260 - v15 : 0), 0) < 0 )
        __fastfail(7u);
    }
LABEL_27:
    if ( ++v8 >= a2 )
    {
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      v17 = (__int16)phHash[1];
      v14 = 0;
      v18 = v21;
      *(BCRYPT_HASH_HANDLE *)((char *)a3 + 4) = phHash[1];
      *(_QWORD *)((char *)a3 + 12) = v18;
      *((_WORD *)a3 + 10) = v17;
      return v14;
    }
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
  if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(phHash[0]);
  return v14;
}

```

## disassembly

```asm
0x1400365b4  mov     [rsp-8+arg_8], rbx
0x1400365b9  push    rbp
0x1400365ba  push    rsi
0x1400365bb  push    rdi
0x1400365bc  push    r12
0x1400365be  push    r13
0x1400365c0  push    r14
0x1400365c2  push    r15
0x1400365c4  lea     rbp, [rsp-180h]
0x1400365cc  sub     rsp, 280h
0x1400365d3  mov     rax, cs:__security_cookie
0x1400365da  xor     rax, rsp
0x1400365dd  mov     [rbp+1B0h+var_40], rax
0x1400365e4  mov     rdi, r8
0x1400365e7  mov     r12d, edx
0x1400365ea  mov     r13, rcx
0x1400365ed  xorps   xmm0, xmm0
0x1400365f0  xor     eax, eax
0x1400365f2  lea     rcx, [rsp+2B0h+DestStr]; void *
0x1400365f7  xor     edx, edx; Val
0x1400365f9  mov     [rsp+2B0h+var_260], rax
0x1400365fe  mov     r8d, 208h; Size
0x140036604  movups  xmmword ptr [rsp+2B0h+phHash], xmm0
0x140036609  call    memset_0
0x14003660e  xor     esi, esi
0x140036610  test    r12d, r12d
0x140036613  jnz     short loc_14003661C
0x140036615  xor     eax, eax
0x140036617  jmp     loc_14003683B
0x14003661c  cmp     dword ptr [rdi], 1
0x14003661f  jbe     short loc_14003662B
0x140036621  mov     eax, 80070057h
0x140036626  jmp     loc_14003683B
0x14003662b  xor     r9d, r9d; cbHashObject
0x14003662e  mov     [rsp+2B0h+dwFlags], esi; dwFlags
0x140036632  mov     [rsp+2B0h+cbSecret], esi; cbSecret
0x140036636  lea     rdx, [rsp+2B0h+phHash]; phHash
0x14003663b  xor     r8d, r8d; pbHashObject
0x14003663e  mov     [rsp+2B0h+pbSecret], rsi; pbSecret
0x140036643  lea     ecx, [r9+21h]; hAlgorithm
0x140036647  call    cs:__imp_BCryptCreateHash
0x14003664e  nop     dword ptr [rax+rax+00h]
0x140036653  test    eax, eax
0x140036655  jns     short loc_14003665E
0x140036657  mov     ecx, 7
0x14003665c  int     29h; Win8: RtlFailFast(ecx)
0x14003665e  mov     r14d, esi
0x140036661  test    r12d, r12d
0x140036664  jz      loc_1400367E8
0x14003666a  mov     eax, r14d
0x14003666d  or      r9d, 0FFFFFFFFh; cchSrc
0x140036671  imul    r15, rax, 418h
0x140036678  lea     rax, [rsp+2B0h+DestStr]
0x14003667d  mov     [rsp+2B0h+cbSecret], 104h; cchDest
0x140036685  add     r15, r13
0x140036688  mov     [rsp+2B0h+pbSecret], rax; lpDestStr
0x14003668d  mov     r8, r15; lpSrcStr
0x140036690  mov     edx, 100h; dwMapFlags
0x140036695  mov     ecx, 7Fh; Locale
0x14003669a  call    cs:__imp_LCMapStringW
0x1400366a1  nop     dword ptr [rax+rax+00h]
0x1400366a6  movsxd  r8, eax
0x1400366a9  test    eax, eax
0x1400366ab  jz      loc_140036866
0x1400366b1  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1400366b6  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cbInput
0x1400366be  xor     r9d, r9d; dwFlags
0x1400366c1  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x1400366c6  call    cs:__imp_BCryptHashData
0x1400366cd  nop     dword ptr [rax+rax+00h]
0x1400366d2  test    eax, eax
0x1400366d4  jns     short loc_1400366DD
0x1400366d6  mov     ecx, 7
0x1400366db  int     29h; Win8: RtlFailFast(ecx)
0x1400366dd  cmp     dword ptr [rdi], 1
0x1400366e0  jnz     loc_1400367DC
0x1400366e6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400366ea  inc     rbx
0x1400366ed  cmp     [r15+rbx*2], si
0x1400366f2  jnz     short loc_1400366EA
0x1400366f4  mov     eax, esi
0x1400366f6  lea     r8, ?ExcludeModList@?1??IsInExcludeList@_werDetail@@YAHPEB_W@Z@4QBQEB_WB; wchar_t const * const near * const `_werDetail::IsInExcludeList(wchar_t const *)'::`2'::ExcludeModList
0x1400366fd  mov     r8, [r8+rax*8]; lpString2
0x140036701  or      rax, 0FFFFFFFFFFFFFFFFh
0x140036705  xor     ecx, ecx
0x140036707  inc     rax
0x14003670a  cmp     [r8+rax*2], cx
0x14003670f  jnz     short loc_140036707
0x140036711  cmp     rbx, rax
0x140036714  jnz     short loc_14003673B
0x140036716  mov     r9d, ebx; cchCount2
0x140036719  mov     dword ptr [rsp+2B0h+pbSecret], 1; bIgnoreCase
0x140036721  mov     edx, ebx; cchCount1
0x140036723  mov     rcx, r15; lpString1
0x140036726  call    cs:__imp_CompareStringOrdinal
0x14003672d  nop     dword ptr [rax+rax+00h]
0x140036732  cmp     eax, 2
0x140036735  jz      loc_1400367DA
0x14003673b  inc     esi
0x14003673d  cmp     esi, 0Ah
0x140036740  jb      short loc_1400366F4
0x140036742  mov     r9, [r15+410h]
0x140036749  lea     r8, a0i64x; "%0I64x"
0x140036750  mov     r15d, 104h
0x140036756  lea     rcx, [rsp+2B0h+DestStr]; wchar_t *
0x14003675b  mov     edx, r15d; unsigned __int64
0x14003675e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140036763  xor     esi, esi
0x140036765  mov     ebx, eax
0x140036767  test    eax, eax
0x140036769  js      loc_140036881
0x14003676f  mov     edx, r15d
0x140036772  lea     rax, [rsp+2B0h+DestStr]
0x140036777  cmp     [rax], si
0x14003677a  jz      short loc_140036786
0x14003677c  add     rax, 2
0x140036780  sub     rdx, 1
0x140036784  jnz     short loc_140036777
0x140036786  mov     rax, rdx
0x140036789  mov     rcx, r15
0x14003678c  neg     rax
0x14003678f  mov     rax, rdx
0x140036792  sbb     ebx, ebx
0x140036794  sub     rcx, rdx
0x140036797  not     ebx
0x140036799  and     ebx, 80070057h
0x14003679f  neg     rax
0x1400367a2  sbb     r8, r8
0x1400367a5  and     r8, rcx
0x1400367a8  test    rdx, rdx
0x1400367ab  jz      loc_140036881
0x1400367b1  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1400367b6  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x1400367bb  add     r8d, r8d; cbInput
0x1400367be  xor     r9d, r9d; dwFlags
0x1400367c1  call    cs:__imp_BCryptHashData
0x1400367c8  nop     dword ptr [rax+rax+00h]
0x1400367cd  test    eax, eax
0x1400367cf  jns     short loc_1400367DC
0x1400367d1  mov     ecx, 7
0x1400367d6  int     29h; Win8: RtlFailFast(ecx)
0x1400367d8  jmp     short loc_1400367DC
0x1400367da  xor     esi, esi
0x1400367dc  inc     r14d
0x1400367df  cmp     r14d, r12d
0x1400367e2  jb      loc_14003666A
0x1400367e8  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1400367ed  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x1400367f2  xor     r9d, r9d; dwFlags
0x1400367f5  lea     r8d, [r9+10h]; cbOutput
0x1400367f9  call    cs:__imp_BCryptFinishHash
0x140036800  nop     dword ptr [rax+rax+00h]
0x140036805  test    eax, eax
0x140036807  jns     short loc_140036810
0x140036809  mov     ecx, 7
0x14003680e  int     29h; Win8: RtlFailFast(ecx)
0x140036810  mov     rcx, [rsp+2B0h+phHash]; hHash
0x140036815  call    cs:__imp_BCryptDestroyHash
0x14003681c  nop     dword ptr [rax+rax+00h]
0x140036821  mov     rcx, [rsp+2B0h+phHash+8]
0x140036826  mov     ebx, esi
0x140036828  mov     rax, [rsp+2B0h+var_260]
0x14003682d  mov     [rdi+4], rcx
0x140036831  mov     [rdi+0Ch], rax
0x140036835  mov     [rdi+14h], cx
0x140036839  mov     eax, ebx
0x14003683b  mov     rcx, [rbp+1B0h+var_40]
0x140036842  xor     rcx, rsp; StackCookie
0x140036845  call    __security_check_cookie
0x14003684a  mov     rbx, [rsp+2B0h+arg_8]
0x140036852  add     rsp, 280h
0x140036859  pop     r15
0x14003685b  pop     r14
0x14003685d  pop     r13
0x14003685f  pop     r12
0x140036861  pop     rdi
0x140036862  pop     rsi
0x140036863  pop     rbp
0x140036864  retn
0x140036866  call    cs:__imp_GetLastError
0x14003686d  nop     dword ptr [rax+rax+00h]
0x140036872  mov     ebx, eax
0x140036874  test    eax, eax
0x140036876  jle     short loc_140036881
0x140036878  movzx   ebx, ax
0x14003687b  or      ebx, 80070000h
0x140036881  mov     rcx, [rsp+2B0h+phHash]; hHash
0x140036886  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x14003688b  xor     r9d, r9d; dwFlags
0x14003688e  lea     r8d, [r9+10h]; cbOutput
0x140036892  call    cs:__imp_BCryptFinishHash
0x140036899  nop     dword ptr [rax+rax+00h]
0x14003689e  test    eax, eax
0x1400368a0  jns     short loc_1400368A9
0x1400368a2  mov     ecx, 7
0x1400368a7  int     29h; Win8: RtlFailFast(ecx)
0x1400368a9  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1400368ae  call    cs:__imp_BCryptDestroyHash
0x1400368b5  nop     dword ptr [rax+rax+00h]
0x1400368ba  jmp     loc_140036839
```
