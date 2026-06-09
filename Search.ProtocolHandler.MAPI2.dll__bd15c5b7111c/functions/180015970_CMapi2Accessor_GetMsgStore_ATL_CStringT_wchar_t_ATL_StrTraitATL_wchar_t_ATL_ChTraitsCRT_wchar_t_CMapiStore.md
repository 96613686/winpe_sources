# CMapi2Accessor::GetMsgStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore * *)

- ea: `0x180015970`
- end: `0x180015d3c`
- name: `?GetMsgStore@CMapi2Accessor@@QEAAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAPEAVCMapiStore@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180015884`
- `0x18001a280`
- `0x180020e44`
- `0x180024824`

## callees

- `0x18000ad14`
- `0x18000e0d0`
- `0x18000e658`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000f1c4`
- `0x1800113ac`
- `0x180011884`
- `0x1800122d8`
- `0x180015178`
- `0x180015970`
- `0x180016948`
- `0x18001732c`
- `0x1800173d4`
- `0x18002ebe4`
- `0x18002f07c`
- `0x180033a38`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015b8f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015b8f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015cb8`

## string_xrefs

- `0x180015ab0`: `CMapi2Accessor::GetMsgStore, returning PRTH_E_SERVER_ERROR because we can't access the shared Outlook memory`
- `0x180015b99`: `CMapi2Accessor::GetMsgStore, PRTH_E_OBJ_NOT_FOUND because store was not found`
- `0x180015bc5`: `CMapi2Accessor::GetMsgStore, returning PRTH_E_SERVER_ERROR because of MsgStore->Connected() failed or Search Owner is not available`
- `0x180015cc9`: `CMapi2Accessor::GetMsgStore, error code changed to PRTH_S_NOT_MODIFIED because store exists in other profile`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMapi2Accessor::GetMsgStore(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rcx
  int *v11; // rdi
  volatile signed __int32 *v12; // rbx
  _QWORD *v13; // r14
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rcx
  volatile signed __int32 *v19; // rbx
  int DisplayName; // esi
  char v21; // r15
  ATL::CStringData *v22; // rsi
  int *v23; // rdi
  volatile signed __int32 *v24; // rbx
  __int64 v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rcx
  char v28; // di
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rdi
  __int64 v33; // [rsp+20h] [rbp-28h] BYREF
  __int64 v34; // [rsp+28h] [rbp-20h] BYREF
  _QWORD *v35; // [rsp+30h] [rbp-18h]
  __int64 v36; // [rsp+90h] [rbp+48h] BYREF
  _QWORD *v37; // [rsp+98h] [rbp+50h]
  volatile signed __int32 *v38; // [rsp+A0h] [rbp+58h] BYREF
  volatile signed __int32 *v39; // [rsp+A8h] [rbp+60h] BYREF

  v37 = a2;
  v36 = a1;
  v5 = a1;
  LODWORD(v38) = 0;
  *a3 = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v39);
  v6 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(a2, L"($");
  if ( v6 > 0 )
  {
    v7 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
           a2,
           &v38,
           (unsigned int)(v6 + 2));
    v8 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimRight(v7);
    v9 = *(_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimLeft(v8);
    v10 = (volatile signed __int32 *)(v9 - 24);
    v11 = (int *)(v39 - 6);
    if ( (volatile signed __int32 *)(v9 - 24) != v39 - 6 )
    {
      if ( v11[4] >= 0 && *(_QWORD *)v10 == *(_QWORD *)v11 )
      {
        v12 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v10);
        ATL::CStringData::Release((ATL::CStringData *)v11);
        v39 = v12 + 6;
      }
      else
      {
        ATL::CSimpleStringT<wchar_t,0>::SetString(&v39, v9, *(unsigned int *)(v9 - 16));
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v38);
  v13 = (_QWORD *)(v5 + 520);
  v35 = (_QWORD *)(v5 + 520);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v34,
    (_QWORD *)(v5 + 520));
  v14 = *(_DWORD *)(v34 - 24 + 8);
  ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
  if ( v14 )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &v34,
      (_QWORD *)(v5 + 520));
    v21 = 6;
    v22 = (ATL::CStringData *)(v34 - 24);
    v19 = v38;
    v23 = (int *)(v38 - 6);
    if ( (volatile signed __int32 *)(v34 - 24) != v38 - 6 )
    {
      if ( v23[4] >= 0 && *(_QWORD *)v22 == *(_QWORD *)v23 )
      {
        v24 = ATL::CSimpleStringT<wchar_t,0>::CloneData((volatile signed __int32 *)(v34 - 24));
        ATL::CStringData::Release((ATL::CStringData *)v23);
        v19 = v24 + 6;
        v38 = v19;
      }
      else
      {
        ATL::CSimpleStringT<wchar_t,0>::SetString(&v38, v34, *(unsigned int *)(v34 - 16));
        v19 = v38;
      }
    }
    ATL::CStringData::Release(v22);
    v5 = v36;
  }
  else
  {
    v15 = *(_QWORD *)(v5 + 64);
    v16 = *(_QWORD *)(v15 + 208);
    if ( !*(_QWORD *)(v16 + 208) )
      CMapiManager::InitSharedOutlookMemory(*(HANDLE **)(v15 + 208));
    v17 = ocslen(*(const wchar_t **)(v16 + 208));
    ATL::CSimpleStringT<wchar_t,0>::SetString(&v38, v18, v17);
    v19 = v38;
    if ( !*((_DWORD *)v38 - 4) )
    {
      CLogger::Info(
        0,
        L"CMapi2Accessor::GetMsgStore, returning PRTH_E_SERVER_ERROR because we can't access the shared Outlook memory");
      DisplayName = -2147216890;
      goto LABEL_47;
    }
    v21 = 2;
  }
  DisplayName = CMapiManager::OpenStore(*(CMapiManager **)(*(_QWORD *)(v5 + 64) + 208LL));
  if ( !DisplayName )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v33);
    v25 = *a3;
    DisplayName = CMapiStore::GetDisplayName(*a3, &v33);
    v26 = v33;
    if ( DisplayName >= 0 && (unsigned int)_o__wcsicmp(v33, *a2) )
    {
      CLogger::Info(DisplayName, L"CMapi2Accessor::GetMsgStore, PRTH_E_OBJ_NOT_FOUND because store was not found");
      DisplayName = -2147216895;
    }
    else
    {
      if ( *(_QWORD *)(v25 + 48) && *(_DWORD *)(v25 + 648) != *(_DWORD *)(v25 + 652) )
        goto LABEL_28;
      CLogger::Info(
        DisplayName,
        L"CMapi2Accessor::GetMsgStore, returning PRTH_E_SERVER_ERROR because of MsgStore->Connected() failed or Search Own"
         "er is not available");
      DisplayName = -2147216890;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    *a3 = 0;
LABEL_28:
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    v13 = v35;
  }
  if ( *a3 )
  {
    v27 = v33;
LABEL_34:
    v28 = 0;
    goto LABEL_35;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v33,
    v13);
  v21 |= 9u;
  v27 = v33;
  if ( *(_DWORD *)(v33 - 16) && DisplayName != -2147221233 )
    goto LABEL_34;
  v28 = 1;
LABEL_35:
  if ( (v21 & 1) != 0 )
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  if ( v28 )
  {
    v33 = 0;
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      (__int64)&v34,
      (const wchar_t *)&dword_1800444C4);
    DisplayName = CMapiManager::OpenStore(*(CMapiManager **)(*(_QWORD *)(v36 + 64) + 208LL));
    if ( DisplayName >= 0 )
    {
      v29 = v33;
      if ( *(_QWORD *)(v33 + 48) )
      {
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v36);
        v30 = CMapiStore::GetDisplayName(v29, &v36);
        v31 = v36;
        if ( v30 >= 0 && (unsigned int)_o__wcsicmp(v36, *a2) )
        {
          DisplayName = -2147216895;
        }
        else
        {
          CLogger::Info(
            DisplayName,
            L"CMapi2Accessor::GetMsgStore, error code changed to PRTH_S_NOT_MODIFIED because store exists in other profile");
          DisplayName = 266755;
        }
        ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      }
      else
      {
        DisplayName = -2147216890;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  }
LABEL_47:
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 6));
  ATL::CStringData::Release((ATL::CStringData *)(v39 - 6));
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 24LL));
  return (unsigned int)DisplayName;
}

```

## disassembly

```asm
0x180015970  mov     [rsp-40h+arg_8], rdx
0x180015975  mov     [rsp-40h+arg_0], rcx
0x18001597a  push    rbp
0x18001597b  push    rbx
0x18001597c  push    rsi
0x18001597d  push    rdi
0x18001597e  push    r12
0x180015980  push    r13
0x180015982  push    r14
0x180015984  push    r15
0x180015986  mov     rbp, rsp
0x180015989  sub     rsp, 48h
0x18001598d  mov     r12, r8
0x180015990  mov     r13, rdx
0x180015993  mov     rsi, rcx
0x180015996  mov     dword ptr [rbp+arg_10], 0
0x18001599d  mov     qword ptr [r8], 0
0x1800159a4  lea     rcx, [rbp+arg_18]
0x1800159a8  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800159ad  nop
0x1800159ae  lea     rdx, asc_18004608C; "($"
0x1800159b5  mov     rcx, r13
0x1800159b8  call    ?Find@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_WH@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(wchar_t const *,int)
0x1800159bd  test    eax, eax
0x1800159bf  jle     short loc_180015A39
0x1800159c1  lea     r8d, [rax+2]
0x1800159c5  lea     rdx, [rbp+arg_10]
0x1800159c9  mov     rcx, r13
0x1800159cc  call    ?Mid@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int)
0x1800159d1  nop
0x1800159d2  mov     rcx, rax
0x1800159d5  call    ?TrimRight@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimRight(wchar_t const *)
0x1800159da  mov     rcx, rax
0x1800159dd  call    ?TrimLeft@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimLeft(wchar_t const *)
0x1800159e2  mov     rdx, [rax]
0x1800159e5  lea     rcx, [rdx-18h]
0x1800159e9  mov     rdi, [rbp+arg_18]
0x1800159ed  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800159f1  cmp     rcx, rdi
0x1800159f4  jz      short loc_180015A2C
0x1800159f6  cmp     dword ptr [rdi+10h], 0
0x1800159fa  jl      short loc_180015A1E
0x1800159fc  mov     rax, [rdi]
0x1800159ff  cmp     [rcx], rax
0x180015a02  jnz     short loc_180015A1E
0x180015a04  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180015a09  mov     rbx, rax
0x180015a0c  mov     rcx, rdi; this
0x180015a0f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015a14  lea     rax, [rbx+18h]
0x180015a18  mov     [rbp+arg_18], rax
0x180015a1c  jmp     short loc_180015A2C
0x180015a1e  mov     r8d, [rdx-10h]
0x180015a22  lea     rcx, [rbp+arg_18]
0x180015a26  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180015a2b  nop
0x180015a2c  mov     rcx, [rbp+arg_10]
0x180015a30  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015a34  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015a39  lea     rcx, [rbp+arg_10]
0x180015a3d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180015a42  nop
0x180015a43  lea     r14, [rsi+208h]
0x180015a4a  mov     [rbp+var_18], r14
0x180015a4e  mov     rdx, r14
0x180015a51  lea     rcx, [rbp+var_20]
0x180015a55  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180015a5a  mov     rcx, [rbp+var_20]
0x180015a5e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015a62  mov     ebx, [rcx+8]
0x180015a65  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015a6a  test    ebx, ebx
0x180015a6c  jnz     short loc_180015AD0
0x180015a6e  mov     rax, [rsi+40h]
0x180015a72  mov     rbx, [rax+0D0h]
0x180015a79  cmp     qword ptr [rbx+0D0h], 0
0x180015a81  jnz     short loc_180015A8B
0x180015a83  mov     rcx, rbx; this
0x180015a86  call    ?InitSharedOutlookMemory@CMapiManager@@AEAAJXZ; CMapiManager::InitSharedOutlookMemory(void)
0x180015a8b  mov     rcx, [rbx+0D0h]; wchar_t *
0x180015a92  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x180015a97  mov     r8d, eax
0x180015a9a  mov     rdx, rcx
0x180015a9d  lea     rcx, [rbp+arg_10]
0x180015aa1  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180015aa6  mov     rbx, [rbp+arg_10]
0x180015aaa  cmp     dword ptr [rbx-10h], 0
0x180015aae  jnz     short loc_180015AC8
0x180015ab0  lea     rdx, aCmapi2accessor_6; "CMapi2Accessor::GetMsgStore, returning "...
0x180015ab7  xor     ecx, ecx; int
0x180015ab9  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180015abe  mov     esi, 80041206h
0x180015ac3  jmp     loc_180015D04
0x180015ac8  mov     r15d, 2
0x180015ace  jmp     short loc_180015B3F
0x180015ad0  mov     rdx, r14
0x180015ad3  lea     rcx, [rbp+var_20]
0x180015ad7  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180015adc  mov     r15d, 6
0x180015ae2  mov     rdx, [rbp+var_20]
0x180015ae6  lea     rsi, [rdx-18h]
0x180015aea  mov     rbx, [rbp+arg_10]
0x180015aee  lea     rdi, [rbx-18h]
0x180015af2  cmp     rsi, rdi
0x180015af5  jz      short loc_180015B33
0x180015af7  cmp     dword ptr [rdi+10h], 0
0x180015afb  jl      short loc_180015B22
0x180015afd  mov     rax, [rdi]
0x180015b00  cmp     [rsi], rax
0x180015b03  jnz     short loc_180015B22
0x180015b05  mov     rcx, rsi
0x180015b08  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180015b0d  mov     rbx, rax
0x180015b10  mov     rcx, rdi; this
0x180015b13  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015b18  add     rbx, 18h
0x180015b1c  mov     [rbp+arg_10], rbx
0x180015b20  jmp     short loc_180015B33
0x180015b22  mov     r8d, [rdx-10h]
0x180015b26  lea     rcx, [rbp+arg_10]
0x180015b2a  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180015b2f  mov     rbx, [rbp+arg_10]
0x180015b33  mov     rcx, rsi; this
0x180015b36  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015b3b  mov     rsi, [rbp+arg_0]
0x180015b3f  mov     rcx, [rsi+40h]
0x180015b43  mov     r9, r12
0x180015b46  lea     r8, [rbp+arg_18]
0x180015b4a  lea     rdx, [rbp+arg_10]
0x180015b4e  mov     rcx, [rcx+0D0h]; this
0x180015b55  call    ?OpenStore@CMapiManager@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@0PEAPEAVCMapiStore@@@Z; CMapiManager::OpenStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,CMapiStore * *)
0x180015b5a  mov     esi, eax
0x180015b5c  test    eax, eax
0x180015b5e  jnz     loc_180015BFC
0x180015b64  lea     rcx, [rbp+var_28]
0x180015b68  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180015b6d  nop
0x180015b6e  mov     r14, [r12]
0x180015b72  lea     rdx, [rbp+var_28]
0x180015b76  mov     rcx, r14
0x180015b79  call    ?GetDisplayName@CMapiStore@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiStore::GetDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180015b7e  mov     esi, eax
0x180015b80  mov     rdi, [rbp+var_28]
0x180015b84  test    eax, eax
0x180015b86  js      short loc_180015BAE
0x180015b88  mov     rdx, [r13+0]
0x180015b8c  mov     rcx, rdi
0x180015b8f  call    cs:__imp__o__wcsicmp
0x180015b95  test    eax, eax
0x180015b97  jz      short loc_180015BAE
0x180015b99  lea     rdx, aCmapi2accessor_0; "CMapi2Accessor::GetMsgStore, PRTH_E_OBJ"...
0x180015ba0  mov     ecx, esi; int
0x180015ba2  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180015ba7  mov     esi, 80041201h
0x180015bac  jmp     short loc_180015BD8
0x180015bae  cmp     qword ptr [r14+30h], 0
0x180015bb3  jz      short loc_180015BC5
0x180015bb5  mov     eax, [r14+28Ch]
0x180015bbc  cmp     [r14+288h], eax
0x180015bc3  jnz     short loc_180015BEF
0x180015bc5  lea     rdx, aCmapi2accessor_1; "CMapi2Accessor::GetMsgStore, returning "...
0x180015bcc  mov     ecx, esi; int
0x180015bce  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180015bd3  mov     esi, 80041206h
0x180015bd8  mov     rax, [r14]
0x180015bdb  mov     rcx, r14
0x180015bde  mov     rax, [rax+10h]
0x180015be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be7  mov     qword ptr [r12], 0
0x180015bef  lea     rcx, [rdi-18h]; this
0x180015bf3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015bf8  mov     r14, [rbp+var_18]
0x180015bfc  cmp     qword ptr [r12], 0
0x180015c01  jnz     short loc_180015C2A
0x180015c03  mov     rdx, r14
0x180015c06  lea     rcx, [rbp+var_28]
0x180015c0a  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180015c0f  or      r15d, 9
0x180015c13  mov     rcx, [rbp+var_28]
0x180015c17  cmp     dword ptr [rcx-10h], 0
0x180015c1b  jz      short loc_180015C25
0x180015c1d  cmp     esi, 8004010Fh
0x180015c23  jnz     short loc_180015C2E
0x180015c25  mov     dil, 1
0x180015c28  jmp     short loc_180015C31
0x180015c2a  mov     rcx, [rbp+var_28]
0x180015c2e  xor     dil, dil
0x180015c31  test    r15b, 1
0x180015c35  jz      short loc_180015C40
0x180015c37  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015c3b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015c40  test    dil, dil
0x180015c43  jz      loc_180015D04
0x180015c49  mov     [rbp+var_28], 0
0x180015c51  lea     rdx, dword_1800444C4
0x180015c58  lea     rcx, [rbp+var_20]
0x180015c5c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180015c61  nop
0x180015c62  mov     rcx, [rbp+arg_0]
0x180015c66  mov     rcx, [rcx+40h]
0x180015c6a  lea     r9, [rbp+var_28]
0x180015c6e  lea     r8, [rbp+arg_18]
0x180015c72  lea     rdx, [rbp+var_20]
0x180015c76  mov     rcx, [rcx+0D0h]; this
0x180015c7d  call    ?OpenStore@CMapiManager@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@0PEAPEAVCMapiStore@@@Z; CMapiManager::OpenStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,CMapiStore * *)
0x180015c82  mov     esi, eax
0x180015c84  test    eax, eax
0x180015c86  js      short loc_180015CEC
0x180015c88  mov     rdi, [rbp+var_28]
0x180015c8c  cmp     qword ptr [rdi+30h], 0
0x180015c91  jz      short loc_180015CE7
0x180015c93  lea     rcx, [rbp+arg_0]
0x180015c97  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180015c9c  nop
0x180015c9d  lea     rdx, [rbp+arg_0]
0x180015ca1  mov     rcx, rdi
0x180015ca4  call    ?GetDisplayName@CMapiStore@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiStore::GetDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180015ca9  mov     rdi, [rbp+arg_0]
0x180015cad  test    eax, eax
0x180015caf  js      short loc_180015CC9
0x180015cb1  mov     rdx, [r13+0]
0x180015cb5  mov     rcx, rdi
0x180015cb8  call    cs:__imp__o__wcsicmp
0x180015cbe  test    eax, eax
0x180015cc0  jz      short loc_180015CC9
0x180015cc2  mov     esi, 80041201h
0x180015cc7  jmp     short loc_180015CDC
0x180015cc9  lea     rdx, aCmapi2accessor; "CMapi2Accessor::GetMsgStore, error code"...
0x180015cd0  mov     ecx, esi; int
0x180015cd2  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180015cd7  mov     esi, 41203h
0x180015cdc  lea     rcx, [rdi-18h]; this
0x180015ce0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015ce5  jmp     short loc_180015CEC
0x180015ce7  mov     esi, 80041206h
0x180015cec  mov     rcx, [rbp+var_20]
0x180015cf0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015cf4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015cf9  nop
0x180015cfa  lea     rcx, [rbp+var_28]
0x180015cfe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015d03  nop
0x180015d04  lea     rcx, [rbx-18h]; this
0x180015d08  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015d0d  nop
0x180015d0e  mov     rcx, [rbp+arg_18]
0x180015d12  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015d16  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015d1b  nop
0x180015d1c  mov     rcx, [r13+0]
0x180015d20  sub     rcx, 18h; this
0x180015d24  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015d29  mov     eax, esi
0x180015d2b  add     rsp, 48h
0x180015d2f  pop     r15
0x180015d31  pop     r14
0x180015d33  pop     r13
0x180015d35  pop     r12
0x180015d37  pop     rdi
0x180015d38  pop     rsi
0x180015d39  pop     rbx
0x180015d3a  pop     rbp
0x180015d3b  retn
```
