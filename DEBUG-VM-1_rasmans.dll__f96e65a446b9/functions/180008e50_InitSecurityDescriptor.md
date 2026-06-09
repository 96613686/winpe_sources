# InitSecurityDescriptor

- ea: `0x180008e50`
- end: `0x180009248`
- name: `InitSecurityDescriptor`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800074c8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180008e50`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008f93`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008f93`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180009156`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180009156`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180009059`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180009059`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180009195`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180009195`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180008f84`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180008f84`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180008eb7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180008eb7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800090af`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800090af`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180008f29`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180008f29`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180008ffd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180008ffd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009107`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009107`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ec4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fa3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ec4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091f1`

## pseudocode

```c
__int64 InitSecurityDescriptor()
{
  DWORD SidLengthRequired; // eax
  HLOCAL v1; // rax
  void *v2; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ebx
  struct _ACL *v10; // rax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 213, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  SidLengthRequired = GetSidLengthRequired(1u);
  v1 = LocalAlloc(0x40u, SidLengthRequired);
  v2 = v1;
  if ( v1 )
  {
    if ( InitializeSid(v1, &pIdentifierAuthority, 1u) )
    {
      *GetSidSubAuthority(v2, 0) = 0;
      v9 = GetLengthSid(v2) + 20;
      v10 = (struct _ACL *)LocalAlloc(0x40u, v9);
      g_pDacl = v10;
      if ( v10 )
      {
        if ( InitializeAcl(v10, v9, 2u) )
        {
          if ( AddAccessAllowedAce(g_pDacl, 2u, 0x12FFFFu, v2) )
          {
            if ( InitializeSecurityDescriptor(RasmanSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorDacl(RasmanSecurityDescriptor, 1, g_pDacl, 0) )
              {
                if ( SetSecurityDescriptorOwner(RasmanSecurityDescriptor, 0, 0) )
                {
                  if ( SetSecurityDescriptorGroup(RasmanSecurityDescriptor, 0, 0) )
                  {
                    v4 = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v4 = LastError;
                    if ( LastError )
                    {
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                      {
                        v8 = 222;
                        goto LABEL_17;
                      }
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v4 = LastError;
                  if ( LastError )
                  {
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      v8 = 221;
                      goto LABEL_17;
                    }
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v4 = LastError;
                if ( LastError )
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    v8 = 220;
                    goto LABEL_17;
                  }
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v8 = 219;
                  goto LABEL_17;
                }
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError )
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v8 = 218;
                goto LABEL_17;
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v8 = 217;
              goto LABEL_17;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v8 = 216;
            goto LABEL_17;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v8 = 215;
LABEL_17:
          WPP_SF_d(v7[1].Flink, v8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
        }
      }
    }
    LocalFree(v2);
    if ( v4 )
      goto LABEL_62;
LABEL_65:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( !v3 )
    goto LABEL_65;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 214, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v3);
LABEL_62:
    v5 = WPP_GLOBAL_Control;
  }
  if ( g_pDacl )
  {
    LocalFree(g_pDacl);
    g_pDacl = 0;
    goto LABEL_65;
  }
LABEL_66:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 6u )
  {
    WPP_SF_d(v5[1].Flink, 223, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180008e50  push    rbx
0x180008e52  push    rbp
0x180008e53  push    rdi
0x180008e54  push    r14
0x180008e56  push    r15
0x180008e58  sub     rsp, 30h
0x180008e5c  mov     rax, cs:__security_cookie
0x180008e63  xor     rax, rsp
0x180008e66  mov     [rsp+58h+var_30], rax
0x180008e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e72  lea     r14, WPP_GLOBAL_Control
0x180008e79  lea     r15, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180008e80  mov     ebp, 2000h
0x180008e85  cmp     rcx, r14
0x180008e88  jz      short loc_180008EA6
0x180008e8a  test    [rcx+1Ch], ebp
0x180008e8d  jz      short loc_180008EA6
0x180008e8f  cmp     byte ptr [rcx+19h], 6
0x180008e93  jb      short loc_180008EA6
0x180008e95  mov     rcx, [rcx+10h]
0x180008e99  mov     edx, 0D5h
0x180008e9e  mov     r8, r15
0x180008ea1  call    WPP_SF_
0x180008ea6  mov     cl, 1; nSubAuthorityCount
0x180008ea8  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], 0
0x180008eb0  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 100h
0x180008eb7  call    cs:__imp_GetSidLengthRequired
0x180008ebd  mov     edx, eax; uBytes
0x180008ebf  mov     ecx, 40h ; '@'; uFlags
0x180008ec4  call    cs:__imp_LocalAlloc
0x180008eca  mov     rdi, rax
0x180008ecd  test    rax, rax
0x180008ed0  jnz     short loc_180008F1E
0x180008ed2  call    cs:__imp_GetLastError
0x180008ed8  mov     ebx, eax
0x180008eda  test    eax, eax
0x180008edc  jz      loc_180009202
0x180008ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee9  cmp     rcx, r14
0x180008eec  jz      loc_1800091E2
0x180008ef2  test    [rcx+1Ch], ebp
0x180008ef5  jz      loc_1800091E2
0x180008efb  cmp     byte ptr [rcx+19h], 2
0x180008eff  jb      loc_1800091E2
0x180008f05  mov     rcx, [rcx+10h]
0x180008f09  mov     edx, 0D6h
0x180008f0e  mov     r9d, eax
0x180008f11  mov     r8, r15
0x180008f14  call    WPP_SF_d
0x180008f19  jmp     loc_1800091DB
0x180008f1e  mov     r8b, 1; nSubAuthorityCount
0x180008f21  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x180008f26  mov     rcx, rdi; Sid
0x180008f29  call    cs:__imp_InitializeSid
0x180008f2f  test    eax, eax
0x180008f31  jnz     short loc_180008F7F
0x180008f33  call    cs:__imp_GetLastError
0x180008f39  mov     ebx, eax
0x180008f3b  test    eax, eax
0x180008f3d  jz      loc_1800091CE
0x180008f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f4a  cmp     rcx, r14
0x180008f4d  jz      loc_1800091CE
0x180008f53  test    [rcx+1Ch], ebp
0x180008f56  jz      loc_1800091CE
0x180008f5c  cmp     byte ptr [rcx+19h], 2
0x180008f60  jb      loc_1800091CE
0x180008f66  mov     edx, 0D7h
0x180008f6b  mov     rcx, [rcx+10h]
0x180008f6f  mov     r9d, eax
0x180008f72  mov     r8, r15
0x180008f75  call    WPP_SF_d
0x180008f7a  jmp     loc_1800091CE
0x180008f7f  xor     edx, edx; nSubAuthority
0x180008f81  mov     rcx, rdi; pSid
0x180008f84  call    cs:__imp_GetSidSubAuthority
0x180008f8a  mov     rcx, rdi; pSid
0x180008f8d  mov     dword ptr [rax], 0
0x180008f93  call    cs:__imp_GetLengthSid
0x180008f99  mov     ecx, 40h ; '@'; uFlags
0x180008f9e  lea     ebx, [rax+14h]
0x180008fa1  mov     edx, ebx; uBytes
0x180008fa3  call    cs:__imp_LocalAlloc
0x180008fa9  mov     cs:g_pDacl, rax
0x180008fb0  test    rax, rax
0x180008fb3  jnz     short loc_180008FF2
0x180008fb5  call    cs:__imp_GetLastError
0x180008fbb  mov     ebx, eax
0x180008fbd  test    eax, eax
0x180008fbf  jz      loc_1800091CE
0x180008fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fcc  cmp     rcx, r14
0x180008fcf  jz      loc_1800091CE
0x180008fd5  test    [rcx+1Ch], ebp
0x180008fd8  jz      loc_1800091CE
0x180008fde  cmp     byte ptr [rcx+19h], 2
0x180008fe2  jb      loc_1800091CE
0x180008fe8  mov     edx, 0D8h
0x180008fed  jmp     loc_180008F6B
0x180008ff2  mov     r8d, 2; dwAclRevision
0x180008ff8  mov     edx, ebx; nAclLength
0x180008ffa  mov     rcx, rax; pAcl
0x180008ffd  call    cs:__imp_InitializeAcl
0x180009003  test    eax, eax
0x180009005  jnz     short loc_180009044
0x180009007  call    cs:__imp_GetLastError
0x18000900d  mov     ebx, eax
0x18000900f  test    eax, eax
0x180009011  jz      loc_1800091CE
0x180009017  mov     rcx, cs:WPP_GLOBAL_Control
0x18000901e  cmp     rcx, r14
0x180009021  jz      loc_1800091CE
0x180009027  test    [rcx+1Ch], ebp
0x18000902a  jz      loc_1800091CE
0x180009030  cmp     byte ptr [rcx+19h], 2
0x180009034  jb      loc_1800091CE
0x18000903a  mov     edx, 0D9h
0x18000903f  jmp     loc_180008F6B
0x180009044  mov     rcx, cs:g_pDacl; pAcl
0x18000904b  mov     r9, rdi; pSid
0x18000904e  mov     edx, 2; dwAceRevision
0x180009053  mov     r8d, 12FFFFh; AccessMask
0x180009059  call    cs:__imp_AddAccessAllowedAce
0x18000905f  test    eax, eax
0x180009061  jnz     short loc_1800090A0
0x180009063  call    cs:__imp_GetLastError
0x180009069  mov     ebx, eax
0x18000906b  test    eax, eax
0x18000906d  jz      loc_1800091CE
0x180009073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000907a  cmp     rcx, r14
0x18000907d  jz      loc_1800091CE
0x180009083  test    [rcx+1Ch], ebp
0x180009086  jz      loc_1800091CE
0x18000908c  cmp     byte ptr [rcx+19h], 2
0x180009090  jb      loc_1800091CE
0x180009096  mov     edx, 0DAh
0x18000909b  jmp     loc_180008F6B
0x1800090a0  lea     rbx, RasmanSecurityDescriptor
0x1800090a7  mov     edx, 1; dwRevision
0x1800090ac  mov     rcx, rbx; pSecurityDescriptor
0x1800090af  call    cs:__imp_InitializeSecurityDescriptor
0x1800090b5  test    eax, eax
0x1800090b7  jnz     short loc_1800090F6
0x1800090b9  call    cs:__imp_GetLastError
0x1800090bf  mov     ebx, eax
0x1800090c1  test    eax, eax
0x1800090c3  jz      loc_1800091CE
0x1800090c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d0  cmp     rcx, r14
0x1800090d3  jz      loc_1800091CE
0x1800090d9  test    [rcx+1Ch], ebp
0x1800090dc  jz      loc_1800091CE
0x1800090e2  cmp     byte ptr [rcx+19h], 2
0x1800090e6  jb      loc_1800091CE
0x1800090ec  mov     edx, 0DBh
0x1800090f1  jmp     loc_180008F6B
0x1800090f6  mov     r8, cs:g_pDacl; pDacl
0x1800090fd  xor     r9d, r9d; bDaclDefaulted
0x180009100  mov     rcx, rbx; pSecurityDescriptor
0x180009103  lea     edx, [r9+1]; bDaclPresent
0x180009107  call    cs:__imp_SetSecurityDescriptorDacl
0x18000910d  test    eax, eax
0x18000910f  jnz     short loc_18000914E
0x180009111  call    cs:__imp_GetLastError
0x180009117  mov     ebx, eax
0x180009119  test    eax, eax
0x18000911b  jz      loc_1800091CE
0x180009121  mov     rcx, cs:WPP_GLOBAL_Control
0x180009128  cmp     rcx, r14
0x18000912b  jz      loc_1800091CE
0x180009131  test    [rcx+1Ch], ebp
0x180009134  jz      loc_1800091CE
0x18000913a  cmp     byte ptr [rcx+19h], 2
0x18000913e  jb      loc_1800091CE
0x180009144  mov     edx, 0DCh
0x180009149  jmp     loc_180008F6B
0x18000914e  xor     r8d, r8d; bOwnerDefaulted
0x180009151  xor     edx, edx; pOwner
0x180009153  mov     rcx, rbx; pSecurityDescriptor
0x180009156  call    cs:__imp_SetSecurityDescriptorOwner
0x18000915c  test    eax, eax
0x18000915e  jnz     short loc_18000918D
0x180009160  call    cs:__imp_GetLastError
0x180009166  mov     ebx, eax
0x180009168  test    eax, eax
0x18000916a  jz      short loc_1800091CE
0x18000916c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009173  cmp     rcx, r14
0x180009176  jz      short loc_1800091CE
0x180009178  test    [rcx+1Ch], ebp
0x18000917b  jz      short loc_1800091CE
0x18000917d  cmp     byte ptr [rcx+19h], 2
0x180009181  jb      short loc_1800091CE
0x180009183  mov     edx, 0DDh
0x180009188  jmp     loc_180008F6B
0x18000918d  xor     r8d, r8d; bGroupDefaulted
0x180009190  xor     edx, edx; pGroup
0x180009192  mov     rcx, rbx; pSecurityDescriptor
0x180009195  call    cs:__imp_SetSecurityDescriptorGroup
0x18000919b  test    eax, eax
0x18000919d  jnz     short loc_1800091CC
0x18000919f  call    cs:__imp_GetLastError
0x1800091a5  mov     ebx, eax
0x1800091a7  test    eax, eax
0x1800091a9  jz      short loc_1800091CE
0x1800091ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091b2  cmp     rcx, r14
0x1800091b5  jz      short loc_1800091CE
0x1800091b7  test    [rcx+1Ch], ebp
0x1800091ba  jz      short loc_1800091CE
0x1800091bc  cmp     byte ptr [rcx+19h], 2
0x1800091c0  jb      short loc_1800091CE
0x1800091c2  mov     edx, 0DEh
0x1800091c7  jmp     loc_180008F6B
0x1800091cc  xor     ebx, ebx
0x1800091ce  mov     rcx, rdi; hMem
0x1800091d1  call    cs:__imp_LocalFree
0x1800091d7  test    ebx, ebx
0x1800091d9  jz      short loc_180009202
0x1800091db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091e2  mov     rax, cs:g_pDacl
0x1800091e9  test    rax, rax
0x1800091ec  jz      short loc_180009209
0x1800091ee  mov     rcx, rax; hMem
0x1800091f1  call    cs:__imp_LocalFree
0x1800091f7  mov     cs:g_pDacl, 0
0x180009202  mov     rcx, cs:WPP_GLOBAL_Control
0x180009209  cmp     rcx, r14
0x18000920c  jz      short loc_18000922D
0x18000920e  test    [rcx+1Ch], ebp
0x180009211  jz      short loc_18000922D
0x180009213  cmp     byte ptr [rcx+19h], 6
0x180009217  jb      short loc_18000922D
0x180009219  mov     rcx, [rcx+10h]
0x18000921d  mov     edx, 0DFh
0x180009222  mov     r9d, ebx
0x180009225  mov     r8, r15
0x180009228  call    WPP_SF_d
0x18000922d  mov     eax, ebx
0x18000922f  mov     rcx, [rsp+58h+var_30]
0x180009234  xor     rcx, rsp; StackCookie
0x180009237  call    __security_check_cookie
0x18000923c  add     rsp, 30h
0x180009240  pop     r15
0x180009242  pop     r14
0x180009244  pop     rdi
0x180009245  pop     rbp
0x180009246  pop     rbx
0x180009247  retn
```
