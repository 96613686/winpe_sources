# CConnectedUserStore::InitializeDomainInfo(void)

- ea: `0x18000b890`
- end: `0x18000bc04`
- name: `?InitializeDomainInfo@CConnectedUserStore@@AEAAJXZ`
- size: `884`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000412c`

## callees

- `0x18000b890`
- `0x18000bc10`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba16`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b99e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b99e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b9c4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b9c4`
- `ntdll!RtlDuplicateUnicodeString` at `0x18000b969`
- `ntdll!RtlDuplicateUnicodeString` at `0x18000b969`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000b923`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000b923`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000b948`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000b948`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000ba52`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000ba52`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000ba6f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000ba6f`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::InitializeDomainInfo(CConnectedUserStore *this, __int64 a2, __int64 a3)
{
  CIdentityProfileHandler *v4; // rcx
  NTSTATUS v5; // eax
  int v6; // edx
  __int64 v7; // r8
  unsigned int v8; // esi
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  void *v11; // rbx
  DWORD LengthSid; // r14d
  void *v13; // rax
  void *v14; // rbp
  int v15; // ebx
  CIdentityProfileHandler *v16; // rcx
  signed int LastError; // eax
  __int64 v19; // rdx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-58h] BYREF
  PVOID DomainInfo; // [rsp+90h] [rbp+8h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+10h] BYREF

  PolicyHandle = 0;
  DomainInfo = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::InitializeDomainInfo");
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v8 = 0;
    if ( v4 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 84, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 2147549183LL);
    v15 = -2147418113;
    goto LABEL_17;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  v8 = v5;
  if ( v5 < 0 )
  {
    v15 = v5 | 0x10000000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_21;
    }
    v19 = 85;
LABEL_45:
    WPP_SF_d(*((_QWORD *)v16 + 2), v19, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, (unsigned int)v15);
    v16 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  v9 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  v8 = v9;
  if ( v9 < 0 )
  {
    v15 = v9 | 0x10000000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_21;
    }
    v19 = 86;
    goto LABEL_45;
  }
  v10 = RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)DomainInfo, (PUNICODE_STRING)((char *)this + 72));
  v8 = v10;
  if ( v10 >= 0 )
  {
    v11 = (void *)*((_QWORD *)DomainInfo + 2);
    if ( v11 )
    {
      LengthSid = GetLengthSid(*((PSID *)DomainInfo + 2));
      v13 = CoTaskMemAlloc(LengthSid);
      v14 = v13;
      if ( v13 )
      {
        if ( !CopySid(LengthSid, v13, v11) )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_13;
        }
        v15 = 0;
        *((_QWORD *)this + 11) = v14;
      }
      else
      {
        v15 = -2147024882;
      }
    }
    else
    {
      v15 = -2147467261;
    }
    CoTaskMemFree(0);
LABEL_13:
    if ( v15 >= 0 )
    {
LABEL_14:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
        (unsigned int)v15);
    }
LABEL_17:
    CConnectedUserStore::FreeDomainInfo(this);
    goto LABEL_14;
  }
  v15 = v10 | 0x10000000;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v19 = 87;
    goto LABEL_45;
  }
LABEL_21:
  if ( v15 < 0 )
    goto LABEL_17;
LABEL_22:
  if ( PolicyHandle )
  {
    LsaLookupClose(PolicyHandle);
    v16 = WPP_GLOBAL_Control;
  }
  if ( DomainInfo )
  {
    LsaLookupFreeMemory(DomainInfo);
    v16 = WPP_GLOBAL_Control;
  }
  if ( v15 < 0 )
  {
    if ( v16 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v16 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v16 + 2), v6, v7, (unsigned int)"CConnectedUserStore::InitializeDomainInfo", v15);
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( v16 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v16 + 2), 12, v7, "CConnectedUserStore::InitializeDomainInfo");
  return v8;
}

```

## disassembly

```asm
0x18000b890  mov     rax, rsp
0x18000b893  push    rbx
0x18000b894  push    r12
0x18000b896  sub     rsp, 78h
0x18000b89a  xorps   xmm0, xmm0
0x18000b89d  mov     [rax-18h], rdi
0x18000b8a1  mov     [rax-28h], r15
0x18000b8a5  mov     rdi, rcx
0x18000b8a8  xor     r15d, r15d
0x18000b8ab  mov     [rax+10h], r15
0x18000b8af  mov     [rax+8], r15
0x18000b8b3  movups  xmmword ptr [rax-58h], xmm0
0x18000b8b7  movups  xmmword ptr [rax-48h], xmm0
0x18000b8bb  movups  xmmword ptr [rax-38h], xmm0
0x18000b8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8c6  lea     r12, WPP_GLOBAL_Control
0x18000b8cd  cmp     rcx, r12
0x18000b8d0  jz      short loc_18000B8DF
0x18000b8d2  test    dword ptr [rcx+1Ch], 400h
0x18000b8d9  jnz     loc_18000BAF6
0x18000b8df  mov     [rsp+88h+arg_18], rsi
0x18000b8e7  cmp     [rdi+58h], r15
0x18000b8eb  jnz     loc_18000B9FB
0x18000b8f1  xorps   xmm0, xmm0
0x18000b8f4  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x18000b8fc  lea     r8, [rsp+88h+PolicyHandle]; PolicyHandle
0x18000b904  mov     [rsp+88h+ObjectAttributes.RootDirectory], r15
0x18000b909  mov     edx, 1; AccessMask
0x18000b90e  mov     [rsp+88h+ObjectAttributes.Attributes], r15d
0x18000b913  lea     rcx, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x18000b918  mov     [rsp+88h+ObjectAttributes.ObjectName], r15
0x18000b91d  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b923  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000b929  mov     esi, eax
0x18000b92b  test    eax, eax
0x18000b92d  js      loc_18000BB17
0x18000b933  mov     rcx, [rsp+88h+PolicyHandle]; PolicyHandle
0x18000b93b  lea     r8, [rsp+88h+DomainInfo]; DomainInfo
0x18000b943  mov     edx, 5; DomainInfoClass
0x18000b948  call    cs:__imp_LsaLookupGetDomainInfo
0x18000b94e  mov     esi, eax
0x18000b950  test    eax, eax
0x18000b952  js      loc_18000BB3E
0x18000b958  mov     rdx, [rsp+88h+DomainInfo]; SourceString
0x18000b960  lea     r8, [rdi+48h]; DestinationString
0x18000b964  mov     ecx, 1; Flags
0x18000b969  call    cs:__imp_RtlDuplicateUnicodeString
0x18000b96f  mov     esi, eax
0x18000b971  test    eax, eax
0x18000b973  js      loc_18000BB65
0x18000b979  mov     rax, [rsp+88h+DomainInfo]
0x18000b981  mov     [rsp+88h+arg_10], rbp
0x18000b989  mov     [rsp+88h+var_20], r14
0x18000b98e  mov     rbx, [rax+10h]
0x18000b992  test    rbx, rbx
0x18000b995  jz      loc_18000BA2D
0x18000b99b  mov     rcx, rbx; pSid
0x18000b99e  call    cs:__imp_GetLengthSid
0x18000b9a4  mov     ecx, eax; cb
0x18000b9a6  mov     r14d, eax
0x18000b9a9  call    cs:__imp_CoTaskMemAlloc
0x18000b9af  mov     rbp, rax
0x18000b9b2  test    rax, rax
0x18000b9b5  jz      loc_18000BBA9
0x18000b9bb  mov     r8, rbx; pSourceSid
0x18000b9be  mov     rdx, rax; pDestinationSid
0x18000b9c1  mov     ecx, r14d; nDestinationSidLength
0x18000b9c4  call    cs:__imp_CopySid
0x18000b9ca  test    eax, eax
0x18000b9cc  jz      short loc_18000BA16
0x18000b9ce  mov     ebx, r15d
0x18000b9d1  mov     [rdi+58h], rbp
0x18000b9d5  xor     ecx, ecx; pv
0x18000b9d7  call    cs:__imp_CoTaskMemFree
0x18000b9dd  mov     r14, [rsp+88h+var_20]
0x18000b9e2  mov     rbp, [rsp+88h+arg_10]
0x18000b9ea  test    ebx, ebx
0x18000b9ec  js      loc_18000BBB3
0x18000b9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9f9  jmp     short loc_18000BA38
0x18000b9fb  mov     esi, r15d
0x18000b9fe  cmp     rcx, r12
0x18000ba01  jnz     loc_18000BACC
0x18000ba07  mov     ebx, 8000FFFFh
0x18000ba0c  mov     rcx, rdi; this
0x18000ba0f  call    ?FreeDomainInfo@CConnectedUserStore@@AEAAXXZ; CConnectedUserStore::FreeDomainInfo(void)
0x18000ba14  jmp     short loc_18000B9F2
0x18000ba16  call    cs:__imp_GetLastError
0x18000ba1c  mov     ebx, eax
0x18000ba1e  test    eax, eax
0x18000ba20  jle     short loc_18000B9DD
0x18000ba22  movzx   ebx, ax
0x18000ba25  or      ebx, 80070000h
0x18000ba2b  jmp     short loc_18000B9DD
0x18000ba2d  mov     ebx, 80004003h
0x18000ba32  jmp     short loc_18000B9D5
0x18000ba34  test    ebx, ebx
0x18000ba36  js      short loc_18000BA0C
0x18000ba38  mov     rax, [rsp+88h+PolicyHandle]
0x18000ba40  mov     r15, [rsp+88h+var_28]
0x18000ba45  mov     rdi, [rsp+88h+var_18]
0x18000ba4a  test    rax, rax
0x18000ba4d  jz      short loc_18000BA5F
0x18000ba4f  mov     rcx, rax; ObjectHandle
0x18000ba52  call    cs:__imp_LsaLookupClose
0x18000ba58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba5f  mov     rax, [rsp+88h+DomainInfo]
0x18000ba67  test    rax, rax
0x18000ba6a  jz      short loc_18000BA7C
0x18000ba6c  mov     rcx, rax; Buffer
0x18000ba6f  call    cs:__imp_LsaLookupFreeMemory
0x18000ba75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba7c  test    ebx, ebx
0x18000ba7e  js      short loc_18000BAA4
0x18000ba80  cmp     rcx, r12
0x18000ba83  jz      short loc_18000BA92
0x18000ba85  test    dword ptr [rcx+1Ch], 400h
0x18000ba8c  jnz     loc_18000BBEA
0x18000ba92  mov     eax, esi
0x18000ba94  mov     rsi, [rsp+88h+arg_18]
0x18000ba9c  add     rsp, 78h
0x18000baa0  pop     r12
0x18000baa2  pop     rbx
0x18000baa3  retn
0x18000baa4  cmp     rcx, r12
0x18000baa7  jz      short loc_18000BA92
0x18000baa9  test    byte ptr [rcx+1Ch], 4
0x18000baad  jz      short loc_18000BA80
0x18000baaf  mov     rcx, [rcx+10h]
0x18000bab3  lea     r9, aCconnecteduser_22; "CConnectedUserStore::InitializeDomainIn"...
0x18000baba  mov     [rsp+88h+var_68], ebx
0x18000babe  call    WPP_SF_sL
0x18000bac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000baca  jmp     short loc_18000BA80
0x18000bacc  test    byte ptr [rcx+1Ch], 4
0x18000bad0  jz      loc_18000BA07
0x18000bad6  mov     rcx, [rcx+10h]
0x18000bada  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000bae1  mov     edx, 54h ; 'T'
0x18000bae6  mov     r9d, 8000FFFFh
0x18000baec  call    WPP_SF_d
0x18000baf1  jmp     loc_18000BA07
0x18000baf6  mov     rcx, [rcx+10h]
0x18000bafa  lea     r9, aCconnecteduser_22; "CConnectedUserStore::InitializeDomainIn"...
0x18000bb01  mov     edx, 0Ah
0x18000bb06  call    WPP_SF_s
0x18000bb0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb12  jmp     loc_18000B8DF
0x18000bb17  mov     ebx, eax
0x18000bb19  bts     ebx, 1Ch
0x18000bb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb24  cmp     rcx, r12
0x18000bb27  jz      loc_18000BA34
0x18000bb2d  test    byte ptr [rcx+1Ch], 4
0x18000bb31  jz      loc_18000BA34
0x18000bb37  mov     edx, 55h ; 'U'
0x18000bb3c  jmp     short loc_18000BB8A
0x18000bb3e  mov     ebx, eax
0x18000bb40  bts     ebx, 1Ch
0x18000bb44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb4b  cmp     rcx, r12
0x18000bb4e  jz      loc_18000BA34
0x18000bb54  test    byte ptr [rcx+1Ch], 4
0x18000bb58  jz      loc_18000BA34
0x18000bb5e  mov     edx, 56h ; 'V'
0x18000bb63  jmp     short loc_18000BB8A
0x18000bb65  mov     ebx, eax
0x18000bb67  bts     ebx, 1Ch
0x18000bb6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb72  cmp     rcx, r12
0x18000bb75  jz      loc_18000BA34
0x18000bb7b  test    byte ptr [rcx+1Ch], 4
0x18000bb7f  jz      loc_18000BA34
0x18000bb85  mov     edx, 57h ; 'W'
0x18000bb8a  mov     rcx, [rcx+10h]
0x18000bb8e  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000bb95  mov     r9d, ebx
0x18000bb98  call    WPP_SF_d
0x18000bb9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bba4  jmp     loc_18000BA34
0x18000bba9  mov     ebx, 8007000Eh
0x18000bbae  jmp     loc_18000B9D5
0x18000bbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbba  cmp     rcx, r12
0x18000bbbd  jz      loc_18000BA0C
0x18000bbc3  test    byte ptr [rcx+1Ch], 4
0x18000bbc7  jz      loc_18000BA0C
0x18000bbcd  mov     rcx, [rcx+10h]
0x18000bbd1  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000bbd8  mov     edx, 58h ; 'X'
0x18000bbdd  mov     r9d, ebx
0x18000bbe0  call    WPP_SF_d
0x18000bbe5  jmp     loc_18000BA0C
0x18000bbea  mov     rcx, [rcx+10h]
0x18000bbee  lea     r9, aCconnecteduser_22; "CConnectedUserStore::InitializeDomainIn"...
0x18000bbf5  mov     edx, 0Ch
0x18000bbfa  call    WPP_SF_s
0x18000bbff  jmp     loc_18000BA92
```
