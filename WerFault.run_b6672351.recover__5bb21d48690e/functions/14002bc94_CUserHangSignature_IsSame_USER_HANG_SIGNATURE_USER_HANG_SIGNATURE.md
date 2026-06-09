# CUserHangSignature::IsSame(_USER_HANG_SIGNATURE *,_USER_HANG_SIGNATURE *)

- ea: `0x14002bc94`
- end: `0x14002bf61`
- name: `?IsSame@CUserHangSignature@@SAHPEAU_USER_HANG_SIGNATURE@@0@Z`
- size: `717`
- prototype: `static int(struct _USER_HANG_SIGNATURE *, struct _USER_HANG_SIGNATURE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002840c`

## callees

- `0x1400166ec`
- `0x14002bc94`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bd16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bd65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bdb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002be03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002be52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bea0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bd16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bd65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bdb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002be03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002be52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002bea0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002becb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002beed`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002bf14`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002bf36`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002becb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002beed`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002bf14`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002bf36`

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
0x14002bc94  push    rbx
0x14002bc96  push    rbp
0x14002bc97  push    rsi
0x14002bc98  push    rdi
0x14002bc99  push    r14
0x14002bc9b  sub     rsp, 30h
0x14002bc9f  xor     r14d, r14d
0x14002bca2  mov     rdi, rdx
0x14002bca5  mov     rsi, rcx
0x14002bca8  test    rcx, rcx
0x14002bcab  jz      loc_14002BF4E
0x14002bcb1  test    rdx, rdx
0x14002bcb4  jz      loc_14002BF4E
0x14002bcba  mov     eax, [rdx+270h]
0x14002bcc0  cmp     [rcx+270h], eax
0x14002bcc6  jnz     loc_14002BF47
0x14002bccc  mov     eax, [rdx+20Ch]
0x14002bcd2  cmp     [rcx+20Ch], eax
0x14002bcd8  jnz     loc_14002BF47
0x14002bcde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002bce2  mov     r9, rbx
0x14002bce5  inc     r9; cchCount2
0x14002bce8  cmp     [rdx+r9*2], r14w
0x14002bced  jnz     short loc_14002BCE5
0x14002bcef  mov     rdx, rbx
0x14002bcf2  inc     rdx; cchCount1
0x14002bcf5  cmp     [rcx+rdx*2], r14w
0x14002bcfa  jnz     short loc_14002BCF2
0x14002bcfc  cmp     rdx, r9
0x14002bcff  jnz     loc_14002BF47
0x14002bd05  mov     ebp, 1
0x14002bd0a  test    rdx, rdx
0x14002bd0d  jz      short loc_14002BD2B
0x14002bd0f  mov     r8, rdi; lpString2
0x14002bd12  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002bd16  call    cs:__imp_CompareStringOrdinal
0x14002bd1d  nop     dword ptr [rax+rax+00h]
0x14002bd22  cmp     eax, 2
0x14002bd25  jnz     loc_14002BF47
0x14002bd2b  lea     r8, [rdi+100h]; lpString2
0x14002bd32  mov     r9, rbx
0x14002bd35  inc     r9; cchCount2
0x14002bd38  cmp     [r8+r9*2], r14w
0x14002bd3d  jnz     short loc_14002BD35
0x14002bd3f  lea     rcx, [rsi+100h]; lpString1
0x14002bd46  mov     rdx, rbx
0x14002bd49  inc     rdx; cchCount1
0x14002bd4c  cmp     [rcx+rdx*2], r14w
0x14002bd51  jnz     short loc_14002BD49
0x14002bd53  cmp     rdx, r9
0x14002bd56  jnz     loc_14002BF47
0x14002bd5c  test    rdx, rdx
0x14002bd5f  jz      short loc_14002BD7A
0x14002bd61  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002bd65  call    cs:__imp_CompareStringOrdinal
0x14002bd6c  nop     dword ptr [rax+rax+00h]
0x14002bd71  cmp     eax, 2
0x14002bd74  jnz     loc_14002BF47
0x14002bd7a  lea     r8, [rdi+180h]; lpString2
0x14002bd81  mov     r9, rbx
0x14002bd84  inc     r9; cchCount2
0x14002bd87  cmp     [r8+r9*2], r14w
0x14002bd8c  jnz     short loc_14002BD84
0x14002bd8e  lea     rcx, [rsi+180h]; lpString1
0x14002bd95  mov     rdx, rbx
0x14002bd98  inc     rdx; cchCount1
0x14002bd9b  cmp     [rcx+rdx*2], r14w
0x14002bda0  jnz     short loc_14002BD98
0x14002bda2  cmp     rdx, r9
0x14002bda5  jnz     loc_14002BF47
0x14002bdab  test    rdx, rdx
0x14002bdae  jz      short loc_14002BDC9
0x14002bdb0  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002bdb4  call    cs:__imp_CompareStringOrdinal
0x14002bdbb  nop     dword ptr [rax+rax+00h]
0x14002bdc0  cmp     eax, 2
0x14002bdc3  jnz     loc_14002BF47
0x14002bdc9  lea     r8, [rdi+274h]; lpString2
0x14002bdd0  mov     r9, rbx
0x14002bdd3  inc     r9; cchCount2
0x14002bdd6  cmp     [r8+r9*2], r14w
0x14002bddb  jnz     short loc_14002BDD3
0x14002bddd  lea     rcx, [rsi+274h]; lpString1
0x14002bde4  mov     rdx, rbx
0x14002bde7  inc     rdx; cchCount1
0x14002bdea  cmp     [rcx+rdx*2], r14w
0x14002bdef  jnz     short loc_14002BDE7
0x14002bdf1  cmp     rdx, r9
0x14002bdf4  jnz     loc_14002BF47
0x14002bdfa  test    rdx, rdx
0x14002bdfd  jz      short loc_14002BE18
0x14002bdff  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002be03  call    cs:__imp_CompareStringOrdinal
0x14002be0a  nop     dword ptr [rax+rax+00h]
0x14002be0f  cmp     eax, 2
0x14002be12  jnz     loc_14002BF47
0x14002be18  lea     r8, [rdi+374h]; lpString2
0x14002be1f  mov     r9, rbx
0x14002be22  inc     r9; cchCount2
0x14002be25  cmp     [r8+r9*2], r14w
0x14002be2a  jnz     short loc_14002BE22
0x14002be2c  lea     rcx, [rsi+374h]; lpString1
0x14002be33  mov     rdx, rbx
0x14002be36  inc     rdx; cchCount1
0x14002be39  cmp     [rcx+rdx*2], r14w
0x14002be3e  jnz     short loc_14002BE36
0x14002be40  cmp     rdx, r9
0x14002be43  jnz     loc_14002BF47
0x14002be49  test    rdx, rdx
0x14002be4c  jz      short loc_14002BE67
0x14002be4e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002be52  call    cs:__imp_CompareStringOrdinal
0x14002be59  nop     dword ptr [rax+rax+00h]
0x14002be5e  cmp     eax, 2
0x14002be61  jnz     loc_14002BF47
0x14002be67  lea     r8, [rdi+3F4h]; lpString2
0x14002be6e  mov     r9, rbx
0x14002be71  inc     r9; cchCount2
0x14002be74  cmp     [r8+r9*2], r14w
0x14002be79  jnz     short loc_14002BE71
0x14002be7b  lea     rcx, [rsi+3F4h]; lpString1
0x14002be82  inc     rbx
0x14002be85  cmp     [rcx+rbx*2], r14w
0x14002be8a  jnz     short loc_14002BE82
0x14002be8c  cmp     rbx, r9
0x14002be8f  jnz     loc_14002BF47
0x14002be95  test    rbx, rbx
0x14002be98  jz      short loc_14002BEB5
0x14002be9a  mov     edx, ebx; cchCount1
0x14002be9c  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x14002bea0  call    cs:__imp_CompareStringOrdinal
0x14002bea7  nop     dword ptr [rax+rax+00h]
0x14002beac  cmp     eax, 2
0x14002beaf  jnz     loc_14002BF47
0x14002beb5  mov     ebx, 8
0x14002beba  lea     rdx, [rdi+204h]; Source2
0x14002bec1  mov     r8d, ebx; Length
0x14002bec4  lea     rcx, [rsi+204h]; Source1
0x14002becb  call    cs:__imp_RtlCompareMemory
0x14002bed2  nop     dword ptr [rax+rax+00h]
0x14002bed7  cmp     rax, rbx
0x14002beda  jnz     short loc_14002BF47
0x14002bedc  lea     rdx, [rdi+478h]; Source2
0x14002bee3  mov     r8d, ebx; Length
0x14002bee6  lea     rcx, [rsi+478h]; Source1
0x14002beed  call    cs:__imp_RtlCompareMemory
0x14002bef4  nop     dword ptr [rax+rax+00h]
0x14002bef9  cmp     rax, rbx
0x14002befc  jnz     short loc_14002BF47
0x14002befe  mov     ebx, 30h ; '0'
0x14002bf03  lea     rdx, [rdi+210h]; Source2
0x14002bf0a  mov     r8d, ebx; Length
0x14002bf0d  lea     rcx, [rsi+210h]; Source1
0x14002bf14  call    cs:__imp_RtlCompareMemory
0x14002bf1b  nop     dword ptr [rax+rax+00h]
0x14002bf20  cmp     rax, rbx
0x14002bf23  jnz     short loc_14002BF47
0x14002bf25  lea     rdx, [rdi+240h]; Source2
0x14002bf2c  mov     r8d, ebx; Length
0x14002bf2f  lea     rcx, [rsi+240h]; Source1
0x14002bf36  call    cs:__imp_RtlCompareMemory
0x14002bf3d  nop     dword ptr [rax+rax+00h]
0x14002bf42  cmp     rax, rbx
0x14002bf45  jz      short loc_14002BF4A
0x14002bf47  mov     ebp, r14d
0x14002bf4a  mov     eax, ebp
0x14002bf4c  jmp     short loc_14002BF55
0x14002bf4e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002bf53  xor     eax, eax
0x14002bf55  add     rsp, 30h
0x14002bf59  pop     r14
0x14002bf5b  pop     rdi
0x14002bf5c  pop     rsi
0x14002bf5d  pop     rbp
0x14002bf5e  pop     rbx
0x14002bf5f  retn
```
