# openDatabase

- ea: `0x18003182c`
- end: `0x180031d47`
- name: `openDatabase`
- size: `1307`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031820`
- `0x18009cf80`
- `0x18009cfa0`

## callees

- `0x18001ff1c`
- `0x180020928`
- `0x180024640`
- `0x18002619c`
- `0x180030330`
- `0x180030570`
- `0x18003182c`
- `0x180031d50`
- `0x180031e90`
- `0x180031f40`
- `0x180034650`
- `0x180035d1c`
- `0x1800375e4`
- `0x180037b34`
- `0x180038d00`
- `0x18003f8d0`
- `0x18003fb44`
- `0x180041eb0`
- `0x18004789c`
- `0x18004b758`
- `0x18005d478`
- `0x18005e810`
- `0x18005fde0`
- `0x18006024c`
- `0x180069d50`
- `0x18006dc30`
- `0x18006ef68`
- `0x1800911e8`
- `0x180091750`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, _QWORD *a2, int a3, const char *a4)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  __int64 result; // rax
  int v10; // esi
  unsigned int v11; // ebx
  __int64 v12; // rax
  _QWORD *v13; // rdi
  __int64 *v14; // r15
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // esi
  unsigned int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // ebx
  __int64 v25[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+90h] [rbp+18h] BYREF

  v27 = 0;
  v25[0] = 0;
  v7 = 0;
  v8 = 0;
  if ( !a2 )
    return sqlite3ReportError(21, 183498, "misuse");
  *a2 = 0;
  result = sqlite3_initialize();
  if ( !(_DWORD)result )
  {
    if ( (_BYTE)word_1800D0874 && (a3 & 0x8000) == 0 )
    {
      v10 = 1;
      if ( (a3 & 0x10000) == 0 )
        v10 = HIBYTE(word_1800D0874);
    }
    else
    {
      v10 = 0;
    }
    if ( (a3 & 0x40000) != 0 )
    {
      a3 &= ~0x20000u;
    }
    else if ( dword_1800D09BC )
    {
      a3 |= 0x20000u;
    }
    v11 = a3 & 0xFFF600E7;
    v28 = v11;
    v12 = sqlite3MallocZero(0x318u);
    v13 = (_QWORD *)v12;
    if ( v12 )
    {
      v14 = (__int64 *)(v12 + 24);
      if ( !v10 || (v15 = sqlite3MutexAlloc(1), (*v14 = v15) != 0) )
      {
        sqlite3_mutex_enter(*v14);
        *((_WORD *)v13 + 210) = 0;
        *((_DWORD *)v13 + 10) = 2;
        *((_BYTE *)v13 + 113) = 109;
        *((_DWORD *)v13 + 104) = 1;
        v13[4] = v13 + 84;
        *((_DWORD *)v13 + 22) = (v11 & 0x2000000) != 0 ? -1 : 255;
        *(_OWORD *)(v13 + 17) = xmmword_1800B55B0;
        *(_OWORD *)(v13 + 19) = xmmword_1800B55C0;
        *((_BYTE *)v13 + 101) = 1;
        *((_BYTE *)v13 + 106) = -1;
        *(_OWORD *)(v13 + 21) = xmmword_1800B55D0;
        *((_DWORD *)v13 + 45) = 0;
        v13[8] = qword_1800D0998;
        v13[26] = off_1800D06E0;
        v13[6] |= 0xE00480E0uLL;
        *((_DWORD *)v13 + 29) = 0;
        v13[79] = 0;
        v13[80] = 0;
        v13[78] = 0;
        v13[70] = 0;
        v13[71] = 0;
        v13[69] = 0;
        createCollation((__int64)v13, (__int64)"BINARY", 1u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"BINARY", 3u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"BINARY", 2u, 0, (__int64)&binCollFunc, 0);
        createCollation((__int64)v13, (__int64)"NOCASE", 1u, 0, (__int64)nocaseCollatingFunc, 0);
        createCollation((__int64)v13, (__int64)"RTRIM", 1u, 0, (__int64)rtrimCollFunc, 0);
        if ( *((_BYTE *)v13 + 103) )
          goto LABEL_40;
        *((_DWORD *)v13 + 19) = v11;
        if ( ((1 << (v11 & 7)) & 0x46) != 0 )
        {
          v16 = sqlite3ParseUri(a4, a1, &v28, v13, &v27, v25);
          v11 = v28;
          v7 = v27;
          v8 = v25[0];
        }
        else
        {
          v16 = sqlite3ReportError(21, 183713, "misuse");
        }
        v17 = v16;
        if ( v16 )
        {
          if ( v16 == 7 )
            sqlite3OomFault(v13);
          sqlite3ErrorWithMsg(v13, v17, (const char *)((unsigned __int64)"%s" & -(__int64)(v8 != 0)), v8);
          sqlite3_free(v8);
        }
        else
        {
          v18 = sqlite3BtreeOpen(*v13, v7, v13, v13[4] + 8LL, 0, v11 | 0x100);
          if ( v18 )
          {
            if ( v18 == 3082 )
              v18 = 7;
            sqlite3Error(v13, v18);
          }
          else
          {
            sqlite3BtreeEnter(*(_QWORD *)(v13[4] + 8LL));
            v19 = v13[4];
            *(_QWORD *)(v19 + 24) = sqlite3SchemaGet(v13, *(_QWORD *)(v19 + 8));
            if ( !*((_BYTE *)v13 + 103) )
            {
              v20 = *(_QWORD *)(v13[4] + 24LL);
              LOBYTE(v20) = *(_BYTE *)(v20 + 113);
              sqlite3SetTextEncoding(v13, v20);
            }
            sqlite3BtreeLeave(*(_QWORD *)(v13[4] + 8LL));
            v21 = v13[4];
            *(_QWORD *)(v21 + 56) = sqlite3SchemaGet(v13, 0);
            *(_QWORD *)v13[4] = "main";
            *(_BYTE *)(v13[4] + 16LL) = 3;
            *(_QWORD *)(v13[4] + 32LL) = "temp";
            *(_BYTE *)(v13[4] + 48LL) = 1;
            *((_BYTE *)v13 + 113) = 118;
            if ( !*((_BYTE *)v13 + 103) )
            {
              sqlite3Error(v13, 0);
              if ( (unsigned int)sqlite3_overload_function(v13, "MATCH", 2) == 7 )
                sqlite3OomFault(v13);
              v22 = sqlite3_errcode(v13);
              v23 = 0;
              while ( !v22 )
              {
                if ( v23 >= 3 )
                {
                  sqlite3AutoLoadExtensions((__int64)v13);
                  if ( (unsigned int)sqlite3_errcode(v13) )
                    goto LABEL_40;
LABEL_39:
                  setupLookaside(v13, 0, (unsigned int)dword_1800D0884, (unsigned int)dword_1800D0888);
                  sqlite3_wal_autocheckpoint(v13, 1000);
                  goto LABEL_40;
                }
                v22 = ((__int64 (__fastcall *)(_QWORD *))funcs_180031C8E[v23++])(v13);
              }
              sqlite3Error(v13, v22);
              goto LABEL_39;
            }
          }
        }
LABEL_40:
        sqlite3_mutex_leave(*v14);
      }
      else
      {
        sqlite3_free(v13);
        v13 = 0;
      }
    }
    v24 = sqlite3_errcode(v13);
    if ( (_BYTE)v24 == 7 )
    {
      sqlite3Close(v13, 0);
      v13 = 0;
    }
    else if ( v24 )
    {
      *((_BYTE *)v13 + 113) = -70;
      *a2 = v13;
LABEL_47:
      sqlite3_free_filename(v7);
      return v24;
    }
    *a2 = v13;
    if ( !v24 )
      sqlite3CodecQueryParameters(v13, 0, v7);
    goto LABEL_47;
  }
  return result;
}

```

## disassembly

```asm
0x18003182c  mov     rax, rsp
0x18003182f  mov     [rax+20h], rbx
0x180031833  mov     [rax+8], rcx
0x180031837  push    rbp
0x180031838  push    rsi
0x180031839  push    rdi
0x18003183a  push    r12
0x18003183c  push    r13
0x18003183e  push    r14
0x180031840  push    r15
0x180031842  sub     rsp, 40h
0x180031846  xor     r15d, r15d
0x180031849  mov     r13, r9
0x18003184c  mov     [rax+10h], r15
0x180031850  mov     ebx, r8d
0x180031853  mov     [rax-48h], r15
0x180031857  mov     r12, rdx
0x18003185a  mov     r14d, r15d
0x18003185d  mov     ebp, r15d
0x180031860  test    rdx, rdx
0x180031863  jnz     short loc_180031880
0x180031865  lea     r8, aMisuse; "misuse"
0x18003186c  mov     edx, 2CCCAh
0x180031871  lea     ecx, [r12+15h]
0x180031876  call    sqlite3ReportError
0x18003187b  jmp     loc_180031D21
0x180031880  mov     [rdx], r15
0x180031883  call    sqlite3_initialize
0x180031888  test    eax, eax
0x18003188a  jnz     loc_180031D21
0x180031890  cmp     byte ptr cs:word_1800D0874, r15b
0x180031897  jz      short loc_18003189F
0x180031899  bt      ebx, 0Fh
0x18003189d  jnb     short loc_1800318A4
0x18003189f  mov     esi, r15d
0x1800318a2  jmp     short loc_1800318B6
0x1800318a4  mov     esi, 1
0x1800318a9  bt      ebx, 10h
0x1800318ad  jb      short loc_1800318B6
0x1800318af  movzx   esi, byte ptr cs:word_1800D0874+1
0x1800318b6  bt      ebx, 12h
0x1800318ba  jnb     short loc_1800318C2
0x1800318bc  btr     ebx, 11h
0x1800318c0  jmp     short loc_1800318CF
0x1800318c2  cmp     cs:dword_1800D09BC, r15d
0x1800318c9  jz      short loc_1800318CF
0x1800318cb  bts     ebx, 11h
0x1800318cf  and     ebx, 0FFF600E7h
0x1800318d5  mov     ecx, 318h; Size
0x1800318da  mov     [rsp+78h+arg_10], ebx
0x1800318e1  call    sqlite3MallocZero
0x1800318e6  mov     rdi, rax
0x1800318e9  test    rax, rax
0x1800318ec  jz      loc_180031CE5
0x1800318f2  lea     r15, [rax+18h]
0x1800318f6  test    esi, esi
0x1800318f8  jz      short loc_18003191D
0x1800318fa  mov     ecx, 1
0x1800318ff  call    sqlite3MutexAlloc
0x180031904  xor     esi, esi
0x180031906  mov     [r15], rax
0x180031909  test    rax, rax
0x18003190c  jnz     short loc_18003191F
0x18003190e  mov     rcx, rdi
0x180031911  call    sqlite3_free
0x180031916  mov     edi, esi
0x180031918  jmp     loc_180031CE7
0x18003191d  xor     esi, esi
0x18003191f  mov     rcx, [r15]
0x180031922  call    sqlite3_mutex_enter
0x180031927  mov     [rdi+1A4h], si
0x18003192e  mov     eax, ebx
0x180031930  mov     dword ptr [rdi+28h], 2
0x180031937  and     eax, 2000000h
0x18003193c  mov     byte ptr [rdi+71h], 6Dh ; 'm'
0x180031940  neg     eax
0x180031942  mov     dword ptr [rdi+1A0h], 1
0x18003194c  lea     rax, [rdi+2A0h]
0x180031953  mov     [rdi+20h], rax
0x180031957  sbb     ecx, ecx
0x180031959  and     ecx, 0FFFFFF00h
0x18003195f  mov     [rsp+78h+var_50], rsi
0x180031964  add     ecx, 0FFh
0x18003196a  xor     r9d, r9d
0x18003196d  mov     [rdi+58h], ecx
0x180031970  mov     r8b, 1
0x180031973  movups  xmm0, cs:xmmword_1800B55B0
0x18003197a  mov     rcx, rdi
0x18003197d  movups  xmmword ptr [rdi+88h], xmm0
0x180031984  movups  xmm1, cs:xmmword_1800B55C0
0x18003198b  movups  xmmword ptr [rdi+98h], xmm1
0x180031992  movups  xmm0, cs:xmmword_1800B55D0
0x180031999  mov     byte ptr [rdi+65h], 1
0x18003199d  mov     byte ptr [rdi+6Ah], 0FFh
0x1800319a1  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800319a8  mov     [rdi+0B4h], esi
0x1800319ae  mov     rax, cs:qword_1800D0998
0x1800319b5  mov     [rdi+40h], rax
0x1800319b9  lea     rax, off_1800D06E0; "ANY"
0x1800319c0  mov     [rdi+0D0h], rax
0x1800319c7  mov     eax, 0E00480E0h
0x1800319cc  or      [rdi+30h], rax
0x1800319d0  lea     rax, binCollFunc
0x1800319d7  mov     [rdi+74h], esi
0x1800319da  mov     [rdi+278h], rsi
0x1800319e1  mov     [rdi+280h], rsi
0x1800319e8  mov     [rdi+270h], rbp
0x1800319ef  mov     [rdi+230h], rsi
0x1800319f6  mov     [rdi+238h], rsi
0x1800319fd  lea     rsi, aBinary_0; "BINARY"
0x180031a04  mov     rdx, rsi
0x180031a07  mov     [rdi+228h], rbp
0x180031a0e  mov     [rsp+78h+var_58], rax
0x180031a13  call    createCollation
0x180031a18  lea     rax, binCollFunc
0x180031a1f  mov     [rsp+78h+var_50], rbp
0x180031a24  xor     r9d, r9d
0x180031a27  mov     [rsp+78h+var_58], rax
0x180031a2c  mov     r8b, 3
0x180031a2f  mov     rdx, rsi
0x180031a32  mov     rcx, rdi
0x180031a35  call    createCollation
0x180031a3a  lea     rax, binCollFunc
0x180031a41  mov     [rsp+78h+var_50], rbp
0x180031a46  xor     r9d, r9d
0x180031a49  mov     [rsp+78h+var_58], rax
0x180031a4e  mov     r8b, 2
0x180031a51  mov     rdx, rsi
0x180031a54  mov     rcx, rdi
0x180031a57  call    createCollation
0x180031a5c  lea     rax, nocaseCollatingFunc
0x180031a63  xor     esi, esi
0x180031a65  mov     [rsp+78h+var_50], rsi
0x180031a6a  lea     rdx, aNocase; "NOCASE"
0x180031a71  xor     r9d, r9d
0x180031a74  mov     [rsp+78h+var_58], rax
0x180031a79  mov     r8b, 1
0x180031a7c  mov     rcx, rdi
0x180031a7f  call    createCollation
0x180031a84  lea     rax, rtrimCollFunc
0x180031a8b  mov     [rsp+78h+var_50], rsi
0x180031a90  xor     r9d, r9d
0x180031a93  mov     [rsp+78h+var_58], rax
0x180031a98  mov     r8b, 1
0x180031a9b  lea     rdx, aRtrim_0; "RTRIM"
0x180031aa2  mov     rcx, rdi
0x180031aa5  call    createCollation
0x180031aaa  cmp     [rdi+67h], sil
0x180031aae  jnz     loc_180031CC8
0x180031ab4  mov     ecx, ebx
0x180031ab6  mov     [rdi+4Ch], ebx
0x180031ab9  and     ecx, 7
0x180031abc  lea     eax, [rsi+1]
0x180031abf  shl     eax, cl
0x180031ac1  test    al, 46h
0x180031ac3  jnz     short loc_180031ADB
0x180031ac5  lea     r8, aMisuse; "misuse"
0x180031acc  mov     edx, 2CDA1h
0x180031ad1  lea     ecx, [rsi+15h]
0x180031ad4  call    sqlite3ReportError
0x180031ad9  jmp     short loc_180031B21
0x180031adb  mov     rdx, [rsp+78h+arg_0]
0x180031ae3  lea     rax, [rsp+78h+var_48]
0x180031ae8  mov     [rsp+78h+var_50], rax
0x180031aed  lea     r8, [rsp+78h+arg_10]
0x180031af5  lea     rax, [rsp+78h+arg_8]
0x180031afd  mov     r9, rdi
0x180031b00  mov     rcx, r13
0x180031b03  mov     [rsp+78h+var_58], rax
0x180031b08  call    sqlite3ParseUri
0x180031b0d  mov     ebx, [rsp+78h+arg_10]
0x180031b14  mov     r14, [rsp+78h+arg_8]
0x180031b1c  mov     rbp, [rsp+78h+var_48]
0x180031b21  mov     esi, eax
0x180031b23  test    eax, eax
0x180031b25  jz      short loc_180031B63
0x180031b27  cmp     eax, 7
0x180031b2a  jnz     short loc_180031B34
0x180031b2c  mov     rcx, rdi
0x180031b2f  call    sqlite3OomFault
0x180031b34  mov     rax, rbp
0x180031b37  mov     r9, rbp
0x180031b3a  neg     rax
0x180031b3d  mov     edx, esi
0x180031b3f  lea     rax, aS_7; "%s"
0x180031b46  mov     rcx, rdi
0x180031b49  sbb     r8, r8
0x180031b4c  and     r8, rax
0x180031b4f  call    sqlite3ErrorWithMsg
0x180031b54  mov     rcx, rbp
0x180031b57  call    sqlite3_free
0x180031b5c  xor     esi, esi
0x180031b5e  jmp     loc_180031CC8
0x180031b63  mov     r9, [rdi+20h]
0x180031b67  bts     ebx, 8
0x180031b6b  mov     rcx, [rdi]
0x180031b6e  xor     esi, esi
0x180031b70  add     r9, 8
0x180031b74  mov     dword ptr [rsp+78h+var_50], ebx
0x180031b78  mov     r8, rdi
0x180031b7b  mov     dword ptr [rsp+78h+var_58], esi
0x180031b7f  mov     rdx, r14
0x180031b82  call    sqlite3BtreeOpen
0x180031b87  test    eax, eax
0x180031b89  jz      short loc_180031BA5
0x180031b8b  cmp     eax, 0C0Ah
0x180031b90  lea     ecx, [rsi+7]
0x180031b93  cmovz   eax, ecx
0x180031b96  mov     rcx, rdi
0x180031b99  mov     edx, eax
0x180031b9b  call    sqlite3Error
0x180031ba0  jmp     loc_180031CC8
0x180031ba5  mov     rcx, [rdi+20h]
0x180031ba9  mov     rcx, [rcx+8]
0x180031bad  call    sqlite3BtreeEnter
0x180031bb2  mov     rbx, [rdi+20h]
0x180031bb6  mov     rcx, rdi
0x180031bb9  mov     rdx, rbx
0x180031bbc  mov     rdx, [rbx+8]
0x180031bc0  call    sqlite3SchemaGet
0x180031bc5  mov     [rbx+18h], rax
0x180031bc9  cmp     [rdi+67h], sil
0x180031bcd  jnz     short loc_180031BE2
0x180031bcf  mov     rax, [rdi+20h]
0x180031bd3  mov     rcx, rdi
0x180031bd6  mov     rdx, [rax+18h]
0x180031bda  mov     dl, [rdx+71h]
0x180031bdd  call    sqlite3SetTextEncoding
0x180031be2  mov     rcx, [rdi+20h]
0x180031be6  mov     rcx, [rcx+8]
0x180031bea  call    sqlite3BtreeLeave
0x180031bef  mov     rbx, [rdi+20h]
0x180031bf3  xor     edx, edx
0x180031bf5  mov     rcx, rdi
0x180031bf8  call    sqlite3SchemaGet
0x180031bfd  mov     [rbx+38h], rax
0x180031c01  lea     rcx, aMain; "main"
0x180031c08  mov     rax, [rdi+20h]
0x180031c0c  mov     [rax], rcx
0x180031c0f  lea     rcx, aTemp; "temp"
0x180031c16  mov     rax, [rdi+20h]
0x180031c1a  mov     byte ptr [rax+10h], 3
0x180031c1e  mov     rax, [rdi+20h]
0x180031c22  mov     [rax+20h], rcx
0x180031c26  mov     rax, [rdi+20h]
0x180031c2a  mov     byte ptr [rax+30h], 1
0x180031c2e  mov     byte ptr [rdi+71h], 76h ; 'v'
0x180031c32  cmp     [rdi+67h], sil
0x180031c36  jnz     loc_180031CC8
0x180031c3c  xor     edx, edx
0x180031c3e  mov     rcx, rdi
0x180031c41  call    sqlite3Error
0x180031c46  mov     r8d, 2
0x180031c4c  lea     rdx, aMatch; "MATCH"
0x180031c53  mov     rcx, rdi
0x180031c56  call    sqlite3_overload_function
0x180031c5b  mov     ecx, 7
0x180031c60  cmp     eax, ecx
0x180031c62  jnz     short loc_180031C6C
0x180031c64  mov     rcx, rdi
0x180031c67  call    sqlite3OomFault
0x180031c6c  mov     rcx, rdi
0x180031c6f  call    sqlite3_errcode
0x180031c74  mov     ebx, esi
0x180031c76  jmp     short loc_180031C95
0x180031c78  mov     rcx, rdi
0x180031c7b  cmp     ebx, 3
0x180031c7e  jge     short loc_180031CD2
0x180031c80  lea     rdx, funcs_180031C8E
0x180031c87  movsxd  rax, ebx
0x180031c8a  mov     rax, ds:(funcs_180031C8E - 1800B1B70h)[rdx+rax*8]
0x180031c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c93  inc     ebx
0x180031c95  test    eax, eax
0x180031c97  jz      short loc_180031C78
0x180031c99  mov     edx, eax
0x180031c9b  mov     rcx, rdi
0x180031c9e  call    sqlite3Error
0x180031ca3  mov     r9d, cs:dword_1800D0888
0x180031caa  xor     edx, edx
0x180031cac  mov     r8d, cs:dword_1800D0884
0x180031cb3  mov     rcx, rdi
0x180031cb6  call    setupLookaside
0x180031cbb  mov     edx, 3E8h
0x180031cc0  mov     rcx, rdi
0x180031cc3  call    sqlite3_wal_autocheckpoint
0x180031cc8  mov     rcx, [r15]
0x180031ccb  call    sqlite3_mutex_leave
0x180031cd0  jmp     short loc_180031CE7
0x180031cd2  call    sqlite3AutoLoadExtensions
0x180031cd7  mov     rcx, rdi
0x180031cda  call    sqlite3_errcode
0x180031cdf  test    eax, eax
0x180031ce1  jz      short loc_180031CA3
0x180031ce3  jmp     short loc_180031CC8
0x180031ce5  xor     esi, esi
0x180031ce7  mov     rcx, rdi
0x180031cea  call    sqlite3_errcode
0x180031cef  mov     ebx, eax
0x180031cf1  cmp     al, 7
  ... truncated ...
```
