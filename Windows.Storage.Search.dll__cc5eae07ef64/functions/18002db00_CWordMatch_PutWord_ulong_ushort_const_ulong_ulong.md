# CWordMatch::PutWord(ulong,ushort const *,ulong,ulong)

- ea: `0x18002db00`
- end: `0x18002dee9`
- name: `?PutWord@CWordMatch@@UEAAJKPEBGKK@Z`
- size: `1001`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016e98`
- `0x18002db00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002dd02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002dd52`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002dd02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002dd52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ded7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ded7`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dc24`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dcb7`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002de02`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dec2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dc24`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dcb7`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002de02`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002dec2`

## pseudocode

```c
unsigned __int64 __fastcall CWordMatch::PutWord(CWordMatch *this, signed int a2, const unsigned __int16 *a3)
{
  __int64 v3; // r15
  const unsigned __int16 *v5; // rdi
  const WCHAR *v6; // rbp
  unsigned int v7; // esi
  int v9; // r9d
  unsigned __int64 result; // rax
  __int64 v11; // rdx
  int v12; // ebx
  const unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  __int64 cchValue; // rax
  __int64 v16; // rax
  const WCHAR *v17; // r8
  __int64 v18; // r9
  const WCHAR *v19; // r8
  __int64 v20; // r9
  const WCHAR *lpStringValue; // rcx
  __int64 v22; // rax
  WCHAR *v23; // rbx
  __int64 v24; // r9
  const WCHAR *v25; // rcx
  __int64 v26; // rax
  WCHAR *v27; // r14
  __int64 v28; // r9
  LPCWSTR lpStringSource; // [rsp+A0h] [rbp+18h] BYREF

  v3 = a2;
  v5 = a3;
  v6 = a3;
  v7 = a2;
  v9 = 0;
  while ( 1 )
  {
    result = 0;
    if ( *((_DWORD *)this + 136) )
      return result;
    v11 = v5 - a3;
    if ( v11 >= v3 )
      return result;
    v12 = v9;
    while ( result < 3 )
    {
      if ( *v5 == pszSet[result] )
      {
        v12 = 0;
        goto LABEL_17;
      }
      v12 = 1;
      ++result;
    }
    if ( v12 )
    {
      v13 = v5;
      if ( v9 )
        v13 = v6;
      v6 = v13;
      v14 = v7 + 1;
      v7 = v12;
      if ( v9 )
        v7 = v14;
      if ( v11 == (_DWORD)v3 - 1 )
      {
        if ( *((_DWORD *)this + 137) == 12 )
        {
          v19 = (const WCHAR *)((char *)this + 12);
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          *((_DWORD *)this + 136) = CompareStringW(*((_DWORD *)this + 138), *((_DWORD *)this + 139), v19, v20, v6, v7) == 2;
        }
        else if ( *((_DWORD *)this + 137) == 13 )
        {
          if ( *((_QWORD *)this + 67) )
          {
            lpStringSource = 0;
            if ( (int)CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                        (CKoreanDecomposition *)g_koreanDecomposition,
                        v6,
                        v7,
                        (unsigned __int16 **)&lpStringSource) >= 0 )
            {
              v25 = (const WCHAR *)*((_QWORD *)this + 67);
              v26 = -1;
              do
                ++v26;
              while ( v25[v26] );
              v27 = (WCHAR *)lpStringSource;
              v28 = -1;
              do
                ++v28;
              while ( lpStringSource[v28] );
              *((_DWORD *)this + 136) = FindNLSString(
                                          *((_DWORD *)this + 138),
                                          *((_DWORD *)this + 139) | 0x100000,
                                          lpStringSource,
                                          v28,
                                          v25,
                                          v26,
                                          0) >= 0;
              CoTaskMemFree(v27);
            }
          }
          else
          {
            v16 = -1;
            do
              ++v16;
            while ( *((_WORD *)this + v16 + 6) );
            *((_DWORD *)this + 136) = FindNLSString(
                                        *((_DWORD *)this + 138),
                                        *((_DWORD *)this + 139) | 0x100000,
                                        v6,
                                        v7,
                                        (LPCWSTR)this + 6,
                                        v16,
                                        0) >= 0;
          }
        }
      }
LABEL_14:
      v9 = v12;
      ++v5;
      continue;
    }
LABEL_17:
    if ( v9 != 1 )
      goto LABEL_14;
    if ( *((_DWORD *)this + 137) == 12 )
    {
      v17 = (const WCHAR *)((char *)this + 12);
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      *((_DWORD *)this + 136) = CompareStringW(*((_DWORD *)this + 138), *((_DWORD *)this + 139), v17, v18, v6, v7) == 2;
LABEL_24:
      v9 = 0;
      ++v5;
    }
    else
    {
      if ( *((_DWORD *)this + 137) != 13 )
        goto LABEL_24;
      if ( !*((_QWORD *)this + 67) )
      {
        cchValue = -1;
        do
          ++cchValue;
        while ( *((_WORD *)this + cchValue + 6) );
        *((_DWORD *)this + 136) = FindNLSString(
                                    *((_DWORD *)this + 138),
                                    *((_DWORD *)this + 139) | 0x100000,
                                    v6,
                                    v7,
                                    (LPCWSTR)this + 6,
                                    cchValue,
                                    0) >= 0;
        goto LABEL_24;
      }
      lpStringSource = 0;
      if ( (int)CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                  (CKoreanDecomposition *)g_koreanDecomposition,
                  v6,
                  v7,
                  (unsigned __int16 **)&lpStringSource) < 0 )
        goto LABEL_24;
      lpStringValue = (const WCHAR *)*((_QWORD *)this + 67);
      v22 = -1;
      do
        ++v22;
      while ( lpStringValue[v22] );
      v23 = (WCHAR *)lpStringSource;
      v24 = -1;
      do
        ++v24;
      while ( lpStringSource[v24] );
      *((_DWORD *)this + 136) = FindNLSString(
                                  *((_DWORD *)this + 138),
                                  *((_DWORD *)this + 139) | 0x100000,
                                  lpStringSource,
                                  v24,
                                  lpStringValue,
                                  v22,
                                  0) >= 0;
      CoTaskMemFree(v23);
      v9 = 0;
      ++v5;
    }
  }
}

```

## disassembly

```asm
0x18002db00  push    rbx
0x18002db02  push    rbp
0x18002db03  push    rsi
0x18002db04  push    rdi
0x18002db05  push    r12
0x18002db07  push    r13
0x18002db09  push    r14
0x18002db0b  push    r15
0x18002db0d  sub     rsp, 48h
0x18002db11  movsxd  r15, edx
0x18002db14  mov     r12, r8
0x18002db17  mov     rdi, r8
0x18002db1a  mov     rbp, r8
0x18002db1d  mov     esi, r15d
0x18002db20  lea     r8, pszSet; "\\/_"
0x18002db27  mov     r13, rcx
0x18002db2a  xor     r9d, r9d
0x18002db2d  nop     dword ptr [rax]
0x18002db30  xor     eax, eax
0x18002db32  cmp     [r13+220h], eax
0x18002db39  jnz     short loc_18002DBA5
0x18002db3b  mov     rdx, rdi
0x18002db3e  xor     ecx, ecx
0x18002db40  sub     rdx, r12
0x18002db43  sar     rdx, 1
0x18002db46  cmp     rdx, r15
0x18002db49  jge     short loc_18002DBA5
0x18002db4b  mov     ebx, r9d
0x18002db4e  cmp     rax, 3
0x18002db52  jnb     short loc_18002DB68
0x18002db54  movzx   ecx, word ptr [r8+rax*2]
0x18002db59  cmp     [rdi], cx
0x18002db5c  jz      short loc_18002DBB6
0x18002db5e  mov     ebx, 1
0x18002db63  inc     rax
0x18002db66  jmp     short loc_18002DB4E
0x18002db68  mov     eax, ebx
0x18002db6a  test    ebx, ebx
0x18002db6c  jz      loc_18002DC49
0x18002db72  cmp     eax, 1
0x18002db75  jnz     short loc_18002DB9C
0x18002db77  test    r9d, r9d
0x18002db7a  mov     rax, rdi
0x18002db7d  cmovnz  rax, rbp
0x18002db81  mov     rbp, rax
0x18002db84  lea     eax, [rsi+1]
0x18002db87  mov     esi, ebx
0x18002db89  cmovnz  esi, eax
0x18002db8c  lea     eax, [r15-1]
0x18002db90  movsxd  rcx, eax
0x18002db93  cmp     rdx, rcx
0x18002db96  jz      loc_18002DC51
0x18002db9c  mov     r9d, ebx
0x18002db9f  add     rdi, 2
0x18002dba3  jmp     short loc_18002DB30
0x18002dba5  add     rsp, 48h
0x18002dba9  pop     r15
0x18002dbab  pop     r14
0x18002dbad  pop     r13
0x18002dbaf  pop     r12
0x18002dbb1  pop     rdi
0x18002dbb2  pop     rsi
0x18002dbb3  pop     rbp
0x18002dbb4  pop     rbx
0x18002dbb5  retn
0x18002dbb6  xor     ebx, ebx
0x18002dbb8  xor     r14d, r14d
0x18002dbbb  cmp     r9d, 1
0x18002dbbf  jnz     short loc_18002DB9C
0x18002dbc1  mov     ecx, [r13+224h]
0x18002dbc8  sub     ecx, 0Ch
0x18002dbcb  jz      loc_18002DCD5
0x18002dbd1  cmp     ecx, r9d
0x18002dbd4  jnz     short loc_18002DC3D
0x18002dbd6  cmp     qword ptr [r13+218h], 0
0x18002dbde  jnz     loc_18002DD6C
0x18002dbe4  lea     rcx, [r13+0Ch]
0x18002dbe8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002dbef  nop
0x18002dbf0  inc     rax
0x18002dbf3  cmp     word ptr [rcx+rax*2], 0
0x18002dbf8  jnz     short loc_18002DBF0
0x18002dbfa  mov     edx, [r13+22Ch]
0x18002dc01  mov     r9d, esi; cchSource
0x18002dc04  mov     [rsp+88h+pcchFound], 0; pcchFound
0x18002dc0d  bts     edx, 14h; dwFindNLSStringFlags
0x18002dc11  mov     [rsp+88h+cchValue], eax; cchValue
0x18002dc15  mov     r8, rbp; lpStringSource
0x18002dc18  mov     [rsp+88h+lpStringValue], rcx; lpStringValue
0x18002dc1d  mov     ecx, [r13+228h]; Locale
0x18002dc24  call    cs:__imp_FindNLSString
0x18002dc2a  not     eax
0x18002dc2c  shr     eax, 1Fh
0x18002dc2f  mov     [r13+220h], eax
0x18002dc36  lea     r8, pszSet; "\\/_"
0x18002dc3d  mov     r9d, r14d
0x18002dc40  add     rdi, 2
0x18002dc44  jmp     loc_18002DB30
0x18002dc49  mov     r14d, ebx
0x18002dc4c  jmp     loc_18002DBBB
0x18002dc51  mov     ecx, [r13+224h]
0x18002dc58  sub     ecx, 0Ch
0x18002dc5b  jz      loc_18002DD1C
0x18002dc61  cmp     ecx, 1
0x18002dc64  jnz     loc_18002DB9C
0x18002dc6a  cmp     qword ptr [r13+218h], 0
0x18002dc72  jnz     loc_18002DE30
0x18002dc78  lea     rcx, [r13+0Ch]
0x18002dc7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002dc83  inc     rax
0x18002dc86  cmp     word ptr [rcx+rax*2], 0
0x18002dc8b  jnz     short loc_18002DC83
0x18002dc8d  mov     edx, [r13+22Ch]
0x18002dc94  mov     r9d, esi; cchSource
0x18002dc97  mov     [rsp+88h+pcchFound], 0; pcchFound
0x18002dca0  bts     edx, 14h; dwFindNLSStringFlags
0x18002dca4  mov     [rsp+88h+cchValue], eax; cchValue
0x18002dca8  mov     r8, rbp; lpStringSource
0x18002dcab  mov     [rsp+88h+lpStringValue], rcx; lpStringValue
0x18002dcb0  mov     ecx, [r13+228h]; Locale
0x18002dcb7  call    cs:__imp_FindNLSString
0x18002dcbd  not     eax
0x18002dcbf  shr     eax, 1Fh
0x18002dcc2  mov     [r13+220h], eax
0x18002dcc9  lea     r8, pszSet; "\\/_"
0x18002dcd0  jmp     loc_18002DB9C
0x18002dcd5  lea     r8, [r13+0Ch]; lpString1
0x18002dcd9  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002dce0  inc     r9; cchCount1
0x18002dce3  cmp     word ptr [r8+r9*2], 0
0x18002dce9  jnz     short loc_18002DCE0
0x18002dceb  mov     edx, [r13+22Ch]; dwCmpFlags
0x18002dcf2  mov     ecx, [r13+228h]; Locale
0x18002dcf9  mov     [rsp+88h+cchValue], esi; cchCount2
0x18002dcfd  mov     [rsp+88h+lpStringValue], rbp; lpString2
0x18002dd02  call    cs:__imp_CompareStringW
0x18002dd08  xor     ecx, ecx
0x18002dd0a  cmp     eax, 2
0x18002dd0d  setz    cl
0x18002dd10  mov     [r13+220h], ecx
0x18002dd17  jmp     loc_18002DC36
0x18002dd1c  lea     r8, [r13+0Ch]; lpString1
0x18002dd20  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002dd27  nop     word ptr [rax+rax+00000000h]
0x18002dd30  inc     r9; cchCount1
0x18002dd33  cmp     word ptr [r8+r9*2], 0
0x18002dd39  jnz     short loc_18002DD30
0x18002dd3b  mov     edx, [r13+22Ch]; dwCmpFlags
0x18002dd42  mov     ecx, [r13+228h]; Locale
0x18002dd49  mov     [rsp+88h+cchValue], esi; cchCount2
0x18002dd4d  mov     [rsp+88h+lpStringValue], rbp; lpString2
0x18002dd52  call    cs:__imp_CompareStringW
0x18002dd58  xor     ecx, ecx
0x18002dd5a  cmp     eax, 2
0x18002dd5d  setz    cl
0x18002dd60  mov     [r13+220h], ecx
0x18002dd67  jmp     loc_18002DCC9
0x18002dd6c  lea     r9, [rsp+88h+lpStringSource]; unsigned __int16 **
0x18002dd74  mov     [rsp+88h+lpStringSource], 0
0x18002dd80  mov     r8d, esi; unsigned int
0x18002dd83  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18002dd8a  mov     rdx, rbp; unsigned __int16 *
0x18002dd8d  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGKPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ulong,ushort * *)
0x18002dd92  test    eax, eax
0x18002dd94  js      loc_18002DC36
0x18002dd9a  mov     rcx, [r13+218h]
0x18002dda1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002dda8  nop     dword ptr [rax+rax+00000000h]
0x18002ddb0  inc     rax
0x18002ddb3  cmp     word ptr [rcx+rax*2], 0
0x18002ddb8  jnz     short loc_18002DDB0
0x18002ddba  mov     rbx, [rsp+88h+lpStringSource]
0x18002ddc2  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002ddc9  nop     dword ptr [rax+00000000h]
0x18002ddd0  inc     r9; cchSource
0x18002ddd3  cmp     word ptr [rbx+r9*2], 0
0x18002ddd9  jnz     short loc_18002DDD0
0x18002dddb  mov     edx, [r13+22Ch]
0x18002dde2  mov     r8, rbx; lpStringSource
0x18002dde5  mov     [rsp+88h+pcchFound], 0; pcchFound
0x18002ddee  bts     edx, 14h; dwFindNLSStringFlags
0x18002ddf2  mov     [rsp+88h+cchValue], eax; cchValue
0x18002ddf6  mov     [rsp+88h+lpStringValue], rcx; lpStringValue
0x18002ddfb  mov     ecx, [r13+228h]; Locale
0x18002de02  call    cs:__imp_FindNLSString
0x18002de08  not     eax
0x18002de0a  mov     rcx, rbx; pv
0x18002de0d  shr     eax, 1Fh
0x18002de10  mov     [r13+220h], eax
0x18002de17  call    cs:__imp_CoTaskMemFree
0x18002de1d  lea     r8, pszSet; "\\/_"
0x18002de24  mov     r9d, r14d
0x18002de27  add     rdi, 2
0x18002de2b  jmp     loc_18002DB30
0x18002de30  lea     r9, [rsp+88h+lpStringSource]; unsigned __int16 **
0x18002de38  mov     [rsp+88h+lpStringSource], 0
0x18002de44  mov     r8d, esi; unsigned int
0x18002de47  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18002de4e  mov     rdx, rbp; unsigned __int16 *
0x18002de51  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGKPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ulong,ushort * *)
0x18002de56  test    eax, eax
0x18002de58  js      loc_18002DCC9
0x18002de5e  mov     rcx, [r13+218h]
0x18002de65  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002de6c  nop     dword ptr [rax+00h]
0x18002de70  inc     rax
0x18002de73  cmp     word ptr [rcx+rax*2], 0
0x18002de78  jnz     short loc_18002DE70
0x18002de7a  mov     r14, [rsp+88h+lpStringSource]
0x18002de82  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002de89  nop     dword ptr [rax+00000000h]
0x18002de90  inc     r9; cchSource
0x18002de93  cmp     word ptr [r14+r9*2], 0
0x18002de99  jnz     short loc_18002DE90
0x18002de9b  mov     edx, [r13+22Ch]
0x18002dea2  mov     r8, r14; lpStringSource
0x18002dea5  mov     [rsp+88h+pcchFound], 0; pcchFound
0x18002deae  bts     edx, 14h; dwFindNLSStringFlags
0x18002deb2  mov     [rsp+88h+cchValue], eax; cchValue
0x18002deb6  mov     [rsp+88h+lpStringValue], rcx; lpStringValue
0x18002debb  mov     ecx, [r13+228h]; Locale
0x18002dec2  call    cs:__imp_FindNLSString
0x18002dec8  not     eax
0x18002deca  mov     rcx, r14; pv
0x18002decd  shr     eax, 1Fh
0x18002ded0  mov     [r13+220h], eax
0x18002ded7  call    cs:__imp_CoTaskMemFree
0x18002dedd  lea     r8, pszSet; "\\/_"
0x18002dee4  jmp     loc_18002DB9C
```
