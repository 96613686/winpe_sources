# TieringHeatSession::GetSpaceUsedForTier(bool,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140029840`
- end: `0x140029b3b`
- name: `?GetSpaceUsedForTier@TieringHeatSession@@QEAAJ_NPEA_K1@Z`
- size: `763`
- prototype: `__int64 __fastcall(TieringHeatSession *this, char, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003e49c`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14002866c`
- `0x140029840`
- `0x14002b95c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x140029a03`
- `ntdll!RtlCompareMemory` at `0x140029a03`
- `ESENT!JetMove` at `0x1400298bb`
- `ESENT!JetMove` at `0x140029a93`
- `ESENT!JetMove` at `0x1400298bb`
- `ESENT!JetMove` at `0x140029a93`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetSpaceUsedForTier(
        TieringHeatSession *this,
        char a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  JET_TABLEID v8; // rdx
  JET_SESID v9; // rcx
  JET_ERR v10; // eax
  JET_ERR v11; // r8d
  unsigned int v12; // ebx
  int v13; // eax
  JET_ERR CurrentHeatRecord; // eax
  bool v15; // zf
  _QWORD *v16; // rcx
  int v17; // edx
  unsigned __int8 v19; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v20[3]; // [rsp+51h] [rbp-2Fh] BYREF
  unsigned __int16 v21; // [rsp+54h] [rbp-2Ch] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+60h] [rbp-20h]
  __int128 Source1; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::GetSpaceUsedForTier";
  CHResultImp::CHResultImp((CHResultImp *)v22);
  *a3 = 0;
  *a4 = 0;
  v8 = *((_QWORD *)this + 3);
  v9 = *((_QWORD *)this + 1);
  v23 = 0;
  v10 = JetMove(v9, v8, 0x80000000, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( ((v10 + 1603) & 0xFFFFFFFD) != 0 )
    {
      if ( v10 == -529 || v10 == -1092 || v10 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v10 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v13 = -v10;
        if ( v13 < 0 )
          LOWORD(v13) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
      }
      v23 = v12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v11);
      }
    }
    else
    {
      v12 = 0;
      v23 = 0;
    }
    goto LABEL_42;
  }
  v20[0] = 0;
  v21 = 0;
  Source1 = 0;
  v19 = 0;
  while ( 1 )
  {
    CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                          this,
                          1u,
                          (struct TE_FILE_ID_128 *)&Source1,
                          0,
                          v20,
                          &v19,
                          0,
                          &v21,
                          0);
    if ( CurrentHeatRecord == -1017 )
      goto LABEL_33;
    if ( CurrentHeatRecord )
      break;
    if ( RtlCompareMemory(&Source1, &NullGuid, 0x10u) != 16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          v20[0],
          *((_QWORD *)&Source1 + 1),
          Source1,
          v20[0],
          v19,
          v21);
      }
      if ( a2 )
      {
        if ( (v19 & 8) == 0 )
        {
          v15 = (v20[0] & 0x50) == 0;
          goto LABEL_31;
        }
      }
      else if ( (v19 & 4) == 0 )
      {
        v15 = (v20[0] & 0x60) == 0;
LABEL_31:
        if ( !v15 )
          *a4 += v21;
        goto LABEL_33;
      }
      *a3 += v21;
    }
LABEL_33:
    CurrentHeatRecord = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    if ( CurrentHeatRecord == -1603 )
      goto LABEL_41;
    if ( CurrentHeatRecord && CurrentHeatRecord != -1017 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 113;
LABEL_40:
        WPP_SF_Sd(
          v16[2],
          v17,
          (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          CurrentHeatRecord);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 111;
    goto LABEL_40;
  }
LABEL_41:
  v12 = 0;
LABEL_42:
  CHResultImp::~CHResultImp((CHResultImp *)v22);
  return v12;
}

```

## disassembly

```asm
0x140029840  mov     [rsp-28h+arg_8], rbx
0x140029845  push    rbp
0x140029846  push    rsi
0x140029847  push    rdi
0x140029848  push    r14
0x14002984a  push    r15
0x14002984c  mov     rbp, rsp
0x14002984f  sub     rsp, 80h
0x140029856  mov     rax, cs:__security_cookie
0x14002985d  xor     rax, rsp
0x140029860  mov     [rbp+var_8], rax
0x140029864  mov     rax, gs:58h
0x14002986d  mov     rsi, rcx
0x140029870  mov     ecx, 8
0x140029875  mov     r14, r9
0x140029878  mov     rbx, r8
0x14002987b  mov     r15b, dl
0x14002987e  mov     r10, [rax]
0x140029881  lea     rax, aTieringheatses_0; "TieringHeatSession::GetSpaceUsedForTier"
0x140029888  mov     [rcx+r10], rax
0x14002988c  lea     rcx, [rbp+var_28]; this
0x140029890  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140029895  mov     qword ptr [rbx], 0
0x14002989c  xor     r9d, r9d; grbit
0x14002989f  mov     qword ptr [r14], 0
0x1400298a6  mov     r8d, 80000000h; cRow
0x1400298ac  mov     rdx, [rsi+18h]; tableid
0x1400298b0  mov     rcx, [rsi+8]; sesid
0x1400298b4  mov     [rbp+var_20], 0
0x1400298bb  call    cs:__imp_JetMove
0x1400298c1  mov     r8d, eax
0x1400298c4  test    eax, eax
0x1400298c6  jz      loc_140029987
0x1400298cc  lea     ecx, [rax+643h]
0x1400298d2  test    ecx, 0FFFFFFFDh
0x1400298d8  jz      loc_14002997D
0x1400298de  cmp     eax, 0FFFFFDEFh
0x1400298e3  jz      short loc_14002991C
0x1400298e5  cmp     eax, 0FFFFFBBCh
0x1400298ea  jz      short loc_14002991C
0x1400298ec  cmp     eax, 0FFFFF8F0h
0x1400298f1  jz      short loc_14002991C
0x1400298f3  cmp     eax, 0FFFFFC0Dh
0x1400298f8  jnz     short loc_140029901
0x1400298fa  mov     ebx, 8007000Eh
0x1400298ff  jmp     short loc_140029928
0x140029901  neg     eax
0x140029903  cmovs   eax, r8d
0x140029907  movzx   ebx, ax
0x14002990a  mov     eax, r8d
0x14002990d  and     eax, 8E5E0000h
0x140029912  or      ebx, eax
0x140029914  or      ebx, 0E5E0000h
0x14002991a  jmp     short loc_140029928
0x14002991c  mov     ecx, 70h ; 'p'; unsigned int
0x140029921  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140029926  mov     ebx, eax
0x140029928  mov     [rbp+var_20], ebx
0x14002992b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029932  lea     rdi, WPP_GLOBAL_Control
0x140029939  cmp     rcx, rdi
0x14002993c  jz      loc_140029AEE
0x140029942  test    byte ptr [rcx+1Ch], 1
0x140029946  jz      loc_140029AEE
0x14002994c  cmp     byte ptr [rcx+19h], 2
0x140029950  jb      loc_140029AEE
0x140029956  mov     r9, [rsi+28h]
0x14002995a  mov     edx, 6Eh ; 'n'
0x14002995f  mov     rcx, [rcx+10h]
0x140029963  mov     dword ptr [rsp+80h+var_60], r8d
0x140029968  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002996f  mov     r9, [r9+70h]
0x140029973  call    WPP_SF_Sd
0x140029978  jmp     loc_140029AEE
0x14002997d  xor     ebx, ebx
0x14002997f  mov     [rbp+var_20], ebx
0x140029982  jmp     loc_140029AEE
0x140029987  xor     eax, eax
0x140029989  mov     [rbp+var_2F], 0
0x14002998d  xorps   xmm0, xmm0
0x140029990  mov     [rbp+var_2C], ax
0x140029994  movups  [rbp+Source1], xmm0
0x140029998  mov     [rbp+var_30], 0
0x14002999c  lea     rdi, WPP_GLOBAL_Control
0x1400299a3  mov     [rsp+80h+var_40], 0; unsigned __int16 *
0x1400299ac  lea     rax, [rbp+var_2C]
0x1400299b0  mov     [rsp+80h+var_48], rax; unsigned __int16 *
0x1400299b5  lea     r8, [rbp+Source1]; struct TE_FILE_ID_128 *
0x1400299b9  lea     rax, [rbp+var_30]
0x1400299bd  mov     [rsp+80h+var_50], 0; unsigned __int8 *
0x1400299c6  mov     [rsp+80h+var_58], rax; unsigned __int8 *
0x1400299cb  xor     r9d, r9d; __int64 *
0x1400299ce  lea     rax, [rbp+var_2F]
0x1400299d2  mov     dl, 1; bool
0x1400299d4  mov     rcx, rsi; this
0x1400299d7  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x1400299dc  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x1400299e1  cmp     eax, 0FFFFFC07h
0x1400299e6  jz      loc_140029A84
0x1400299ec  test    eax, eax
0x1400299ee  jnz     loc_140029B1C
0x1400299f4  lea     r8d, [rax+10h]; Length
0x1400299f8  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x1400299ff  lea     rcx, [rbp+Source1]; Source1
0x140029a03  call    cs:__imp_RtlCompareMemory
0x140029a09  cmp     rax, 10h
0x140029a0d  jz      short loc_140029A84
0x140029a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a16  cmp     rcx, rdi
0x140029a19  jz      short loc_140029A57
0x140029a1b  test    byte ptr [rcx+1Ch], 1
0x140029a1f  jz      short loc_140029A57
0x140029a21  cmp     byte ptr [rcx+19h], 5
0x140029a25  jb      short loc_140029A57
0x140029a27  movzx   eax, [rbp+var_2C]
0x140029a2b  movzx   edx, [rbp+var_30]
0x140029a2f  movzx   r8d, [rbp+var_2F]
0x140029a34  mov     r9, qword ptr [rbp+Source1+8]
0x140029a38  mov     rcx, [rcx+10h]
0x140029a3c  mov     dword ptr [rsp+80h+var_48], eax
0x140029a40  mov     rax, qword ptr [rbp+Source1]
0x140029a44  mov     dword ptr [rsp+80h+var_50], edx
0x140029a48  mov     dword ptr [rsp+80h+var_58], r8d
0x140029a4d  mov     [rsp+80h+var_60], rax
0x140029a52  call    WPP_SF_iiDDD
0x140029a57  test    r15b, r15b
0x140029a5a  jz      short loc_140029A68
0x140029a5c  test    [rbp+var_30], 8
0x140029a60  jnz     short loc_140029A6E
0x140029a62  test    [rbp+var_2F], 50h
0x140029a66  jmp     short loc_140029A7B
0x140029a68  test    [rbp+var_30], 4
0x140029a6c  jz      short loc_140029A77
0x140029a6e  movzx   eax, [rbp+var_2C]
0x140029a72  add     [rbx], rax
0x140029a75  jmp     short loc_140029A84
0x140029a77  test    [rbp+var_2F], 60h
0x140029a7b  jz      short loc_140029A84
0x140029a7d  movzx   eax, [rbp+var_2C]
0x140029a81  add     [r14], rax
0x140029a84  mov     rdx, [rsi+18h]; tableid
0x140029a88  xor     r9d, r9d; grbit
0x140029a8b  mov     rcx, [rsi+8]; sesid
0x140029a8f  lea     r8d, [r9+1]; cRow
0x140029a93  call    cs:__imp_JetMove
0x140029a99  cmp     eax, 0FFFFF9BDh
0x140029a9e  jz      short loc_140029AEC
0x140029aa0  test    eax, eax
0x140029aa2  jz      loc_1400299A3
0x140029aa8  cmp     eax, 0FFFFFC07h
0x140029aad  jz      loc_1400299A3
0x140029ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x140029aba  cmp     rcx, rdi
0x140029abd  jz      short loc_140029AEC
0x140029abf  test    byte ptr [rcx+1Ch], 1
0x140029ac3  jz      short loc_140029AEC
0x140029ac5  cmp     byte ptr [rcx+19h], 2
0x140029ac9  jb      short loc_140029AEC
0x140029acb  mov     edx, 71h ; 'q'
0x140029ad0  mov     r9, [rsi+28h]
0x140029ad4  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140029adb  mov     rcx, [rcx+10h]
0x140029adf  mov     dword ptr [rsp+80h+var_60], eax
0x140029ae3  mov     r9, [r9+70h]
0x140029ae7  call    WPP_SF_Sd
0x140029aec  xor     ebx, ebx
0x140029aee  lea     rcx, [rbp+var_28]; this
0x140029af2  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140029af7  mov     eax, ebx
0x140029af9  mov     rcx, [rbp+var_8]
0x140029afd  xor     rcx, rsp; StackCookie
0x140029b00  call    __security_check_cookie
0x140029b05  mov     rbx, [rsp+80h+arg_8]
0x140029b0d  add     rsp, 80h
0x140029b14  pop     r15
0x140029b16  pop     r14
0x140029b18  pop     rdi
0x140029b19  pop     rsi
0x140029b1a  pop     rbp
0x140029b1b  retn
0x140029b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029b23  cmp     rcx, rdi
0x140029b26  jz      short loc_140029AEC
0x140029b28  test    byte ptr [rcx+1Ch], 1
0x140029b2c  jz      short loc_140029AEC
0x140029b2e  cmp     byte ptr [rcx+19h], 2
0x140029b32  jb      short loc_140029AEC
0x140029b34  mov     edx, 6Fh ; 'o'
0x140029b39  jmp     short loc_140029AD0
```
