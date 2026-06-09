# CConnectedUserStore::GetConnectedUserEnum(ulong,_GUID const *,IEnumUnknown * *)

- ea: `0x180004490`
- end: `0x180004e66`
- name: `?GetConnectedUserEnum@CConnectedUserStore@@UEAAJKPEBU_GUID@@PEAPEAUIEnumUnknown@@@Z`
- size: `2518`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, int, struct _GUID *, struct IEnumUnknown **)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037a0`
- `0x180003a70`
- `0x180004490`
- `0x180004e70`
- `0x180005ea0`
- `0x18000fba2`
- `0x180014430`
- `0x1800144b4`
- `0x180016718`
- `0x180016bb8`
- `0x1800191ac`
- `0x180019210`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047c3`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004d5b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ac`
- `SAMLIB!SamQueryInformationUser` at `0x1800046f3`
- `SAMLIB!SamQueryInformationUser` at `0x1800046f3`
- `SAMLIB!SamFreeMemory` at `0x180004747`
- `SAMLIB!SamFreeMemory` at `0x180004747`
- `SAMLIB!SamCloseHandle` at `0x180004731`
- `SAMLIB!SamCloseHandle` at `0x180004731`
- `SAMLIB!SamOpenUser` at `0x1800046d6`
- `SAMLIB!SamOpenUser` at `0x1800046d6`

## string_xrefs

- `0x180004ac8`: `CConnectedUserStore::CoCreateConnectedUser`
- `0x180004c30`: `CConnectedUserStore::CoCreateConnectedUser`
- `0x180004c9a`: `CConnectedUserStore::CoCreateConnectedUser`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::GetConnectedUserEnum(
        CConnectedUserStore *this,
        int a2,
        struct _GUID *a3,
        struct IEnumUnknown **a4)
{
  const struct _GUID *v5; // r12
  CConnectedUserStore *v6; // r15
  __int64 v7; // rdx
  CConnectedUser *v8; // rbx
  GUID *v9; // rcx
  GUID *v10; // rax
  struct IConnectedIdentityProvider *v11; // rdi
  CIdentityProfileHandler *v12; // r10
  int inited; // eax
  int ConnectedAADUserEnum; // esi
  __int64 v15; // r14
  __int64 v16; // rax
  _QWORD *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r12
  unsigned int v20; // r13d
  int v21; // eax
  CConnectedUser *v22; // r15
  int v23; // r15d
  __int64 v24; // rax
  unsigned int v25; // esi
  __int64 v26; // rax
  int v27; // esi
  __int64 v28; // r13
  unsigned int v29; // esi
  void *v30; // r15
  HANDLE ProcessHeap; // rax
  LPVOID v32; // rax
  int v33; // r15d
  CConnectedUser *v34; // rcx
  char v35; // al
  ULONGLONG v36; // rax
  CConnectedUser *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r9
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // [rsp+30h] [rbp-49h]
  int v47; // [rsp+34h] [rbp-45h]
  _QWORD *v48; // [rsp+38h] [rbp-41h]
  struct _GUID v49; // [rsp+40h] [rbp-39h] BYREF
  struct IConnectedIdentityProvider *v50; // [rsp+50h] [rbp-29h] BYREF
  int v51; // [rsp+58h] [rbp-21h]
  CConnectedUserStore *v52; // [rsp+60h] [rbp-19h]
  const struct _GUID *v53; // [rsp+68h] [rbp-11h]
  struct IEnumUnknown **v54; // [rsp+70h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+78h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+88h] [rbp+Fh] BYREF

  v54 = a4;
  v5 = a3;
  v53 = a3;
  v51 = a2;
  v6 = this;
  v52 = this;
  LODWORD(v7) = 0;
  *(_QWORD *)&v49.Data1 = 0;
  v8 = 0;
  v9 = &GUID_NULL;
  v10 = a3;
  if ( !a3 )
    v10 = &GUID_NULL;
  v56 = (struct _EVENT_DATA_DESCRIPTOR)*v10;
  v11 = 0;
  v50 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::GetConnectedUserEnum");
    v12 = WPP_GLOBAL_Control;
    LODWORD(v7) = 0;
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer((int)v9, (int)&GetConnectedUserEnumStart, (int)a3, (int)a4, &v55);
    v12 = WPP_GLOBAL_Control;
    LODWORD(v7) = 0;
  }
  if ( !a4 )
  {
    ConnectedAADUserEnum = -2147467261;
    if ( v12 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 4) == 0 )
      goto LABEL_68;
    v38 = 14;
    v39 = 2147500035LL;
LABEL_92:
    WPP_SF_d(*((_QWORD *)v12 + 2), v38, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v39);
    v12 = WPP_GLOBAL_Control;
    goto LABEL_68;
  }
  *a4 = 0;
  if ( v5 )
  {
    v41 = *(_QWORD *)&v5->Data1 - 0x4967A148B16898C6LL;
    if ( *(_QWORD *)&v5->Data1 == 0x4967A148B16898C6LL )
      v41 = *(_QWORD *)v5->Data4 - 0x2085DA55D7647191LL;
    if ( !v41 )
    {
      ConnectedAADUserEnum = CConnectedUserStore::GetConnectedAADUserEnum((CConnectedUserStore *)v9, a4);
      v12 = WPP_GLOBAL_Control;
      goto LABEL_68;
    }
  }
  inited = CConnectedUserStore::LazyInitConnectedUserArray(v6);
  ConnectedAADUserEnum = inited;
  if ( inited < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_68;
    }
    v38 = 15;
    v39 = (unsigned int)inited;
    goto LABEL_92;
  }
  ConnectedAADUserEnum = ATL::CComObject<CGenericEnum>::CreateInstance(&v49);
  v15 = *(_QWORD *)&v49.Data1;
  if ( ConnectedAADUserEnum < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v42 = 16;
LABEL_150:
      WPP_SF_d(
        *((_QWORD *)v12 + 2),
        v42,
        WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
        (unsigned int)ConnectedAADUserEnum);
LABEL_65:
      v12 = WPP_GLOBAL_Control;
    }
    goto LABEL_66;
  }
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v49.Data1 + 8LL))(*(_QWORD *)&v49.Data1);
  *(GUID *)(v15 + 92) = GUID_9d5f2149_de8c_45f2_b313_6587a04f771d;
  v47 = 0;
  v16 = 0;
  v17 = (_QWORD *)((char *)v6 + 112);
  v12 = WPP_GLOBAL_Control;
  while ( 1 )
  {
    v48 = v17;
    v46 = v16;
    if ( (unsigned int)v16 >= *((_DWORD *)v6 + 30) )
      break;
    v18 = 20 * v16;
    if ( !v5 )
      goto LABEL_15;
    v36 = *(_QWORD *)(*v17 + v18 + 4) - v56.Ptr;
    if ( !v36 )
      v36 = *(_QWORD *)(*v17 + v18 + 12) - *(_QWORD *)&v56.Size;
    if ( v36 )
    {
      v17 = (_QWORD *)((char *)v6 + 112);
      v16 = (unsigned int)(v46 + 1);
    }
    else
    {
LABEL_15:
      v19 = v18 + *v17;
      v20 = *(_DWORD *)v19;
      *(_QWORD *)&v49.Data1 = 0;
      if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
        WPP_SF_s(*((_QWORD *)v12 + 2), 10, v17, "CConnectedUserStore::CoCreateConnectedUser");
      v21 = ATL::CComObject<CConnectedUser>::CreateInstance(&v49);
      ConnectedAADUserEnum = v21;
      if ( v21 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
          goto LABEL_25;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_98;
        v43 = 105;
        v44 = (unsigned int)v21;
        goto LABEL_125;
      }
      v22 = *(CConnectedUser **)&v49.Data1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v49.Data1 + 8LL))(*(_QWORD *)&v49.Data1);
      v49 = *(struct _GUID *)(v19 + 4);
      ConnectedAADUserEnum = CConnectedUser::InitializeConnectedUser(
                               v22,
                               v20,
                               &v49,
                               (CConnectedUserStore *)((char *)v52 + 8));
      if ( ConnectedAADUserEnum >= 0 )
      {
        v8 = v22;
        goto LABEL_21;
      }
      (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v22 + 16LL))(v22);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v43 = 106;
        v44 = (unsigned int)ConnectedAADUserEnum;
LABEL_125:
        WPP_SF_d(*((_QWORD *)v12 + 2), v43, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v44);
        v12 = WPP_GLOBAL_Control;
      }
LABEL_98:
      if ( v12 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_BYTE *)v12 + 28) & 4) == 0 )
        goto LABEL_22;
      WPP_SF_sL(
        *((_QWORD *)v12 + 2),
        v7,
        (_DWORD)a3,
        (unsigned int)"CConnectedUserStore::CoCreateConnectedUser",
        ConnectedAADUserEnum);
LABEL_21:
      v12 = WPP_GLOBAL_Control;
LABEL_22:
      if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
      {
        WPP_SF_s(*((_QWORD *)v12 + 2), 12, a3, "CConnectedUserStore::CoCreateConnectedUser");
        v12 = WPP_GLOBAL_Control;
      }
LABEL_25:
      if ( ConnectedAADUserEnum < 0 )
      {
        if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
        {
          v42 = 18;
          goto LABEL_150;
        }
        goto LABEL_66;
      }
      v47 = 1;
      if ( (v51 & 1) != 0 )
        goto LABEL_49;
      v23 = 0;
      v55.Ptr = 0;
      *(_QWORD *)&v49.Data1 = 0;
      if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
      {
        WPP_SF_s(*((_QWORD *)v12 + 2), 10, a3, "CConnectedUser::IsVerifiedUser");
        v12 = WPP_GLOBAL_Control;
      }
      v24 = *(_QWORD *)((char *)v8 + 68) - 0x4967A148B16898C6LL;
      if ( *(_QWORD *)((char *)v8 + 68) == 0x4967A148B16898C6LL )
        v24 = *(_QWORD *)((char *)v8 + 76) - 0x2085DA55D7647191LL;
      if ( v24 )
      {
        v25 = *((_DWORD *)v8 + 16);
        v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 11) + 24LL))(*((_QWORD *)v8 + 11));
        v27 = SamOpenUser(v26, 0x2000000, v25, &v55);
        if ( v27 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v45 = 14;
            goto LABEL_129;
          }
LABEL_83:
          ConnectedAADUserEnum = v27 | 0x10000000;
          goto LABEL_39;
        }
        v27 = SamQueryInformationUser(v55.Ptr, 28, &v49);
        if ( v27 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v45 = 15;
LABEL_129:
            WPP_SF_d(*((_QWORD *)v12 + 2), v45, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, (unsigned int)v27);
            v12 = WPP_GLOBAL_Control;
          }
          goto LABEL_83;
        }
        ConnectedAADUserEnum = 0;
        if ( (**(_DWORD **)&v49.Data1 & 0x100000) != 0 && *(_DWORD *)(*(_QWORD *)&v49.Data1 + 128LL) )
          v23 = 1;
        v12 = WPP_GLOBAL_Control;
      }
      else
      {
        ConnectedAADUserEnum = -2147024846;
      }
LABEL_39:
      if ( v55.Ptr )
      {
        SamCloseHandle(v55.Ptr);
        v12 = WPP_GLOBAL_Control;
      }
      LODWORD(v9) = v49.Data1;
      if ( *(_QWORD *)&v49.Data1 )
      {
        SamFreeMemory(*(_QWORD *)&v49.Data1);
        v12 = WPP_GLOBAL_Control;
      }
      if ( ConnectedAADUserEnum < 0 )
      {
        if ( v12 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
          goto LABEL_47;
        if ( (*((_BYTE *)v12 + 28) & 4) != 0 )
        {
          WPP_SF_sL(
            *((_QWORD *)v12 + 2),
            v7,
            (_DWORD)a3,
            (unsigned int)"CConnectedUser::IsVerifiedUser",
            ConnectedAADUserEnum);
          v12 = WPP_GLOBAL_Control;
        }
      }
      if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
      {
        WPP_SF_s(*((_QWORD *)v12 + 2), 12, a3, "CConnectedUser::IsVerifiedUser");
        v12 = WPP_GLOBAL_Control;
      }
LABEL_47:
      if ( ConnectedAADUserEnum < 0 )
      {
        if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
        {
          v42 = 19;
          goto LABEL_150;
        }
        goto LABEL_66;
      }
      if ( !v23 )
      {
        if ( v8 )
        {
          v37 = v8;
          v8 = 0;
          (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v37 + 16LL))(v37);
          v12 = WPP_GLOBAL_Control;
        }
        goto LABEL_62;
      }
LABEL_49:
      v28 = *(unsigned int *)(v15 + 72);
      LODWORD(v9) = v28 + 1;
      if ( (_DWORD)v28 != -1 )
      {
        if ( (unsigned int)v9 <= *(_DWORD *)(v15 + 76) )
        {
LABEL_55:
          memmove_0(
            (void *)(8 * v28 + *(_QWORD *)(v15 + 64) + 8),
            (const void *)(8 * v28 + *(_QWORD *)(v15 + 64)),
            8LL * (unsigned int)(*(_DWORD *)(v15 + 72) - v28));
          v9 = (GUID *)*(unsigned int *)(v15 + 72);
          *(_DWORD *)(v15 + 72) = (_DWORD)v9 + 1;
          v7 = *(_QWORD *)(v15 + 64);
          if ( 8 * v28 + v7 )
          {
            *(_QWORD *)(v7 + 8LL * (_QWORD)v9) = v8;
            (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v8 + 8LL))(v8);
            v33 = 1;
            v12 = WPP_GLOBAL_Control;
            goto LABEL_57;
          }
        }
        else
        {
          v29 = (_DWORD)v9 + ((unsigned int)v9 >> 1) + 32;
          v30 = *(void **)(v15 + 64);
          ProcessHeap = GetProcessHeap();
          if ( v30 )
            v32 = HeapReAlloc(ProcessHeap, 0, v30, 8 * v29);
          else
            v32 = HeapAlloc(ProcessHeap, 0, 8 * v29);
          if ( v32 )
          {
            *(_QWORD *)(v15 + 64) = v32;
            *(_DWORD *)(v15 + 76) = v29;
            goto LABEL_55;
          }
        }
        v12 = WPP_GLOBAL_Control;
      }
      v33 = 0;
LABEL_57:
      ConnectedAADUserEnum = 0;
      if ( !v33 )
        ConnectedAADUserEnum = -2147024882;
      if ( v8 )
      {
        v34 = v8;
        v8 = 0;
        (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v34 + 16LL))(v34);
        v12 = WPP_GLOBAL_Control;
      }
      if ( !v33 )
      {
        if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
        {
          v42 = 20;
          goto LABEL_150;
        }
        goto LABEL_66;
      }
LABEL_62:
      v5 = v53;
      v6 = v52;
      v17 = v48;
      v16 = (unsigned int)(v46 + 1);
    }
  }
  if ( !v47 && v5 )
  {
    ConnectedAADUserEnum = CConnectedUserStore::GetConnectedProvider(v6, (const struct _GUID *)&v56, &v50);
    if ( ConnectedAADUserEnum < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
          (unsigned int)ConnectedAADUserEnum);
        v11 = v50;
        goto LABEL_65;
      }
      v11 = v50;
      goto LABEL_66;
    }
    v11 = v50;
  }
  ConnectedAADUserEnum = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEnumUnknown **))v15)(
                           v15,
                           &GUID_00000100_0000_0000_c000_000000000046,
                           v54);
  if ( ConnectedAADUserEnum >= 0 )
    goto LABEL_65;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v42 = 22;
    goto LABEL_150;
  }
LABEL_66:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_68:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer((int)v9, (int)&GetConnectedUserEnumStop, (int)a3, (int)a4, &v56);
    v12 = WPP_GLOBAL_Control;
  }
  v35 = 13;
  if ( ConnectedAADUserEnum == -805306355 )
  {
    ConnectedAADUserEnum = -2147024809;
  }
  else
  {
    v35 = 34;
    if ( ConnectedAADUserEnum == -805306334 )
    {
      ConnectedAADUserEnum = -2147024891;
      goto LABEL_73;
    }
    if ( ConnectedAADUserEnum >= 0 )
    {
LABEL_102:
      if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
        WPP_SF_s(*((_QWORD *)v12 + 2), 12, a3, "CConnectedUserStore::GetConnectedUserEnum");
      goto LABEL_105;
    }
    v35 = ConnectedAADUserEnum;
  }
LABEL_73:
  if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v12 + 2), v7, (_DWORD)a3, (unsigned int)"CConnectedUserStore::GetConnectedUserEnum", v35);
      v12 = WPP_GLOBAL_Control;
    }
    goto LABEL_102;
  }
LABEL_105:
  if ( v11 )
    ((void (__fastcall *)(struct IConnectedIdentityProvider *))v11->lpVtbl->Release)(v11);
  if ( v8 )
    (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)ConnectedAADUserEnum;
}

```

## disassembly

```asm
0x180004490  mov     [rsp-8+arg_8], rbx
0x180004495  push    rbp
0x180004496  push    rsi
0x180004497  push    rdi
0x180004498  push    r12
0x18000449a  push    r13
0x18000449c  push    r14
0x18000449e  push    r15
0x1800044a0  lea     rbp, [rsp-27h]
0x1800044a5  sub     rsp, 0A0h
0x1800044ac  mov     rax, cs:__security_cookie
0x1800044b3  xor     rax, rsp
0x1800044b6  mov     [rbp+57h+var_38], rax
0x1800044ba  mov     r13, r9
0x1800044bd  mov     [rbp+57h+var_60], r9
0x1800044c1  mov     r12, r8
0x1800044c4  mov     [rbp+57h+var_68], r8
0x1800044c8  mov     [rbp+57h+var_78], edx
0x1800044cb  mov     r15, rcx
0x1800044ce  mov     [rbp+57h+var_70], rcx
0x1800044d2  xor     edx, edx
0x1800044d4  mov     qword ptr [rbp+57h+var_90.Data1], rdx
0x1800044d8  mov     ebx, edx
0x1800044da  lea     rcx, GUID_NULL; int
0x1800044e1  mov     rax, r8
0x1800044e4  test    r8, r8
0x1800044e7  cmovz   rax, rcx
0x1800044eb  movups  xmm0, xmmword ptr [rax]
0x1800044ee  movups  xmmword ptr [rbp+57h+var_48.Ptr], xmm0
0x1800044f2  mov     edi, edx
0x1800044f4  mov     [rbp+57h+var_80], rdx
0x1800044f8  lea     r14, WPP_GLOBAL_Control
0x1800044ff  mov     r10, cs:WPP_GLOBAL_Control
0x180004506  cmp     r10, r14
0x180004509  jz      short loc_180004519
0x18000450b  test    dword ptr [r10+1Ch], 400h
0x180004513  jnz     loc_180004BB9
0x180004519  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180004520  jnz     loc_180004BDC
0x180004526  test    r13, r13
0x180004529  jz      loc_180004A59
0x18000452f  mov     [r13+0], rdx
0x180004533  test    r12, r12
0x180004536  jnz     loc_180004B81
0x18000453c  mov     rcx, r15; this
0x18000453f  call    ?LazyInitConnectedUserArray@CConnectedUserStore@@AEAAJXZ; CConnectedUserStore::LazyInitConnectedUserArray(void)
0x180004544  mov     esi, eax
0x180004546  test    eax, eax
0x180004548  js      loc_180004A1A
0x18000454e  lea     rcx, [rbp+57h+var_90]
0x180004552  call    ?CreateInstance@?$CComObject@VCGenericEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGenericEnum>::CreateInstance(ATL::CComObject<CGenericEnum> * *)
0x180004557  mov     esi, eax
0x180004559  mov     r14, qword ptr [rbp+57h+var_90.Data1]
0x18000455d  test    eax, eax
0x18000455f  js      loc_180004BFF
0x180004565  mov     rax, [r14]
0x180004568  mov     rcx, r14
0x18000456b  mov     rax, [rax+8]
0x18000456f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004574  movups  xmm0, xmmword ptr cs:_GUID_9d5f2149_de8c_45f2_b313_6587a04f771d.Data1
0x18000457b  movups  xmmword ptr [r14+5Ch], xmm0
0x180004580  xor     r9d, r9d
0x180004583  mov     [rbp+57h+var_9C], r9d
0x180004587  mov     eax, r9d
0x18000458a  lea     r8, [r15+70h]
0x18000458e  mov     r10, cs:WPP_GLOBAL_Control
0x180004595  mov     [rbp+57h+var_98], r8
0x180004599  mov     [rbp+57h+var_A0], eax
0x18000459c  cmp     eax, [r15+78h]
0x1800045a0  jnb     loc_180004891
0x1800045a6  lea     rcx, [rax+rax*4]
0x1800045aa  lea     rcx, ds:0[rcx*4]
0x1800045b2  test    r12, r12
0x1800045b5  jnz     loc_180004946
0x1800045bb  mov     r12, [r8]
0x1800045be  add     r12, rcx
0x1800045c1  mov     r13d, [r12]
0x1800045c5  mov     qword ptr [rbp+57h+var_90.Data1], r9
0x1800045c9  lea     rax, WPP_GLOBAL_Control
0x1800045d0  cmp     r10, rax
0x1800045d3  jz      short loc_1800045E3
0x1800045d5  test    dword ptr [r10+1Ch], 400h
0x1800045dd  jnz     loc_180004C2B
0x1800045e3  lea     rcx, [rbp+57h+var_90]
0x1800045e7  call    ?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)
0x1800045ec  mov     esi, eax
0x1800045ee  test    eax, eax
0x1800045f0  js      loc_180004C45
0x1800045f6  mov     r15, qword ptr [rbp+57h+var_90.Data1]
0x1800045fa  mov     rax, [r15]
0x1800045fd  mov     rcx, r15
0x180004600  mov     rax, [rax+8]
0x180004604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004609  movups  xmm0, xmmword ptr [r12+4]
0x18000460f  movaps  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180004613  mov     r9, [rbp+57h+var_70]
0x180004617  add     r9, 8; struct IConnectedUserSite *
0x18000461b  lea     r8, [rbp+57h+var_90]; struct _GUID
0x18000461f  mov     edx, r13d; unsigned int
0x180004622  mov     rcx, r15; this
0x180004625  call    ?InitializeConnectedUser@CConnectedUser@@QEAAJKU_GUID@@PEAVIConnectedUserSite@@@Z; CConnectedUser::InitializeConnectedUser(ulong,_GUID,IConnectedUserSite *)
0x18000462a  mov     esi, eax
0x18000462c  test    eax, eax
0x18000462e  js      loc_180004A7F
0x180004634  mov     rbx, r15
0x180004637  lea     r12, WPP_GLOBAL_Control
0x18000463e  mov     r10, cs:WPP_GLOBAL_Control
0x180004645  cmp     r10, r12
0x180004648  jz      short loc_180004658
0x18000464a  test    dword ptr [r10+1Ch], 400h
0x180004652  jnz     loc_180004C95
0x180004658  test    esi, esi
0x18000465a  js      loc_180004DB5
0x180004660  mov     [rbp+57h+var_9C], 1
0x180004667  mov     eax, [rbp+57h+var_78]
0x18000466a  test    al, 1
0x18000466c  jnz     loc_180004780
0x180004672  xor     r13d, r13d
0x180004675  mov     r15d, r13d
0x180004678  mov     [rbp+57h+var_58.Ptr], r13
0x18000467c  mov     qword ptr [rbp+57h+var_90.Data1], r13
0x180004680  cmp     r10, r12
0x180004683  jz      short loc_180004693
0x180004685  test    dword ptr [r10+1Ch], 400h
0x18000468d  jnz     loc_180004CB6
0x180004693  mov     rax, [rbx+44h]
0x180004697  sub     rax, qword ptr cs:xmmword_18001E7E0
0x18000469e  jnz     short loc_1800046AB
0x1800046a0  mov     rax, [rbx+4Ch]
0x1800046a4  sub     rax, qword ptr cs:xmmword_18001E7E0+8
0x1800046ab  test    rax, rax
0x1800046ae  jz      loc_180004CD7
0x1800046b4  mov     esi, [rbx+40h]
0x1800046b7  mov     rcx, [rbx+58h]
0x1800046bb  mov     rax, [rcx]
0x1800046be  mov     rax, [rax+18h]
0x1800046c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c7  lea     r9, [rbp+57h+var_58]
0x1800046cb  mov     r8d, esi
0x1800046ce  mov     edx, 2000000h
0x1800046d3  mov     rcx, rax
0x1800046d6  call    cs:__imp_SamOpenUser
0x1800046dc  mov     esi, eax
0x1800046de  test    eax, eax
0x1800046e0  js      loc_18000499B
0x1800046e6  lea     r8, [rbp+57h+var_90]
0x1800046ea  mov     edx, 1Ch
0x1800046ef  mov     rcx, [rbp+57h+var_58.Ptr]
0x1800046f3  call    cs:__imp_SamQueryInformationUser
0x1800046f9  mov     esi, eax
0x1800046fb  test    eax, eax
0x1800046fd  js      loc_180004D17
0x180004703  mov     esi, r13d
0x180004706  mov     rcx, qword ptr [rbp+57h+var_90.Data1]
0x18000470a  test    dword ptr [rcx], 100000h
0x180004710  jz      short loc_180004721
0x180004712  cmp     [rcx+80h], r13d
0x180004719  jz      short loc_180004721
0x18000471b  mov     r15d, 1
0x180004721  mov     r10, cs:WPP_GLOBAL_Control
0x180004728  mov     rcx, [rbp+57h+var_58.Ptr]
0x18000472c  test    rcx, rcx
0x18000472f  jz      short loc_18000473E
0x180004731  call    cs:__imp_SamCloseHandle
0x180004737  mov     r10, cs:WPP_GLOBAL_Control
0x18000473e  mov     rcx, qword ptr [rbp+57h+var_90.Data1]
0x180004742  test    rcx, rcx
0x180004745  jz      short loc_180004754
0x180004747  call    cs:__imp_SamFreeMemory
0x18000474d  mov     r10, cs:WPP_GLOBAL_Control
0x180004754  test    esi, esi
0x180004756  js      loc_180004B4D
0x18000475c  cmp     r10, r12
0x18000475f  jz      short loc_18000476F
0x180004761  test    dword ptr [r10+1Ch], 400h
0x180004769  jnz     loc_180004D34
0x18000476f  test    esi, esi
0x180004771  js      loc_180004D7F
0x180004777  test    r15d, r15d
0x18000477a  jz      loc_180004974
0x180004780  mov     r13d, [r14+48h]
0x180004784  lea     ecx, [r13+1]
0x180004788  cmp     ecx, 1
0x18000478b  jb      loc_180004D74
0x180004791  cmp     ecx, [r14+4Ch]
0x180004795  jbe     short loc_1800047E1
0x180004797  mov     esi, ecx
0x180004799  shr     esi, 1
0x18000479b  add     esi, 20h ; ' '
0x18000479e  add     esi, ecx
0x1800047a0  mov     r15, [r14+40h]
0x1800047a4  lea     r12d, ds:0[rsi*8]
0x1800047ac  call    cs:__imp_GetProcessHeap
0x1800047b2  xor     edx, edx; dwFlags
0x1800047b4  mov     rcx, rax; hHeap
0x1800047b7  test    r15, r15
0x1800047ba  jnz     loc_180004D55
0x1800047c0  mov     r8d, r12d; dwBytes
0x1800047c3  call    cs:__imp_HeapAlloc
0x1800047c9  test    rax, rax
0x1800047cc  jz      loc_180004D66
0x1800047d2  mov     [r14+40h], rax
0x1800047d6  mov     [r14+4Ch], esi
0x1800047da  lea     r12, WPP_GLOBAL_Control
0x1800047e1  lea     rsi, ds:0[r13*8]
0x1800047e9  mov     rdx, [r14+40h]
0x1800047ed  add     rdx, rsi; Src
0x1800047f0  mov     r8d, [r14+48h]
0x1800047f4  sub     r8d, r13d
0x1800047f7  shl     r8, 3; Size
0x1800047fb  lea     rcx, [rdx+8]; void *
0x1800047ff  call    memmove_0
0x180004804  mov     ecx, [r14+48h]
0x180004808  lea     eax, [rcx+1]
0x18000480b  mov     [r14+48h], eax
0x18000480f  mov     rdx, [r14+40h]
0x180004813  lea     rax, [rsi+rdx]
0x180004817  test    rax, rax
0x18000481a  jz      loc_180004D66
0x180004820  mov     [rdx+rcx*8], rbx
0x180004824  mov     rax, [rbx]
0x180004827  mov     rcx, rbx
0x18000482a  mov     rax, [rax+8]
0x18000482e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004833  mov     r15d, 1
0x180004839  mov     r10, cs:WPP_GLOBAL_Control
0x180004840  xor     r13d, r13d
0x180004843  mov     esi, r13d
0x180004846  test    r15d, r15d
0x180004849  mov     eax, 8007000Eh
0x18000484e  cmovz   esi, eax
0x180004851  test    rbx, rbx
0x180004854  jz      short loc_18000486F
0x180004856  mov     rcx, rbx
0x180004859  mov     rbx, r13
0x18000485c  mov     rax, [rcx]
0x18000485f  mov     rax, [rax+10h]
0x180004863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004868  mov     r10, cs:WPP_GLOBAL_Control
0x18000486f  test    r15d, r15d
0x180004872  jz      loc_180004D9A
0x180004878  xor     r9d, r9d
0x18000487b  mov     r12, [rbp+57h+var_68]
0x18000487f  mov     r15, [rbp+57h+var_70]
0x180004883  mov     r8, [rbp+57h+var_98]
0x180004887  mov     eax, [rbp+57h+var_A0]
0x18000488a  inc     eax
0x18000488c  jmp     loc_180004595
0x180004891  cmp     [rbp+57h+var_9C], edi
0x180004894  jz      loc_1800049B4
0x18000489a  mov     rax, [r14]
0x18000489d  mov     r8, [rbp+57h+var_60]
0x1800048a1  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x1800048a8  mov     rcx, r14
0x1800048ab  mov     rax, [rax]
0x1800048ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b3  mov     esi, eax
0x1800048b5  test    eax, eax
0x1800048b7  js      loc_180004DE2
0x1800048bd  mov     r10, cs:WPP_GLOBAL_Control
0x1800048c4  test    r14, r14
0x1800048c7  jz      short loc_1800048DF
0x1800048c9  mov     rax, [r14]
0x1800048cc  mov     rcx, r14
0x1800048cf  mov     rax, [rax+10h]
0x1800048d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d8  mov     r10, cs:WPP_GLOBAL_Control
0x1800048df  lea     r14, WPP_GLOBAL_Control
0x1800048e6  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800048ed  jnz     loc_180004E21
0x1800048f3  mov     eax, 0D000000Dh
0x1800048f8  cmp     esi, eax
0x1800048fa  jz      loc_180004E42
0x180004900  mov     eax, 0D0000022h
0x180004905  cmp     esi, eax
0x180004907  jnz     loc_180004ADD
0x18000490d  mov     esi, 80070005h
0x180004912  cmp     r10, r14
0x180004915  jz      loc_180004AF4
0x18000491b  test    byte ptr [r10+1Ch], 4
0x180004920  jz      loc_180004AE1
0x180004926  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000492a  lea     r9, aCconnecteduser; "CConnectedUserStore::GetConnectedUserEn"...
0x180004931  mov     rcx, [r10+10h]
0x180004935  call    WPP_SF_sL
0x18000493a  mov     r10, cs:WPP_GLOBAL_Control
0x180004941  jmp     loc_180004AE1
0x180004946  mov     rdx, [r8]
0x180004949  mov     rax, [rdx+rcx+4]
0x18000494e  sub     rax, [rbp+57h+var_48.Ptr]
0x180004952  jnz     short loc_18000495D
0x180004954  mov     rax, [rdx+rcx+0Ch]
0x180004959  sub     rax, qword ptr [rbp+57h+var_48.Size]
0x18000495d  test    rax, rax
0x180004960  jz      loc_1800045BB
0x180004966  lea     r8, [r15+70h]
0x18000496a  mov     eax, [rbp+57h+var_A0]
0x18000496d  inc     eax
0x18000496f  jmp     loc_180004595
0x180004974  test    rbx, rbx
  ... truncated ...
```
