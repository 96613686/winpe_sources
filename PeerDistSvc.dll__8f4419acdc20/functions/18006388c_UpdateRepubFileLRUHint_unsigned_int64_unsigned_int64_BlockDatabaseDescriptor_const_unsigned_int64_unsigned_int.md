# UpdateRepubFileLRUHint(unsigned __int64,unsigned __int64,_BlockDatabaseDescriptor const *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18006388c`
- end: `0x180063c98`
- name: `?UpdateRepubFileLRUHint@@YAK_K0PEBU_BlockDatabaseDescriptor@@000@Z`
- size: `1036`
- prototype: `unsigned int __usercall@<eax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, const struct _BlockDatabaseDescriptor *@<r8>, unsigned __int64@<r9>, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180074d48`
- `0x180074f9c`

## callees

- `0x180008290`
- `0x180008310`
- `0x180028e84`
- `0x18002a918`
- `0x18006388c`
- `0x180093220`
- `0x1800945f0`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180063ab4`
- `ESENT!JetPrepareUpdate` at `0x180063ab4`
- `ESENT!JetSetColumns` at `0x180063ad3`
- `ESENT!JetSetColumns` at `0x180063ad3`
- `ESENT!JetRetrieveColumns` at `0x1800639e5`
- `ESENT!JetRetrieveColumns` at `0x1800639e5`
- `ESENT!JetUpdate` at `0x180063af8`
- `ESENT!JetUpdate` at `0x180063af8`

## pseudocode

```c
__int64 __fastcall UpdateRepubFileLRUHint(
        JET_SESID sesid,
        JET_TABLEID tableid,
        const struct _BlockDatabaseDescriptor *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v6; // r13
  unsigned int First; // eax
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // r10
  unsigned __int64 i; // rsi
  unsigned int v15; // ebx
  JET_ERR v16; // eax
  unsigned int Next; // eax
  CHostedCacheMsgEncoding *v18; // r10
  __int64 v19; // rdx
  void **v20; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v22; // [rsp+48h] [rbp-C0h]
  JET_SESID v23; // [rsp+50h] [rbp-B8h]
  JET_TABLEID v24; // [rsp+58h] [rbp-B0h]
  __int64 v25; // [rsp+60h] [rbp-A8h]
  JET_SETCOLUMN psetcolumn; // [rsp+68h] [rbp-A0h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v28; // [rsp+148h] [rbp+40h] BYREF
  const struct _BlockDatabaseDescriptor *v29; // [rsp+158h] [rbp+50h]

  v29 = a3;
  v6 = a5;
  v23 = sesid;
  v20 = &CFileTableFileRangeIterator::`vftable';
  v22 = a5;
  v28 = 0;
  v24 = tableid;
  v21 = a4;
  First = CFileTableFileRangeIterator::FindFirst((CFileTableFileRangeIterator *)&v20);
  v11 = First;
  if ( First == 1168 )
  {
LABEL_2:
    v11 = 0;
    goto LABEL_3;
  }
  if ( First )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, a4, First);
        goto LABEL_3;
      }
      goto LABEL_4;
    }
    return v11;
  }
  for ( i = a4; ; ++i )
  {
    if ( i > v6 )
      goto LABEL_3;
    memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
    pretrievecolumn.columnid = *((_DWORD *)v29 + 159);
    pretrievecolumn.pvData = &v28;
    pretrievecolumn.cbData = 8;
    pretrievecolumn.itagSequence = 1;
    v15 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 1u);
    if ( v15 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_48;
      }
      v19 = 57;
LABEL_47:
      WPP_SF_d(*((_QWORD *)v18 + 12), v19, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v15);
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        58,
        WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids,
        i,
        v28,
        a6,
        (_DWORD)v20,
        v21,
        v22,
        v23,
        v24,
        v25,
        *(_QWORD *)&psetcolumn.columnid,
        psetcolumn.pvData);
    }
    if ( v28 - 1 <= 1 || v28 >= a6 || a6 - v28 <= 0xA )
      goto LABEL_32;
    *(&psetcolumn.columnid + 1) = 0;
    *(_QWORD *)&psetcolumn.grbit = 0;
    *(_QWORD *)&psetcolumn.err = 0;
    psetcolumn.columnid = *((_DWORD *)v29 + 159);
    psetcolumn.pvData = &a6;
    psetcolumn.cbData = 8;
    psetcolumn.itagSequence = 1;
    v15 = JetPrepareUpdate(sesid, tableid, 4u);
    if ( v15 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_48;
      }
      v19 = 59;
      goto LABEL_47;
    }
    v15 = JetSetColumns(sesid, tableid, &psetcolumn, 1u);
    if ( v15 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_48;
      }
      v19 = 60;
      goto LABEL_47;
    }
    v16 = JetUpdate(sesid, tableid, 0, 0, 0);
    v15 = v16;
    if ( !v16 )
      goto LABEL_32;
    if ( v16 != -1102 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v19 = 61;
        goto LABEL_47;
      }
LABEL_48:
      v11 = TranslateJetError(v15);
      goto LABEL_4;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, 4294966194LL);
    }
LABEL_32:
    Next = CFileTableFileRangeIterator::FindNext((CFileTableFileRangeIterator *)&v20);
    v11 = Next;
    if ( Next == 4053 )
      goto LABEL_2;
    if ( Next )
      break;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        63,
        WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids,
        a4,
        v6,
        Next);
LABEL_3:
      v12 = WPP_GLOBAL_Control;
    }
LABEL_4:
    if ( v12 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v12 + 108) & 4) != 0
      && *((_BYTE *)v12 + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)v12 + 12), 64, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v11);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18006388c  mov     rax, rsp
0x18006388f  mov     [rax+10h], rbx
0x180063893  mov     [rax+20h], rsi
0x180063897  mov     [rax+18h], r8
0x18006389b  push    rbp
0x18006389c  push    r12
0x18006389e  push    r13
0x1800638a0  push    r14
0x1800638a2  push    r15
0x1800638a4  lea     rbp, [rax-38h]
0x1800638a8  sub     rsp, 110h
0x1800638af  mov     r13, [rbp+30h+arg_20]
0x1800638b3  lea     rax, ??_7CFileTableFileRangeIterator@@6B@; const CFileTableFileRangeIterator::`vftable'
0x1800638ba  mov     r12, rcx
0x1800638bd  mov     [rsp+130h+var_E8], rcx
0x1800638c2  lea     rcx, [rsp+130h+var_100]; this
0x1800638c7  mov     [rsp+130h+var_100], rax
0x1800638cc  mov     [rsp+130h+var_F0], r13
0x1800638d1  mov     r14, r9
0x1800638d4  mov     r15, rdx
0x1800638d7  mov     [rbp+30h+arg_0], 0
0x1800638df  mov     [rsp+130h+var_E0], rdx
0x1800638e4  mov     [rsp+130h+var_F8], r9
0x1800638e9  call    ?FindFirst@CFileTableFileRangeIterator@@UEAAKXZ; CFileTableFileRangeIterator::FindFirst(void)
0x1800638ee  mov     ebx, eax
0x1800638f0  cmp     eax, 490h
0x1800638f5  jnz     short loc_180063951
0x1800638f7  xor     ebx, ebx
0x1800638f9  lea     rsi, WPP_GLOBAL_Control
0x180063900  mov     r10, cs:WPP_GLOBAL_Control
0x180063907  cmp     r10, rsi
0x18006390a  jz      short loc_180063932
0x18006390c  test    byte ptr [r10+6Ch], 4
0x180063911  jz      short loc_180063932
0x180063913  cmp     byte ptr [r10+69h], 4
0x180063918  jb      short loc_180063932
0x18006391a  mov     rcx, [r10+60h]
0x18006391e  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063925  mov     edx, 40h ; '@'
0x18006392a  mov     r9d, ebx
0x18006392d  call    WPP_SF_d
0x180063932  lea     r11, [rsp+130h+var_20]
0x18006393a  mov     eax, ebx
0x18006393c  mov     rbx, [r11+38h]
0x180063940  mov     rsi, [r11+48h]
0x180063944  mov     rsp, r11
0x180063947  pop     r15
0x180063949  pop     r14
0x18006394b  pop     r13
0x18006394d  pop     r12
0x18006394f  pop     rbp
0x180063950  retn
0x180063951  test    eax, eax
0x180063953  jz      short loc_180063997
0x180063955  mov     r10, cs:WPP_GLOBAL_Control
0x18006395c  lea     rsi, WPP_GLOBAL_Control
0x180063963  cmp     r10, rsi
0x180063966  jz      short loc_180063932
0x180063968  test    byte ptr [r10+6Ch], 4
0x18006396d  jz      short loc_180063907
0x18006396f  cmp     byte ptr [r10+69h], 1
0x180063974  jb      short loc_180063907
0x180063976  mov     rcx, [r10+60h]
0x18006397a  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063981  mov     edx, 38h ; '8'
0x180063986  mov     dword ptr [rsp+130h+pcbActual], eax
0x18006398a  mov     r9, r14
0x18006398d  call    WPP_SF_qD
0x180063992  jmp     loc_180063900
0x180063997  mov     rsi, r14
0x18006399a  cmp     rsi, r13
0x18006399d  ja      loc_1800638F9
0x1800639a3  mov     rax, [rbp+30h+arg_10]
0x1800639a7  lea     r8, [rbp+30h+pretrievecolumn]; pretrievecolumn
0x1800639ab  xorps   xmm0, xmm0
0x1800639ae  mov     r9d, 1; cretrievecolumn
0x1800639b4  movups  xmmword ptr [rbp+30h+pretrievecolumn.columnid], xmm0
0x1800639b8  mov     rdx, r15; tableid
0x1800639bb  mov     rcx, r12; sesid
0x1800639be  mov     eax, [rax+27Ch]
0x1800639c4  mov     [rbp+30h+pretrievecolumn.columnid], eax
0x1800639c7  lea     rax, [rbp+30h+arg_0]
0x1800639cb  movups  xmmword ptr [rbp+30h+pretrievecolumn.cbData], xmm0
0x1800639cf  mov     [rbp+30h+pretrievecolumn.pvData], rax
0x1800639d3  movups  xmmword ptr [rbp+30h+pretrievecolumn.itagSequence], xmm0
0x1800639d7  mov     [rbp+30h+pretrievecolumn.cbData], 8
0x1800639de  mov     [rbp+30h+pretrievecolumn.itagSequence], 1
0x1800639e5  call    cs:__imp_JetRetrieveColumns
0x1800639eb  mov     ebx, eax
0x1800639ed  test    eax, eax
0x1800639ef  jnz     loc_180063C65
0x1800639f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800639fc  lea     rax, WPP_GLOBAL_Control
0x180063a03  cmp     rcx, rax
0x180063a06  jz      short loc_180063A3C
0x180063a08  test    byte ptr [rcx+6Ch], 4
0x180063a0c  jz      short loc_180063A3C
0x180063a0e  cmp     byte ptr [rcx+69h], 4
0x180063a12  jb      short loc_180063A3C
0x180063a14  mov     rax, [rbp+30h+arg_28]
0x180063a18  lea     edx, [rbx+3Ah]
0x180063a1b  mov     rcx, [rcx+60h]
0x180063a1f  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063a26  mov     [rsp+130h+var_108], rax
0x180063a2b  mov     r9, rsi
0x180063a2e  mov     rax, [rbp+30h+arg_0]
0x180063a32  mov     [rsp+130h+pcbActual], rax
0x180063a37  call    WPP_SF_qqq
0x180063a3c  mov     rcx, [rbp+30h+arg_0]
0x180063a40  lea     rax, [rcx-1]
0x180063a44  cmp     rax, 1
0x180063a48  jbe     loc_180063B46
0x180063a4e  mov     rax, [rbp+30h+arg_28]
0x180063a52  cmp     rcx, rax
0x180063a55  jnb     loc_180063B46
0x180063a5b  sub     rax, rcx
0x180063a5e  cmp     rax, 0Ah
0x180063a62  jbe     loc_180063B46
0x180063a68  mov     rax, [rbp+30h+arg_10]
0x180063a6c  mov     r8d, 4; prep
0x180063a72  mov     rdx, r15; tableid
0x180063a75  mov     dword ptr [rsp+130h+psetcolumn+4], 0
0x180063a7d  mov     rcx, r12; sesid
0x180063a80  mov     qword ptr [rsp+130h+psetcolumn.grbit], 0
0x180063a89  mov     qword ptr [rbp+30h+psetcolumn.err], 0
0x180063a91  mov     eax, [rax+27Ch]
0x180063a97  mov     [rsp+130h+psetcolumn.columnid], eax
0x180063a9b  lea     rax, [rbp+30h+arg_28]
0x180063a9f  mov     [rsp+130h+psetcolumn.pvData], rax
0x180063aa4  mov     [rsp+130h+psetcolumn.cbData], 8
0x180063aac  mov     [rsp+130h+psetcolumn.itagSequence], 1
0x180063ab4  call    cs:__imp_JetPrepareUpdate
0x180063aba  mov     ebx, eax
0x180063abc  test    eax, eax
0x180063abe  jnz     loc_180063BBD
0x180063ac4  lea     r9d, [rax+1]; csetcolumn
0x180063ac8  mov     rdx, r15; tableid
0x180063acb  lea     r8, [rsp+130h+psetcolumn]; psetcolumn
0x180063ad0  mov     rcx, r12; sesid
0x180063ad3  call    cs:__imp_JetSetColumns
0x180063ad9  mov     ebx, eax
0x180063adb  test    eax, eax
0x180063add  jnz     loc_180063B95
0x180063ae3  xor     r9d, r9d; cbBookmark
0x180063ae6  mov     [rsp+130h+pcbActual], 0; pcbActual
0x180063aef  xor     r8d, r8d; pvBookmark
0x180063af2  mov     rdx, r15; tableid
0x180063af5  mov     rcx, r12; sesid
0x180063af8  call    cs:__imp_JetUpdate
0x180063afe  mov     ebx, eax
0x180063b00  test    eax, eax
0x180063b02  jz      short loc_180063B46
0x180063b04  mov     r8d, 0FFFFFBB2h
0x180063b0a  cmp     eax, r8d
0x180063b0d  jnz     short loc_180063B6D
0x180063b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b16  lea     rax, WPP_GLOBAL_Control
0x180063b1d  cmp     rcx, rax
0x180063b20  jz      short loc_180063B46
0x180063b22  test    byte ptr [rcx+6Ch], 4
0x180063b26  jz      short loc_180063B46
0x180063b28  cmp     byte ptr [rcx+69h], 1
0x180063b2c  jb      short loc_180063B46
0x180063b2e  mov     rcx, [rcx+60h]
0x180063b32  mov     r9d, r8d
0x180063b35  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063b3c  mov     edx, 3Eh ; '>'
0x180063b41  call    WPP_SF_d
0x180063b46  lea     rcx, [rsp+130h+var_100]; this
0x180063b4b  call    ?FindNext@CFileTableFileRangeIterator@@UEAAKXZ; CFileTableFileRangeIterator::FindNext(void)
0x180063b50  mov     ebx, eax
0x180063b52  cmp     eax, 0FD5h
0x180063b57  jz      loc_1800638F7
0x180063b5d  test    eax, eax
0x180063b5f  jnz     loc_180063C12
0x180063b65  inc     rsi
0x180063b68  jmp     loc_18006399A
0x180063b6d  mov     r10, cs:WPP_GLOBAL_Control
0x180063b74  lea     rax, WPP_GLOBAL_Control
0x180063b7b  cmp     r10, rax
0x180063b7e  jz      short loc_180063BFD
0x180063b80  test    byte ptr [r10+6Ch], 4
0x180063b85  jz      short loc_180063BFD
0x180063b87  cmp     byte ptr [r10+69h], 1
0x180063b8c  jb      short loc_180063BFD
0x180063b8e  mov     edx, 3Dh ; '='
0x180063b93  jmp     short loc_180063BE3
0x180063b95  mov     r10, cs:WPP_GLOBAL_Control
0x180063b9c  lea     rax, WPP_GLOBAL_Control
0x180063ba3  cmp     r10, rax
0x180063ba6  jz      short loc_180063BFD
0x180063ba8  test    byte ptr [r10+6Ch], 4
0x180063bad  jz      short loc_180063BFD
0x180063baf  cmp     byte ptr [r10+69h], 1
0x180063bb4  jb      short loc_180063BFD
0x180063bb6  mov     edx, 3Ch ; '<'
0x180063bbb  jmp     short loc_180063BE3
0x180063bbd  mov     r10, cs:WPP_GLOBAL_Control
0x180063bc4  lea     rax, WPP_GLOBAL_Control
0x180063bcb  cmp     r10, rax
0x180063bce  jz      short loc_180063BFD
0x180063bd0  test    byte ptr [r10+6Ch], 4
0x180063bd5  jz      short loc_180063BFD
0x180063bd7  cmp     byte ptr [r10+69h], 1
0x180063bdc  jb      short loc_180063BFD
0x180063bde  mov     edx, 3Bh ; ';'
0x180063be3  mov     rcx, [r10+60h]
0x180063be7  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063bee  mov     r9d, ebx
0x180063bf1  call    WPP_SF_d
0x180063bf6  mov     r10, cs:WPP_GLOBAL_Control
0x180063bfd  mov     ecx, ebx; int
0x180063bff  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180063c04  mov     ebx, eax
0x180063c06  lea     rsi, WPP_GLOBAL_Control
0x180063c0d  jmp     loc_180063907
0x180063c12  mov     r10, cs:WPP_GLOBAL_Control
0x180063c19  lea     rsi, WPP_GLOBAL_Control
0x180063c20  cmp     r10, rsi
0x180063c23  jz      loc_180063932
0x180063c29  test    byte ptr [r10+6Ch], 4
0x180063c2e  jz      loc_180063907
0x180063c34  cmp     byte ptr [r10+69h], 1
0x180063c39  jb      loc_180063907
0x180063c3f  mov     rcx, [r10+60h]
0x180063c43  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063c4a  mov     dword ptr [rsp+130h+var_108], eax
0x180063c4e  mov     edx, 3Fh ; '?'
0x180063c53  mov     r9, r14
0x180063c56  mov     [rsp+130h+pcbActual], r13
0x180063c5b  call    WPP_SF_qqD
0x180063c60  jmp     loc_180063900
0x180063c65  mov     r10, cs:WPP_GLOBAL_Control
0x180063c6c  lea     rax, WPP_GLOBAL_Control
0x180063c73  cmp     r10, rax
0x180063c76  jz      short loc_180063BFD
0x180063c78  test    byte ptr [r10+6Ch], 4
0x180063c7d  jz      loc_180063BFD
0x180063c83  cmp     byte ptr [r10+69h], 1
0x180063c88  jb      loc_180063BFD
0x180063c8e  mov     edx, 39h ; '9'
0x180063c93  jmp     loc_180063BE3
```
