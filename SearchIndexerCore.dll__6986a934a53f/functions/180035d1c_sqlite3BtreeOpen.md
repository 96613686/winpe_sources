# sqlite3BtreeOpen

- ea: `0x180035d1c`
- end: `0x180036379`
- name: `sqlite3BtreeOpen`
- size: `1629`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, loader_planting`

## callers

- `0x1800286a4`
- `0x18003182c`
- `0x180076710`
- `0x18007a180`

## callees

- `0x18001eb90`
- `0x180024640`
- `0x1800330b8`
- `0x18003352c`
- `0x180033ff4`
- `0x18003405c`
- `0x180035d1c`
- `0x1800375e4`
- `0x180037620`
- `0x180038d00`
- `0x18003c510`
- `0x18003f8d0`
- `0x18003fb44`
- `0x180041eb0`
- `0x180046ca4`
- `0x18004b758`
- `0x18006ae48`
- `0x1800789c0`
- `0x1800af5e4`
- `0x1800af620`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeOpen(__int64 a1, char *a2, __int64 a3, __int64 *a4, int a5, unsigned int a6)
{
  unsigned int v6; // ebx
  __int64 v7; // r14
  __int64 v9; // rbp
  int v10; // edi
  int v11; // r13d
  int v12; // r12d
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 *v15; // rax
  __int64 v16; // r9
  __int64 *i; // rdi
  unsigned int Fileheader; // ebp
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  _QWORD *v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r9
  _DWORD *v24; // rbx
  int v25; // ecx
  unsigned __int8 v26; // cl
  int v27; // r14d
  __int64 *v28; // rbx
  _BYTE *v29; // r12
  int v30; // eax
  __int64 v31; // rbx
  _QWORD *v32; // rcx
  int v34; // eax
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // rdi
  unsigned int v38; // ebp
  _BYTE *v39; // r14
  int v40; // edx
  int j; // r8d
  __int64 v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // rax
  unsigned __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // [rsp+20h] [rbp-118h]
  __int64 v51; // [rsp+28h] [rbp-110h]
  __int64 v52; // [rsp+30h] [rbp-108h]
  int v54; // [rsp+48h] [rbp-F0h]
  __int64 v57; // [rsp+60h] [rbp-D8h]
  __int64 v58; // [rsp+68h] [rbp-D0h]
  char v59[16]; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+80h] [rbp-B8h]
  unsigned int v61; // [rsp+A4h] [rbp-94h]
  unsigned int v62; // [rsp+B0h] [rbp-88h]

  v6 = a6;
  v7 = a3;
  v9 = a1;
  if ( a2 && *a2 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 1;
    if ( !a2 )
    {
LABEL_31:
      if ( *(_BYTE *)(v7 + 102) == 2 )
        goto LABEL_6;
      goto LABEL_8;
    }
  }
  if ( !strcmp_0(a2, ":memory:") )
  {
LABEL_6:
    v11 = 1;
    goto LABEL_10;
  }
  if ( v10 )
    goto LABEL_31;
LABEL_8:
  if ( (a6 & 0x80u) != 0 )
    goto LABEL_6;
  v11 = 0;
LABEL_10:
  v12 = a5 | 2;
  if ( !v11 )
    v12 = a5;
  v54 = v12;
  if ( (a6 & 0x100) != 0 && (v11 || v10) )
    v6 = a6 & 0xFFFFFCFF | 0x200;
  v13 = sqlite3MallocZero(0x48u);
  v14 = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = v7;
    v57 = 0;
    *(_BYTE *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 48) = v13;
    *(_DWORD *)(v13 + 56) = 1;
    if ( v10 || v11 && (v6 & 0x40) == 0 || (v6 & 0x20000) == 0 )
      goto LABEL_19;
    v34 = sqlite3Strlen30(a2);
    v36 = *(_DWORD *)(v9 + 8);
    v37 = v34;
    v38 = v36 + 1;
    if ( v36 + 1 <= v34 + 1 )
      v36 = v34;
    v39 = (_BYTE *)sqlite3Malloc(v35 + v36);
    v29 = (_BYTE *)(v14 + 17);
    *(_BYTE *)(v14 + 17) = 1;
    if ( v39 )
    {
      if ( v11 )
      {
        Fileheader = 0;
        memcpy_0(v39, a2, v37 + 1);
        goto LABEL_50;
      }
      *v39 = 0;
      v43 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _BYTE *))(a1 + 64))(a1, a2, v38, v39);
      Fileheader = v43;
      if ( !v43 )
      {
LABEL_50:
        v57 = sqlite3MutexAlloc(4);
        sqlite3_mutex_enter(v57);
        v58 = sqlite3MutexAlloc(2);
        sqlite3_mutex_enter(v58);
        for ( i = (__int64 *)qword_1800D0DB0; i; i = (__int64 *)i[14] )
        {
          if ( !strcmp(v39, *(const char **)(*i + 216)) && *(_QWORD *)*i == a1 )
          {
            v40 = *(_DWORD *)(a3 + 40);
            do
            {
              if ( --v40 < 0 )
              {
                *(_QWORD *)(v14 + 8) = i;
                ++*((_DWORD *)i + 26);
                goto LABEL_58;
              }
              v44 = *(_QWORD *)(32LL * v40 + *(_QWORD *)(a3 + 32) + 8);
            }
            while ( !v44 || *(__int64 **)(v44 + 8) != i );
            sqlite3_mutex_leave(v58);
            sqlite3_mutex_leave(v57);
            sqlite3_free(v39);
            sqlite3_free(v14);
            return 19;
          }
        }
LABEL_58:
        sqlite3_mutex_leave(v58);
        sqlite3_free(v39);
        if ( i )
          goto LABEL_59;
        v7 = a3;
        v12 = v54;
        v9 = a1;
LABEL_19:
        v60 = 0;
        v15 = (__int64 *)sqlite3MallocZero(0x98u);
        i = v15;
        if ( v15 )
        {
          LODWORD(v51) = v6;
          LODWORD(v50) = v12;
          Fileheader = sqlite3PagerOpen(v9, v15, a2, v16, v50, v51, v52);
          if ( Fileheader )
            goto LABEL_28;
          *(_QWORD *)(*i + 160) = *(_QWORD *)(v7 + 64);
          pagerFixMaplimit();
          Fileheader = sqlite3PagerReadFileheader(*i, v19, v59);
          if ( Fileheader )
            goto LABEL_28;
          v20 = (_QWORD *)*i;
          *((_BYTE *)i + 32) = v12;
          i[1] = v7;
          v21 = v20 + 29;
          v20[30] = i;
          v22 = v20[9];
          *v21 = btreeInvokeBusyHandler;
          sqlite3OsFileControlHint(v22, 15);
          *(_QWORD *)(v14 + 8) = i;
          v23 = *i;
          i[2] = 0;
          i[3] = 0;
          if ( *(_BYTE *)(v23 + 18) )
            *((_WORD *)i + 20) |= 1u;
          v24 = (_DWORD *)i + 13;
          v25 = (unsigned __int16)v60 << 8;
          *((_DWORD *)i + 13) = v25;
          if ( (unsigned int)(v25 - 512) > 0xFE00 || ((v25 - 1) & v25) != 0 )
          {
            *v24 = 0;
            if ( a2 && !v11 )
              *(_WORD *)((char *)i + 33) = 0;
            v26 = 0;
          }
          else
          {
            v26 = BYTE4(v60);
            *((_WORD *)i + 20) |= 2u;
            *((_BYTE *)i + 33) = _byteswap_ulong(v61) != 0;
            *((_BYTE *)i + 34) = _byteswap_ulong(v62) != 0;
          }
          v27 = v26;
          Fileheader = sqlite3PagerSetPagesize(v23, (char *)i + 52, v26);
          if ( Fileheader )
            goto LABEL_28;
          v29 = (_BYTE *)(v14 + 17);
          v30 = *v24 - v27;
          *((_DWORD *)i + 26) = 1;
          *((_DWORD *)i + 14) = v30;
          if ( *(_BYTE *)(v14 + 17) )
          {
            v45 = sqlite3MutexAlloc(2);
            if ( (_BYTE)word_1800D0874 )
            {
              v46 = sqlite3MutexAlloc(0);
              i[11] = v46;
              if ( !v46 )
              {
                Fileheader = 7;
LABEL_28:
                v28 = a4;
LABEL_29:
                if ( *i )
                  sqlite3PagerClose(*i, 0);
                goto LABEL_73;
              }
            }
            sqlite3_mutex_enter(v45);
            i[14] = qword_1800D0DB0;
            qword_1800D0DB0 = (__int64)i;
            sqlite3_mutex_leave(v45);
LABEL_59:
            if ( *v29 )
            {
              for ( j = 0; j < *(_DWORD *)(a3 + 40); ++j )
              {
                v42 = *(_QWORD *)(32LL * j + *(_QWORD *)(a3 + 32) + 8);
                if ( v42 && *(_BYTE *)(v42 + 17) )
                {
                  while ( *(_QWORD *)(v42 + 40) )
                    v42 = *(_QWORD *)(v42 + 40);
                  v47 = *(_QWORD *)(v14 + 8);
                  if ( v47 >= *(_QWORD *)(v42 + 8) )
                  {
                    if ( *(_QWORD *)(v42 + 32) )
                    {
                      do
                      {
                        v48 = *(_QWORD *)(v42 + 32);
                        if ( *(_QWORD *)(v48 + 8) >= v47 )
                          break;
                        v42 = *(_QWORD *)(v42 + 32);
                      }
                      while ( *(_QWORD *)(v48 + 32) );
                    }
                    v49 = *(_QWORD *)(v42 + 32);
                    *(_QWORD *)(v14 + 32) = v49;
                    *(_QWORD *)(v14 + 40) = v42;
                    if ( v49 )
                      *(_QWORD *)(v49 + 40) = v14;
                    *(_QWORD *)(v42 + 32) = v14;
                  }
                  else
                  {
                    *(_QWORD *)(v14 + 32) = v42;
                    *(_QWORD *)(v14 + 40) = 0;
                    *(_QWORD *)(v42 + 40) = v14;
                  }
                  break;
                }
              }
            }
          }
          v28 = a4;
          *a4 = v14;
          if ( !Fileheader )
          {
            v31 = *(_QWORD *)(v14 + 8);
            sqlite3BtreeEnter(v14);
            sqlite3BtreeLeave(v14);
            if ( !*(_QWORD *)(v31 + 72) )
              sqlite3BtreeSetCacheSize(v14, 4294965296LL);
            v32 = *(_QWORD **)(*i + 72);
            if ( *v32 )
              sqlite3OsFileControlHint(v32, 30);
            goto LABEL_41;
          }
          if ( i )
            goto LABEL_29;
        }
        else
        {
          v28 = a4;
          Fileheader = 7;
        }
LABEL_73:
        sqlite3_free(i);
        sqlite3_free(v14);
        *v28 = 0;
LABEL_41:
        if ( v57 )
          sqlite3_mutex_leave(v57);
        return Fileheader;
      }
      if ( v43 == 512 )
      {
        Fileheader = 0;
        goto LABEL_50;
      }
      sqlite3_free(v39);
    }
    else
    {
      Fileheader = 7;
    }
    sqlite3_free(v14);
    return Fileheader;
  }
  return 7;
}

```

## disassembly

```asm
0x180035d1c  push    rbx
0x180035d1e  push    rbp
0x180035d1f  push    rsi
0x180035d20  push    rdi
0x180035d21  push    r12
0x180035d23  push    r13
0x180035d25  push    r14
0x180035d27  push    r15
0x180035d29  sub     rsp, 0F8h
0x180035d30  mov     rax, cs:__security_cookie
0x180035d37  xor     rax, rsp
0x180035d3a  mov     [rsp+138h+var_58], rax
0x180035d42  mov     ebx, [rsp+138h+arg_28]
0x180035d49  mov     r14, r8
0x180035d4c  mov     [rsp+138h+var_F8], r9
0x180035d51  mov     r15, rdx
0x180035d54  mov     [rsp+138h+var_E0], r8
0x180035d59  mov     rbp, rcx
0x180035d5c  mov     [rsp+138h+var_E8], rcx
0x180035d61  mov     esi, 1
0x180035d66  test    rdx, rdx
0x180035d69  jz      short loc_180035D74
0x180035d6b  cmp     byte ptr [rdx], 0
0x180035d6e  jz      short loc_180035D74
0x180035d70  xor     edi, edi
0x180035d72  jmp     short loc_180035D7F
0x180035d74  mov     edi, esi
0x180035d76  test    r15, r15
0x180035d79  jz      loc_180035F48
0x180035d7f  lea     rdx, Str2; ":memory:"
0x180035d86  mov     rcx, r15; Str1
0x180035d89  call    strcmp_0
0x180035d8e  test    eax, eax
0x180035d90  jnz     short loc_180035D97
0x180035d92  mov     r13d, esi
0x180035d95  jmp     short loc_180035DA6
0x180035d97  test    edi, edi
0x180035d99  jnz     loc_180035F48
0x180035d9f  test    bl, bl
0x180035da1  js      short loc_180035D92
0x180035da3  xor     r13d, r13d
0x180035da6  mov     r12d, [rsp+138h+arg_20]
0x180035dae  or      r12d, 2
0x180035db2  test    r13d, r13d
0x180035db5  cmovz   r12d, [rsp+138h+arg_20]
0x180035dbe  mov     [rsp+138h+var_F0], r12d
0x180035dc3  bt      ebx, 8
0x180035dc7  jnb     short loc_180035DDA
0x180035dc9  test    r13d, r13d
0x180035dcc  jnz     loc_180036250
0x180035dd2  test    edi, edi
0x180035dd4  jnz     loc_180036250
0x180035dda  mov     ecx, 48h ; 'H'; Size
0x180035ddf  call    sqlite3MallocZero
0x180035de4  mov     rsi, rax
0x180035de7  test    rax, rax
0x180035dea  jz      loc_18003603D
0x180035df0  xor     ecx, ecx
0x180035df2  mov     [rax], r14
0x180035df5  mov     [rsp+138h+var_D8], rcx
0x180035dfa  mov     [rax+10h], cl
0x180035dfd  mov     [rax+30h], rax
0x180035e01  lea     r8d, [rcx+1]
0x180035e05  mov     [rax+38h], r8d
0x180035e09  test    edi, edi
0x180035e0b  jnz     short loc_180035E20
0x180035e0d  test    r13d, r13d
0x180035e10  jnz     loc_18003625D
0x180035e16  bt      ebx, 11h
0x180035e1a  jb      loc_180036044
0x180035e20  xor     eax, eax
0x180035e22  mov     ecx, 98h; Size
0x180035e27  mov     [rsp+138h+var_B8], rax
0x180035e2f  call    sqlite3MallocZero
0x180035e34  mov     rdi, rax
0x180035e37  test    rax, rax
0x180035e3a  jz      loc_18003628C
0x180035e40  mov     dword ptr [rsp+138h+var_110], ebx
0x180035e44  mov     r8, r15
0x180035e47  mov     rdx, rax
0x180035e4a  mov     dword ptr [rsp+138h+var_118], r12d
0x180035e4f  mov     rcx, rbp
0x180035e52  call    sqlite3PagerOpen
0x180035e57  mov     ebp, eax
0x180035e59  test    eax, eax
0x180035e5b  jnz     loc_180035F2B
0x180035e61  mov     rcx, [rdi]
0x180035e64  mov     rax, [r14+40h]
0x180035e68  mov     [rcx+0A0h], rax
0x180035e6f  call    pagerFixMaplimit
0x180035e74  mov     rcx, [rdi]
0x180035e77  lea     r8, [rsp+138h+var_C8]
0x180035e7c  call    sqlite3PagerReadFileheader
0x180035e81  mov     ebp, eax
0x180035e83  test    eax, eax
0x180035e85  jnz     loc_180035F2B
0x180035e8b  mov     rcx, [rdi]
0x180035e8e  lea     rax, btreeInvokeBusyHandler
0x180035e95  mov     [rdi+20h], r12b
0x180035e99  lea     edx, [rbp+0Fh]
0x180035e9c  mov     [rdi+8], r14
0x180035ea0  lea     r8, [rcx+0E8h]
0x180035ea7  mov     [rcx+0F0h], rdi
0x180035eae  mov     rcx, [rcx+48h]
0x180035eb2  mov     [r8], rax
0x180035eb5  call    sqlite3OsFileControlHint
0x180035eba  mov     [rsi+8], rdi
0x180035ebe  xor     edx, edx
0x180035ec0  mov     r9, [rdi]
0x180035ec3  mov     [rdi+10h], rdx
0x180035ec7  mov     [rdi+18h], rdx
0x180035ecb  cmp     [r9+12h], dl
0x180035ecf  jnz     loc_180036298
0x180035ed5  movzx   eax, byte ptr [rsp+138h+var_B8]
0x180035edd  lea     rbx, [rdi+34h]
0x180035ee1  movzx   ecx, byte ptr [rsp+138h+var_B8+1]
0x180035ee9  shl     ecx, 8
0x180035eec  or      ecx, eax
0x180035eee  shl     ecx, 8
0x180035ef1  mov     [rbx], ecx
0x180035ef3  lea     eax, [rcx-200h]
0x180035ef9  cmp     eax, 0FE00h
0x180035efe  jbe     short loc_180035F58
0x180035f00  mov     [rbx], edx
0x180035f02  test    r15, r15
0x180035f05  jnz     loc_1800362A6
0x180035f0b  xor     cl, cl
0x180035f0d  mov     r15d, 2
0x180035f13  movzx   r14d, cl
0x180035f17  mov     rdx, rbx
0x180035f1a  mov     r8d, r14d
0x180035f1d  mov     rcx, r9
0x180035f20  call    sqlite3PagerSetPagesize
0x180035f25  mov     ebp, eax
0x180035f27  test    eax, eax
0x180035f29  jz      short loc_180035F98
0x180035f2b  mov     rbx, [rsp+138h+var_F8]
0x180035f30  mov     rcx, [rdi]
0x180035f33  test    rcx, rcx
0x180035f36  jz      loc_180036234
0x180035f3c  xor     edx, edx
0x180035f3e  call    sqlite3PagerClose
0x180035f43  jmp     loc_180036234
0x180035f48  cmp     byte ptr [r14+66h], 2
0x180035f4d  jnz     loc_180035D9F
0x180035f53  jmp     loc_180035D92
0x180035f58  lea     eax, [rcx-1]
0x180035f5b  test    ecx, eax
0x180035f5d  jnz     short loc_180035F00
0x180035f5f  mov     cl, byte ptr [rsp+138h+var_B8+4]
0x180035f66  mov     r15d, 2
0x180035f6c  or      [rdi+28h], r15w
0x180035f71  mov     eax, [rsp+138h+var_94]
0x180035f78  bswap   eax
0x180035f7a  test    eax, eax
0x180035f7c  setnz   al
0x180035f7f  mov     [rdi+21h], al
0x180035f82  mov     eax, [rsp+138h+var_88]
0x180035f89  bswap   eax
0x180035f8b  test    eax, eax
0x180035f8d  setnz   al
0x180035f90  mov     [rdi+22h], al
0x180035f93  jmp     loc_180035F13
0x180035f98  mov     eax, [rbx]
0x180035f9a  lea     r12, [rsi+11h]
0x180035f9e  sub     eax, r14d
0x180035fa1  mov     dword ptr [rdi+68h], 1
0x180035fa8  mov     [rdi+38h], eax
0x180035fab  cmp     byte ptr [r12], 0
0x180035fb0  jnz     loc_1800362B8
0x180035fb6  mov     rbx, [rsp+138h+var_F8]
0x180035fbb  mov     [rbx], rsi
0x180035fbe  test    ebp, ebp
0x180035fc0  jnz     loc_18003622B
0x180035fc6  mov     rbx, [rsi+8]
0x180035fca  mov     rcx, rsi
0x180035fcd  call    sqlite3BtreeEnter
0x180035fd2  mov     rcx, rsi
0x180035fd5  call    sqlite3BtreeLeave
0x180035fda  cmp     qword ptr [rbx+48h], 0
0x180035fdf  jnz     short loc_180035FEE
0x180035fe1  mov     edx, 0FFFFF830h
0x180035fe6  mov     rcx, rsi
0x180035fe9  call    sqlite3BtreeSetCacheSize
0x180035fee  mov     rax, [rdi]
0x180035ff1  mov     rcx, [rax+48h]
0x180035ff5  cmp     qword ptr [rcx], 0
0x180035ff9  jz      short loc_180036009
0x180035ffb  lea     r8, [rdi+8]
0x180035fff  mov     edx, 1Eh
0x180036004  call    sqlite3OsFileControlHint
0x180036009  mov     rax, [rsp+138h+var_D8]
0x18003600e  test    rax, rax
0x180036011  jnz     loc_1800361CD
0x180036017  mov     eax, ebp
0x180036019  mov     rcx, [rsp+138h+var_58]
0x180036021  xor     rcx, rsp; StackCookie
0x180036024  call    __security_check_cookie
0x180036029  add     rsp, 0F8h
0x180036030  pop     r15
0x180036032  pop     r14
0x180036034  pop     r13
0x180036036  pop     r12
0x180036038  pop     rdi
0x180036039  pop     rsi
0x18003603a  pop     rbp
0x18003603b  pop     rbx
0x18003603c  retn
0x18003603d  mov     eax, 7
0x180036042  jmp     short loc_180036019
0x180036044  mov     rcx, r15
0x180036047  call    sqlite3Strlen30
0x18003604c  mov     edx, [rbp+8]
0x18003604f  movsxd  rdi, eax
0x180036052  lea     ebp, [rdx+1]
0x180036055  lea     ecx, [rdi+1]
0x180036058  cmp     ebp, ecx
0x18003605a  cmovle  edx, edi
0x18003605d  movsxd  rcx, edx
0x180036060  add     rcx, r8
0x180036063  call    sqlite3Malloc
0x180036068  mov     r14, rax
0x18003606b  lea     r12, [rsi+11h]
0x18003606f  mov     eax, 1
0x180036074  mov     [r12], al
0x180036078  test    r14, r14
0x18003607b  jz      loc_180036184
0x180036081  mov     rdx, r15; Src
0x180036084  test    r13d, r13d
0x180036087  jz      loc_180036196
0x18003608d  xor     ebp, ebp
0x18003608f  lea     r8, [rax+rdi]; Size
0x180036093  mov     rcx, r14; void *
0x180036096  call    memcpy_0
0x18003609b  mov     ecx, 4
0x1800360a0  call    sqlite3MutexAlloc
0x1800360a5  mov     rcx, rax
0x1800360a8  mov     [rsp+138h+var_D8], rax
0x1800360ad  call    sqlite3_mutex_enter
0x1800360b2  mov     ecx, 2
0x1800360b7  call    sqlite3MutexAlloc
0x1800360bc  mov     rcx, rax
0x1800360bf  mov     [rsp+138h+var_D0], rax
0x1800360c4  call    sqlite3_mutex_enter
0x1800360c9  mov     r10, [rsp+138h+var_E8]
0x1800360ce  mov     rdi, cs:qword_1800D0DB0
0x1800360d5  test    rdi, rdi
0x1800360d8  jz      short loc_18003612E
0x1800360da  mov     r9, [rdi]
0x1800360dd  mov     rcx, r14
0x1800360e0  mov     r11d, 1
0x1800360e6  mov     r8, [r9+0D8h]
0x1800360ed  sub     r8, r14
0x1800360f0  movzx   edx, byte ptr [rcx]
0x1800360f3  movzx   eax, byte ptr [rcx+r8]
0x1800360f8  sub     edx, eax
0x1800360fa  jnz     short loc_180036103
0x1800360fc  add     rcx, r11
0x1800360ff  test    eax, eax
0x180036101  jnz     short loc_1800360F0
0x180036103  test    edx, edx
0x180036105  jz      short loc_18003610D
0x180036107  mov     rdi, [rdi+70h]
0x18003610b  jmp     short loc_1800360D5
0x18003610d  cmp     [r9], r10
0x180036110  jnz     short loc_180036107
0x180036112  mov     r9, [rsp+138h+var_E0]
0x180036117  mov     edx, [r9+28h]
0x18003611b  sub     edx, r11d
0x18003611e  test    edx, edx
0x180036120  jns     loc_1800361DA
0x180036126  mov     [rsi+8], rdi
0x18003612a  add     [rdi+68h], r11d
0x18003612e  mov     rcx, [rsp+138h+var_D0]
0x180036133  call    sqlite3_mutex_leave
0x180036138  mov     rcx, r14
0x18003613b  call    sqlite3_free
0x180036140  test    rdi, rdi
0x180036143  jz      loc_180036278
0x180036149  cmp     byte ptr [r12], 0
0x18003614e  jz      loc_180035FB6
0x180036154  xor     r8d, r8d
0x180036157  mov     rax, [rsp+138h+var_E0]
0x18003615c  cmp     r8d, [rax+28h]
0x180036160  jge     loc_180035FB6
0x180036166  mov     rax, [rax+20h]
0x18003616a  movsxd  rcx, r8d
0x18003616d  shl     rcx, 5
0x180036171  mov     rdx, [rcx+rax+8]
0x180036176  test    rdx, rdx
0x180036179  jnz     loc_18003630B
0x18003617f  inc     r8d
0x180036182  jmp     short loc_180036157
0x180036184  mov     ebp, 7
0x180036189  mov     rcx, rsi
0x18003618c  call    sqlite3_free
0x180036191  jmp     loc_180036017
0x180036196  mov     rax, [rsp+138h+var_E8]
0x18003619b  mov     r9, r14
0x18003619e  mov     byte ptr [r14], 0
  ... truncated ...
```
