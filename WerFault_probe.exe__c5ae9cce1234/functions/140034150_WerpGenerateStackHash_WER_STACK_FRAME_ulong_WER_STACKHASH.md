# WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)

- ea: `0x140034150`
- end: `0x14003441b`
- name: `?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(struct _WER_STACK_FRAME *, unsigned int, struct WER_STACKHASH *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400339d8`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b540`
- `0x140034150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400343d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400343d7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x140034230`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x140034230`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400342b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400342b0`
- `bcrypt!BCryptFinishHash` at `0x140034377`
- `bcrypt!BCryptFinishHash` at `0x1400343fd`
- `bcrypt!BCryptFinishHash` at `0x140034377`
- `bcrypt!BCryptFinishHash` at `0x1400343fd`
- `bcrypt!BCryptDestroyHash` at `0x14003438d`
- `bcrypt!BCryptDestroyHash` at `0x140034413`
- `bcrypt!BCryptDestroyHash` at `0x14003438d`
- `bcrypt!BCryptDestroyHash` at `0x140034413`
- `bcrypt!BCryptCreateHash` at `0x1400341e3`
- `bcrypt!BCryptCreateHash` at `0x1400341e3`
- `bcrypt!BCryptHashData` at `0x140034256`
- `bcrypt!BCryptHashData` at `0x140034345`
- `bcrypt!BCryptHashData` at `0x140034256`
- `bcrypt!BCryptHashData` at `0x140034345`

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
0x140034150  mov     [rsp-8+arg_8], rbx
0x140034155  push    rbp
0x140034156  push    rsi
0x140034157  push    rdi
0x140034158  push    r12
0x14003415a  push    r13
0x14003415c  push    r14
0x14003415e  push    r15
0x140034160  lea     rbp, [rsp-180h]
0x140034168  sub     rsp, 280h
0x14003416f  mov     rax, cs:__security_cookie
0x140034176  xor     rax, rsp
0x140034179  mov     [rbp+1B0h+var_40], rax
0x140034180  mov     rdi, r8
0x140034183  mov     r12d, edx
0x140034186  mov     r13, rcx
0x140034189  xorps   xmm0, xmm0
0x14003418c  xor     eax, eax
0x14003418e  lea     rcx, [rsp+2B0h+DestStr]; void *
0x140034193  xor     edx, edx; Val
0x140034195  mov     [rsp+2B0h+var_260], rax
0x14003419a  mov     r8d, 208h; Size
0x1400341a0  movups  xmmword ptr [rsp+2B0h+phHash], xmm0
0x1400341a5  call    memset_0
0x1400341aa  xor     esi, esi
0x1400341ac  test    r12d, r12d
0x1400341af  jnz     short loc_1400341B8
0x1400341b1  xor     eax, eax
0x1400341b3  jmp     loc_1400343AD
0x1400341b8  cmp     dword ptr [rdi], 1
0x1400341bb  jbe     short loc_1400341C7
0x1400341bd  mov     eax, 80070057h
0x1400341c2  jmp     loc_1400343AD
0x1400341c7  xor     r9d, r9d; cbHashObject
0x1400341ca  mov     [rsp+2B0h+dwFlags], esi; dwFlags
0x1400341ce  mov     [rsp+2B0h+cbSecret], esi; cbSecret
0x1400341d2  lea     rdx, [rsp+2B0h+phHash]; phHash
0x1400341d7  xor     r8d, r8d; pbHashObject
0x1400341da  mov     [rsp+2B0h+pbSecret], rsi; pbSecret
0x1400341df  lea     ecx, [r9+21h]; hAlgorithm
0x1400341e3  call    cs:__imp_BCryptCreateHash
0x1400341e9  test    eax, eax
0x1400341eb  jns     short loc_1400341F4
0x1400341ed  mov     ecx, 7
0x1400341f2  int     29h; Win8: RtlFailFast(ecx)
0x1400341f4  mov     r14d, esi
0x1400341f7  test    r12d, r12d
0x1400341fa  jz      loc_140034366
0x140034200  mov     eax, r14d
0x140034203  or      r9d, 0FFFFFFFFh; cchSrc
0x140034207  imul    r15, rax, 418h
0x14003420e  lea     rax, [rsp+2B0h+DestStr]
0x140034213  mov     [rsp+2B0h+cbSecret], 104h; cchDest
0x14003421b  add     r15, r13
0x14003421e  mov     [rsp+2B0h+pbSecret], rax; lpDestStr
0x140034223  mov     r8, r15; lpSrcStr
0x140034226  mov     edx, 100h; dwMapFlags
0x14003422b  mov     ecx, 7Fh; Locale
0x140034230  call    cs:__imp_LCMapStringW
0x140034236  movsxd  r8, eax
0x140034239  test    eax, eax
0x14003423b  jz      loc_1400343D7
0x140034241  mov     rcx, [rsp+2B0h+phHash]; hHash
0x140034246  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cbInput
0x14003424e  xor     r9d, r9d; dwFlags
0x140034251  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x140034256  call    cs:__imp_BCryptHashData
0x14003425c  test    eax, eax
0x14003425e  jns     short loc_140034267
0x140034260  mov     ecx, 7
0x140034265  int     29h; Win8: RtlFailFast(ecx)
0x140034267  cmp     dword ptr [rdi], 1
0x14003426a  jnz     loc_14003435A
0x140034270  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140034274  inc     rbx
0x140034277  cmp     [r15+rbx*2], si
0x14003427c  jnz     short loc_140034274
0x14003427e  mov     eax, esi
0x140034280  lea     r8, ?ExcludeModList@?1??IsInExcludeList@_werDetail@@YAHPEB_W@Z@4QBQEB_WB; wchar_t const * const near * const `_werDetail::IsInExcludeList(wchar_t const *)'::`2'::ExcludeModList
0x140034287  mov     r8, [r8+rax*8]; lpString2
0x14003428b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003428f  xor     ecx, ecx
0x140034291  inc     rax
0x140034294  cmp     [r8+rax*2], cx
0x140034299  jnz     short loc_140034291
0x14003429b  cmp     rbx, rax
0x14003429e  jnz     short loc_1400342BF
0x1400342a0  mov     r9d, ebx; cchCount2
0x1400342a3  mov     dword ptr [rsp+2B0h+pbSecret], 1; bIgnoreCase
0x1400342ab  mov     edx, ebx; cchCount1
0x1400342ad  mov     rcx, r15; lpString1
0x1400342b0  call    cs:__imp_CompareStringOrdinal
0x1400342b6  cmp     eax, 2
0x1400342b9  jz      loc_140034358
0x1400342bf  inc     esi
0x1400342c1  cmp     esi, 0Ah
0x1400342c4  jb      short loc_14003427E
0x1400342c6  mov     r9, [r15+410h]
0x1400342cd  lea     r8, a0i64x; "%0I64x"
0x1400342d4  mov     r15d, 104h
0x1400342da  lea     rcx, [rsp+2B0h+DestStr]; wchar_t *
0x1400342df  mov     edx, r15d; unsigned __int64
0x1400342e2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400342e7  xor     esi, esi
0x1400342e9  mov     ebx, eax
0x1400342eb  test    eax, eax
0x1400342ed  js      loc_1400343EC
0x1400342f3  mov     edx, r15d
0x1400342f6  lea     rax, [rsp+2B0h+DestStr]
0x1400342fb  cmp     [rax], si
0x1400342fe  jz      short loc_14003430A
0x140034300  add     rax, 2
0x140034304  sub     rdx, 1
0x140034308  jnz     short loc_1400342FB
0x14003430a  mov     rax, rdx
0x14003430d  mov     rcx, r15
0x140034310  neg     rax
0x140034313  mov     rax, rdx
0x140034316  sbb     ebx, ebx
0x140034318  sub     rcx, rdx
0x14003431b  not     ebx
0x14003431d  and     ebx, 80070057h
0x140034323  neg     rax
0x140034326  sbb     r8, r8
0x140034329  and     r8, rcx
0x14003432c  test    rdx, rdx
0x14003432f  jz      loc_1400343EC
0x140034335  mov     rcx, [rsp+2B0h+phHash]; hHash
0x14003433a  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x14003433f  add     r8d, r8d; cbInput
0x140034342  xor     r9d, r9d; dwFlags
0x140034345  call    cs:__imp_BCryptHashData
0x14003434b  test    eax, eax
0x14003434d  jns     short loc_14003435A
0x14003434f  mov     ecx, 7
0x140034354  int     29h; Win8: RtlFailFast(ecx)
0x140034356  jmp     short loc_14003435A
0x140034358  xor     esi, esi
0x14003435a  inc     r14d
0x14003435d  cmp     r14d, r12d
0x140034360  jb      loc_140034200
0x140034366  mov     rcx, [rsp+2B0h+phHash]; hHash
0x14003436b  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x140034370  xor     r9d, r9d; dwFlags
0x140034373  lea     r8d, [r9+10h]; cbOutput
0x140034377  call    cs:__imp_BCryptFinishHash
0x14003437d  test    eax, eax
0x14003437f  jns     short loc_140034388
0x140034381  mov     ecx, 7
0x140034386  int     29h; Win8: RtlFailFast(ecx)
0x140034388  mov     rcx, [rsp+2B0h+phHash]; hHash
0x14003438d  call    cs:__imp_BCryptDestroyHash
0x140034393  mov     rcx, [rsp+2B0h+phHash+8]
0x140034398  mov     ebx, esi
0x14003439a  mov     rax, [rsp+2B0h+var_260]
0x14003439f  mov     [rdi+4], rcx
0x1400343a3  mov     [rdi+0Ch], rax
0x1400343a7  mov     [rdi+14h], cx
0x1400343ab  mov     eax, ebx
0x1400343ad  mov     rcx, [rbp+1B0h+var_40]
0x1400343b4  xor     rcx, rsp; StackCookie
0x1400343b7  call    __security_check_cookie
0x1400343bc  mov     rbx, [rsp+2B0h+arg_8]
0x1400343c4  add     rsp, 280h
0x1400343cb  pop     r15
0x1400343cd  pop     r14
0x1400343cf  pop     r13
0x1400343d1  pop     r12
0x1400343d3  pop     rdi
0x1400343d4  pop     rsi
0x1400343d5  pop     rbp
0x1400343d6  retn
0x1400343d7  call    cs:__imp_GetLastError
0x1400343dd  mov     ebx, eax
0x1400343df  test    eax, eax
0x1400343e1  jle     short loc_1400343EC
0x1400343e3  movzx   ebx, ax
0x1400343e6  or      ebx, 80070000h
0x1400343ec  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1400343f1  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x1400343f6  xor     r9d, r9d; dwFlags
0x1400343f9  lea     r8d, [r9+10h]; cbOutput
0x1400343fd  call    cs:__imp_BCryptFinishHash
0x140034403  test    eax, eax
0x140034405  jns     short loc_14003440E
0x140034407  mov     ecx, 7
0x14003440c  int     29h; Win8: RtlFailFast(ecx)
0x14003440e  mov     rcx, [rsp+2B0h+phHash]; hHash
0x140034413  call    cs:__imp_BCryptDestroyHash
0x140034419  jmp     short loc_1400343AB
```
