# DpspClientDeleteQueuedResolution

- ea: `0x1800146b0`
- end: `0x1800149d3`
- name: `DpspClientDeleteQueuedResolution`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800104f4`

## callees

- `0x180001010`
- `0x1800069b0`
- `0x180006eec`
- `0x180008ea0`
- `0x180009090`
- `0x1800130a8`
- `0x180013a10`
- `0x1800146b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001472f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001472f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001474b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014787`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001474b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014787`

## string_xrefs

- `0x180014708`: `DpspClientDeleteQueuedResolution`
- `0x180014766`: `DpspClientDeleteQueuedResolution`
- `0x1800147b2`: `DpspClientDeleteQueuedResolution`

## pseudocode

```c
__int64 __fastcall DpspClientDeleteQueuedResolution(__int64 a1, struct _GUID *a2)
{
  int v4; // ebx
  __int64 InstanceFromId; // rax
  __int64 v6; // rdi
  int v7; // r15d
  int v8; // r8d
  int v9; // eax
  int UserFromUserSID; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char Args[8]; // [rsp+20h] [rbp-30h]
  void *v18; // [rsp+30h] [rbp-20h]
  struct __TARGETUSER *v19; // [rsp+40h] [rbp-10h] BYREF
  PSID pSid1; // [rsp+48h] [rbp-8h] BYREF
  int v21; // [rsp+88h] [rbp+38h] BYREF
  int v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+98h] [rbp+48h] BYREF

  pSid1 = 0;
  v22 = 0;
  v19 = 0;
  v21 = 0;
  v23 = 0;
  if ( a2 )
  {
    AcquireSRWLockShared(&g_SRWInstanceList);
    InstanceFromId = DpspGetInstanceFromId(&a2[4], 0);
    v6 = InstanceFromId;
    if ( !InstanceFromId )
    {
      ReleaseSRWLockShared(&g_SRWInstanceList);
      v4 = -2147024809;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (__int64)L"DpspClientDeleteQueuedResolution",
        2101,
        (const wchar_t *)L"Error = %d",
        87);
      goto LABEL_40;
    }
    _InterlockedIncrement((volatile signed __int32 *)(InstanceFromId + 72));
    ReleaseSRWLockShared(&g_SRWInstanceList);
    if ( _interlockedbittestandset((volatile signed __int32 *)(v6 + 104), 0xAu) )
    {
      v7 = 0;
      v8 = 2120;
    }
    else
    {
      v7 = 4;
      if ( (*(_DWORD *)(v6 + 104) & 0x20) != 0 )
      {
        v4 = -2147020579;
        *(_DWORD *)Args = 4317;
        v8 = 2129;
        goto LABEL_8;
      }
      if ( *(_QWORD *)(v6 + 96) == a1 )
      {
        if ( (*(_DWORD *)(v6 + 104) & 0x100) != 0 )
        {
          v4 = -2147020579;
          *(_DWORD *)Args = 4317;
          v8 = 2147;
        }
        else
        {
          v9 = DpspRetrieveClientCredentials((RTL_SRWLOCK *)v6, (__int64)a2, 8u, &pSid1, &v23, &v22, v18, 0);
          v4 = v9;
          if ( v9 >= 0 )
          {
            if ( (a2[7].Data4[0] & 8) != 0 )
              _InterlockedOr((volatile signed __int32 *)(v6 + 104), 0x80u);
            if ( !v22 )
              goto LABEL_26;
            UserFromUserSID = DpspGetUserFromUserSID(g_pAdminSid, (PSLIST_ENTRY *)&v19);
            v4 = UserFromUserSID;
            if ( UserFromUserSID < 0 )
            {
              v8 = 2171;
              *(_DWORD *)Args = (unsigned __int16)UserFromUserSID;
              goto LABEL_8;
            }
            if ( !v19 )
              goto LABEL_26;
            v11 = DpspRemoveInstanceFromUser(v19, a2 + 8, &v21);
            v4 = v11;
            if ( v11 < 0 )
            {
              v8 = 2179;
              *(_DWORD *)Args = (unsigned __int16)v11;
              goto LABEL_8;
            }
            if ( !v21 )
            {
LABEL_26:
              v12 = DpspGetUserFromUserSID(g_pEveryoneSid, (PSLIST_ENTRY *)&v19);
              v4 = v12;
              if ( v12 < 0 )
              {
                v8 = 2191;
                *(_DWORD *)Args = (unsigned __int16)v12;
                goto LABEL_8;
              }
              if ( !v19 )
                goto LABEL_32;
              v13 = DpspRemoveInstanceFromUser(v19, a2 + 8, &v21);
              v4 = v13;
              if ( v13 < 0 )
              {
                v8 = 2199;
                *(_DWORD *)Args = (unsigned __int16)v13;
                goto LABEL_8;
              }
              if ( !v21 )
              {
LABEL_32:
                v14 = DpspGetUserFromUserSID(pSid1, (PSLIST_ENTRY *)&v19);
                v4 = v14;
                if ( v14 < 0 )
                {
                  v8 = 2210;
                  *(_DWORD *)Args = (unsigned __int16)v14;
                  goto LABEL_8;
                }
                if ( !v19 )
                  goto LABEL_38;
                v15 = DpspRemoveInstanceFromUser(v19, a2 + 8, &v21);
                v4 = v15;
                if ( v15 < 0 )
                {
                  v8 = 2217;
                  *(_DWORD *)Args = (unsigned __int16)v15;
                  goto LABEL_8;
                }
                if ( !v21 )
LABEL_38:
                  v4 = -2147024894;
              }
            }
LABEL_39:
            DpspCloseInstance(v6, 7, v7 | 1u, (unsigned int)v4);
            if ( v4 >= 0 )
              goto LABEL_41;
LABEL_40:
            a2[7].Data1 = v4;
            goto LABEL_41;
          }
          v8 = 2158;
          *(_DWORD *)Args = (unsigned __int16)v9;
        }
LABEL_8:
        WdipTraceError(
          (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
          (__int64)L"DpspClientDeleteQueuedResolution",
          v8,
          (const wchar_t *)L"Error = %d",
          *(_QWORD *)Args);
        goto LABEL_39;
      }
      v8 = 2138;
    }
    *(_DWORD *)Args = 16389;
    v4 = -2147467259;
    goto LABEL_8;
  }
  v4 = -2147024809;
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
    (__int64)L"DpspClientDeleteQueuedResolution",
    2092,
    (const wchar_t *)L"Error = %d",
    87);
LABEL_41:
  WdipFree(pSid1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800146b0  mov     [rsp-28h+arg_0], rbx
0x1800146b5  push    rbp
0x1800146b6  push    rsi
0x1800146b7  push    rdi
0x1800146b8  push    r14
0x1800146ba  push    r15
0x1800146bc  mov     rbp, rsp
0x1800146bf  sub     rsp, 50h
0x1800146c3  mov     [rbp+pSid1], 0
0x1800146cb  mov     rsi, rdx
0x1800146ce  mov     [rbp+arg_10], 0
0x1800146d5  mov     rbx, rcx
0x1800146d8  mov     [rbp+var_10], 0
0x1800146e0  mov     [rbp+arg_8], 0
0x1800146e7  mov     [rbp+arg_18], 0
0x1800146ee  test    rdx, rdx
0x1800146f1  jnz     short loc_180014725
0x1800146f3  lea     r9, aErrorD; "Error = %d"
0x1800146fa  mov     dword ptr [rsp+50h+Args], 57h ; 'W'; Args
0x180014702  mov     r8d, 82Ch; int
0x180014708  lea     rdx, aDpspclientdele; "DpspClientDeleteQueuedResolution"
0x18001470f  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180014716  mov     ebx, 80070057h
0x18001471b  call    WdipTraceError
0x180014720  jmp     loc_1800149B4
0x180014725  lea     r14, g_SRWInstanceList
0x18001472c  mov     rcx, r14; SRWLock
0x18001472f  call    cs:__imp_AcquireSRWLockShared
0x180014735  lea     rcx, [rsi+40h]
0x180014739  xor     edx, edx
0x18001473b  call    DpspGetInstanceFromId
0x180014740  mov     rdi, rax
0x180014743  mov     rcx, r14; SRWLock
0x180014746  test    rax, rax
0x180014749  jnz     short loc_180014783
0x18001474b  call    cs:__imp_ReleaseSRWLockShared
0x180014751  lea     r9, aErrorD; "Error = %d"
0x180014758  mov     dword ptr [rsp+50h+Args], 57h ; 'W'; Args
0x180014760  mov     r8d, 835h; int
0x180014766  lea     rdx, aDpspclientdele; "DpspClientDeleteQueuedResolution"
0x18001476d  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180014774  mov     ebx, 80070057h
0x180014779  call    WdipTraceError
0x18001477e  jmp     loc_1800149B1
0x180014783  lock inc dword ptr [rax+48h]
0x180014787  call    cs:__imp_ReleaseSRWLockShared
0x18001478d  lock bts dword ptr [rdi+68h], 0Ah
0x180014793  jnb     short loc_1800147CA
0x180014795  xor     r15d, r15d
0x180014798  mov     r8d, 848h; int
0x18001479e  mov     dword ptr [rsp+50h+Args], 4005h; Args
0x1800147a6  mov     ebx, 80004005h
0x1800147ab  lea     r9, aErrorD; "Error = %d"
0x1800147b2  lea     rdx, aDpspclientdele; "DpspClientDeleteQueuedResolution"
0x1800147b9  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800147c0  call    WdipTraceError
0x1800147c5  jmp     loc_180014996
0x1800147ca  mov     eax, [rdi+68h]
0x1800147cd  mov     r15d, 4
0x1800147d3  test    al, 20h
0x1800147d5  jz      short loc_1800147EC
0x1800147d7  mov     ebx, 800710DDh
0x1800147dc  mov     dword ptr [rsp+50h+Args], 10DDh
0x1800147e4  mov     r8d, 851h
0x1800147ea  jmp     short loc_1800147AB
0x1800147ec  cmp     [rdi+60h], rbx
0x1800147f0  jz      short loc_1800147FA
0x1800147f2  mov     r8d, 85Ah
0x1800147f8  jmp     short loc_18001479E
0x1800147fa  mov     eax, [rdi+68h]
0x1800147fd  bt      eax, 8
0x180014801  jnb     short loc_180014818
0x180014803  mov     ebx, 800710DDh
0x180014808  mov     dword ptr [rsp+50h+Args], 10DDh
0x180014810  mov     r8d, 863h
0x180014816  jmp     short loc_1800147AB
0x180014818  lea     rax, [rbp+arg_10]
0x18001481c  mov     [rsp+50h+var_18], 0
0x180014825  mov     [rsp+50h+var_28], rax
0x18001482a  lea     r9, [rbp+pSid1]
0x18001482e  lea     rax, [rbp+arg_18]
0x180014832  mov     r8d, 8
0x180014838  mov     rdx, rsi
0x18001483b  mov     qword ptr [rsp+50h+Args], rax
0x180014840  mov     rcx, rdi
0x180014843  call    DpspRetrieveClientCredentials
0x180014848  mov     ebx, eax
0x18001484a  test    eax, eax
0x18001484c  jns     short loc_180014860
0x18001484e  movzx   eax, ax
0x180014851  mov     r8d, 86Eh
0x180014857  mov     dword ptr [rsp+50h+Args], eax
0x18001485b  jmp     loc_1800147AB
0x180014860  test    byte ptr [rsi+78h], 8
0x180014864  jz      short loc_18001486E
0x180014866  lock or dword ptr [rdi+68h], 80h
0x18001486e  cmp     [rbp+arg_10], 0
0x180014872  jz      short loc_1800148D7
0x180014874  mov     rcx, cs:g_pAdminSid; pSid1
0x18001487b  lea     rdx, [rbp+var_10]; struct __TARGETUSER **
0x18001487f  call    ?DpspGetUserFromUserSID@@YAJPEAXPEAPEAU__TARGETUSER@@@Z; DpspGetUserFromUserSID(void *,__TARGETUSER * *)
0x180014884  mov     ebx, eax
0x180014886  test    eax, eax
0x180014888  jns     short loc_18001489C
0x18001488a  movzx   eax, ax
0x18001488d  mov     r8d, 87Bh
0x180014893  mov     dword ptr [rsp+50h+Args], eax
0x180014897  jmp     loc_1800147AB
0x18001489c  mov     rcx, [rbp+var_10]; struct __TARGETUSER *
0x1800148a0  test    rcx, rcx
0x1800148a3  jz      short loc_1800148D7
0x1800148a5  lea     rdx, [rsi+80h]; struct _GUID *
0x1800148ac  lea     r8, [rbp+arg_8]; int *
0x1800148b0  call    ?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z; DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)
0x1800148b5  mov     ebx, eax
0x1800148b7  test    eax, eax
0x1800148b9  jns     short loc_1800148CD
0x1800148bb  movzx   eax, ax
0x1800148be  mov     r8d, 883h
0x1800148c4  mov     dword ptr [rsp+50h+Args], eax
0x1800148c8  jmp     loc_1800147AB
0x1800148cd  cmp     [rbp+arg_8], 0
0x1800148d1  jnz     loc_180014996
0x1800148d7  mov     rcx, cs:g_pEveryoneSid; pSid1
0x1800148de  lea     rdx, [rbp+var_10]; struct __TARGETUSER **
0x1800148e2  call    ?DpspGetUserFromUserSID@@YAJPEAXPEAPEAU__TARGETUSER@@@Z; DpspGetUserFromUserSID(void *,__TARGETUSER * *)
0x1800148e7  mov     ebx, eax
0x1800148e9  test    eax, eax
0x1800148eb  jns     short loc_1800148FF
0x1800148ed  movzx   eax, ax
0x1800148f0  mov     r8d, 88Fh
0x1800148f6  mov     dword ptr [rsp+50h+Args], eax
0x1800148fa  jmp     loc_1800147AB
0x1800148ff  mov     rcx, [rbp+var_10]; struct __TARGETUSER *
0x180014903  lea     r14, [rsi+80h]
0x18001490a  test    rcx, rcx
0x18001490d  jz      short loc_180014939
0x18001490f  lea     r8, [rbp+arg_8]; int *
0x180014913  mov     rdx, r14; struct _GUID *
0x180014916  call    ?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z; DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)
0x18001491b  mov     ebx, eax
0x18001491d  test    eax, eax
0x18001491f  jns     short loc_180014933
0x180014921  movzx   eax, ax
0x180014924  mov     r8d, 897h
0x18001492a  mov     dword ptr [rsp+50h+Args], eax
0x18001492e  jmp     loc_1800147AB
0x180014933  cmp     [rbp+arg_8], 0
0x180014937  jnz     short loc_180014996
0x180014939  mov     rcx, [rbp+pSid1]; pSid1
0x18001493d  lea     rdx, [rbp+var_10]; struct __TARGETUSER **
0x180014941  call    ?DpspGetUserFromUserSID@@YAJPEAXPEAPEAU__TARGETUSER@@@Z; DpspGetUserFromUserSID(void *,__TARGETUSER * *)
0x180014946  mov     ebx, eax
0x180014948  test    eax, eax
0x18001494a  jns     short loc_18001495E
0x18001494c  movzx   eax, ax
0x18001494f  mov     r8d, 8A2h
0x180014955  mov     dword ptr [rsp+50h+Args], eax
0x180014959  jmp     loc_1800147AB
0x18001495e  mov     rcx, [rbp+var_10]; struct __TARGETUSER *
0x180014962  test    rcx, rcx
0x180014965  jz      short loc_180014991
0x180014967  lea     r8, [rbp+arg_8]; int *
0x18001496b  mov     rdx, r14; struct _GUID *
0x18001496e  call    ?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z; DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)
0x180014973  mov     ebx, eax
0x180014975  test    eax, eax
0x180014977  jns     short loc_18001498B
0x180014979  movzx   eax, ax
0x18001497c  mov     r8d, 8A9h
0x180014982  mov     dword ptr [rsp+50h+Args], eax
0x180014986  jmp     loc_1800147AB
0x18001498b  cmp     [rbp+arg_8], 0
0x18001498f  jnz     short loc_180014996
0x180014991  mov     ebx, 80070002h
0x180014996  or      r15d, 1
0x18001499a  mov     r9d, ebx
0x18001499d  mov     r8d, r15d
0x1800149a0  mov     edx, 7
0x1800149a5  mov     rcx, rdi
0x1800149a8  call    DpspCloseInstance
0x1800149ad  test    ebx, ebx
0x1800149af  jns     short loc_1800149B4
0x1800149b1  mov     [rsi+70h], ebx
0x1800149b4  mov     rcx, [rbp+pSid1]
0x1800149b8  call    WdipFree
0x1800149bd  mov     eax, ebx
0x1800149bf  mov     rbx, [rsp+50h+arg_0]
0x1800149c7  add     rsp, 50h
0x1800149cb  pop     r15
0x1800149cd  pop     r14
0x1800149cf  pop     rdi
0x1800149d0  pop     rsi
0x1800149d1  pop     rbp
0x1800149d2  retn
```
