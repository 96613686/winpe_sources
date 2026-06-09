# BfeNotifySinkCreate

- ea: `0x1800040f0`
- end: `0x180004743`
- name: `BfeNotifySinkCreate`
- size: `1619`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004aeb8`

## callees

- `0x1800040f0`
- `0x18000474c`
- `0x180004850`
- `0x1800048f8`
- `0x180004954`
- `0x18000e000`
- `0x18000f1a8`
- `0x18001236c`
- `0x180012950`
- `0x180012b54`
- `0x180018b74`
- `0x180037828`
- `0x18004e230`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004165`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004222`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004165`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004222`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800045ea`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000466e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000468c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800045ea`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000466e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000468c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000447d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000447d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000469e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000469e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d4`
- `RPCRT4!UuidCreate` at `0x180004330`
- `RPCRT4!UuidCreate` at `0x180004330`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800042b1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800042b1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000427e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000429b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000427e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000429b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041da`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041da`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041fb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000430f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000430f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000425e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000425e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800042ce`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800042ce`

## string_xrefs

- `0x1800044fd`: `UuidCreate`
- `0x1800045b3`: `CreateEventA`
- `0x1800042eb`: `AddAccessAllowedAce`
- `0x1800046b6`: `AddAccessAllowedAce`
- `0x1800046fd`: `CreateEventW`
- `0x18000472f`: `BfeNotifySinkCreate`
- `0x1800046a4`: `InitializeAcl`
- `0x1800046c8`: `InitializeSecurityDescriptor`
- `0x1800046da`: `SetSecurityDescriptorDacl`
- `0x1800046e6`: `WfpCreateSimpleSD`
- `0x180004711`: `WfpHashtableCreate`

## pseudocode

```c
__int64 __fastcall BfeNotifySinkCreate(PSID pSid, __int64 a2, _QWORD *a3)
{
  struct _ACL *v3; // r12
  char *v5; // rax
  __int64 v6; // rcx
  char *v7; // r15
  __int64 v8; // rbx
  DWORD LengthSid; // edi
  __int64 v10; // r14
  struct _ACL *v11; // rax
  __int64 v12; // rcx
  struct _ACL *v13; // rdi
  DWORD v14; // eax
  __int64 v15; // rcx
  const char *v16; // rdx
  int v17; // r8d
  HANDLE v18; // rax
  DWORD LastError; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  _QWORD *v22; // rax
  DWORD v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  struct _ACL *v28; // [rsp+78h] [rbp-90h] BYREF
  char *v29; // [rsp+80h] [rbp-88h] BYREF
  struct _ACL *v30; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v31; // [rsp+90h] [rbp-78h]
  PSID pSida; // [rsp+98h] [rbp-70h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+A0h] [rbp-68h] BYREF
  UUID Uuid; // [rsp+B8h] [rbp-50h] BYREF
  char v35[16]; // [rsp+C8h] [rbp-40h] BYREF
  const char *v36; // [rsp+D8h] [rbp-30h]
  __int64 v37; // [rsp+E0h] [rbp-28h]
  struct _ACL **v38; // [rsp+E8h] [rbp-20h]
  __int64 v39; // [rsp+F0h] [rbp-18h]

  v3 = 0;
  v31 = a3;
  v29 = 0;
  v30 = 0;
  memset(&EventAttributes, 0, 20);
  *a3 = 0;
  Uuid = 0;
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v7 = v29;
    v8 = WfpMemAlloc25B(0x110u);
  }
  else
  {
    v5 = (char *)HeapAlloc(gWfpHeap, 8u, 0x110u);
    v29 = v5;
    v7 = v5;
    if ( v5 )
    {
      v8 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v5));
    }
    else
    {
      v26 = WfpReportSysErrorAsNtStatus(v6, "HeapAlloc", 3221225495LL);
      v8 = v26;
      if ( v26 )
        WfpReportError(v26, "WfpMemAlloc");
    }
  }
  if ( !v8 )
  {
    v8 = WfpCriticalSectionCreate(v7);
    if ( !v8 )
    {
      *(_QWORD *)(v7 + 52) = 0x4000;
      *((_QWORD *)v7 + 9) = v7 + 64;
      *((_QWORD *)v7 + 8) = v7 + 64;
      *((_QWORD *)v7 + 10) = 0;
      pSida = 0;
      v28 = 0;
      LengthSid = GetLengthSid(pSid);
      v8 = WfpAllocAnyAppContainerSid(&pSida);
      if ( !v8 )
      {
        v10 = LengthSid + GetLengthSid(pSida) + 24;
        if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
        {
          v13 = v28;
          v8 = WfpMemAlloc25B(v10 + 40);
        }
        else
        {
          v11 = (struct _ACL *)HeapAlloc(gWfpHeap, 0, v10 + 40);
          v28 = v11;
          v13 = v11;
          if ( v11 )
          {
            v8 = 0;
            if ( gWfpTrackHeapBytes )
              _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v11));
          }
          else
          {
            v27 = WfpReportSysErrorAsNtStatus(v12, "HeapAlloc", 3221225495LL);
            v8 = v27;
            if ( v27 )
              WfpReportError(v27, "WfpMemAlloc");
          }
        }
        if ( !v8 )
        {
          if ( InitializeAcl(v13 + 5, v10, 2u) )
          {
            if ( AddAccessAllowedAce(v13 + 5, 2u, 0x100000u, pSid) && AddAccessAllowedAce(v13 + 5, 2u, 0x100000u, pSida) )
            {
              if ( InitializeSecurityDescriptor(v13, 1u) )
              {
                if ( SetSecurityDescriptorDacl(v13, 1, v13 + 5, 0) )
                {
                  v3 = v13;
                  v30 = v13;
LABEL_21:
                  if ( pSida )
                    FreeSid(pSida);
                  if ( v8 )
                  {
                    WfpReportError(v8, "WfpCreateSimpleSD");
                  }
                  else
                  {
                    EventAttributes.nLength = 24;
                    EventAttributes.lpSecurityDescriptor = v3;
                    EventAttributes.bInheritHandle = 0;
                    LODWORD(v8) = UuidCreate(&Uuid);
                    if ( (_DWORD)v8 )
                    {
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v17, 0, (__int64)"UuidCreate", v8);
                      }
                      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
                      {
                        LODWORD(v28) = v8;
                        v38 = &v28;
                        v36 = "UuidCreate";
                        v37 = 11;
                        v39 = 4;
                        McGenEventWrite_EtwEventWriteTransfer(
                          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
                          (unsigned int)WFP_USERMODE_ERROR,
                          v17,
                          3,
                          (__int64)v35);
                      }
                      if ( (int)v8 > 0 )
                        LODWORD(v8) = (unsigned __int16)v8 | 0x80070000;
                      v8 = (int)v8;
                    }
                    else
                    {
                      StringCchPrintfW(
                        (STRSAFE_LPWSTR)v7 + 68,
                        0x27u,
                        L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
                        Uuid.Data1,
                        Uuid.Data2,
                        Uuid.Data3,
                        Uuid.Data4[0],
                        Uuid.Data4[1],
                        Uuid.Data4[2],
                        Uuid.Data4[3],
                        Uuid.Data4[4],
                        Uuid.Data4[5],
                        Uuid.Data4[6],
                        Uuid.Data4[7]);
                      *(_OWORD *)(v7 + 88) = xmmword_1800B2DF0;
                      *(_OWORD *)(v7 + 104) = xmmword_1800B2E00;
                      *(_OWORD *)(v7 + 120) = xmmword_1800B2E10;
                      v18 = CreateEventW(&EventAttributes, 0, 0, (LPCWSTR)v7 + 44);
                      *((_QWORD *)v7 + 27) = v18;
                      if ( v18 )
                      {
                        LastError = GetLastError();
                        if ( LastError )
                        {
                          v8 = WfpReportSysErrorAsWinError(v20, "CreateEventW", LastError);
                        }
                        else
                        {
                          v21 = WfpHashtableCreateEx(v20, v7 + 224);
                          v8 = v21;
                          if ( v21 )
                          {
                            WfpReportError(v21, "WfpHashtableCreate");
                          }
                          else
                          {
                            v22 = v31;
                            *((_DWORD *)v7 + 66) = 1;
                            *v22 = v7;
                          }
                        }
                      }
                      else
                      {
                        v24 = GetLastError();
                        v8 = WfpReportSysErrorAsWinError(v25, "CreateEventA", v24);
                      }
                    }
                  }
                  goto LABEL_29;
                }
                v14 = GetLastError();
                v16 = "SetSecurityDescriptorDacl";
              }
              else
              {
                v14 = GetLastError();
                v16 = "InitializeSecurityDescriptor";
              }
            }
            else
            {
              v14 = GetLastError();
              v16 = "AddAccessAllowedAce";
            }
          }
          else
          {
            v14 = GetLastError();
            v16 = "InitializeAcl";
          }
          v8 = WfpReportSysErrorAsWinError(v15, v16, v14);
          if ( !v8 )
            goto LABEL_21;
        }
      }
      WfpMemFree(&v28);
      goto LABEL_21;
    }
  }
LABEL_29:
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    WfpMemFree25B(&v30);
  }
  else
  {
    if ( gWfpTrackHeapBytes && v3 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v3));
    HeapFree(gWfpHeap, 0, v3);
  }
  if ( v8 )
  {
    BfeNotifySinkDestroy(&v29);
    WfpReportError(v8, "BfeNotifySinkCreate");
  }
  return v8;
}

```

## disassembly

```asm
0x1800040f0  mov     r11, rsp
0x1800040f3  push    rbp
0x1800040f4  push    rbx
0x1800040f5  lea     rbp, [r11-38h]
0x1800040f9  sub     rsp, 128h
0x180004100  mov     rax, cs:__security_cookie
0x180004107  xor     rax, rsp
0x18000410a  mov     [rbp+30h+var_40], rax
0x18000410e  mov     [r11+10h], rsi
0x180004112  xorps   xmm0, xmm0
0x180004115  xor     esi, esi
0x180004117  mov     [r11-20h], r12
0x18000411b  mov     [r11-28h], r13
0x18000411f  mov     r12d, esi
0x180004122  mov     r13, rcx
0x180004125  mov     [r11-38h], r15
0x180004129  xor     ecx, ecx
0x18000412b  mov     [rbp+30h+var_A8], r8
0x18000412f  mov     [rbp+30h+EventAttributes.bInheritHandle], ecx
0x180004132  mov     [rsp+130h+var_B8], rsi
0x180004137  mov     [rbp+30h+var_B0], rsi
0x18000413b  movups  xmmword ptr [rbp+30h+EventAttributes.nLength], xmm0
0x18000413f  mov     [r8], rsi
0x180004142  movups  xmmword ptr [rbp+30h+Uuid.Data1], xmm0
0x180004146  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000414b  mov     edx, 8; dwFlags
0x180004150  test    eax, eax
0x180004152  jnz     loc_1800044B8
0x180004158  mov     rcx, cs:gWfpHeap; hHeap
0x18000415f  mov     r8d, 110h; dwBytes
0x180004165  call    cs:__imp_HeapAlloc
0x18000416b  mov     [rsp+130h+var_B8], rax
0x180004170  mov     r15, rax
0x180004173  test    rax, rax
0x180004176  jz      loc_1800045FE
0x18000417c  cmp     cs:gWfpTrackHeapBytes, esi
0x180004182  mov     ebx, esi
0x180004184  jnz     loc_180004662
0x18000418a  test    rbx, rbx
0x18000418d  jnz     loc_180004444
0x180004193  mov     rcx, r15
0x180004196  call    WfpCriticalSectionCreate
0x18000419b  mov     rbx, rax
0x18000419e  test    rax, rax
0x1800041a1  jnz     loc_180004444
0x1800041a7  mov     qword ptr [r15+34h], 4000h
0x1800041af  lea     rax, [r15+40h]
0x1800041b3  mov     [rax+8], rax
0x1800041b7  mov     rcx, r13; pSid
0x1800041ba  mov     [rax], rax
0x1800041bd  mov     [rsp+120h], rdi
0x1800041c5  mov     [r15+50h], rsi
0x1800041c9  mov     [rsp+130h+var_28], r14
0x1800041d1  mov     [rbp+30h+pSid], rsi
0x1800041d5  mov     [rsp+130h+var_C0], rsi
0x1800041da  call    cs:__imp_GetLengthSid
0x1800041e0  lea     rcx, [rbp+30h+pSid]; pSid
0x1800041e4  mov     edi, eax
0x1800041e6  call    WfpAllocAnyAppContainerSid
0x1800041eb  mov     rbx, rax
0x1800041ee  test    rax, rax
0x1800041f1  jnz     loc_180004528
0x1800041f7  mov     rcx, [rbp+30h+pSid]; pSid
0x1800041fb  call    cs:__imp_GetLengthSid
0x180004201  lea     r14d, [rax+18h]
0x180004205  add     r14d, edi
0x180004208  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000420d  xor     edx, edx; dwFlags
0x18000420f  test    eax, eax
0x180004211  jnz     loc_1800044D4
0x180004217  mov     rcx, cs:gWfpHeap; hHeap
0x18000421e  lea     r8, [r14+28h]; dwBytes
0x180004222  call    cs:__imp_HeapAlloc
0x180004228  mov     [rsp+130h+var_C0], rax
0x18000422d  mov     rdi, rax
0x180004230  test    rax, rax
0x180004233  jz      loc_180004630
0x180004239  cmp     cs:gWfpTrackHeapBytes, esi
0x18000423f  mov     rbx, rsi
0x180004242  jnz     loc_180004680
0x180004248  test    rbx, rbx
0x18000424b  jnz     loc_180004528
0x180004251  mov     r8d, 2; dwAclRevision
0x180004257  lea     rcx, [rdi+28h]; pAcl
0x18000425b  mov     edx, r14d; nAclLength
0x18000425e  call    cs:__imp_InitializeAcl
0x180004264  test    eax, eax
0x180004266  jz      loc_18000469E
0x18000426c  mov     r9, r13; pSid
0x18000426f  lea     rcx, [rdi+28h]; pAcl
0x180004273  mov     edx, 2; dwAceRevision
0x180004278  mov     r8d, 100000h; AccessMask
0x18000427e  call    cs:__imp_AddAccessAllowedAce
0x180004284  test    eax, eax
0x180004286  jz      short loc_1800042E5
0x180004288  mov     r9, [rbp+30h+pSid]; pSid
0x18000428c  lea     rcx, [rdi+28h]; pAcl
0x180004290  mov     edx, 2; dwAceRevision
0x180004295  mov     r8d, 100000h; AccessMask
0x18000429b  call    cs:__imp_AddAccessAllowedAce
0x1800042a1  test    eax, eax
0x1800042a3  jz      loc_1800046B0
0x1800042a9  mov     edx, 1; dwRevision
0x1800042ae  mov     rcx, rdi; pSecurityDescriptor
0x1800042b1  call    cs:__imp_InitializeSecurityDescriptor
0x1800042b7  test    eax, eax
0x1800042b9  jz      loc_1800046C2
0x1800042bf  xor     r9d, r9d; bDaclDefaulted
0x1800042c2  lea     r8, [rdi+28h]; pDacl
0x1800042c6  mov     edx, 1; bDaclPresent
0x1800042cb  mov     rcx, rdi; pSecurityDescriptor
0x1800042ce  call    cs:__imp_SetSecurityDescriptorDacl
0x1800042d4  test    eax, eax
0x1800042d6  jz      loc_1800046D4
0x1800042dc  mov     r12, rdi
0x1800042df  mov     [rbp+30h+var_B0], rdi
0x1800042e3  jmp     short loc_180004306
0x1800042e5  call    cs:__imp_GetLastError
0x1800042eb  lea     rdx, aAddaccessallow; "AddAccessAllowedAce"
0x1800042f2  mov     r8d, eax
0x1800042f5  call    WfpReportSysErrorAsWinError
0x1800042fa  mov     rbx, rax
0x1800042fd  test    rax, rax
0x180004300  jnz     loc_180004528
0x180004306  mov     rcx, [rbp+30h+pSid]; pSid
0x18000430a  test    rcx, rcx
0x18000430d  jz      short loc_180004315
0x18000430f  call    cs:__imp_FreeSid
0x180004315  test    rbx, rbx
0x180004318  jnz     loc_1800046E6
0x18000431e  lea     rcx, [rbp+30h+Uuid]; Uuid
0x180004322  mov     [rbp+30h+EventAttributes.nLength], 18h
0x180004329  mov     [rbp+30h+EventAttributes.lpSecurityDescriptor], r12
0x18000432d  mov     [rbp+30h+EventAttributes.bInheritHandle], esi
0x180004330  call    cs:__imp_UuidCreate
0x180004336  mov     ebx, eax
0x180004338  test    eax, eax
0x18000433a  jnz     loc_1800044EF
0x180004340  movzx   edx, [rbp+30h+Uuid.Data4+6]
0x180004344  lea     rcx, [r15+88h]; pszDest
0x18000434b  movzx   r8d, [rbp+30h+Uuid.Data4+5]
0x180004350  movzx   r9d, [rbp+30h+Uuid.Data4+4]
0x180004355  movzx   eax, [rbp+30h+Uuid.Data4+7]
0x180004359  movzx   r10d, [rbp+30h+Uuid.Data4+3]
0x18000435e  movzx   r11d, [rbp+30h+Uuid.Data4+2]
0x180004363  movzx   ebx, [rbp+30h+Uuid.Data4+1]
0x180004367  movzx   edi, [rbp+30h+Uuid.Data4]
0x18000436b  movzx   esi, [rbp+30h+Uuid.Data3]
0x18000436f  movzx   r14d, [rbp+30h+Uuid.Data2]
0x180004374  mov     dword ptr [rsp+130h+var_C8], eax
0x180004378  mov     [rsp+130h+var_D0], edx
0x18000437c  mov     edx, 27h ; '''; cchDest
0x180004381  mov     [rsp+130h+var_D8], r8d
0x180004386  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x18000438d  mov     [rsp+130h+var_E0], r9d
0x180004392  mov     r9d, [rbp+30h+Uuid.Data1]
0x180004396  mov     [rsp+130h+var_E8], r10d
0x18000439b  mov     [rsp+130h+var_F0], r11d
0x1800043a0  mov     [rsp+130h+var_F8], ebx
0x1800043a4  mov     [rsp+130h+var_100], edi
0x1800043a8  mov     [rsp+130h+var_108], esi
0x1800043ac  mov     [rsp+130h+var_110], r14d
0x1800043b1  call    StringCchPrintfW
0x1800043b6  movups  xmm0, cs:xmmword_1800B2DF0
0x1800043bd  lea     r9, [r15+58h]; lpName
0x1800043c1  xor     r8d, r8d; bInitialState
0x1800043c4  xor     edx, edx; bManualReset
0x1800043c6  lea     rcx, [rbp+30h+EventAttributes]; lpEventAttributes
0x1800043ca  movups  xmmword ptr [r9], xmm0
0x1800043ce  movups  xmm1, cs:xmmword_1800B2E00
0x1800043d5  movups  xmmword ptr [r9+10h], xmm1
0x1800043da  movups  xmm0, cs:xmmword_1800B2E10
0x1800043e1  movups  xmmword ptr [r9+20h], xmm0
0x1800043e6  call    cs:__imp_CreateEventW
0x1800043ec  mov     [r15+0D8h], rax
0x1800043f3  test    rax, rax
0x1800043f6  jz      loc_1800045AA
0x1800043fc  call    cs:__imp_GetLastError
0x180004402  test    eax, eax
0x180004404  jnz     loc_1800046FA
0x18000440a  lea     rdx, [r15+0E0h]
0x180004411  call    WfpHashtableCreateEx
0x180004416  mov     rbx, rax
0x180004419  test    rax, rax
0x18000441c  jnz     loc_180004711
0x180004422  mov     rax, [rbp+30h+var_A8]
0x180004426  mov     dword ptr [r15+108h], 1
0x180004431  mov     [rax], r15
0x180004434  mov     r14, [rsp+130h+var_28]
0x18000443c  mov     rdi, [rsp+120h]
0x180004444  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180004449  mov     r15, [rsp+130h+var_30]
0x180004451  mov     r13, [rsp+130h+var_20]
0x180004459  mov     rsi, [rsp+130h+arg_8]
0x180004461  test    eax, eax
0x180004463  jnz     short loc_1800044AD
0x180004465  cmp     cs:gWfpTrackHeapBytes, eax
0x18000446b  jnz     loc_1800045D5
0x180004471  mov     rcx, cs:gWfpHeap; hHeap
0x180004478  mov     r8, r12; lpMem
0x18000447b  xor     edx, edx; dwFlags
0x18000447d  call    cs:__imp_HeapFree
0x180004483  mov     r12, [rsp+130h+var_18]
0x18000448b  test    rbx, rbx
0x18000448e  jnz     loc_180004725
0x180004494  mov     rax, rbx
0x180004497  mov     rcx, [rbp+30h+var_40]
0x18000449b  xor     rcx, rsp; StackCookie
0x18000449e  call    __security_check_cookie
0x1800044a3  add     rsp, 128h
0x1800044aa  pop     rbx
0x1800044ab  pop     rbp
0x1800044ac  retn
0x1800044ad  lea     rcx, [rbp+30h+var_B0]
0x1800044b1  call    WfpMemFree25B
0x1800044b6  jmp     short loc_180004483
0x1800044b8  lea     r8, [rsp+130h+var_B8]
0x1800044bd  mov     ecx, 110h; dwBytes
0x1800044c2  call    WfpMemAlloc25B
0x1800044c7  mov     r15, [rsp+130h+var_B8]
0x1800044cc  mov     rbx, rax
0x1800044cf  jmp     loc_18000418A
0x1800044d4  lea     r8, [rsp+130h+var_C0]
0x1800044d9  lea     rcx, [r14+28h]; dwBytes
0x1800044dd  call    WfpMemAlloc25B
0x1800044e2  mov     rdi, [rsp+130h+var_C0]
0x1800044e7  mov     rbx, rax
0x1800044ea  jmp     loc_180004248
0x1800044ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f6  lea     rax, WPP_GLOBAL_Control
0x1800044fd  lea     rdi, aUuidcreate; "UuidCreate"
0x180004504  cmp     rcx, rax
0x180004507  jz      short loc_18000450F
0x180004509  cmp     byte ptr [rcx+19h], 2
0x18000450d  jnb     short loc_180004537
0x18000450f  cmp     dword ptr cs:1800EF078h, 0
0x180004516  jnz     short loc_180004559
0x180004518  test    ebx, ebx
0x18000451a  jg      loc_1800045C7
0x180004520  movsxd  rbx, ebx
0x180004523  jmp     loc_180004434
0x180004528  lea     rcx, [rsp+130h+var_C0]
0x18000452d  call    WfpMemFree
0x180004532  jmp     loc_180004306
0x180004537  test    byte ptr [rcx+1Ch], 1
0x18000453b  jz      short loc_18000450F
0x18000453d  mov     rcx, [rcx+10h]
0x180004541  mov     edx, 17h
0x180004546  mov     [rsp+130h+var_108], ebx
0x18000454a  xor     r9d, r9d
0x18000454d  mov     qword ptr [rsp+130h+var_110], rdi
0x180004552  call    WPP_SF_SsD
0x180004557  jmp     short loc_18000450F
0x180004559  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180004560  jz      short loc_180004518
0x180004562  lea     rax, [rsp+130h+var_C0]
0x180004567  mov     dword ptr [rsp+130h+var_C0], ebx
0x18000456b  mov     [rbp+30h+var_50], rax
0x18000456f  lea     rdx, WFP_USERMODE_ERROR
0x180004576  lea     rax, [rbp+30h+var_70]
0x18000457a  mov     [rbp+30h+var_60], rdi
0x18000457e  mov     r9d, 3
0x180004584  mov     qword ptr [rsp+130h+var_110], rax
0x180004589  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180004590  mov     [rbp+30h+var_58], 0Bh
0x180004598  mov     [rbp+30h+var_48], 4
0x1800045a0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800045a5  jmp     loc_180004518
0x1800045aa  call    cs:__imp_GetLastError
0x1800045b0  mov     r8d, eax
0x1800045b3  lea     rdx, aCreateeventa; "CreateEventA"
0x1800045ba  call    WfpReportSysErrorAsWinError
0x1800045bf  mov     rbx, rax
0x1800045c2  jmp     loc_180004434
0x1800045c7  movzx   ebx, bx
0x1800045ca  or      ebx, 80070000h
0x1800045d0  jmp     loc_180004520
0x1800045d5  test    r12, r12
0x1800045d8  jz      loc_180004471
0x1800045de  mov     rcx, cs:gWfpHeap; hHeap
0x1800045e5  mov     r8, r12; lpMem
0x1800045e8  xor     edx, edx; dwFlags
0x1800045ea  call    cs:__imp_HeapSize
0x1800045f0  neg     eax
0x1800045f2  lock add cs:gWfpHeapBytesAllocated, eax
0x1800045f9  jmp     loc_180004471
0x1800045fe  mov     r8d, 0C0000017h
0x180004604  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000460b  call    WfpReportSysErrorAsNtStatus
0x180004610  mov     rbx, rax
0x180004613  test    rax, rax
0x180004616  jz      loc_18000418A
0x18000461c  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180004623  mov     rcx, rax
0x180004626  call    WfpReportError
0x18000462b  jmp     loc_18000418A
0x180004630  mov     r8d, 0C0000017h
0x180004636  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000463d  call    WfpReportSysErrorAsNtStatus
0x180004642  mov     rbx, rax
  ... truncated ...
```
