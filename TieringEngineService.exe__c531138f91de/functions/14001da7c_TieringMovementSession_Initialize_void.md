# TieringMovementSession::Initialize(void)

- ea: `0x14001da7c`
- end: `0x14001dbe9`
- name: `?Initialize@TieringMovementSession@@QEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(JET_SESID *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400127dc`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14001866c`
- `0x14001da7c`

## import_xrefs

- `ESENT!JetBeginSessionW` at `0x14001dadf`
- `ESENT!JetBeginSessionW` at `0x14001dadf`

## string_xrefs

- `0x14001da9f`: `TieringMovementSession::Initialize`

## pseudocode

```c
__int64 __fastcall TieringMovementSession::Initialize(JET_SESID *this)
{
  unsigned int v2; // ebx
  JET_ERR v3; // eax
  JET_ERR v4; // r8d
  int v5; // eax
  _BYTE v7[8]; // [rsp+30h] [rbp-18h] BYREF
  int v8; // [rsp+38h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringMovementSession::Initialize";
  CHResultImp::CHResultImp((CHResultImp *)v7);
  if ( this[1] == -1 )
  {
    v3 = JetBeginSessionW(*(_QWORD *)(*this + 1176), this + 1, 0, 0);
    v4 = v3;
    if ( v3 )
    {
      if ( v3 == -529 || v3 == -1092 || v3 == -1808 )
      {
        v2 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v3 == -1011 )
      {
        v2 = -2147024882;
      }
      else
      {
        v5 = -v3;
        if ( v5 < 0 )
          LOWORD(v5) = v4;
        v2 = v4 & 0x8E5E0000 | (unsigned __int16)v5 | 0xE5E0000;
      }
      v8 = v2;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
          *(_DWORD *)this + 696,
          v4);
      }
    }
    else
    {
      v2 = 0;
      v8 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
          this[1],
          *this + 696);
      }
    }
  }
  else
  {
    v2 = -2147019873;
    v8 = -2147019873;
  }
  CHResultImp::~CHResultImp((CHResultImp *)v7);
  return v2;
}

```

## disassembly

```asm
0x14001da7c  mov     [rsp+arg_0], rbx
0x14001da81  mov     [rsp+arg_8], rsi
0x14001da86  push    rdi
0x14001da87  sub     rsp, 40h
0x14001da8b  mov     rax, gs:58h
0x14001da94  mov     rsi, rcx
0x14001da97  mov     ecx, 8
0x14001da9c  mov     rdx, [rax]
0x14001da9f  lea     rax, aTieringmovemen_0; "TieringMovementSession::Initialize"
0x14001daa6  mov     [rcx+rdx], rax
0x14001daaa  lea     rcx, [rsp+48h+var_18]; this
0x14001daaf  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001dab4  lea     rdi, [rsi+8]
0x14001dab8  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14001dabc  jz      short loc_14001DACC
0x14001dabe  mov     ebx, 8007139Fh
0x14001dac3  mov     [rsp+48h+var_10], ebx
0x14001dac7  jmp     loc_14001DBCD
0x14001dacc  mov     rcx, [rsi]
0x14001dacf  xor     r9d, r9d; szPassword
0x14001dad2  xor     r8d, r8d; szUserName
0x14001dad5  mov     rdx, rdi; psesid
0x14001dad8  mov     rcx, [rcx+498h]; instance
0x14001dadf  call    cs:__imp_JetBeginSessionW
0x14001dae5  mov     r8d, eax
0x14001dae8  test    eax, eax
0x14001daea  jz      loc_14001DB83
0x14001daf0  cmp     eax, 0FFFFFDEFh
0x14001daf5  jz      short loc_14001DB2E
0x14001daf7  cmp     eax, 0FFFFFBBCh
0x14001dafc  jz      short loc_14001DB2E
0x14001dafe  cmp     eax, 0FFFFF8F0h
0x14001db03  jz      short loc_14001DB2E
0x14001db05  cmp     eax, 0FFFFFC0Dh
0x14001db0a  jnz     short loc_14001DB13
0x14001db0c  mov     ebx, 8007000Eh
0x14001db11  jmp     short loc_14001DB3A
0x14001db13  neg     eax
0x14001db15  cmovs   eax, r8d
0x14001db19  movzx   ebx, ax
0x14001db1c  mov     eax, r8d
0x14001db1f  and     eax, 8E5E0000h
0x14001db24  or      ebx, eax
0x14001db26  or      ebx, 0E5E0000h
0x14001db2c  jmp     short loc_14001DB3A
0x14001db2e  mov     ecx, 70h ; 'p'; unsigned int
0x14001db33  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001db38  mov     ebx, eax
0x14001db3a  mov     [rsp+48h+var_10], ebx
0x14001db3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db45  lea     rax, WPP_GLOBAL_Control
0x14001db4c  cmp     rcx, rax
0x14001db4f  jz      short loc_14001DBCD
0x14001db51  test    byte ptr [rcx+1Ch], 1
0x14001db55  jz      short loc_14001DBCD
0x14001db57  cmp     byte ptr [rcx+19h], 2
0x14001db5b  jb      short loc_14001DBCD
0x14001db5d  mov     r9, [rsi]
0x14001db60  mov     edx, 0Ah
0x14001db65  mov     rcx, [rcx+10h]
0x14001db69  add     r9, 2B8h
0x14001db70  mov     dword ptr [rsp+48h+var_28], r8d
0x14001db75  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001db7c  call    WPP_SF_Zd
0x14001db81  jmp     short loc_14001DBCD
0x14001db83  xor     ebx, ebx
0x14001db85  mov     [rsp+48h+var_10], ebx
0x14001db89  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db90  lea     rax, WPP_GLOBAL_Control
0x14001db97  cmp     rcx, rax
0x14001db9a  jz      short loc_14001DBCD
0x14001db9c  test    byte ptr [rcx+1Ch], 1
0x14001dba0  jz      short loc_14001DBCD
0x14001dba2  cmp     byte ptr [rcx+19h], 4
0x14001dba6  jb      short loc_14001DBCD
0x14001dba8  mov     r8, [rsi]
0x14001dbab  lea     edx, [rbx+0Bh]
0x14001dbae  mov     r9, [rdi]
0x14001dbb1  add     r8, 2B8h
0x14001dbb8  mov     rcx, [rcx+10h]
0x14001dbbc  mov     [rsp+48h+var_28], r8
0x14001dbc1  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001dbc8  call    WPP_SF_qZ
0x14001dbcd  lea     rcx, [rsp+48h+var_18]; this
0x14001dbd2  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001dbd7  mov     rsi, [rsp+48h+arg_8]
0x14001dbdc  mov     eax, ebx
0x14001dbde  mov     rbx, [rsp+48h+arg_0]
0x14001dbe3  add     rsp, 40h
0x14001dbe7  pop     rdi
0x14001dbe8  retn
```
