# BfeNotifySinkCreate

- ea: `0x1800040d0`
- end: `0x180004792`
- name: `BfeNotifySinkCreate`
- size: `1730`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cce8`

## callees

- `0x1800040d0`
- `0x180004798`
- `0x1800048a8`
- `0x180004950`
- `0x1800049b4`
- `0x18000e7e0`
- `0x18000fb34`
- `0x180012d8c`
- `0x1800133a0`
- `0x1800135ac`
- `0x1800197d0`
- `0x180035e40`
- `0x18004fb50`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000440a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000440a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004145`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004214`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004145`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004214`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180004627`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800046b1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800046d5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180004627`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800046b1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800046d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000471d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000471d`
- `RPCRT4!UuidCreate` at `0x18000434e`
- `RPCRT4!UuidCreate` at `0x18000434e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800042b7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800042b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000427c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000429f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000427c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000429f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041c0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041c0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800041e7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004327`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004327`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180004256`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180004256`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800042da`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800042da`

## string_xrefs

- `0x180004534`: `UuidCreate`
- `0x1800045f0`: `CreateEventA`
- `0x180004303`: `AddAccessAllowedAce`
- `0x18000474c`: `CreateEventW`
- `0x18000477e`: `BfeNotifySinkCreate`
- `0x1800046f9`: `InitializeAcl`
- `0x180004711`: `InitializeSecurityDescriptor`
- `0x180004729`: `SetSecurityDescriptorDacl`
- `0x180004735`: `WfpCreateSimpleSD`
- `0x180004760`: `WfpHashtableCreate`

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
                      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
                      *(_OWORD *)(v7 + 88) = xmmword_1800B5DC0;
                      *(_OWORD *)(v7 + 104) = xmmword_1800B5DD0;
                      *(_OWORD *)(v7 + 120) = xmmword_1800B5DE0;
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
0x1800040d0  mov     r11, rsp
0x1800040d3  push    rbp
0x1800040d4  push    rbx
0x1800040d5  lea     rbp, [r11-38h]
0x1800040d9  sub     rsp, 128h
0x1800040e0  mov     rax, cs:__security_cookie
0x1800040e7  xor     rax, rsp
0x1800040ea  mov     [rbp+30h+var_40], rax
0x1800040ee  mov     [r11+10h], rsi
0x1800040f2  xorps   xmm0, xmm0
0x1800040f5  xor     esi, esi
0x1800040f7  mov     [r11-20h], r12
0x1800040fb  mov     [r11-28h], r13
0x1800040ff  mov     r12d, esi
0x180004102  mov     r13, rcx
0x180004105  mov     [r11-38h], r15
0x180004109  xor     ecx, ecx
0x18000410b  mov     [rbp+30h+var_A8], r8
0x18000410f  mov     [rbp+30h+EventAttributes.bInheritHandle], ecx
0x180004112  mov     [rsp+130h+var_B8], rsi
0x180004117  mov     [rbp+30h+var_B0], rsi
0x18000411b  movups  xmmword ptr [rbp+30h+EventAttributes.nLength], xmm0
0x18000411f  mov     [r8], rsi
0x180004122  movups  xmmword ptr [rbp+30h+Uuid.Data1], xmm0
0x180004126  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000412b  mov     edx, 8; dwFlags
0x180004130  test    eax, eax
0x180004132  jnz     loc_1800044EF
0x180004138  mov     rcx, cs:gWfpHeap; hHeap
0x18000413f  mov     r8d, 110h; dwBytes
0x180004145  call    cs:__imp_HeapAlloc
0x18000414c  nop     dword ptr [rax+rax+00h]
0x180004151  mov     [rsp+130h+var_B8], rax
0x180004156  mov     r15, rax
0x180004159  test    rax, rax
0x18000415c  jz      loc_180004641
0x180004162  cmp     cs:gWfpTrackHeapBytes, esi
0x180004168  mov     ebx, esi
0x18000416a  jnz     loc_1800046A5
0x180004170  test    rbx, rbx
0x180004173  jnz     loc_180004474
0x180004179  mov     rcx, r15
0x18000417c  call    WfpCriticalSectionCreate
0x180004181  mov     rbx, rax
0x180004184  test    rax, rax
0x180004187  jnz     loc_180004474
0x18000418d  mov     qword ptr [r15+34h], 4000h
0x180004195  lea     rax, [r15+40h]
0x180004199  mov     [rax+8], rax
0x18000419d  mov     rcx, r13; pSid
0x1800041a0  mov     [rax], rax
0x1800041a3  mov     [rsp+120h], rdi
0x1800041ab  mov     [r15+50h], rsi
0x1800041af  mov     [rsp+130h+var_28], r14
0x1800041b7  mov     [rbp+30h+pSid], rsi
0x1800041bb  mov     [rsp+130h+var_C0], rsi
0x1800041c0  call    cs:__imp_GetLengthSid
0x1800041c7  nop     dword ptr [rax+rax+00h]
0x1800041cc  lea     rcx, [rbp+30h+pSid]; pSid
0x1800041d0  mov     edi, eax
0x1800041d2  call    WfpAllocAnyAppContainerSid
0x1800041d7  mov     rbx, rax
0x1800041da  test    rax, rax
0x1800041dd  jnz     loc_18000455F
0x1800041e3  mov     rcx, [rbp+30h+pSid]; pSid
0x1800041e7  call    cs:__imp_GetLengthSid
0x1800041ee  nop     dword ptr [rax+rax+00h]
0x1800041f3  lea     r14d, [rax+18h]
0x1800041f7  add     r14d, edi
0x1800041fa  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x1800041ff  xor     edx, edx; dwFlags
0x180004201  test    eax, eax
0x180004203  jnz     loc_18000450B
0x180004209  mov     rcx, cs:gWfpHeap; hHeap
0x180004210  lea     r8, [r14+28h]; dwBytes
0x180004214  call    cs:__imp_HeapAlloc
0x18000421b  nop     dword ptr [rax+rax+00h]
0x180004220  mov     [rsp+130h+var_C0], rax
0x180004225  mov     rdi, rax
0x180004228  test    rax, rax
0x18000422b  jz      loc_180004673
0x180004231  cmp     cs:gWfpTrackHeapBytes, esi
0x180004237  mov     rbx, rsi
0x18000423a  jnz     loc_1800046C9
0x180004240  test    rbx, rbx
0x180004243  jnz     loc_18000455F
0x180004249  mov     r8d, 2; dwAclRevision
0x18000424f  lea     rcx, [rdi+28h]; pAcl
0x180004253  mov     edx, r14d; nAclLength
0x180004256  call    cs:__imp_InitializeAcl
0x18000425d  nop     dword ptr [rax+rax+00h]
0x180004262  test    eax, eax
0x180004264  jz      loc_1800046ED
0x18000426a  mov     r9, r13; pSid
0x18000426d  lea     rcx, [rdi+28h]; pAcl
0x180004271  mov     edx, 2; dwAceRevision
0x180004276  mov     r8d, 100000h; AccessMask
0x18000427c  call    cs:__imp_AddAccessAllowedAce
0x180004283  nop     dword ptr [rax+rax+00h]
0x180004288  test    eax, eax
0x18000428a  jz      short loc_1800042F7
0x18000428c  mov     r9, [rbp+30h+pSid]; pSid
0x180004290  lea     rcx, [rdi+28h]; pAcl
0x180004294  mov     edx, 2; dwAceRevision
0x180004299  mov     r8d, 100000h; AccessMask
0x18000429f  call    cs:__imp_AddAccessAllowedAce
0x1800042a6  nop     dword ptr [rax+rax+00h]
0x1800042ab  test    eax, eax
0x1800042ad  jz      short loc_1800042F7
0x1800042af  mov     edx, 1; dwRevision
0x1800042b4  mov     rcx, rdi; pSecurityDescriptor
0x1800042b7  call    cs:__imp_InitializeSecurityDescriptor
0x1800042be  nop     dword ptr [rax+rax+00h]
0x1800042c3  test    eax, eax
0x1800042c5  jz      loc_180004705
0x1800042cb  xor     r9d, r9d; bDaclDefaulted
0x1800042ce  lea     r8, [rdi+28h]; pDacl
0x1800042d2  mov     edx, 1; bDaclPresent
0x1800042d7  mov     rcx, rdi; pSecurityDescriptor
0x1800042da  call    cs:__imp_SetSecurityDescriptorDacl
0x1800042e1  nop     dword ptr [rax+rax+00h]
0x1800042e6  test    eax, eax
0x1800042e8  jz      loc_18000471D
0x1800042ee  mov     r12, rdi
0x1800042f1  mov     [rbp+30h+var_B0], rdi
0x1800042f5  jmp     short loc_18000431E
0x1800042f7  call    cs:__imp_GetLastError
0x1800042fe  nop     dword ptr [rax+rax+00h]
0x180004303  lea     rdx, aAddaccessallow; "AddAccessAllowedAce"
0x18000430a  mov     r8d, eax
0x18000430d  call    WfpReportSysErrorAsWinError
0x180004312  mov     rbx, rax
0x180004315  test    rax, rax
0x180004318  jnz     loc_18000455F
0x18000431e  mov     rcx, [rbp+30h+pSid]; pSid
0x180004322  test    rcx, rcx
0x180004325  jz      short loc_180004333
0x180004327  call    cs:__imp_FreeSid
0x18000432e  nop     dword ptr [rax+rax+00h]
0x180004333  test    rbx, rbx
0x180004336  jnz     loc_180004735
0x18000433c  lea     rcx, [rbp+30h+Uuid]; Uuid
0x180004340  mov     [rbp+30h+EventAttributes.nLength], 18h
0x180004347  mov     [rbp+30h+EventAttributes.lpSecurityDescriptor], r12
0x18000434b  mov     [rbp+30h+EventAttributes.bInheritHandle], esi
0x18000434e  call    cs:__imp_UuidCreate
0x180004355  nop     dword ptr [rax+rax+00h]
0x18000435a  mov     ebx, eax
0x18000435c  test    eax, eax
0x18000435e  jnz     loc_180004526
0x180004364  movzx   edx, [rbp+30h+Uuid.Data4+6]
0x180004368  lea     rcx, [r15+88h]; pszDest
0x18000436f  movzx   r8d, [rbp+30h+Uuid.Data4+5]
0x180004374  movzx   r9d, [rbp+30h+Uuid.Data4+4]
0x180004379  movzx   eax, [rbp+30h+Uuid.Data4+7]
0x18000437d  movzx   r10d, [rbp+30h+Uuid.Data4+3]
0x180004382  movzx   r11d, [rbp+30h+Uuid.Data4+2]
0x180004387  movzx   ebx, [rbp+30h+Uuid.Data4+1]
0x18000438b  movzx   edi, [rbp+30h+Uuid.Data4]
0x18000438f  movzx   esi, [rbp+30h+Uuid.Data3]
0x180004393  movzx   r14d, [rbp+30h+Uuid.Data2]
0x180004398  mov     dword ptr [rsp+130h+var_C8], eax
0x18000439c  mov     [rsp+130h+var_D0], edx
0x1800043a0  mov     edx, 27h ; '''; cchDest
0x1800043a5  mov     [rsp+130h+var_D8], r8d
0x1800043aa  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x1800043b1  mov     [rsp+130h+var_E0], r9d
0x1800043b6  mov     r9d, [rbp+30h+Uuid.Data1]
0x1800043ba  mov     [rsp+130h+var_E8], r10d
0x1800043bf  mov     [rsp+130h+var_F0], r11d
0x1800043c4  mov     [rsp+130h+var_F8], ebx
0x1800043c8  mov     [rsp+130h+var_100], edi
0x1800043cc  mov     [rsp+130h+var_108], esi
0x1800043d0  mov     [rsp+130h+var_110], r14d
0x1800043d5  call    StringCchPrintfW
0x1800043da  movups  xmm0, cs:xmmword_1800B5DC0
0x1800043e1  lea     r9, [r15+58h]; lpName
0x1800043e5  xor     r8d, r8d; bInitialState
0x1800043e8  xor     edx, edx; bManualReset
0x1800043ea  lea     rcx, [rbp+30h+EventAttributes]; lpEventAttributes
0x1800043ee  movups  xmmword ptr [r9], xmm0
0x1800043f2  movups  xmm1, cs:xmmword_1800B5DD0
0x1800043f9  movups  xmmword ptr [r9+10h], xmm1
0x1800043fe  movups  xmm0, cs:xmmword_1800B5DE0
0x180004405  movups  xmmword ptr [r9+20h], xmm0
0x18000440a  call    cs:__imp_CreateEventW
0x180004411  nop     dword ptr [rax+rax+00h]
0x180004416  mov     [r15+0D8h], rax
0x18000441d  test    rax, rax
0x180004420  jz      loc_1800045E1
0x180004426  call    cs:__imp_GetLastError
0x18000442d  nop     dword ptr [rax+rax+00h]
0x180004432  test    eax, eax
0x180004434  jnz     loc_180004749
0x18000443a  lea     rdx, [r15+0E0h]
0x180004441  call    WfpHashtableCreateEx
0x180004446  mov     rbx, rax
0x180004449  test    rax, rax
0x18000444c  jnz     loc_180004760
0x180004452  mov     rax, [rbp+30h+var_A8]
0x180004456  mov     dword ptr [r15+108h], 1
0x180004461  mov     [rax], r15
0x180004464  mov     r14, [rsp+130h+var_28]
0x18000446c  mov     rdi, [rsp+120h]
0x180004474  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180004479  mov     r15, [rsp+130h+var_30]
0x180004481  mov     r13, [rsp+130h+var_20]
0x180004489  mov     rsi, [rsp+130h+arg_8]
0x180004491  test    eax, eax
0x180004493  jnz     short loc_1800044E4
0x180004495  cmp     cs:gWfpTrackHeapBytes, eax
0x18000449b  jnz     loc_180004612
0x1800044a1  mov     rcx, cs:gWfpHeap; hHeap
0x1800044a8  mov     r8, r12; lpMem
0x1800044ab  xor     edx, edx; dwFlags
0x1800044ad  call    cs:__imp_HeapFree
0x1800044b4  nop     dword ptr [rax+rax+00h]
0x1800044b9  mov     r12, [rsp+130h+var_18]
0x1800044c1  test    rbx, rbx
0x1800044c4  jnz     loc_180004774
0x1800044ca  mov     rax, rbx
0x1800044cd  mov     rcx, [rbp+30h+var_40]
0x1800044d1  xor     rcx, rsp; StackCookie
0x1800044d4  call    __security_check_cookie
0x1800044d9  add     rsp, 128h
0x1800044e0  pop     rbx
0x1800044e1  pop     rbp
0x1800044e2  retn
0x1800044e4  lea     rcx, [rbp+30h+var_B0]
0x1800044e8  call    WfpMemFree25B
0x1800044ed  jmp     short loc_1800044B9
0x1800044ef  lea     r8, [rsp+130h+var_B8]
0x1800044f4  mov     ecx, 110h; dwBytes
0x1800044f9  call    WfpMemAlloc25B
0x1800044fe  mov     r15, [rsp+130h+var_B8]
0x180004503  mov     rbx, rax
0x180004506  jmp     loc_180004170
0x18000450b  lea     r8, [rsp+130h+var_C0]
0x180004510  lea     rcx, [r14+28h]; dwBytes
0x180004514  call    WfpMemAlloc25B
0x180004519  mov     rdi, [rsp+130h+var_C0]
0x18000451e  mov     rbx, rax
0x180004521  jmp     loc_180004240
0x180004526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000452d  lea     rax, WPP_GLOBAL_Control
0x180004534  lea     rdi, aUuidcreate; "UuidCreate"
0x18000453b  cmp     rcx, rax
0x18000453e  jz      short loc_180004546
0x180004540  cmp     byte ptr [rcx+19h], 2
0x180004544  jnb     short loc_18000456E
0x180004546  cmp     cs:gWfpLogUserModeErrors, 0
0x18000454d  jnz     short loc_180004590
0x18000454f  test    ebx, ebx
0x180004551  jg      loc_180004604
0x180004557  movsxd  rbx, ebx
0x18000455a  jmp     loc_180004464
0x18000455f  lea     rcx, [rsp+130h+var_C0]
0x180004564  call    WfpMemFree
0x180004569  jmp     loc_18000431E
0x18000456e  test    byte ptr [rcx+1Ch], 1
0x180004572  jz      short loc_180004546
0x180004574  mov     rcx, [rcx+10h]
0x180004578  mov     edx, 17h
0x18000457d  mov     [rsp+130h+var_108], ebx
0x180004581  xor     r9d, r9d
0x180004584  mov     qword ptr [rsp+130h+var_110], rdi
0x180004589  call    WPP_SF_SsD
0x18000458e  jmp     short loc_180004546
0x180004590  test    cs:byte_1800F6115, 1
0x180004597  jz      short loc_18000454F
0x180004599  lea     rax, [rsp+130h+var_C0]
0x18000459e  mov     dword ptr [rsp+130h+var_C0], ebx
0x1800045a2  mov     [rbp+30h+var_50], rax
0x1800045a6  lea     rdx, WFP_USERMODE_ERROR
0x1800045ad  lea     rax, [rbp+30h+var_70]
0x1800045b1  mov     [rbp+30h+var_60], rdi
0x1800045b5  mov     r9d, 3
0x1800045bb  mov     qword ptr [rsp+130h+var_110], rax
0x1800045c0  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800045c7  mov     [rbp+30h+var_58], 0Bh
0x1800045cf  mov     [rbp+30h+var_48], 4
0x1800045d7  call    McGenEventWrite_EtwEventWriteTransfer
0x1800045dc  jmp     loc_18000454F
0x1800045e1  call    cs:__imp_GetLastError
0x1800045e8  nop     dword ptr [rax+rax+00h]
0x1800045ed  mov     r8d, eax
0x1800045f0  lea     rdx, aCreateeventa; "CreateEventA"
0x1800045f7  call    WfpReportSysErrorAsWinError
0x1800045fc  mov     rbx, rax
0x1800045ff  jmp     loc_180004464
0x180004604  movzx   ebx, bx
0x180004607  or      ebx, 80070000h
0x18000460d  jmp     loc_180004557
0x180004612  test    r12, r12
0x180004615  jz      loc_1800044A1
0x18000461b  mov     rcx, cs:gWfpHeap; hHeap
0x180004622  mov     r8, r12; lpMem
0x180004625  xor     edx, edx; dwFlags
0x180004627  call    cs:__imp_HeapSize
0x18000462e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
