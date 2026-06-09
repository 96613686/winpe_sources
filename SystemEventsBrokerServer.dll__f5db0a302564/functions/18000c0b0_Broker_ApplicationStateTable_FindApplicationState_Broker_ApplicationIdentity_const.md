# Broker::ApplicationStateTable::FindApplicationState(Broker::ApplicationIdentity const &)

- ea: `0x18000c0b0`
- end: `0x18000c390`
- name: `?FindApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z`
- size: `736`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x18000c0b0`
- `0x18001732c`
- `0x18001d9ac`
- `0x18001f3fc`
- `0x180022434`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c15c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c296`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c15c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c296`

## pseudocode

```c
_QWORD *__fastcall Broker::ApplicationStateTable::FindApplicationState(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 *v3; // rsi
  __int64 v6; // rdi
  int v7; // r12d
  __int64 *v8; // rbx
  const void *v9; // rcx
  size_t v10; // rax
  size_t v11; // r8
  int v12; // edi
  const WCHAR *lpString2; // rax
  const WCHAR *v14; // r8
  int v15; // eax
  _QWORD *v16; // rax
  int v17; // eax
  const void *v18; // rdx
  size_t v19; // rax
  size_t v20; // r8
  const WCHAR *v21; // rax
  const WCHAR *v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v28; // eax
  void **pExceptionObject; // [rsp+58h] [rbp-70h] BYREF
  __int128 v30; // [rsp+60h] [rbp-68h]
  int v31; // [rsp+70h] [rbp-58h]

  v3 = *(__int64 **)(a1 + 32);
  DWORD1(v30) = 0;
  v6 = a1;
  v7 = -1;
  v8 = (__int64 *)v3[1];
  if ( *((_BYTE *)v8 + 25) )
    goto LABEL_12;
  do
  {
    v9 = (const void *)v8[4];
    v10 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
    v11 = v8[5] - (_QWORD)v9;
    if ( v11 >= v10 )
    {
      if ( v11 <= v10 )
      {
        v17 = memcmp_0(v9, *(const void **)a3, v11);
        if ( v17 < 0 )
          v12 = -1;
        else
          v12 = v17 > 0;
      }
      else
      {
        v12 = 1;
      }
    }
    else
    {
      v12 = -1;
    }
    if ( *(_QWORD *)(a3 + 48) <= 7u )
      lpString2 = (const WCHAR *)(a3 + 24);
    else
      lpString2 = *(const WCHAR **)(a3 + 24);
    v14 = (const WCHAR *)(v8 + 7);
    if ( (unsigned __int64)v8[10] > 7 )
      v14 = *(const WCHAR **)v14;
    v15 = CompareStringEx(&LocaleName, 1u, v14, *((_DWORD *)v8 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0);
    if ( v15 == 1 )
    {
LABEL_9:
      v8 += 2;
      goto LABEL_10;
    }
    v28 = v15 - 2;
    if ( v28 )
    {
      if ( v28 != 1 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)&pExceptionObject);
        throw (Broker::Win32Error *)&pExceptionObject;
      }
    }
    else if ( v12 == -1 )
    {
      goto LABEL_9;
    }
    v3 = v8;
LABEL_10:
    v8 = (__int64 *)*v8;
  }
  while ( !*((_BYTE *)v8 + 25) );
  v6 = a1;
LABEL_12:
  if ( *((_BYTE *)v3 + 25) )
    goto LABEL_13;
  v18 = (const void *)v3[4];
  v19 = v3[5] - (_QWORD)v18;
  v20 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( v20 >= v19 )
  {
    if ( v20 <= v19 )
    {
      v25 = memcmp_0(*(const void **)a3, v18, v20);
      if ( v25 >= 0 )
        v7 = v25 > 0;
    }
    else
    {
      v7 = 1;
    }
  }
  v21 = (const WCHAR *)(v3 + 7);
  if ( (unsigned __int64)v3[10] > 7 )
    v21 = *(const WCHAR **)v21;
  v22 = (const WCHAR *)(a3 + 24);
  if ( *(_QWORD *)(a3 + 48) > 7u )
    v22 = *(const WCHAR **)v22;
  v23 = CompareStringEx(&LocaleName, 1u, v22, *(_DWORD *)(a3 + 40), v21, *((_DWORD *)v3 + 18), 0, 0, 0);
  if ( v23 == 1 )
    goto LABEL_13;
  v24 = v23 - 2;
  if ( !v24 )
  {
    if ( v7 != -1 )
      goto LABEL_40;
    goto LABEL_13;
  }
  if ( v24 != 1 )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&pExceptionObject);
    throw (Broker::Win32Error *)&pExceptionObject;
  }
LABEL_40:
  if ( v3 == *(__int64 **)(v6 + 32) )
  {
LABEL_13:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v16 = (_QWORD *)(a3 + 56);
      if ( *(_QWORD *)(a3 + 80) > 7u )
        v16 = (_QWORD *)*v16;
      WPP_SF__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v16);
    }
    v31 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    v30 = 0;
    throw (Broker::NotFound *)&pExceptionObject;
  }
  *a2 = 0;
  a2[1] = 0;
  v26 = v3[16];
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
  *a2 = v3[15];
  a2[1] = v3[16];
  return a2;
}

```

## disassembly

```asm
0x18000c0b0  mov     [rsp+arg_0], rcx
0x18000c0b5  push    rbx
0x18000c0b6  push    rbp
0x18000c0b7  push    rsi
0x18000c0b8  push    rdi
0x18000c0b9  push    r12
0x18000c0bb  push    r13
0x18000c0bd  push    r14
0x18000c0bf  push    r15
0x18000c0c1  sub     rsp, 88h
0x18000c0c8  mov     rsi, [rcx+20h]
0x18000c0cc  xor     eax, eax
0x18000c0ce  xor     r9d, r9d
0x18000c0d1  mov     [rsp+0C8h+var_64], eax
0x18000c0d5  mov     r14, r8
0x18000c0d8  mov     rbp, rdx
0x18000c0db  mov     rdi, rcx
0x18000c0de  mov     r12d, 0FFFFFFFFh
0x18000c0e4  mov     rbx, [rsi+8]
0x18000c0e8  cmp     [rbx+19h], al
0x18000c0eb  jnz     loc_18000C187
0x18000c0f1  mov     rdx, [r14]; Buf2
0x18000c0f4  mov     rax, [r14+8]
0x18000c0f8  mov     rcx, [rbx+20h]; Buf1
0x18000c0fc  sub     rax, rdx
0x18000c0ff  mov     r8, [rbx+28h]
0x18000c103  sub     r8, rcx; Size
0x18000c106  cmp     r8, rax
0x18000c109  jnb     loc_18000C20E
0x18000c10f  mov     edi, r12d
0x18000c112  cmp     qword ptr [r14+30h], 7
0x18000c117  mov     ecx, [r14+28h]
0x18000c11b  jbe     loc_18000C1FD
0x18000c121  mov     rax, [r14+18h]
0x18000c125  cmp     qword ptr [rbx+50h], 7
0x18000c12a  lea     r8, [rbx+38h]; lpString1
0x18000c12e  ja      loc_18000C206
0x18000c134  mov     [rsp+0C8h+lParam], r9; lParam
0x18000c139  mov     edx, 1; dwCmpFlags
0x18000c13e  mov     [rsp+0C8h+lpReserved], r9; lpReserved
0x18000c143  mov     [rsp+0C8h+lpVersionInformation], r9; lpVersionInformation
0x18000c148  mov     r9d, [rbx+48h]; cchCount1
0x18000c14c  mov     [rsp+0C8h+cchCount2], ecx; cchCount2
0x18000c150  lea     rcx, LocaleName; lpLocaleName
0x18000c157  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18000c15c  call    cs:__imp_CompareStringEx
0x18000c162  cmp     eax, 1
0x18000c165  jnz     loc_18000C36A
0x18000c16b  add     rbx, 10h
0x18000c16f  mov     rbx, [rbx]
0x18000c172  xor     r9d, r9d
0x18000c175  cmp     [rbx+19h], r9b
0x18000c179  jz      loc_18000C0F1
0x18000c17f  mov     rdi, [rsp+0C8h+arg_0]
0x18000c187  cmp     byte ptr [rsi+19h], 0
0x18000c18b  jz      loc_18000C238
0x18000c191  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c198  test    byte ptr [rcx+1Ch], 2
0x18000c19c  jz      short loc_18000C1CF
0x18000c19e  cmp     byte ptr [rcx+19h], 3
0x18000c1a2  jb      short loc_18000C1CF
0x18000c1a4  cmp     qword ptr [r14+50h], 7
0x18000c1a9  lea     rax, [r14+38h]
0x18000c1ad  jbe     short loc_18000C1B2
0x18000c1af  mov     rax, [rax]
0x18000c1b2  mov     r9, [r14]
0x18000c1b5  lea     r8, WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids
0x18000c1bc  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c1c0  mov     edx, 0Bh
0x18000c1c5  mov     [rsp+0C8h+lpString2], rax; __int64
0x18000c1ca  call    WPP_SF__sid_S
0x18000c1cf  xorps   xmm0, xmm0
0x18000c1d2  mov     [rsp+0C8h+var_58], 3
0x18000c1da  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000c1e1  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000c1e8  mov     [rsp+0C8h+pExceptionObject], rax
0x18000c1ed  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000c1f2  movups  xmmword ptr [rsp+60h], xmm0
0x18000c1f7  call    _CxxThrowException_0
0x18000c1fd  lea     rax, [r14+18h]
0x18000c201  jmp     loc_18000C125
0x18000c206  mov     r8, [r8]
0x18000c209  jmp     loc_18000C134
0x18000c20e  jbe     short loc_18000C21A
0x18000c210  mov     edi, 1
0x18000c215  jmp     loc_18000C112
0x18000c21a  call    memcmp_0
0x18000c21f  xor     r9d, r9d
0x18000c222  test    eax, eax
0x18000c224  js      loc_18000C362
0x18000c22a  test    eax, eax
0x18000c22c  mov     edi, r9d
0x18000c22f  setnle  dil
0x18000c233  jmp     loc_18000C112
0x18000c238  mov     rdx, [rsi+20h]; Buf2
0x18000c23c  mov     rax, [rsi+28h]
0x18000c240  mov     rcx, [r14]; Buf1
0x18000c243  sub     rax, rdx
0x18000c246  mov     r8, [r14+8]
0x18000c24a  sub     r8, rcx; Size
0x18000c24d  cmp     r8, rax
0x18000c250  jnb     short loc_18000C2D0
0x18000c252  cmp     qword ptr [rsi+50h], 7
0x18000c257  lea     rax, [rsi+38h]
0x18000c25b  mov     ecx, [rsi+48h]
0x18000c25e  jbe     short loc_18000C263
0x18000c260  mov     rax, [rax]
0x18000c263  cmp     qword ptr [r14+30h], 7
0x18000c268  lea     r8, [r14+18h]; lpString1
0x18000c26c  ja      short loc_18000C2CB
0x18000c26e  mov     [rsp+0C8h+lParam], r9; lParam
0x18000c273  mov     edx, 1; dwCmpFlags
0x18000c278  mov     [rsp+0C8h+lpReserved], r9; lpReserved
0x18000c27d  mov     [rsp+0C8h+lpVersionInformation], r9; lpVersionInformation
0x18000c282  mov     r9d, [r14+28h]; cchCount1
0x18000c286  mov     [rsp+0C8h+cchCount2], ecx; cchCount2
0x18000c28a  lea     rcx, LocaleName; lpLocaleName
0x18000c291  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18000c296  call    cs:__imp_CompareStringEx
0x18000c29c  cmp     eax, 1
0x18000c29f  jz      loc_18000C191
0x18000c2a5  sub     eax, 2
0x18000c2a8  jz      short loc_18000C30A
0x18000c2aa  cmp     eax, 1
0x18000c2ad  jz      short loc_18000C314
0x18000c2af  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x18000c2b4  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000c2b9  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c2c0  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000c2c5  call    _CxxThrowException_0
0x18000c2cb  mov     r8, [r8]
0x18000c2ce  jmp     short loc_18000C26E
0x18000c2d0  jbe     short loc_18000C2DD
0x18000c2d2  mov     r12d, 1
0x18000c2d8  jmp     loc_18000C252
0x18000c2dd  call    memcmp_0
0x18000c2e2  xor     r9d, r9d
0x18000c2e5  test    eax, eax
0x18000c2e7  js      loc_18000C252
0x18000c2ed  mov     r12d, r9d
0x18000c2f0  setnle  r12b
0x18000c2f4  jmp     loc_18000C252
0x18000c2f9  cmp     edi, r12d
0x18000c2fc  jz      loc_18000C16B
0x18000c302  mov     rsi, rbx
0x18000c305  jmp     loc_18000C16F
0x18000c30a  cmp     r12d, 0FFFFFFFFh
0x18000c30e  jz      loc_18000C191
0x18000c314  cmp     rsi, [rdi+20h]
0x18000c318  jz      loc_18000C191
0x18000c31e  xor     eax, eax
0x18000c320  mov     [rbp+0], rax
0x18000c324  mov     [rbp+8], rax
0x18000c328  mov     rax, [rsi+80h]
0x18000c32f  test    rax, rax
0x18000c332  jz      short loc_18000C338
0x18000c334  lock inc dword ptr [rax+8]
0x18000c338  mov     rax, [rsi+78h]
0x18000c33c  mov     [rbp+0], rax
0x18000c340  mov     rax, [rsi+80h]
0x18000c347  mov     [rbp+8], rax
0x18000c34b  mov     rax, rbp
0x18000c34e  add     rsp, 88h
0x18000c355  pop     r15
0x18000c357  pop     r14
0x18000c359  pop     r13
0x18000c35b  pop     r12
0x18000c35d  pop     rdi
0x18000c35e  pop     rsi
0x18000c35f  pop     rbp
0x18000c360  pop     rbx
0x18000c361  retn
0x18000c362  mov     edi, r12d
0x18000c365  jmp     loc_18000C112
0x18000c36a  sub     eax, 2
0x18000c36d  jz      short loc_18000C2F9
0x18000c36f  cmp     eax, 1
0x18000c372  jz      short loc_18000C302
0x18000c374  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x18000c379  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000c37e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c385  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000c38a  call    _CxxThrowException_0
```
