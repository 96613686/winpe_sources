# CConnectedUserStore::GetRidFromInternetSid(void *,ulong *,_GUID *)

- ea: `0x1800014fc`
- end: `0x1800017ff`
- name: `?GetRidFromInternetSid@CConnectedUserStore@@AEAAJPEAXPEAKPEAU_GUID@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(const wchar_t **this, PSID Sid, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x180001064`
- `0x1800014fc`
- `0x180003560`
- `0x1800144b4`
- `0x1800145a0`
- `0x18001719c`
- `0x1800191ac`
- `0x180019722`
- `0x180019750`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001661`
- `msvcrt!_wcsicmp` at `0x180001661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800017ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800017ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001601`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180001744`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180001744`
- `SAMLIB!SamFreeMemory` at `0x1800017aa`
- `SAMLIB!SamFreeMemory` at `0x1800017ba`
- `SAMLIB!SamFreeMemory` at `0x1800017aa`
- `SAMLIB!SamFreeMemory` at `0x1800017ba`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800015f7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800015f7`

## string_xrefs

- `0x18000158e`: `CConnectedUserStore::GetRidFromInternetSid`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::GetRidFromInternetSid(
        const wchar_t **this,
        PSID Sid,
        unsigned int *a3,
        struct _GUID *a4)
{
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ebx
  CIdentityProfileHandler *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int IdentityProviderGuid; // eax
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // ebx
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+270h] [rbp+170h] BYREF

  v21 = 0;
  memset_0(Name, 0, 0x1FEu);
  memset_0(ReferencedDomainName, 0, 0x1FEu);
  *(_OWORD *)pv = 0;
  v25 = 0;
  v26 = 0;
  peUse = 0;
  cchName = 254;
  cchReferencedDomainName = 254;
  v28[1] = "CConnectedUserStore::GetRidFromInternetSid";
  v28[0] = &v21;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v8, "CConnectedUserStore::GetRidFromInternetSid");
  }
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, LastError);
    }
    if ( v12 == 1332 )
    {
      v12 = -805305819;
    }
    else if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
    }
LABEL_12:
    v21 = v12;
    goto LABEL_35;
  }
  if ( _wcsicmp(ReferencedDomainName, this[10]) )
  {
    IdentityProviderGuid = CConnectedUserStore::GetIdentityProviderGuid(
                             (CConnectedUserStore *)this,
                             ReferencedDomainName,
                             a4);
    v21 = IdentityProviderGuid;
    if ( IdentityProviderGuid >= 0 )
    {
      IdentityProviderGuid = MakeQualifiedIdentityName(ReferencedDomainName, Name, (struct _UNICODE_STRING *)pv);
      v21 = IdentityProviderGuid;
      if ( IdentityProviderGuid >= 0 )
      {
        v17 = SamLookupNamesInDomain2(this[12], 1, pv, &v25, &v26);
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              72,
              (unsigned int)WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
              pv[1],
              v17);
          }
          if ( v18 == -1073741709 )
            v18 = -1073741275;
          v12 = v18 | 0x10000000;
          goto LABEL_12;
        }
        *a3 = *v25;
        goto LABEL_35;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_35;
      }
      v14 = 71;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_35;
      }
      v14 = 70;
    }
    v15 = (unsigned int)IdentityProviderGuid;
    goto LABEL_17;
  }
  v21 = -805305819;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = 69;
    v15 = 3489661477LL;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v15);
  }
LABEL_35:
  if ( v25 )
    SamFreeMemory(v25);
  if ( v26 )
    SamFreeMemory(v26);
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  v19 = v21;
  CLogBlock::~CLogBlock((CLogBlock *)v28, v10, v11);
  return v19;
}

```

## disassembly

```asm
0x1800014fc  push    rbp
0x1800014fe  push    rbx
0x1800014ff  push    rsi
0x180001500  push    rdi
0x180001501  push    r14
0x180001503  push    r15
0x180001505  lea     rbp, [rsp-388h]
0x18000150d  sub     rsp, 488h
0x180001514  mov     rax, cs:__security_cookie
0x18000151b  xor     rax, rsp
0x18000151e  mov     [rbp+3B0h+var_40], rax
0x180001525  mov     rsi, r9
0x180001528  mov     rdi, r8
0x18000152b  mov     r14, rdx
0x18000152e  mov     rbx, rcx
0x180001531  mov     [rsp+4B0h+var_480], 0
0x180001539  mov     r15d, 1FEh
0x18000153f  mov     r8d, r15d; Size
0x180001542  xor     edx, edx; Val
0x180001544  lea     rcx, [rbp+3B0h+Name]; void *
0x18000154b  call    memset_0
0x180001550  mov     r8d, r15d; Size
0x180001553  xor     edx, edx; Val
0x180001555  lea     rcx, [rsp+4B0h+ReferencedDomainName]; void *
0x18000155a  call    memset_0
0x18000155f  xorps   xmm0, xmm0
0x180001562  movups  xmmword ptr [rsp+4B0h+pv], xmm0
0x180001567  mov     [rsp+4B0h+var_470], 0
0x180001570  mov     [rsp+4B0h+var_468], 0
0x180001579  mov     [rsp+4B0h+var_47C], 0
0x180001581  mov     eax, 0FEh
0x180001586  mov     [rsp+4B0h+cchName], eax
0x18000158a  mov     [rsp+4B0h+var_478], eax
0x18000158e  lea     r9, aCconnecteduser_11; "CConnectedUserStore::GetRidFromInternet"...
0x180001595  mov     [rsp+4B0h+var_448], r9
0x18000159a  lea     rax, [rsp+4B0h+var_480]
0x18000159f  mov     [rsp+4B0h+var_450], rax
0x1800015a4  lea     r15, WPP_GLOBAL_Control
0x1800015ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015b2  cmp     rcx, r15
0x1800015b5  jz      short loc_1800015CF
0x1800015b7  test    dword ptr [rcx+1Ch], 400h
0x1800015be  jz      short loc_1800015CF
0x1800015c0  mov     edx, 0Ah
0x1800015c5  mov     rcx, [rcx+10h]
0x1800015c9  call    WPP_SF_s
0x1800015ce  nop
0x1800015cf  lea     rax, [rsp+4B0h+var_47C]
0x1800015d4  mov     [rsp+4B0h+peUse], rax; peUse
0x1800015d9  lea     rax, [rsp+4B0h+var_478]
0x1800015de  mov     [rsp+4B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800015e3  lea     r9, [rsp+4B0h+ReferencedDomainName]; ReferencedDomainName
0x1800015e8  lea     r8, [rsp+4B0h+cchName]; cchName
0x1800015ed  lea     rdx, [rbp+3B0h+Name]; Name
0x1800015f4  mov     rcx, r14; Sid
0x1800015f7  call    cs:__imp_LookupAccountSidLocalW
0x1800015fd  test    eax, eax
0x1800015ff  jnz     short loc_180001658
0x180001601  call    cs:__imp_GetLastError
0x180001607  mov     ebx, eax
0x180001609  mov     rcx, cs:WPP_GLOBAL_Control
0x180001610  cmp     rcx, r15
0x180001613  jz      short loc_180001633
0x180001615  test    byte ptr [rcx+1Ch], 4
0x180001619  jz      short loc_180001633
0x18000161b  mov     edx, 44h ; 'D'
0x180001620  mov     r9d, eax
0x180001623  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000162a  mov     rcx, [rcx+10h]
0x18000162e  call    WPP_SF_d
0x180001633  cmp     ebx, 534h
0x180001639  jnz     short loc_180001642
0x18000163b  mov     ebx, 0D0000225h
0x180001640  jmp     short loc_18000164F
0x180001642  test    ebx, ebx
0x180001644  jle     short loc_18000164F
0x180001646  movzx   ebx, bx
0x180001649  or      ebx, 80070000h
0x18000164f  mov     [rsp+4B0h+var_480], ebx
0x180001653  jmp     loc_1800017A0
0x180001658  mov     rdx, [rbx+50h]; String2
0x18000165c  lea     rcx, [rsp+4B0h+ReferencedDomainName]; String1
0x180001661  call    cs:__imp__wcsicmp
0x180001667  test    eax, eax
0x180001669  jnz     short loc_1800016AC
0x18000166b  mov     ebx, 0D0000225h
0x180001670  mov     [rsp+4B0h+var_480], ebx
0x180001674  mov     rcx, cs:WPP_GLOBAL_Control
0x18000167b  cmp     rcx, r15
0x18000167e  jz      loc_1800017A0
0x180001684  test    byte ptr [rcx+1Ch], 4
0x180001688  jz      loc_1800017A0
0x18000168e  lea     edx, [rax+45h]
0x180001691  mov     r9d, 0D0000225h
0x180001697  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000169e  mov     rcx, [rcx+10h]
0x1800016a2  call    WPP_SF_d
0x1800016a7  jmp     loc_1800017A0
0x1800016ac  mov     r8, rsi; struct _GUID *
0x1800016af  lea     rdx, [rsp+4B0h+ReferencedDomainName]; String1
0x1800016b4  mov     rcx, rbx; this
0x1800016b7  call    ?GetIdentityProviderGuid@CConnectedUserStore@@AEAAJPEBGPEAU_GUID@@@Z; CConnectedUserStore::GetIdentityProviderGuid(ushort const *,_GUID *)
0x1800016bc  mov     [rsp+4B0h+var_480], eax
0x1800016c0  test    eax, eax
0x1800016c2  jns     short loc_1800016E8
0x1800016c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016cb  cmp     rcx, r15
0x1800016ce  jz      loc_1800017A0
0x1800016d4  test    byte ptr [rcx+1Ch], 4
0x1800016d8  jz      loc_1800017A0
0x1800016de  mov     edx, 46h ; 'F'
0x1800016e3  mov     r9d, eax
0x1800016e6  jmp     short loc_180001697
0x1800016e8  lea     r8, [rsp+4B0h+pv]; struct _UNICODE_STRING *
0x1800016ed  lea     rdx, [rbp+3B0h+Name]; wchar_t *
0x1800016f4  lea     rcx, [rsp+4B0h+ReferencedDomainName]; Source
0x1800016f9  call    ?MakeQualifiedIdentityName@@YAJPEBG0PEAU_UNICODE_STRING@@@Z; MakeQualifiedIdentityName(ushort const *,ushort const *,_UNICODE_STRING *)
0x1800016fe  mov     [rsp+4B0h+var_480], eax
0x180001702  test    eax, eax
0x180001704  jns     short loc_180001727
0x180001706  mov     rcx, cs:WPP_GLOBAL_Control
0x18000170d  cmp     rcx, r15
0x180001710  jz      loc_1800017A0
0x180001716  test    byte ptr [rcx+1Ch], 4
0x18000171a  jz      loc_1800017A0
0x180001720  mov     edx, 47h ; 'G'
0x180001725  jmp     short loc_1800016E3
0x180001727  lea     rax, [rsp+4B0h+var_468]
0x18000172c  mov     [rsp+4B0h+cchReferencedDomainName], rax
0x180001731  lea     r9, [rsp+4B0h+var_470]
0x180001736  lea     r8, [rsp+4B0h+pv]
0x18000173b  mov     edx, 1
0x180001740  mov     rcx, [rbx+60h]
0x180001744  call    cs:__imp_SamLookupNamesInDomain2
0x18000174a  mov     ebx, eax
0x18000174c  test    eax, eax
0x18000174e  jns     short loc_180001797
0x180001750  mov     rcx, cs:WPP_GLOBAL_Control
0x180001757  cmp     rcx, r15
0x18000175a  jz      short loc_180001780
0x18000175c  test    byte ptr [rcx+1Ch], 4
0x180001760  jz      short loc_180001780
0x180001762  mov     edx, 48h ; 'H'
0x180001767  mov     dword ptr [rsp+4B0h+cchReferencedDomainName], eax
0x18000176b  mov     r9, [rsp+4B0h+pv+8]
0x180001770  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180001777  mov     rcx, [rcx+10h]
0x18000177b  call    WPP_SF_Sd
0x180001780  mov     eax, 0C0000225h
0x180001785  cmp     ebx, 0C0000073h
0x18000178b  cmovz   ebx, eax
0x18000178e  bts     ebx, 1Ch
0x180001792  jmp     loc_18000164F
0x180001797  mov     rax, [rsp+4B0h+var_470]
0x18000179c  mov     ecx, [rax]
0x18000179e  mov     [rdi], ecx
0x1800017a0  mov     rcx, [rsp+4B0h+var_470]
0x1800017a5  test    rcx, rcx
0x1800017a8  jz      short loc_1800017B0
0x1800017aa  call    cs:__imp_SamFreeMemory
0x1800017b0  mov     rcx, [rsp+4B0h+var_468]
0x1800017b5  test    rcx, rcx
0x1800017b8  jz      short loc_1800017C0
0x1800017ba  call    cs:__imp_SamFreeMemory
0x1800017c0  mov     rcx, [rsp+4B0h+pv+8]; pv
0x1800017c5  test    rcx, rcx
0x1800017c8  jz      short loc_1800017D0
0x1800017ca  call    cs:__imp_CoTaskMemFree
0x1800017d0  mov     ebx, [rsp+4B0h+var_480]
0x1800017d4  lea     rcx, [rsp+4B0h+var_450]; this
0x1800017d9  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800017de  mov     eax, ebx
0x1800017e0  mov     rcx, [rbp+3B0h+var_40]
0x1800017e7  xor     rcx, rsp; StackCookie
0x1800017ea  call    __security_check_cookie
0x1800017ef  add     rsp, 488h
0x1800017f6  pop     r15
0x1800017f8  pop     r14
0x1800017fa  pop     rdi
0x1800017fb  pop     rsi
0x1800017fc  pop     rbx
0x1800017fd  pop     rbp
0x1800017fe  retn
```
