# TieringHeatSession::GetHeatRecordsByIndexNumber(ulong,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0007 * *)

- ea: `0x140029268`
- end: `0x140029837`
- name: `?GetHeatRecordsByIndexNumber@TieringHeatSession@@QEAAJKPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0007@@@Z`
- size: `1487`
- prototype: `__int64 __fastcall(TieringHeatSession *this, int cRow, int *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0007 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003d800`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009904`
- `0x140009c08`
- `0x14001cd80`
- `0x14002670c`
- `0x14002866c`
- `0x140029268`
- `0x14002b764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029338`
- `ESENT!JetMove` at `0x1400292d1`
- `ESENT!JetMove` at `0x1400292f5`
- `ESENT!JetMove` at `0x14002950d`
- `ESENT!JetMove` at `0x1400292d1`
- `ESENT!JetMove` at `0x1400292f5`
- `ESENT!JetMove` at `0x14002950d`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetHeatRecordsByIndexNumber(
        TieringHeatSession *this,
        int cRow,
        int *a3,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0007 **a4)
{
  JET_TABLEID v8; // rdx
  JET_SESID v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // r15d
  char *v16; // rbx
  JET_ERR CurrentHeatRecord; // eax
  JET_ERR v18; // ecx
  bool v19; // zf
  __int64 v20; // r8
  int v21; // edx
  char v22; // al
  unsigned int v23; // ecx
  __int64 v24; // rdx
  bool v25; // cf
  _DWORD *v26; // rax
  JET_ERR v27; // eax
  int v28; // r8d
  int v30; // eax
  _QWORD *v31; // rcx
  int v32; // edx
  int v33; // r9d
  int v34; // eax
  int v35; // eax
  unsigned __int8 v36[4]; // [rsp+60h] [rbp-20h] BYREF
  int v37; // [rsp+64h] [rbp-1Ch] BYREF
  _BYTE v38[8]; // [rsp+68h] [rbp-18h] BYREF
  int v39; // [rsp+70h] [rbp-10h]
  char v40; // [rsp+C0h] [rbp+40h] BYREF
  int *v41; // [rsp+D0h] [rbp+50h]
  char v42; // [rsp+D8h] [rbp+58h] BYREF

  v41 = a3;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::GetHeatRecordsByIndexNumber";
  CHResultImp::CHResultImp((CHResultImp *)v38);
  *a3 = 0;
  *a4 = 0;
  v8 = *((_QWORD *)this + 3);
  v9 = *((_QWORD *)this + 1);
  v39 = 0;
  v10 = JetMove(v9, v8, 0x80000000, 0);
  v12 = v10;
  if ( v10 || cRow && (v13 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), cRow, 0), (v12 = v13) != 0) )
  {
    if ( (((_DWORD)v12 + 1603) & 0xFFFFFFFD) != 0 )
    {
      if ( (_DWORD)v12 == -529 || (_DWORD)v12 == -1092 || (_DWORD)v12 == -1808 )
      {
        v14 = ATL::AtlHresultFromWin32(112);
      }
      else if ( (_DWORD)v12 == -1011 )
      {
        v14 = -2147024882;
      }
      else
      {
        v35 = -(int)v12;
        if ( (int)v12 > 0 )
          LOWORD(v35) = v12;
        v14 = v12 & 0x8E5E0000 | (unsigned __int16)v35 | 0xE5E0000;
      }
      v39 = v14;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v12);
      }
      goto LABEL_91;
    }
    v14 = 0;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12);
  }
  *a4 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0007 *)CoTaskMemAlloc(0xC3500u);
  *a3 = 0;
  if ( !*a4 )
  {
    v14 = -2147024882;
    v39 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        10000,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        14);
    }
    goto LABEL_91;
  }
  v15 = 0;
  memset_0(*a4, 0, 0xC3500u);
  v16 = (char *)*a4;
  v36[0] = 0;
  v42 = 0;
  v40 = 0;
  CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                        this,
                        1u,
                        (struct TE_FILE_ID_128 *)v16,
                        (__int64 *)v16 + 2,
                        v36,
                        (unsigned __int8 *)&v42,
                        (unsigned __int8 *)&v40,
                        (unsigned __int16 *)v16 + 16,
                        (unsigned __int16 *)v16 + 18);
  v18 = CurrentHeatRecord;
  if ( CurrentHeatRecord )
  {
    v28 = CurrentHeatRecord;
LABEL_58:
    if ( v28 == -529 || v28 == -1092 || v28 == -1808 )
    {
      v14 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v28 == -1011 )
    {
      v14 = -2147024882;
    }
    else
    {
      v34 = -v28;
      if ( v28 > 0 )
        LOWORD(v34) = v28;
      v14 = v18 & 0x8E5E0000 | (unsigned __int16)v34 | 0xE5E0000;
    }
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_72;
    }
    v32 = 67;
    v33 = cRow;
  }
  else
  {
    while ( 1 )
    {
      v19 = *(_QWORD *)v16 == *(_QWORD *)&NullGuid.Data1;
      v20 = *((_QWORD *)v16 + 2);
      v37 = 0;
      if ( v19 && *((_QWORD *)v16 + 1) == *(_QWORD *)NullGuid.Data4 && !v20 )
      {
        *((_DWORD *)v16 + 7) = 0xFFFF;
        v21 = 0;
      }
      else
      {
        TieringHeatSession::AddCurrentCountAndAgeHistory(
          this,
          (const struct TE_FILE_ID_128 *)v16,
          v20,
          0,
          v40,
          *((_WORD *)v16 + 16),
          v42,
          (unsigned __int16 *)v16 + 18,
          &v37,
          (unsigned int *)v16 + 7,
          0);
        if ( (v42 & 8) != 0 )
        {
          v22 = 1;
        }
        else if ( (v42 & 4) != 0 )
        {
          v22 = 2;
        }
        else
        {
          v23 = *((_DWORD *)v16 + 7);
          v24 = **((_QWORD **)this + 5);
          if ( (v36[0] & 0x10) != 0 )
            v25 = v23 < *(_DWORD *)(v24 + 228);
          else
            v25 = v23 < *(_DWORD *)(v24 + 224);
          v22 = v25 + 1;
        }
        v21 = (unsigned __int8)(v22 | v36[0]) | (((unsigned __int8)v42 | ((unsigned __int8)v40 << 8)) << 8);
        v36[0] |= v22;
      }
      *((_DWORD *)v16 + 6) = v21;
      ++v15;
      v26 = v41;
      *((_WORD *)v16 + 17) = 7;
      *v26 = v15;
      do
      {
        v27 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
        v28 = v27;
      }
      while ( v27 == -1017 );
      if ( ((v27 + 1603) & 0xFFFFFFFD) == 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            v15,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        goto LABEL_39;
      }
      if ( v27 )
        break;
      if ( v15 >= 0x2710 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            v15,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        v39 = 0;
LABEL_39:
        CHResultImp::~CHResultImp((CHResultImp *)v38);
        return 0;
      }
      v16 += 80;
      v36[0] = 0;
      v42 = 0;
      v40 = 0;
      v18 = TieringHeatSession::GetCurrentHeatRecord(
              this,
              1u,
              (struct TE_FILE_ID_128 *)v16,
              (__int64 *)v16 + 2,
              v36,
              (unsigned __int8 *)&v42,
              (unsigned __int8 *)&v40,
              (unsigned __int16 *)v16 + 16,
              (unsigned __int16 *)v16 + 18);
      v28 = v18;
      if ( v18 )
        goto LABEL_58;
    }
    if ( v27 == -529 || v27 == -1092 || v27 == -1808 )
    {
      v14 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v27 == -1011 )
    {
      v14 = -2147024882;
    }
    else
    {
      v30 = -v27;
      if ( v30 < 0 )
        LOWORD(v30) = v28;
      v14 = v28 & 0x8E5E0000 | (unsigned __int16)v30 | 0xE5E0000;
    }
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_72;
    }
    v32 = 69;
    v33 = v15;
  }
  WPP_SF_DSd(
    v31[2],
    v32,
    (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
    v33,
    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
    v28);
LABEL_72:
  if ( v15 )
    v14 = 0;
LABEL_90:
  v39 = v14;
LABEL_91:
  CHResultImp::~CHResultImp((CHResultImp *)v38);
  return v14;
}

```

## disassembly

```asm
0x140029268  mov     [rsp-38h+arg_10], r8
0x14002926d  push    rbp
0x14002926e  push    rbx
0x14002926f  push    rsi
0x140029270  push    r12
0x140029272  push    r13
0x140029274  push    r14
0x140029276  push    r15
0x140029278  mov     rbp, rsp
0x14002927b  sub     rsp, 80h
0x140029282  mov     rax, gs:58h
0x14002928b  mov     rsi, rcx
0x14002928e  mov     ecx, 8
0x140029293  mov     rbx, r9
0x140029296  mov     r15, r8
0x140029299  mov     r12d, edx
0x14002929c  mov     r10, [rax]
0x14002929f  lea     rax, aTieringheatses_5; "TieringHeatSession::GetHeatRecordsByInd"...
0x1400292a6  mov     [rcx+r10], rax
0x1400292aa  lea     rcx, [rbp+var_18]; this
0x1400292ae  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400292b3  xor     r13d, r13d
0x1400292b6  xor     r9d, r9d; grbit
0x1400292b9  mov     [r15], r13d
0x1400292bc  mov     r8d, 80000000h; cRow
0x1400292c2  mov     [rbx], r13
0x1400292c5  mov     rdx, [rsi+18h]; tableid
0x1400292c9  mov     rcx, [rsi+8]; sesid
0x1400292cd  mov     [rbp+var_10], r13d
0x1400292d1  call    cs:__imp_JetMove
0x1400292d7  mov     r8d, eax
0x1400292da  test    eax, eax
0x1400292dc  jnz     loc_140029766
0x1400292e2  test    r12d, r12d
0x1400292e5  jz      short loc_140029306
0x1400292e7  mov     rdx, [rsi+18h]; tableid
0x1400292eb  xor     r9d, r9d; grbit
0x1400292ee  mov     rcx, [rsi+8]; sesid
0x1400292f2  mov     r8d, r12d; cRow
0x1400292f5  call    cs:__imp_JetMove
0x1400292fb  mov     r8d, eax
0x1400292fe  test    eax, eax
0x140029300  jnz     loc_140029766
0x140029306  mov     rcx, cs:WPP_GLOBAL_Control
0x14002930d  lea     r14, WPP_GLOBAL_Control
0x140029314  cmp     rcx, r14
0x140029317  jz      short loc_140029333
0x140029319  test    byte ptr [rcx+1Ch], 1
0x14002931d  jz      short loc_140029333
0x14002931f  cmp     byte ptr [rcx+19h], 5
0x140029323  jb      short loc_140029333
0x140029325  mov     rcx, [rcx+10h]
0x140029329  mov     dword ptr [rsp+80h+var_58], r12d
0x14002932e  call    WPP_SF_DDD
0x140029333  mov     ecx, 0C3500h; cb
0x140029338  call    cs:__imp_CoTaskMemAlloc
0x14002933e  mov     [rbx], rax
0x140029341  mov     [r15], r13d
0x140029344  mov     rcx, [rbx]; void *
0x140029347  test    rcx, rcx
0x14002934a  jnz     short loc_1400293A9
0x14002934c  mov     ebx, 8007000Eh
0x140029351  mov     [rbp+var_10], ebx
0x140029354  mov     rcx, cs:WPP_GLOBAL_Control
0x14002935b  cmp     rcx, r14
0x14002935e  jz      loc_140029819
0x140029364  test    byte ptr [rcx+1Ch], 1
0x140029368  jz      loc_140029819
0x14002936e  cmp     byte ptr [rcx+19h], 2
0x140029372  jb      loc_140029819
0x140029378  mov     rax, [rsi+28h]
0x14002937c  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140029383  mov     rcx, [rcx+10h]
0x140029387  mov     edx, 42h ; 'B'
0x14002938c  mov     dword ptr [rsp+80h+var_58], ebx
0x140029390  mov     r9d, 2710h
0x140029396  mov     rax, [rax+70h]
0x14002939a  mov     [rsp+80h+var_60], rax
0x14002939f  call    WPP_SF_DSd
0x1400293a4  jmp     loc_140029819
0x1400293a9  xor     edx, edx; Val
0x1400293ab  mov     r8d, 0C3500h; Size
0x1400293b1  mov     r15d, r13d
0x1400293b4  call    memset_0
0x1400293b9  mov     rbx, [rbx]
0x1400293bc  mov     dl, 1; bool
0x1400293be  mov     r8, rbx; struct TE_FILE_ID_128 *
0x1400293c1  mov     [rbp+var_20], r13b
0x1400293c5  mov     [rbp+arg_18], r13b
0x1400293c9  mov     [rbp+arg_0], r13b
0x1400293cd  lea     rax, [rbx+24h]
0x1400293d1  mov     [rsp+80h+var_40], rax; unsigned __int16 *
0x1400293d6  lea     rcx, [rbx+20h]
0x1400293da  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x1400293df  lea     rax, [rbp+arg_0]
0x1400293e3  mov     [rsp+80h+var_50], rax; unsigned __int8 *
0x1400293e8  lea     r9, [rbx+10h]; __int64 *
0x1400293ec  lea     rax, [rbp+arg_18]
0x1400293f0  mov     rcx, rsi; this
0x1400293f3  mov     [rsp+80h+var_58], rax; unsigned __int8 *
0x1400293f8  lea     rax, [rbp+var_20]
0x1400293fc  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x140029401  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140029406  mov     ecx, eax
0x140029408  test    eax, eax
0x14002940a  jnz     loc_1400296C2
0x140029410  mov     rax, [rbx]
0x140029413  cmp     rax, qword ptr cs:?NullGuid@@3U_GUID@@A.Data1; _GUID NullGuid ...
0x14002941a  mov     r8, [rbx+10h]; __int64
0x14002941e  mov     [rbp+var_1C], r13d
0x140029422  jnz     short loc_140029445
0x140029424  mov     rax, [rbx+8]
0x140029428  cmp     rax, qword ptr cs:?NullGuid@@3U_GUID@@A.Data4; _GUID NullGuid ...
0x14002942f  jnz     short loc_140029445
0x140029431  test    r8, r8
0x140029434  jnz     short loc_140029445
0x140029436  mov     dword ptr [rbx+1Ch], 0FFFFh
0x14002943d  mov     edx, r13d
0x140029440  jmp     loc_1400294EB
0x140029445  mov     [rsp+80h+var_30], 0; unsigned int *
0x14002944e  lea     rax, [rbx+24h]
0x140029452  lea     rcx, [rbp+var_1C]
0x140029456  xor     r9d, r9d; unsigned int
0x140029459  lea     r13, [rbx+1Ch]
0x14002945d  mov     rdx, rbx; struct TE_FILE_ID_128 *
0x140029460  mov     [rsp+80h+var_38], r13; unsigned int *
0x140029465  mov     [rsp+80h+var_40], rcx; int *
0x14002946a  mov     rcx, rsi; this
0x14002946d  mov     [rsp+80h+var_48], rax; unsigned __int16 *
0x140029472  mov     al, [rbp+arg_18]
0x140029475  mov     byte ptr [rsp+80h+var_50], al; char
0x140029479  movzx   eax, word ptr [rbx+20h]
0x14002947d  mov     word ptr [rsp+80h+var_58], ax; unsigned __int16
0x140029482  mov     al, [rbp+arg_0]
0x140029485  mov     byte ptr [rsp+80h+var_60], al; char
0x140029489  call    ?AddCurrentCountAndAgeHistory@TieringHeatSession@@QEAAXPEBUTE_FILE_ID_128@@_JKEGEPEAGPEAHPEAK4@Z; TieringHeatSession::AddCurrentCountAndAgeHistory(TE_FILE_ID_128 const *,__int64,ulong,uchar,ushort,uchar,ushort *,int *,ulong *,ulong *)
0x14002948e  movzx   r9d, [rbp+arg_18]
0x140029493  mov     r8b, [rbp+var_20]
0x140029497  test    r9b, 8
0x14002949b  jz      short loc_1400294A1
0x14002949d  mov     al, 1
0x14002949f  jmp     short loc_1400294CF
0x1400294a1  test    r9b, 4
0x1400294a5  jz      short loc_1400294AB
0x1400294a7  mov     al, 2
0x1400294a9  jmp     short loc_1400294CF
0x1400294ab  mov     rax, [rsi+28h]
0x1400294af  mov     ecx, [r13+0]
0x1400294b3  mov     rdx, [rax]
0x1400294b6  test    r8b, 10h
0x1400294ba  jz      short loc_1400294C4
0x1400294bc  cmp     ecx, [rdx+0E4h]
0x1400294c2  jmp     short loc_1400294CA
0x1400294c4  cmp     ecx, [rdx+0E0h]
0x1400294ca  setb    al
0x1400294cd  inc     al
0x1400294cf  movzx   edx, [rbp+arg_0]
0x1400294d3  or      r8b, al
0x1400294d6  shl     edx, 8
0x1400294d9  or      edx, r9d
0x1400294dc  movzx   ecx, r8b
0x1400294e0  shl     edx, 8
0x1400294e3  or      edx, ecx
0x1400294e5  mov     [rbp+var_20], cl
0x1400294e8  xor     r13d, r13d
0x1400294eb  mov     [rbx+18h], edx
0x1400294ee  inc     r15d
0x1400294f1  mov     rax, [rbp+arg_10]
0x1400294f5  mov     word ptr [rbx+22h], 7
0x1400294fb  mov     [rax], r15d
0x1400294fe  mov     rdx, [rsi+18h]; tableid
0x140029502  xor     r9d, r9d; grbit
0x140029505  mov     rcx, [rsi+8]; sesid
0x140029509  lea     r8d, [r9+1]; cRow
0x14002950d  call    cs:__imp_JetMove
0x140029513  mov     r8d, eax
0x140029516  cmp     eax, 0FFFFFC07h
0x14002951b  jz      short loc_1400294FE
0x14002951d  lea     ecx, [rax+643h]
0x140029523  test    ecx, 0FFFFFFFDh
0x140029529  jz      loc_140029674
0x14002952f  test    eax, eax
0x140029531  jnz     loc_1400295F1
0x140029537  cmp     r15d, 2710h
0x14002953e  jnb     short loc_1400295A0
0x140029540  add     rbx, 50h ; 'P'
0x140029544  mov     [rbp+var_20], r13b
0x140029548  mov     r8, rbx; struct TE_FILE_ID_128 *
0x14002954b  mov     [rbp+arg_18], r13b
0x14002954f  mov     dl, 1; bool
0x140029551  mov     [rbp+arg_0], r13b
0x140029555  lea     rax, [rbx+24h]
0x140029559  mov     [rsp+80h+var_40], rax; unsigned __int16 *
0x14002955e  lea     rcx, [rbx+20h]
0x140029562  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x140029567  lea     rax, [rbp+arg_0]
0x14002956b  mov     [rsp+80h+var_50], rax; unsigned __int8 *
0x140029570  lea     r9, [rbx+10h]; __int64 *
0x140029574  lea     rax, [rbp+arg_18]
0x140029578  mov     rcx, rsi; this
0x14002957b  mov     [rsp+80h+var_58], rax; unsigned __int8 *
0x140029580  lea     rax, [rbp+var_20]
0x140029584  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x140029589  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002958e  mov     ecx, eax
0x140029590  mov     r8d, eax
0x140029593  test    eax, eax
0x140029595  jz      loc_140029410
0x14002959b  jmp     loc_1400296C5
0x1400295a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295a7  cmp     rcx, r14
0x1400295aa  jz      short loc_1400295DD
0x1400295ac  test    byte ptr [rcx+1Ch], 1
0x1400295b0  jz      short loc_1400295DD
0x1400295b2  cmp     byte ptr [rcx+19h], 4
0x1400295b6  jb      short loc_1400295DD
0x1400295b8  mov     rax, [rsi+28h]
0x1400295bc  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400295c3  mov     rcx, [rcx+10h]
0x1400295c7  mov     edx, 46h ; 'F'
0x1400295cc  mov     r9d, r15d
0x1400295cf  mov     rax, [rax+70h]
0x1400295d3  mov     [rsp+80h+var_60], rax
0x1400295d8  call    WPP_SF_DS
0x1400295dd  mov     [rbp+var_10], r13d
0x1400295e1  lea     rcx, [rbp+var_18]; this
0x1400295e5  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400295ea  xor     eax, eax
0x1400295ec  jmp     loc_140029824
0x1400295f1  cmp     r8d, 0FFFFFDEFh
0x1400295f8  jz      short loc_140029637
0x1400295fa  cmp     r8d, 0FFFFFBBCh
0x140029601  jz      short loc_140029637
0x140029603  cmp     r8d, 0FFFFF8F0h
0x14002960a  jz      short loc_140029637
0x14002960c  cmp     r8d, 0FFFFFC0Dh
0x140029613  jnz     short loc_14002961C
0x140029615  mov     ebx, 8007000Eh
0x14002961a  jmp     short loc_140029643
0x14002961c  neg     eax
0x14002961e  cmovs   eax, r8d
0x140029622  movzx   ebx, ax
0x140029625  mov     eax, r8d
0x140029628  and     eax, 8E5E0000h
0x14002962d  or      ebx, eax
0x14002962f  or      ebx, 0E5E0000h
0x140029635  jmp     short loc_140029643
0x140029637  mov     ecx, 70h ; 'p'; unsigned int
0x14002963c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140029641  mov     ebx, eax
0x140029643  mov     rcx, cs:WPP_GLOBAL_Control
0x14002964a  cmp     rcx, r14
0x14002964d  jz      loc_14002975A
0x140029653  test    byte ptr [rcx+1Ch], 1
0x140029657  jz      loc_14002975A
0x14002965d  cmp     byte ptr [rcx+19h], 2
0x140029661  jb      loc_14002975A
0x140029667  mov     edx, 45h ; 'E'
0x14002966c  mov     r9d, r15d
0x14002966f  jmp     loc_140029738
0x140029674  mov     rcx, cs:WPP_GLOBAL_Control
0x14002967b  cmp     rcx, r14
0x14002967e  jz      loc_1400295E1
0x140029684  test    byte ptr [rcx+1Ch], 1
0x140029688  jz      loc_1400295E1
0x14002968e  cmp     byte ptr [rcx+19h], 4
0x140029692  jb      loc_1400295E1
0x140029698  mov     rax, [rsi+28h]
0x14002969c  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400296a3  mov     rcx, [rcx+10h]
0x1400296a7  mov     edx, 44h ; 'D'
0x1400296ac  mov     r9d, r15d
0x1400296af  mov     rax, [rax+70h]
0x1400296b3  mov     [rsp+80h+var_60], rax
0x1400296b8  call    WPP_SF_DS
0x1400296bd  jmp     loc_1400295E1
0x1400296c2  mov     r8d, eax
0x1400296c5  cmp     r8d, 0FFFFFDEFh
0x1400296cc  jz      short loc_14002970C
0x1400296ce  cmp     r8d, 0FFFFFBBCh
0x1400296d5  jz      short loc_14002970C
0x1400296d7  cmp     r8d, 0FFFFF8F0h
0x1400296de  jz      short loc_14002970C
0x1400296e0  cmp     r8d, 0FFFFFC0Dh
0x1400296e7  jnz     short loc_1400296F0
0x1400296e9  mov     ebx, 8007000Eh
0x1400296ee  jmp     short loc_140029718
0x1400296f0  mov     eax, r8d
0x1400296f3  neg     eax
0x1400296f5  cmovs   eax, r8d
0x1400296f9  and     ecx, 8E5E0000h
0x1400296ff  movzx   ebx, ax
0x140029702  or      ebx, ecx
0x140029704  or      ebx, 0E5E0000h
0x14002970a  jmp     short loc_140029718
0x14002970c  mov     ecx, 70h ; 'p'; unsigned int
0x140029711  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140029716  mov     ebx, eax
0x140029718  mov     rcx, cs:WPP_GLOBAL_Control
0x14002971f  cmp     rcx, r14
  ... truncated ...
```
