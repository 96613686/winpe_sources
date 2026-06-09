# TieringMovementSession::AddMovementRecord(unsigned __int64,ulong,TE_FILE_ID_128 const *,__int64)

- ea: `0x14001d058`
- end: `0x14001d52e`
- name: `?AddMovementRecord@TieringMovementSession@@QEAAJ_KKPEBUTE_FILE_ID_128@@_J@Z`
- size: `1238`
- prototype: `__int64 __fastcall(TieringMovementSession *this, JET_TABLEID, int, const struct TE_FILE_ID_128 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140031e04`

## callees

- `0x140002323`
- `0x140002db0`
- `0x1400185a0`
- `0x14001d058`
- `0x14001dd94`
- `0x14001dec8`
- `0x14001e018`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001d2dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001d2dc`
- `ESENT!JetSetColumns` at `0x14001d1bf`
- `ESENT!JetSetColumns` at `0x14001d1bf`
- `ESENT!JetPrepareUpdate` at `0x14001d09c`
- `ESENT!JetPrepareUpdate` at `0x14001d0b8`
- `ESENT!JetPrepareUpdate` at `0x14001d0c8`
- `ESENT!JetPrepareUpdate` at `0x14001d237`
- `ESENT!JetPrepareUpdate` at `0x14001d2c9`
- `ESENT!JetPrepareUpdate` at `0x14001d51a`
- `ESENT!JetPrepareUpdate` at `0x14001d09c`
- `ESENT!JetPrepareUpdate` at `0x14001d0b8`
- `ESENT!JetPrepareUpdate` at `0x14001d0c8`
- `ESENT!JetPrepareUpdate` at `0x14001d237`
- `ESENT!JetPrepareUpdate` at `0x14001d2c9`
- `ESENT!JetPrepareUpdate` at `0x14001d51a`
- `ESENT!JetUpdate` at `0x14001d258`
- `ESENT!JetUpdate` at `0x14001d258`

## string_xrefs

- `0x14001d0d0`: `DiskToFlashMovementTable`
- `0x14001d38d`: `FlashToDiskMovementTable`
- `0x14001d444`: `FlashToDiskMovementTable`
- `0x14001d4c6`: `FlashToDiskMovementTable`

## pseudocode

```c
__int64 __fastcall TieringMovementSession::AddMovementRecord(
        TieringMovementSession *this,
        JET_TABLEID a2,
        int a3,
        const struct TE_FILE_ID_128 *a4,
        __int64 a5)
{
  JET_ERR v9; // ebx
  const char *v10; // r15
  const char *v11; // r8
  _UNKNOWN **v12; // r10
  _UNKNOWN **v13; // rdx
  bool v14; // zf
  __int64 v15; // rcx
  int v16; // eax
  JET_SESID v17; // rcx
  JET_ERR v18; // eax
  unsigned int v19; // esi
  int v21; // eax
  const char *v22; // rax
  int v23; // [rsp+50h] [rbp-81h] BYREF
  __int64 v24; // [rsp+58h] [rbp-79h] BYREF
  JET_SETCOLUMN psetcolumn; // [rsp+60h] [rbp-71h] BYREF
  int v26; // [rsp+88h] [rbp-49h]
  const struct TE_FILE_ID_128 *v27; // [rsp+90h] [rbp-41h]
  int v28; // [rsp+98h] [rbp-39h]
  int v29; // [rsp+B0h] [rbp-21h]
  __int64 *v30; // [rsp+B8h] [rbp-19h]
  int v31; // [rsp+C0h] [rbp-11h]

  do
  {
    while ( 1 )
    {
      v9 = JetPrepareUpdate(*((_QWORD *)this + 1), a2, 0);
      if ( v9 == -1607 )
      {
        JetPrepareUpdate(*((_QWORD *)this + 1), a2, 3u);
        v9 = JetPrepareUpdate(*((_QWORD *)this + 1), a2, 0);
      }
      v10 = "DiskToFlashMovementTable";
      v11 = "UnknownTable";
      if ( v9 )
        break;
      v24 = a5;
      v23 = a3;
      memset_0(&psetcolumn, 0, 0x78u);
      v14 = a2 == *((_QWORD *)this + 2);
      v15 = 32;
      psetcolumn.cbData = 4;
      v27 = a4;
      v28 = 16;
      v31 = 8;
      if ( !v14 )
        v15 = 44;
      psetcolumn.columnid = *(_DWORD *)((char *)this + v15);
      psetcolumn.pvData = &v23;
      v26 = *(_DWORD *)((char *)this + v15 + 4);
      v16 = *(_DWORD *)((char *)this + v15 + 8);
      v17 = *((_QWORD *)this + 1);
      v29 = v16;
      v30 = &v24;
      v18 = JetSetColumns(v17, a2, &psetcolumn, 3u);
      v9 = v18;
      if ( v18 == -1605 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( a2 == *((_QWORD *)this + 3) )
          {
            v22 = "DiskToFlashMovementTable";
          }
          else
          {
            v22 = "FlashToDiskMovementTable";
            if ( a2 != *((_QWORD *)this + 2) )
              v22 = "UnknownTable";
          }
          WPP_SF_iiiLsZL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_QWORD *)a4,
            a5,
            a3,
            (__int64)v22,
            *(_QWORD *)this + 696LL,
            187);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), a2, 3u);
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
        v19 = 0;
        goto LABEL_34;
      }
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
            *((_QWORD *)a4 + 1),
            *(_QWORD *)a4,
            *(_QWORD *)this + 696LL,
            v18);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), a2, 3u);
        goto LABEL_25;
      }
      v9 = JetUpdate(*((_QWORD *)this + 1), a2, 0, 0, 0);
      if ( !v9 )
        goto LABEL_25;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
          *((_QWORD *)a4 + 1),
          *(_QWORD *)a4,
          *(_QWORD *)this + 696LL,
          v9);
      }
      JetPrepareUpdate(*((_QWORD *)this + 1), a2, 3u);
      if ( v9 != -1102 )
      {
        if ( v9 == -1605 )
        {
          v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
          v19 = 0;
          goto LABEL_34;
        }
        goto LABEL_25;
      }
      Sleep(0x64u);
    }
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v13 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *((_QWORD *)a4 + 1),
        *(_QWORD *)a4,
        *(_QWORD *)this + 696LL,
        v9);
LABEL_25:
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v13 = &WPP_GLOBAL_Control;
      v11 = "UnknownTable";
    }
  }
  while ( v9 == -1102 );
  v19 = 0;
  if ( v9 )
  {
    if ( v9 == -529 || v9 == -1092 || v9 == -1808 )
    {
      v19 = ATL::AtlHresultFromWin32(0x70u);
    }
    else
    {
      if ( v9 == -1011 )
      {
        v19 = -2147024882;
LABEL_47:
        if ( v12 != v13 && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
        {
          if ( a2 != *((_QWORD *)this + 3) )
          {
            v10 = "FlashToDiskMovementTable";
            if ( a2 != *((_QWORD *)this + 2) )
              v10 = v11;
          }
          WPP_SF_iiiLsZd((TRACEHANDLE)v12[2], *(_QWORD *)a4, a5, a3, (__int64)v10, *(_QWORD *)this + 696LL, v19);
        }
        return v19;
      }
      v21 = -v9;
      if ( v9 > 0 )
        LOWORD(v21) = v9;
      v19 = v9 & 0x8E5E0000 | (unsigned __int16)v21 | 0xE5E0000;
    }
    if ( (v19 & 0x80000000) != 0 )
      goto LABEL_47;
  }
LABEL_34:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
  {
    if ( a2 != *((_QWORD *)this + 3) )
    {
      v10 = "FlashToDiskMovementTable";
      if ( a2 != *((_QWORD *)this + 2) )
        v10 = "UnknownTable";
    }
    WPP_SF_iiiLsZ((TRACEHANDLE)v12[2], *(_QWORD *)a4, a5, a3, (__int64)v10, *(_QWORD *)this + 696LL);
  }
  return v19;
}

```

## disassembly

```asm
0x14001d058  mov     [rsp-8+arg_10], rbx
0x14001d05d  push    rbp
0x14001d05e  push    rsi
0x14001d05f  push    rdi
0x14001d060  push    r12
0x14001d062  push    r13
0x14001d064  push    r14
0x14001d066  push    r15
0x14001d068  lea     rbp, [rsp-1Fh]
0x14001d06d  sub     rsp, 0F0h
0x14001d074  mov     rax, cs:__security_cookie
0x14001d07b  xor     rax, rsp
0x14001d07e  mov     [rbp+4Fh+var_40], rax
0x14001d082  mov     rsi, qword ptr [rbp+4Fh+arg_20]
0x14001d086  mov     r12, r9
0x14001d089  mov     r13d, r8d
0x14001d08c  mov     r14, rdx
0x14001d08f  mov     rdi, rcx
0x14001d092  mov     rcx, [rdi+8]; sesid
0x14001d096  xor     r8d, r8d; prep
0x14001d099  mov     rdx, r14; tableid
0x14001d09c  call    cs:__imp_JetPrepareUpdate
0x14001d0a2  mov     ebx, eax
0x14001d0a4  cmp     eax, 0FFFFF9B9h
0x14001d0a9  jnz     short loc_14001D0D0
0x14001d0ab  mov     rcx, [rdi+8]; sesid
0x14001d0af  mov     r8d, 3; prep
0x14001d0b5  mov     rdx, r14; tableid
0x14001d0b8  call    cs:__imp_JetPrepareUpdate
0x14001d0be  mov     rcx, [rdi+8]; sesid
0x14001d0c2  xor     r8d, r8d; prep
0x14001d0c5  mov     rdx, r14; tableid
0x14001d0c8  call    cs:__imp_JetPrepareUpdate
0x14001d0ce  mov     ebx, eax
0x14001d0d0  lea     r15, aDisktoflashmov; "DiskToFlashMovementTable"
0x14001d0d7  lea     r8, aUnknowntable; "UnknownTable"
0x14001d0de  test    ebx, ebx
0x14001d0e0  jz      short loc_14001D149
0x14001d0e2  mov     r10, cs:WPP_GLOBAL_Control
0x14001d0e9  lea     rdx, WPP_GLOBAL_Control
0x14001d0f0  cmp     r10, rdx
0x14001d0f3  jz      loc_14001D304
0x14001d0f9  test    byte ptr [r10+1Ch], 1
0x14001d0fe  jz      loc_14001D304
0x14001d104  cmp     byte ptr [r10+19h], 2
0x14001d109  jb      loc_14001D304
0x14001d10f  mov     rax, [rdi]
0x14001d112  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d119  mov     r9, [r12+8]
0x14001d11e  add     rax, 2B8h
0x14001d124  mov     rcx, [r10+10h]
0x14001d128  mov     edx, 18h
0x14001d12d  mov     dword ptr [rsp+120h+var_F0], ebx
0x14001d131  mov     qword ptr [rsp+120h+var_F8], rax
0x14001d136  mov     rax, [r12]
0x14001d13a  mov     [rsp+120h+pcbActual], rax
0x14001d13f  call    WPP_SF_iiZd
0x14001d144  jmp     loc_14001D2EF
0x14001d149  xor     edx, edx; Val
0x14001d14b  mov     [rbp+4Fh+var_C8], rsi
0x14001d14f  lea     rcx, [rbp+4Fh+psetcolumn]; void *
0x14001d153  mov     [rsp+120h+var_D0], r13d
0x14001d158  lea     r8d, [rdx+78h]; Size
0x14001d15c  call    memset_0
0x14001d161  cmp     r14, [rdi+10h]
0x14001d165  lea     r8, [rbp+4Fh+psetcolumn]; psetcolumn
0x14001d169  mov     ecx, 20h ; ' '
0x14001d16e  mov     [rbp+4Fh+psetcolumn.cbData], 4
0x14001d175  mov     r9d, 3; csetcolumn
0x14001d17b  mov     [rbp+4Fh+var_90], r12
0x14001d17f  mov     rdx, r14; tableid
0x14001d182  mov     [rbp+4Fh+var_88], 10h
0x14001d189  mov     [rbp+4Fh+var_60], 8
0x14001d190  lea     eax, [rcx+0Ch]
0x14001d193  cmovnz  ecx, eax
0x14001d196  mov     eax, [rcx+rdi]
0x14001d199  mov     [rbp+4Fh+psetcolumn.columnid], eax
0x14001d19c  lea     rax, [rsp+120h+var_D0]
0x14001d1a1  mov     [rbp+4Fh+psetcolumn.pvData], rax
0x14001d1a5  mov     eax, [rcx+rdi+4]
0x14001d1a9  mov     [rbp+4Fh+var_98], eax
0x14001d1ac  mov     eax, [rcx+rdi+8]
0x14001d1b0  mov     rcx, [rdi+8]; sesid
0x14001d1b4  mov     [rbp+4Fh+var_70], eax
0x14001d1b7  lea     rax, [rbp+4Fh+var_C8]
0x14001d1bb  mov     [rbp+4Fh+var_68], rax
0x14001d1bf  call    cs:__imp_JetSetColumns
0x14001d1c5  mov     ebx, eax
0x14001d1c7  cmp     eax, 0FFFFF9BBh
0x14001d1cc  jz      loc_14001D487
0x14001d1d2  test    eax, eax
0x14001d1d4  jz      short loc_14001D242
0x14001d1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1dd  lea     rax, WPP_GLOBAL_Control
0x14001d1e4  cmp     rcx, rax
0x14001d1e7  jz      short loc_14001D22A
0x14001d1e9  test    byte ptr [rcx+1Ch], 1
0x14001d1ed  jz      short loc_14001D22A
0x14001d1ef  cmp     byte ptr [rcx+19h], 2
0x14001d1f3  jb      short loc_14001D22A
0x14001d1f5  mov     rax, [rdi]
0x14001d1f8  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d1ff  mov     r9, [r12+8]
0x14001d204  add     rax, 2B8h
0x14001d20a  mov     rcx, [rcx+10h]
0x14001d20e  mov     edx, 1Ah
0x14001d213  mov     dword ptr [rsp+120h+var_F0], ebx
0x14001d217  mov     qword ptr [rsp+120h+var_F8], rax
0x14001d21c  mov     rax, [r12]
0x14001d220  mov     [rsp+120h+pcbActual], rax
0x14001d225  call    WPP_SF_iiZd
0x14001d22a  mov     rcx, [rdi+8]; sesid
0x14001d22e  mov     r8d, 3; prep
0x14001d234  mov     rdx, r14; tableid
0x14001d237  call    cs:__imp_JetPrepareUpdate
0x14001d23d  jmp     loc_14001D2EF
0x14001d242  mov     rcx, [rdi+8]; sesid
0x14001d246  xor     r9d, r9d; cbBookmark
0x14001d249  xor     r8d, r8d; pvBookmark
0x14001d24c  mov     [rsp+120h+pcbActual], 0; pcbActual
0x14001d255  mov     rdx, r14; tableid
0x14001d258  call    cs:__imp_JetUpdate
0x14001d25e  mov     ebx, eax
0x14001d260  test    eax, eax
0x14001d262  jz      loc_14001D2EF
0x14001d268  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d26f  lea     rax, WPP_GLOBAL_Control
0x14001d276  cmp     rcx, rax
0x14001d279  jz      short loc_14001D2BC
0x14001d27b  test    byte ptr [rcx+1Ch], 1
0x14001d27f  jz      short loc_14001D2BC
0x14001d281  cmp     byte ptr [rcx+19h], 2
0x14001d285  jb      short loc_14001D2BC
0x14001d287  mov     rax, [rdi]
0x14001d28a  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d291  mov     r9, [r12+8]
0x14001d296  add     rax, 2B8h
0x14001d29c  mov     rcx, [rcx+10h]
0x14001d2a0  mov     edx, 1Bh
0x14001d2a5  mov     dword ptr [rsp+120h+var_F0], ebx
0x14001d2a9  mov     qword ptr [rsp+120h+var_F8], rax
0x14001d2ae  mov     rax, [r12]
0x14001d2b2  mov     [rsp+120h+pcbActual], rax
0x14001d2b7  call    WPP_SF_iiZd
0x14001d2bc  mov     rcx, [rdi+8]; sesid
0x14001d2c0  mov     r8d, 3; prep
0x14001d2c6  mov     rdx, r14; tableid
0x14001d2c9  call    cs:__imp_JetPrepareUpdate
0x14001d2cf  cmp     ebx, 0FFFFFBB2h
0x14001d2d5  jnz     short loc_14001D2E7
0x14001d2d7  mov     ecx, 64h ; 'd'; dwMilliseconds
0x14001d2dc  call    cs:__imp_Sleep
0x14001d2e2  jmp     loc_14001D092
0x14001d2e7  cmp     ebx, 0FFFFF9BBh
0x14001d2ed  jz      short loc_14001D350
0x14001d2ef  mov     r10, cs:WPP_GLOBAL_Control
0x14001d2f6  lea     rdx, WPP_GLOBAL_Control
0x14001d2fd  lea     r8, aUnknowntable; "UnknownTable"
0x14001d304  cmp     ebx, 0FFFFFBB2h
0x14001d30a  jz      loc_14001D092
0x14001d310  xor     esi, esi
0x14001d312  test    ebx, ebx
0x14001d314  jz      short loc_14001D359
0x14001d316  cmp     ebx, 0FFFFFDEFh
0x14001d31c  jz      loc_14001D40A
0x14001d322  cmp     ebx, 0FFFFFBBCh
0x14001d328  jz      loc_14001D40A
0x14001d32e  cmp     ebx, 0FFFFF8F0h
0x14001d334  jz      loc_14001D40A
0x14001d33a  cmp     ebx, 0FFFFFC0Dh
0x14001d340  jnz     loc_14001D3F0
0x14001d346  mov     esi, 8007000Eh
0x14001d34b  jmp     loc_14001D41E
0x14001d350  mov     r10, cs:WPP_GLOBAL_Control
0x14001d357  xor     esi, esi
0x14001d359  lea     rbx, aUnknowntable; "UnknownTable"
0x14001d360  lea     rax, WPP_GLOBAL_Control
0x14001d367  cmp     r10, rax
0x14001d36a  jz      short loc_14001D3C7
0x14001d36c  test    byte ptr [r10+1Ch], 1
0x14001d371  jz      short loc_14001D3C7
0x14001d373  cmp     byte ptr [r10+19h], 5
0x14001d378  jb      short loc_14001D3C7
0x14001d37a  mov     rax, [rdi]
0x14001d37d  add     rax, 2B8h
0x14001d383  cmp     r14, [rdi+18h]
0x14001d387  jz      short loc_14001D398
0x14001d389  cmp     r14, [rdi+10h]
0x14001d38d  lea     r15, aFlashtodiskmov; "FlashToDiskMovementTable"
0x14001d394  cmovnz  r15, rbx
0x14001d398  mov     r9, [r12+8]
0x14001d39d  mov     rcx, [r10+10h]; LoggerHandle
0x14001d3a1  mov     [rsp+120h+var_E0], rax; __int64
0x14001d3a6  mov     rax, qword ptr [rbp+4Fh+arg_20]
0x14001d3aa  mov     [rsp+120h+var_E8], r15; __int64
0x14001d3af  mov     dword ptr [rsp+120h+var_F0], r13d; char
0x14001d3b4  mov     qword ptr [rsp+120h+var_F8], rax; char
0x14001d3b9  mov     rax, [r12]
0x14001d3bd  mov     [rsp+120h+pcbActual], rax; char
0x14001d3c2  call    WPP_SF_iiiLsZ
0x14001d3c7  mov     eax, esi
0x14001d3c9  mov     rcx, [rbp+4Fh+var_40]
0x14001d3cd  xor     rcx, rsp; StackCookie
0x14001d3d0  call    __security_check_cookie
0x14001d3d5  mov     rbx, [rsp+120h+arg_10]
0x14001d3dd  add     rsp, 0F0h
0x14001d3e4  pop     r15
0x14001d3e6  pop     r14
0x14001d3e8  pop     r13
0x14001d3ea  pop     r12
0x14001d3ec  pop     rdi
0x14001d3ed  pop     rsi
0x14001d3ee  pop     rbp
0x14001d3ef  retn
0x14001d3f0  mov     eax, ebx
0x14001d3f2  neg     eax
0x14001d3f4  cmovs   eax, ebx
0x14001d3f7  and     ebx, 8E5E0000h
0x14001d3fd  movzx   esi, ax
0x14001d400  or      esi, ebx
0x14001d402  or      esi, 0E5E0000h
0x14001d408  jmp     short loc_14001D416
0x14001d40a  mov     ecx, 70h ; 'p'; unsigned int
0x14001d40f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001d414  mov     esi, eax
0x14001d416  test    esi, esi
0x14001d418  jns     loc_14001D359
0x14001d41e  cmp     r10, rdx
0x14001d421  jz      short loc_14001D3C7
0x14001d423  test    byte ptr [r10+1Ch], 1
0x14001d428  jz      short loc_14001D3C7
0x14001d42a  cmp     byte ptr [r10+19h], 2
0x14001d42f  jb      short loc_14001D3C7
0x14001d431  mov     rax, [rdi]
0x14001d434  add     rax, 2B8h
0x14001d43a  cmp     r14, [rdi+18h]
0x14001d43e  jz      short loc_14001D44F
0x14001d440  cmp     r14, [rdi+10h]
0x14001d444  lea     r15, aFlashtodiskmov; "FlashToDiskMovementTable"
0x14001d44b  cmovnz  r15, r8
0x14001d44f  mov     r9, [r12+8]
0x14001d454  mov     rcx, [r10+10h]; LoggerHandle
0x14001d458  mov     dword ptr [rsp+120h+var_D8], esi; char
0x14001d45c  mov     [rsp+120h+var_E0], rax; __int64
0x14001d461  mov     rax, qword ptr [rbp+4Fh+arg_20]
0x14001d465  mov     [rsp+120h+var_E8], r15; __int64
0x14001d46a  mov     dword ptr [rsp+120h+var_F0], r13d; char
0x14001d46f  mov     qword ptr [rsp+120h+var_F8], rax; char
0x14001d474  mov     rax, [r12]
0x14001d478  mov     [rsp+120h+pcbActual], rax; char
0x14001d47d  call    WPP_SF_iiiLsZd
0x14001d482  jmp     loc_14001D3C7
0x14001d487  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d48e  lea     rax, WPP_GLOBAL_Control
0x14001d495  cmp     rcx, rax
0x14001d498  jz      short loc_14001D506
0x14001d49a  test    byte ptr [rcx+1Ch], 1
0x14001d49e  jz      short loc_14001D506
0x14001d4a0  cmp     byte ptr [rcx+19h], 2
0x14001d4a4  jb      short loc_14001D506
0x14001d4a6  mov     rdx, [rdi]
0x14001d4a9  lea     rbx, aUnknowntable; "UnknownTable"
0x14001d4b0  add     rdx, 2B8h
0x14001d4b7  cmp     r14, [rdi+18h]
0x14001d4bb  jnz     short loc_14001D4C2
0x14001d4bd  mov     rax, r15
0x14001d4c0  jmp     short loc_14001D4D1
0x14001d4c2  cmp     r14, [rdi+10h]
0x14001d4c6  lea     rax, aFlashtodiskmov; "FlashToDiskMovementTable"
0x14001d4cd  cmovnz  rax, rbx
0x14001d4d1  mov     r9, [r12+8]
0x14001d4d6  mov     rcx, [rcx+10h]; LoggerHandle
0x14001d4da  mov     dword ptr [rsp+120h+var_D8], 0FFFFF9BBh; char
0x14001d4e2  mov     [rsp+120h+var_E0], rdx; __int64
0x14001d4e7  mov     [rsp+120h+var_E8], rax; __int64
0x14001d4ec  mov     rax, [r12]
0x14001d4f0  mov     dword ptr [rsp+120h+var_F0], r13d; char
0x14001d4f5  mov     qword ptr [rsp+120h+var_F8], rsi; char
0x14001d4fa  mov     [rsp+120h+pcbActual], rax; char
0x14001d4ff  call    WPP_SF_iiiLsZL
0x14001d504  jmp     short loc_14001D50D
0x14001d506  lea     rbx, aUnknowntable; "UnknownTable"
0x14001d50d  mov     rcx, [rdi+8]; sesid
0x14001d511  mov     r8d, 3; prep
0x14001d517  mov     rdx, r14; tableid
0x14001d51a  call    cs:__imp_JetPrepareUpdate
0x14001d520  mov     r10, cs:WPP_GLOBAL_Control
0x14001d527  xor     esi, esi
0x14001d529  jmp     loc_14001D360
```
