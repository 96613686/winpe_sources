# BackUpRecoveryPasswordOrClearBackupInfo(ushort const *,_GUID const *,_LIST_ENTRY *)

- ea: `0x18003afc8`
- end: `0x18003b54c`
- name: `?BackUpRecoveryPasswordOrClearBackupInfo@@YAXPEBGPEBU_GUID@@PEAU_LIST_ENTRY@@@Z`
- size: `1412`
- prototype: `void __fastcall(const unsigned __int16 *, const struct _GUID *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800289c0`

## callees

- `0x1800016a4`
- `0x1800017cc`
- `0x180001fe8`
- `0x180009f30`
- `0x180009f60`
- `0x180020430`
- `0x180034070`
- `0x18003afc8`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x18003b429`
- `FVEAPI!FveCommitChanges` at `0x18003b429`
- `FVEAPI!FveClearRecoveryPasswordBackupInformation` at `0x18003b2ce`
- `FVEAPI!FveClearRecoveryPasswordBackupInformation` at `0x18003b2ce`
- `FVEAPI!FveBackupRecoveryInformationToAAD` at `0x18003b129`
- `FVEAPI!FveBackupRecoveryInformationToAAD` at `0x18003b273`
- `FVEAPI!FveBackupRecoveryInformationToAAD` at `0x18003b129`
- `FVEAPI!FveBackupRecoveryInformationToAAD` at `0x18003b273`
- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x18003b0f3`
- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x18003b244`
- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x18003b0f3`
- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x18003b244`
- `FVEAPI!FveOpenVolumeW` at `0x18003b093`
- `FVEAPI!FveOpenVolumeW` at `0x18003b093`
- `FVEAPI!FveCloseVolume` at `0x18003b4ef`
- `FVEAPI!FveCloseVolume` at `0x18003b4ef`

## pseudocode

```c
void __fastcall BackUpRecoveryPasswordOrClearBackupInfo(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        struct _LIST_ENTRY *a3)
{
  unsigned int DomainInfo; // eax
  int v7; // ebx
  int v8; // r13d
  unsigned int v9; // eax
  char v10; // r14
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  struct _LIST_ENTRY *Flink; // rsi
  struct _LIST_ENTRY *v17; // rdi
  struct _LIST_ENTRY *v18; // rdx
  int v19; // eax
  int v20; // ebx
  PVOID *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  bool v29; // [rsp+50h] [rbp-19h] BYREF
  int v30; // [rsp+54h] [rbp-15h] BYREF
  int v31; // [rsp+58h] [rbp-11h] BYREF
  int v32; // [rsp+5Ch] [rbp-Dh] BYREF
  int v33; // [rsp+60h] [rbp-9h] BYREF
  int v34; // [rsp+64h] [rbp-5h] BYREF
  __int64 v35; // [rsp+68h] [rbp-1h] BYREF
  __int64 v36; // [rsp+70h] [rbp+7h] BYREF
  __int64 v37; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE v38[8]; // [rsp+80h] [rbp+17h] BYREF

  v37 = -1;
  v38[0] = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  DomainInfo = FveDomain::GetDomainInfo(&v29, 0);
  v7 = DomainInfo;
  if ( DomainInfo )
  {
    v8 = 5994;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, DomainInfo);
    if ( v7 < 0 )
      goto LABEL_68;
  }
  v8 = 6002;
  v34 = 6002;
  v9 = FveOpenVolumeW(a1, 1, &v37);
  v7 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v9);
    if ( v7 < 0 )
      goto LABEL_68;
  }
  v10 = 0;
  if ( !a2 )
    goto LABEL_29;
  if ( v29 )
  {
    v7 = FveBackupRecoveryInformationToADEx(v37, a2, 0);
    if ( v7 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 219;
LABEL_24:
        WPP_SF_d(v11[2], v12, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, (unsigned int)v7);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
LABEL_28:
    v10 = 1;
    goto LABEL_29;
  }
  v7 = FveBackupRecoveryInformationToAAD(v37, a2, 0);
  if ( v7 >= 0 )
    goto LABEL_28;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 220;
    goto LABEL_24;
  }
LABEL_25:
  if ( (unsigned int)dword_18009A348 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
  {
    v33 = v29;
    v36 = 0x1000000;
    v32 = 1;
    v30 = -1;
    v35 = (__int64)a2;
    v31 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v13,
      (int)&byte_18008CAD7,
      v14,
      v15,
      (__int64)&v31,
      &v35,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v36);
  }
LABEL_29:
  if ( !a3 )
    goto LABEL_63;
  Flink = a3->Flink;
  if ( a3->Flink == a3 )
    goto LABEL_63;
  do
  {
    v17 = Flink - 37;
    v18 = Flink - 37;
    if ( BYTE6(Flink[-1].Blink) )
    {
      if ( v29 )
      {
        v19 = FveBackupRecoveryInformationToADEx(v37, v18, 0);
        v20 = v19;
        if ( v19 < 0 )
        {
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 221;
LABEL_41:
            WPP_SF_d(v21[2], v22, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, (unsigned int)v19);
            v21 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_42;
          }
          goto LABEL_42;
        }
      }
      else
      {
        v19 = FveBackupRecoveryInformationToAAD(v37, v18, 0);
        v20 = v19;
        if ( v19 < 0 )
        {
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 222;
            goto LABEL_41;
          }
LABEL_42:
          if ( v20 < 0 )
            goto LABEL_48;
          goto LABEL_57;
        }
      }
LABEL_56:
      v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
      v10 = 1;
      goto LABEL_58;
    }
    v23 = FveClearRecoveryPasswordBackupInformation(v37, v18, 4, v38);
    v20 = v23;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          223,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          (unsigned int)v23);
LABEL_48:
      if ( (unsigned int)dword_18009A348 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
      {
        v31 = BYTE6(v17[36].Blink);
        v30 = v29;
        v33 = (int)v17[1].Flink;
        v35 = 0x1000000;
        v36 = (__int64)&Flink[-37];
        v32 = v20;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v24,
          (int)&unk_18008CA40,
          v25,
          v26,
          (__int64)&v32,
          &v36,
          (__int64)&v33,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v35);
      }
LABEL_55:
      v21 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_58;
    }
    if ( v38[0] )
      goto LABEL_56;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, 0);
      goto LABEL_55;
    }
LABEL_58:
    Flink = Flink->Flink;
  }
  while ( Flink != a3 );
  v8 = v34;
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
    WPP_SF_(v21[2], 225, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v7 = 0;
LABEL_63:
  if ( v10 )
  {
    v8 = 6119;
    v7 = FveCommitChanges(v37);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          226,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          (unsigned int)v7);
    }
  }
LABEL_68:
  if ( (unsigned int)dword_18009A348 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
  {
    v31 = v29;
    v35 = 0x1000000;
    v34 = v8;
    v30 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_18009A348,
      (int)byte_18008C9D9,
      v27,
      v28,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&v34,
      (__int64)&v35);
  }
  if ( v37 != -1 )
  {
    FveCloseVolume(v37);
    v37 = -1;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      227,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      (unsigned int)v7);
}

```

## disassembly

```asm
0x18003afc8  push    rbp
0x18003afca  push    rbx
0x18003afcb  push    rsi
0x18003afcc  push    rdi
0x18003afcd  push    r13
0x18003afcf  push    r14
0x18003afd1  push    r15
0x18003afd3  lea     rbp, [rsp-27h]
0x18003afd8  sub     rsp, 90h
0x18003afdf  mov     rax, cs:__security_cookie
0x18003afe6  xor     rax, rsp
0x18003afe9  mov     [rbp+57h+var_38], rax
0x18003afed  mov     r15, r8
0x18003aff0  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x18003aff8  mov     rdi, rdx
0x18003affb  mov     [rbp+57h+var_40], 0
0x18003afff  mov     rsi, rcx
0x18003b002  mov     [rbp+57h+var_70], 0
0x18003b006  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b00d  lea     r14, WPP_GLOBAL_Control
0x18003b014  cmp     rcx, r14
0x18003b017  jz      short loc_18003B034
0x18003b019  test    byte ptr [rcx+1Ch], 20h
0x18003b01d  jz      short loc_18003B034
0x18003b01f  mov     rcx, [rcx+10h]
0x18003b023  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b02a  mov     edx, 0D8h
0x18003b02f  call    WPP_SF_
0x18003b034  xor     edx, edx; struct _GUID *
0x18003b036  lea     rcx, [rbp+57h+var_70]; bool *
0x18003b03a  call    ?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z; FveDomain::GetDomainInfo(bool *,_GUID *)
0x18003b03f  mov     ebx, eax
0x18003b041  test    eax, eax
0x18003b043  jz      short loc_18003B07D
0x18003b045  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b04c  mov     r13d, 176Ah
0x18003b052  cmp     rcx, r14
0x18003b055  jz      short loc_18003B075
0x18003b057  test    byte ptr [rcx+1Ch], 40h
0x18003b05b  jz      short loc_18003B075
0x18003b05d  mov     rcx, [rcx+10h]
0x18003b061  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b068  mov     edx, 0D9h
0x18003b06d  mov     r9d, eax
0x18003b070  call    WPP_SF_d
0x18003b075  test    ebx, ebx
0x18003b077  js      loc_18003B473
0x18003b07d  mov     r13d, 1772h
0x18003b083  lea     r8, [rbp+57h+var_48]
0x18003b087  mov     edx, 1
0x18003b08c  mov     [rbp+57h+var_5C], r13d
0x18003b090  mov     rcx, rsi
0x18003b093  call    cs:__imp_FveOpenVolumeW
0x18003b09a  nop     dword ptr [rax+rax+00h]
0x18003b09f  mov     ebx, eax
0x18003b0a1  test    eax, eax
0x18003b0a3  jz      short loc_18003B0D7
0x18003b0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0ac  cmp     rcx, r14
0x18003b0af  jz      short loc_18003B0CF
0x18003b0b1  test    byte ptr [rcx+1Ch], 40h
0x18003b0b5  jz      short loc_18003B0CF
0x18003b0b7  mov     rcx, [rcx+10h]
0x18003b0bb  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b0c2  mov     edx, 0DAh
0x18003b0c7  mov     r9d, eax
0x18003b0ca  call    WPP_SF_d
0x18003b0cf  test    ebx, ebx
0x18003b0d1  js      loc_18003B473
0x18003b0d7  xor     r14b, r14b
0x18003b0da  test    rdi, rdi
0x18003b0dd  jz      loc_18003B204
0x18003b0e3  mov     rcx, [rbp+57h+var_48]
0x18003b0e7  xor     r8d, r8d
0x18003b0ea  mov     rdx, rdi
0x18003b0ed  cmp     [rbp+57h+var_70], r14b
0x18003b0f1  jz      short loc_18003B129
0x18003b0f3  call    cs:__imp_FveBackupRecoveryInformationToADEx
0x18003b0fa  nop     dword ptr [rax+rax+00h]
0x18003b0ff  mov     ebx, eax
0x18003b101  test    eax, eax
0x18003b103  jns     loc_18003B201
0x18003b109  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b110  lea     rax, WPP_GLOBAL_Control
0x18003b117  cmp     rcx, rax
0x18003b11a  jz      short loc_18003B170
0x18003b11c  test    byte ptr [rcx+1Ch], 2
0x18003b120  jz      short loc_18003B170
0x18003b122  mov     edx, 0DBh
0x18003b127  jmp     short loc_18003B15D
0x18003b129  call    cs:__imp_FveBackupRecoveryInformationToAAD
0x18003b130  nop     dword ptr [rax+rax+00h]
0x18003b135  mov     ebx, eax
0x18003b137  test    eax, eax
0x18003b139  jns     loc_18003B201
0x18003b13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b146  lea     rax, WPP_GLOBAL_Control
0x18003b14d  cmp     rcx, rax
0x18003b150  jz      short loc_18003B170
0x18003b152  test    byte ptr [rcx+1Ch], 2
0x18003b156  jz      short loc_18003B170
0x18003b158  mov     edx, 0DCh
0x18003b15d  mov     rcx, [rcx+10h]
0x18003b161  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b168  mov     r9d, ebx
0x18003b16b  call    WPP_SF_d
0x18003b170  mov     eax, cs:dword_18009A348
0x18003b176  cmp     eax, 5
0x18003b179  jbe     loc_18003B204
0x18003b17f  mov     rdx, 400000000000h
0x18003b189  lea     rcx, dword_18009A348
0x18003b190  call    _tlgKeywordOn
0x18003b195  test    al, al
0x18003b197  jz      short loc_18003B204
0x18003b199  movzx   eax, [rbp+57h+var_70]
0x18003b19d  lea     rdx, byte_18008CAD7
0x18003b1a4  mov     [rbp+57h+var_60], eax
0x18003b1a7  lea     rax, [rbp+57h+var_50]
0x18003b1ab  mov     [rsp+0C0h+var_78], rax
0x18003b1b0  lea     rax, [rbp+57h+var_64]
0x18003b1b4  mov     [rsp+0C0h+var_80], rax
0x18003b1b9  lea     rax, [rbp+57h+var_60]
0x18003b1bd  mov     [rsp+0C0h+var_88], rax
0x18003b1c2  lea     rax, [rbp+57h+var_6C]
0x18003b1c6  mov     [rsp+0C0h+var_90], rax
0x18003b1cb  lea     rax, [rbp+57h+var_58]
0x18003b1cf  mov     [rsp+0C0h+var_98], rax
0x18003b1d4  lea     rax, [rbp+57h+var_68]
0x18003b1d8  mov     [rsp+0C0h+var_A0], rax
0x18003b1dd  mov     [rbp+57h+var_50], 1000000h
0x18003b1e5  mov     [rbp+57h+var_64], 1
0x18003b1ec  mov     [rbp+57h+var_6C], 0FFFFFFFFh
0x18003b1f3  mov     [rbp+57h+var_58], rdi
0x18003b1f7  mov     [rbp+57h+var_68], ebx
0x18003b1fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003b1ff  jmp     short loc_18003B204
0x18003b201  mov     r14b, 1
0x18003b204  test    r15, r15
0x18003b207  jz      loc_18003B41A
0x18003b20d  mov     rsi, [r15]
0x18003b210  cmp     rsi, r15
0x18003b213  jz      loc_18003B41A
0x18003b219  lea     r13, WPP_GLOBAL_Control
0x18003b220  mov     rcx, [rbp+57h+var_48]
0x18003b224  lea     rdi, [rsi-250h]
0x18003b22b  cmp     byte ptr [rdi+24Eh], 0
0x18003b232  mov     rdx, rdi
0x18003b235  jz      loc_18003B2C4
0x18003b23b  xor     r8d, r8d
0x18003b23e  cmp     [rbp+57h+var_70], r8b
0x18003b242  jz      short loc_18003B273
0x18003b244  call    cs:__imp_FveBackupRecoveryInformationToADEx
0x18003b24b  nop     dword ptr [rax+rax+00h]
0x18003b250  mov     ebx, eax
0x18003b252  test    eax, eax
0x18003b254  jns     loc_18003B3DE
0x18003b25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b261  cmp     rcx, r13
0x18003b264  jz      short loc_18003B2BA
0x18003b266  test    byte ptr [rcx+1Ch], 2
0x18003b26a  jz      short loc_18003B2BA
0x18003b26c  mov     edx, 0DDh
0x18003b271  jmp     short loc_18003B2A0
0x18003b273  call    cs:__imp_FveBackupRecoveryInformationToAAD
0x18003b27a  nop     dword ptr [rax+rax+00h]
0x18003b27f  mov     ebx, eax
0x18003b281  test    eax, eax
0x18003b283  jns     loc_18003B3DE
0x18003b289  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b290  cmp     rcx, r13
0x18003b293  jz      short loc_18003B2BA
0x18003b295  test    byte ptr [rcx+1Ch], 2
0x18003b299  jz      short loc_18003B2BA
0x18003b29b  mov     edx, 0DEh
0x18003b2a0  mov     rcx, [rcx+10h]
0x18003b2a4  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b2ab  mov     r9d, eax
0x18003b2ae  call    WPP_SF_d
0x18003b2b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2ba  test    ebx, ebx
0x18003b2bc  jns     loc_18003B3E5
0x18003b2c2  jmp     short loc_18003B30E
0x18003b2c4  mov     r8d, 4
0x18003b2ca  lea     r9, [rbp+57h+var_40]
0x18003b2ce  call    cs:__imp_FveClearRecoveryPasswordBackupInformation
0x18003b2d5  nop     dword ptr [rax+rax+00h]
0x18003b2da  mov     ebx, eax
0x18003b2dc  test    eax, eax
0x18003b2de  jns     loc_18003B3A5
0x18003b2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2eb  cmp     rcx, r13
0x18003b2ee  jz      short loc_18003B30E
0x18003b2f0  test    byte ptr [rcx+1Ch], 2
0x18003b2f4  jz      short loc_18003B30E
0x18003b2f6  mov     rcx, [rcx+10h]
0x18003b2fa  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b301  mov     edx, 0DFh
0x18003b306  mov     r9d, eax
0x18003b309  call    WPP_SF_d
0x18003b30e  mov     eax, cs:dword_18009A348
0x18003b314  cmp     eax, 5
0x18003b317  jbe     loc_18003B3D5
0x18003b31d  mov     rdx, 400000000000h
0x18003b327  lea     rcx, dword_18009A348
0x18003b32e  call    _tlgKeywordOn
0x18003b333  test    al, al
0x18003b335  jz      loc_18003B3D5
0x18003b33b  movzx   eax, byte ptr [rdi+24Eh]
0x18003b342  lea     rdx, unk_18008CA40
0x18003b349  mov     [rbp+57h+var_68], eax
0x18003b34c  movzx   eax, [rbp+57h+var_70]
0x18003b350  mov     [rbp+57h+var_6C], eax
0x18003b353  mov     eax, [rdi+10h]
0x18003b356  mov     [rbp+57h+var_60], eax
0x18003b359  lea     rax, [rbp+57h+var_58]
0x18003b35d  mov     [rsp+0C0h+var_78], rax
0x18003b362  lea     rax, [rbp+57h+var_68]
0x18003b366  mov     [rsp+0C0h+var_80], rax
0x18003b36b  lea     rax, [rbp+57h+var_6C]
0x18003b36f  mov     [rsp+0C0h+var_88], rax
0x18003b374  lea     rax, [rbp+57h+var_60]
0x18003b378  mov     [rsp+0C0h+var_90], rax
0x18003b37d  lea     rax, [rbp+57h+var_50]
0x18003b381  mov     [rsp+0C0h+var_98], rax
0x18003b386  lea     rax, [rbp+57h+var_64]
0x18003b38a  mov     [rsp+0C0h+var_A0], rax
0x18003b38f  mov     [rbp+57h+var_58], 1000000h
0x18003b397  mov     [rbp+57h+var_50], rdi
0x18003b39b  mov     [rbp+57h+var_64], ebx
0x18003b39e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003b3a3  jmp     short loc_18003B3D5
0x18003b3a5  cmp     [rbp+57h+var_40], 0
0x18003b3a9  jnz     short loc_18003B3DE
0x18003b3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3b2  cmp     rcx, r13
0x18003b3b5  jz      short loc_18003B3E8
0x18003b3b7  test    byte ptr [rcx+1Ch], 4
0x18003b3bb  jz      short loc_18003B3E8
0x18003b3bd  mov     rcx, [rcx+10h]
0x18003b3c1  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b3c8  mov     edx, 0E0h
0x18003b3cd  xor     r9d, r9d
0x18003b3d0  call    WPP_SF_d
0x18003b3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3dc  jmp     short loc_18003B3E8
0x18003b3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3e5  mov     r14b, 1
0x18003b3e8  mov     rsi, [rsi]
0x18003b3eb  cmp     rsi, r15
0x18003b3ee  jnz     loc_18003B220
0x18003b3f4  cmp     rcx, r13
0x18003b3f7  mov     r13d, [rbp+57h+var_5C]
0x18003b3fb  jz      short loc_18003B418
0x18003b3fd  test    byte ptr [rcx+1Ch], 8
0x18003b401  jz      short loc_18003B418
0x18003b403  mov     rcx, [rcx+10h]
0x18003b407  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b40e  mov     edx, 0E1h
0x18003b413  call    WPP_SF_
0x18003b418  xor     ebx, ebx
0x18003b41a  test    r14b, r14b
0x18003b41d  jz      short loc_18003B46C
0x18003b41f  mov     rcx, [rbp+57h+var_48]
0x18003b423  mov     r13d, 17E7h
0x18003b429  call    cs:__imp_FveCommitChanges
0x18003b430  nop     dword ptr [rax+rax+00h]
0x18003b435  mov     ebx, eax
0x18003b437  test    eax, eax
0x18003b439  jz      short loc_18003B46C
0x18003b43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b442  lea     rax, WPP_GLOBAL_Control
0x18003b449  cmp     rcx, rax
0x18003b44c  jz      short loc_18003B46C
0x18003b44e  test    byte ptr [rcx+1Ch], 40h
0x18003b452  jz      short loc_18003B46C
0x18003b454  mov     rcx, [rcx+10h]
0x18003b458  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b45f  mov     edx, 0E2h
0x18003b464  mov     r9d, ebx
0x18003b467  call    WPP_SF_d
0x18003b46c  lea     r14, WPP_GLOBAL_Control
0x18003b473  mov     eax, cs:dword_18009A348
0x18003b479  cmp     eax, 5
0x18003b47c  jbe     short loc_18003B4E5
0x18003b47e  mov     rdx, 400000000000h
0x18003b488  lea     rcx, dword_18009A348
0x18003b48f  call    _tlgKeywordOn
0x18003b494  test    al, al
0x18003b496  jz      short loc_18003B4E5
0x18003b498  movzx   eax, [rbp+57h+var_70]
0x18003b49c  lea     rdx, byte_18008C9D9
0x18003b4a3  mov     [rbp+57h+var_68], eax
0x18003b4a6  lea     rcx, dword_18009A348
0x18003b4ad  lea     rax, [rbp+57h+var_58]
0x18003b4b1  mov     [rbp+57h+var_58], 1000000h
0x18003b4b9  mov     [rsp+0C0h+var_88], rax
0x18003b4be  lea     rax, [rbp+57h+var_5C]
0x18003b4c2  mov     [rsp+0C0h+var_90], rax
0x18003b4c7  lea     rax, [rbp+57h+var_68]
0x18003b4cb  mov     [rsp+0C0h+var_98], rax
  ... truncated ...
```
