# FAXStartServerNotificationInternal

- ea: `0x140011fa0`
- end: `0x14001280d`
- name: `FAXStartServerNotificationInternal`
- size: `2157`
- prototype: `__int64 __fastcall(void *, wchar_t *, wchar_t *, unsigned __int16 *, struct _OVERLAPPED *, wchar_t *String1, int, int, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140022d90`
- `0x140022e40`

## callees

- `0x140001bac`
- `0x1400023ec`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004eb0`
- `0x140011fa0`
- `0x1400264ac`
- `0x14002e3d4`
- `0x140047d20`
- `0x140048284`
- `0x140051dec`
- `0x14005757c`
- `0x14005770c`
- `0x140057818`
- `0x140057ad8`
- `0x140058108`
- `0x14005af4c`
- `0x14006998c`
- `0x1400799cc`
- `0x140079adc`
- `0x14007ab38`
- `0x140086e8e`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012335`
- `KERNEL32!GetLastError` at `0x14001264e`
- `KERNEL32!GetLastError` at `0x140012335`
- `KERNEL32!GetLastError` at `0x14001264e`
- `KERNEL32!EnterCriticalSection` at `0x1400123e2`
- `KERNEL32!EnterCriticalSection` at `0x1400123e2`
- `KERNEL32!LeaveCriticalSection` at `0x140012784`
- `KERNEL32!LeaveCriticalSection` at `0x140012784`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14001263e`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14001263e`
- `RPCRT4!RpcBindingFree` at `0x140012700`
- `RPCRT4!RpcBindingFree` at `0x140012700`

## pseudocode

```c
__int64 __fastcall FAXStartServerNotificationInternal(
        void *a1,
        wchar_t *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        struct _OVERLAPPED *a5,
        wchar_t *String1,
        int a7,
        int a8,
        unsigned int a9,
        unsigned __int16 **a10)
{
  __int64 result; // rax
  unsigned int v14; // eax
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  CMapDeviceId *v17; // rcx
  __int64 v18; // rdx
  CMapDeviceId *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // edi
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  wchar_t *v25; // rdi
  void *ClientUserSID; // rax
  DWORD LastError; // eax
  struct _OVERLAPPED *v28; // r13
  int v29; // eax
  unsigned int v30; // eax
  unsigned __int16 *v31; // r12
  CMapDeviceId *v32; // rcx
  __int64 v33; // rdx
  void *v34; // rax
  __int64 v35; // rdx
  RPC_WSTR v36; // rdi
  CMapDeviceId *v37; // rcx
  __int64 v38; // rdx
  void *v39; // rax
  __int64 v40; // rdx
  CClientID *v41; // rax
  CClientsMap *v42; // rcx
  unsigned int v43; // eax
  DWORD v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // [rsp+50h] [rbp-1A8h] BYREF
  unsigned int v47; // [rsp+54h] [rbp-1A4h]
  LPVOID lpMem; // [rsp+58h] [rbp-1A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-198h] BYREF
  RPC_WSTR Endpoint; // [rsp+68h] [rbp-190h]
  struct _OVERLAPPED *v51; // [rsp+70h] [rbp-188h]
  wchar_t *String2; // [rsp+78h] [rbp-180h]
  void *v53; // [rsp+80h] [rbp-178h]
  unsigned __int16 **v54; // [rsp+88h] [rbp-170h]
  void *v55; // [rsp+90h] [rbp-168h]
  char v56[80]; // [rsp+A0h] [rbp-158h] BYREF
  _BYTE v57[192]; // [rsp+F0h] [rbp-108h] BYREF

  Endpoint = a4;
  String2 = a3;
  v53 = a1;
  v51 = a5;
  v47 = a9;
  v54 = a10;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 542, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  Binding = 0;
  v46 = 0;
  LODWORD(lpMem) = 0;
  result = FaxSvcAccessCheck(0x2000000u, (int *)&lpMem, &v46, 1);
  if ( (_DWORD)result )
    return result;
  v14 = v46;
  if ( (v46 & 0xE03FF) == 0 )
    return 5;
  if ( !a4 || !a3 || !v54 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v16 = 543;
LABEL_148:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  if ( v47 > 1 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 544, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v47);
    }
    return 87;
  }
  if ( a7 )
  {
    if ( (a8 & 0x3FF) == 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v16 = 545;
      goto LABEL_148;
    }
    if ( (a8 & 0xFFFFFC00) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v16 = 546;
      goto LABEL_148;
    }
  }
  if ( a2 )
  {
    if ( !(unsigned int)ValidFaxAccountName(a2) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v18 = 548;
      goto LABEL_84;
    }
    v14 = v46;
  }
  if ( a7 != 1 )
  {
    LODWORD(lpMem) = 0;
    if ( a8 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v20 = 551;
    }
    else
    {
      v21 = IsLocalRPCConnectionNP(&lpMem);
      v22 = v21;
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 552, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v21);
        }
        return v22;
      }
      if ( (_DWORD)lpMem )
        goto LABEL_65;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v20 = 553;
    }
LABEL_51:
    WPP_SF_(*((_QWORD *)v19 + 2), v20, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 5;
  }
  if ( (a8 & 0x201) != 0 && !(unsigned int)CanAccessUnAssignedFaxes(v14, 1) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 5;
    }
    v20 = 549;
    goto LABEL_51;
  }
  if ( (a8 & 0x10C) != 0 && (v46 & 0x20) == 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 5;
    }
    v20 = 550;
    goto LABEL_51;
  }
LABEL_65:
  v23 = -1;
  v24 = -1;
  v25 = String2;
  do
    ++v24;
  while ( String2[v24] );
  if ( v24 <= 0xF )
  {
    do
      ++v23;
    while ( a4[v23] );
    if ( v23 < 0xB )
    {
      ClientUserSID = GetClientUserSID();
      lpMem = ClientUserSID;
      if ( !ClientUserSID )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            555,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError);
        }
LABEL_75:
        if ( v22 == 8 || v22 == 14 )
          return 7001;
        return v22;
      }
      if ( a2 && !(unsigned int)SameNTUser(a2, ClientUserSID) )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 87;
        }
        v18 = 556;
LABEL_84:
        WPP_SF_S(*((_QWORD *)v17 + 2), v18, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a2);
        return 87;
      }
      v28 = 0;
      EnterCriticalSection(&g_CsClients);
      v29 = wcsncmp_0(String1, L"ncalrpc", 7u);
      v30 = RpcBindToFaxClient(v25, Endpoint, v29 == 0, &Binding);
      v22 = v30;
      if ( v30 )
      {
        v31 = 0;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_126;
        }
        v33 = 557;
        goto LABEL_90;
      }
      v34 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v55 = v34;
      v36 = Endpoint;
      if ( v34 )
        v31 = (unsigned __int16 *)CClientID::CClientID(v34, v35, String2, Endpoint, v51);
      else
        v31 = 0;
      Endpoint = v31;
      if ( v31 )
      {
        v39 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        v55 = v39;
        if ( v39 )
          v28 = (struct _OVERLAPPED *)CClientID::CClientID(v39, v40, String2, v36, v51);
        else
          v28 = 0;
        v51 = v28;
        if ( v28 )
        {
          FindClientAPIVersion(v53);
          v53 = Binding;
          v41 = CClientID::CClientID((CClientID *)v56, (const struct CClientID *)v31);
          CClient::CClient(v57, v41, lpMem);
          v43 = CClientsMap::AddClient(v42, (const struct CClient *)v57);
          v22 = v43;
          if ( v43 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 560, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v43);
            }
            CClient::~CClient((CClient *)v57);
            goto LABEL_126;
          }
          Binding = 0;
          CClient::~CClient((CClient *)v57);
          if ( !PostQueuedCompletionStatus(g_hSendEventsCompPort, 8u, 3u, v28) )
          {
            v44 = GetLastError();
            v22 = v44;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 562, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v44);
            }
            v30 = CClientsMap::ReleaseClient(g_pClientsMap, (const struct CClientID *)v31, 0);
            if ( !v30 )
              goto LABEL_126;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_126;
            }
            v33 = 563;
LABEL_90:
            WPP_SF_d(*((_QWORD *)v32 + 2), v33, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v30);
            goto LABEL_126;
          }
          v28 = 0;
          *v54 = v31;
          v31 = 0;
LABEL_126:
          if ( Binding )
          {
            v45 = RpcBindingFree(&Binding);
            if ( v45 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  564,
                  &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                  v45);
              }
            }
          }
          if ( v31 )
          {
            memset_0(v31, 0, 0x50u);
            operator delete(v31);
          }
          if ( v28 )
          {
            memset_0(v28, 0, 0x50u);
            operator delete(v28);
          }
          if ( !v22 )
            ++g_dwlClientID;
          LeaveCriticalSection(&g_CsClients);
          pMemFree(lpMem);
          goto LABEL_75;
        }
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_100:
          v22 = 14;
          goto LABEL_126;
        }
        v38 = 559;
      }
      else
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_100;
        }
        v38 = 558;
      }
      WPP_SF_(*((_QWORD *)v37 + 2), v38, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      goto LABEL_100;
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      554,
      (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
      (_DWORD)String2,
      (__int64)a4);
  }
  return 11;
}

```

## disassembly

```asm
0x140011fa0  push    rbx
0x140011fa2  push    rsi
0x140011fa3  push    rdi
0x140011fa4  push    r12
0x140011fa6  push    r13
0x140011fa8  push    r14
0x140011faa  push    r15
0x140011fac  sub     rsp, 1C0h
0x140011fb3  mov     rax, cs:__security_cookie
0x140011fba  xor     rax, rsp
0x140011fbd  mov     [rsp+1F8h+var_48], rax
0x140011fc5  mov     r13, r9
0x140011fc8  mov     [rsp+1F8h+Endpoint], r9
0x140011fcd  mov     rdi, r8
0x140011fd0  mov     [rsp+1F8h+String2], r8
0x140011fd5  mov     r12, rdx
0x140011fd8  mov     [rsp+1F8h+var_178], rcx
0x140011fe0  mov     rax, [rsp+1F8h+arg_20]
0x140011fe8  mov     [rsp+1F8h+var_188], rax
0x140011fed  mov     eax, [rsp+1F8h+arg_40]
0x140011ff4  mov     [rsp+1F8h+var_1A4], eax
0x140011ff8  mov     rax, [rsp+1F8h+arg_48]
0x140012000  mov     [rsp+1F8h+var_170], rax
0x140012008  lea     r15, WPP_GLOBAL_Control
0x14001200f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012016  mov     sil, 4
0x140012019  cmp     rcx, r15
0x14001201c  jz      short loc_140012044
0x14001201e  test    [rcx+1Ch], sil
0x140012022  jz      short loc_140012044
0x140012024  lea     r14, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001202b  cmp     byte ptr [rcx+19h], 5
0x14001202f  jb      short loc_14001204B
0x140012031  mov     edx, 21Eh
0x140012036  mov     r8, r14
0x140012039  mov     rcx, [rcx+10h]
0x14001203d  call    WPP_SF_
0x140012042  jmp     short loc_14001204B
0x140012044  lea     r14, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001204b  xor     ebx, ebx
0x14001204d  mov     [rsp+1F8h+Binding], rbx
0x140012052  mov     [rsp+1F8h+var_1A8], ebx
0x140012056  mov     dword ptr [rsp+1F8h+lpMem], ebx
0x14001205a  lea     r9d, [rbx+1]; int
0x14001205e  lea     r8, [rsp+1F8h+var_1A8]; unsigned int *
0x140012063  lea     rdx, [rsp+1F8h+lpMem]; int *
0x140012068  mov     ecx, 2000000h; unsigned int
0x14001206d  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140012072  test    eax, eax
0x140012074  jnz     loc_14001225E
0x14001207a  mov     eax, [rsp+1F8h+var_1A8]
0x14001207e  test    eax, 0E03FFh
0x140012083  jz      loc_140012259
0x140012089  test    r13, r13
0x14001208c  jz      loc_1400127DA
0x140012092  test    rdi, rdi
0x140012095  jz      loc_1400127DA
0x14001209b  cmp     [rsp+1F8h+var_170], rbx
0x1400120a3  jz      loc_1400127DA
0x1400120a9  mov     r8d, [rsp+1F8h+var_1A4]
0x1400120ae  cmp     r8d, 1
0x1400120b2  jbe     short loc_1400120F1
0x1400120b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120bb  cmp     rcx, r15
0x1400120be  jz      loc_140012803
0x1400120c4  test    [rcx+1Ch], sil
0x1400120c8  jz      loc_140012803
0x1400120ce  cmp     byte ptr [rcx+19h], 2
0x1400120d2  jb      loc_140012803
0x1400120d8  mov     edx, 220h
0x1400120dd  mov     r9d, r8d
0x1400120e0  mov     r8, r14
0x1400120e3  mov     rcx, [rcx+10h]
0x1400120e7  call    WPP_SF_d
0x1400120ec  jmp     loc_140012803
0x1400120f1  mov     edi, [rsp+1F8h+arg_38]
0x1400120f8  cmp     [rsp+1F8h+arg_30], ebx
0x1400120ff  jz      short loc_14001216D
0x140012101  test    edi, 3FFh
0x140012107  jnz     short loc_140012137
0x140012109  mov     rcx, cs:WPP_GLOBAL_Control
0x140012110  cmp     rcx, r15
0x140012113  jz      loc_140012803
0x140012119  test    [rcx+1Ch], sil
0x14001211d  jz      loc_140012803
0x140012123  cmp     byte ptr [rcx+19h], 2
0x140012127  jb      loc_140012803
0x14001212d  mov     edx, 221h
0x140012132  jmp     loc_1400127F7
0x140012137  test    edi, 0FFFFFC00h
0x14001213d  jz      short loc_14001216D
0x14001213f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012146  cmp     rcx, r15
0x140012149  jz      loc_140012803
0x14001214f  test    [rcx+1Ch], sil
0x140012153  jz      loc_140012803
0x140012159  cmp     byte ptr [rcx+19h], 2
0x14001215d  jb      loc_140012803
0x140012163  mov     edx, 222h
0x140012168  jmp     loc_1400127F7
0x14001216d  test    r12, r12
0x140012170  jz      short loc_1400121B0
0x140012172  mov     rcx, r12; Str
0x140012175  call    ValidFaxAccountName
0x14001217a  test    eax, eax
0x14001217c  jnz     short loc_1400121AC
0x14001217e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012185  cmp     rcx, r15
0x140012188  jz      loc_140012803
0x14001218e  test    [rcx+1Ch], sil
0x140012192  jz      loc_140012803
0x140012198  cmp     byte ptr [rcx+19h], 2
0x14001219c  jb      loc_140012803
0x1400121a2  mov     edx, 224h
0x1400121a7  jmp     loc_1400123C4
0x1400121ac  mov     eax, [rsp+1F8h+var_1A8]
0x1400121b0  cmp     [rsp+1F8h+arg_30], 1
0x1400121b8  jnz     short loc_140012228
0x1400121ba  test    edi, 201h
0x1400121c0  jz      short loc_1400121F1
0x1400121c2  mov     edx, 1; int
0x1400121c7  mov     ecx, eax; unsigned int
0x1400121c9  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x1400121ce  test    eax, eax
0x1400121d0  jnz     short loc_1400121F1
0x1400121d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121d9  cmp     rcx, r15
0x1400121dc  jz      short loc_140012259
0x1400121de  test    [rcx+1Ch], sil
0x1400121e2  jz      short loc_140012259
0x1400121e4  cmp     byte ptr [rcx+19h], 2
0x1400121e8  jb      short loc_140012259
0x1400121ea  mov     edx, 225h
0x1400121ef  jmp     short loc_14001224D
0x1400121f1  test    edi, 10Ch
0x1400121f7  jz      loc_1400122F2
0x1400121fd  mov     eax, [rsp+1F8h+var_1A8]
0x140012201  test    al, 20h
0x140012203  jnz     loc_1400122F2
0x140012209  mov     rcx, cs:WPP_GLOBAL_Control
0x140012210  cmp     rcx, r15
0x140012213  jz      short loc_140012259
0x140012215  test    [rcx+1Ch], sil
0x140012219  jz      short loc_140012259
0x14001221b  cmp     byte ptr [rcx+19h], 2
0x14001221f  jb      short loc_140012259
0x140012221  mov     edx, 226h
0x140012226  jmp     short loc_14001224D
0x140012228  mov     dword ptr [rsp+1F8h+lpMem], ebx
0x14001222c  test    edi, edi
0x14001222e  jz      short loc_140012282
0x140012230  mov     rcx, cs:WPP_GLOBAL_Control
0x140012237  cmp     rcx, r15
0x14001223a  jz      short loc_140012259
0x14001223c  test    [rcx+1Ch], sil
0x140012240  jz      short loc_140012259
0x140012242  cmp     byte ptr [rcx+19h], 2
0x140012246  jb      short loc_140012259
0x140012248  mov     edx, 227h
0x14001224d  mov     r8, r14
0x140012250  mov     rcx, [rcx+10h]
0x140012254  call    WPP_SF_
0x140012259  mov     eax, 5
0x14001225e  mov     rcx, [rsp+1F8h+var_48]
0x140012266  xor     rcx, rsp; StackCookie
0x140012269  call    __security_check_cookie
0x14001226e  add     rsp, 1C0h
0x140012275  pop     r15
0x140012277  pop     r14
0x140012279  pop     r13
0x14001227b  pop     r12
0x14001227d  pop     rdi
0x14001227e  pop     rsi
0x14001227f  pop     rbx
0x140012280  retn
0x140012282  lea     rcx, [rsp+1F8h+lpMem]
0x140012287  call    IsLocalRPCConnectionNP
0x14001228c  mov     edi, eax
0x14001228e  test    eax, eax
0x140012290  jz      short loc_1400122C2
0x140012292  mov     rcx, cs:WPP_GLOBAL_Control
0x140012299  cmp     rcx, r15
0x14001229c  jz      short loc_1400122BE
0x14001229e  test    [rcx+1Ch], sil
0x1400122a2  jz      short loc_1400122BE
0x1400122a4  cmp     byte ptr [rcx+19h], 2
0x1400122a8  jb      short loc_1400122BE
0x1400122aa  mov     edx, 228h
0x1400122af  mov     r9d, eax
0x1400122b2  mov     r8, r14
0x1400122b5  mov     rcx, [rcx+10h]
0x1400122b9  call    WPP_SF_d
0x1400122be  mov     eax, edi
0x1400122c0  jmp     short loc_14001225E
0x1400122c2  cmp     dword ptr [rsp+1F8h+lpMem], ebx
0x1400122c6  jnz     short loc_1400122F2
0x1400122c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122cf  cmp     rcx, r15
0x1400122d2  jz      short loc_140012259
0x1400122d4  test    [rcx+1Ch], sil
0x1400122d8  jz      loc_140012259
0x1400122de  cmp     byte ptr [rcx+19h], 2
0x1400122e2  jb      loc_140012259
0x1400122e8  mov     edx, 229h
0x1400122ed  jmp     loc_14001224D
0x1400122f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400122f6  mov     rcx, rax
0x1400122f9  mov     rdi, [rsp+1F8h+String2]
0x1400122fe  inc     rcx
0x140012301  cmp     [rdi+rcx*2], bx
0x140012305  jnz     short loc_1400122FE
0x140012307  cmp     rcx, 0Fh
0x14001230b  ja      loc_14001279F
0x140012311  inc     rax
0x140012314  cmp     [r13+rax*2+0], bx
0x14001231a  jnz     short loc_140012311
0x14001231c  cmp     rax, 0Bh
0x140012320  jnb     loc_14001279F
0x140012326  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14001232b  mov     [rsp+1F8h+lpMem], rax
0x140012330  test    rax, rax
0x140012333  jnz     short loc_140012387
0x140012335  call    cs:__imp_GetLastError
0x14001233c  nop     dword ptr [rax+rax+00h]
0x140012341  mov     edi, eax
0x140012343  mov     rcx, cs:WPP_GLOBAL_Control
0x14001234a  cmp     rcx, r15
0x14001234d  jz      short loc_14001236F
0x14001234f  test    [rcx+1Ch], sil
0x140012353  jz      short loc_14001236F
0x140012355  cmp     byte ptr [rcx+19h], 2
0x140012359  jb      short loc_14001236F
0x14001235b  mov     edx, 22Bh
0x140012360  mov     r9d, eax
0x140012363  mov     r8, r14
0x140012366  mov     rcx, [rcx+10h]
0x14001236a  call    WPP_SF_d
0x14001236f  cmp     edi, 8
0x140012372  jz      short loc_14001237D
0x140012374  cmp     edi, 0Eh
0x140012377  jnz     loc_1400122BE
0x14001237d  mov     edi, 1B59h
0x140012382  jmp     loc_1400122BE
0x140012387  test    r12, r12
0x14001238a  jz      short loc_1400123D8
0x14001238c  mov     rdx, rax; Sid
0x14001238f  mov     rcx, r12; String2
0x140012392  call    SameNTUser
0x140012397  test    eax, eax
0x140012399  jnz     short loc_1400123D8
0x14001239b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123a2  cmp     rcx, r15
0x1400123a5  jz      loc_140012803
0x1400123ab  test    [rcx+1Ch], sil
0x1400123af  jz      loc_140012803
0x1400123b5  cmp     byte ptr [rcx+19h], 2
0x1400123b9  jb      loc_140012803
0x1400123bf  mov     edx, 22Ch
0x1400123c4  mov     r9, r12
0x1400123c7  mov     r8, r14
0x1400123ca  mov     rcx, [rcx+10h]
0x1400123ce  call    WPP_SF_S
0x1400123d3  jmp     loc_140012803
0x1400123d8  mov     r13, rbx
0x1400123db  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400123e2  call    cs:__imp_EnterCriticalSection
0x1400123e9  nop     dword ptr [rax+rax+00h]
0x1400123ee  mov     r8d, 7; MaxCount
0x1400123f4  lea     rdx, aNcalrpc; "ncalrpc"
0x1400123fb  mov     rcx, [rsp+1F8h+String1]; String1
0x140012403  call    wcsncmp_0
0x140012408  mov     r8d, ebx
0x14001240b  test    eax, eax
0x14001240d  setz    r8b; AuthzSvc
0x140012411  lea     r9, [rsp+1F8h+Binding]; Binding
0x140012416  mov     rdx, [rsp+1F8h+Endpoint]; Endpoint
0x14001241b  mov     rcx, rdi; String2
0x14001241e  call    ?RpcBindToFaxClient@@YAKPEBG0HPEAPEAX@Z; RpcBindToFaxClient(ushort const *,ushort const *,int,void * *)
0x140012423  mov     edi, eax
0x140012425  test    eax, eax
0x140012427  jz      short loc_140012469
0x140012429  mov     r12, rbx
0x14001242c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012433  cmp     rcx, r15
0x140012436  jz      loc_1400126F4
0x14001243c  test    [rcx+1Ch], sil
0x140012440  jz      loc_1400126F4
0x140012446  cmp     byte ptr [rcx+19h], 2
0x14001244a  jb      loc_1400126F4
0x140012450  mov     edx, 22Dh
0x140012455  mov     r9d, eax
0x140012458  mov     r8, r14
0x14001245b  mov     rcx, [rcx+10h]
0x14001245f  call    WPP_SF_d
0x140012464  jmp     loc_1400126F4
0x140012469  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012470  mov     ecx, 50h ; 'P'; unsigned __int64
0x140012475  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001247a  mov     [rsp+1F8h+var_168], rax
0x140012482  mov     rdi, [rsp+1F8h+Endpoint]
  ... truncated ...
```
