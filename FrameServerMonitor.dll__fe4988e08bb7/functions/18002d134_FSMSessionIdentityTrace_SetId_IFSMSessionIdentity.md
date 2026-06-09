# FSMSessionIdentityTrace::SetId(IFSMSessionIdentity *)

- ea: `0x18002d134`
- end: `0x18002d57e`
- name: `?SetId@FSMSessionIdentityTrace@@QEAAXPEAUIFSMSessionIdentity@@@Z`
- size: `1098`
- prototype: `void __fastcall(FSMSessionIdentityTrace *__hidden this, struct IFSMSessionIdentity *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d084`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x18002d0b0`
- `0x18002d134`
- `0x18002d584`
- `0x18002d680`
- `0x18002fba4`
- `0x18004d010`

## string_xrefs

- `0x18002d20d`: `token=0x%p,pid=%d,sessionid=%d,type=%s`
- `0x18002d3a8`: `,settingsbroker`
- `0x18002d467`: `,sidstring=%ws`
- `0x18002d4cb`: `,apppackagesid=%ws`

## pseudocode

```c
void __fastcall FSMSessionIdentityTrace::SetId(FSMSessionIdentityTrace *this, struct IFSMSessionIdentity *a2)
{
  unsigned int v4; // eax
  const char *FSSessionTypeName; // rsi
  int v6; // edi
  int v7; // ebx
  const void *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int v13; // [rsp+28h] [rbp-D8h]
  size_t cbDest; // [rsp+50h] [rbp-B0h] BYREF
  STRSAFE_LPSTR v15; // [rsp+58h] [rbp-A8h] BYREF
  char pszDest[272]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(pszDest, 0, 0x104u);
  cbDest = 260;
  v15 = pszDest;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 280LL))(a2);
    FSSessionTypeName = (const char *)GetFSSessionTypeName(v4);
    v6 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 352LL))(a2);
    v7 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 360LL))(a2);
    v8 = (const void *)(*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 272LL))(a2);
    if ( (int)StringCchPrintfExA(
                pszDest,
                0x104u,
                &v15,
                &cbDest,
                0,
                "token=0x%p,pid=%d,sessionid=%d,type=%s",
                v8,
                v7,
                v6,
                FSSessionTypeName) >= 0
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 288LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",admin", &v15, &cbDest, v13) >= 0)
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 296LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",localsystem", &v15, &cbDest, v13) >= 0)
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 304LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",frameserver", &v15, &cbDest, v13) >= 0)
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 312LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",settingsapp", &v15, &cbDest, v13) >= 0)
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 320LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",appcontainer", &v15, &cbDest, v13) >= 0)
      && (!(*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 392LL))(a2)
       || (int)StringCchCatExA(v15, cbDest, ",settingsbroker", &v15, &cbDest, v13) >= 0) )
    {
      if ( !(*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 328LL))(a2)
        || (v9 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 328LL))(a2),
            (int)StringCchPrintfExA(v15, cbDest, &v15, &cbDest, 0, ",pfn=%ws", v9) >= 0) )
      {
        if ( !(*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 336LL))(a2)
          || (v10 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 336LL))(a2),
              (int)StringCchPrintfExA(v15, cbDest, &v15, &cbDest, 0, ",sidstring=%ws", v10) >= 0) )
        {
          if ( !(*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 344LL))(a2)
            || (v11 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 344LL))(a2),
                (int)StringCchPrintfExA(v15, cbDest, &v15, &cbDest, 0, ",apppackagesid=%ws", v11) >= 0) )
          {
            if ( !(*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 368LL))(a2)
              || (v12 = (*(__int64 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a2 + 368LL))(a2),
                  (int)StringCchPrintfExA(v15, cbDest, &v15, &cbDest, 0, ",processname=%ws", v12) >= 0) )
            {
              FSString::SetString(this, pszDest);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18002d134  mov     [rsp-8+arg_10], rbx
0x18002d139  mov     [rsp-8+arg_18], rsi
0x18002d13e  push    rbp
0x18002d13f  push    rdi
0x18002d140  push    r13
0x18002d142  push    r14
0x18002d144  push    r15
0x18002d146  lea     rbp, [rsp-80h]
0x18002d14b  sub     rsp, 180h
0x18002d152  mov     rax, cs:__security_cookie
0x18002d159  xor     rax, rsp
0x18002d15c  mov     [rbp+0A0h+var_30], rax
0x18002d160  mov     r14, rdx
0x18002d163  mov     r15, rcx
0x18002d166  mov     r13d, 104h
0x18002d16c  lea     rcx, [rsp+1A0h+pszDest]; void *
0x18002d171  mov     r8d, r13d; Size
0x18002d174  xor     edx, edx; Val
0x18002d176  call    memset_0
0x18002d17b  mov     [rsp+1A0h+cbDest], r13
0x18002d180  lea     rax, [rsp+1A0h+pszDest]
0x18002d185  mov     [rsp+1A0h+var_148], rax
0x18002d18a  test    r14, r14
0x18002d18d  jz      loc_18002D556
0x18002d193  mov     rax, [r14]
0x18002d196  mov     rcx, r14
0x18002d199  mov     rax, [rax+118h]
0x18002d1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1a5  mov     ecx, eax
0x18002d1a7  call    GetFSSessionTypeName
0x18002d1ac  mov     rcx, [r14]
0x18002d1af  mov     rsi, rax
0x18002d1b2  mov     rax, [rcx+160h]
0x18002d1b9  mov     rcx, r14
0x18002d1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c1  mov     rcx, [r14]
0x18002d1c4  mov     edi, eax
0x18002d1c6  mov     rax, [rcx+168h]
0x18002d1cd  mov     rcx, r14
0x18002d1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1d5  mov     rcx, [r14]
0x18002d1d8  mov     ebx, eax
0x18002d1da  mov     rax, [rcx+110h]
0x18002d1e1  mov     rcx, r14
0x18002d1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1e9  mov     [rsp+1A0h+var_158], rsi
0x18002d1ee  lea     r9, [rsp+1A0h+cbDest]; unsigned __int64 *
0x18002d1f3  mov     [rsp+1A0h+var_160], edi
0x18002d1f7  lea     r8, [rsp+1A0h+var_148]; char **
0x18002d1fc  mov     [rsp+1A0h+var_168], ebx
0x18002d200  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x18002d205  mov     [rsp+1A0h+var_170], rax
0x18002d20a  mov     edx, r13d; cbDest
0x18002d20d  lea     rax, aToken0xPPidDSe; "token=0x%p,pid=%d,sessionid=%d,type=%s"
0x18002d214  mov     [rsp+1A0h+var_178], rax; unsigned int
0x18002d219  mov     qword ptr [rsp+1A0h+dwFlags], 0; dwFlags
0x18002d222  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18002d227  test    eax, eax
0x18002d229  js      loc_18002D556
0x18002d22f  mov     rax, [r14]
0x18002d232  mov     rcx, r14
0x18002d235  mov     rax, [rax+120h]
0x18002d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d241  test    al, al
0x18002d243  jz      short loc_18002D272
0x18002d245  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d24a  lea     rax, [rsp+1A0h+cbDest]
0x18002d24f  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d254  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d259  lea     r8, aAdmin; ",admin"
0x18002d260  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d265  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d26a  test    eax, eax
0x18002d26c  js      loc_18002D556
0x18002d272  mov     rax, [r14]
0x18002d275  mov     rcx, r14
0x18002d278  mov     rax, [rax+128h]
0x18002d27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d284  test    al, al
0x18002d286  jz      short loc_18002D2B5
0x18002d288  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d28d  lea     rax, [rsp+1A0h+cbDest]
0x18002d292  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d297  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d29c  lea     r8, aLocalsystem; ",localsystem"
0x18002d2a3  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d2a8  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d2ad  test    eax, eax
0x18002d2af  js      loc_18002D556
0x18002d2b5  mov     rax, [r14]
0x18002d2b8  mov     rcx, r14
0x18002d2bb  mov     rax, [rax+130h]
0x18002d2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c7  test    al, al
0x18002d2c9  jz      short loc_18002D2F8
0x18002d2cb  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d2d0  lea     rax, [rsp+1A0h+cbDest]
0x18002d2d5  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d2da  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d2df  lea     r8, aFrameserver; ",frameserver"
0x18002d2e6  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d2eb  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d2f0  test    eax, eax
0x18002d2f2  js      loc_18002D556
0x18002d2f8  mov     rax, [r14]
0x18002d2fb  mov     rcx, r14
0x18002d2fe  mov     rax, [rax+138h]
0x18002d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d30a  test    al, al
0x18002d30c  jz      short loc_18002D33B
0x18002d30e  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d313  lea     rax, [rsp+1A0h+cbDest]
0x18002d318  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d31d  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d322  lea     r8, aSettingsapp_0; ",settingsapp"
0x18002d329  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d32e  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d333  test    eax, eax
0x18002d335  js      loc_18002D556
0x18002d33b  mov     rax, [r14]
0x18002d33e  mov     rcx, r14
0x18002d341  mov     rax, [rax+140h]
0x18002d348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d34d  test    al, al
0x18002d34f  jz      short loc_18002D37E
0x18002d351  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d356  lea     rax, [rsp+1A0h+cbDest]
0x18002d35b  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d360  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d365  lea     r8, aAppcontainer; ",appcontainer"
0x18002d36c  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d371  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d376  test    eax, eax
0x18002d378  js      loc_18002D556
0x18002d37e  mov     rax, [r14]
0x18002d381  mov     rcx, r14
0x18002d384  mov     rax, [rax+188h]
0x18002d38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d390  test    al, al
0x18002d392  jz      short loc_18002D3C1
0x18002d394  mov     rdx, [rsp+1A0h+cbDest]; unsigned __int64
0x18002d399  lea     rax, [rsp+1A0h+cbDest]
0x18002d39e  mov     rcx, [rsp+1A0h+var_148]; char *
0x18002d3a3  lea     r9, [rsp+1A0h+var_148]; char **
0x18002d3a8  lea     r8, aSettingsbroker; ",settingsbroker"
0x18002d3af  mov     qword ptr [rsp+1A0h+dwFlags], rax; unsigned __int64 *
0x18002d3b4  call    ?StringCchCatExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCatExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18002d3b9  test    eax, eax
0x18002d3bb  js      loc_18002D556
0x18002d3c1  mov     rax, [r14]
0x18002d3c4  mov     rcx, r14
0x18002d3c7  mov     rax, [rax+148h]
0x18002d3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3d3  test    rax, rax
0x18002d3d6  jz      short loc_18002D425
0x18002d3d8  mov     rax, [r14]
0x18002d3db  mov     rcx, r14
0x18002d3de  mov     rax, [rax+148h]
0x18002d3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3ea  mov     rdx, [rsp+1A0h+cbDest]; cbDest
0x18002d3ef  lea     r9, [rsp+1A0h+cbDest]; unsigned __int64 *
0x18002d3f4  mov     rcx, [rsp+1A0h+var_148]; pszDest
0x18002d3f9  lea     r8, [rsp+1A0h+var_148]; char **
0x18002d3fe  mov     [rsp+1A0h+var_170], rax
0x18002d403  lea     rax, aPfnWs; ",pfn=%ws"
0x18002d40a  mov     [rsp+1A0h+var_178], rax; char *
0x18002d40f  mov     qword ptr [rsp+1A0h+dwFlags], 0; dwFlags
0x18002d418  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18002d41d  test    eax, eax
0x18002d41f  js      loc_18002D556
0x18002d425  mov     rax, [r14]
0x18002d428  mov     rcx, r14
0x18002d42b  mov     rax, [rax+150h]
0x18002d432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d437  test    rax, rax
0x18002d43a  jz      short loc_18002D489
0x18002d43c  mov     rax, [r14]
0x18002d43f  mov     rcx, r14
0x18002d442  mov     rax, [rax+150h]
0x18002d449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d44e  mov     rdx, [rsp+1A0h+cbDest]; cbDest
0x18002d453  lea     r9, [rsp+1A0h+cbDest]; unsigned __int64 *
0x18002d458  mov     rcx, [rsp+1A0h+var_148]; pszDest
0x18002d45d  lea     r8, [rsp+1A0h+var_148]; char **
0x18002d462  mov     [rsp+1A0h+var_170], rax
0x18002d467  lea     rax, aSidstringWs; ",sidstring=%ws"
0x18002d46e  mov     [rsp+1A0h+var_178], rax; char *
0x18002d473  mov     qword ptr [rsp+1A0h+dwFlags], 0; dwFlags
0x18002d47c  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18002d481  test    eax, eax
0x18002d483  js      loc_18002D556
0x18002d489  mov     rax, [r14]
0x18002d48c  mov     rcx, r14
0x18002d48f  mov     rax, [rax+158h]
0x18002d496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d49b  test    rax, rax
0x18002d49e  jz      short loc_18002D4E9
0x18002d4a0  mov     rax, [r14]
0x18002d4a3  mov     rcx, r14
0x18002d4a6  mov     rax, [rax+158h]
0x18002d4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4b2  mov     rdx, [rsp+1A0h+cbDest]; cbDest
0x18002d4b7  lea     r9, [rsp+1A0h+cbDest]; unsigned __int64 *
0x18002d4bc  mov     rcx, [rsp+1A0h+var_148]; pszDest
0x18002d4c1  lea     r8, [rsp+1A0h+var_148]; char **
0x18002d4c6  mov     [rsp+1A0h+var_170], rax
0x18002d4cb  lea     rax, aApppackagesidW; ",apppackagesid=%ws"
0x18002d4d2  mov     [rsp+1A0h+var_178], rax; char *
0x18002d4d7  mov     qword ptr [rsp+1A0h+dwFlags], 0; dwFlags
0x18002d4e0  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18002d4e5  test    eax, eax
0x18002d4e7  js      short loc_18002D556
0x18002d4e9  mov     rax, [r14]
0x18002d4ec  mov     rcx, r14
0x18002d4ef  mov     rax, [rax+170h]
0x18002d4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4fb  test    rax, rax
0x18002d4fe  jz      short loc_18002D549
0x18002d500  mov     rax, [r14]
0x18002d503  mov     rcx, r14
0x18002d506  mov     rax, [rax+170h]
0x18002d50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d512  mov     rdx, [rsp+1A0h+cbDest]; cbDest
0x18002d517  lea     r9, [rsp+1A0h+cbDest]; unsigned __int64 *
0x18002d51c  mov     rcx, [rsp+1A0h+var_148]; pszDest
0x18002d521  lea     r8, [rsp+1A0h+var_148]; char **
0x18002d526  mov     [rsp+1A0h+var_170], rax
0x18002d52b  lea     rax, aProcessnameWs; ",processname=%ws"
0x18002d532  mov     [rsp+1A0h+var_178], rax; char *
0x18002d537  mov     qword ptr [rsp+1A0h+dwFlags], 0; dwFlags
0x18002d540  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18002d545  test    eax, eax
0x18002d547  js      short loc_18002D556
0x18002d549  lea     rdx, [rsp+1A0h+pszDest]; char *
0x18002d54e  mov     rcx, r15; this
0x18002d551  call    ?SetString@FSString@@QEAAXPEBD@Z; FSString::SetString(char const *)
0x18002d556  mov     rcx, [rbp+0A0h+var_30]
0x18002d55a  xor     rcx, rsp; StackCookie
0x18002d55d  call    __security_check_cookie
0x18002d562  lea     r11, [rsp+1A0h+var_20]
0x18002d56a  mov     rbx, [r11+40h]
0x18002d56e  mov     rsi, [r11+48h]
0x18002d572  mov     rsp, r11
0x18002d575  pop     r15
0x18002d577  pop     r14
0x18002d579  pop     r13
0x18002d57b  pop     rdi
0x18002d57c  pop     rbp
0x18002d57d  retn
```
