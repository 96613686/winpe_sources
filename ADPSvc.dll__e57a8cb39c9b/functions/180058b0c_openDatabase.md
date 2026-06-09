# openDatabase

- ea: `0x180058b0c`
- end: `0x18005905b`
- name: `openDatabase`
- size: `1359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180033350`
- `0x1800aa6e0`
- `0x1800aa700`
- `0x1800aa7e0`

## callees

- `0x18003ae40`
- `0x180040f54`
- `0x180058b0c`
- `0x180066690`
- `0x180069550`
- `0x18006c5c8`
- `0x18006de94`
- `0x18006eebc`
- `0x180073a9c`
- `0x180073b98`
- `0x18007fbd0`
- `0x180080cc8`
- `0x180081230`
- `0x180081a3c`
- `0x180083b60`
- `0x18008b698`
- `0x18008dd18`
- `0x18008f420`
- `0x1800a8e90`
- `0x1800a98a0`
- `0x1800a9930`
- `0x1800a9e4c`
- `0x1800aa7f0`
- `0x1800af180`
- `0x1800b2174`
- `0x1800ca010`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, _QWORD *a2, int a3, const char *a4)
{
  __int64 v5; // r14
  __int64 v6; // rbp
  __int64 result; // rax
  int v11; // esi
  unsigned int v12; // ebx
  _QWORD *v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v23; // rbx
  unsigned int v24; // eax
  int i; // ebx
  unsigned int v26; // ebx
  __int64 v27; // [rsp+20h] [rbp-58h]
  __int64 v28[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v29; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  v29 = 0;
  v6 = 0;
  v28[0] = 0;
  *a2 = 0;
  result = sqlite3_initialize();
  if ( !(_DWORD)result )
  {
    if ( (_BYTE)word_18010EE54 && (a3 & 0x8000) == 0 )
    {
      v11 = 1;
      if ( (a3 & 0x10000) == 0 )
        v11 = HIBYTE(word_18010EE54);
    }
    else
    {
      v11 = 0;
    }
    if ( (a3 & 0x40000) != 0 )
    {
      a3 &= ~0x20000u;
    }
    else if ( dword_18010EF9C )
    {
      a3 |= 0x20000u;
    }
    v12 = a3 & 0xFFF600E7;
    v30 = v12;
    v13 = (_QWORD *)sqlite3MallocZero(0x318u);
    if ( v13 )
    {
      if ( !v11
        || ((_BYTE)word_18010EE54 ? (v14 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(1)) : (v14 = 0),
            (v13[3] = v14) != 0) )
      {
        if ( v13[3] )
          ((void (*)(void))xmmword_18010EED0)();
        *((_WORD *)v13 + 210) = 0;
        *((_DWORD *)v13 + 10) = 2;
        *((_BYTE *)v13 + 113) = 109;
        *((_DWORD *)v13 + 104) = 1;
        v13[4] = v13 + 84;
        *((_DWORD *)v13 + 22) = (v12 & 0x2000000) != 0 ? -1 : 255;
        *(_OWORD *)(v13 + 17) = xmmword_1800FB4D0;
        *(_OWORD *)(v13 + 19) = xmmword_1800FB4E0;
        *((_BYTE *)v13 + 101) = 1;
        *((_BYTE *)v13 + 106) = -1;
        *(_OWORD *)(v13 + 21) = xmmword_1800FB4F0;
        *((_DWORD *)v13 + 45) = 0;
        v13[8] = qword_18010EF78;
        v13[26] = off_18010E5A0;
        v13[6] |= 0xE004C0E0uLL;
        *((_DWORD *)v13 + 29) = 0;
        v13[79] = 0;
        v13[80] = 0;
        v13[70] = 0;
        v13[71] = 0;
        v13[78] = 0;
        v13[69] = 0;
        createCollation((__int64)v13, (__int64)"BINARY", 1u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"BINARY", 3u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"BINARY", 2u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"NOCASE", 1u, 0, (__int64)nocaseCollatingFunc, 0);
        createCollation((__int64)v13, (__int64)"RTRIM", 1u, 0, (__int64)rtrimCollFunc, 0);
        if ( !*((_BYTE *)v13 + 103) )
        {
          *((_DWORD *)v13 + 19) = v12;
          if ( ((1 << (v12 & 7)) & 0x46) != 0 )
          {
            v15 = sqlite3ParseUri(a4, a1, &v30, v13, &v29, v28);
            v12 = v30;
            v5 = v29;
            v6 = v28[0];
          }
          else
          {
            v15 = sqlite3MisuseError(183714);
          }
          v16 = v15;
          if ( v15 )
          {
            if ( v15 == 7 )
              sqlite3OomFault(v13);
            sqlite3ErrorWithMsg(v13, v16, (const char *)((unsigned __int64)"%s" & -(__int64)(v6 != 0)), v6);
            sqlite3_free(v6);
          }
          else
          {
            LODWORD(v27) = 0;
            v17 = sqlite3BtreeOpen(*v13, v5, v13, v13[4] + 8LL, v27, v12 | 0x100);
            if ( v17 )
            {
              if ( v17 == 3082 )
                v17 = 7;
              *((_DWORD *)v13 + 20) = v17;
              sqlite3ErrorFinish(v13, v17);
            }
            else
            {
              v18 = *(_QWORD *)(v13[4] + 8LL);
              if ( *(_BYTE *)(v18 + 17) )
              {
                ++*(_DWORD *)(v18 + 20);
                if ( !*(_BYTE *)(v18 + 18) )
                  btreeLockCarefully(v18);
              }
              v19 = v13[4];
              *(_QWORD *)(v19 + 24) = sqlite3SchemaGet(v13, *(_QWORD *)(v19 + 8));
              if ( !*((_BYTE *)v13 + 103) )
              {
                v20 = *(_QWORD *)(v13[4] + 24LL);
                LOBYTE(v20) = *(_BYTE *)(v20 + 113);
                sqlite3SetTextEncoding(v13, v20);
              }
              v21 = *(_QWORD *)(v13[4] + 8LL);
              if ( *(_BYTE *)(v21 + 17) )
              {
                if ( (*(_DWORD *)(v21 + 20))-- == 1 )
                  unlockBtreeMutex(v21);
              }
              v23 = v13[4];
              *(_QWORD *)(v23 + 56) = sqlite3SchemaGet(v13, 0);
              *(_QWORD *)v13[4] = "main";
              *(_BYTE *)(v13[4] + 16LL) = 3;
              *(_QWORD *)(v13[4] + 32LL) = "temp";
              *(_BYTE *)(v13[4] + 48LL) = 1;
              *((_BYTE *)v13 + 113) = 118;
              if ( !*((_BYTE *)v13 + 103) )
              {
                *((_DWORD *)v13 + 20) = 0;
                if ( v13[50] )
                  sqlite3ErrorFinish(v13, 0);
                else
                  *((_DWORD *)v13 + 21) = -1;
                if ( (unsigned int)sqlite3_overload_function(v13, "MATCH", 2) == 7 )
                  sqlite3OomFault(v13);
                v24 = sqlite3_errcode(v13);
                for ( i = 0; ; ++i )
                {
                  if ( v24 )
                  {
                    *((_DWORD *)v13 + 20) = v24;
                    sqlite3ErrorFinish(v13, v24);
LABEL_51:
                    setupLookaside(v13, 0, (unsigned int)dword_18010EE64, (unsigned int)dword_18010EE68);
                    sqlite3_wal_hook(v13, sqlite3WalDefaultHook, 1000);
                    goto LABEL_52;
                  }
                  if ( i >= 2 )
                    break;
                  v24 = ((__int64 (__fastcall *)(_QWORD *))funcs_180058F8C[i])(v13);
                }
                sqlite3AutoLoadExtensions((__int64)v13);
                if ( !(unsigned int)sqlite3_errcode(v13) )
                  goto LABEL_51;
              }
            }
          }
        }
LABEL_52:
        if ( v13[3] )
          ((void (*)(void))xmmword_18010EEE0)();
      }
      else
      {
        sqlite3_free(v13);
        v13 = 0;
      }
    }
    v26 = sqlite3_errcode(v13);
    if ( (_BYTE)v26 == 7 )
    {
      sqlite3Close(v13, 0);
      v13 = 0;
    }
    else if ( v26 )
    {
      *((_BYTE *)v13 + 113) = -70;
      *a2 = v13;
LABEL_60:
      sqlite3_free_filename(v5);
      return v26;
    }
    *a2 = v13;
    if ( !v26 )
      sqlite3CodecQueryParameters(v13, 0, v5);
    goto LABEL_60;
  }
  return result;
}

```

## disassembly

```asm
0x180058b0c  mov     rax, rsp
0x180058b0f  mov     [rax+8], rbx
0x180058b13  push    rbp
0x180058b14  push    rsi
0x180058b15  push    rdi
0x180058b16  push    r12
0x180058b18  push    r13
0x180058b1a  push    r14
0x180058b1c  push    r15
0x180058b1e  sub     rsp, 40h
0x180058b22  xor     edi, edi
0x180058b24  mov     r12, r9
0x180058b27  mov     r14d, edi
0x180058b2a  mov     [rax+10h], rdi
0x180058b2e  mov     ebp, edi
0x180058b30  mov     [rax-48h], rdi
0x180058b34  mov     [rdx], rdi
0x180058b37  mov     ebx, r8d
0x180058b3a  mov     r15, rdx
0x180058b3d  mov     r13, rcx
0x180058b40  call    sqlite3_initialize
0x180058b45  test    eax, eax
0x180058b47  jnz     loc_180059036
0x180058b4d  cmp     byte ptr cs:word_18010EE54, dil
0x180058b54  jz      short loc_180058B5C
0x180058b56  bt      ebx, 0Fh
0x180058b5a  jnb     short loc_180058B60
0x180058b5c  mov     esi, edi
0x180058b5e  jmp     short loc_180058B72
0x180058b60  mov     esi, 1
0x180058b65  bt      ebx, 10h
0x180058b69  jb      short loc_180058B72
0x180058b6b  movzx   esi, byte ptr cs:word_18010EE54+1
0x180058b72  bt      ebx, 12h
0x180058b76  jnb     short loc_180058B7E
0x180058b78  btr     ebx, 11h
0x180058b7c  jmp     short loc_180058B8A
0x180058b7e  cmp     cs:dword_18010EF9C, edi
0x180058b84  jz      short loc_180058B8A
0x180058b86  bts     ebx, 11h
0x180058b8a  and     ebx, 0FFF600E7h
0x180058b90  mov     ecx, 318h; Size
0x180058b95  mov     [rsp+78h+arg_10], ebx
0x180058b9c  call    sqlite3MallocZero
0x180058ba1  mov     rdi, rax
0x180058ba4  test    rax, rax
0x180058ba7  jz      loc_180058FFB
0x180058bad  test    esi, esi
0x180058baf  jz      short loc_180058BEA
0x180058bb1  xor     esi, esi
0x180058bb3  cmp     byte ptr cs:word_18010EE54, sil
0x180058bba  jnz     short loc_180058BC0
0x180058bbc  mov     eax, esi
0x180058bbe  jmp     short loc_180058BD1
0x180058bc0  mov     rax, qword ptr cs:xmmword_18010EEC0
0x180058bc7  mov     ecx, 1
0x180058bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bd1  mov     [rdi+18h], rax
0x180058bd5  test    rax, rax
0x180058bd8  jnz     short loc_180058BEC
0x180058bda  mov     rcx, rdi
0x180058bdd  call    sqlite3_free
0x180058be2  mov     rdi, rsi
0x180058be5  jmp     loc_180058FFD
0x180058bea  xor     esi, esi
0x180058bec  mov     rcx, [rdi+18h]
0x180058bf0  test    rcx, rcx
0x180058bf3  jz      short loc_180058C01
0x180058bf5  mov     rax, qword ptr cs:xmmword_18010EED0
0x180058bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c01  mov     [rdi+1A4h], si
0x180058c08  mov     eax, ebx
0x180058c0a  mov     dword ptr [rdi+28h], 2
0x180058c11  and     eax, 2000000h
0x180058c16  mov     byte ptr [rdi+71h], 6Dh ; 'm'
0x180058c1a  neg     eax
0x180058c1c  mov     dword ptr [rdi+1A0h], 1
0x180058c26  lea     rax, [rdi+2A0h]
0x180058c2d  mov     [rdi+20h], rax
0x180058c31  sbb     ecx, ecx
0x180058c33  and     ecx, 0FFFFFF00h
0x180058c39  mov     [rsp+78h+var_50], rsi
0x180058c3e  add     ecx, 0FFh
0x180058c44  xor     r9d, r9d
0x180058c47  mov     [rdi+58h], ecx
0x180058c4a  mov     r8b, 1
0x180058c4d  movups  xmm0, cs:xmmword_1800FB4D0
0x180058c54  mov     rcx, rdi
0x180058c57  movups  xmmword ptr [rdi+88h], xmm0
0x180058c5e  movups  xmm1, cs:xmmword_1800FB4E0
0x180058c65  movups  xmmword ptr [rdi+98h], xmm1
0x180058c6c  movups  xmm0, cs:xmmword_1800FB4F0
0x180058c73  mov     byte ptr [rdi+65h], 1
0x180058c77  mov     byte ptr [rdi+6Ah], 0FFh
0x180058c7b  movups  xmmword ptr [rdi+0A8h], xmm0
0x180058c82  mov     [rdi+0B4h], esi
0x180058c88  mov     rax, cs:qword_18010EF78
0x180058c8f  mov     [rdi+40h], rax
0x180058c93  lea     rax, off_18010E5A0; "ANY"
0x180058c9a  mov     [rdi+0D0h], rax
0x180058ca1  mov     eax, 0E004C0E0h
0x180058ca6  or      [rdi+30h], rax
0x180058caa  lea     rax, binCollFunc
0x180058cb1  mov     [rdi+74h], esi
0x180058cb4  mov     [rdi+278h], rsi
0x180058cbb  mov     [rdi+280h], rsi
0x180058cc2  mov     [rdi+230h], rsi
0x180058cc9  mov     [rdi+238h], rsi
0x180058cd0  lea     rsi, aBinary_0; "BINARY"
0x180058cd7  mov     rdx, rsi
0x180058cda  mov     [rsp+78h+var_58], rax
0x180058cdf  mov     [rdi+270h], rbp
0x180058ce6  mov     [rdi+228h], rbp
0x180058ced  call    createCollation
0x180058cf2  lea     rax, binCollFunc
0x180058cf9  mov     [rsp+78h+var_50], rbp
0x180058cfe  xor     r9d, r9d
0x180058d01  mov     [rsp+78h+var_58], rax
0x180058d06  mov     r8b, 3
0x180058d09  mov     rdx, rsi
0x180058d0c  mov     rcx, rdi
0x180058d0f  call    createCollation
0x180058d14  lea     rax, binCollFunc
0x180058d1b  mov     [rsp+78h+var_50], rbp
0x180058d20  xor     r9d, r9d
0x180058d23  mov     [rsp+78h+var_58], rax
0x180058d28  mov     r8b, 2
0x180058d2b  mov     rdx, rsi
0x180058d2e  mov     rcx, rdi
0x180058d31  call    createCollation
0x180058d36  lea     rax, nocaseCollatingFunc
0x180058d3d  xor     esi, esi
0x180058d3f  mov     [rsp+78h+var_50], rsi
0x180058d44  lea     rdx, aNocase; "NOCASE"
0x180058d4b  xor     r9d, r9d
0x180058d4e  mov     [rsp+78h+var_58], rax
0x180058d53  mov     r8b, 1
0x180058d56  mov     rcx, rdi
0x180058d59  call    createCollation
0x180058d5e  lea     rax, rtrimCollFunc
0x180058d65  mov     [rsp+78h+var_50], rsi
0x180058d6a  xor     r9d, r9d
0x180058d6d  mov     [rsp+78h+var_58], rax
0x180058d72  mov     r8b, 1
0x180058d75  lea     rdx, aRtrim_0; "RTRIM"
0x180058d7c  mov     rcx, rdi
0x180058d7f  call    createCollation
0x180058d84  cmp     [rdi+67h], sil
0x180058d88  jnz     loc_180058FD1
0x180058d8e  mov     ecx, ebx
0x180058d90  mov     [rdi+4Ch], ebx
0x180058d93  and     ecx, 7
0x180058d96  lea     eax, [rsi+1]
0x180058d99  shl     eax, cl
0x180058d9b  test    al, 46h
0x180058d9d  jnz     short loc_180058DAB
0x180058d9f  mov     ecx, 2CDA2h
0x180058da4  call    sqlite3MisuseError
0x180058da9  jmp     short loc_180058DEC
0x180058dab  lea     rax, [rsp+78h+var_48]
0x180058db0  mov     r9, rdi
0x180058db3  mov     [rsp+78h+var_50], rax
0x180058db8  lea     r8, [rsp+78h+arg_10]
0x180058dc0  lea     rax, [rsp+78h+arg_8]
0x180058dc8  mov     rdx, r13
0x180058dcb  mov     rcx, r12
0x180058dce  mov     [rsp+78h+var_58], rax
0x180058dd3  call    sqlite3ParseUri
0x180058dd8  mov     ebx, [rsp+78h+arg_10]
0x180058ddf  mov     r14, [rsp+78h+arg_8]
0x180058de7  mov     rbp, [rsp+78h+var_48]
0x180058dec  mov     esi, eax
0x180058dee  test    eax, eax
0x180058df0  jz      short loc_180058E2E
0x180058df2  cmp     eax, 7
0x180058df5  jnz     short loc_180058DFF
0x180058df7  mov     rcx, rdi
0x180058dfa  call    sqlite3OomFault
0x180058dff  mov     rax, rbp
0x180058e02  mov     r9, rbp
0x180058e05  neg     rax
0x180058e08  mov     edx, esi
0x180058e0a  lea     rax, aS_7; "%s"
0x180058e11  mov     rcx, rdi
0x180058e14  sbb     r8, r8
0x180058e17  and     r8, rax
0x180058e1a  call    sqlite3ErrorWithMsg
0x180058e1f  mov     rcx, rbp
0x180058e22  call    sqlite3_free
0x180058e27  xor     esi, esi
0x180058e29  jmp     loc_180058FD1
0x180058e2e  mov     r9, [rdi+20h]
0x180058e32  bts     ebx, 8
0x180058e36  mov     rcx, [rdi]
0x180058e39  xor     esi, esi
0x180058e3b  add     r9, 8
0x180058e3f  mov     dword ptr [rsp+78h+var_50], ebx
0x180058e43  mov     r8, rdi
0x180058e46  mov     dword ptr [rsp+78h+var_58], esi
0x180058e4a  mov     rdx, r14
0x180058e4d  call    sqlite3BtreeOpen
0x180058e52  test    eax, eax
0x180058e54  jz      short loc_180058E73
0x180058e56  cmp     eax, 0C0Ah
0x180058e5b  lea     ecx, [rsi+7]
0x180058e5e  cmovz   eax, ecx
0x180058e61  mov     rcx, rdi
0x180058e64  mov     edx, eax
0x180058e66  mov     [rdi+50h], eax
0x180058e69  call    sqlite3ErrorFinish
0x180058e6e  jmp     loc_180058FD1
0x180058e73  mov     rax, [rdi+20h]
0x180058e77  mov     rcx, [rax+8]
0x180058e7b  cmp     [rcx+11h], sil
0x180058e7f  jz      short loc_180058E8F
0x180058e81  inc     dword ptr [rcx+14h]
0x180058e84  cmp     [rcx+12h], sil
0x180058e88  jnz     short loc_180058E8F
0x180058e8a  call    btreeLockCarefully
0x180058e8f  mov     rbx, [rdi+20h]
0x180058e93  mov     rcx, rdi
0x180058e96  mov     rdx, rbx
0x180058e99  mov     rdx, [rbx+8]
0x180058e9d  call    sqlite3SchemaGet
0x180058ea2  mov     [rbx+18h], rax
0x180058ea6  cmp     [rdi+67h], sil
0x180058eaa  jnz     short loc_180058EBF
0x180058eac  mov     rax, [rdi+20h]
0x180058eb0  mov     rcx, rdi
0x180058eb3  mov     rdx, [rax+18h]
0x180058eb7  mov     dl, [rdx+71h]
0x180058eba  call    sqlite3SetTextEncoding
0x180058ebf  mov     rax, [rdi+20h]
0x180058ec3  mov     rcx, [rax+8]
0x180058ec7  cmp     [rcx+11h], sil
0x180058ecb  jz      short loc_180058ED8
0x180058ecd  sub     dword ptr [rcx+14h], 1
0x180058ed1  jnz     short loc_180058ED8
0x180058ed3  call    unlockBtreeMutex
0x180058ed8  mov     rbx, [rdi+20h]
0x180058edc  xor     edx, edx
0x180058ede  mov     rcx, rdi
0x180058ee1  call    sqlite3SchemaGet
0x180058ee6  mov     [rbx+38h], rax
0x180058eea  lea     rcx, aMain; "main"
0x180058ef1  mov     rax, [rdi+20h]
0x180058ef5  mov     [rax], rcx
0x180058ef8  lea     rcx, aTemp; "temp"
0x180058eff  mov     rax, [rdi+20h]
0x180058f03  mov     byte ptr [rax+10h], 3
0x180058f07  mov     rax, [rdi+20h]
0x180058f0b  mov     [rax+20h], rcx
0x180058f0f  mov     rax, [rdi+20h]
0x180058f13  mov     byte ptr [rax+30h], 1
0x180058f17  mov     byte ptr [rdi+71h], 76h ; 'v'
0x180058f1b  cmp     [rdi+67h], sil
0x180058f1f  jnz     loc_180058FD1
0x180058f25  mov     [rdi+50h], esi
0x180058f28  cmp     [rdi+190h], rsi
0x180058f2f  jz      short loc_180058F3D
0x180058f31  xor     edx, edx
0x180058f33  mov     rcx, rdi
0x180058f36  call    sqlite3ErrorFinish
0x180058f3b  jmp     short loc_180058F44
0x180058f3d  mov     dword ptr [rdi+54h], 0FFFFFFFFh
0x180058f44  mov     r8d, 2
0x180058f4a  lea     rdx, aMatch; "MATCH"
0x180058f51  mov     rcx, rdi
0x180058f54  call    sqlite3_overload_function
0x180058f59  mov     ecx, 7
0x180058f5e  cmp     eax, ecx
0x180058f60  jnz     short loc_180058F6A
0x180058f62  mov     rcx, rdi
0x180058f65  call    sqlite3OomFault
0x180058f6a  mov     rcx, rdi
0x180058f6d  call    sqlite3_errcode
0x180058f72  mov     ebx, esi
0x180058f74  jmp     short loc_180058F93
0x180058f76  mov     rcx, rdi
0x180058f79  cmp     ebx, 2
0x180058f7c  jge     short loc_180058FE8
0x180058f7e  lea     rdx, funcs_180058F8C
0x180058f85  movsxd  rax, ebx
0x180058f88  mov     rax, ds:(funcs_180058F8C - 1800CB850h)[rdx+rax*8]
0x180058f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f91  inc     ebx
0x180058f93  test    eax, eax
0x180058f95  jz      short loc_180058F76
0x180058f97  mov     edx, eax
0x180058f99  mov     [rdi+50h], eax
0x180058f9c  mov     rcx, rdi
0x180058f9f  call    sqlite3ErrorFinish
0x180058fa4  mov     r9d, cs:dword_18010EE68
0x180058fab  xor     edx, edx
0x180058fad  mov     r8d, cs:dword_18010EE64
0x180058fb4  mov     rcx, rdi
0x180058fb7  call    setupLookaside
0x180058fbc  mov     r8d, 3E8h
0x180058fc2  lea     rdx, sqlite3WalDefaultHook
0x180058fc9  mov     rcx, rdi
  ... truncated ...
```
