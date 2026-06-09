# CUserHangSignature::IsSame(_USER_HANG_SIGNATURE *,_USER_HANG_SIGNATURE *)

- ea: `0x14002a0d0`
- end: `0x14002a35c`
- name: `?IsSame@CUserHangSignature@@SAHPEAU_USER_HANG_SIGNATURE@@0@Z`
- size: `652`
- prototype: `static int(struct _USER_HANG_SIGNATURE *, struct _USER_HANG_SIGNATURE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026a70`

## callees

- `0x140015b40`
- `0x14002a0d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a152`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a19b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a1e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a22d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a276`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a2be`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a152`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a19b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a1e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a22d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a276`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002a2be`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a2df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a2fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a31c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a338`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a2df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a2fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a31c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002a338`

## pseudocode

```c
__int64 __fastcall CUserHangSignature::IsSame(struct _USER_HANG_SIGNATURE *a1, struct _USER_HANG_SIGNATURE *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // ebp
  const WCHAR *v8; // r8
  __int64 v9; // r9
  const WCHAR *v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // r8
  __int64 v13; // r9
  const WCHAR *v14; // rcx
  __int64 v15; // rdx
  const WCHAR *v16; // r8
  __int64 v17; // r9
  const WCHAR *v18; // rcx
  __int64 v19; // rdx
  const WCHAR *v20; // r8
  __int64 v21; // r9
  const WCHAR *v22; // rcx
  __int64 v23; // rdx
  const WCHAR *v24; // r8
  __int64 v25; // r9
  const WCHAR *v26; // rcx

  if ( a1 && a2 )
  {
    if ( *((_DWORD *)a1 + 156) != *((_DWORD *)a2 + 156) )
      return 0;
    if ( *((_DWORD *)a1 + 131) != *((_DWORD *)a2 + 131) )
      return 0;
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)a2 + v5) );
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)a1 + v6) );
    if ( v6 != v5 )
      return 0;
    v7 = 1;
    if ( v6 )
    {
      if ( CompareStringOrdinal((LPCWCH)a1, v6, (LPCWCH)a2, v5, 1) != 2 )
        return 0;
    }
    v8 = (const WCHAR *)((char *)a2 + 256);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = (const WCHAR *)((char *)a1 + 256);
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    if ( v11 != v9 || v11 && CompareStringOrdinal(v10, v11, v8, v9, 1) != 2 )
      return 0;
    v12 = (const WCHAR *)((char *)a2 + 384);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = (const WCHAR *)((char *)a1 + 384);
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    if ( v15 != v13 || v15 && CompareStringOrdinal(v14, v15, v12, v13, 1) != 2 )
      return 0;
    v16 = (const WCHAR *)((char *)a2 + 628);
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    v18 = (const WCHAR *)((char *)a1 + 628);
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 != v17 || v19 && CompareStringOrdinal(v18, v19, v16, v17, 1) != 2 )
      return 0;
    v20 = (const WCHAR *)((char *)a2 + 884);
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v22 = (const WCHAR *)((char *)a1 + 884);
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    if ( v23 != v21 || v23 && CompareStringOrdinal(v22, v23, v20, v21, 1) != 2 )
      return 0;
    v24 = (const WCHAR *)((char *)a2 + 1012);
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v26 = (const WCHAR *)((char *)a1 + 1012);
    do
      ++v4;
    while ( v26[v4] );
    if ( v4 != v25
      || v4 && CompareStringOrdinal(v26, v4, v24, v25, 1) != 2
      || RtlCompareMemory((char *)a1 + 516, (char *)a2 + 516, 8u) != 8
      || RtlCompareMemory((char *)a1 + 1144, (char *)a2 + 1144, 8u) != 8
      || RtlCompareMemory((char *)a1 + 528, (char *)a2 + 528, 0x30u) != 48
      || RtlCompareMemory((char *)a1 + 576, (char *)a2 + 576, 0x30u) != 48 )
    {
      return 0;
    }
    return v7;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 0;
  }
}

```

## disassembly

```asm
0x14002a0d0  push    rbx
0x14002a0d2  push    rbp
0x14002a0d3  push    rsi
0x14002a0d4  push    rdi
0x14002a0d5  push    r14
0x14002a0d7  sub     rsp, 30h
0x14002a0db  xor     r14d, r14d
0x14002a0de  mov     rdi, rdx
0x14002a0e1  mov     rsi, rcx
0x14002a0e4  test    rcx, rcx
0x14002a0e7  jz      loc_14002A34A
0x14002a0ed  test    rdx, rdx
0x14002a0f0  jz      loc_14002A34A
0x14002a0f6  mov     eax, [rdx+270h]
0x14002a0fc  cmp     [rcx+270h], eax
0x14002a102  jnz     loc_14002A343
0x14002a108  mov     eax, [rdx+20Ch]
0x14002a10e  cmp     [rcx+20Ch], eax
0x14002a114  jnz     loc_14002A343
0x14002a11a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002a11e  mov     r9, rbx
0x14002a121  inc     r9; cchCount2
0x14002a124  cmp     [rdx+r9*2], r14w
0x14002a129  jnz     short loc_14002A121
0x14002a12b  mov     rdx, rbx
0x14002a12e  inc     rdx; cchCount1
0x14002a131  cmp     [rcx+rdx*2], r14w
0x14002a136  jnz     short loc_14002A12E
0x14002a138  cmp     rdx, r9
0x14002a13b  jnz     loc_14002A343
0x14002a141  mov     ebp, 1
0x14002a146  test    rdx, rdx
0x14002a149  jz      short loc_14002A161
0x14002a14b  mov     r8, rdi; lpString2
0x14002a14e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a152  call    cs:__imp_CompareStringOrdinal
0x14002a158  cmp     eax, 2
0x14002a15b  jnz     loc_14002A343
0x14002a161  lea     r8, [rdi+100h]; lpString2
0x14002a168  mov     r9, rbx
0x14002a16b  inc     r9; cchCount2
0x14002a16e  cmp     [r8+r9*2], r14w
0x14002a173  jnz     short loc_14002A16B
0x14002a175  lea     rcx, [rsi+100h]; lpString1
0x14002a17c  mov     rdx, rbx
0x14002a17f  inc     rdx; cchCount1
0x14002a182  cmp     [rcx+rdx*2], r14w
0x14002a187  jnz     short loc_14002A17F
0x14002a189  cmp     rdx, r9
0x14002a18c  jnz     loc_14002A343
0x14002a192  test    rdx, rdx
0x14002a195  jz      short loc_14002A1AA
0x14002a197  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a19b  call    cs:__imp_CompareStringOrdinal
0x14002a1a1  cmp     eax, 2
0x14002a1a4  jnz     loc_14002A343
0x14002a1aa  lea     r8, [rdi+180h]; lpString2
0x14002a1b1  mov     r9, rbx
0x14002a1b4  inc     r9; cchCount2
0x14002a1b7  cmp     [r8+r9*2], r14w
0x14002a1bc  jnz     short loc_14002A1B4
0x14002a1be  lea     rcx, [rsi+180h]; lpString1
0x14002a1c5  mov     rdx, rbx
0x14002a1c8  inc     rdx; cchCount1
0x14002a1cb  cmp     [rcx+rdx*2], r14w
0x14002a1d0  jnz     short loc_14002A1C8
0x14002a1d2  cmp     rdx, r9
0x14002a1d5  jnz     loc_14002A343
0x14002a1db  test    rdx, rdx
0x14002a1de  jz      short loc_14002A1F3
0x14002a1e0  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a1e4  call    cs:__imp_CompareStringOrdinal
0x14002a1ea  cmp     eax, 2
0x14002a1ed  jnz     loc_14002A343
0x14002a1f3  lea     r8, [rdi+274h]; lpString2
0x14002a1fa  mov     r9, rbx
0x14002a1fd  inc     r9; cchCount2
0x14002a200  cmp     [r8+r9*2], r14w
0x14002a205  jnz     short loc_14002A1FD
0x14002a207  lea     rcx, [rsi+274h]; lpString1
0x14002a20e  mov     rdx, rbx
0x14002a211  inc     rdx; cchCount1
0x14002a214  cmp     [rcx+rdx*2], r14w
0x14002a219  jnz     short loc_14002A211
0x14002a21b  cmp     rdx, r9
0x14002a21e  jnz     loc_14002A343
0x14002a224  test    rdx, rdx
0x14002a227  jz      short loc_14002A23C
0x14002a229  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a22d  call    cs:__imp_CompareStringOrdinal
0x14002a233  cmp     eax, 2
0x14002a236  jnz     loc_14002A343
0x14002a23c  lea     r8, [rdi+374h]; lpString2
0x14002a243  mov     r9, rbx
0x14002a246  inc     r9; cchCount2
0x14002a249  cmp     [r8+r9*2], r14w
0x14002a24e  jnz     short loc_14002A246
0x14002a250  lea     rcx, [rsi+374h]; lpString1
0x14002a257  mov     rdx, rbx
0x14002a25a  inc     rdx; cchCount1
0x14002a25d  cmp     [rcx+rdx*2], r14w
0x14002a262  jnz     short loc_14002A25A
0x14002a264  cmp     rdx, r9
0x14002a267  jnz     loc_14002A343
0x14002a26d  test    rdx, rdx
0x14002a270  jz      short loc_14002A285
0x14002a272  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a276  call    cs:__imp_CompareStringOrdinal
0x14002a27c  cmp     eax, 2
0x14002a27f  jnz     loc_14002A343
0x14002a285  lea     r8, [rdi+3F4h]; lpString2
0x14002a28c  mov     r9, rbx
0x14002a28f  inc     r9; cchCount2
0x14002a292  cmp     [r8+r9*2], r14w
0x14002a297  jnz     short loc_14002A28F
0x14002a299  lea     rcx, [rsi+3F4h]; lpString1
0x14002a2a0  inc     rbx
0x14002a2a3  cmp     [rcx+rbx*2], r14w
0x14002a2a8  jnz     short loc_14002A2A0
0x14002a2aa  cmp     rbx, r9
0x14002a2ad  jnz     loc_14002A343
0x14002a2b3  test    rbx, rbx
0x14002a2b6  jz      short loc_14002A2C9
0x14002a2b8  mov     edx, ebx; cchCount1
0x14002a2ba  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002a2be  call    cs:__imp_CompareStringOrdinal
0x14002a2c4  cmp     eax, 2
0x14002a2c7  jnz     short loc_14002A343
0x14002a2c9  mov     ebx, 8
0x14002a2ce  lea     rdx, [rdi+204h]; Source2
0x14002a2d5  mov     r8d, ebx; Length
0x14002a2d8  lea     rcx, [rsi+204h]; Source1
0x14002a2df  call    cs:__imp_RtlCompareMemory
0x14002a2e5  cmp     rax, rbx
0x14002a2e8  jnz     short loc_14002A343
0x14002a2ea  lea     rdx, [rdi+478h]; Source2
0x14002a2f1  mov     r8d, ebx; Length
0x14002a2f4  lea     rcx, [rsi+478h]; Source1
0x14002a2fb  call    cs:__imp_RtlCompareMemory
0x14002a301  cmp     rax, rbx
0x14002a304  jnz     short loc_14002A343
0x14002a306  mov     ebx, 30h ; '0'
0x14002a30b  lea     rdx, [rdi+210h]; Source2
0x14002a312  mov     r8d, ebx; Length
0x14002a315  lea     rcx, [rsi+210h]; Source1
0x14002a31c  call    cs:__imp_RtlCompareMemory
0x14002a322  cmp     rax, rbx
0x14002a325  jnz     short loc_14002A343
0x14002a327  lea     rdx, [rdi+240h]; Source2
0x14002a32e  mov     r8d, ebx; Length
0x14002a331  lea     rcx, [rsi+240h]; Source1
0x14002a338  call    cs:__imp_RtlCompareMemory
0x14002a33e  cmp     rax, rbx
0x14002a341  jz      short loc_14002A346
0x14002a343  mov     ebp, r14d
0x14002a346  mov     eax, ebp
0x14002a348  jmp     short loc_14002A351
0x14002a34a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002a34f  xor     eax, eax
0x14002a351  add     rsp, 30h
0x14002a355  pop     r14
0x14002a357  pop     rdi
0x14002a358  pop     rsi
0x14002a359  pop     rbp
0x14002a35a  pop     rbx
0x14002a35b  retn
```
