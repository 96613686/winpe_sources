# FAX_RemoveOutboundGroup

- ea: `0x140061e40`
- end: `0x1400621b2`
- name: `FAX_RemoveOutboundGroup`
- size: `882`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x14002e3d4`
- `0x140047d20`
- `0x1400589ac`
- `0x14005fa1c`
- `0x14005fdf8`
- `0x140061e40`
- `0x14006409c`
- `0x140074f18`
- `0x14007566c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140062170`
- `ADVAPI32!RegCloseKey` at `0x140062170`
- `ADVAPI32!RegDeleteKeyW` at `0x1400620f2`
- `ADVAPI32!RegDeleteKeyW` at `0x1400620f2`
- `KERNEL32!GetLastError` at `0x14006204c`
- `KERNEL32!GetLastError` at `0x1400620ac`
- `KERNEL32!GetLastError` at `0x14006204c`
- `KERNEL32!GetLastError` at `0x1400620ac`
- `KERNEL32!EnterCriticalSection` at `0x140061f97`
- `KERNEL32!EnterCriticalSection` at `0x140061f97`
- `KERNEL32!LeaveCriticalSection` at `0x140062183`
- `KERNEL32!LeaveCriticalSection` at `0x140062183`
- `msvcrt!_wcsicmp` at `0x140061e9d`
- `msvcrt!_wcsicmp` at `0x140061e9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    return FindClientAPIVersion(a1) < 0x10000 ? 87 : 7011;
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
    v12 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Outbound Routing\\Groups", 0, 196639);
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
0x140061e40  mov     [rsp+arg_0], rbx
0x140061e45  push    rbp
0x140061e46  push    rsi
0x140061e47  push    rdi
0x140061e48  push    r12
0x140061e4a  push    r15
0x140061e4c  sub     rsp, 30h
0x140061e50  mov     rdi, rdx
0x140061e53  mov     rbx, rcx
0x140061e56  mov     rcx, cs:WPP_GLOBAL_Control
0x140061e5d  lea     r15, WPP_GLOBAL_Control
0x140061e64  lea     r12, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x140061e6b  cmp     rcx, r15
0x140061e6e  jz      short loc_140061E8D
0x140061e70  test    byte ptr [rcx+1Ch], 4
0x140061e74  jz      short loc_140061E8D
0x140061e76  cmp     byte ptr [rcx+19h], 5
0x140061e7a  jb      short loc_140061E8D
0x140061e7c  mov     rcx, [rcx+10h]
0x140061e80  mov     edx, 69h ; 'i'
0x140061e85  mov     r8, r12
0x140061e88  call    WPP_SF_
0x140061e8d  xor     ebp, ebp
0x140061e8f  lea     rdx, aAllDevices; "<All devices>"
0x140061e96  mov     rcx, rdi; String1
0x140061e99  mov     [rsp+58h+arg_10], ebp
0x140061e9d  call    cs:__imp__wcsicmp
0x140061ea4  nop     dword ptr [rax+rax+00h]
0x140061ea9  test    eax, eax
0x140061eab  jnz     short loc_140061EB7
0x140061ead  mov     eax, 10DDh
0x140061eb2  jmp     loc_1400621A0
0x140061eb7  call    IsServerSku
0x140061ebc  test    eax, eax
0x140061ebe  jnz     short loc_140061EDE
0x140061ec0  mov     rcx, rbx; void *
0x140061ec3  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x140061ec8  cmp     eax, 10000h
0x140061ecd  sbb     eax, eax
0x140061ecf  and     eax, 0FFFFE4F4h
0x140061ed4  add     eax, 1B63h
0x140061ed9  jmp     loc_1400621A0
0x140061ede  or      rax, 0FFFFFFFFFFFFFFFFh
0x140061ee2  inc     rax
0x140061ee5  cmp     [rdi+rax*2], bp
0x140061ee9  jnz     short loc_140061EE2
0x140061eeb  cmp     rax, 80h
0x140061ef1  jb      short loc_140061EFD
0x140061ef3  mov     eax, 6Fh ; 'o'
0x140061ef8  jmp     loc_1400621A0
0x140061efd  mov     r9d, 1; int
0x140061f03  lea     rdx, [rsp+58h+arg_10]; int *
0x140061f08  xor     r8d, r8d; unsigned int *
0x140061f0b  lea     ecx, [r9+3Fh]; unsigned int
0x140061f0f  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140061f14  mov     ebx, eax
0x140061f16  test    eax, eax
0x140061f18  jz      short loc_140061F57
0x140061f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140061f21  cmp     rcx, r15
0x140061f24  jz      loc_14006218F
0x140061f2a  test    byte ptr [rcx+1Ch], 4
0x140061f2e  jz      loc_14006218F
0x140061f34  cmp     byte ptr [rcx+19h], 2
0x140061f38  jb      loc_14006218F
0x140061f3e  mov     rcx, [rcx+10h]
0x140061f42  mov     edx, 6Ah ; 'j'
0x140061f47  mov     r9d, eax
0x140061f4a  mov     r8, r12
0x140061f4d  call    WPP_SF_d
0x140061f52  jmp     loc_14006218F
0x140061f57  cmp     [rsp+58h+arg_10], ebp
0x140061f5b  jnz     short loc_140061F90
0x140061f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140061f64  cmp     rcx, r15
0x140061f67  jz      short loc_140061F86
0x140061f69  test    byte ptr [rcx+1Ch], 4
0x140061f6d  jz      short loc_140061F86
0x140061f6f  cmp     byte ptr [rcx+19h], 2
0x140061f73  jb      short loc_140061F86
0x140061f75  mov     rcx, [rcx+10h]
0x140061f79  mov     edx, 6Bh ; 'k'
0x140061f7e  mov     r8, r12
0x140061f81  call    WPP_SF_
0x140061f86  mov     eax, 5
0x140061f8b  jmp     loc_1400621A0
0x140061f90  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140061f97  call    cs:__imp_EnterCriticalSection
0x140061f9e  nop     dword ptr [rax+rax+00h]
0x140061fa3  lea     r8, [rsp+58h+arg_18]; int *
0x140061fa8  mov     [rsp+58h+arg_18], ebp
0x140061fac  mov     rdx, rdi; unsigned __int16 *
0x140061faf  call    ?IsGroupInRuleDest@COutboundRulesMap@@QEBAKPEBGPEAH@Z; COutboundRulesMap::IsGroupInRuleDest(ushort const *,int *)
0x140061fb4  mov     ebx, eax
0x140061fb6  test    eax, eax
0x140061fb8  jz      short loc_140061FFB
0x140061fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140061fc1  cmp     rcx, r15
0x140061fc4  jz      loc_14006217C
0x140061fca  test    byte ptr [rcx+1Ch], 4
0x140061fce  jz      loc_14006217C
0x140061fd4  cmp     byte ptr [rcx+19h], 2
0x140061fd8  jb      loc_14006217C
0x140061fde  mov     edx, 6Dh ; 'm'
0x140061fe3  mov     rcx, [rcx+10h]
0x140061fe7  mov     r9, rdi
0x140061fea  mov     r8, r12
0x140061fed  mov     [rsp+58h+var_38], eax
0x140061ff1  call    WPP_SF_Sd
0x140061ff6  jmp     loc_14006217C
0x140061ffb  cmp     [rsp+58h+arg_18], 1
0x140062000  jnz     short loc_140062038
0x140062002  mov     rcx, cs:WPP_GLOBAL_Control
0x140062009  cmp     rcx, r15
0x14006200c  jz      short loc_14006202E
0x14006200e  test    byte ptr [rcx+1Ch], 4
0x140062012  jz      short loc_14006202E
0x140062014  cmp     byte ptr [rcx+19h], 2
0x140062018  jb      short loc_14006202E
0x14006201a  mov     rcx, [rcx+10h]
0x14006201e  mov     edx, 6Eh ; 'n'
0x140062023  mov     r9, rdi
0x140062026  mov     r8, r12
0x140062029  call    WPP_SF_S
0x14006202e  mov     ebx, 1B5Ch
0x140062033  jmp     loc_14006217C
0x140062038  mov     rcx, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; this
0x14006203f  mov     rdx, rdi; unsigned __int16 *
0x140062042  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x140062047  test    rax, rax
0x14006204a  jnz     short loc_140062088
0x14006204c  call    cs:__imp_GetLastError
0x140062053  nop     dword ptr [rax+rax+00h]
0x140062058  mov     ebx, eax
0x14006205a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062061  cmp     rcx, r15
0x140062064  jz      loc_14006217C
0x14006206a  test    byte ptr [rcx+1Ch], 4
0x14006206e  jz      loc_14006217C
0x140062074  cmp     byte ptr [rcx+19h], 2
0x140062078  jb      loc_14006217C
0x14006207e  mov     edx, 6Fh ; 'o'
0x140062083  jmp     loc_140061FE3
0x140062088  mov     r9d, 3001Fh
0x14006208e  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x140062095  xor     r8d, r8d
0x140062098  mov     rcx, 0FFFFFFFF80000002h
0x14006209f  call    OpenRegistryKey
0x1400620a4  mov     rsi, rax
0x1400620a7  test    rax, rax
0x1400620aa  jnz     short loc_1400620EC
0x1400620ac  call    cs:__imp_GetLastError
0x1400620b3  nop     dword ptr [rax+rax+00h]
0x1400620b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400620bf  cmp     rcx, r15
0x1400620c2  jz      short loc_1400620E2
0x1400620c4  test    byte ptr [rcx+1Ch], 4
0x1400620c8  jz      short loc_1400620E2
0x1400620ca  cmp     byte ptr [rcx+19h], 2
0x1400620ce  jb      short loc_1400620E2
0x1400620d0  mov     rcx, [rcx+10h]
0x1400620d4  lea     edx, [rsi+70h]
0x1400620d7  mov     r9d, eax
0x1400620da  mov     r8, r12
0x1400620dd  call    WPP_SF_d
0x1400620e2  mov     ebx, 3F7h
0x1400620e7  jmp     loc_14006217C
0x1400620ec  mov     rdx, rdi; lpSubKey
0x1400620ef  mov     rcx, rsi; hKey
0x1400620f2  call    cs:__imp_RegDeleteKeyW
0x1400620f9  nop     dword ptr [rax+rax+00h]
0x1400620fe  mov     ebx, eax
0x140062100  test    eax, eax
0x140062102  jz      short loc_140062136
0x140062104  mov     rcx, cs:WPP_GLOBAL_Control
0x14006210b  cmp     rcx, r15
0x14006210e  jz      short loc_14006216D
0x140062110  test    byte ptr [rcx+1Ch], 4
0x140062114  jz      short loc_14006216D
0x140062116  cmp     byte ptr [rcx+19h], 2
0x14006211a  jb      short loc_14006216D
0x14006211c  mov     edx, 71h ; 'q'
0x140062121  mov     rcx, [rcx+10h]
0x140062125  mov     r9, rdi
0x140062128  mov     r8, r12
0x14006212b  mov     [rsp+58h+var_38], eax
0x14006212f  call    WPP_SF_Sd
0x140062134  jmp     short loc_14006216D
0x140062136  mov     rdx, rdi; unsigned __int16 *
0x140062139  call    ?DelGroup@COutboundRoutingGroupsMap@@QEAAKPEBG@Z; COutboundRoutingGroupsMap::DelGroup(ushort const *)
0x14006213e  mov     ebx, eax
0x140062140  test    eax, eax
0x140062142  jz      short loc_140062163
0x140062144  mov     rcx, cs:WPP_GLOBAL_Control
0x14006214b  cmp     rcx, r15
0x14006214e  jz      short loc_14006216D
0x140062150  test    byte ptr [rcx+1Ch], 4
0x140062154  jz      short loc_14006216D
0x140062156  cmp     byte ptr [rcx+19h], 2
0x14006215a  jb      short loc_14006216D
0x14006215c  mov     edx, 72h ; 'r'
0x140062161  jmp     short loc_140062121
0x140062163  mov     ecx, 8
0x140062168  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x14006216d  mov     rcx, rsi; hKey
0x140062170  call    cs:__imp_RegCloseKey
0x140062177  nop     dword ptr [rax+rax+00h]
0x14006217c  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140062183  call    cs:__imp_LeaveCriticalSection
0x14006218a  nop     dword ptr [rax+rax+00h]
0x14006218f  cmp     ebx, 8
0x140062192  jz      short loc_140062199
0x140062194  cmp     ebx, 0Eh
0x140062197  jnz     short loc_14006219E
0x140062199  mov     ebx, 1B59h
0x14006219e  mov     eax, ebx
0x1400621a0  mov     rbx, [rsp+58h+arg_0]
0x1400621a5  add     rsp, 30h
0x1400621a9  pop     r15
0x1400621ab  pop     r12
0x1400621ad  pop     rdi
0x1400621ae  pop     rsi
0x1400621af  pop     rbp
0x1400621b0  retn
```
