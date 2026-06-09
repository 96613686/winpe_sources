# CAppInfo::SetActionPass1(void)

- ea: `0x180007ea4`
- end: `0x1800084cd`
- name: `?SetActionPass1@CAppInfo@@QEAAXXZ`
- size: `1577`
- prototype: `void __fastcall(CAppInfo *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003370`
- `0x18000b0a8`

## callees

- `0x1800016d0`
- `0x180007de4`
- `0x180007ea4`
- `0x180008f58`
- `0x18000a554`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008395`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008395`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800083d7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800083e4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800083d7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800083e4`

## pseudocode

```c
void __fastcall CAppInfo::SetActionPass1(CAppInfo *this)
{
  CAppInfo *v1; // rdi
  int v2; // edx
  int v3; // r8d
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // edx
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  CAppList *v19; // rcx
  const FILETIME *v20; // r14
  __int64 v21; // [rsp+20h] [rbp-A9h]
  __int64 v22; // [rsp+28h] [rbp-A1h]
  __int64 v23; // [rsp+30h] [rbp-99h]
  __int64 v24; // [rsp+38h] [rbp-91h]
  __int64 v25; // [rsp+40h] [rbp-89h]
  struct _SYSTEMTIME v26; // [rsp+50h] [rbp-79h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int16 v28[32]; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int16 v29[32]; // [rsp+B0h] [rbp-19h] BYREF

  v1 = this;
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 308LL) )
  {
    if ( (*((_DWORD *)this + 53) & 0x408) == 0 || (*((_DWORD *)this + 53) & 0x20) == 0 )
      return;
    v2 = 2;
    v3 = 0;
    goto LABEL_4;
  }
  v2 = 1;
  if ( *((_DWORD *)this + 55) )
  {
    CAppInfo::SetAction((__int64)this, 1, 0, 0);
    v2 = 1;
  }
  v4 = *((_QWORD *)v1 + 2);
  if ( !*(_DWORD *)(v4 + 300) )
  {
    v8 = *((_DWORD *)v1 + 53);
    if ( (v8 & 0x100) != 0 )
    {
      v9 = (_DWORD *)((char *)v1 + 224);
      v10 = *((_DWORD *)v1 + 56);
      if ( (v10 & 0x103) != 0 )
      {
        v11 = 3;
        goto LABEL_31;
      }
    }
    else
    {
      v10 = *((_DWORD *)v1 + 56);
    }
    v9 = (_DWORD *)((char *)v1 + 224);
    if ( (v10 & 0x140) != 0x140 )
      goto LABEL_33;
    if ( *(_DWORD *)(v4 + 296) && (v8 & 0x400) != 0 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xCB1u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
LABEL_33:
      if ( *((_DWORD *)v1 + 57) == 4 )
        return;
      if ( *((char *)v1 + 212) < 0 && (*v9 & 0x103) != 0 || (*v9 & 0x120) == 0x120 )
      {
        CAppInfo::SetAction((__int64)v1, 5, 3, 0);
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xBF8u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
      }
      v12 = *((_DWORD *)v1 + 57);
      if ( v12 == 5 )
        return;
      if ( v12 )
      {
LABEL_68:
        if ( *((_DWORD *)v1 + 57) || *((_DWORD *)v1 + 53) || (v17 = *((_DWORD *)v1 + 56), (v17 & 3) == 0) )
        {
          if ( (*((_DWORD *)v1 + 56) & 3) != 0 && (*((_DWORD *)v1 + 56) & 0x100) != 0 )
          {
            v18 = *((_DWORD *)v1 + 51);
            if ( v18 )
            {
              if ( *((_DWORD *)v1 + 48) >= v18 )
              {
                v19 = (CAppList *)(*((_QWORD *)v1 + 2) + 136LL);
                v26 = *(struct _SYSTEMTIME *)((char *)v1 + 24);
                v20 = (const FILETIME *)((char *)CAppList::Find(v19, (struct _GUID *)&v26) + 196);
                if ( CompareFileTime(v20, (const FILETIME *)((char *)v1 + 196)) < 0 )
                {
                  CAppInfo::SetAction((__int64)v1, 3, 8, 0);
                  if ( (gDebugLevel & 2) != 0 )
                  {
                    SystemTime = 0;
                    v26 = 0;
                    FileTimeToSystemTime(v20, &SystemTime);
                    FileTimeToSystemTime((const FILETIME *)((char *)v1 + 196), &v26);
                    StringCchPrintfW(
                      v29,
                      0x20u,
                      L"%02d-%02d %02d:%02d:%02d:%03d",
                      SystemTime.wMonth,
                      SystemTime.wDay,
                      SystemTime.wHour,
                      SystemTime.wMinute,
                      SystemTime.wSecond,
                      SystemTime.wMilliseconds);
                    LODWORD(v25) = v26.wMilliseconds;
                    LODWORD(v24) = v26.wSecond;
                    LODWORD(v23) = v26.wMinute;
                    LODWORD(v22) = v26.wHour;
                    LODWORD(v21) = v26.wDay;
                    StringCchPrintfW(v28, 0x20u, L"%02d-%02d %02d:%02d:%02d:%03d", v26.wMonth, v21, v22, v23, v24, v25);
                    if ( *(_DWORD *)&gDebugLevel )
                      _DebugMsg(4, 0xC1Cu, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9), v29, v28);
                  }
                }
              }
              else
              {
                CAppInfo::SetAction((__int64)v1, 3, 8, 0);
                if ( *(_DWORD *)&gDebugLevel )
                  _DebugMsg(4, 0xC08u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
              }
            }
          }
        }
        else
        {
          if ( (v17 & 0x10) != 0 )
          {
            CAppInfo::SetAction((__int64)v1, 4, 5, 0);
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xC05u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
          }
          else
          {
            CAppInfo::SetAction((__int64)v1, 5, 5, 0);
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xC04u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
          }
          *((_DWORD *)v1 + 96) = 5;
        }
        return;
      }
      v13 = *((_DWORD *)v1 + 53);
      if ( (v13 & 0x400) != 0 )
      {
        if ( (v13 & 0x2000) == 0 || (*v9 & 0x280) == 0x80 )
        {
          if ( *(_DWORD *)(*((_QWORD *)v1 + 2) + 296LL) )
            goto LABEL_50;
          if ( (*(_BYTE *)v9 & 1) == 0 )
          {
            CAppInfo::SetAction((__int64)v1, 2, 1, 0);
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xBD7u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
            goto LABEL_52;
          }
          v14 = *((_DWORD *)v1 + 54);
          if ( v14 != 1 && (unsigned int)(v14 - 3) > 2 )
          {
LABEL_50:
            CAppInfo::SetAction((__int64)v1, 1, 1, 0);
            *v9 |= 0x4000u;
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xBD8u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
          }
        }
        else
        {
          CAppInfo::SetAction((__int64)v1, 2, 1, 0);
          if ( *(_DWORD *)&gDebugLevel )
            _DebugMsg(4, 0xBFEu, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
        }
      }
LABEL_52:
      if ( (*((_BYTE *)v1 + 212) & 8) != 0 )
      {
        v15 = *((_DWORD *)v1 + 56);
        if ( (v15 & 3) != 0 )
        {
          if ( (v15 & 0x200) != 0 )
          {
            CAppInfo::SetAction((__int64)v1, 1, 3, 0);
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xBDAu, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
          }
          else if ( *((_DWORD *)v1 + 78) )
          {
            CAppInfo::SetAction((__int64)v1, 1, 0, 0);
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xCA7u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
          }
          else
          {
            v16 = *((_DWORD *)v1 + 54);
            if ( v16 == -1 || v16 == 2 )
            {
              CAppInfo::SetAction((__int64)v1, 5, 4, 0);
              if ( *(_DWORD *)&gDebugLevel )
                _DebugMsg(4, 0xC0Fu, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
            }
            else if ( *(_DWORD *)&gDebugLevel )
            {
              _DebugMsg(4, 0xC06u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
            }
          }
        }
      }
      goto LABEL_68;
    }
    v11 = 8;
LABEL_31:
    CAppInfo::SetAction((__int64)v1, 4, v11, 0);
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBD6u, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
    goto LABEL_33;
  }
  v5 = *((_DWORD *)v1 + 56);
  if ( (v5 & 1) != 0 )
  {
    if ( *(_DWORD *)(v4 + 296) || (v6 = *((_DWORD *)v1 + 54), v6 != 1) && (unsigned int)(v6 - 3) > 2 )
    {
      CAppInfo::SetAction((__int64)v1, 1, 1, 0);
      *((_DWORD *)v1 + 56) |= 0x4000u;
    }
  }
  else if ( (v5 & 2) != 0 )
  {
    if ( (v5 & 0x200) != 0 )
    {
      this = v1;
      v3 = 3;
LABEL_4:
      CAppInfo::SetAction((__int64)this, v2, v3, 0);
      return;
    }
    v7 = *((_DWORD *)v1 + 54);
    if ( (v7 == -1 || v7 == 2) && !*((_DWORD *)v1 + 78) )
    {
      CAppInfo::SetAction((__int64)v1, 5, 8, 0);
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC0Fu, *((_QWORD *)v1 + 5), *((_QWORD *)v1 + 9));
    }
  }
}

```

## disassembly

```asm
0x180007ea4  mov     [rsp-8+arg_8], rbx
0x180007ea9  mov     [rsp-8+arg_10], rsi
0x180007eae  push    rbp
0x180007eaf  push    rdi
0x180007eb0  push    r13
0x180007eb2  push    r14
0x180007eb4  push    r15
0x180007eb6  lea     rbp, [rsp-37h]
0x180007ebb  sub     rsp, 100h
0x180007ec2  mov     rax, cs:__security_cookie
0x180007ec9  xor     rax, rsp
0x180007ecc  mov     [rbp+57h+var_30], rax
0x180007ed0  mov     rax, [rcx+10h]
0x180007ed4  xor     r13d, r13d
0x180007ed7  mov     rdi, rcx
0x180007eda  cmp     [rax+134h], r13d
0x180007ee1  jz      short loc_180007F12
0x180007ee3  mov     eax, [rcx+0D4h]
0x180007ee9  test    eax, 408h
0x180007eee  setnz   dl
0x180007ef1  test    al, 20h
0x180007ef3  setnz   al
0x180007ef6  test    al, dl
0x180007ef8  jz      loc_1800084A5
0x180007efe  xor     r9d, r9d
0x180007f01  lea     edx, [r13+2]
0x180007f05  xor     r8d, r8d
0x180007f08  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180007f0d  jmp     loc_1800084A5
0x180007f12  mov     edx, 1
0x180007f17  cmp     [rcx+0DCh], r13d
0x180007f1e  jz      short loc_180007F30
0x180007f20  xor     r9d, r9d
0x180007f23  xor     r8d, r8d
0x180007f26  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180007f2b  mov     edx, 1
0x180007f30  mov     rcx, [rdi+10h]
0x180007f34  cmp     [rcx+12Ch], r13d
0x180007f3b  jz      loc_180007FF6
0x180007f41  mov     eax, [rdi+0E0h]
0x180007f47  test    dl, al
0x180007f49  jz      short loc_180007F89
0x180007f4b  cmp     [rcx+128h], r13d
0x180007f52  jnz     short loc_180007F6E
0x180007f54  mov     eax, [rdi+0D8h]
0x180007f5a  cmp     eax, edx
0x180007f5c  jz      loc_1800084A5
0x180007f62  add     eax, 0FFFFFFFDh
0x180007f65  cmp     eax, 2
0x180007f68  jbe     loc_1800084A5
0x180007f6e  xor     r9d, r9d
0x180007f71  mov     r8d, edx
0x180007f74  mov     rcx, rdi
0x180007f77  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180007f7c  bts     dword ptr [rdi+0E0h], 0Eh
0x180007f84  jmp     loc_1800084A5
0x180007f89  test    al, 2
0x180007f8b  jz      loc_1800084A5
0x180007f91  bt      eax, 9
0x180007f95  jnb     short loc_180007FA6
0x180007f97  xor     r9d, r9d
0x180007f9a  mov     rcx, rdi
0x180007f9d  lea     r8d, [r9+3]
0x180007fa1  jmp     loc_180007F08
0x180007fa6  mov     eax, [rdi+0D8h]
0x180007fac  cmp     eax, 0FFFFFFFFh
0x180007faf  jz      short loc_180007FBA
0x180007fb1  cmp     eax, 2
0x180007fb4  jnz     loc_1800084A5
0x180007fba  cmp     [rdi+138h], r13d
0x180007fc1  jnz     loc_1800084A5
0x180007fc7  xor     r9d, r9d
0x180007fca  mov     rcx, rdi
0x180007fcd  lea     edx, [r9+5]
0x180007fd1  lea     r8d, [r9+8]
0x180007fd5  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180007fda  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180007fe1  jz      loc_1800084A5
0x180007fe7  mov     edx, 0C0Fh
0x180007fec  mov     ecx, 4
0x180007ff1  jmp     loc_180008352
0x180007ff6  mov     edx, [rdi+0D4h]
0x180007ffc  mov     esi, 4
0x180008001  lea     r15d, [rsi-1]
0x180008005  bt      edx, 8
0x180008009  jnb     short loc_180008020
0x18000800b  lea     rbx, [rdi+0E0h]
0x180008012  mov     eax, [rbx]
0x180008014  test    eax, 103h
0x180008019  jz      short loc_180008026
0x18000801b  mov     r8d, r15d
0x18000801e  jmp     short loc_180008060
0x180008020  mov     eax, [rdi+0E0h]
0x180008026  mov     r8d, 140h
0x18000802c  lea     rbx, [rdi+0E0h]
0x180008033  and     eax, r8d
0x180008036  cmp     eax, r8d
0x180008039  jnz     short loc_18000808A
0x18000803b  cmp     [rcx+128h], r13d
0x180008042  jz      short loc_18000805A
0x180008044  bt      edx, 0Ah
0x180008048  jnb     short loc_18000805A
0x18000804a  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008051  jz      short loc_18000808A
0x180008053  mov     edx, 0CB1h
0x180008058  jmp     short loc_18000807B
0x18000805a  mov     r8d, 8
0x180008060  xor     r9d, r9d
0x180008063  mov     edx, esi
0x180008065  mov     rcx, rdi
0x180008068  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18000806d  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008074  jz      short loc_18000808A
0x180008076  mov     edx, 0BD6h; unsigned int
0x18000807b  mov     r9, [rdi+48h]
0x18000807f  mov     ecx, esi; unsigned int
0x180008081  mov     r8, [rdi+28h]
0x180008085  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000808a  cmp     [rdi+0E4h], esi
0x180008090  jz      loc_1800084A5
0x180008096  test    byte ptr [rdi+0D4h], 80h
0x18000809d  mov     r14d, 5
0x1800080a3  jz      short loc_1800080AD
0x1800080a5  test    dword ptr [rbx], 103h
0x1800080ab  jnz     short loc_1800080BA
0x1800080ad  mov     eax, [rbx]
0x1800080af  mov     ecx, 120h
0x1800080b4  and     eax, ecx
0x1800080b6  cmp     eax, ecx
0x1800080b8  jnz     short loc_1800080E8
0x1800080ba  xor     r9d, r9d
0x1800080bd  mov     r8d, r15d
0x1800080c0  mov     edx, r14d
0x1800080c3  mov     rcx, rdi
0x1800080c6  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x1800080cb  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x1800080d2  jz      short loc_1800080E8
0x1800080d4  mov     r9, [rdi+48h]
0x1800080d8  mov     edx, 0BF8h; unsigned int
0x1800080dd  mov     r8, [rdi+28h]
0x1800080e1  mov     ecx, esi; unsigned int
0x1800080e3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800080e8  mov     eax, [rdi+0E4h]
0x1800080ee  cmp     eax, r14d
0x1800080f1  jz      loc_1800084A5
0x1800080f7  test    eax, eax
0x1800080f9  jnz     loc_180008289
0x1800080ff  mov     eax, [rdi+0D4h]
0x180008105  bt      eax, 0Ah
0x180008109  jnb     loc_1800081A2
0x18000810f  bt      eax, 0Dh
0x180008113  jnb     short loc_180008146
0x180008115  mov     eax, [rbx]
0x180008117  and     eax, 280h
0x18000811c  cmp     eax, 80h
0x180008121  jz      short loc_180008146
0x180008123  xor     r9d, r9d
0x180008126  mov     rcx, rdi
0x180008129  lea     edx, [r9+2]
0x18000812d  lea     r8d, [r9+1]
0x180008131  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180008136  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000813d  jz      short loc_1800081A2
0x18000813f  mov     edx, 0BFEh
0x180008144  jmp     short loc_180008193
0x180008146  mov     rax, [rdi+10h]
0x18000814a  cmp     [rax+128h], r13d
0x180008151  jnz     short loc_18000816F
0x180008153  test    byte ptr [rbx], 1
0x180008156  jz      loc_1800081ED
0x18000815c  mov     eax, [rdi+0D8h]
0x180008162  cmp     eax, 1
0x180008165  jz      short loc_1800081A2
0x180008167  add     eax, 0FFFFFFFDh
0x18000816a  cmp     eax, 2
0x18000816d  jbe     short loc_1800081A2
0x18000816f  xor     r9d, r9d
0x180008172  mov     rcx, rdi
0x180008175  lea     edx, [r9+1]
0x180008179  mov     r8d, edx
0x18000817c  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180008181  bts     dword ptr [rbx], 0Eh
0x180008185  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000818c  jz      short loc_1800081A2
0x18000818e  mov     edx, 0BD8h; unsigned int
0x180008193  mov     r9, [rdi+48h]
0x180008197  mov     ecx, esi; unsigned int
0x180008199  mov     r8, [rdi+28h]
0x18000819d  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800081a2  test    byte ptr [rdi+0D4h], 8
0x1800081a9  jz      loc_180008289
0x1800081af  mov     eax, [rdi+0E0h]
0x1800081b5  test    r15b, al
0x1800081b8  jz      loc_180008289
0x1800081be  bt      eax, 9
0x1800081c2  jnb     short loc_180008210
0x1800081c4  xor     r9d, r9d
0x1800081c7  mov     r8d, r15d
0x1800081ca  mov     rcx, rdi
0x1800081cd  lea     edx, [r9+1]
0x1800081d1  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x1800081d6  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x1800081dd  jz      loc_180008289
0x1800081e3  mov     edx, 0BDAh
0x1800081e8  jmp     loc_18000827A
0x1800081ed  xor     r9d, r9d
0x1800081f0  mov     rcx, rdi
0x1800081f3  lea     edx, [r9+2]
0x1800081f7  lea     r8d, [r9+1]
0x1800081fb  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x180008200  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008207  jz      short loc_1800081A2
0x180008209  mov     edx, 0BD7h
0x18000820e  jmp     short loc_180008193
0x180008210  cmp     [rdi+138h], r13d
0x180008217  jz      short loc_18000823B
0x180008219  xor     r9d, r9d
0x18000821c  xor     r8d, r8d
0x18000821f  mov     rcx, rdi
0x180008222  lea     edx, [r9+1]
0x180008226  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18000822b  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008232  jz      short loc_180008289
0x180008234  mov     edx, 0CA7h
0x180008239  jmp     short loc_18000827A
0x18000823b  mov     eax, [rdi+0D8h]
0x180008241  cmp     eax, 0FFFFFFFFh
0x180008244  jz      short loc_18000825B
0x180008246  cmp     eax, 2
0x180008249  jz      short loc_18000825B
0x18000824b  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008252  jz      short loc_180008289
0x180008254  mov     edx, 0C06h
0x180008259  jmp     short loc_18000827A
0x18000825b  xor     r9d, r9d
0x18000825e  mov     r8d, esi
0x180008261  mov     edx, r14d
0x180008264  mov     rcx, rdi
0x180008267  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18000826c  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008273  jz      short loc_180008289
0x180008275  mov     edx, 0C0Fh; unsigned int
0x18000827a  mov     r9, [rdi+48h]
0x18000827e  mov     ecx, esi; unsigned int
0x180008280  mov     r8, [rdi+28h]
0x180008284  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180008289  cmp     [rdi+0E4h], r13d
0x180008290  jnz     short loc_1800082FB
0x180008292  cmp     [rdi+0D4h], r13d
0x180008299  jnz     short loc_1800082FB
0x18000829b  mov     eax, [rdi+0E0h]
0x1800082a1  test    r15b, al
0x1800082a4  jz      short loc_1800082FB
0x1800082a6  xor     r9d, r9d
0x1800082a9  mov     r8d, r14d
0x1800082ac  mov     rcx, rdi
0x1800082af  test    al, 10h
0x1800082b1  jz      short loc_1800082CA
0x1800082b3  mov     edx, esi
0x1800082b5  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x1800082ba  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x1800082c1  jz      short loc_1800082EF
0x1800082c3  mov     edx, 0C05h
0x1800082c8  jmp     short loc_1800082E0
0x1800082ca  mov     edx, r14d
0x1800082cd  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x1800082d2  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x1800082d9  jz      short loc_1800082EF
0x1800082db  mov     edx, 0C04h; unsigned int
0x1800082e0  mov     r9, [rdi+48h]
0x1800082e4  mov     ecx, esi; unsigned int
0x1800082e6  mov     r8, [rdi+28h]
0x1800082ea  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800082ef  mov     [rdi+180h], r14d
0x1800082f6  jmp     loc_1800084A5
0x1800082fb  mov     eax, [rdi+0E0h]
0x180008301  test    r15b, al
0x180008304  setnz   cl
0x180008307  bt      eax, 8
0x18000830b  setb    al
0x18000830e  test    al, cl
0x180008310  jz      loc_1800084A5
0x180008316  mov     eax, [rdi+0CCh]
0x18000831c  test    eax, eax
0x18000831e  jz      loc_1800084A5
0x180008324  cmp     [rdi+0C0h], eax
0x18000832a  jnb     short loc_180008364
0x18000832c  xor     r9d, r9d
0x18000832f  mov     edx, r15d
0x180008332  mov     rcx, rdi
0x180008335  lea     r8d, [r9+8]
0x180008339  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18000833e  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180008345  jz      loc_1800084A5
0x18000834b  mov     edx, 0C08h; unsigned int
0x180008350  mov     ecx, esi; unsigned int
0x180008352  mov     r8, [rdi+28h]
0x180008356  mov     r9, [rdi+48h]
0x18000835a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000835f  jmp     loc_1800084A5
  ... truncated ...
```
