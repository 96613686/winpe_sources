# DavFindOrCreateExtErrorEntry

- ea: `0x180010c48`
- end: `0x180010ff6`
- name: `DavFindOrCreateExtErrorEntry`
- size: `942`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, wint_t *, int, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800146fc`
- `0x180024000`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000bc5c`
- `0x18000fb24`
- `0x180010c48`
- `0x180014820`
- `0x180014e60`

## import_xrefs

- `msvcrt!time` at `0x180010e23`
- `msvcrt!time` at `0x180010f8e`
- `msvcrt!time` at `0x180010e23`
- `msvcrt!time` at `0x180010f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010edd`
- `KERNEL32!LocalFree` at `0x180010e0a`
- `KERNEL32!LocalFree` at `0x180010fcf`
- `KERNEL32!LocalFree` at `0x180010e0a`
- `KERNEL32!LocalFree` at `0x180010fcf`
- `KERNEL32!LocalAlloc` at `0x180010ecf`
- `KERNEL32!LocalAlloc` at `0x180010ecf`

## pseudocode

```c
__int64 __fastcall DavFindOrCreateExtErrorEntry(_DWORD *a1, __int64 a2, __int64 a3, wint_t *a4, int a5, __int64 *a6)
{
  unsigned int v6; // r13d
  unsigned int v8; // esi
  unsigned int v9; // r14d
  _QWORD *v11; // r10
  DWORD LastError; // ebx
  DWORD ExtErrorInfo; // eax
  unsigned int v14; // r9d
  _DWORD *v15; // rdi
  __int64 *v16; // r14
  __int64 v17; // rsi
  __int64 v18; // rax
  unsigned int v20; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21[8]; // [rsp+48h] [rbp-40h] BYREF

  v6 = 0;
  v20 = 0;
  v8 = a3;
  v21[0] = 0;
  v9 = a2;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_llqq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a1[1], *a1, a2, a3);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a6 || a5 && !a4 )
    return 87;
  LastError = 0;
  if ( a4 )
  {
    ExtErrorInfo = DavVerifyAndGetExtErrorInfo(a4, &v20, v21);
    LastError = ExtErrorInfo;
    if ( ExtErrorInfo )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          ExtErrorInfo);
      return LastError;
    }
    v6 = v20;
    v11 = WPP_GLOBAL_Control;
  }
  v14 = a1[1];
  v15 = 0;
  v16 = &ExtErrorHashTable[2
                         * (((unsigned __int16)*a1
                           + (unsigned __int16)v8
                           + (unsigned __int16)(v8 >> 8)
                           + (unsigned __int16)(v14 >> 8)
                           + (unsigned __int16)v14
                           + (unsigned __int16)(v9 >> 8)
                           + (unsigned __int16)(*a1 >> 8)
                           + (unsigned __int16)v9)
                          & 0x1FF)];
  v17 = *v16;
  if ( (__int64 *)*v16 != v16 )
  {
    while ( *(_DWORD *)(v17 + 20) != v14
         || *(_DWORD *)(v17 + 16) != *a1
         || *(_QWORD *)(v17 + 24) != a2
         || *(_QWORD *)(v17 + 32) != a3 )
    {
      v17 = *(_QWORD *)v17;
      if ( (__int64 *)v17 == v16 )
        goto LABEL_19;
    }
    if ( a4 )
    {
      LocalFree(*(HLOCAL *)(v17 + 48));
      *(_QWORD *)(v17 + 56) = v21[0];
      *(_QWORD *)(v17 + 48) = a4;
      *(_DWORD *)(v17 + 64) = v6;
      *(_QWORD *)(v17 + 40) = time(0) + 60;
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_q(v11[2], 156, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v17);
    *a6 = v17;
    goto LABEL_45;
  }
LABEL_19:
  if ( !a5 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_(v11[2], 157, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
    goto LABEL_44;
  }
  if ( ExtErrorHashEntries != 1024 || (DavCleanupExtErrorEntries(0), ExtErrorHashEntries != 1024) )
  {
    v15 = LocalAlloc(0x40u, 0x48u);
    if ( !v15 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v15);
    v15[5] = a1[1];
    v15[4] = *a1;
    *((_QWORD *)v15 + 3) = a2;
    *((_QWORD *)v15 + 4) = a3;
    *((_QWORD *)v15 + 7) = v21[0];
    *((_QWORD *)v15 + 6) = a4;
    v15[16] = v6;
    *((_QWORD *)v15 + 5) = time(0) + 60;
    v18 = *v16;
    if ( *(__int64 **)(*v16 + 8) != v16 )
      __fastfail(3u);
    ++ExtErrorHashEntries;
    *(_QWORD *)v15 = v18;
    *((_QWORD *)v15 + 1) = v16;
    *(_QWORD *)(v18 + 8) = v15;
    *v16 = (__int64)v15;
LABEL_44:
    *a6 = (__int64)v15;
LABEL_45:
    if ( LastError && v15 )
      LocalFree(v15);
    return LastError;
  }
  LastError = 1359;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x180010c48  mov     rax, rsp
0x180010c4b  mov     [rax+8], rbx
0x180010c4f  mov     [rax+18h], r8
0x180010c53  mov     [rax+10h], rdx
0x180010c57  push    rbp
0x180010c58  push    rsi
0x180010c59  push    rdi
0x180010c5a  push    r12
0x180010c5c  push    r13
0x180010c5e  push    r14
0x180010c60  push    r15
0x180010c62  sub     rsp, 50h
0x180010c66  xor     r13d, r13d
0x180010c69  mov     rbp, r9
0x180010c6c  mov     [rax-48h], r13d
0x180010c70  mov     rsi, r8
0x180010c73  mov     [rax-40h], r13
0x180010c77  mov     r14, rdx
0x180010c7a  mov     r12, rcx
0x180010c7d  mov     r10, cs:WPP_GLOBAL_Control
0x180010c84  lea     rdi, WPP_GLOBAL_Control
0x180010c8b  cmp     r10, rdi
0x180010c8e  jz      short loc_180010CB9
0x180010c90  test    byte ptr [r10+1Ch], 2
0x180010c95  jz      short loc_180010CB9
0x180010c97  mov     r9d, [rcx+4]
0x180010c9b  mov     [rax-58h], r8
0x180010c9f  mov     [rax-60h], rdx
0x180010ca3  mov     eax, [rcx]
0x180010ca5  mov     rcx, [r10+10h]
0x180010ca9  mov     [rsp+88h+var_68], eax
0x180010cad  call    WPP_SF_llqq
0x180010cb2  mov     r10, cs:WPP_GLOBAL_Control
0x180010cb9  mov     r15, [rsp+88h+arg_28]
0x180010cc1  test    r15, r15
0x180010cc4  jz      loc_180010FD7
0x180010cca  cmp     [rsp+88h+arg_20], r13d
0x180010cd2  jz      short loc_180010CDD
0x180010cd4  test    rbp, rbp
0x180010cd7  jz      loc_180010FD7
0x180010cdd  xor     ebx, ebx
0x180010cdf  test    rbp, rbp
0x180010ce2  jz      short loc_180010D3F
0x180010ce4  lea     r8, [rsp+88h+var_40]
0x180010ce9  mov     rcx, rbp
0x180010cec  lea     rdx, [rsp+88h+var_48]
0x180010cf1  call    DavVerifyAndGetExtErrorInfo
0x180010cf6  mov     ebx, eax
0x180010cf8  test    eax, eax
0x180010cfa  jz      short loc_180010D33
0x180010cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d03  cmp     rcx, rdi
0x180010d06  jz      loc_180010FDC
0x180010d0c  test    byte ptr [rcx+1Ch], 1
0x180010d10  jz      loc_180010FDC
0x180010d16  mov     rcx, [rcx+10h]
0x180010d1a  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010d21  mov     edx, 9Ah
0x180010d26  mov     r9d, eax
0x180010d29  call    WPP_SF_d
0x180010d2e  jmp     loc_180010FDC
0x180010d33  mov     r13d, [rsp+88h+var_48]
0x180010d38  mov     r10, cs:WPP_GLOBAL_Control
0x180010d3f  mov     r9d, [r12+4]
0x180010d44  mov     eax, esi
0x180010d46  mov     r8d, [r12]
0x180010d4a  mov     edx, r9d
0x180010d4d  shr     eax, 8
0x180010d50  mov     ecx, r8d
0x180010d53  shr     ecx, 8
0x180010d56  xor     edi, edi
0x180010d58  shr     edx, 8
0x180010d5b  add     edx, eax
0x180010d5d  mov     eax, r14d
0x180010d60  shr     eax, 8
0x180010d63  add     eax, r9d
0x180010d66  add     eax, edx
0x180010d68  add     ecx, eax
0x180010d6a  add     ecx, esi
0x180010d6c  add     r14d, ecx
0x180010d6f  lea     rcx, ExtErrorHashTable
0x180010d76  add     r14d, r8d
0x180010d79  and     r14d, 1FFh
0x180010d80  shl     r14, 4
0x180010d84  add     r14, rcx
0x180010d87  mov     rsi, [r14]
0x180010d8a  cmp     rsi, r14
0x180010d8d  jz      short loc_180010DBF
0x180010d8f  mov     rax, [rsp+88h+arg_10]
0x180010d97  mov     rcx, [rsp+88h+arg_8]
0x180010d9f  cmp     [rsi+14h], r9d
0x180010da3  jnz     short loc_180010DB7
0x180010da5  cmp     [rsi+10h], r8d
0x180010da9  jnz     short loc_180010DB7
0x180010dab  cmp     [rsi+18h], rcx
0x180010daf  jnz     short loc_180010DB7
0x180010db1  cmp     [rsi+20h], rax
0x180010db5  jz      short loc_180010E01
0x180010db7  mov     rsi, [rsi]
0x180010dba  cmp     rsi, r14
0x180010dbd  jnz     short loc_180010D9F
0x180010dbf  cmp     [rsp+88h+arg_20], edi
0x180010dc6  jnz     loc_180010E6B
0x180010dcc  lea     rax, WPP_GLOBAL_Control
0x180010dd3  cmp     r10, rax
0x180010dd6  jz      loc_180010FC0
0x180010ddc  test    byte ptr [r10+1Ch], 1
0x180010de1  jz      loc_180010FC0
0x180010de7  mov     rcx, [r10+10h]
0x180010deb  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010df2  mov     edx, 9Dh
0x180010df7  call    WPP_SF_
0x180010dfc  jmp     loc_180010FC0
0x180010e01  test    rbp, rbp
0x180010e04  jz      short loc_180010E38
0x180010e06  mov     rcx, [rsi+30h]; hMem
0x180010e0a  call    cs:__imp_LocalFree
0x180010e10  mov     rax, [rsp+88h+var_40]
0x180010e15  xor     ecx, ecx; Time
0x180010e17  mov     [rsi+38h], rax
0x180010e1b  mov     [rsi+30h], rbp
0x180010e1f  mov     [rsi+40h], r13d
0x180010e23  call    cs:__imp_time
0x180010e29  add     rax, 3Ch ; '<'
0x180010e2d  mov     [rsi+28h], rax
0x180010e31  mov     r10, cs:WPP_GLOBAL_Control
0x180010e38  lea     rax, WPP_GLOBAL_Control
0x180010e3f  cmp     r10, rax
0x180010e42  jz      short loc_180010E63
0x180010e44  test    byte ptr [r10+1Ch], 2
0x180010e49  jz      short loc_180010E63
0x180010e4b  mov     rcx, [r10+10h]
0x180010e4f  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010e56  mov     edx, 9Ch
0x180010e5b  mov     r9, rsi
0x180010e5e  call    WPP_SF_q
0x180010e63  mov     [r15], rsi
0x180010e66  jmp     loc_180010FC3
0x180010e6b  mov     edi, 400h
0x180010e70  cmp     cs:ExtErrorHashEntries, edi
0x180010e76  jnz     short loc_180010EC7
0x180010e78  xor     ecx, ecx
0x180010e7a  call    DavCleanupExtErrorEntries
0x180010e7f  cmp     cs:ExtErrorHashEntries, edi
0x180010e85  jnz     short loc_180010EC7
0x180010e87  mov     ebx, 54Fh
0x180010e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e93  lea     rax, WPP_GLOBAL_Control
0x180010e9a  cmp     rcx, rax
0x180010e9d  jz      loc_180010FDC
0x180010ea3  test    byte ptr [rcx+1Ch], 2
0x180010ea7  jz      loc_180010FDC
0x180010ead  mov     rcx, [rcx+10h]
0x180010eb1  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010eb8  mov     edx, 9Eh
0x180010ebd  call    WPP_SF_
0x180010ec2  jmp     loc_180010FDC
0x180010ec7  mov     edx, 48h ; 'H'; uBytes
0x180010ecc  lea     ecx, [rdx-8]; uFlags
0x180010ecf  call    cs:__imp_LocalAlloc
0x180010ed5  mov     rdi, rax
0x180010ed8  test    rax, rax
0x180010edb  jnz     short loc_180010F23
0x180010edd  call    cs:__imp_GetLastError
0x180010ee3  mov     ebx, eax
0x180010ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010eec  lea     rax, WPP_GLOBAL_Control
0x180010ef3  cmp     rcx, rax
0x180010ef6  jz      loc_180010FC3
0x180010efc  test    byte ptr [rcx+1Ch], 1
0x180010f00  jz      loc_180010FC3
0x180010f06  mov     rcx, [rcx+10h]
0x180010f0a  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010f11  mov     edx, 9Fh
0x180010f16  mov     r9d, ebx
0x180010f19  call    WPP_SF_d
0x180010f1e  jmp     loc_180010FC3
0x180010f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f2a  lea     rax, WPP_GLOBAL_Control
0x180010f31  cmp     rcx, rax
0x180010f34  jz      short loc_180010F54
0x180010f36  test    byte ptr [rcx+1Ch], 2
0x180010f3a  jz      short loc_180010F54
0x180010f3c  mov     rcx, [rcx+10h]
0x180010f40  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010f47  mov     edx, 0A0h
0x180010f4c  mov     r9, rdi
0x180010f4f  call    WPP_SF_q
0x180010f54  mov     eax, [r12+4]
0x180010f59  xor     ecx, ecx; Time
0x180010f5b  mov     [rdi+14h], eax
0x180010f5e  mov     eax, [r12]
0x180010f62  mov     [rdi+10h], eax
0x180010f65  mov     rax, [rsp+88h+arg_8]
0x180010f6d  mov     [rdi+18h], rax
0x180010f71  mov     rax, [rsp+88h+arg_10]
0x180010f79  mov     [rdi+20h], rax
0x180010f7d  mov     rax, [rsp+88h+var_40]
0x180010f82  mov     [rdi+38h], rax
0x180010f86  mov     [rdi+30h], rbp
0x180010f8a  mov     [rdi+40h], r13d
0x180010f8e  call    cs:__imp_time
0x180010f94  add     rax, 3Ch ; '<'
0x180010f98  mov     [rdi+28h], rax
0x180010f9c  mov     rax, [r14]
0x180010f9f  cmp     [rax+8], r14
0x180010fa3  jz      short loc_180010FAC
0x180010fa5  mov     ecx, 3
0x180010faa  int     29h; Win8: RtlFailFast(ecx)
0x180010fac  inc     cs:ExtErrorHashEntries
0x180010fb2  mov     [rdi], rax
0x180010fb5  mov     [rdi+8], r14
0x180010fb9  mov     [rax+8], rdi
0x180010fbd  mov     [r14], rdi
0x180010fc0  mov     [r15], rdi
0x180010fc3  test    ebx, ebx
0x180010fc5  jz      short loc_180010FDC
0x180010fc7  test    rdi, rdi
0x180010fca  jz      short loc_180010FDC
0x180010fcc  mov     rcx, rdi; hMem
0x180010fcf  call    cs:__imp_LocalFree
0x180010fd5  jmp     short loc_180010FDC
0x180010fd7  mov     ebx, 57h ; 'W'
0x180010fdc  mov     eax, ebx
0x180010fde  mov     rbx, [rsp+88h+arg_0]
0x180010fe6  add     rsp, 50h
0x180010fea  pop     r15
0x180010fec  pop     r14
0x180010fee  pop     r13
0x180010ff0  pop     r12
0x180010ff2  pop     rdi
0x180010ff3  pop     rsi
0x180010ff4  pop     rbp
0x180010ff5  retn
```
