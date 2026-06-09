# TieringJetSession::GetRecordCount(ulong *)

- ea: `0x140019e70`
- end: `0x14001a048`
- name: `?GetRecordCount@TieringJetSession@@QEAAJPEAK@Z`
- size: `472`
- prototype: `__int64 __fastcall(TieringJetSession *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ef74`

## callees

- `0x140002db0`
- `0x140009c08`
- `0x140019e70`
- `0x14003fbb0`

## import_xrefs

- `ESENT!JetComputeStats` at `0x140019eab`
- `ESENT!JetComputeStats` at `0x140019eab`
- `ESENT!JetGetObjectInfoW` at `0x140019f83`
- `ESENT!JetGetObjectInfoW` at `0x140019f83`

## pseudocode

```c
__int64 __fastcall TieringJetSession::GetRecordCount(TieringJetSession *this, unsigned int *a2)
{
  JET_TABLEID v3; // rdx
  JET_SESID v5; // rcx
  JET_ERR v6; // eax
  JET_ERR v7; // r8d
  unsigned int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  JET_ERR ObjectInfoW; // eax
  int v14; // eax
  _OWORD pvResult[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+60h] [rbp-18h]

  v3 = *((_QWORD *)this + 3);
  v5 = *((_QWORD *)this + 1);
  memset(pvResult, 0, sizeof(pvResult));
  v16 = 0;
  v6 = JetComputeStats(v5, v3);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 == -529 || v6 == -1092 || v6 == -1808 )
    {
      v8 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v6 == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v9 = -v6;
      if ( v9 < 0 )
        LOWORD(v9) = v7;
      v8 = v7 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 120;
LABEL_15:
    WPP_SF_Sd(
      v10[2],
      v11,
      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v7);
    return v8;
  }
  ObjectInfoW = JetGetObjectInfoW(
                  *((_QWORD *)this + 1),
                  *((_DWORD *)this + 4),
                  1u,
                  0,
                  *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 88LL),
                  pvResult,
                  0x28u,
                  0);
  v7 = ObjectInfoW;
  if ( ObjectInfoW )
  {
    if ( ObjectInfoW == -529 || ObjectInfoW == -1092 || ObjectInfoW == -1808 )
    {
      v8 = ATL::AtlHresultFromWin32(112);
    }
    else if ( ObjectInfoW == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v14 = -ObjectInfoW;
      if ( v14 < 0 )
        LOWORD(v14) = v7;
      v8 = v7 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 121;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 5) + 96LL) == 1 && (_DWORD)v16 )
    *a2 = v16 - 1;
  else
    *a2 = v16;
  return 0;
}

```

## disassembly

```asm
0x140019e70  mov     [rsp+arg_10], rbx
0x140019e75  push    rdi
0x140019e76  sub     rsp, 70h
0x140019e7a  mov     rax, cs:__security_cookie
0x140019e81  xor     rax, rsp
0x140019e84  mov     [rsp+78h+var_10], rax
0x140019e89  xorps   xmm0, xmm0
0x140019e8c  mov     rbx, rdx
0x140019e8f  mov     rdx, [rcx+18h]; tableid
0x140019e93  mov     rdi, rcx
0x140019e96  mov     rcx, [rcx+8]; sesid
0x140019e9a  xor     eax, eax
0x140019e9c  movups  [rsp+78h+var_38], xmm0
0x140019ea1  mov     [rsp+78h+var_18], rax
0x140019ea6  movups  [rsp+78h+var_28], xmm0
0x140019eab  call    cs:__imp_JetComputeStats
0x140019eb1  mov     r8d, eax
0x140019eb4  test    eax, eax
0x140019eb6  jz      loc_140019F4E
0x140019ebc  cmp     eax, 0FFFFFDEFh
0x140019ec1  jz      short loc_140019EFA
0x140019ec3  cmp     eax, 0FFFFFBBCh
0x140019ec8  jz      short loc_140019EFA
0x140019eca  cmp     eax, 0FFFFF8F0h
0x140019ecf  jz      short loc_140019EFA
0x140019ed1  cmp     eax, 0FFFFFC0Dh
0x140019ed6  jnz     short loc_140019EDF
0x140019ed8  mov     ebx, 8007000Eh
0x140019edd  jmp     short loc_140019F06
0x140019edf  neg     eax
0x140019ee1  cmovs   eax, r8d
0x140019ee5  movzx   ebx, ax
0x140019ee8  mov     eax, r8d
0x140019eeb  and     eax, 8E5E0000h
0x140019ef0  or      ebx, eax
0x140019ef2  or      ebx, 0E5E0000h
0x140019ef8  jmp     short loc_140019F06
0x140019efa  mov     ecx, 70h ; 'p'; unsigned int
0x140019eff  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140019f04  mov     ebx, eax
0x140019f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f0d  lea     rax, WPP_GLOBAL_Control
0x140019f14  cmp     rcx, rax
0x140019f17  jz      short loc_140019F47
0x140019f19  test    byte ptr [rcx+1Ch], 1
0x140019f1d  jz      short loc_140019F47
0x140019f1f  cmp     byte ptr [rcx+19h], 2
0x140019f23  jb      short loc_140019F47
0x140019f25  mov     edx, 78h ; 'x'
0x140019f2a  mov     r9, [rdi+28h]
0x140019f2e  mov     rcx, [rcx+10h]
0x140019f32  mov     dword ptr [rsp+78h+szObjectName], r8d
0x140019f37  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x140019f3e  mov     r9, [r9+70h]
0x140019f42  call    WPP_SF_Sd
0x140019f47  mov     eax, ebx
0x140019f49  jmp     loc_14001A02D
0x140019f4e  mov     rax, [rdi+28h]
0x140019f52  lea     rcx, [rsp+78h+var_38]
0x140019f57  mov     edx, [rdi+10h]; dbid
0x140019f5a  xor     r9d, r9d; szContainerName
0x140019f5d  mov     [rsp+78h+InfoLevel], 0; InfoLevel
0x140019f65  mov     [rsp+78h+cbMax], 28h ; '('; cbMax
0x140019f6d  mov     rax, [rax+58h]
0x140019f71  mov     [rsp+78h+pvResult], rcx; pvResult
0x140019f76  lea     r8d, [r9+1]; objtyp
0x140019f7a  mov     rcx, [rdi+8]; sesid
0x140019f7e  mov     [rsp+78h+szObjectName], rax; szObjectName
0x140019f83  call    cs:__imp_JetGetObjectInfoW
0x140019f89  mov     r8d, eax
0x140019f8c  test    eax, eax
0x140019f8e  jz      short loc_14001A00F
0x140019f90  cmp     eax, 0FFFFFDEFh
0x140019f95  jz      short loc_140019FCE
0x140019f97  cmp     eax, 0FFFFFBBCh
0x140019f9c  jz      short loc_140019FCE
0x140019f9e  cmp     eax, 0FFFFF8F0h
0x140019fa3  jz      short loc_140019FCE
0x140019fa5  cmp     eax, 0FFFFFC0Dh
0x140019faa  jnz     short loc_140019FB3
0x140019fac  mov     ebx, 8007000Eh
0x140019fb1  jmp     short loc_140019FDA
0x140019fb3  neg     eax
0x140019fb5  cmovs   eax, r8d
0x140019fb9  movzx   ebx, ax
0x140019fbc  mov     eax, r8d
0x140019fbf  and     eax, 8E5E0000h
0x140019fc4  or      ebx, eax
0x140019fc6  or      ebx, 0E5E0000h
0x140019fcc  jmp     short loc_140019FDA
0x140019fce  mov     ecx, 70h ; 'p'; unsigned int
0x140019fd3  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140019fd8  mov     ebx, eax
0x140019fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fe1  lea     rax, WPP_GLOBAL_Control
0x140019fe8  cmp     rcx, rax
0x140019feb  jz      loc_140019F47
0x140019ff1  test    byte ptr [rcx+1Ch], 1
0x140019ff5  jz      loc_140019F47
0x140019ffb  cmp     byte ptr [rcx+19h], 2
0x140019fff  jb      loc_140019F47
0x14001a005  mov     edx, 79h ; 'y'
0x14001a00a  jmp     loc_140019F2A
0x14001a00f  mov     rax, [rdi+28h]
0x14001a013  mov     rcx, [rsp+78h+var_18]
0x14001a018  cmp     dword ptr [rax+60h], 1
0x14001a01c  jnz     short loc_14001A029
0x14001a01e  test    ecx, ecx
0x14001a020  jz      short loc_14001A029
0x14001a022  lea     eax, [rcx-1]
0x14001a025  mov     [rbx], eax
0x14001a027  jmp     short loc_14001A02B
0x14001a029  mov     [rbx], ecx
0x14001a02b  xor     eax, eax
0x14001a02d  mov     rcx, [rsp+78h+var_10]
0x14001a032  xor     rcx, rsp; StackCookie
0x14001a035  call    __security_check_cookie
0x14001a03a  mov     rbx, [rsp+78h+arg_10]
0x14001a042  add     rsp, 70h
0x14001a046  pop     rdi
0x14001a047  retn
```
