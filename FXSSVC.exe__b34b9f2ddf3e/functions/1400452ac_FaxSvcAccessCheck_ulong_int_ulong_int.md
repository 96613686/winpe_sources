# FaxSvcAccessCheck(ulong,int *,ulong *,int)

- ea: `0x1400452ac`
- end: `0x140045558`
- name: `?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z`
- size: `684`
- prototype: `__int64 __fastcall(DWORD, int *, unsigned int *, int)`
- caller_count: `84`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000eaf0`
- `0x14000eee0`
- `0x14000f080`
- `0x14000f2f0`
- `0x14000f700`
- `0x140010bc8`
- `0x140010f50`
- `0x1400111e0`
- `0x14001186c`
- `0x1400120b8`
- `0x14001287c`
- `0x140015d90`
- `0x1400164a0`
- `0x140016770`
- `0x140016870`
- `0x140016a60`
- `0x140016e90`
- `0x140017390`
- `0x1400175c0`
- `0x140017c10`
- `0x140017eb0`
- `0x140018110`
- `0x140018450`
- `0x1400186f0`
- `0x140018aa0`
- `0x140018d00`
- `0x140018f50`
- `0x140019370`
- `0x140019980`
- `0x140019dc0`
- `0x14001a0f0`
- `0x14001a290`
- `0x14001a5f0`
- `0x14001a6a0`
- `0x14001ac80`
- `0x14001aec0`
- `0x14001b0d0`
- `0x14001b1d0`
- `0x14001b490`
- `0x14001b5a0`
- `0x14001b680`
- `0x14001b9c0`
- `0x14001bb40`
- `0x14001bc50`
- `0x14001c000`
- `0x14001c1f0`
- `0x14001c5c0`
- `0x14001c720`
- `0x14001cb80`
- `0x14001cf70`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14000e964`
- `0x1400452ac`
- `0x140065dbc`
- `0x140073418`

## import_xrefs

- `ADVAPI32!MapGenericMask` at `0x140045450`
- `ADVAPI32!MapGenericMask` at `0x140045450`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x1400454a2`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x1400454a2`
- `KERNEL32!GetLastError` at `0x140045362`
- `KERNEL32!GetLastError` at `0x1400454ac`
- `KERNEL32!GetLastError` at `0x140045362`
- `KERNEL32!GetLastError` at `0x1400454ac`
- `KERNEL32!EnterCriticalSection` at `0x1400453b7`
- `KERNEL32!EnterCriticalSection` at `0x140045438`
- `KERNEL32!EnterCriticalSection` at `0x1400453b7`
- `KERNEL32!EnterCriticalSection` at `0x140045438`
- `KERNEL32!LeaveCriticalSection` at `0x1400453d9`
- `KERNEL32!LeaveCriticalSection` at `0x1400454f9`
- `KERNEL32!LeaveCriticalSection` at `0x1400453d9`
- `KERNEL32!LeaveCriticalSection` at `0x1400454f9`
- `RPCRT4!RpcRevertToSelf` at `0x140045506`
- `RPCRT4!RpcRevertToSelf` at `0x140045506`
- `RPCRT4!RpcImpersonateClient` at `0x140045310`
- `RPCRT4!RpcImpersonateClient` at `0x140045310`

## pseudocode

```c
__int64 __fastcall FaxSvcAccessCheck(DWORD a1, int *a2, unsigned int *a3, int a4)
{
  unsigned int v7; // eax
  unsigned int v8; // edi
  CMapDeviceId *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  void *CurrentThreadSID; // rbp
  DWORD LastError; // eax
  __int64 AccountBySid; // rbx
  DWORD v15; // eax
  unsigned int v16; // eax
  DWORD GrantedAccess; // [rsp+60h] [rbp-28h] BYREF
  WINBOOL pfGenerateOnClose[3]; // [rsp+64h] [rbp-24h] BYREF
  DWORD AccessMask; // [rsp+90h] [rbp+8h] BYREF

  AccessMask = a1;
  GrantedAccess = 0;
  pfGenerateOnClose[0] = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v7 = RpcImpersonateClient(0);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 11;
      v11 = v7;
LABEL_35:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v11);
      return v8;
    }
    return v8;
  }
  if ( !a4 )
    goto LABEL_22;
  CurrentThreadSID = (void *)GetCurrentThreadSID();
  if ( !CurrentThreadSID )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
    goto LABEL_30;
  }
  EnterCriticalSection(&g_CsConfig);
  AccountBySid = CFaxAccountList::_FindAccountBySid(g_pAccountList, CurrentThreadSID, 0);
  LeaveCriticalSection(&g_CsConfig);
  pMemFree(CurrentThreadSID);
  if ( AccountBySid )
  {
LABEL_22:
    EnterCriticalSection(&g_CsSecurity);
    MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
    if ( AccessCheckAndAuditAlarmW(
           L"Fax",
           0,
           0,
           0,
           g_pFaxSD,
           AccessMask,
           (PGENERIC_MAPPING)&GenericMapping,
           0,
           &GrantedAccess,
           a2,
           pfGenerateOnClose) )
    {
      if ( a3 )
        *a3 = GrantedAccess;
    }
    else
    {
      v15 = GetLastError();
      v8 = v15;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v15);
      }
    }
    LeaveCriticalSection(&g_CsSecurity);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v8 = 5;
  }
LABEL_30:
  v16 = RpcRevertToSelf();
  if ( v16 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 15;
      v11 = v16;
      goto LABEL_35;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400452ac  mov     rax, rsp
0x1400452af  mov     [rax+10h], rbx
0x1400452b3  mov     [rax+18h], rbp
0x1400452b7  mov     [rax+8], ecx
0x1400452ba  push    rdi
0x1400452bb  push    r14
0x1400452bd  push    r15
0x1400452bf  sub     rsp, 70h
0x1400452c3  mov     ebx, r9d
0x1400452c6  mov     dword ptr [rax-28h], 0
0x1400452cd  mov     r14, r8
0x1400452d0  mov     dword ptr [rax-24h], 0
0x1400452d7  mov     r15, rdx
0x1400452da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400452e1  lea     rbp, WPP_GLOBAL_Control
0x1400452e8  cmp     rcx, rbp
0x1400452eb  jz      short loc_14004530E
0x1400452ed  test    byte ptr [rcx+1Ch], 4
0x1400452f1  jz      short loc_14004530E
0x1400452f3  cmp     byte ptr [rcx+19h], 5
0x1400452f7  jb      short loc_14004530E
0x1400452f9  mov     rcx, [rcx+10h]
0x1400452fd  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140045304  mov     edx, 0Ah
0x140045309  call    WPP_SF_
0x14004530e  xor     ecx, ecx; BindingHandle
0x140045310  call    cs:__imp_RpcImpersonateClient
0x140045316  mov     edi, eax
0x140045318  test    eax, eax
0x14004531a  jz      short loc_14004534D
0x14004531c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045323  cmp     rcx, rbp
0x140045326  jz      loc_140045540
0x14004532c  test    byte ptr [rcx+1Ch], 4
0x140045330  jz      loc_140045540
0x140045336  cmp     byte ptr [rcx+19h], 2
0x14004533a  jb      loc_140045540
0x140045340  mov     edx, 0Bh
0x140045345  mov     r9d, eax
0x140045348  jmp     loc_140045530
0x14004534d  test    ebx, ebx
0x14004534f  jz      loc_140045431
0x140045355  call    GetCurrentThreadSID
0x14004535a  mov     rbp, rax
0x14004535d  test    rax, rax
0x140045360  jnz     short loc_1400453B0
0x140045362  call    cs:__imp_GetLastError
0x140045368  mov     edi, eax
0x14004536a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045371  lea     rbx, WPP_GLOBAL_Control
0x140045378  cmp     rcx, rbx
0x14004537b  jz      loc_140045506
0x140045381  test    byte ptr [rcx+1Ch], 4
0x140045385  jz      loc_140045506
0x14004538b  cmp     byte ptr [rcx+19h], 2
0x14004538f  jb      loc_140045506
0x140045395  mov     rcx, [rcx+10h]
0x140045399  lea     edx, [rbp+0Ch]
0x14004539c  mov     r9d, eax
0x14004539f  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400453a6  call    WPP_SF_d
0x1400453ab  jmp     loc_140045506
0x1400453b0  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400453b7  call    cs:__imp_EnterCriticalSection
0x1400453bd  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x1400453c4  xor     r8d, r8d
0x1400453c7  mov     rdx, rbp
0x1400453ca  call    ?_FindAccountBySid@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEAXPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountBySid(void *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x1400453cf  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400453d6  mov     rbx, rax
0x1400453d9  call    cs:__imp_LeaveCriticalSection
0x1400453df  mov     rcx, rbp; lpMem
0x1400453e2  call    pMemFree
0x1400453e7  test    rbx, rbx
0x1400453ea  jnz     short loc_14004542A
0x1400453ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400453f3  lea     rbx, WPP_GLOBAL_Control
0x1400453fa  cmp     rcx, rbx
0x1400453fd  jz      short loc_140045420
0x1400453ff  test    byte ptr [rcx+1Ch], 4
0x140045403  jz      short loc_140045420
0x140045405  cmp     byte ptr [rcx+19h], 2
0x140045409  jb      short loc_140045420
0x14004540b  mov     rcx, [rcx+10h]
0x14004540f  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140045416  mov     edx, 0Dh
0x14004541b  call    WPP_SF_
0x140045420  mov     edi, 5
0x140045425  jmp     loc_140045506
0x14004542a  lea     rbp, WPP_GLOBAL_Control
0x140045431  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045438  call    cs:__imp_EnterCriticalSection
0x14004543e  lea     rbx, GenericMapping
0x140045445  mov     rdx, rbx; GenericMapping
0x140045448  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x140045450  call    cs:__imp_MapGenericMask
0x140045456  lea     rax, [rsp+88h+var_24]
0x14004545b  xor     r9d, r9d; ObjectName
0x14004545e  mov     [rsp+88h+pfGenerateOnClose], rax; pfGenerateOnClose
0x140045463  lea     rcx, SubsystemName; "Fax"
0x14004546a  mov     [rsp+88h+AccessStatus], r15; AccessStatus
0x14004546f  lea     rax, [rsp+88h+var_28]
0x140045474  mov     [rsp+88h+GrantedAccess], rax; GrantedAccess
0x140045479  xor     r8d, r8d; ObjectTypeName
0x14004547c  mov     eax, [rsp+88h+AccessMask]
0x140045483  xor     edx, edx; HandleId
0x140045485  mov     [rsp+88h+ObjectCreation], 0; ObjectCreation
0x14004548d  mov     [rsp+88h+GenericMapping], rbx; GenericMapping
0x140045492  mov     [rsp+88h+DesiredAccess], eax; DesiredAccess
0x140045496  mov     rax, cs:?g_pFaxSD@@3PEAXEA; void * g_pFaxSD
0x14004549d  mov     [rsp+88h+SecurityDescriptor], rax; SecurityDescriptor
0x1400454a2  call    cs:__imp_AccessCheckAndAuditAlarmW
0x1400454a8  test    eax, eax
0x1400454aa  jnz     short loc_1400454E6
0x1400454ac  call    cs:__imp_GetLastError
0x1400454b2  mov     edi, eax
0x1400454b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400454bb  cmp     rcx, rbp
0x1400454be  jz      short loc_1400454F2
0x1400454c0  test    byte ptr [rcx+1Ch], 4
0x1400454c4  jz      short loc_1400454F2
0x1400454c6  cmp     byte ptr [rcx+19h], 2
0x1400454ca  jb      short loc_1400454F2
0x1400454cc  mov     rcx, [rcx+10h]
0x1400454d0  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400454d7  mov     edx, 0Eh
0x1400454dc  mov     r9d, eax
0x1400454df  call    WPP_SF_d
0x1400454e4  jmp     short loc_1400454F2
0x1400454e6  test    r14, r14
0x1400454e9  jz      short loc_1400454F2
0x1400454eb  mov     eax, [rsp+88h+var_28]
0x1400454ef  mov     [r14], eax
0x1400454f2  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400454f9  call    cs:__imp_LeaveCriticalSection
0x1400454ff  lea     rbx, WPP_GLOBAL_Control
0x140045506  call    cs:__imp_RpcRevertToSelf
0x14004550c  test    eax, eax
0x14004550e  jz      short loc_140045540
0x140045510  mov     rcx, cs:WPP_GLOBAL_Control
0x140045517  cmp     rcx, rbx
0x14004551a  jz      short loc_140045540
0x14004551c  test    byte ptr [rcx+1Ch], 4
0x140045520  jz      short loc_140045540
0x140045522  cmp     byte ptr [rcx+19h], 2
0x140045526  jb      short loc_140045540
0x140045528  mov     edx, 0Fh
0x14004552d  mov     r9d, eax
0x140045530  mov     rcx, [rcx+10h]
0x140045534  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004553b  call    WPP_SF_d
0x140045540  lea     r11, [rsp+88h+var_18]
0x140045545  mov     eax, edi
0x140045547  mov     rbx, [r11+28h]
0x14004554b  mov     rbp, [r11+30h]
0x14004554f  mov     rsp, r11
0x140045552  pop     r15
0x140045554  pop     r14
0x140045556  pop     rdi
0x140045557  retn
```
