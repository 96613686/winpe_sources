# NcbRegistrarpGetApplicationPackageSid

- ea: `0x1800043f0`
- end: `0x1800048e3`
- name: `NcbRegistrarpGetApplicationPackageSid`
- size: `1267`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c3f0`

## callees

- `0x180003ed0`
- `0x1800043f0`
- `0x1800050d0`
- `0x180009740`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000473a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000488b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000473a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000488b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800047fd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800047fd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004881`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004881`

## string_xrefs

- `0x180004619`: `NcbReg: Package sid information ended with`
- `0x1800046f1`: `NcbReg: Failed to query TokenAppContainerSid buffer length`
- `0x180004590`: `Failed to malloc token buffer\n`
- `0x180004791`: `NcbReg: Failed to query TokenAppContainerSid buffer`
- `0x1800047a9`: `NcbReg: NULL TokenAppContainerSid`
- `0x180004861`: `Failed to malloc package sid\n`

## pseudocode

```c
__int64 __fastcall NcbRegistrarpGetApplicationPackageSid(__int64 a1, void *a2)
{
  __int64 v4; // rdx
  PSID *v5; // rbx
  __int64 v6; // r8
  unsigned int v7; // esi
  PVOID *v8; // rcx
  DWORD LastError; // eax
  __int64 v11; // rdx
  DWORD v12; // eax
  __int64 v13; // rdx
  DWORD LengthSid; // edi
  void *v15; // rax
  __int64 v16; // rdx
  DWORD v17; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-78h] BYREF
  int v19; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v20[16]; // [rsp+40h] [rbp-68h] BYREF
  const wchar_t *v21; // [rsp+50h] [rbp-58h]
  __int64 v22; // [rsp+58h] [rbp-50h]
  int *v23; // [rsp+60h] [rbp-48h]
  __int64 v24; // [rsp+68h] [rbp-40h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  TokenInformationLength = 0;
  *(_QWORD *)(a1 + 256) = 0;
  if ( !GetTokenInformation(a2, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 122 )
    {
      v5 = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, LastError);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(v8, v11, L"NcbReg: Failed to query TokenAppContainerSid buffer length", v7);
LABEL_60:
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      goto LABEL_20;
    }
  }
  v5 = (PSID *)MALLOC(TokenInformationLength + 8LL);
  if ( v5 )
  {
    v7 = 0;
    if ( GetTokenInformation(a2, TokenAppContainerSid, v5, TokenInformationLength, &TokenInformationLength)
      || (v12 = GetLastError(), (v7 = v12) == 0) )
    {
      if ( *v5 )
      {
        LengthSid = GetLengthSid(*v5);
        v15 = (void *)MALLOC(LengthSid);
        *(_QWORD *)(a1 + 256) = v15;
        if ( v15 )
        {
          if ( CopySid(LengthSid, v15, *v5) )
          {
            *(_DWORD *)(a1 + 264) = LengthSid;
            goto LABEL_60;
          }
          v17 = GetLastError();
          v7 = v17;
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v17);
            goto LABEL_60;
          }
LABEL_20:
          if ( !v7 )
            goto LABEL_21;
          goto LABEL_9;
        }
        v7 = 8;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 8);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v8, v16, L"Failed to malloc package sid\n");
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        v7 = 1008;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 1008);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v19 = 1008;
          v21 = L"NcbReg: NULL TokenAppContainerSid";
          v22 = 68;
          v23 = &v19;
          v24 = 4;
          McGenEventWrite_EventWriteTransfer(v8, NcbApiStatus, v6, 3, v20);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v12);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(v8, v13, L"NcbReg: Failed to query TokenAppContainerSid buffer", v7);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v7 = 8;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 8);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v8, v4, L"Failed to malloc token buffer\n");
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_9:
  if ( *(_QWORD *)(a1 + 256) )
  {
    VpnFree(*(LPVOID *)(a1 + 256));
    *(_QWORD *)(a1 + 256) = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v5 )
  {
    VpnFree(v5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v19 = v7;
    v21 = L"NcbReg: Package sid information ended with";
    v22 = 86;
    v23 = &v19;
    v24 = 4;
    McGenEventWrite_EventWriteTransfer(v8, NcbApiStatus, v6, 3, v20);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 93, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800043f0  mov     r11, rsp
0x1800043f3  sub     rsp, 0A8h
0x1800043fa  mov     rax, cs:__security_cookie
0x180004401  xor     rax, rsp
0x180004404  mov     [rsp+0A8h+var_38], rax
0x180004409  mov     [r11+18h], rbx
0x18000440d  mov     [r11-8], rbp
0x180004411  mov     rbp, rcx
0x180004414  mov     [r11-18h], rdi
0x180004418  mov     rdi, rdx
0x18000441b  mov     [r11-20h], r14
0x18000441f  mov     [r11-28h], r15
0x180004423  mov     rcx, cs:WPP_GLOBAL_Control
0x18000442a  lea     r14, WPP_GLOBAL_Control
0x180004431  cmp     rcx, r14
0x180004434  jnz     loc_180004510
0x18000443a  xor     r15d, r15d
0x18000443d  mov     [rsp+0A8h+var_10], rsi
0x180004445  lea     rax, [rsp+0A8h+TokenInformationLength]
0x18000444a  mov     [rsp+0A8h+TokenInformationLength], r15d
0x18000444f  xor     r9d, r9d; TokenInformationLength
0x180004452  mov     [rbp+100h], r15
0x180004459  xor     r8d, r8d; TokenInformation
0x18000445c  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x180004461  mov     edx, 1Fh; TokenInformationClass
0x180004466  mov     rcx, rdi; TokenHandle
0x180004469  call    cs:__imp_GetTokenInformation
0x18000446f  test    eax, eax
0x180004471  jz      loc_180004696
0x180004477  mov     ecx, [rsp+0A8h+TokenInformationLength]
0x18000447b  add     rcx, 8; dwBytes
0x18000447f  call    MALLOC
0x180004484  mov     rbx, rax
0x180004487  test    rax, rax
0x18000448a  jz      loc_18000456E
0x180004490  mov     r9d, [rsp+0A8h+TokenInformationLength]; TokenInformationLength
0x180004495  lea     rax, [rsp+0A8h+TokenInformationLength]
0x18000449a  mov     r8, rbx; TokenInformation
0x18000449d  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x1800044a2  mov     edx, 1Fh; TokenInformationClass
0x1800044a7  mov     rcx, rdi; TokenHandle
0x1800044aa  mov     esi, r15d
0x1800044ad  call    cs:__imp_GetTokenInformation
0x1800044b3  test    eax, eax
0x1800044b5  jz      loc_18000473A
0x1800044bb  mov     rcx, [rbx]; pSid
0x1800044be  test    rcx, rcx
0x1800044c1  jnz     loc_1800047FD
0x1800044c7  mov     esi, 3F0h
0x1800044cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044d3  cmp     rcx, r14
0x1800044d6  jnz     short loc_18000453E
0x1800044d8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800044df  jnz     loc_1800047A9
0x1800044e5  mov     rax, [rbp+100h]
0x1800044ec  test    rax, rax
0x1800044ef  jz      loc_1800045B0
0x1800044f5  mov     rcx, rax; lpMem
0x1800044f8  call    VpnFree
0x1800044fd  mov     [rbp+100h], r15
0x180004504  mov     rcx, cs:WPP_GLOBAL_Control
0x18000450b  jmp     loc_1800045B0
0x180004510  test    byte ptr [rcx+1Ch], 1
0x180004514  jz      loc_18000443A
0x18000451a  cmp     byte ptr [rcx+19h], 6
0x18000451e  jb      loc_18000443A
0x180004524  mov     rcx, [rcx+10h]
0x180004528  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000452f  mov     edx, 56h ; 'V'
0x180004534  call    WPP_SF_
0x180004539  jmp     loc_18000443A
0x18000453e  test    byte ptr [rcx+1Ch], 1
0x180004542  jz      short loc_1800044D8
0x180004544  cmp     byte ptr [rcx+19h], 2
0x180004548  jb      short loc_1800044D8
0x18000454a  mov     rcx, [rcx+10h]
0x18000454e  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180004555  mov     edx, 5Ah ; 'Z'
0x18000455a  mov     r9d, esi
0x18000455d  call    WPP_SF_d
0x180004562  mov     rcx, cs:WPP_GLOBAL_Control
0x180004569  jmp     loc_1800044D8
0x18000456e  mov     esi, 8
0x180004573  mov     rcx, cs:WPP_GLOBAL_Control
0x18000457a  cmp     rcx, r14
0x18000457d  jnz     loc_180004702
0x180004583  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000458a  jz      loc_1800044E5
0x180004590  lea     r8, aFailedToMalloc_0; "Failed to malloc token buffer\n"
0x180004597  call    McTemplateU0z_EventWriteTransfer
0x18000459c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a3  jmp     loc_1800044E5
0x1800045a8  test    esi, esi
0x1800045aa  jnz     loc_1800044E5
0x1800045b0  mov     rdi, [rsp+0A8h+var_18]
0x1800045b8  mov     rbp, [rsp+0A8h+var_8]
0x1800045c0  test    rbx, rbx
0x1800045c3  jz      short loc_1800045D4
0x1800045c5  mov     rcx, rbx; lpMem
0x1800045c8  call    VpnFree
0x1800045cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045d4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800045db  mov     rbx, [rsp+0A8h+arg_10]
0x1800045e3  jnz     short loc_180004619
0x1800045e5  mov     r15, [rsp+0A8h+var_28]
0x1800045ed  cmp     rcx, r14
0x1800045f0  mov     r14, [rsp+0A8h+var_20]
0x1800045f8  jnz     short loc_18000466D
0x1800045fa  mov     eax, esi
0x1800045fc  mov     rsi, [rsp+0A8h+var_10]
0x180004604  mov     rcx, [rsp+0A8h+var_38]
0x180004609  xor     rcx, rsp; StackCookie
0x18000460c  call    __security_check_cookie
0x180004611  add     rsp, 0A8h
0x180004618  retn
0x180004619  lea     rax, aNcbregPackageS; "NcbReg: Package sid information ended w"...
0x180004620  mov     [rsp+0A8h+var_70], esi
0x180004624  mov     [rsp+0A8h+var_58], rax
0x180004629  lea     rdx, NcbApiStatus
0x180004630  lea     rax, [rsp+0A8h+var_70]
0x180004635  mov     [rsp+0A8h+var_50], 56h ; 'V'
0x18000463e  mov     [rsp+0A8h+var_48], rax
0x180004643  mov     r9d, 3
0x180004649  lea     rax, [rsp+0A8h+var_68]
0x18000464e  mov     [rsp+0A8h+var_40], 4
0x180004657  mov     [rsp+0A8h+ReturnLength], rax
0x18000465c  call    McGenEventWrite_EventWriteTransfer
0x180004661  mov     rcx, cs:WPP_GLOBAL_Control
0x180004668  jmp     loc_1800045E5
0x18000466d  test    byte ptr [rcx+1Ch], 1
0x180004671  jz      short loc_1800045FA
0x180004673  cmp     byte ptr [rcx+19h], 6
0x180004677  jb      short loc_1800045FA
0x180004679  mov     rcx, [rcx+10h]
0x18000467d  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180004684  mov     edx, 5Dh ; ']'
0x180004689  mov     r9d, esi
0x18000468c  call    WPP_SF_d
0x180004691  jmp     loc_1800045FA
0x180004696  call    cs:__imp_GetLastError
0x18000469c  mov     esi, eax
0x18000469e  cmp     eax, 7Ah ; 'z'
0x1800046a1  jz      loc_180004477
0x1800046a7  mov     rbx, r15
0x1800046aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046b1  cmp     rcx, r14
0x1800046b4  jz      short loc_1800046E1
0x1800046b6  test    byte ptr [rcx+1Ch], 1
0x1800046ba  jz      short loc_1800046E1
0x1800046bc  cmp     byte ptr [rcx+19h], 2
0x1800046c0  jb      short loc_1800046E1
0x1800046c2  mov     rcx, [rcx+10h]
0x1800046c6  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x1800046cd  mov     edx, 57h ; 'W'
0x1800046d2  mov     r9d, eax
0x1800046d5  call    WPP_SF_d
0x1800046da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046e1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800046e8  jz      loc_1800045A8
0x1800046ee  mov     r9d, esi
0x1800046f1  lea     r8, aNcbregFailedTo; "NcbReg: Failed to query TokenAppContain"...
0x1800046f8  call    McTemplateU0zq_EventWriteTransfer
0x1800046fd  jmp     loc_1800048D7
0x180004702  test    byte ptr [rcx+1Ch], 1
0x180004706  jz      loc_180004583
0x18000470c  cmp     byte ptr [rcx+19h], 2
0x180004710  jb      loc_180004583
0x180004716  mov     rcx, [rcx+10h]
0x18000471a  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180004721  mov     edx, 58h ; 'X'
0x180004726  mov     r9d, esi
0x180004729  call    WPP_SF_d
0x18000472e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004735  jmp     loc_180004583
0x18000473a  call    cs:__imp_GetLastError
0x180004740  mov     esi, eax
0x180004742  test    eax, eax
0x180004744  jz      loc_1800044BB
0x18000474a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004751  cmp     rcx, r14
0x180004754  jz      short loc_180004781
0x180004756  test    byte ptr [rcx+1Ch], 1
0x18000475a  jz      short loc_180004781
0x18000475c  cmp     byte ptr [rcx+19h], 2
0x180004760  jb      short loc_180004781
0x180004762  mov     rcx, [rcx+10h]
0x180004766  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000476d  mov     edx, 59h ; 'Y'
0x180004772  mov     r9d, eax
0x180004775  call    WPP_SF_d
0x18000477a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004781  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004788  jz      loc_1800044E5
0x18000478e  mov     r9d, esi
0x180004791  lea     r8, aNcbregFailedTo_0; "NcbReg: Failed to query TokenAppContain"...
0x180004798  call    McTemplateU0zq_EventWriteTransfer
0x18000479d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047a4  jmp     loc_1800044E5
0x1800047a9  lea     rax, aNcbregNullToke; "NcbReg: NULL TokenAppContainerSid"
0x1800047b0  mov     [rsp+0A8h+var_70], esi
0x1800047b4  mov     [rsp+0A8h+var_58], rax
0x1800047b9  lea     rdx, NcbApiStatus
0x1800047c0  lea     rax, [rsp+0A8h+var_70]
0x1800047c5  mov     [rsp+0A8h+var_50], 44h ; 'D'
0x1800047ce  mov     [rsp+0A8h+var_48], rax
0x1800047d3  mov     r9d, 3
0x1800047d9  lea     rax, [rsp+0A8h+var_68]
0x1800047de  mov     [rsp+0A8h+var_40], 4
0x1800047e7  mov     [rsp+0A8h+ReturnLength], rax
0x1800047ec  call    McGenEventWrite_EventWriteTransfer
0x1800047f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047f8  jmp     loc_1800044E5
0x1800047fd  call    cs:__imp_GetLengthSid
0x180004803  mov     ecx, eax; dwBytes
0x180004805  mov     edi, eax
0x180004807  call    MALLOC
0x18000480c  mov     [rbp+100h], rax
0x180004813  test    rax, rax
0x180004816  jnz     short loc_180004879
0x180004818  mov     esi, 8
0x18000481d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004824  cmp     rcx, r14
0x180004827  jz      short loc_180004854
0x180004829  test    byte ptr [rcx+1Ch], 1
0x18000482d  jz      short loc_180004854
0x18000482f  cmp     byte ptr [rcx+19h], 2
0x180004833  jb      short loc_180004854
0x180004835  mov     rcx, [rcx+10h]
0x180004839  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180004840  mov     edx, 5Bh ; '['
0x180004845  mov     r9d, esi
0x180004848  call    WPP_SF_d
0x18000484d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004854  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000485b  jz      loc_1800044E5
0x180004861  lea     r8, aFailedToMalloc_1; "Failed to malloc package sid\n"
0x180004868  call    McTemplateU0z_EventWriteTransfer
0x18000486d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004874  jmp     loc_1800044E5
0x180004879  mov     r8, [rbx]; pSourceSid
0x18000487c  mov     rdx, rax; pDestinationSid
0x18000487f  mov     ecx, edi; nDestinationSidLength
0x180004881  call    cs:__imp_CopySid
0x180004887  test    eax, eax
0x180004889  jnz     short loc_1800048D1
0x18000488b  call    cs:__imp_GetLastError
0x180004891  mov     esi, eax
0x180004893  mov     rcx, cs:WPP_GLOBAL_Control
0x18000489a  cmp     rcx, r14
0x18000489d  jz      loc_1800045A8
0x1800048a3  test    byte ptr [rcx+1Ch], 1
0x1800048a7  jz      loc_1800045A8
0x1800048ad  cmp     byte ptr [rcx+19h], 2
0x1800048b1  jb      loc_1800045A8
0x1800048b7  mov     rcx, [rcx+10h]
0x1800048bb  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x1800048c2  mov     edx, 5Ch ; '\'
0x1800048c7  mov     r9d, eax
0x1800048ca  call    WPP_SF_d
0x1800048cf  jmp     short loc_1800048D7
0x1800048d1  mov     [rbp+108h], edi
0x1800048d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048de  jmp     loc_1800045A8
```
