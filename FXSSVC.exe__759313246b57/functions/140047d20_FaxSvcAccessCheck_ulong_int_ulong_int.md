# FaxSvcAccessCheck(ulong,int *,ulong *,int)

- ea: `0x140047d20`
- end: `0x140048009`
- name: `?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z`
- size: `745`
- prototype: `__int64 __fastcall(DWORD, int *, unsigned int *, int)`
- caller_count: `84`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f270`
- `0x14000f680`
- `0x14000f830`
- `0x14000fab0`
- `0x14000fee0`
- `0x1400112c8`
- `0x140011650`
- `0x1400118e4`
- `0x140011fa0`
- `0x140012814`
- `0x140013004`
- `0x140016690`
- `0x140016de0`
- `0x1400170e0`
- `0x1400171e0`
- `0x1400173d0`
- `0x140017800`
- `0x140017d20`
- `0x140017f50`
- `0x1400185f0`
- `0x1400188a0`
- `0x140018b10`
- `0x140018e50`
- `0x1400190f0`
- `0x1400194a0`
- `0x140019710`
- `0x140019970`
- `0x140019d90`
- `0x14001a3c0`
- `0x14001a830`
- `0x14001ab70`
- `0x14001ad20`
- `0x14001b0d0`
- `0x14001b190`
- `0x14001b790`
- `0x14001b9f0`
- `0x14001bc10`
- `0x14001bd10`
- `0x14001bfe0`
- `0x14001c0f0`
- `0x14001c1d0`
- `0x14001c530`
- `0x14001c6c0`
- `0x14001c7d0`
- `0x14001cb80`
- `0x14001cd80`
- `0x14001d190`
- `0x14001d310`
- `0x14001d790`
- `0x14001dbc0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14000f0e0`
- `0x140047d20`
- `0x14006998c`
- `0x140077e50`

## import_xrefs

- `ADVAPI32!MapGenericMask` at `0x140047ee2`
- `ADVAPI32!MapGenericMask` at `0x140047ee2`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x140047f3a`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x140047f3a`
- `KERNEL32!GetLastError` at `0x140047ddc`
- `KERNEL32!GetLastError` at `0x140047f4a`
- `KERNEL32!GetLastError` at `0x140047ddc`
- `KERNEL32!GetLastError` at `0x140047f4a`
- `KERNEL32!EnterCriticalSection` at `0x140047e37`
- `KERNEL32!EnterCriticalSection` at `0x140047ec4`
- `KERNEL32!EnterCriticalSection` at `0x140047e37`
- `KERNEL32!EnterCriticalSection` at `0x140047ec4`
- `KERNEL32!LeaveCriticalSection` at `0x140047e5f`
- `KERNEL32!LeaveCriticalSection` at `0x140047f9d`
- `KERNEL32!LeaveCriticalSection` at `0x140047e5f`
- `KERNEL32!LeaveCriticalSection` at `0x140047f9d`
- `RPCRT4!RpcRevertToSelf` at `0x140047fb0`
- `RPCRT4!RpcRevertToSelf` at `0x140047fb0`
- `RPCRT4!RpcImpersonateClient` at `0x140047d84`
- `RPCRT4!RpcImpersonateClient` at `0x140047d84`

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
0x140047d20  mov     rax, rsp
0x140047d23  mov     [rax+10h], rbx
0x140047d27  mov     [rax+18h], rbp
0x140047d2b  mov     [rax+8], ecx
0x140047d2e  push    rdi
0x140047d2f  push    r14
0x140047d31  push    r15
0x140047d33  sub     rsp, 70h
0x140047d37  mov     ebx, r9d
0x140047d3a  mov     dword ptr [rax-28h], 0
0x140047d41  mov     r14, r8
0x140047d44  mov     dword ptr [rax-24h], 0
0x140047d4b  mov     r15, rdx
0x140047d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d55  lea     rbp, WPP_GLOBAL_Control
0x140047d5c  cmp     rcx, rbp
0x140047d5f  jz      short loc_140047D82
0x140047d61  test    byte ptr [rcx+1Ch], 4
0x140047d65  jz      short loc_140047D82
0x140047d67  cmp     byte ptr [rcx+19h], 5
0x140047d6b  jb      short loc_140047D82
0x140047d6d  mov     rcx, [rcx+10h]
0x140047d71  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047d78  mov     edx, 0Ah
0x140047d7d  call    WPP_SF_
0x140047d82  xor     ecx, ecx; BindingHandle
0x140047d84  call    cs:__imp_RpcImpersonateClient
0x140047d8b  nop     dword ptr [rax+rax+00h]
0x140047d90  mov     edi, eax
0x140047d92  test    eax, eax
0x140047d94  jz      short loc_140047DC7
0x140047d96  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d9d  cmp     rcx, rbp
0x140047da0  jz      loc_140047FF0
0x140047da6  test    byte ptr [rcx+1Ch], 4
0x140047daa  jz      loc_140047FF0
0x140047db0  cmp     byte ptr [rcx+19h], 2
0x140047db4  jb      loc_140047FF0
0x140047dba  mov     edx, 0Bh
0x140047dbf  mov     r9d, eax
0x140047dc2  jmp     loc_140047FE0
0x140047dc7  test    ebx, ebx
0x140047dc9  jz      loc_140047EBD
0x140047dcf  call    GetCurrentThreadSID
0x140047dd4  mov     rbp, rax
0x140047dd7  test    rax, rax
0x140047dda  jnz     short loc_140047E30
0x140047ddc  call    cs:__imp_GetLastError
0x140047de3  nop     dword ptr [rax+rax+00h]
0x140047de8  mov     edi, eax
0x140047dea  mov     rcx, cs:WPP_GLOBAL_Control
0x140047df1  lea     rbx, WPP_GLOBAL_Control
0x140047df8  cmp     rcx, rbx
0x140047dfb  jz      loc_140047FB0
0x140047e01  test    byte ptr [rcx+1Ch], 4
0x140047e05  jz      loc_140047FB0
0x140047e0b  cmp     byte ptr [rcx+19h], 2
0x140047e0f  jb      loc_140047FB0
0x140047e15  mov     rcx, [rcx+10h]
0x140047e19  lea     edx, [rbp+0Ch]
0x140047e1c  mov     r9d, eax
0x140047e1f  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047e26  call    WPP_SF_d
0x140047e2b  jmp     loc_140047FB0
0x140047e30  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140047e37  call    cs:__imp_EnterCriticalSection
0x140047e3e  nop     dword ptr [rax+rax+00h]
0x140047e43  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x140047e4a  xor     r8d, r8d
0x140047e4d  mov     rdx, rbp
0x140047e50  call    ?_FindAccountBySid@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEAXPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountBySid(void *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x140047e55  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140047e5c  mov     rbx, rax
0x140047e5f  call    cs:__imp_LeaveCriticalSection
0x140047e66  nop     dword ptr [rax+rax+00h]
0x140047e6b  mov     rcx, rbp; lpMem
0x140047e6e  call    pMemFree
0x140047e73  test    rbx, rbx
0x140047e76  jnz     short loc_140047EB6
0x140047e78  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e7f  lea     rbx, WPP_GLOBAL_Control
0x140047e86  cmp     rcx, rbx
0x140047e89  jz      short loc_140047EAC
0x140047e8b  test    byte ptr [rcx+1Ch], 4
0x140047e8f  jz      short loc_140047EAC
0x140047e91  cmp     byte ptr [rcx+19h], 2
0x140047e95  jb      short loc_140047EAC
0x140047e97  mov     rcx, [rcx+10h]
0x140047e9b  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047ea2  mov     edx, 0Dh
0x140047ea7  call    WPP_SF_
0x140047eac  mov     edi, 5
0x140047eb1  jmp     loc_140047FB0
0x140047eb6  lea     rbp, WPP_GLOBAL_Control
0x140047ebd  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140047ec4  call    cs:__imp_EnterCriticalSection
0x140047ecb  nop     dword ptr [rax+rax+00h]
0x140047ed0  lea     rbx, GenericMapping
0x140047ed7  mov     rdx, rbx; GenericMapping
0x140047eda  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x140047ee2  call    cs:__imp_MapGenericMask
0x140047ee9  nop     dword ptr [rax+rax+00h]
0x140047eee  lea     rax, [rsp+88h+var_24]
0x140047ef3  xor     r9d, r9d; ObjectName
0x140047ef6  mov     [rsp+88h+pfGenerateOnClose], rax; pfGenerateOnClose
0x140047efb  lea     rcx, SubsystemName; "Fax"
0x140047f02  mov     [rsp+88h+AccessStatus], r15; AccessStatus
0x140047f07  lea     rax, [rsp+88h+var_28]
0x140047f0c  mov     [rsp+88h+GrantedAccess], rax; GrantedAccess
0x140047f11  xor     r8d, r8d; ObjectTypeName
0x140047f14  mov     eax, [rsp+88h+AccessMask]
0x140047f1b  xor     edx, edx; HandleId
0x140047f1d  mov     [rsp+88h+ObjectCreation], 0; ObjectCreation
0x140047f25  mov     [rsp+88h+GenericMapping], rbx; GenericMapping
0x140047f2a  mov     [rsp+88h+DesiredAccess], eax; DesiredAccess
0x140047f2e  mov     rax, cs:?g_pFaxSD@@3PEAXEA; void * g_pFaxSD
0x140047f35  mov     [rsp+88h+SecurityDescriptor], rax; SecurityDescriptor
0x140047f3a  call    cs:__imp_AccessCheckAndAuditAlarmW
0x140047f41  nop     dword ptr [rax+rax+00h]
0x140047f46  test    eax, eax
0x140047f48  jnz     short loc_140047F8A
0x140047f4a  call    cs:__imp_GetLastError
0x140047f51  nop     dword ptr [rax+rax+00h]
0x140047f56  mov     edi, eax
0x140047f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f5f  cmp     rcx, rbp
0x140047f62  jz      short loc_140047F96
0x140047f64  test    byte ptr [rcx+1Ch], 4
0x140047f68  jz      short loc_140047F96
0x140047f6a  cmp     byte ptr [rcx+19h], 2
0x140047f6e  jb      short loc_140047F96
0x140047f70  mov     rcx, [rcx+10h]
0x140047f74  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047f7b  mov     edx, 0Eh
0x140047f80  mov     r9d, eax
0x140047f83  call    WPP_SF_d
0x140047f88  jmp     short loc_140047F96
0x140047f8a  test    r14, r14
0x140047f8d  jz      short loc_140047F96
0x140047f8f  mov     eax, [rsp+88h+var_28]
0x140047f93  mov     [r14], eax
0x140047f96  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140047f9d  call    cs:__imp_LeaveCriticalSection
0x140047fa4  nop     dword ptr [rax+rax+00h]
0x140047fa9  lea     rbx, WPP_GLOBAL_Control
0x140047fb0  call    cs:__imp_RpcRevertToSelf
0x140047fb7  nop     dword ptr [rax+rax+00h]
0x140047fbc  test    eax, eax
0x140047fbe  jz      short loc_140047FF0
0x140047fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140047fc7  cmp     rcx, rbx
0x140047fca  jz      short loc_140047FF0
0x140047fcc  test    byte ptr [rcx+1Ch], 4
0x140047fd0  jz      short loc_140047FF0
0x140047fd2  cmp     byte ptr [rcx+19h], 2
0x140047fd6  jb      short loc_140047FF0
0x140047fd8  mov     edx, 0Fh
0x140047fdd  mov     r9d, eax
0x140047fe0  mov     rcx, [rcx+10h]
0x140047fe4  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047feb  call    WPP_SF_d
0x140047ff0  lea     r11, [rsp+88h+var_18]
0x140047ff5  mov     eax, edi
0x140047ff7  mov     rbx, [r11+28h]
0x140047ffb  mov     rbp, [r11+30h]
0x140047fff  mov     rsp, r11
0x140048002  pop     r15
0x140048004  pop     r14
0x140048006  pop     rdi
0x140048007  retn
```
