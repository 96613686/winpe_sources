# TieringMovementSession::Teardown(void)

- ea: `0x14001dbf0`
- end: `0x14001dd8c`
- name: `?Teardown@TieringMovementSession@@QEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(JET_SESID *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14000bf3c`
- `0x1400164c8`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14001d7ec`
- `0x14001dbf0`
- `0x14001e168`

## import_xrefs

- `ESENT!JetEndSession` at `0x14001dcd4`
- `ESENT!JetEndSession` at `0x14001dcd4`
- `ESENT!JetResetSessionContext` at `0x14001dc8e`
- `ESENT!JetResetSessionContext` at `0x14001dc8e`

## string_xrefs

- `0x14001dc0f`: `TieringMovementSession::Teardown`

## pseudocode

```c
__int64 __fastcall TieringMovementSession::Teardown(JET_SESID *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  JET_SESID v4; // rcx
  JET_ERR v5; // edx
  int v6; // r8d
  JET_ERR v7; // eax
  JET_ERR v8; // r8d
  int v9; // eax
  _BYTE v11[8]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-30h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringMovementSession::Teardown";
  CHResultImp::CHResultImp((CHResultImp *)v11);
  if ( this[1] == -1 )
  {
    v2 = 0;
    v12 = 0;
  }
  else
  {
    v3 = TieringMovementSession::DeleteMovementTables((TieringMovementSession *)this);
    v2 = 0;
    if ( v3 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *(_DWORD *)this + 696,
        v3);
    }
    v4 = this[1];
    v12 = 0;
    v5 = JetResetSessionContext(v4);
    if ( v5
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qZL(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, this[1], *this + 696, v5);
    }
    v7 = JetEndSession(this[1], 0);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 == -529 || v7 == -1092 || v7 == -1808 )
      {
        v2 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v7 == -1011 )
      {
        v2 = -2147024882;
      }
      else
      {
        v9 = -v7;
        if ( v9 < 0 )
          LOWORD(v9) = v8;
        v2 = v8 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
      }
      v12 = v2;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
          *(_DWORD *)this + 696,
          v8);
      }
    }
    else
    {
      this[1] = -1;
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v11);
  return v2;
}

```

## disassembly

```asm
0x14001dbf0  push    rbx
0x14001dbf2  push    rdi
0x14001dbf3  push    r14
0x14001dbf5  push    r15
0x14001dbf7  sub     rsp, 48h
0x14001dbfb  mov     rax, gs:58h
0x14001dc04  mov     rdi, rcx
0x14001dc07  mov     ecx, 8
0x14001dc0c  mov     rdx, [rax]
0x14001dc0f  lea     rax, aTieringmovemen_2; "TieringMovementSession::Teardown"
0x14001dc16  mov     [rcx+rdx], rax
0x14001dc1a  lea     rcx, [rsp+68h+var_38]; this
0x14001dc1f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001dc24  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14001dc29  jnz     short loc_14001DC36
0x14001dc2b  xor     ebx, ebx
0x14001dc2d  mov     [rsp+68h+var_30], ebx
0x14001dc31  jmp     loc_14001DD75
0x14001dc36  mov     rcx, rdi; this
0x14001dc39  call    ?DeleteMovementTables@TieringMovementSession@@QEAAJXZ; TieringMovementSession::DeleteMovementTables(void)
0x14001dc3e  xor     ebx, ebx
0x14001dc40  lea     r14, WPP_GLOBAL_Control
0x14001dc47  mov     r15d, 2B8h
0x14001dc4d  test    eax, eax
0x14001dc4f  jns     short loc_14001DC86
0x14001dc51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc58  cmp     rcx, r14
0x14001dc5b  jz      short loc_14001DC86
0x14001dc5d  test    byte ptr [rcx+1Ch], 1
0x14001dc61  jz      short loc_14001DC86
0x14001dc63  cmp     byte ptr [rcx+19h], 2
0x14001dc67  jb      short loc_14001DC86
0x14001dc69  mov     r9, [rdi]
0x14001dc6c  lea     edx, [rbx+0Ch]
0x14001dc6f  mov     rcx, [rcx+10h]
0x14001dc73  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001dc7a  add     r9, r15
0x14001dc7d  mov     dword ptr [rsp+68h+var_48], eax
0x14001dc81  call    WPP_SF_Zd
0x14001dc86  mov     rcx, [rdi+8]; sesid
0x14001dc8a  mov     [rsp+68h+var_30], ebx
0x14001dc8e  call    cs:__imp_JetResetSessionContext
0x14001dc94  mov     edx, eax
0x14001dc96  test    eax, eax
0x14001dc98  jz      short loc_14001DCCE
0x14001dc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dca1  cmp     rcx, r14
0x14001dca4  jz      short loc_14001DCCE
0x14001dca6  test    byte ptr [rcx+1Ch], 1
0x14001dcaa  jz      short loc_14001DCCE
0x14001dcac  cmp     byte ptr [rcx+19h], 2
0x14001dcb0  jb      short loc_14001DCCE
0x14001dcb2  mov     rax, [rdi]
0x14001dcb5  mov     r9, [rdi+8]
0x14001dcb9  add     rax, r15
0x14001dcbc  mov     rcx, [rcx+10h]
0x14001dcc0  mov     [rsp+68h+var_40], edx
0x14001dcc4  mov     [rsp+68h+var_48], rax
0x14001dcc9  call    WPP_SF_qZL
0x14001dcce  mov     rcx, [rdi+8]; sesid
0x14001dcd2  xor     edx, edx; grbit
0x14001dcd4  call    cs:__imp_JetEndSession
0x14001dcda  mov     r8d, eax
0x14001dcdd  test    eax, eax
0x14001dcdf  jz      loc_14001DD6D
0x14001dce5  cmp     eax, 0FFFFFDEFh
0x14001dcea  jz      short loc_14001DD23
0x14001dcec  cmp     eax, 0FFFFFBBCh
0x14001dcf1  jz      short loc_14001DD23
0x14001dcf3  cmp     eax, 0FFFFF8F0h
0x14001dcf8  jz      short loc_14001DD23
0x14001dcfa  cmp     eax, 0FFFFFC0Dh
0x14001dcff  jnz     short loc_14001DD08
0x14001dd01  mov     ebx, 8007000Eh
0x14001dd06  jmp     short loc_14001DD2F
0x14001dd08  neg     eax
0x14001dd0a  cmovs   eax, r8d
0x14001dd0e  movzx   ebx, ax
0x14001dd11  mov     eax, r8d
0x14001dd14  and     eax, 8E5E0000h
0x14001dd19  or      ebx, eax
0x14001dd1b  or      ebx, 0E5E0000h
0x14001dd21  jmp     short loc_14001DD2F
0x14001dd23  mov     ecx, 70h ; 'p'; unsigned int
0x14001dd28  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001dd2d  mov     ebx, eax
0x14001dd2f  mov     [rsp+68h+var_30], ebx
0x14001dd33  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd3a  cmp     rcx, r14
0x14001dd3d  jz      short loc_14001DD75
0x14001dd3f  test    byte ptr [rcx+1Ch], 1
0x14001dd43  jz      short loc_14001DD75
0x14001dd45  cmp     byte ptr [rcx+19h], 2
0x14001dd49  jb      short loc_14001DD75
0x14001dd4b  mov     r9, [rdi]
0x14001dd4e  mov     edx, 0Eh
0x14001dd53  mov     rcx, [rcx+10h]
0x14001dd57  add     r9, r15
0x14001dd5a  mov     dword ptr [rsp+68h+var_48], r8d
0x14001dd5f  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001dd66  call    WPP_SF_Zd
0x14001dd6b  jmp     short loc_14001DD75
0x14001dd6d  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14001dd75  lea     rcx, [rsp+68h+var_38]; this
0x14001dd7a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001dd7f  mov     eax, ebx
0x14001dd81  add     rsp, 48h
0x14001dd85  pop     r15
0x14001dd87  pop     r14
0x14001dd89  pop     rdi
0x14001dd8a  pop     rbx
0x14001dd8b  retn
```
