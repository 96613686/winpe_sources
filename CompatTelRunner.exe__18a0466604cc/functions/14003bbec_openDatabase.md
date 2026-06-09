# openDatabase

- ea: `0x14003bbec`
- end: `0x14003c133`
- name: `openDatabase`
- size: `1351`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008ba90`
- `0x14008bab0`
- `0x14008bba0`

## callees

- `0x140020730`
- `0x140026634`
- `0x14003bbec`
- `0x14004911c`
- `0x14004bf5c`
- `0x14004efa0`
- `0x14005086c`
- `0x140056074`
- `0x140056170`
- `0x140061c70`
- `0x140062d60`
- `0x140063280`
- `0x1400636dc`
- `0x140065754`
- `0x14006cc68`
- `0x14006f2b8`
- `0x140070960`
- `0x14008a240`
- `0x14008ac90`
- `0x14008ad20`
- `0x14008b1cc`
- `0x14008bbb0`
- `0x140090240`
- `0x140092d90`
- `0x1400a8010`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, _QWORD *a2, int a3, const char *a4)
{
  __int64 v8; // r14
  __int64 v9; // rbp
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
  __int64 v27[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v28; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+18h] BYREF

  v28 = 0;
  v27[0] = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 )
    return sqlite3MisuseError(179589);
  *a2 = 0;
  result = sqlite3_initialize();
  if ( !(_DWORD)result )
  {
    if ( (_BYTE)word_1400C84B4 && (a3 & 0x8000) == 0 )
    {
      v11 = 1;
      if ( (a3 & 0x10000) == 0 )
        v11 = HIBYTE(word_1400C84B4);
    }
    else
    {
      v11 = 0;
    }
    if ( (a3 & 0x40000) != 0 )
    {
      a3 &= ~0x20000u;
    }
    else if ( dword_1400C85FC )
    {
      a3 |= 0x20000u;
    }
    v12 = a3 & 0xFFF600E7;
    v29 = v12;
    v13 = (_QWORD *)sqlite3MallocZero(0x310u);
    if ( v13 )
    {
      if ( !v11
        || ((_BYTE)word_1400C84B4 ? (v14 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(1)) : (v14 = 0),
            (v13[3] = v14) != 0) )
      {
        if ( v13[3] )
          ((void (*)(void))xmmword_1400C8530)();
        *((_WORD *)v13 + 210) = 0;
        *((_DWORD *)v13 + 10) = 2;
        *((_BYTE *)v13 + 113) = 109;
        *((_DWORD *)v13 + 104) = 1;
        v13[4] = v13 + 84;
        *((_DWORD *)v13 + 22) = (v12 & 0x2000000) != 0 ? -1 : 255;
        *(_OWORD *)(v13 + 17) = xmmword_1400B22C8;
        *(_OWORD *)(v13 + 19) = xmmword_1400B22D8;
        *((_BYTE *)v13 + 101) = 1;
        *((_BYTE *)v13 + 106) = -1;
        *(_OWORD *)(v13 + 21) = xmmword_1400B22E8;
        *((_DWORD *)v13 + 45) = 0;
        v13[8] = qword_1400C85D8;
        v13[26] = off_1400C8180;
        v13[6] |= 0xE00480E0uLL;
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
            v15 = sqlite3ParseUri(a4, a1, &v29, v13, &v28, v27);
            v12 = v29;
            v8 = v28;
            v9 = v27[0];
          }
          else
          {
            v15 = sqlite3MisuseError(179804);
          }
          v16 = v15;
          if ( v15 )
          {
            if ( v15 == 7 )
              sqlite3OomFault(v13);
            sqlite3ErrorWithMsg(v13, v16, (const char *)((unsigned __int64)"%s" & -(__int64)(v9 != 0)), v9);
            sqlite3_free(v9);
          }
          else
          {
            v17 = sqlite3BtreeOpen(*v13, v8, v13, v13[4] + 8LL, 0, v12 | 0x100);
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
                  btreeLockCarefully((__int64 *)v18);
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
LABEL_53:
                    setupLookaside(v13, 0, (unsigned int)dword_1400C84C4, (unsigned int)dword_1400C84C8);
                    sqlite3_wal_autocheckpoint(v13, 1000);
                    goto LABEL_54;
                  }
                  if ( i >= 2 )
                    break;
                  v24 = ((__int64 (__fastcall *)(_QWORD *))funcs_14003C080[i])(v13);
                }
                sqlite3AutoLoadExtensions((__int64)v13);
                if ( !(unsigned int)sqlite3_errcode(v13) )
                  goto LABEL_53;
              }
            }
          }
        }
LABEL_54:
        if ( v13[3] )
          ((void (*)(void))xmmword_1400C8540)();
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
    }
    *a2 = v13;
    sqlite3_free_filename(v8);
    return v26;
  }
  return result;
}

```

## disassembly

```asm
0x14003bbec  mov     rax, rsp
0x14003bbef  mov     [rax+8], rbx
0x14003bbf3  push    rbp
0x14003bbf4  push    rsi
0x14003bbf5  push    rdi
0x14003bbf6  push    r12
0x14003bbf8  push    r13
0x14003bbfa  push    r14
0x14003bbfc  push    r15
0x14003bbfe  sub     rsp, 40h
0x14003bc02  xor     edi, edi
0x14003bc04  mov     r12, r9
0x14003bc07  mov     [rax+10h], rdi
0x14003bc0b  mov     ebx, r8d
0x14003bc0e  mov     [rax-48h], rdi
0x14003bc12  mov     r15, rdx
0x14003bc15  mov     r13, rcx
0x14003bc18  mov     r14d, edi
0x14003bc1b  mov     ebp, edi
0x14003bc1d  test    rdx, rdx
0x14003bc20  jnz     short loc_14003BC31
0x14003bc22  mov     ecx, 2BD85h
0x14003bc27  call    sqlite3MisuseError
0x14003bc2c  jmp     loc_14003C11B
0x14003bc31  mov     [rdx], rdi
0x14003bc34  call    sqlite3_initialize
0x14003bc39  test    eax, eax
0x14003bc3b  jnz     loc_14003C11B
0x14003bc41  cmp     byte ptr cs:word_1400C84B4, dil
0x14003bc48  jz      short loc_14003BC50
0x14003bc4a  bt      ebx, 0Fh
0x14003bc4e  jnb     short loc_14003BC54
0x14003bc50  mov     esi, edi
0x14003bc52  jmp     short loc_14003BC66
0x14003bc54  mov     esi, 1
0x14003bc59  bt      ebx, 10h
0x14003bc5d  jb      short loc_14003BC66
0x14003bc5f  movzx   esi, byte ptr cs:word_1400C84B4+1
0x14003bc66  bt      ebx, 12h
0x14003bc6a  jnb     short loc_14003BC72
0x14003bc6c  btr     ebx, 11h
0x14003bc70  jmp     short loc_14003BC7E
0x14003bc72  cmp     cs:dword_1400C85FC, edi
0x14003bc78  jz      short loc_14003BC7E
0x14003bc7a  bts     ebx, 11h
0x14003bc7e  and     ebx, 0FFF600E7h
0x14003bc84  mov     ecx, 310h; Size
0x14003bc89  mov     [rsp+78h+arg_10], ebx
0x14003bc90  call    sqlite3MallocZero
0x14003bc95  mov     rdi, rax
0x14003bc98  test    rax, rax
0x14003bc9b  jz      loc_14003C0E7
0x14003bca1  test    esi, esi
0x14003bca3  jz      short loc_14003BCDE
0x14003bca5  xor     esi, esi
0x14003bca7  cmp     byte ptr cs:word_1400C84B4, sil
0x14003bcae  jnz     short loc_14003BCB4
0x14003bcb0  mov     eax, esi
0x14003bcb2  jmp     short loc_14003BCC5
0x14003bcb4  mov     rax, qword ptr cs:xmmword_1400C8520
0x14003bcbb  mov     ecx, 1
0x14003bcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bcc5  mov     [rdi+18h], rax
0x14003bcc9  test    rax, rax
0x14003bccc  jnz     short loc_14003BCE0
0x14003bcce  mov     rcx, rdi
0x14003bcd1  call    sqlite3_free
0x14003bcd6  mov     rdi, rsi
0x14003bcd9  jmp     loc_14003C0E9
0x14003bcde  xor     esi, esi
0x14003bce0  mov     rcx, [rdi+18h]
0x14003bce4  test    rcx, rcx
0x14003bce7  jz      short loc_14003BCF5
0x14003bce9  mov     rax, qword ptr cs:xmmword_1400C8530
0x14003bcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bcf5  mov     [rdi+1A4h], si
0x14003bcfc  mov     eax, ebx
0x14003bcfe  mov     dword ptr [rdi+28h], 2
0x14003bd05  and     eax, 2000000h
0x14003bd0a  mov     byte ptr [rdi+71h], 6Dh ; 'm'
0x14003bd0e  neg     eax
0x14003bd10  mov     dword ptr [rdi+1A0h], 1
0x14003bd1a  lea     rax, [rdi+2A0h]
0x14003bd21  mov     [rdi+20h], rax
0x14003bd25  sbb     ecx, ecx
0x14003bd27  and     ecx, 0FFFFFF00h
0x14003bd2d  mov     [rsp+78h+var_50], rsi
0x14003bd32  add     ecx, 0FFh
0x14003bd38  xor     r9d, r9d
0x14003bd3b  mov     [rdi+58h], ecx
0x14003bd3e  mov     r8b, 1
0x14003bd41  movups  xmm0, cs:xmmword_1400B22C8
0x14003bd48  mov     rcx, rdi
0x14003bd4b  movups  xmmword ptr [rdi+88h], xmm0
0x14003bd52  movups  xmm1, cs:xmmword_1400B22D8
0x14003bd59  movups  xmmword ptr [rdi+98h], xmm1
0x14003bd60  movups  xmm0, cs:xmmword_1400B22E8
0x14003bd67  mov     byte ptr [rdi+65h], 1
0x14003bd6b  mov     byte ptr [rdi+6Ah], 0FFh
0x14003bd6f  movups  xmmword ptr [rdi+0A8h], xmm0
0x14003bd76  mov     [rdi+0B4h], esi
0x14003bd7c  mov     rax, cs:qword_1400C85D8
0x14003bd83  mov     [rdi+40h], rax
0x14003bd87  lea     rax, off_1400C8180; "ANY"
0x14003bd8e  mov     [rdi+0D0h], rax
0x14003bd95  mov     eax, 0E00480E0h
0x14003bd9a  or      [rdi+30h], rax
0x14003bd9e  lea     rax, binCollFunc
0x14003bda5  mov     [rdi+74h], esi
0x14003bda8  mov     [rdi+278h], rsi
0x14003bdaf  mov     [rdi+280h], rsi
0x14003bdb6  mov     [rdi+230h], rsi
0x14003bdbd  mov     [rdi+238h], rsi
0x14003bdc4  lea     rsi, aBinary_0; "BINARY"
0x14003bdcb  mov     rdx, rsi
0x14003bdce  mov     [rsp+78h+var_58], rax
0x14003bdd3  mov     [rdi+270h], rbp
0x14003bdda  mov     [rdi+228h], rbp
0x14003bde1  call    createCollation
0x14003bde6  lea     rax, binCollFunc
0x14003bded  mov     [rsp+78h+var_50], rbp
0x14003bdf2  xor     r9d, r9d
0x14003bdf5  mov     [rsp+78h+var_58], rax
0x14003bdfa  mov     r8b, 3
0x14003bdfd  mov     rdx, rsi
0x14003be00  mov     rcx, rdi
0x14003be03  call    createCollation
0x14003be08  lea     rax, binCollFunc
0x14003be0f  mov     [rsp+78h+var_50], rbp
0x14003be14  xor     r9d, r9d
0x14003be17  mov     [rsp+78h+var_58], rax
0x14003be1c  mov     r8b, 2
0x14003be1f  mov     rdx, rsi
0x14003be22  mov     rcx, rdi
0x14003be25  call    createCollation
0x14003be2a  lea     rax, nocaseCollatingFunc
0x14003be31  xor     esi, esi
0x14003be33  mov     [rsp+78h+var_50], rsi
0x14003be38  lea     rdx, aNocase; "NOCASE"
0x14003be3f  xor     r9d, r9d
0x14003be42  mov     [rsp+78h+var_58], rax
0x14003be47  mov     r8b, 1
0x14003be4a  mov     rcx, rdi
0x14003be4d  call    createCollation
0x14003be52  lea     rax, rtrimCollFunc
0x14003be59  mov     [rsp+78h+var_50], rsi
0x14003be5e  xor     r9d, r9d
0x14003be61  mov     [rsp+78h+var_58], rax
0x14003be66  mov     r8b, 1
0x14003be69  lea     rdx, aRtrim_0; "RTRIM"
0x14003be70  mov     rcx, rdi
0x14003be73  call    createCollation
0x14003be78  cmp     [rdi+67h], sil
0x14003be7c  jnz     loc_14003C0BD
0x14003be82  mov     ecx, ebx
0x14003be84  mov     [rdi+4Ch], ebx
0x14003be87  and     ecx, 7
0x14003be8a  lea     eax, [rsi+1]
0x14003be8d  shl     eax, cl
0x14003be8f  test    al, 46h
0x14003be91  jnz     short loc_14003BE9F
0x14003be93  mov     ecx, 2BE5Ch
0x14003be98  call    sqlite3MisuseError
0x14003be9d  jmp     short loc_14003BEE0
0x14003be9f  lea     rax, [rsp+78h+var_48]
0x14003bea4  mov     r9, rdi
0x14003bea7  mov     [rsp+78h+var_50], rax
0x14003beac  lea     r8, [rsp+78h+arg_10]
0x14003beb4  lea     rax, [rsp+78h+arg_8]
0x14003bebc  mov     rdx, r13
0x14003bebf  mov     rcx, r12
0x14003bec2  mov     [rsp+78h+var_58], rax
0x14003bec7  call    sqlite3ParseUri
0x14003becc  mov     ebx, [rsp+78h+arg_10]
0x14003bed3  mov     r14, [rsp+78h+arg_8]
0x14003bedb  mov     rbp, [rsp+78h+var_48]
0x14003bee0  mov     esi, eax
0x14003bee2  test    eax, eax
0x14003bee4  jz      short loc_14003BF22
0x14003bee6  cmp     eax, 7
0x14003bee9  jnz     short loc_14003BEF3
0x14003beeb  mov     rcx, rdi
0x14003beee  call    sqlite3OomFault
0x14003bef3  mov     rax, rbp
0x14003bef6  mov     r9, rbp
0x14003bef9  neg     rax
0x14003befc  mov     edx, esi
0x14003befe  lea     rax, aS_6; "%s"
0x14003bf05  mov     rcx, rdi
0x14003bf08  sbb     r8, r8
0x14003bf0b  and     r8, rax
0x14003bf0e  call    sqlite3ErrorWithMsg
0x14003bf13  mov     rcx, rbp
0x14003bf16  call    sqlite3_free
0x14003bf1b  xor     esi, esi
0x14003bf1d  jmp     loc_14003C0BD
0x14003bf22  mov     r9, [rdi+20h]
0x14003bf26  bts     ebx, 8
0x14003bf2a  mov     rcx, [rdi]
0x14003bf2d  xor     esi, esi
0x14003bf2f  add     r9, 8
0x14003bf33  mov     dword ptr [rsp+78h+var_50], ebx
0x14003bf37  mov     r8, rdi
0x14003bf3a  mov     dword ptr [rsp+78h+var_58], esi
0x14003bf3e  mov     rdx, r14
0x14003bf41  call    sqlite3BtreeOpen
0x14003bf46  test    eax, eax
0x14003bf48  jz      short loc_14003BF67
0x14003bf4a  cmp     eax, 0C0Ah
0x14003bf4f  lea     ecx, [rsi+7]
0x14003bf52  cmovz   eax, ecx
0x14003bf55  mov     rcx, rdi
0x14003bf58  mov     edx, eax
0x14003bf5a  mov     [rdi+50h], eax
0x14003bf5d  call    sqlite3ErrorFinish
0x14003bf62  jmp     loc_14003C0BD
0x14003bf67  mov     rax, [rdi+20h]
0x14003bf6b  mov     rcx, [rax+8]
0x14003bf6f  cmp     [rcx+11h], sil
0x14003bf73  jz      short loc_14003BF83
0x14003bf75  inc     dword ptr [rcx+14h]
0x14003bf78  cmp     [rcx+12h], sil
0x14003bf7c  jnz     short loc_14003BF83
0x14003bf7e  call    btreeLockCarefully
0x14003bf83  mov     rbx, [rdi+20h]
0x14003bf87  mov     rcx, rdi
0x14003bf8a  mov     rdx, rbx
0x14003bf8d  mov     rdx, [rbx+8]
0x14003bf91  call    sqlite3SchemaGet
0x14003bf96  mov     [rbx+18h], rax
0x14003bf9a  cmp     [rdi+67h], sil
0x14003bf9e  jnz     short loc_14003BFB3
0x14003bfa0  mov     rax, [rdi+20h]
0x14003bfa4  mov     rcx, rdi
0x14003bfa7  mov     rdx, [rax+18h]
0x14003bfab  mov     dl, [rdx+71h]
0x14003bfae  call    sqlite3SetTextEncoding
0x14003bfb3  mov     rax, [rdi+20h]
0x14003bfb7  mov     rcx, [rax+8]
0x14003bfbb  cmp     [rcx+11h], sil
0x14003bfbf  jz      short loc_14003BFCC
0x14003bfc1  sub     dword ptr [rcx+14h], 1
0x14003bfc5  jnz     short loc_14003BFCC
0x14003bfc7  call    unlockBtreeMutex
0x14003bfcc  mov     rbx, [rdi+20h]
0x14003bfd0  xor     edx, edx
0x14003bfd2  mov     rcx, rdi
0x14003bfd5  call    sqlite3SchemaGet
0x14003bfda  mov     [rbx+38h], rax
0x14003bfde  lea     rcx, aMain; "main"
0x14003bfe5  mov     rax, [rdi+20h]
0x14003bfe9  mov     [rax], rcx
0x14003bfec  lea     rcx, aTemp_0; "temp"
0x14003bff3  mov     rax, [rdi+20h]
0x14003bff7  mov     byte ptr [rax+10h], 3
0x14003bffb  mov     rax, [rdi+20h]
0x14003bfff  mov     [rax+20h], rcx
0x14003c003  mov     rax, [rdi+20h]
0x14003c007  mov     byte ptr [rax+30h], 1
0x14003c00b  mov     byte ptr [rdi+71h], 76h ; 'v'
0x14003c00f  cmp     [rdi+67h], sil
0x14003c013  jnz     loc_14003C0BD
0x14003c019  mov     [rdi+50h], esi
0x14003c01c  cmp     [rdi+190h], rsi
0x14003c023  jz      short loc_14003C031
0x14003c025  xor     edx, edx
0x14003c027  mov     rcx, rdi
0x14003c02a  call    sqlite3ErrorFinish
0x14003c02f  jmp     short loc_14003C038
0x14003c031  mov     dword ptr [rdi+54h], 0FFFFFFFFh
0x14003c038  mov     r8d, 2
0x14003c03e  lea     rdx, aMatch; "MATCH"
0x14003c045  mov     rcx, rdi
0x14003c048  call    sqlite3_overload_function
0x14003c04d  mov     ecx, 7
0x14003c052  cmp     eax, ecx
0x14003c054  jnz     short loc_14003C05E
0x14003c056  mov     rcx, rdi
0x14003c059  call    sqlite3OomFault
0x14003c05e  mov     rcx, rdi
0x14003c061  call    sqlite3_errcode
0x14003c066  mov     ebx, esi
0x14003c068  jmp     short loc_14003C087
0x14003c06a  mov     rcx, rdi
0x14003c06d  cmp     ebx, 2
0x14003c070  jge     short loc_14003C0D4
0x14003c072  lea     rdx, funcs_14003C080
0x14003c079  movsxd  rax, ebx
0x14003c07c  mov     rax, ds:(funcs_14003C080 - 1400A9260h)[rdx+rax*8]
0x14003c080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c085  inc     ebx
0x14003c087  test    eax, eax
0x14003c089  jz      short loc_14003C06A
0x14003c08b  mov     edx, eax
0x14003c08d  mov     [rdi+50h], eax
0x14003c090  mov     rcx, rdi
0x14003c093  call    sqlite3ErrorFinish
0x14003c098  mov     r9d, cs:dword_1400C84C8
0x14003c09f  xor     edx, edx
0x14003c0a1  mov     r8d, cs:dword_1400C84C4
  ... truncated ...
```
