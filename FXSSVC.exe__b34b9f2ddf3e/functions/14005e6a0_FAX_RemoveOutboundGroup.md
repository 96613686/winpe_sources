# FAX_RemoveOutboundGroup

- ea: `0x14005e6a0`
- end: `0x14005e9e7`
- name: `FAX_RemoveOutboundGroup`
- size: `839`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x14002ce80`
- `0x1400452ac`
- `0x14005549c`
- `0x14005c340`
- `0x14005c704`
- `0x14005e6a0`
- `0x1400607e4`
- `0x1400708c4`
- `0x140070f1c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005e9b2`
- `ADVAPI32!RegCloseKey` at `0x14005e9b2`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e93a`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e93a`
- `KERNEL32!GetLastError` at `0x14005e8a0`
- `KERNEL32!GetLastError` at `0x14005e8fa`
- `KERNEL32!GetLastError` at `0x14005e8a0`
- `KERNEL32!GetLastError` at `0x14005e8fa`
- `KERNEL32!EnterCriticalSection` at `0x14005e7f1`
- `KERNEL32!EnterCriticalSection` at `0x14005e7f1`
- `KERNEL32!LeaveCriticalSection` at `0x14005e9bf`
- `KERNEL32!LeaveCriticalSection` at `0x14005e9bf`
- `msvcrt!_wcsicmp` at `0x14005e6fd`
- `msvcrt!_wcsicmp` at `0x14005e6fd`

## pseudocode

```c
__int64 __fastcall FAX_RemoveOutboundGroup(void *a1, unsigned __int16 *a2)
{
  unsigned __int64 v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  COutboundRulesMap *v8; // rcx
  DWORD IsGroupInRuleDest; // eax
  CMapDeviceId *v10; // rcx
  int v11; // edx
  HKEY v12; // rax
  HKEY v13; // rsi
  DWORD LastError; // eax
  LSTATUS v15; // eax
  COutboundRoutingGroupsMap *v16; // rcx
  CMapDeviceId *v17; // rcx
  int v18; // edx
  int v19; // [rsp+70h] [rbp+18h] BYREF
  int v20; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  v19 = 0;
  if ( !_wcsicmp(a2, L"<All devices>") )
    return 4317;
  if ( !(unsigned int)IsServerSku() )
    return (unsigned int)FindClientAPIVersion(a1) < 0x10000 ? 87 : 7011;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 >= 0x80 )
    return 111;
  v6 = FaxSvcAccessCheck(0x40u, &v19, 0, 1);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v6);
    }
    goto LABEL_61;
  }
  if ( v19 )
  {
    EnterCriticalSection(&g_CsConfig);
    v20 = 0;
    IsGroupInRuleDest = COutboundRulesMap::IsGroupInRuleDest(v8, a2, &v20);
    v7 = IsGroupInRuleDest;
    if ( IsGroupInRuleDest )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v11 = 109;
      goto LABEL_29;
    }
    if ( v20 == 1 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, a2);
      }
      v7 = 7004;
      goto LABEL_60;
    }
    if ( !COutboundRoutingGroupsMap::FindGroup(g_pGroupsMap, a2) )
    {
      IsGroupInRuleDest = GetLastError();
      v7 = IsGroupInRuleDest;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v11 = 111;
LABEL_29:
      WPP_SF_Sd(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (_DWORD)a2,
        IsGroupInRuleDest);
LABEL_60:
      LeaveCriticalSection(&g_CsConfig);
LABEL_61:
      if ( v7 == 8 || v7 == 14 )
        return 7001;
      return v7;
    }
    v12 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Groups", 0, 0x3001Fu);
    v13 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, LastError);
      }
      v7 = 1015;
      goto LABEL_60;
    }
    v15 = RegDeleteKeyW(v12, a2);
    v7 = v15;
    if ( v15 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v18 = 113;
    }
    else
    {
      v15 = COutboundRoutingGroupsMap::DelGroup(v16, a2);
      v7 = v15;
      if ( !v15 )
      {
        CreateConfigEvent(8);
        goto LABEL_59;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v18 = 114;
    }
    WPP_SF_Sd(*((_QWORD *)v17 + 2), v18, (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, (_DWORD)a2, v15);
LABEL_59:
    RegCloseKey(v13);
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x14005e6a0  mov     [rsp+arg_0], rbx
0x14005e6a5  push    rbp
0x14005e6a6  push    rsi
0x14005e6a7  push    rdi
0x14005e6a8  push    r12
0x14005e6aa  push    r15
0x14005e6ac  sub     rsp, 30h
0x14005e6b0  mov     rdi, rdx
0x14005e6b3  mov     rbx, rcx
0x14005e6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e6bd  lea     r15, WPP_GLOBAL_Control
0x14005e6c4  lea     r12, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005e6cb  cmp     rcx, r15
0x14005e6ce  jz      short loc_14005E6ED
0x14005e6d0  test    byte ptr [rcx+1Ch], 4
0x14005e6d4  jz      short loc_14005E6ED
0x14005e6d6  cmp     byte ptr [rcx+19h], 5
0x14005e6da  jb      short loc_14005E6ED
0x14005e6dc  mov     rcx, [rcx+10h]
0x14005e6e0  mov     edx, 69h ; 'i'
0x14005e6e5  mov     r8, r12
0x14005e6e8  call    WPP_SF_
0x14005e6ed  xor     ebp, ebp
0x14005e6ef  lea     rdx, aAllDevices; "<All devices>"
0x14005e6f6  mov     rcx, rdi; String1
0x14005e6f9  mov     [rsp+58h+arg_10], ebp
0x14005e6fd  call    cs:__imp__wcsicmp
0x14005e703  test    eax, eax
0x14005e705  jnz     short loc_14005E711
0x14005e707  mov     eax, 10DDh
0x14005e70c  jmp     loc_14005E9D6
0x14005e711  call    IsServerSku
0x14005e716  test    eax, eax
0x14005e718  jnz     short loc_14005E738
0x14005e71a  mov     rcx, rbx; void *
0x14005e71d  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x14005e722  cmp     eax, 10000h
0x14005e727  sbb     eax, eax
0x14005e729  and     eax, 0FFFFE4F4h
0x14005e72e  add     eax, 1B63h
0x14005e733  jmp     loc_14005E9D6
0x14005e738  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e73c  inc     rax
0x14005e73f  cmp     [rdi+rax*2], bp
0x14005e743  jnz     short loc_14005E73C
0x14005e745  cmp     rax, 80h
0x14005e74b  jb      short loc_14005E757
0x14005e74d  mov     eax, 6Fh ; 'o'
0x14005e752  jmp     loc_14005E9D6
0x14005e757  mov     r9d, 1; int
0x14005e75d  lea     rdx, [rsp+58h+arg_10]; int *
0x14005e762  xor     r8d, r8d; unsigned int *
0x14005e765  lea     ecx, [r9+3Fh]; unsigned int
0x14005e769  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14005e76e  mov     ebx, eax
0x14005e770  test    eax, eax
0x14005e772  jz      short loc_14005E7B1
0x14005e774  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e77b  cmp     rcx, r15
0x14005e77e  jz      loc_14005E9C5
0x14005e784  test    byte ptr [rcx+1Ch], 4
0x14005e788  jz      loc_14005E9C5
0x14005e78e  cmp     byte ptr [rcx+19h], 2
0x14005e792  jb      loc_14005E9C5
0x14005e798  mov     rcx, [rcx+10h]
0x14005e79c  mov     edx, 6Ah ; 'j'
0x14005e7a1  mov     r9d, eax
0x14005e7a4  mov     r8, r12
0x14005e7a7  call    WPP_SF_d
0x14005e7ac  jmp     loc_14005E9C5
0x14005e7b1  cmp     [rsp+58h+arg_10], ebp
0x14005e7b5  jnz     short loc_14005E7EA
0x14005e7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e7be  cmp     rcx, r15
0x14005e7c1  jz      short loc_14005E7E0
0x14005e7c3  test    byte ptr [rcx+1Ch], 4
0x14005e7c7  jz      short loc_14005E7E0
0x14005e7c9  cmp     byte ptr [rcx+19h], 2
0x14005e7cd  jb      short loc_14005E7E0
0x14005e7cf  mov     rcx, [rcx+10h]
0x14005e7d3  mov     edx, 6Bh ; 'k'
0x14005e7d8  mov     r8, r12
0x14005e7db  call    WPP_SF_
0x14005e7e0  mov     eax, 5
0x14005e7e5  jmp     loc_14005E9D6
0x14005e7ea  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005e7f1  call    cs:__imp_EnterCriticalSection
0x14005e7f7  lea     r8, [rsp+58h+arg_18]; int *
0x14005e7fc  mov     [rsp+58h+arg_18], ebp
0x14005e800  mov     rdx, rdi; unsigned __int16 *
0x14005e803  call    ?IsGroupInRuleDest@COutboundRulesMap@@QEBAKPEBGPEAH@Z; COutboundRulesMap::IsGroupInRuleDest(ushort const *,int *)
0x14005e808  mov     ebx, eax
0x14005e80a  test    eax, eax
0x14005e80c  jz      short loc_14005E84F
0x14005e80e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e815  cmp     rcx, r15
0x14005e818  jz      loc_14005E9B8
0x14005e81e  test    byte ptr [rcx+1Ch], 4
0x14005e822  jz      loc_14005E9B8
0x14005e828  cmp     byte ptr [rcx+19h], 2
0x14005e82c  jb      loc_14005E9B8
0x14005e832  mov     edx, 6Dh ; 'm'
0x14005e837  mov     rcx, [rcx+10h]
0x14005e83b  mov     r9, rdi
0x14005e83e  mov     r8, r12
0x14005e841  mov     [rsp+58h+var_38], eax
0x14005e845  call    WPP_SF_Sd
0x14005e84a  jmp     loc_14005E9B8
0x14005e84f  cmp     [rsp+58h+arg_18], 1
0x14005e854  jnz     short loc_14005E88C
0x14005e856  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e85d  cmp     rcx, r15
0x14005e860  jz      short loc_14005E882
0x14005e862  test    byte ptr [rcx+1Ch], 4
0x14005e866  jz      short loc_14005E882
0x14005e868  cmp     byte ptr [rcx+19h], 2
0x14005e86c  jb      short loc_14005E882
0x14005e86e  mov     rcx, [rcx+10h]
0x14005e872  mov     edx, 6Eh ; 'n'
0x14005e877  mov     r9, rdi
0x14005e87a  mov     r8, r12
0x14005e87d  call    WPP_SF_S
0x14005e882  mov     ebx, 1B5Ch
0x14005e887  jmp     loc_14005E9B8
0x14005e88c  mov     rcx, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; this
0x14005e893  mov     rdx, rdi; unsigned __int16 *
0x14005e896  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x14005e89b  test    rax, rax
0x14005e89e  jnz     short loc_14005E8D6
0x14005e8a0  call    cs:__imp_GetLastError
0x14005e8a6  mov     ebx, eax
0x14005e8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e8af  cmp     rcx, r15
0x14005e8b2  jz      loc_14005E9B8
0x14005e8b8  test    byte ptr [rcx+1Ch], 4
0x14005e8bc  jz      loc_14005E9B8
0x14005e8c2  cmp     byte ptr [rcx+19h], 2
0x14005e8c6  jb      loc_14005E9B8
0x14005e8cc  mov     edx, 6Fh ; 'o'
0x14005e8d1  jmp     loc_14005E837
0x14005e8d6  mov     r9d, 3001Fh
0x14005e8dc  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x14005e8e3  xor     r8d, r8d
0x14005e8e6  mov     rcx, 0FFFFFFFF80000002h
0x14005e8ed  call    OpenRegistryKey
0x14005e8f2  mov     rsi, rax
0x14005e8f5  test    rax, rax
0x14005e8f8  jnz     short loc_14005E934
0x14005e8fa  call    cs:__imp_GetLastError
0x14005e900  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e907  cmp     rcx, r15
0x14005e90a  jz      short loc_14005E92A
0x14005e90c  test    byte ptr [rcx+1Ch], 4
0x14005e910  jz      short loc_14005E92A
0x14005e912  cmp     byte ptr [rcx+19h], 2
0x14005e916  jb      short loc_14005E92A
0x14005e918  mov     rcx, [rcx+10h]
0x14005e91c  lea     edx, [rsi+70h]
0x14005e91f  mov     r9d, eax
0x14005e922  mov     r8, r12
0x14005e925  call    WPP_SF_d
0x14005e92a  mov     ebx, 3F7h
0x14005e92f  jmp     loc_14005E9B8
0x14005e934  mov     rdx, rdi; lpSubKey
0x14005e937  mov     rcx, rsi; hKey
0x14005e93a  call    cs:__imp_RegDeleteKeyW
0x14005e940  mov     ebx, eax
0x14005e942  test    eax, eax
0x14005e944  jz      short loc_14005E978
0x14005e946  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e94d  cmp     rcx, r15
0x14005e950  jz      short loc_14005E9AF
0x14005e952  test    byte ptr [rcx+1Ch], 4
0x14005e956  jz      short loc_14005E9AF
0x14005e958  cmp     byte ptr [rcx+19h], 2
0x14005e95c  jb      short loc_14005E9AF
0x14005e95e  mov     edx, 71h ; 'q'
0x14005e963  mov     rcx, [rcx+10h]
0x14005e967  mov     r9, rdi
0x14005e96a  mov     r8, r12
0x14005e96d  mov     [rsp+58h+var_38], eax
0x14005e971  call    WPP_SF_Sd
0x14005e976  jmp     short loc_14005E9AF
0x14005e978  mov     rdx, rdi; unsigned __int16 *
0x14005e97b  call    ?DelGroup@COutboundRoutingGroupsMap@@QEAAKPEBG@Z; COutboundRoutingGroupsMap::DelGroup(ushort const *)
0x14005e980  mov     ebx, eax
0x14005e982  test    eax, eax
0x14005e984  jz      short loc_14005E9A5
0x14005e986  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e98d  cmp     rcx, r15
0x14005e990  jz      short loc_14005E9AF
0x14005e992  test    byte ptr [rcx+1Ch], 4
0x14005e996  jz      short loc_14005E9AF
0x14005e998  cmp     byte ptr [rcx+19h], 2
0x14005e99c  jb      short loc_14005E9AF
0x14005e99e  mov     edx, 72h ; 'r'
0x14005e9a3  jmp     short loc_14005E963
0x14005e9a5  mov     ecx, 8
0x14005e9aa  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x14005e9af  mov     rcx, rsi; hKey
0x14005e9b2  call    cs:__imp_RegCloseKey
0x14005e9b8  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005e9bf  call    cs:__imp_LeaveCriticalSection
0x14005e9c5  cmp     ebx, 8
0x14005e9c8  jz      short loc_14005E9CF
0x14005e9ca  cmp     ebx, 0Eh
0x14005e9cd  jnz     short loc_14005E9D4
0x14005e9cf  mov     ebx, 1B59h
0x14005e9d4  mov     eax, ebx
0x14005e9d6  mov     rbx, [rsp+58h+arg_0]
0x14005e9db  add     rsp, 30h
0x14005e9df  pop     r15
0x14005e9e1  pop     r12
0x14005e9e3  pop     rdi
0x14005e9e4  pop     rsi
0x14005e9e5  pop     rbp
0x14005e9e6  retn
```
