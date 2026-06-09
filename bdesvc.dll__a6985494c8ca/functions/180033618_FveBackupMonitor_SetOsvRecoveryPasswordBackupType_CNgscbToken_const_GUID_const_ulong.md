# FveBackupMonitor::SetOsvRecoveryPasswordBackupType(CNgscbToken const *,_GUID const *,ulong)

- ea: `0x180033618`
- end: `0x180033952`
- name: `?SetOsvRecoveryPasswordBackupType@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEBU_GUID@@K@Z`
- size: `826`
- prototype: `__int64 __fastcall(const struct CNgscbToken *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b560`

## callees

- `0x180009f60`
- `0x18001b7f0`
- `0x18001b890`
- `0x180021d18`
- `0x180026190`
- `0x180033618`
- `0x180034070`
- `0x180034d28`
- `0x18006fc78`
- `0x180070958`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180033912`
- `ntdll!RtlFreeUnicodeString` at `0x180033912`
- `ntdll!RtlStringFromGUID` at `0x180033718`
- `ntdll!RtlStringFromGUID` at `0x180033718`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033848`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800338b8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033848`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800338b8`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::SetOsvRecoveryPasswordBackupType(
        const struct CNgscbToken *a1,
        const struct _GUID *a2,
        int a3)
{
  signed int v6; // ebx
  unsigned int v7; // eax
  NTSTATUS v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int OsvRecoveryPasswordBackupTypeMaskForUser; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  _BYTE v15[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Data; // [rsp+34h] [rbp-CCh] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  Data = 0;
  v15[0] = 0;
  GuidString = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_929186be452536e5252128d48ffaedab_Traceguids, 2147500035LL);
LABEL_42:
    FveBackupMonitor::DeleteOsvRecoveryPasswordBackupTypeRecords(0);
    goto LABEL_43;
  }
  if ( a1 )
  {
    v7 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)v15, a1);
    v6 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_929186be452536e5252128d48ffaedab_Traceguids, v7);
      if ( v6 < 0 )
        goto LABEL_42;
    }
  }
  v8 = RtlStringFromGUID(a2, &GuidString);
  v9 = FromNtStatus(v8);
  v6 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_929186be452536e5252128d48ffaedab_Traceguids, v9);
    if ( v6 < 0 )
      goto LABEL_42;
  }
  v10 = StringCchPrintfW(
          SubKey,
          0x104u,
          L"%s\\%s",
          L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\KeyBackupMonitor",
          L"OSV");
  v6 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_929186be452536e5252128d48ffaedab_Traceguids, v10);
    if ( v6 < 0 )
      goto LABEL_42;
  }
  OsvRecoveryPasswordBackupTypeMaskForUser = FveBackupMonitor::GetOsvRecoveryPasswordBackupTypeMaskForUser(0, a2, &Data);
  v6 = OsvRecoveryPasswordBackupTypeMaskForUser;
  if ( OsvRecoveryPasswordBackupTypeMaskForUser )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_929186be452536e5252128d48ffaedab_Traceguids,
        OsvRecoveryPasswordBackupTypeMaskForUser);
    if ( v6 < 0 )
      goto LABEL_42;
  }
  if ( (a3 & Data) != 0 )
  {
    v6 = 0;
    goto LABEL_43;
  }
  Data |= a3;
  v12 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"RecoveryPwdId", 2u, GuidString.Buffer, GuidString.Length + 2);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_929186be452536e5252128d48ffaedab_Traceguids,
        (unsigned int)v6);
    if ( v6 < 0 )
      goto LABEL_42;
  }
  v13 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"RecoveryPwdBackupType", 4u, &Data, 4u);
  v6 = v13;
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_929186be452536e5252128d48ffaedab_Traceguids,
        (unsigned int)v6);
    if ( v6 < 0 )
      goto LABEL_42;
  }
LABEL_43:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  CScopedImpersonation::Revert((CScopedImpersonation *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180033618  mov     [rsp-8+arg_18], rbx
0x18003361d  push    rbp
0x18003361e  push    rsi
0x18003361f  push    r12
0x180033621  push    r14
0x180033623  push    r15
0x180033625  lea     rbp, [rsp-170h]
0x18003362d  sub     rsp, 270h
0x180033634  mov     rax, cs:__security_cookie
0x18003363b  xor     rax, rsp
0x18003363e  mov     [rbp+190h+var_30], rax
0x180033645  mov     r12d, r8d
0x180033648  mov     r15, rdx
0x18003364b  mov     rbx, rcx
0x18003364e  xor     edx, edx; Val
0x180033650  mov     r8d, 208h; Size
0x180033656  lea     rcx, [rsp+290h+SubKey]; void *
0x18003365b  call    memset_0
0x180033660  mov     [rsp+290h+Data], 0
0x180033668  xorps   xmm0, xmm0
0x18003366b  mov     [rsp+290h+var_260], 0
0x180033670  movups  xmmword ptr [rsp+290h+GuidString.Length], xmm0
0x180033675  test    r15, r15
0x180033678  jnz     short loc_1800336BC
0x18003367a  mov     ebx, 80004003h
0x18003367f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033686  lea     rsi, WPP_GLOBAL_Control
0x18003368d  cmp     rcx, rsi
0x180033690  jz      loc_1800338FE
0x180033696  test    byte ptr [rcx+1Ch], 40h
0x18003369a  jz      loc_1800338FE
0x1800336a0  mov     rcx, [rcx+10h]
0x1800336a4  lea     edx, [r15+27h]
0x1800336a8  mov     r9d, ebx
0x1800336ab  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x1800336b2  call    WPP_SF_d
0x1800336b7  jmp     loc_1800338FE
0x1800336bc  lea     rsi, WPP_GLOBAL_Control
0x1800336c3  lea     r14, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x1800336ca  test    rbx, rbx
0x1800336cd  jz      short loc_180033710
0x1800336cf  mov     rdx, rbx; struct CNgscbToken *
0x1800336d2  lea     rcx, [rsp+290h+var_260]; this
0x1800336d7  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x1800336dc  mov     ebx, eax
0x1800336de  test    eax, eax
0x1800336e0  jz      short loc_180033710
0x1800336e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336e9  cmp     rcx, rsi
0x1800336ec  jz      short loc_180033708
0x1800336ee  test    byte ptr [rcx+1Ch], 40h
0x1800336f2  jz      short loc_180033708
0x1800336f4  mov     rcx, [rcx+10h]
0x1800336f8  mov     edx, 28h ; '('
0x1800336fd  mov     r9d, eax
0x180033700  mov     r8, r14
0x180033703  call    WPP_SF_d
0x180033708  test    ebx, ebx
0x18003370a  js      loc_1800338FE
0x180033710  lea     rdx, [rsp+290h+GuidString]; GuidString
0x180033715  mov     rcx, r15; Guid
0x180033718  call    cs:__imp_RtlStringFromGUID
0x18003371f  nop     dword ptr [rax+rax+00h]
0x180033724  mov     ecx, eax; int
0x180033726  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18003372b  mov     ebx, eax
0x18003372d  test    eax, eax
0x18003372f  jz      short loc_18003375F
0x180033731  mov     rcx, cs:WPP_GLOBAL_Control
0x180033738  cmp     rcx, rsi
0x18003373b  jz      short loc_180033757
0x18003373d  test    byte ptr [rcx+1Ch], 40h
0x180033741  jz      short loc_180033757
0x180033743  mov     rcx, [rcx+10h]
0x180033747  mov     edx, 29h ; ')'
0x18003374c  mov     r9d, eax
0x18003374f  mov     r8, r14
0x180033752  call    WPP_SF_d
0x180033757  test    ebx, ebx
0x180033759  js      loc_1800338FE
0x18003375f  lea     rax, aOsv; "OSV"
0x180033766  mov     edx, 104h; unsigned __int64
0x18003376b  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033772  mov     [rsp+290h+lpData], rax
0x180033777  lea     r8, aSS; "%s\\%s"
0x18003377e  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x180033783  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033788  mov     ebx, eax
0x18003378a  test    eax, eax
0x18003378c  jz      short loc_1800337BC
0x18003378e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033795  cmp     rcx, rsi
0x180033798  jz      short loc_1800337B4
0x18003379a  test    byte ptr [rcx+1Ch], 40h
0x18003379e  jz      short loc_1800337B4
0x1800337a0  mov     rcx, [rcx+10h]
0x1800337a4  mov     edx, 2Ah ; '*'
0x1800337a9  mov     r9d, eax
0x1800337ac  mov     r8, r14
0x1800337af  call    WPP_SF_d
0x1800337b4  test    ebx, ebx
0x1800337b6  js      loc_1800338FE
0x1800337bc  lea     r8, [rsp+290h+Data]; unsigned int *
0x1800337c1  mov     rdx, r15; struct _GUID *
0x1800337c4  xor     ecx, ecx; struct CNgscbToken *
0x1800337c6  call    ?GetOsvRecoveryPasswordBackupTypeMaskForUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEBU_GUID@@PEAK@Z; FveBackupMonitor::GetOsvRecoveryPasswordBackupTypeMaskForUser(CNgscbToken const *,_GUID const *,ulong *)
0x1800337cb  mov     ebx, eax
0x1800337cd  test    eax, eax
0x1800337cf  jz      short loc_1800337FF
0x1800337d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337d8  cmp     rcx, rsi
0x1800337db  jz      short loc_1800337F7
0x1800337dd  test    byte ptr [rcx+1Ch], 40h
0x1800337e1  jz      short loc_1800337F7
0x1800337e3  mov     rcx, [rcx+10h]
0x1800337e7  mov     edx, 2Bh ; '+'
0x1800337ec  mov     r9d, eax
0x1800337ef  mov     r8, r14
0x1800337f2  call    WPP_SF_d
0x1800337f7  test    ebx, ebx
0x1800337f9  js      loc_1800338FE
0x1800337ff  mov     eax, [rsp+290h+Data]
0x180033803  test    eax, r12d
0x180033806  jz      short loc_18003380F
0x180033808  xor     ebx, ebx
0x18003380a  jmp     loc_180033905
0x18003380f  or      eax, r12d
0x180033812  lea     r8, aRecoverypwdid; "RecoveryPwdId"
0x180033819  mov     [rsp+290h+Data], eax
0x18003381d  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180033822  movzx   eax, [rsp+290h+GuidString.Length]
0x180033827  mov     r9d, 2; dwType
0x18003382d  add     eax, r9d
0x180033830  mov     r12, 0FFFFFFFF80000001h
0x180033837  mov     [rsp+290h+cbData], eax; cbData
0x18003383b  mov     rcx, r12; hKey
0x18003383e  mov     rax, [rsp+290h+GuidString.Buffer]
0x180033843  mov     [rsp+290h+lpData], rax; lpData
0x180033848  call    cs:__imp_RegSetKeyValueW
0x18003384f  nop     dword ptr [rax+rax+00h]
0x180033854  mov     ebx, eax
0x180033856  mov     r15d, 80070000h
0x18003385c  test    eax, eax
0x18003385e  jle     short loc_180033866
0x180033860  movzx   ebx, ax
0x180033863  or      ebx, r15d
0x180033866  test    ebx, ebx
0x180033868  jz      short loc_180033894
0x18003386a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033871  cmp     rcx, rsi
0x180033874  jz      short loc_180033890
0x180033876  test    byte ptr [rcx+1Ch], 40h
0x18003387a  jz      short loc_180033890
0x18003387c  mov     rcx, [rcx+10h]
0x180033880  mov     edx, 2Ch ; ','
0x180033885  mov     r9d, ebx
0x180033888  mov     r8, r14
0x18003388b  call    WPP_SF_d
0x180033890  test    ebx, ebx
0x180033892  js      short loc_1800338FE
0x180033894  mov     r9d, 4; dwType
0x18003389a  lea     rax, [rsp+290h+Data]
0x18003389f  mov     [rsp+290h+cbData], r9d; cbData
0x1800338a4  lea     r8, aRecoverypwdbac; "RecoveryPwdBackupType"
0x1800338ab  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800338b0  mov     [rsp+290h+lpData], rax; lpData
0x1800338b5  mov     rcx, r12; hKey
0x1800338b8  call    cs:__imp_RegSetKeyValueW
0x1800338bf  nop     dword ptr [rax+rax+00h]
0x1800338c4  mov     ebx, eax
0x1800338c6  test    eax, eax
0x1800338c8  jle     short loc_1800338D0
0x1800338ca  movzx   ebx, ax
0x1800338cd  or      ebx, r15d
0x1800338d0  test    ebx, ebx
0x1800338d2  jz      short loc_180033905
0x1800338d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338db  cmp     rcx, rsi
0x1800338de  jz      short loc_1800338FA
0x1800338e0  test    byte ptr [rcx+1Ch], 40h
0x1800338e4  jz      short loc_1800338FA
0x1800338e6  mov     rcx, [rcx+10h]
0x1800338ea  mov     edx, 2Dh ; '-'
0x1800338ef  mov     r9d, ebx
0x1800338f2  mov     r8, r14
0x1800338f5  call    WPP_SF_d
0x1800338fa  test    ebx, ebx
0x1800338fc  jns     short loc_180033905
0x1800338fe  xor     ecx, ecx; struct CNgscbToken *
0x180033900  call    ?DeleteOsvRecoveryPasswordBackupTypeRecords@FveBackupMonitor@@SAJPEBVCNgscbToken@@@Z; FveBackupMonitor::DeleteOsvRecoveryPasswordBackupTypeRecords(CNgscbToken const *)
0x180033905  cmp     [rsp+290h+GuidString.Buffer], 0
0x18003390b  jz      short loc_18003391E
0x18003390d  lea     rcx, [rsp+290h+GuidString]; UnicodeString
0x180033912  call    cs:__imp_RtlFreeUnicodeString
0x180033919  nop     dword ptr [rax+rax+00h]
0x18003391e  lea     rcx, [rsp+290h+var_260]; this
0x180033923  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x180033928  mov     eax, ebx
0x18003392a  mov     rcx, [rbp+190h+var_30]
0x180033931  xor     rcx, rsp; StackCookie
0x180033934  call    __security_check_cookie
0x180033939  mov     rbx, [rsp+290h+arg_18]
0x180033941  add     rsp, 270h
0x180033948  pop     r15
0x18003394a  pop     r14
0x18003394c  pop     r12
0x18003394e  pop     rsi
0x18003394f  pop     rbp
0x180033950  retn
```
