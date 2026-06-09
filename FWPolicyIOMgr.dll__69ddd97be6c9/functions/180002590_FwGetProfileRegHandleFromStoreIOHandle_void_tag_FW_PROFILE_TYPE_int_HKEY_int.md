# FwGetProfileRegHandleFromStoreIOHandle(void *,_tag_FW_PROFILE_TYPE,int,HKEY__ * *,int)

- ea: `0x180002590`
- end: `0x180002a4d`
- name: `?FwGetProfileRegHandleFromStoreIOHandle@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@HPEAPEAUHKEY__@@H@Z`
- size: `1213`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800022b0`

## callees

- `0x180001a18`
- `0x180002590`
- `0x1800042c4`
- `0x18001f650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002856`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002856`
- `fwbase!FwRegOpenKey` at `0x18000269b`
- `fwbase!FwRegOpenKey` at `0x180002795`
- `fwbase!FwRegOpenKey` at `0x1800029ab`
- `fwbase!FwRegOpenKey` at `0x180002a07`
- `fwbase!FwRegOpenKey` at `0x18000269b`
- `fwbase!FwRegOpenKey` at `0x180002795`
- `fwbase!FwRegOpenKey` at `0x1800029ab`
- `fwbase!FwRegOpenKey` at `0x180002a07`
- `fwbase!FwRegCloseKey` at `0x180002a42`
- `fwbase!FwRegCloseKey` at `0x180002a42`
- `fwbase!FwLicensingIsXbox` at `0x180002757`
- `fwbase!FwLicensingIsXbox` at `0x180002834`
- `fwbase!FwLicensingIsXbox` at `0x180002757`
- `fwbase!FwLicensingIsXbox` at `0x180002834`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x180002606`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x180002606`
- `fwbase!FwRegCreateKey` at `0x180002929`
- `fwbase!FwRegCreateKey` at `0x180002929`

## string_xrefs

- `0x180002848`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18000284f`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FwGetProfileRegHandleFromStoreIOHandle(__int64 a1, unsigned int a2, int a3, _QWORD *a4, int a5)
{
  int IsNewProfilesPresent; // esi
  int ProfileIndexFromProfileType; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // r14d
  int *v14; // rbx
  __int64 v15; // r15
  unsigned __int64 v16; // r14
  __int64 v17; // r9
  unsigned __int16 *v18; // rdx
  LPCOLESTR v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 *v22[4]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h] BYREF
  int v24; // [rsp+60h] [rbp+7h] BYREF
  int v25; // [rsp+64h] [rbp+Bh] BYREF

  IsNewProfilesPresent = 0;
  v22[0] = L"DomainProfile";
  v22[1] = L"StandardProfile";
  v22[2] = L"PublicProfile";
  v22[3] = L"PrivateProfile";
  v24 = 0;
  v23 = 0;
  ProfileIndexFromProfileType = FwGetProfileIndexFromProfileType(a2);
  v13 = ProfileIndexFromProfileType;
  if ( ProfileIndexFromProfileType >= 3 )
  {
    IsNewProfilesPresent = -2147024809;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v20 = 55;
      goto LABEL_15;
    }
    goto LABEL_18;
  }
  if ( (unsigned int)(ProfileIndexFromProfileType - 1) > 1 || (v14 = (int *)(a1 + 8), *(_DWORD *)(a1 + 8) != 1) )
  {
    v14 = (int *)(a1 + 8);
    if ( *(_DWORD *)(a1 + 8) != 6 || ProfileIndexFromProfileType != 1 )
      goto LABEL_5;
    goto LABEL_49;
  }
  v25 = 0;
  IsNewProfilesPresent = FwIsNewProfilesPresent((void *)a1, (const unsigned __int16 **)v22, &v25);
  if ( IsNewProfilesPresent < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v20 = 56;
      goto LABEL_15;
    }
    goto LABEL_18;
  }
  if ( v25 )
  {
    if ( v25 != 1 || v13 != 1 )
      goto LABEL_5;
LABEL_49:
    v13 = 3;
    goto LABEL_5;
  }
  v13 = 1;
LABEL_5:
  v15 = a1 + 168;
  if ( a3 )
    v15 = a1 + 200;
  v23 = *(_QWORD *)(a1 + 40);
  if ( ((*v14 - 2) & 0xFFFFFFF7) == 0 )
  {
    if ( (unsigned int)((__int64 (*)(void))FwLicensingIsXbox)() )
    {
      IsNewProfilesPresent = FwRegOpenKey(-2147483646, *(&PolicyStore + 33 * *v14 + 2), 1, &v23, &v24);
      if ( IsNewProfilesPresent < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v20 = 58;
          goto LABEL_15;
        }
        goto LABEL_18;
      }
    }
  }
  v16 = 8LL * v13;
  v17 = v16 + v15;
  if ( *(_QWORD *)(v16 + v15) )
    goto LABEL_16;
  v18 = v22[v16 / 8];
  if ( a3 == 1 )
  {
    IsNewProfilesPresent = FwRegCreateKey(v23, v18, 6, v17);
    if ( IsNewProfilesPresent < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v20 = 59;
        goto LABEL_15;
      }
      goto LABEL_18;
    }
    v24 = 1;
    goto LABEL_16;
  }
  IsNewProfilesPresent = FwRegOpenKey(v23, v18, 1, v17, &v24);
  if ( IsNewProfilesPresent < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v20 = 60;
      goto LABEL_15;
    }
    goto LABEL_18;
  }
  if ( v24 )
  {
LABEL_16:
    if ( a5
      && !a3
      && !(unsigned int)FwLicensingIsXbox(v11, v10, v12, v17)
      && (unsigned int)_o__wcsnicmp(
                         g_FwPersistentStoreRootKey,
                         L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                         73) )
    {
      v15 = a1 + 232;
      if ( a1 == -232 )
      {
        IsNewProfilesPresent = -2147024894;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v20 = 62;
          goto LABEL_15;
        }
        goto LABEL_18;
      }
      if ( !*(_QWORD *)(v16 + v15) )
      {
        IsNewProfilesPresent = FwRegOpenKey(-2147483646, *(&PolicyStore + 33 * *v14 + 3), 1, &v23, &v24);
        if ( IsNewProfilesPresent < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v20 = 63;
            goto LABEL_15;
          }
          goto LABEL_18;
        }
        if ( v24 )
        {
          IsNewProfilesPresent = FwRegOpenKey(v23, v22[v16 / 8], 1, v16 + v15, &v24);
          if ( IsNewProfilesPresent < 0 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v20 = 64;
              goto LABEL_15;
            }
            goto LABEL_18;
          }
        }
      }
    }
    *a4 = *(_QWORD *)(v16 + v15);
    goto LABEL_18;
  }
  IsNewProfilesPresent = -2147024894;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v20 = 61;
LABEL_15:
    WPP_SF_d(
      *((_QWORD *)v19 + 2),
      v20,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)IsNewProfilesPresent);
  }
LABEL_18:
  if ( v23 != *(_QWORD *)(a1 + 40) )
    FwRegCloseKey(v23);
  return (unsigned int)IsNewProfilesPresent;
}

```

## disassembly

```asm
0x180002590  mov     r11, rsp
0x180002593  push    rbp
0x180002594  push    rsi
0x180002595  lea     rbp, [r11-57h]
0x180002599  sub     rsp, 98h
0x1800025a0  mov     rax, cs:__security_cookie
0x1800025a7  xor     rax, rsp
0x1800025aa  mov     [rbp+4Fh+var_40], rax
0x1800025ae  mov     [r11+18h], rbx
0x1800025b2  lea     rax, aDomainprofile; "DomainProfile"
0x1800025b9  mov     [r11-18h], rdi
0x1800025bd  xor     esi, esi
0x1800025bf  mov     [r11-20h], r12
0x1800025c3  mov     rdi, rcx
0x1800025c6  mov     [rbp+4Fh+var_70], rax
0x1800025ca  mov     ecx, edx
0x1800025cc  mov     [r11-28h], r13
0x1800025d0  lea     rax, aStandardprofil_1; "StandardProfile"
0x1800025d7  mov     [rbp+4Fh+var_68], rax
0x1800025db  mov     r13, r9
0x1800025de  lea     rax, aPublicprofile; "PublicProfile"
0x1800025e5  mov     [r11-30h], r14
0x1800025e9  mov     [rbp+4Fh+var_60], rax
0x1800025ed  mov     r12d, r8d
0x1800025f0  lea     rax, aPrivateprofile; "PrivateProfile"
0x1800025f7  mov     [r11-38h], r15
0x1800025fb  mov     [rbp+4Fh+var_58], rax
0x1800025ff  mov     [rbp+4Fh+var_48], esi
0x180002602  mov     [rbp+4Fh+var_50], rsi
0x180002606  call    cs:__imp_FwGetProfileIndexFromProfileType
0x18000260c  mov     r14d, eax
0x18000260f  cmp     eax, 3
0x180002612  jge     loc_1800027D0
0x180002618  dec     eax
0x18000261a  cmp     eax, 1
0x18000261d  ja      short loc_18000262D
0x18000261f  cmp     dword ptr [rdi+8], 1
0x180002623  lea     rbx, [rdi+8]
0x180002627  jz      loc_1800028A4
0x18000262d  cmp     dword ptr [rdi+8], 6
0x180002631  lea     rbx, [rdi+8]
0x180002635  jz      loc_18000290E
0x18000263b  lea     r15, [rdi+0A8h]
0x180002642  test    r12d, r12d
0x180002645  jnz     loc_18000274B
0x18000264b  mov     rax, [rdi+28h]
0x18000264f  mov     [rbp+4Fh+var_50], rax
0x180002653  mov     eax, [rbx]
0x180002655  sub     eax, 2
0x180002658  test    eax, 0FFFFFFF7h
0x18000265d  jz      loc_180002757
0x180002663  movsxd  rax, r14d
0x180002666  lea     r14, ds:0[rax*8]
0x18000266e  cmp     qword ptr [r14+r15], 0
0x180002673  lea     r9, [r14+r15]
0x180002677  jnz     short loc_1800026E9
0x180002679  mov     rdx, [rbp+r14+4Fh+var_70]
0x18000267e  mov     rcx, [rbp+4Fh+var_50]
0x180002682  cmp     r12d, 1
0x180002686  jz      loc_180002923
0x18000268c  lea     rax, [rbp+4Fh+var_48]
0x180002690  mov     r8d, 1
0x180002696  mov     [rsp+20h], rax
0x18000269b  call    cs:__imp_FwRegOpenKey
0x1800026a1  mov     esi, eax
0x1800026a3  test    eax, eax
0x1800026a5  js      loc_180002800
0x1800026ab  cmp     [rbp+4Fh+var_48], 0
0x1800026af  jnz     short loc_1800026E9
0x1800026b1  mov     esi, 80070002h
0x1800026b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026bd  lea     rax, WPP_GLOBAL_Control
0x1800026c4  cmp     rcx, rax
0x1800026c7  jz      short loc_1800026FB
0x1800026c9  test    byte ptr [rcx+1Ch], 1
0x1800026cd  jz      short loc_1800026FB
0x1800026cf  mov     edx, 3Dh ; '='
0x1800026d4  mov     rcx, [rcx+10h]
0x1800026d8  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800026df  mov     r9d, esi
0x1800026e2  call    WPP_SF_d
0x1800026e7  jmp     short loc_1800026FB
0x1800026e9  cmp     [rbp+4Fh+arg_20], 0
0x1800026ed  jnz     loc_18000282B
0x1800026f3  mov     rax, [r14+r15]
0x1800026f7  mov     [r13+0], rax
0x1800026fb  mov     rcx, [rbp+4Fh+var_50]
0x1800026ff  cmp     rcx, [rdi+28h]
0x180002703  mov     rdi, [rsp+90h]
0x18000270b  mov     r15, [rsp+0A0h+var_30]
0x180002710  mov     r14, [rsp+0A0h+var_28]
0x180002715  mov     r13, [rsp+0A0h+var_20]
0x18000271d  mov     r12, [rsp+0A0h+var_18]
0x180002725  mov     rbx, [rsp+0A0h+arg_10]
0x18000272d  jnz     loc_180002A42
0x180002733  mov     eax, esi
0x180002735  mov     rcx, [rbp+4Fh+var_40]
0x180002739  xor     rcx, rsp; StackCookie
0x18000273c  call    __security_check_cookie
0x180002741  add     rsp, 98h
0x180002748  pop     rsi
0x180002749  pop     rbp
0x18000274a  retn
0x18000274b  lea     r15, [rdi+0C8h]
0x180002752  jmp     loc_18000264B
0x180002757  call    cs:__imp_FwLicensingIsXbox
0x18000275d  test    eax, eax
0x18000275f  jz      loc_180002663
0x180002765  movsxd  rax, dword ptr [rbx]
0x180002768  lea     r9, [rbp+4Fh+var_50]
0x18000276c  imul    rdx, rax, 108h
0x180002773  lea     rax, [rbp+4Fh+var_48]
0x180002777  mov     r8d, 1
0x18000277d  mov     [rsp+20h], rax
0x180002782  mov     rcx, 0FFFFFFFF80000002h
0x180002789  lea     rax, ?PolicyStore@@3PAU_tag_WF_POLICY_STORE@@A; _tag_WF_POLICY_STORE near * PolicyStore
0x180002790  mov     rdx, [rdx+rax+10h]
0x180002795  call    cs:__imp_FwRegOpenKey
0x18000279b  mov     esi, eax
0x18000279d  test    eax, eax
0x18000279f  jns     loc_180002663
0x1800027a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027ac  lea     rax, WPP_GLOBAL_Control
0x1800027b3  cmp     rcx, rax
0x1800027b6  jz      loc_1800026FB
0x1800027bc  test    byte ptr [rcx+1Ch], 1
0x1800027c0  jz      loc_1800026FB
0x1800027c6  mov     edx, 3Ah ; ':'
0x1800027cb  jmp     loc_1800026D4
0x1800027d0  mov     esi, 80070057h
0x1800027d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027dc  lea     rax, WPP_GLOBAL_Control
0x1800027e3  cmp     rcx, rax
0x1800027e6  jz      loc_1800026FB
0x1800027ec  test    byte ptr [rcx+1Ch], 1
0x1800027f0  jz      loc_1800026FB
0x1800027f6  mov     edx, 37h ; '7'
0x1800027fb  jmp     loc_1800026D4
0x180002800  mov     rcx, cs:WPP_GLOBAL_Control
0x180002807  lea     rax, WPP_GLOBAL_Control
0x18000280e  cmp     rcx, rax
0x180002811  jz      loc_1800026FB
0x180002817  test    byte ptr [rcx+1Ch], 1
0x18000281b  jz      loc_1800026FB
0x180002821  mov     edx, 3Ch ; '<'
0x180002826  jmp     loc_1800026D4
0x18000282b  test    r12d, r12d
0x18000282e  jnz     loc_1800026F3
0x180002834  call    cs:__imp_FwLicensingIsXbox
0x18000283a  test    eax, eax
0x18000283c  jnz     loc_1800026F3
0x180002842  mov     r8d, 49h ; 'I'
0x180002848  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18000284f  lea     rcx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180002856  call    cs:__imp__o__wcsnicmp
0x18000285c  test    eax, eax
0x18000285e  jz      loc_1800026F3
0x180002864  lea     r15, [rdi+0E8h]
0x18000286b  test    r15, r15
0x18000286e  jnz     loc_18000296C
0x180002874  mov     esi, 80070002h
0x180002879  mov     rcx, cs:WPP_GLOBAL_Control
0x180002880  lea     rax, WPP_GLOBAL_Control
0x180002887  cmp     rcx, rax
0x18000288a  jz      loc_1800026FB
0x180002890  test    byte ptr [rcx+1Ch], 1
0x180002894  jz      loc_1800026FB
0x18000289a  mov     edx, 3Eh ; '>'
0x18000289f  jmp     loc_1800026D4
0x1800028a4  lea     r8, [rbp+4Fh+var_44]; int *
0x1800028a8  mov     [rbp+4Fh+var_44], esi
0x1800028ab  lea     rdx, [rbp+4Fh+var_70]; unsigned __int16 **
0x1800028af  mov     rcx, rdi; void *
0x1800028b2  call    ?FwIsNewProfilesPresent@@YAJPEAXPEAPEBGPEAH@Z; FwIsNewProfilesPresent(void *,ushort const * *,int *)
0x1800028b7  mov     esi, eax
0x1800028b9  test    eax, eax
0x1800028bb  js      short loc_1800028D8
0x1800028bd  mov     eax, [rbp+4Fh+var_44]
0x1800028c0  test    eax, eax
0x1800028c2  jz      short loc_180002903
0x1800028c4  cmp     eax, 1
0x1800028c7  jnz     loc_18000263B
0x1800028cd  cmp     r14d, eax
0x1800028d0  jnz     loc_18000263B
0x1800028d6  jmp     short loc_180002918
0x1800028d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028df  lea     rax, WPP_GLOBAL_Control
0x1800028e6  cmp     rcx, rax
0x1800028e9  jz      loc_1800026FB
0x1800028ef  test    byte ptr [rcx+1Ch], 1
0x1800028f3  jz      loc_1800026FB
0x1800028f9  mov     edx, 38h ; '8'
0x1800028fe  jmp     loc_1800026D4
0x180002903  mov     r14d, 1
0x180002909  jmp     loc_18000263B
0x18000290e  cmp     r14d, 1
0x180002912  jnz     loc_18000263B
0x180002918  mov     r14d, 3
0x18000291e  jmp     loc_18000263B
0x180002923  mov     r8d, 6
0x180002929  call    cs:__imp_FwRegCreateKey
0x18000292f  mov     esi, eax
0x180002931  test    eax, eax
0x180002933  jns     short loc_180002960
0x180002935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000293c  lea     rax, WPP_GLOBAL_Control
0x180002943  cmp     rcx, rax
0x180002946  jz      loc_1800026FB
0x18000294c  test    byte ptr [rcx+1Ch], 1
0x180002950  jz      loc_1800026FB
0x180002956  mov     edx, 3Bh ; ';'
0x18000295b  jmp     loc_1800026D4
0x180002960  mov     [rbp+4Fh+var_48], 1
0x180002967  jmp     loc_1800026E9
0x18000296c  cmp     qword ptr [r14+r15], 0
0x180002971  lea     r12, [r14+r15]
0x180002975  jnz     loc_1800026F3
0x18000297b  movsxd  rax, dword ptr [rbx]
0x18000297e  lea     r9, [rbp+4Fh+var_50]
0x180002982  imul    rdx, rax, 108h
0x180002989  lea     rax, [rbp+4Fh+var_48]
0x18000298d  mov     r8d, 1
0x180002993  mov     [rsp+20h], rax
0x180002998  mov     rcx, 0FFFFFFFF80000002h
0x18000299f  lea     rax, ?PolicyStore@@3PAU_tag_WF_POLICY_STORE@@A; _tag_WF_POLICY_STORE near * PolicyStore
0x1800029a6  mov     rdx, [rdx+rax+18h]
0x1800029ab  call    cs:__imp_FwRegOpenKey
0x1800029b1  mov     esi, eax
0x1800029b3  test    eax, eax
0x1800029b5  jns     short loc_1800029E2
0x1800029b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029be  lea     rax, WPP_GLOBAL_Control
0x1800029c5  cmp     rcx, rax
0x1800029c8  jz      loc_1800026FB
0x1800029ce  test    byte ptr [rcx+1Ch], 1
0x1800029d2  jz      loc_1800026FB
0x1800029d8  mov     edx, 3Fh ; '?'
0x1800029dd  jmp     loc_1800026D4
0x1800029e2  cmp     [rbp+4Fh+var_48], 0
0x1800029e6  jz      loc_1800026F3
0x1800029ec  mov     rdx, [rbp+r14+4Fh+var_70]
0x1800029f1  lea     rax, [rbp+4Fh+var_48]
0x1800029f5  mov     rcx, [rbp+4Fh+var_50]
0x1800029f9  mov     r9, r12
0x1800029fc  mov     r8d, 1
0x180002a02  mov     [rsp+20h], rax
0x180002a07  call    cs:__imp_FwRegOpenKey
0x180002a0d  mov     esi, eax
0x180002a0f  test    eax, eax
0x180002a11  jns     loc_1800026F3
0x180002a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a1e  lea     rax, WPP_GLOBAL_Control
0x180002a25  cmp     rcx, rax
0x180002a28  jz      loc_1800026FB
0x180002a2e  test    byte ptr [rcx+1Ch], 1
0x180002a32  jz      loc_1800026FB
0x180002a38  mov     edx, 40h ; '@'
0x180002a3d  jmp     loc_1800026D4
0x180002a42  call    cs:__imp_FwRegCloseKey
0x180002a48  jmp     loc_180002733
```
