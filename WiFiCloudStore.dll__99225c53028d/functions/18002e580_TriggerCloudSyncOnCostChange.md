# TriggerCloudSyncOnCostChange

- ea: `0x18002e580`
- end: `0x18002e752`
- name: `TriggerCloudSyncOnCostChange`
- size: `466`
- prototype: `__int64 __fastcall(struct _GUID *, LPCWCH lpString1)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800242a0`
- `0x18002477c`
- `0x180024c14`
- `0x180029098`
- `0x180029130`
- `0x18002e580`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e64c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e64c`
- `wlanapi!WlanWcmGetProfileList` at `0x18002e5d9`
- `wlanapi!WlanWcmGetProfileList` at `0x18002e5d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TriggerCloudSyncOnCostChange(struct _GUID *a1, LPCWCH lpString1, int a3)
{
  unsigned int ProfileList; // ebx
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  unsigned int i; // ebx
  __int64 v11; // r14
  struct WCM_WLAN_PROFILE_INFO *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-48h]
  unsigned int **v18; // [rsp+30h] [rbp-38h] BYREF
  struct WCM_WLAN_PROFILE_INFO_LIST *v19; // [rsp+38h] [rbp-30h] BYREF
  char v20; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int *v22; // [rsp+70h] [rbp+8h] BYREF

  if ( a1 && lpString1 && *lpString1 )
  {
    try
    {
      v22 = 0;
      v18 = &v22;
      v19 = 0;
      v20 = 1;
      ProfileList = WlanWcmGetProfileList(a1, 0, &v19);
      wil::details::out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>>::~out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>>(&v18);
      if ( ProfileList )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1C,
               (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
               (const char *)ProfileList,
               bIgnoreCase);
        std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v22);
        result = v7;
      }
      else
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *v22 )
          {
            v16 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2C,
                    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
                    (const char *)0x490,
                    bIgnoreCase);
            std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v22);
            result = v16;
            goto LABEL_22;
          }
          v11 = 154LL * i;
          if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)&v22[v11 + 6], -1, 0) == 2 )
            break;
        }
        v12 = (struct WCM_WLAN_PROFILE_INFO *)&v22[v11 + 2];
        if ( (*((_BYTE *)v12 + 528) & 3) != 0 )
        {
          v15 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x31,
                  (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
                  (const char *)0x32,
                  bIgnoreCase);
          std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v22);
          result = v15;
        }
        else
        {
          v13 = CdsTriggerCostSyncIfProfileEligible(a1, v12, a3 != 0);
          v14 = v13;
          if ( v13 >= 0 )
          {
            std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v22);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
              (const char *)(unsigned int)v13,
              bIgnoreCase);
            std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v22);
            result = v14;
          }
        }
      }
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x38,
                               (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
                               v8);
    }
LABEL_22:
    ;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002e580  mov     r11, rsp
0x18002e583  mov     [r11+10h], rbx
0x18002e587  mov     [r11+18h], rsi
0x18002e58b  push    rdi
0x18002e58c  push    r14
0x18002e58e  push    r15
0x18002e590  sub     rsp, 50h
0x18002e594  mov     r15d, r8d
0x18002e597  mov     rdi, rdx
0x18002e59a  mov     rsi, rcx
0x18002e59d  test    rcx, rcx
0x18002e5a0  jz      loc_18002E715
0x18002e5a6  test    rdx, rdx
0x18002e5a9  jz      loc_18002E715
0x18002e5af  xor     eax, eax
0x18002e5b1  cmp     ax, [rdx]
0x18002e5b4  jz      loc_18002E715
0x18002e5ba  mov     [r11+8], rax
0x18002e5be  lea     rax, [r11+8]
0x18002e5c2  mov     [r11-38h], rax
0x18002e5c6  mov     qword ptr [r11-30h], 0
0x18002e5ce  mov     [rsp+68h+var_28], 1
0x18002e5d3  lea     r8, [r11-30h]
0x18002e5d7  xor     edx, edx
0x18002e5d9  call    cs:__imp_?WlanWcmGetProfileList@@YAKPEBU_GUID@@PEAXPEAPEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; WlanWcmGetProfileList(_GUID const *,void *,WCM_WLAN_PROFILE_INFO_LIST * *)
0x18002e5df  mov     ebx, eax
0x18002e5e1  lea     rcx, [rsp+68h+var_38]
0x18002e5e6  call    ??1?$out_param_t@V?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>>::~out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>>(void)
0x18002e5eb  test    ebx, ebx
0x18002e5ed  jz      short loc_18002E61B
0x18002e5ef  mov     rcx, [rsp+68h]; this
0x18002e5f4  mov     r9d, ebx; char *
0x18002e5f7  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002e5fe  mov     edx, 1Ch; void *
0x18002e603  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e608  mov     ebx, eax
0x18002e60a  lea     rcx, [rsp+68h+arg_0]
0x18002e60f  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(void)
0x18002e614  mov     eax, ebx
0x18002e616  jmp     loc_18002E73B
0x18002e61b  xor     ebx, ebx
0x18002e61d  mov     rax, [rsp+68h+arg_0]
0x18002e622  cmp     ebx, [rax]
0x18002e624  jnb     loc_18002E6E9
0x18002e62a  mov     ecx, ebx
0x18002e62c  imul    r14, rcx, 268h
0x18002e633  lea     r8, [rax+18h]
0x18002e637  add     r8, r14; lpString2
0x18002e63a  mov     [rsp+68h+bIgnoreCase], 0; unsigned int
0x18002e642  or      r9d, 0FFFFFFFFh; cchCount2
0x18002e646  or      edx, r9d; cchCount1
0x18002e649  mov     rcx, rdi; lpString1
0x18002e64c  call    cs:__imp_CompareStringOrdinal
0x18002e652  cmp     eax, 2
0x18002e655  jz      short loc_18002E65B
0x18002e657  inc     ebx
0x18002e659  jmp     short loc_18002E61D
0x18002e65b  mov     rdx, [rsp+68h+arg_0]
0x18002e660  add     rdx, 8
0x18002e664  add     rdx, r14; struct WCM_WLAN_PROFILE_INFO *
0x18002e667  test    byte ptr [rdx+210h], 3
0x18002e66e  jnz     short loc_18002E6BE
0x18002e670  test    r15d, r15d
0x18002e673  setnz   r8b; bool
0x18002e677  mov     rcx, rsi; struct _GUID *
0x18002e67a  call    ?CdsTriggerCostSyncIfProfileEligible@@YAJPEBU_GUID@@QEAUWCM_WLAN_PROFILE_INFO@@_N@Z; CdsTriggerCostSyncIfProfileEligible(_GUID const *,WCM_WLAN_PROFILE_INFO * const,bool)
0x18002e67f  mov     ebx, eax
0x18002e681  test    eax, eax
0x18002e683  jns     short loc_18002E6B0
0x18002e685  mov     rcx, [rsp+68h]; this
0x18002e68a  mov     r9d, eax; char *
0x18002e68d  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002e694  mov     edx, 34h ; '4'; void *
0x18002e699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e69e  nop
0x18002e69f  lea     rcx, [rsp+68h+arg_0]
0x18002e6a4  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(void)
0x18002e6a9  mov     eax, ebx
0x18002e6ab  jmp     loc_18002E73B
0x18002e6b0  lea     rcx, [rsp+68h+arg_0]
0x18002e6b5  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(void)
0x18002e6ba  xor     eax, eax
0x18002e6bc  jmp     short loc_18002E73B
0x18002e6be  mov     rcx, [rsp+68h]; this
0x18002e6c3  mov     r9d, 32h ; '2'; char *
0x18002e6c9  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002e6d0  lea     edx, [r9-1]; void *
0x18002e6d4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e6d9  mov     ebx, eax
0x18002e6db  lea     rcx, [rsp+68h+arg_0]
0x18002e6e0  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(void)
0x18002e6e5  mov     eax, ebx
0x18002e6e7  jmp     short loc_18002E73B
0x18002e6e9  mov     rcx, [rsp+68h]; this
0x18002e6ee  mov     r9d, 490h; char *
0x18002e6f4  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002e6fb  mov     edx, 2Ch ; ','; void *
0x18002e700  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e705  mov     ebx, eax
0x18002e707  lea     rcx, [rsp+68h+arg_0]
0x18002e70c  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(void)
0x18002e711  mov     eax, ebx
0x18002e713  jmp     short loc_18002E73B
0x18002e715  mov     rcx, [rsp+68h]; this
0x18002e71a  mov     ebx, 80070057h
0x18002e71f  mov     r9d, ebx; char *
0x18002e722  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002e729  mov     edx, 18h; void *
0x18002e72e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e733  mov     eax, ebx
0x18002e735  jmp     short loc_18002E73B
0x18002e737  mov     eax, dword ptr [rsp+68h+arg_0]
0x18002e73b  lea     r11, [rsp+68h+var_18]
0x18002e740  mov     rbx, [r11+28h]
0x18002e744  mov     rsi, [r11+30h]
0x18002e748  mov     rsp, r11
0x18002e74b  pop     r15
0x18002e74d  pop     r14
0x18002e74f  pop     rdi
0x18002e750  retn
```
