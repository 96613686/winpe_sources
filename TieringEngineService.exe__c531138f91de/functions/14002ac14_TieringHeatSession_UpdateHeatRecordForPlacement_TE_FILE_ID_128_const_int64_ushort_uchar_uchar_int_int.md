# TieringHeatSession::UpdateHeatRecordForPlacement(TE_FILE_ID_128 const *,__int64,ushort,uchar,uchar,int,int)

- ea: `0x14002ac14`
- end: `0x14002b155`
- name: `?UpdateHeatRecordForPlacement@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JGEEHH@Z`
- size: `1345`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, __int64, unsigned __int16, char, char, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002a8e4`

## callees

- `0x140021018`
- `0x1400210c8`
- `0x14002670c`
- `0x14002866c`
- `0x140029dec`
- `0x14002ac14`
- `0x14002bb90`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002ad91`
- `ntdll!RtlCompareMemory` at `0x14002ad91`
- `ESENT!JetPrepareUpdate` at `0x14002ac56`
- `ESENT!JetPrepareUpdate` at `0x14002ac73`
- `ESENT!JetPrepareUpdate` at `0x14002ac87`
- `ESENT!JetPrepareUpdate` at `0x14002b0bc`
- `ESENT!JetPrepareUpdate` at `0x14002ac56`
- `ESENT!JetPrepareUpdate` at `0x14002ac73`
- `ESENT!JetPrepareUpdate` at `0x14002ac87`
- `ESENT!JetPrepareUpdate` at `0x14002b0bc`
- `ESENT!JetUpdate` at `0x14002b051`
- `ESENT!JetUpdate` at `0x14002b051`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::UpdateHeatRecordForPlacement(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        __int64 a3,
        unsigned __int16 a4,
        char a5,
        char a6,
        int a7,
        int a8)
{
  unsigned int CurrentHeatRecord; // ebx
  _QWORD *v13; // rcx
  int v14; // edx
  __int64 *v15; // r11
  unsigned __int16 v16; // dx
  unsigned __int8 v17; // r9
  char v18; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int8 v19; // [rsp+61h] [rbp-38h] BYREF
  unsigned __int8 v20[6]; // [rsp+62h] [rbp-37h] BYREF
  unsigned __int16 v21; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 v22[2]; // [rsp+70h] [rbp-29h] BYREF
  int v23; // [rsp+74h] [rbp-25h] BYREF
  __int64 v24; // [rsp+78h] [rbp-21h] BYREF
  __int128 Source1; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 v26[8]; // [rsp+90h] [rbp-9h] BYREF

  v21 = a4;
  CurrentHeatRecord = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
  if ( CurrentHeatRecord == -1607 )
  {
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
    CurrentHeatRecord = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
  }
  if ( CurrentHeatRecord )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        CurrentHeatRecord);
    }
    return CurrentHeatRecord;
  }
  v24 = 0;
  v22[0] = 0;
  v19 = 0;
  v20[0] = 0;
  v18 = 0;
  Source1 = 0;
  CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                        this,
                        1u,
                        (struct TE_FILE_ID_128 *)&Source1,
                        &v24,
                        &v19,
                        v20,
                        (unsigned __int8 *)&v18,
                        v22,
                        v26);
  if ( CurrentHeatRecord )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v14 = 56;
    goto LABEL_53;
  }
  if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiiiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        SBYTE8(Source1),
        Source1,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        -107);
    }
LABEL_19:
    CurrentHeatRecord = -107;
LABEL_54:
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
    return CurrentHeatRecord;
  }
  if ( v24 != a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiiiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        a3,
        v24,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        -107);
    }
    goto LABEL_19;
  }
  v15 = (__int64 *)*((_QWORD *)this + 5);
  v16 = v21;
  v17 = a6 | 0x30;
  if ( !a7 )
    v17 = a6 & 0xCF | 0x20;
  a6 = v17;
  if ( (unsigned int)v21 > *(_DWORD *)(*v15 + 320) )
  {
    v16 = *(_WORD *)(*v15 + 320);
    v21 = v16;
  }
  if ( a8 )
  {
    v23 = 0;
    TieringHeatSession::AddCurrentCountAndAgeHistory(this, a2, v24, 0, v18, v16, v17, v26, &v23, 0, 0);
    CurrentHeatRecord = TieringHeatSession::SetCurrentHeatRecord(
                          this,
                          0,
                          0,
                          (unsigned __int8 *)&a5,
                          (unsigned __int8 *)&a6,
                          (unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL),
                          &v21,
                          0);
    if ( CurrentHeatRecord )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v14 = 59;
      goto LABEL_53;
    }
  }
  else
  {
    if ( a5 == v19 && v17 == v20[0] && v22[0] == v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiiDDDS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          v17,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          a3,
          v16,
          a5,
          v17,
          v15[14]);
      }
      CurrentHeatRecord = 0;
      goto LABEL_54;
    }
    v22[0] = v16;
    CurrentHeatRecord = TieringHeatSession::SetCurrentHeatRecord(
                          this,
                          0,
                          0,
                          (unsigned __int8 *)&a5,
                          (unsigned __int8 *)&a6,
                          0,
                          &v21,
                          0);
    if ( CurrentHeatRecord )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v14 = 60;
LABEL_53:
      WPP_SF_iiSd(
        v13[2],
        v14,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        CurrentHeatRecord);
      goto LABEL_54;
    }
  }
  CurrentHeatRecord = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
  if ( CurrentHeatRecord )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v14 = 62;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_iiiDDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      (unsigned __int8)a6,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      a3,
      v21,
      a5,
      a6,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  return 0;
}

```

## disassembly

```asm
0x14002ac14  mov     [rsp-8+arg_10], rbx
0x14002ac19  push    rbp
0x14002ac1a  push    rsi
0x14002ac1b  push    rdi
0x14002ac1c  push    r12
0x14002ac1e  push    r15
0x14002ac20  lea     rbp, [rsp-17h]
0x14002ac25  sub     rsp, 0B0h
0x14002ac2c  mov     rax, cs:__security_cookie
0x14002ac33  xor     rax, rsp
0x14002ac36  mov     [rbp+37h+var_30], rax
0x14002ac3a  mov     rsi, rdx
0x14002ac3d  mov     [rbp+37h+var_68], r9w
0x14002ac42  mov     rdx, [rcx+18h]; tableid
0x14002ac46  mov     r15, r8
0x14002ac49  mov     rdi, rcx
0x14002ac4c  mov     r8d, 2; prep
0x14002ac52  mov     rcx, [rcx+8]; sesid
0x14002ac56  call    cs:__imp_JetPrepareUpdate
0x14002ac5c  mov     ebx, eax
0x14002ac5e  cmp     eax, 0FFFFF9B9h
0x14002ac63  jnz     short loc_14002AC8F
0x14002ac65  mov     rdx, [rdi+18h]; tableid
0x14002ac69  mov     r8d, 3; prep
0x14002ac6f  mov     rcx, [rdi+8]; sesid
0x14002ac73  call    cs:__imp_JetPrepareUpdate
0x14002ac79  mov     rdx, [rdi+18h]; tableid
0x14002ac7d  mov     r8d, 2; prep
0x14002ac83  mov     rcx, [rdi+8]; sesid
0x14002ac87  call    cs:__imp_JetPrepareUpdate
0x14002ac8d  mov     ebx, eax
0x14002ac8f  xor     r12d, r12d
0x14002ac92  test    ebx, ebx
0x14002ac94  jz      short loc_14002ACEE
0x14002ac96  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac9d  lea     rax, WPP_GLOBAL_Control
0x14002aca4  cmp     rcx, rax
0x14002aca7  jz      short loc_14002ACE7
0x14002aca9  test    byte ptr [rcx+1Ch], 1
0x14002acad  jz      short loc_14002ACE7
0x14002acaf  cmp     byte ptr [rcx+19h], 2
0x14002acb3  jb      short loc_14002ACE7
0x14002acb5  mov     rax, [rdi+28h]
0x14002acb9  lea     edx, [r12+37h]
0x14002acbe  mov     r9, [rsi+8]
0x14002acc2  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002acc9  mov     rcx, [rcx+10h]
0x14002accd  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x14002acd1  mov     rax, [rax+70h]
0x14002acd5  mov     [rsp+0D0h+var_A8], rax
0x14002acda  mov     rax, [rsi]
0x14002acdd  mov     [rsp+0D0h+pcbActual], rax
0x14002ace2  call    WPP_SF_iiSd
0x14002ace7  mov     eax, ebx
0x14002ace9  jmp     loc_14002B132
0x14002acee  lea     rax, [rbp+37h+var_40]
0x14002acf2  mov     [rbp+37h+var_58], r12
0x14002acf6  mov     [rsp+0D0h+var_90], rax; unsigned __int16 *
0x14002acfb  lea     r9, [rbp+37h+var_58]; __int64 *
0x14002acff  lea     rax, [rbp+37h+var_60]
0x14002ad03  mov     [rbp+37h+var_60], r12w
0x14002ad08  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x14002ad0d  lea     r8, [rbp+37h+Source1]; struct TE_FILE_ID_128 *
0x14002ad11  lea     rax, [rbp+37h+var_70]
0x14002ad15  mov     [rbp+37h+var_6F], r12b
0x14002ad19  mov     [rsp+0D0h+var_A0], rax; unsigned __int8 *
0x14002ad1e  xorps   xmm0, xmm0
0x14002ad21  lea     rax, [rbp+37h+var_6E]
0x14002ad25  mov     [rbp+37h+var_6E], r12b
0x14002ad29  mov     [rsp+0D0h+var_A8], rax; unsigned __int8 *
0x14002ad2e  mov     dl, 1; bool
0x14002ad30  lea     rax, [rbp+37h+var_6F]
0x14002ad34  mov     [rbp+37h+var_70], r12b
0x14002ad38  mov     rcx, rdi; this
0x14002ad3b  mov     [rsp+0D0h+pcbActual], rax; unsigned __int8 *
0x14002ad40  movups  [rbp+37h+Source1], xmm0
0x14002ad44  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002ad49  mov     ebx, eax
0x14002ad4b  test    eax, eax
0x14002ad4d  jz      short loc_14002AD84
0x14002ad4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad56  lea     rax, WPP_GLOBAL_Control
0x14002ad5d  cmp     rcx, rax
0x14002ad60  jz      loc_14002B0AE
0x14002ad66  test    byte ptr [rcx+1Ch], 1
0x14002ad6a  jz      loc_14002B0AE
0x14002ad70  cmp     byte ptr [rcx+19h], 2
0x14002ad74  jb      loc_14002B0AE
0x14002ad7a  mov     edx, 38h ; '8'
0x14002ad7f  jmp     loc_14002B081
0x14002ad84  mov     r8d, 10h; Length
0x14002ad8a  lea     rcx, [rbp+37h+Source1]; Source1
0x14002ad8e  mov     rdx, rsi; Source2
0x14002ad91  call    cs:__imp_RtlCompareMemory
0x14002ad97  cmp     rax, 10h
0x14002ad9b  jz      short loc_14002AE0E
0x14002ad9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ada4  lea     rax, WPP_GLOBAL_Control
0x14002adab  cmp     rcx, rax
0x14002adae  jz      short loc_14002AE04
0x14002adb0  test    byte ptr [rcx+1Ch], 1
0x14002adb4  jz      short loc_14002AE04
0x14002adb6  cmp     byte ptr [rcx+19h], 2
0x14002adba  jb      short loc_14002AE04
0x14002adbc  mov     rax, [rdi+28h]
0x14002adc0  mov     edx, 39h ; '9'
0x14002adc5  mov     dword ptr [rsp+0D0h+var_90], 0FFFFFF95h
0x14002adcd  mov     rax, [rax+70h]
0x14002add1  mov     [rsp+0D0h+var_98], rax
0x14002add6  mov     rax, qword ptr [rbp+37h+Source1]
0x14002adda  mov     [rsp+0D0h+var_A0], rax
0x14002addf  mov     rax, qword ptr [rbp+37h+Source1+8]
0x14002ade3  mov     [rsp+0D0h+var_A8], rax
0x14002ade8  mov     rax, [rsi]
0x14002adeb  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002adf2  mov     r9, [rsi+8]
0x14002adf6  mov     rcx, [rcx+10h]
0x14002adfa  mov     [rsp+0D0h+pcbActual], rax
0x14002adff  call    WPP_SF_iiiiSd
0x14002ae04  mov     ebx, 0FFFFFF95h
0x14002ae09  jmp     loc_14002B0AE
0x14002ae0e  mov     r8, [rbp+37h+var_58]; __int64
0x14002ae12  cmp     r8, r15
0x14002ae15  jz      short loc_14002AE5C
0x14002ae17  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae1e  lea     rax, WPP_GLOBAL_Control
0x14002ae25  cmp     rcx, rax
0x14002ae28  jz      short loc_14002AE04
0x14002ae2a  test    byte ptr [rcx+1Ch], 1
0x14002ae2e  jz      short loc_14002AE04
0x14002ae30  cmp     byte ptr [rcx+19h], 2
0x14002ae34  jb      short loc_14002AE04
0x14002ae36  mov     rax, [rdi+28h]
0x14002ae3a  mov     edx, 3Ah ; ':'
0x14002ae3f  mov     dword ptr [rsp+0D0h+var_90], 0FFFFFF95h
0x14002ae47  mov     rax, [rax+70h]
0x14002ae4b  mov     [rsp+0D0h+var_98], rax
0x14002ae50  mov     [rsp+0D0h+var_A0], r8
0x14002ae55  mov     [rsp+0D0h+var_A8], r15
0x14002ae5a  jmp     short loc_14002ADE8
0x14002ae5c  mov     cl, [rbp+37h+arg_28]
0x14002ae5f  mov     r11, [rdi+28h]
0x14002ae63  or      cl, 20h
0x14002ae66  movzx   edx, [rbp+37h+var_68]
0x14002ae6a  mov     al, cl
0x14002ae6c  or      cl, 10h
0x14002ae6f  and     al, 0EFh
0x14002ae71  cmp     [rbp+37h+arg_30], r12d
0x14002ae75  movzx   r9d, cl
0x14002ae79  movzx   eax, al
0x14002ae7c  cmovz   r9d, eax
0x14002ae80  mov     [rbp+37h+arg_28], r9b
0x14002ae84  mov     rcx, [r11]
0x14002ae87  cmp     edx, [rcx+140h]
0x14002ae8d  jbe     short loc_14002AE9A
0x14002ae8f  movzx   edx, word ptr [rcx+140h]
0x14002ae96  mov     [rbp+37h+var_68], dx
0x14002ae9a  cmp     [rbp+37h+arg_38], r12d
0x14002ae9e  jz      loc_14002AF5D
0x14002aea4  mov     [rsp+0D0h+var_80], r12; unsigned int *
0x14002aea9  lea     rax, [rbp+37h+var_5C]
0x14002aead  mov     [rsp+0D0h+var_88], r12; unsigned int *
0x14002aeb2  mov     rcx, rdi; this
0x14002aeb5  mov     [rsp+0D0h+var_90], rax; int *
0x14002aeba  lea     rax, [rbp+37h+var_40]
0x14002aebe  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x14002aec3  mov     al, [rbp+37h+var_70]
0x14002aec6  mov     byte ptr [rsp+0D0h+var_A0], r9b; char
0x14002aecb  xor     r9d, r9d; unsigned int
0x14002aece  mov     word ptr [rsp+0D0h+var_A8], dx; unsigned __int16
0x14002aed3  mov     rdx, rsi; struct TE_FILE_ID_128 *
0x14002aed6  mov     [rbp+37h+var_5C], r12d
0x14002aeda  mov     byte ptr [rsp+0D0h+pcbActual], al; char
0x14002aede  call    ?AddCurrentCountAndAgeHistory@TieringHeatSession@@QEAAXPEBUTE_FILE_ID_128@@_JKEGEPEAGPEAHPEAK4@Z; TieringHeatSession::AddCurrentCountAndAgeHistory(TE_FILE_ID_128 const *,__int64,ulong,uchar,ushort,uchar,ushort *,int *,ulong *,ulong *)
0x14002aee3  mov     rax, [rdi+28h]
0x14002aee7  lea     r9, [rbp+37h+arg_20]; unsigned __int8 *
0x14002aeeb  mov     [rsp+0D0h+var_98], r12; unsigned __int16 *
0x14002aef0  xor     r8d, r8d; __int64 *
0x14002aef3  xor     edx, edx; struct TE_FILE_ID_128 *
0x14002aef5  mov     rcx, [rax]
0x14002aef8  lea     rax, [rbp+37h+var_68]
0x14002aefc  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 *
0x14002af01  add     rcx, 148h
0x14002af08  mov     [rsp+0D0h+var_A8], rcx; unsigned __int8 *
0x14002af0d  lea     rax, [rbp+37h+arg_28]
0x14002af11  mov     rcx, rdi; this
0x14002af14  mov     [rsp+0D0h+pcbActual], rax; unsigned __int8 *
0x14002af19  call    ?SetCurrentHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@PEA_JPEAE22PEAG3@Z; TieringHeatSession::SetCurrentHeatRecord(TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002af1e  mov     ebx, eax
0x14002af20  test    eax, eax
0x14002af22  jz      loc_14002B03E
0x14002af28  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af2f  lea     rax, WPP_GLOBAL_Control
0x14002af36  cmp     rcx, rax
0x14002af39  jz      loc_14002B0AE
0x14002af3f  test    byte ptr [rcx+1Ch], 1
0x14002af43  jz      loc_14002B0AE
0x14002af49  cmp     byte ptr [rcx+19h], 2
0x14002af4d  jb      loc_14002B0AE
0x14002af53  mov     edx, 3Bh ; ';'
0x14002af58  jmp     loc_14002B081
0x14002af5d  movzx   r10d, [rbp+37h+arg_20]
0x14002af62  cmp     r10b, [rbp+37h+var_6F]
0x14002af66  jnz     short loc_14002AFDD
0x14002af68  cmp     r9b, [rbp+37h+var_6E]
0x14002af6c  jnz     short loc_14002AFDD
0x14002af6e  cmp     [rbp+37h+var_60], dx
0x14002af72  jnz     short loc_14002AFDD
0x14002af74  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af7b  lea     rax, WPP_GLOBAL_Control
0x14002af82  cmp     rcx, rax
0x14002af85  jz      short loc_14002AFD5
0x14002af87  test    byte ptr [rcx+1Ch], 1
0x14002af8b  jz      short loc_14002AFD5
0x14002af8d  cmp     byte ptr [rcx+19h], 5
0x14002af91  jb      short loc_14002AFD5
0x14002af93  mov     rax, [r11+70h]
0x14002af97  mov     rcx, [rcx+10h]
0x14002af9b  mov     [rsp+0D0h+var_88], rax
0x14002afa0  mov     rax, [rsi]
0x14002afa3  movzx   r8d, r9b
0x14002afa7  mov     r9d, r10d
0x14002afaa  mov     dword ptr [rsp+0D0h+var_90], r8d
0x14002afaf  mov     dword ptr [rsp+0D0h+var_98], r9d
0x14002afb4  mov     r9, [rsi+8]
0x14002afb8  movzx   r10d, dx
0x14002afbc  mov     edx, 3Dh ; '='
0x14002afc1  mov     dword ptr [rsp+0D0h+var_A0], r10d
0x14002afc6  mov     [rsp+0D0h+var_A8], r15
0x14002afcb  mov     [rsp+0D0h+pcbActual], rax
0x14002afd0  call    WPP_SF_iiiDDDS
0x14002afd5  mov     ebx, r12d
0x14002afd8  jmp     loc_14002B0AE
0x14002afdd  mov     [rsp+0D0h+var_98], r12; unsigned __int16 *
0x14002afe2  lea     rax, [rbp+37h+var_68]
0x14002afe6  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 *
0x14002afeb  lea     r9, [rbp+37h+arg_20]; unsigned __int8 *
0x14002afef  lea     rax, [rbp+37h+arg_28]
0x14002aff3  mov     [rbp+37h+var_60], dx
0x14002aff7  mov     [rsp+0D0h+var_A8], r12; unsigned __int8 *
0x14002affc  xor     r8d, r8d; __int64 *
0x14002afff  xor     edx, edx; struct TE_FILE_ID_128 *
0x14002b001  mov     [rsp+0D0h+pcbActual], rax; unsigned __int8 *
0x14002b006  mov     rcx, rdi; this
0x14002b009  call    ?SetCurrentHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@PEA_JPEAE22PEAG3@Z; TieringHeatSession::SetCurrentHeatRecord(TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002b00e  mov     ebx, eax
0x14002b010  test    eax, eax
0x14002b012  jz      short loc_14002B03E
0x14002b014  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b01b  lea     rax, WPP_GLOBAL_Control
0x14002b022  cmp     rcx, rax
0x14002b025  jz      loc_14002B0AE
0x14002b02b  test    byte ptr [rcx+1Ch], 1
0x14002b02f  jz      short loc_14002B0AE
0x14002b031  cmp     byte ptr [rcx+19h], 2
0x14002b035  jb      short loc_14002B0AE
0x14002b037  mov     edx, 3Ch ; '<'
0x14002b03c  jmp     short loc_14002B081
0x14002b03e  mov     rdx, [rdi+18h]; tableid
0x14002b042  xor     r9d, r9d; cbBookmark
0x14002b045  mov     rcx, [rdi+8]; sesid
0x14002b049  xor     r8d, r8d; pvBookmark
0x14002b04c  mov     [rsp+0D0h+pcbActual], r12; pcbActual
0x14002b051  call    cs:__imp_JetUpdate
0x14002b057  mov     ebx, eax
0x14002b059  test    eax, eax
0x14002b05b  jz      short loc_14002B0C7
0x14002b05d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b064  lea     rax, WPP_GLOBAL_Control
0x14002b06b  cmp     rcx, rax
0x14002b06e  jz      short loc_14002B0AE
0x14002b070  test    byte ptr [rcx+1Ch], 1
0x14002b074  jz      short loc_14002B0AE
0x14002b076  cmp     byte ptr [rcx+19h], 2
0x14002b07a  jb      short loc_14002B0AE
0x14002b07c  mov     edx, 3Eh ; '>'
0x14002b081  mov     rax, [rdi+28h]
0x14002b085  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002b08c  mov     r9, [rsi+8]
0x14002b090  mov     rcx, [rcx+10h]
0x14002b094  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x14002b098  mov     rax, [rax+70h]
0x14002b09c  mov     [rsp+0D0h+var_A8], rax
0x14002b0a1  mov     rax, [rsi]
0x14002b0a4  mov     [rsp+0D0h+pcbActual], rax
0x14002b0a9  call    WPP_SF_iiSd
0x14002b0ae  mov     rdx, [rdi+18h]; tableid
0x14002b0b2  mov     r8d, 3; prep
0x14002b0b8  mov     rcx, [rdi+8]; sesid
0x14002b0bc  call    cs:__imp_JetPrepareUpdate
0x14002b0c2  jmp     loc_14002ACE7
0x14002b0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b0ce  lea     rax, WPP_GLOBAL_Control
0x14002b0d5  cmp     rcx, rax
0x14002b0d8  jz      short loc_14002B130
0x14002b0da  test    byte ptr [rcx+1Ch], 1
0x14002b0de  jz      short loc_14002B130
0x14002b0e0  cmp     byte ptr [rcx+19h], 5
0x14002b0e4  jb      short loc_14002B130
0x14002b0e6  movzx   r9d, [rbp+37h+arg_20]
  ... truncated ...
```
