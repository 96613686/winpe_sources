# CConnectedUserStore::EnumConnectedUsersInSam(_CONNECTED_USER_SAM_INFO * *,ulong *)

- ea: `0x180003be0`
- end: `0x180004124`
- name: `?EnumConnectedUsersInSam@CConnectedUserStore@@AEAAJPEAPEAU_CONNECTED_USER_SAM_INFO@@PEAK@Z`
- size: `1348`
- prototype: `__int64 __fastcall(CConnectedUserStore *__hidden this, struct _CONNECTED_USER_SAM_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004e70`

## callees

- `0x180003be0`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`
- `0x180019722`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003cef`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003c7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003c7c`
- `SAMLIB!SamQueryInformationUser` at `0x180003d5b`
- `SAMLIB!SamQueryInformationUser` at `0x180003d5b`
- `SAMLIB!SamFreeMemory` at `0x180003df7`
- `SAMLIB!SamFreeMemory` at `0x180003e50`
- `SAMLIB!SamFreeMemory` at `0x1800040c5`
- `SAMLIB!SamFreeMemory` at `0x180003df7`
- `SAMLIB!SamFreeMemory` at `0x180003e50`
- `SAMLIB!SamFreeMemory` at `0x1800040c5`
- `SAMLIB!SamCloseHandle` at `0x180003e0a`
- `SAMLIB!SamCloseHandle` at `0x1800040da`
- `SAMLIB!SamCloseHandle` at `0x180003e0a`
- `SAMLIB!SamCloseHandle` at `0x1800040da`
- `SAMLIB!SamEnumerateUsersInDomain2` at `0x180003cc0`
- `SAMLIB!SamEnumerateUsersInDomain2` at `0x180003cc0`
- `SAMLIB!SamOpenUser` at `0x180003d3e`
- `SAMLIB!SamOpenUser` at `0x180003d3e`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::EnumConnectedUsersInSam(
        CConnectedUserStore *this,
        struct _CONNECTED_USER_SAM_INFO **a2,
        unsigned int *a3)
{
  __int64 v6; // r8
  struct _CONNECTED_USER_SAM_INFO *v7; // rsi
  int v8; // edx
  __int64 v9; // r8
  int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // r14d
  unsigned int i; // ebx
  __int64 v14; // r15
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  char *v20; // rdx
  CIdentityProfileHandler *v21; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  CConnectedUserStore *v30; // [rsp+68h] [rbp-98h]
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  char v32; // [rsp+18Ah] [rbp+8Ah]

  v30 = this;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v7 = 0;
  v25 = 0;
  v29 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, "CConnectedUserStore::EnumConnectedUsersInSam");
  }
  if ( GetVersionExW(&VersionInformation) && v32 == 2
    || (v10 = SamEnumerateUsersInDomain2(*((_QWORD *)this + 12), &v29, 0, 2, &v26, -1, &v25), v10 >= 0) )
  {
    if ( !v25 )
    {
      *a2 = (struct _CONNECTED_USER_SAM_INFO *)-1LL;
      *a3 = 0;
      v11 = 0;
      v21 = WPP_GLOBAL_Control;
      goto LABEL_28;
    }
    if ( 20 * (unsigned __int64)v25 > 0xFFFFFFFF )
    {
      v11 = -2147024362;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_28;
      }
      v23 = 99;
      v24 = 2147942934LL;
    }
    else
    {
      v7 = (struct _CONNECTED_USER_SAM_INFO *)CoTaskMemAlloc(20 * v25);
      if ( v7 )
      {
        v11 = 0;
        v12 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= v25 )
          {
            if ( v12 )
            {
              *a2 = v7;
              v7 = 0;
              *a3 = v12;
              v25 = 0;
            }
            else
            {
              *a2 = (struct _CONNECTED_USER_SAM_INFO *)-1LL;
              *a3 = 0;
            }
            goto LABEL_27;
          }
          v14 = 24LL * i;
          v15 = SamOpenUser(*((_QWORD *)v30 + 12), 0x2000000, *(unsigned int *)(v14 + v26), &v28);
          if ( v15 >= 0 )
            break;
          v11 = v15 | 0x10000000;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              101,
              WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
              *(unsigned int *)(v14 + v26),
              v11);
          }
LABEL_24:
          ;
        }
        v16 = SamQueryInformationUser(v28, 28, &v27);
        if ( v16 < 0 )
        {
          v11 = v16 | 0x10000000;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              102,
              WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
              *(unsigned int *)(v14 + v26),
              v16 | 0x10000000);
            v21 = WPP_GLOBAL_Control;
          }
          goto LABEL_28;
        }
        v17 = v27;
        if ( (*(_DWORD *)v27 & 0x40000) == 0 )
          goto LABEL_19;
        v18 = *(_QWORD *)(v27 + 96) - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v18 )
          v18 = *(_QWORD *)(v27 + 104) - *(_QWORD *)GUID_NULL.Data4;
        if ( v18 )
        {
          v19 = v12++;
          v20 = (char *)v7 + 20 * v19;
          *(_DWORD *)v20 = *(_DWORD *)(v14 + v26);
          *(_OWORD *)(v20 + 4) = *(_OWORD *)(v27 + 96);
        }
        else
        {
LABEL_19:
          if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          {
            goto LABEL_23;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            103,
            WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
            *(unsigned int *)(v14 + v26));
        }
        v17 = v27;
LABEL_23:
        SamFreeMemory(v17);
        v27 = 0;
        SamCloseHandle(v28);
        v28 = 0;
        goto LABEL_24;
      }
      v11 = -2147024882;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_28;
      }
      v23 = 100;
      v24 = 2147942414LL;
    }
  }
  else
  {
    v11 = v10 | 0x10000000;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_28;
    }
    v23 = 98;
    v24 = v11;
  }
  WPP_SF_d(*((_QWORD *)v21 + 2), v23, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v24);
LABEL_27:
  v21 = WPP_GLOBAL_Control;
LABEL_28:
  if ( v26 )
  {
    SamFreeMemory(v26);
    v21 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v21 = WPP_GLOBAL_Control;
  }
  if ( v27 )
  {
    SamFreeMemory(v27);
    v21 = WPP_GLOBAL_Control;
  }
  if ( v28 )
  {
    SamCloseHandle(v28);
    v21 = WPP_GLOBAL_Control;
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    *a2 = 0;
    *a3 = 0;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_39;
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      (unsigned int)"CConnectedUserStore::EnumConnectedUsersInSam",
      v11);
    goto LABEL_50;
  }
  if ( v21 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)v21 + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v21 + 2), 104, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, *a3);
LABEL_50:
    v21 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( v21 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v21 + 2), 12, v9, "CConnectedUserStore::EnumConnectedUsersInSam");
  return v11;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp-8+arg_18], rbx
0x180003be5  push    rbp
0x180003be6  push    rsi
0x180003be7  push    rdi
0x180003be8  push    r12
0x180003bea  push    r13
0x180003bec  push    r14
0x180003bee  push    r15
0x180003bf0  lea     rbp, [rsp-0A0h]
0x180003bf8  sub     rsp, 1A0h
0x180003bff  mov     rax, cs:__security_cookie
0x180003c06  xor     rax, rsp
0x180003c09  mov     [rbp+0D0h+var_40], rax
0x180003c10  mov     r13, r8
0x180003c13  mov     [rsp+1D0h+var_168], rcx
0x180003c18  mov     r12, rdx
0x180003c1b  mov     rbx, rcx
0x180003c1e  xor     edx, edx; Val
0x180003c20  lea     rcx, [rsp+1D0h+VersionInformation.dwMajorVersion]; void *
0x180003c25  mov     r8d, 118h; Size
0x180003c2b  call    memset_0
0x180003c30  xor     r15d, r15d
0x180003c33  mov     [rsp+1D0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180003c3b  mov     esi, r15d
0x180003c3e  mov     [rsp+1D0h+var_190], r15d
0x180003c43  mov     [rsp+1D0h+var_170], r15d
0x180003c48  mov     [rsp+1D0h+var_188], r15
0x180003c4d  mov     [rsp+1D0h+var_178], r15
0x180003c52  mov     [rsp+1D0h+var_180], r15
0x180003c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c5e  lea     rax, WPP_GLOBAL_Control
0x180003c65  cmp     rcx, rax
0x180003c68  jz      short loc_180003C77
0x180003c6a  test    dword ptr [rcx+1Ch], 400h
0x180003c71  jnz     loc_180003FB3
0x180003c77  lea     rcx, [rsp+1D0h+VersionInformation]; lpVersionInformation
0x180003c7c  call    cs:__imp_GetVersionExW
0x180003c82  mov     r14d, 0FFFFFFFFh
0x180003c88  test    eax, eax
0x180003c8a  jz      short loc_180003C95
0x180003c8c  cmp     [rbp+0D0h+var_46], 2
0x180003c93  jz      short loc_180003CD0
0x180003c95  mov     rcx, [rbx+60h]
0x180003c99  lea     rax, [rsp+1D0h+var_190]
0x180003c9e  mov     [rsp+1D0h+var_1A0], rax
0x180003ca3  lea     rdx, [rsp+1D0h+var_170]
0x180003ca8  lea     rax, [rsp+1D0h+var_188]
0x180003cad  mov     [rsp+1D0h+var_1A8], r14d
0x180003cb2  mov     r9d, 2
0x180003cb8  mov     [rsp+1D0h+var_1B0], rax
0x180003cbd  xor     r8d, r8d
0x180003cc0  call    cs:__imp_SamEnumerateUsersInDomain2
0x180003cc6  mov     edi, eax
0x180003cc8  test    eax, eax
0x180003cca  js      loc_180003F81
0x180003cd0  mov     eax, [rsp+1D0h+var_190]
0x180003cd4  test    eax, eax
0x180003cd6  jz      loc_180003F5F
0x180003cdc  lea     rcx, [rax+rax*4]
0x180003ce0  shl     rcx, 2
0x180003ce4  cmp     rcx, r14
0x180003ce7  ja      loc_180003ED7
0x180003ced  mov     ecx, ecx; cb
0x180003cef  call    cs:__imp_CoTaskMemAlloc
0x180003cf5  mov     rsi, rax
0x180003cf8  test    rax, rax
0x180003cfb  jz      loc_180003FCD
0x180003d01  mov     edi, r15d
0x180003d04  mov     r14d, r15d
0x180003d07  mov     ebx, r15d
0x180003d0a  cmp     ebx, [rsp+1D0h+var_190]
0x180003d0e  jnb     loc_180003E1C
0x180003d14  mov     r8, [rsp+1D0h+var_188]
0x180003d19  lea     r9, [rsp+1D0h+var_178]
0x180003d1e  mov     eax, ebx
0x180003d20  mov     edx, 2000000h
0x180003d25  lea     rcx, [rax+rax*2]
0x180003d29  mov     rax, [rsp+1D0h+var_168]
0x180003d2e  lea     r15, ds:0[rcx*8]
0x180003d36  mov     r8d, [r15+r8]
0x180003d3a  mov     rcx, [rax+60h]
0x180003d3e  call    cs:__imp_SamOpenUser
0x180003d44  test    eax, eax
0x180003d46  js      loc_180004003
0x180003d4c  mov     rcx, [rsp+1D0h+var_178]
0x180003d51  lea     r8, [rsp+1D0h+var_180]
0x180003d56  mov     edx, 1Ch
0x180003d5b  call    cs:__imp_SamQueryInformationUser
0x180003d61  test    eax, eax
0x180003d63  js      loc_18000404C
0x180003d69  mov     rcx, [rsp+1D0h+var_180]
0x180003d6e  test    dword ptr [rcx], 40000h
0x180003d74  jz      short loc_180003D93
0x180003d76  mov     rax, [rcx+60h]
0x180003d7a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180003d81  jnz     short loc_180003D8E
0x180003d83  mov     rax, [rcx+68h]
0x180003d87  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180003d8e  test    rax, rax
0x180003d91  jnz     short loc_180003DCC
0x180003d93  mov     rax, cs:WPP_GLOBAL_Control
0x180003d9a  lea     rdx, WPP_GLOBAL_Control
0x180003da1  cmp     rax, rdx
0x180003da4  jz      short loc_180003DF7
0x180003da6  test    byte ptr [rax+1Ch], 8
0x180003daa  jz      short loc_180003DF7
0x180003dac  mov     r9, [rsp+1D0h+var_188]
0x180003db1  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180003db8  mov     rcx, [rax+10h]
0x180003dbc  mov     edx, 67h ; 'g'
0x180003dc1  mov     r9d, [r15+r9]
0x180003dc5  call    WPP_SF_d
0x180003dca  jmp     short loc_180003DF2
0x180003dcc  mov     eax, r14d
0x180003dcf  inc     r14d
0x180003dd2  lea     rcx, [rax+rax*4]
0x180003dd6  mov     rax, [rsp+1D0h+var_188]
0x180003ddb  lea     rdx, [rsi+rcx*4]
0x180003ddf  mov     ecx, [r15+rax]
0x180003de3  mov     [rdx], ecx
0x180003de5  mov     rax, [rsp+1D0h+var_180]
0x180003dea  movups  xmm0, xmmword ptr [rax+60h]
0x180003dee  movups  xmmword ptr [rdx+4], xmm0
0x180003df2  mov     rcx, [rsp+1D0h+var_180]
0x180003df7  call    cs:__imp_SamFreeMemory
0x180003dfd  mov     rcx, [rsp+1D0h+var_178]
0x180003e02  xor     r15d, r15d
0x180003e05  mov     [rsp+1D0h+var_180], r15
0x180003e0a  call    cs:__imp_SamCloseHandle
0x180003e10  mov     [rsp+1D0h+var_178], r15
0x180003e15  inc     ebx
0x180003e17  jmp     loc_180003D0A
0x180003e1c  lea     rbx, WPP_GLOBAL_Control
0x180003e23  test    r14d, r14d
0x180003e26  jz      loc_18000409C
0x180003e2c  mov     [r12], rsi
0x180003e30  mov     rsi, r15
0x180003e33  mov     [r13+0], r14d
0x180003e37  mov     [rsp+1D0h+var_190], r15d
0x180003e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e43  mov     rax, [rsp+1D0h+var_188]
0x180003e48  test    rax, rax
0x180003e4b  jz      short loc_180003E5D
0x180003e4d  mov     rcx, rax
0x180003e50  call    cs:__imp_SamFreeMemory
0x180003e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e5d  test    rsi, rsi
0x180003e60  jnz     loc_1800040AD
0x180003e66  mov     rax, [rsp+1D0h+var_180]
0x180003e6b  test    rax, rax
0x180003e6e  jnz     loc_1800040C2
0x180003e74  mov     rax, [rsp+1D0h+var_178]
0x180003e79  test    rax, rax
0x180003e7c  jnz     loc_1800040D7
0x180003e82  test    edi, edi
0x180003e84  js      loc_180003F1D
0x180003e8a  cmp     rcx, rbx
0x180003e8d  jz      short loc_180003EAB
0x180003e8f  test    byte ptr [rcx+1Ch], 10h
0x180003e93  jnz     loc_1800040EC
0x180003e99  cmp     rcx, rbx
0x180003e9c  jz      short loc_180003EAB
0x180003e9e  test    dword ptr [rcx+1Ch], 400h
0x180003ea5  jnz     loc_18000410A
0x180003eab  mov     eax, edi
0x180003ead  mov     rcx, [rbp+0D0h+var_40]
0x180003eb4  xor     rcx, rsp; StackCookie
0x180003eb7  call    __security_check_cookie
0x180003ebc  mov     rbx, [rsp+1D0h+arg_18]
0x180003ec4  add     rsp, 1A0h
0x180003ecb  pop     r15
0x180003ecd  pop     r14
0x180003ecf  pop     r13
0x180003ed1  pop     r12
0x180003ed3  pop     rdi
0x180003ed4  pop     rsi
0x180003ed5  pop     rbp
0x180003ed6  retn
0x180003ed7  mov     edi, 80070216h
0x180003edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ee3  lea     rbx, WPP_GLOBAL_Control
0x180003eea  cmp     rcx, rbx
0x180003eed  jz      loc_180003E43
0x180003ef3  test    byte ptr [rcx+1Ch], 4
0x180003ef7  jz      loc_180003E43
0x180003efd  mov     edx, 63h ; 'c'
0x180003f02  mov     r9d, 80070216h
0x180003f08  mov     rcx, [rcx+10h]
0x180003f0c  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180003f13  call    WPP_SF_d
0x180003f18  jmp     loc_180003E3C
0x180003f1d  mov     [r12], r15
0x180003f21  mov     [r13+0], r15d
0x180003f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f2c  cmp     rcx, rbx
0x180003f2f  jz      loc_180003EAB
0x180003f35  test    byte ptr [rcx+1Ch], 4
0x180003f39  jz      loc_180003E99
0x180003f3f  mov     rcx, [rcx+10h]
0x180003f43  lea     r9, aCconnecteduser_9; "CConnectedUserStore::EnumConnectedUsers"...
0x180003f4a  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180003f4e  call    WPP_SF_sL
0x180003f53  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f5a  jmp     loc_180003E99
0x180003f5f  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180003f67  lea     rbx, WPP_GLOBAL_Control
0x180003f6e  mov     [r13+0], r15d
0x180003f72  mov     edi, r15d
0x180003f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f7c  jmp     loc_180003E43
0x180003f81  bts     edi, 1Ch
0x180003f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f8c  lea     rbx, WPP_GLOBAL_Control
0x180003f93  cmp     rcx, rbx
0x180003f96  jz      loc_180003E43
0x180003f9c  test    byte ptr [rcx+1Ch], 4
0x180003fa0  jz      loc_180003E43
0x180003fa6  mov     edx, 62h ; 'b'
0x180003fab  mov     r9d, edi
0x180003fae  jmp     loc_180003F08
0x180003fb3  mov     rcx, [rcx+10h]
0x180003fb7  lea     r9, aCconnecteduser_9; "CConnectedUserStore::EnumConnectedUsers"...
0x180003fbe  mov     edx, 0Ah
0x180003fc3  call    WPP_SF_s
0x180003fc8  jmp     loc_180003C77
0x180003fcd  mov     edi, 8007000Eh
0x180003fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd9  lea     rbx, WPP_GLOBAL_Control
0x180003fe0  cmp     rcx, rbx
0x180003fe3  jz      loc_180003E43
0x180003fe9  test    byte ptr [rcx+1Ch], 4
0x180003fed  jz      loc_180003E43
0x180003ff3  mov     edx, 64h ; 'd'
0x180003ff8  mov     r9d, 8007000Eh
0x180003ffe  jmp     loc_180003F08
0x180004003  mov     edi, eax
0x180004005  bts     edi, 1Ch
0x180004009  mov     rcx, cs:WPP_GLOBAL_Control
0x180004010  lea     rax, WPP_GLOBAL_Control
0x180004017  cmp     rcx, rax
0x18000401a  jz      short loc_180004044
0x18000401c  test    byte ptr [rcx+1Ch], 8
0x180004020  jz      short loc_180004044
0x180004022  mov     r9, [rsp+1D0h+var_188]
0x180004027  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000402e  mov     rcx, [rcx+10h]
0x180004032  mov     edx, 65h ; 'e'
0x180004037  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x18000403b  mov     r9d, [r15+r9]
0x18000403f  call    WPP_SF_DD
0x180004044  xor     r15d, r15d
0x180004047  jmp     loc_180003E15
0x18000404c  mov     edi, eax
0x18000404e  bts     edi, 1Ch
0x180004052  mov     rcx, cs:WPP_GLOBAL_Control
0x180004059  lea     rbx, WPP_GLOBAL_Control
0x180004060  cmp     rcx, rbx
0x180004063  jz      short loc_180004094
0x180004065  test    byte ptr [rcx+1Ch], 4
0x180004069  jz      short loc_180004094
0x18000406b  mov     r9, [rsp+1D0h+var_188]
0x180004070  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180004077  mov     rcx, [rcx+10h]
0x18000407b  mov     edx, 66h ; 'f'
0x180004080  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180004084  mov     r9d, [r15+r9]
0x180004088  call    WPP_SF_DD
0x18000408d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004094  xor     r15d, r15d
0x180004097  jmp     loc_180003E43
0x18000409c  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x1800040a4  mov     [r13+0], r15d
0x1800040a8  jmp     loc_180003E3C
0x1800040ad  mov     rcx, rsi; pv
0x1800040b0  call    cs:__imp_CoTaskMemFree
0x1800040b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040bd  jmp     loc_180003E66
0x1800040c2  mov     rcx, rax
0x1800040c5  call    cs:__imp_SamFreeMemory
0x1800040cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040d2  jmp     loc_180003E74
0x1800040d7  mov     rcx, rax
0x1800040da  call    cs:__imp_SamCloseHandle
0x1800040e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040e7  jmp     loc_180003E82
0x1800040ec  mov     r9d, [r13+0]
0x1800040f0  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800040f7  mov     rcx, [rcx+10h]
0x1800040fb  mov     edx, 68h ; 'h'
0x180004100  call    WPP_SF_d
0x180004105  jmp     loc_180003F53
0x18000410a  mov     rcx, [rcx+10h]
0x18000410e  lea     r9, aCconnecteduser_9; "CConnectedUserStore::EnumConnectedUsers"...
0x180004115  mov     edx, 0Ch
0x18000411a  call    WPP_SF_s
0x18000411f  jmp     loc_180003EAB
```
