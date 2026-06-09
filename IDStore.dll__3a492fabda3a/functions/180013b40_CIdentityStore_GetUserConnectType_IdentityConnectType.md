# CIdentityStore::GetUserConnectType(_IdentityConnectType *)

- ea: `0x180013b40`
- end: `0x180013fed`
- name: `?GetUserConnectType@CIdentityStore@@UEAAJPEAW4_IdentityConnectType@@@Z`
- size: `1197`
- prototype: `__int64 __fastcall(void **this, enum _IdentityConnectType *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001b88`
- `0x180001bf4`
- `0x180002c80`
- `0x180003290`
- `0x180003560`
- `0x18000acb0`
- `0x18000d620`
- `0x18000dff0`
- `0x180013b40`
- `0x180014430`
- `0x18001448c`
- `0x1800144b4`
- `0x180014618`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013cbd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dbf`
- `ntdll!RtlLengthSid` at `0x180013d39`
- `ntdll!RtlLengthSid` at `0x180013d39`

## pseudocode

```c
__int64 __fastcall CIdentityStore::GetUserConnectType(void **this, enum _IdentityConnectType *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rdx
  int v6; // ecx
  __int64 v7; // r8
  int v8; // r9d
  CIdentityProfileHandler *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int IsCallerLocalUser; // eax
  HANDLE *v13; // rdi
  int CallerTokenUserSid; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  CIdentityProfileHandler *v17; // rcx
  __int64 v18; // rdx
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, _QWORD, _QWORD, _QWORD); // rbx
  ULONG v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // r8
  CIdentityProfileHandler *v26; // rcx
  __int64 v27; // rdx
  CIdentityProfileHandler *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-60h]
  int v33; // [rsp+30h] [rbp-50h] BYREF
  bool v34; // [rsp+34h] [rbp-4Ch] BYREF
  LPVOID v35; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v38[16]; // [rsp+50h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+60h] [rbp-20h] BYREF

  v2 = 0;
  v33 = 0;
  v37 = 0;
  v34 = 0;
  CLogBlock::CLogBlock((CLogBlock *)v38, "CIdentityStore::GetUserConnectType", &v33);
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, (int)&GetConnectTypeStart, v7, v8, &v39);
  if ( a2 )
  {
    *(_DWORD *)a2 = 0;
    IsCallerLocalUser = CIdentityStore::IsCallerLocalUser(&v34);
    v33 = IsCallerLocalUser;
    if ( IsCallerLocalUser < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_70;
      }
      v10 = 86;
      goto LABEL_12;
    }
    v13 = this + 16;
    IsCallerLocalUser = LockPerUserIdStore(this + 16);
    v33 = IsCallerLocalUser;
    if ( IsCallerLocalUser < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_70;
      }
      v10 = 87;
LABEL_12:
      v11 = (unsigned int)IsCallerLocalUser;
      goto LABEL_7;
    }
    if ( v34 )
    {
      v35 = 0;
      pv = 0;
      CallerTokenUserSid = CoCreateInstance(
                             &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
                             0,
                             0x17u,
                             &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
                             &v35);
      v33 = CallerTokenUserSid;
      if ( CallerTokenUserSid < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_27;
        }
        v18 = 88;
LABEL_26:
        WPP_SF_d(
          *((_QWORD *)v17 + 2),
          v18,
          WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
          (unsigned int)CallerTokenUserSid);
LABEL_27:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
        goto LABEL_69;
      }
      CallerTokenUserSid = GetCallerTokenUserSid((struct _TOKEN_USER **)&pv, v15, v16);
      v33 = CallerTokenUserSid;
      if ( CallerTokenUserSid < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_27;
        }
        v18 = 89;
        goto LABEL_26;
      }
      v19 = v35;
      v20 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v35 + 56LL);
      v21 = RtlLengthSid(*(PSID *)pv);
      v22 = v20(v19, *(_QWORD *)pv, v21, 0);
      v2 = 0;
      v33 = v22;
      if ( v22 < 0 )
      {
        if ( v22 != -805305819
          && WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            91,
            WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
            (unsigned int)v22);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids);
        }
        *(_DWORD *)a2 = 2;
      }
      v33 = 0;
      CoTaskMemFree(pv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
      v13 = this + 16;
    }
    if ( *(_DWORD *)a2 )
      goto LABEL_69;
    v23 = (*((__int64 (__fastcall **)(char *, unsigned int *))*(this - 1) + 3))((char *)this - 8, &v37);
    v33 = v23;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          92,
          WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
          (unsigned int)v23);
      }
LABEL_69:
      UnlockPerUserIdStore(*v13);
      goto LABEL_70;
    }
    while ( 1 )
    {
      if ( v2 >= v37 )
      {
LABEL_68:
        v33 = 0;
        goto LABEL_69;
      }
      v39.Ptr = 0;
      v35 = 0;
      LODWORD(pv) = 0;
      v24 = (*((__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID *))*(this - 1) + 4))(
              (char *)this - 8,
              v2,
              0,
              &v35);
      v33 = v24;
      if ( v24 >= 0 )
      {
        if ( v35 )
        {
          ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(
            (__int64 *)&v39,
            (void (__fastcall ***)(_QWORD, GUID *, __int64 *))v35,
            v25);
          if ( v39.Ptr )
          {
            v24 = (*(__int64 (__fastcall **)(ULONGLONG, LPVOID *))(*(_QWORD *)v39.Ptr + 40LL))(v39.Ptr, &pv);
            v33 = v24;
            if ( v24 >= 0 )
            {
              if ( (_DWORD)pv )
              {
                if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v2);
                }
                *(_DWORD *)a2 = 1;
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v39);
                goto LABEL_68;
              }
            }
            else
            {
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v27 = 96;
                goto LABEL_48;
              }
            }
          }
          else
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v29 = 95;
              goto LABEL_53;
            }
          }
        }
        else
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v29 = 94;
LABEL_53:
            WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v2);
          }
        }
      }
      else
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v27 = 93;
LABEL_48:
          LODWORD(ppv) = v24;
          WPP_SF_dd(*((_QWORD *)v26 + 2), v27, v25, v2, ppv);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v39);
      ++v2;
    }
  }
  v33 = -2147467261;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v10 = 85;
    v11 = 2147500035LL;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v11);
  }
LABEL_70:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)v9, (int)&GetConnectTypeStop, v7, v8, &v39);
  v30 = v33;
  CLogBlock::~CLogBlock((CLogBlock *)v38, v5, v7);
  return v30;
}

```

## disassembly

```asm
0x180013b40  mov     [rsp-38h+arg_10], rbx
0x180013b45  push    rbp
0x180013b46  push    rsi
0x180013b47  push    rdi
0x180013b48  push    r12
0x180013b4a  push    r13
0x180013b4c  push    r14
0x180013b4e  push    r15
0x180013b50  mov     rbp, rsp
0x180013b53  sub     rsp, 80h
0x180013b5a  mov     rax, cs:__security_cookie
0x180013b61  xor     rax, rsp
0x180013b64  mov     [rbp+var_10], rax
0x180013b68  xor     ebx, ebx
0x180013b6a  lea     r8, [rbp+var_50]; int *
0x180013b6e  mov     r12, rdx
0x180013b71  mov     [rbp+var_50], ebx
0x180013b74  mov     r13, rcx
0x180013b77  mov     [rbp+var_38], ebx
0x180013b7a  lea     rdx, aCidentitystore_2; "CIdentityStore::GetUserConnectType"
0x180013b81  mov     [rbp+var_4C], bl
0x180013b84  lea     rcx, [rbp+var_30]; this
0x180013b88  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x180013b8d  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180013b94  jz      short loc_180013BAB
0x180013b96  lea     rax, [rbp+var_20]
0x180013b9a  lea     rdx, GetConnectTypeStart; int
0x180013ba1  mov     [rsp+80h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x180013ba6  call    McGenEventWrite_EventWriteTransfer
0x180013bab  test    r12, r12
0x180013bae  jnz     short loc_180013BFB
0x180013bb0  mov     [rbp+var_50], 80004003h
0x180013bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bbe  lea     rsi, WPP_GLOBAL_Control
0x180013bc5  cmp     rcx, rsi
0x180013bc8  jz      loc_180013F9A
0x180013bce  mov     r14b, 4
0x180013bd1  test    [rcx+1Ch], r14b
0x180013bd5  jz      loc_180013F9A
0x180013bdb  lea     edx, [r12+55h]
0x180013be0  mov     r9d, 80004003h
0x180013be6  mov     rcx, [rcx+10h]
0x180013bea  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180013bf1  call    WPP_SF_d
0x180013bf6  jmp     loc_180013F9A
0x180013bfb  lea     rcx, [rbp+var_4C]; bool *
0x180013bff  mov     [r12], ebx
0x180013c03  call    ?IsCallerLocalUser@CIdentityStore@@CAJPEA_N@Z; CIdentityStore::IsCallerLocalUser(bool *)
0x180013c08  mov     [rbp+var_50], eax
0x180013c0b  test    eax, eax
0x180013c0d  jns     short loc_180013C3D
0x180013c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c16  lea     rsi, WPP_GLOBAL_Control
0x180013c1d  cmp     rcx, rsi
0x180013c20  jz      loc_180013F9A
0x180013c26  mov     r14b, 4
0x180013c29  test    [rcx+1Ch], r14b
0x180013c2d  jz      loc_180013F9A
0x180013c33  mov     edx, 56h ; 'V'
0x180013c38  mov     r9d, eax
0x180013c3b  jmp     short loc_180013BE6
0x180013c3d  lea     rdi, [r13+80h]
0x180013c44  mov     rcx, rdi; void **
0x180013c47  call    ?LockPerUserIdStore@@YAJPEAPEAX@Z; LockPerUserIdStore(void * *)
0x180013c4c  mov     [rbp+var_50], eax
0x180013c4f  test    eax, eax
0x180013c51  jns     short loc_180013C7E
0x180013c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c5a  lea     rsi, WPP_GLOBAL_Control
0x180013c61  cmp     rcx, rsi
0x180013c64  jz      loc_180013F9A
0x180013c6a  mov     r14b, 4
0x180013c6d  test    [rcx+1Ch], r14b
0x180013c71  jz      loc_180013F9A
0x180013c77  mov     edx, 57h ; 'W'
0x180013c7c  jmp     short loc_180013C38
0x180013c7e  lea     rsi, WPP_GLOBAL_Control
0x180013c85  mov     r14b, 4
0x180013c88  lea     r15, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180013c8f  cmp     [rbp+var_4C], bl
0x180013c92  jz      loc_180013DD5
0x180013c98  xor     edx, edx; pUnkOuter
0x180013c9a  mov     [rbp+var_48], rbx
0x180013c9e  lea     rax, [rbp+var_48]
0x180013ca2  mov     [rbp+pv], rbx
0x180013ca6  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180013cad  mov     [rsp+80h+ppv], rax; ppv
0x180013cb2  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180013cb9  lea     r8d, [rdx+17h]; dwClsContext
0x180013cbd  call    cs:__imp_CoCreateInstance
0x180013cc3  mov     [rbp+var_50], eax
0x180013cc6  test    eax, eax
0x180013cc8  jns     short loc_180013CE3
0x180013cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cd1  cmp     rcx, rsi
0x180013cd4  jz      short loc_180013D19
0x180013cd6  test    [rcx+1Ch], r14b
0x180013cda  jz      short loc_180013D19
0x180013cdc  mov     edx, 58h ; 'X'
0x180013ce1  jmp     short loc_180013D0A
0x180013ce3  lea     rcx, [rbp+pv]; struct _TOKEN_USER **
0x180013ce7  call    ?GetCallerTokenUserSid@@YAJPEAPEAU_TOKEN_USER@@@Z; GetCallerTokenUserSid(_TOKEN_USER * *)
0x180013cec  mov     [rbp+var_50], eax
0x180013cef  test    eax, eax
0x180013cf1  jns     short loc_180013D27
0x180013cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cfa  cmp     rcx, rsi
0x180013cfd  jz      short loc_180013D19
0x180013cff  test    [rcx+1Ch], r14b
0x180013d03  jz      short loc_180013D19
0x180013d05  mov     edx, 59h ; 'Y'
0x180013d0a  mov     rcx, [rcx+10h]
0x180013d0e  mov     r9d, eax
0x180013d11  mov     r8, r15
0x180013d14  call    WPP_SF_d
0x180013d19  lea     rcx, [rbp+var_48]
0x180013d1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013d22  jmp     loc_180013F92
0x180013d27  mov     rdi, [rbp+var_48]
0x180013d2b  mov     rcx, [rbp+pv]
0x180013d2f  mov     rax, [rdi]
0x180013d32  mov     rcx, [rcx]; Sid
0x180013d35  mov     rbx, [rax+38h]
0x180013d39  call    cs:__imp_RtlLengthSid
0x180013d3f  xor     r9d, r9d
0x180013d42  mov     rcx, rdi
0x180013d45  mov     r8d, eax
0x180013d48  mov     rax, [rbp+pv]
0x180013d4c  mov     rdx, [rax]
0x180013d4f  mov     rax, rbx
0x180013d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d57  xor     ebx, ebx
0x180013d59  mov     [rbp+var_50], eax
0x180013d5c  test    eax, eax
0x180013d5e  js      short loc_180013D8B
0x180013d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d67  cmp     rcx, rsi
0x180013d6a  jz      short loc_180013D81
0x180013d6c  test    byte ptr [rcx+1Ch], 10h
0x180013d70  jz      short loc_180013D81
0x180013d72  mov     rcx, [rcx+10h]
0x180013d76  lea     edx, [rbx+5Ah]
0x180013d79  mov     r8, r15
0x180013d7c  call    WPP_SF_
0x180013d81  mov     dword ptr [r12], 2
0x180013d89  jmp     short loc_180013DB8
0x180013d8b  cmp     eax, 0D0000225h
0x180013d90  jz      short loc_180013DB8
0x180013d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d99  cmp     rcx, rsi
0x180013d9c  jz      short loc_180013DB8
0x180013d9e  test    [rcx+1Ch], r14b
0x180013da2  jz      short loc_180013DB8
0x180013da4  mov     rcx, [rcx+10h]
0x180013da8  mov     edx, 5Bh ; '['
0x180013dad  mov     r9d, eax
0x180013db0  mov     r8, r15
0x180013db3  call    WPP_SF_d
0x180013db8  mov     rcx, [rbp+pv]; pv
0x180013dbc  mov     [rbp+var_50], ebx
0x180013dbf  call    cs:__imp_CoTaskMemFree
0x180013dc5  lea     rcx, [rbp+var_48]
0x180013dc9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dce  lea     rdi, [r13+80h]
0x180013dd5  cmp     [r12], ebx
0x180013dd9  jnz     loc_180013F92
0x180013ddf  mov     rax, [r13-8]
0x180013de3  lea     rdx, [rbp+var_38]
0x180013de7  lea     rcx, [r13-8]
0x180013deb  mov     rax, [rax+18h]
0x180013def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df4  mov     [rbp+var_50], eax
0x180013df7  test    eax, eax
0x180013df9  jns     short loc_180013E2E
0x180013dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e02  cmp     rcx, rsi
0x180013e05  jz      loc_180013F92
0x180013e0b  test    [rcx+1Ch], r14b
0x180013e0f  jz      loc_180013F92
0x180013e15  mov     rcx, [rcx+10h]
0x180013e19  mov     edx, 5Ch ; '\'
0x180013e1e  mov     r9d, eax
0x180013e21  mov     r8, r15
0x180013e24  call    WPP_SF_d
0x180013e29  jmp     loc_180013F92
0x180013e2e  cmp     ebx, [rbp+var_38]
0x180013e31  jnb     loc_180013F8B
0x180013e37  xor     eax, eax
0x180013e39  lea     r9, [rbp+var_48]
0x180013e3d  mov     [rbp+var_20.Ptr], rax
0x180013e41  lea     rcx, [r13-8]
0x180013e45  mov     [rbp+var_48], rax
0x180013e49  xor     r8d, r8d
0x180013e4c  mov     dword ptr [rbp+pv], eax
0x180013e4f  mov     edx, ebx
0x180013e51  mov     rax, [r13-8]
0x180013e55  mov     rax, [rax+20h]
0x180013e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5e  mov     [rbp+var_50], eax
0x180013e61  test    eax, eax
0x180013e63  jns     short loc_180013E99
0x180013e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e6c  cmp     rcx, rsi
0x180013e6f  jz      loc_180013F32
0x180013e75  test    [rcx+1Ch], r14b
0x180013e79  jz      loc_180013F32
0x180013e7f  mov     edx, 5Dh ; ']'
0x180013e84  mov     rcx, [rcx+10h]
0x180013e88  mov     r9d, ebx
0x180013e8b  mov     dword ptr [rsp+80h+ppv], eax
0x180013e8f  call    WPP_SF_dd
0x180013e94  jmp     loc_180013F32
0x180013e99  mov     rdx, [rbp+var_48]
0x180013e9d  test    rdx, rdx
0x180013ea0  jnz     short loc_180013ECE
0x180013ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ea9  cmp     rcx, rsi
0x180013eac  jz      loc_180013F32
0x180013eb2  test    [rcx+1Ch], r14b
0x180013eb6  jz      short loc_180013F32
0x180013eb8  mov     edx, 5Eh ; '^'
0x180013ebd  mov     rcx, [rcx+10h]
0x180013ec1  mov     r9d, ebx
0x180013ec4  mov     r8, r15
0x180013ec7  call    WPP_SF_d
0x180013ecc  jmp     short loc_180013F32
0x180013ece  lea     rcx, [rbp+var_20]
0x180013ed2  call    ??4?$CComQIPtr@UIConnectedIdentityProvider@@$1?_GUID_b7417b54_e08c_429b_96c8_678d1369ecb1@@3U__s_GUID@@B@ATL@@QEAAPEAUIConnectedIdentityProvider@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(IUnknown *)
0x180013ed7  mov     rcx, [rbp+var_20.Ptr]
0x180013edb  test    rcx, rcx
0x180013ede  jnz     short loc_180013EF9
0x180013ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee7  cmp     rcx, rsi
0x180013eea  jz      short loc_180013F32
0x180013eec  test    [rcx+1Ch], r14b
0x180013ef0  jz      short loc_180013F32
0x180013ef2  mov     edx, 5Fh ; '_'
0x180013ef7  jmp     short loc_180013EBD
0x180013ef9  mov     rax, [rcx]
0x180013efc  lea     rdx, [rbp+pv]
0x180013f00  mov     rax, [rax+28h]
0x180013f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f09  mov     [rbp+var_50], eax
0x180013f0c  test    eax, eax
0x180013f0e  jns     short loc_180013F2C
0x180013f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f17  cmp     rcx, rsi
0x180013f1a  jz      short loc_180013F32
0x180013f1c  test    [rcx+1Ch], r14b
0x180013f20  jz      short loc_180013F32
0x180013f22  mov     edx, 60h ; '`'
0x180013f27  jmp     loc_180013E84
0x180013f2c  cmp     dword ptr [rbp+pv], 0
0x180013f30  jnz     short loc_180013F4B
0x180013f32  lea     rcx, [rbp+var_48]
0x180013f36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013f3b  lea     rcx, [rbp+var_20]
0x180013f3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013f44  inc     ebx
0x180013f46  jmp     loc_180013E2E
0x180013f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f52  cmp     rcx, rsi
0x180013f55  jz      short loc_180013F71
0x180013f57  test    byte ptr [rcx+1Ch], 10h
0x180013f5b  jz      short loc_180013F71
0x180013f5d  mov     rcx, [rcx+10h]
0x180013f61  mov     edx, 61h ; 'a'
0x180013f66  mov     r9d, ebx
0x180013f69  mov     r8, r15
0x180013f6c  call    WPP_SF_d
0x180013f71  lea     rcx, [rbp+var_48]
0x180013f75  mov     dword ptr [r12], 1
0x180013f7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013f82  lea     rcx, [rbp+var_20]
0x180013f86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013f8b  mov     [rbp+var_50], 0
0x180013f92  mov     rcx, [rdi]; hMutex
0x180013f95  call    ?UnlockPerUserIdStore@@YAXPEAX@Z; UnlockPerUserIdStore(void *)
0x180013f9a  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180013fa1  jz      short loc_180013FB8
0x180013fa3  lea     rax, [rbp+var_20]
0x180013fa7  lea     rdx, GetConnectTypeStop; int
0x180013fae  mov     [rsp+80h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x180013fb3  call    McGenEventWrite_EventWriteTransfer
0x180013fb8  mov     ebx, [rbp+var_50]
0x180013fbb  lea     rcx, [rbp+var_30]; this
0x180013fbf  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180013fc4  mov     eax, ebx
0x180013fc6  mov     rcx, [rbp+var_10]
0x180013fca  xor     rcx, rsp; StackCookie
0x180013fcd  call    __security_check_cookie
0x180013fd2  mov     rbx, [rsp+80h+arg_10]
0x180013fda  add     rsp, 80h
0x180013fe1  pop     r15
0x180013fe3  pop     r14
0x180013fe5  pop     r13
0x180013fe7  pop     r12
0x180013fe9  pop     rdi
0x180013fea  pop     rsi
0x180013feb  pop     rbp
  ... truncated ...
```
