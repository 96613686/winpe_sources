# CheckParentProcessIdentity(ulong,int *)

- ea: `0x140022568`
- end: `0x140022a06`
- name: `?CheckParentProcessIdentity@@YAJKPEAH@Z`
- size: `1182`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140005c20`
- `0x140005c40`
- `0x14001da70`
- `0x140021e54`
- `0x140022568`
- `0x140022ac4`
- `0x140024cc0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140022648`
- `KERNEL32!GetCurrentProcessId` at `0x140022648`
- `KERNEL32!Process32FirstW` at `0x14002263a`
- `KERNEL32!Process32FirstW` at `0x14002263a`
- `KERNEL32!Process32NextW` at `0x14002265e`
- `KERNEL32!Process32NextW` at `0x14002265e`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1400225b2`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1400225b2`
- `KERNEL32!LocalFree` at `0x140022899`
- `KERNEL32!LocalFree` at `0x1400228a9`
- `KERNEL32!LocalFree` at `0x140022903`
- `KERNEL32!LocalFree` at `0x140022899`
- `KERNEL32!LocalFree` at `0x1400228a9`
- `KERNEL32!LocalFree` at `0x140022903`
- `KERNEL32!CloseHandle` at `0x14002260b`
- `KERNEL32!CloseHandle` at `0x1400226b0`
- `KERNEL32!CloseHandle` at `0x1400228e3`
- `KERNEL32!CloseHandle` at `0x140022927`
- `KERNEL32!CloseHandle` at `0x1400229ce`
- `KERNEL32!CloseHandle` at `0x14002260b`
- `KERNEL32!CloseHandle` at `0x1400226b0`
- `KERNEL32!CloseHandle` at `0x1400228e3`
- `KERNEL32!CloseHandle` at `0x140022927`
- `KERNEL32!CloseHandle` at `0x1400229ce`
- `KERNEL32!GetLastError` at `0x1400225c1`
- `KERNEL32!GetLastError` at `0x1400226d6`
- `KERNEL32!GetLastError` at `0x140022935`
- `KERNEL32!GetLastError` at `0x140022980`
- `KERNEL32!GetLastError` at `0x1400225c1`
- `KERNEL32!GetLastError` at `0x1400226d6`
- `KERNEL32!GetLastError` at `0x140022935`
- `KERNEL32!GetLastError` at `0x140022980`
- `ADVAPI32!CloseServiceHandle` at `0x14002278b`
- `ADVAPI32!CloseServiceHandle` at `0x1400228d5`
- `ADVAPI32!CloseServiceHandle` at `0x140022919`
- `ADVAPI32!CloseServiceHandle` at `0x14002278b`
- `ADVAPI32!CloseServiceHandle` at `0x1400228d5`
- `ADVAPI32!CloseServiceHandle` at `0x140022919`
- `ADVAPI32!OpenSCManagerW` at `0x1400226c8`
- `ADVAPI32!OpenSCManagerW` at `0x1400226c8`
- `ADVAPI32!EnumServicesStatusExW` at `0x14002275a`
- `ADVAPI32!EnumServicesStatusExW` at `0x1400227d4`
- `ADVAPI32!EnumServicesStatusExW` at `0x14002275a`
- `ADVAPI32!EnumServicesStatusExW` at `0x1400227d4`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14002283c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14002283c`

## pseudocode

```c
__int64 __fastcall CheckParentProcessIdentity(__int64 a1, int *a2)
{
  int *v2; // r14
  HANDLE Toolhelp32Snapshot; // rbx
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD CurrentProcessId; // edi
  DWORD th32ParentProcessID; // r13d
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  unsigned int v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  LPBYTE v15; // rdi
  LPWSTR v16; // rdx
  DWORD v17; // ecx
  unsigned __int64 v18; // r12
  LPBYTE v19; // r15
  wchar_t **v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned int ServiceSid; // r14d
  LPWSTR v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r8
  int v27; // r9d
  int v28; // r10d
  signed int v29; // eax
  signed int v30; // eax
  DWORD ServicesReturned[2]; // [rsp+60h] [rbp-A8h] BYREF
  LPBYTE lpServices; // [rsp+68h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-98h] BYREF
  PROCESSENTRY32W pe; // [rsp+78h] [rbp-90h] BYREF

  v2 = a2;
  *a2 = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  if ( Toolhelp32Snapshot == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v5);
    CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
    return v5;
  }
  memset(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
  {
    v30 = GetLastError();
    v11 = v30;
    if ( v30 > 0 )
      v11 = (unsigned __int16)v30 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 20;
LABEL_74:
      WPP_SF_d(v12[2], v13, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v11);
    }
    goto LABEL_75;
  }
  CurrentProcessId = GetCurrentProcessId();
  while ( pe.th32ProcessID != CurrentProcessId )
  {
    if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
      goto LABEL_14;
  }
  th32ParentProcessID = pe.th32ParentProcessID;
  if ( pe.th32ParentProcessID == -1 )
  {
LABEL_14:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, 2147500037LL);
    if ( Toolhelp32Snapshot )
      CloseHandle(Toolhelp32Snapshot);
    return 2147942402LL;
  }
  v9 = OpenSCManagerW(0, 0, 4u);
  if ( !v9 )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 18;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  ServicesReturned[1] = 0;
  ServicesReturned[0] = 0;
  EnumServicesStatusExW(v9, SC_ENUM_PROCESS_INFO, 0x30u, 1u, 0, 0, ServicesReturned, &ServicesReturned[1], 0, 0);
  lpServices = 0;
  v11 = CommonUtil::MpNewBuffer<unsigned char>(&lpServices, ServicesReturned[0]);
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( lpServices )
      operator delete(lpServices, v14);
    CloseServiceHandle(v9);
LABEL_75:
    if ( Toolhelp32Snapshot )
      CloseHandle(Toolhelp32Snapshot);
    return v11;
  }
  v15 = lpServices;
  if ( EnumServicesStatusExW(
         v9,
         SC_ENUM_PROCESS_INFO,
         0x30u,
         1u,
         lpServices,
         ServicesReturned[0],
         ServicesReturned,
         &ServicesReturned[1],
         0,
         0) )
  {
    v17 = ServicesReturned[1];
    v18 = 0;
    if ( ServicesReturned[1] )
    {
      v19 = v15;
      while ( *v2 != 1 )
      {
        if ( *((_DWORD *)v19 + 11) == th32ParentProcessID )
        {
          v20 = *(wchar_t ***)v19;
          lpServices = 0;
          ServiceSid = MpCreateServiceSid(v20, (PSID *)&lpServices);
          if ( (ServiceSid & 0x80000000) != 0 )
          {
            if ( lpServices )
              LocalFree(lpServices);
            goto LABEL_59;
          }
          StringSid = 0;
          ConvertSidToStringSidW(lpServices, &StringSid);
          v23 = StringSid;
          v24 = 0;
          while ( 1 )
          {
            if ( (*((_BYTE *)&g_IdentityList + v24) & 0x10) != 0 )
            {
              v25 = *(__int64 *)((char *)&g_IdentityList + v24 + 8);
              if ( v25 )
              {
                v16 = StringSid;
                v26 = v25 - (_QWORD)StringSid;
                do
                {
                  v27 = *(LPWSTR)((char *)v16 + v26);
                  v28 = *v16 - v27;
                  if ( v28 )
                    break;
                  ++v16;
                }
                while ( v27 );
                if ( !v28 )
                  break;
              }
            }
            v24 += 16LL;
            if ( v24 >= 0xA0 )
            {
              v2 = a2;
              goto LABEL_45;
            }
          }
          v2 = a2;
          *a2 = 1;
LABEL_45:
          if ( v23 )
            LocalFree(v23);
          if ( lpServices )
            LocalFree(lpServices);
          v17 = ServicesReturned[1];
        }
        ++v18;
        v19 += 56;
        if ( v18 >= v17 )
          break;
      }
    }
    if ( v15 )
      operator delete(v15, (unsigned __int64)v16);
    CloseServiceHandle(v9);
    if ( Toolhelp32Snapshot )
      CloseHandle(Toolhelp32Snapshot);
    return 0;
  }
  else
  {
    v29 = GetLastError();
    ServiceSid = v29;
    if ( v29 > 0 )
      ServiceSid = (unsigned __int16)v29 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, ServiceSid);
LABEL_59:
    if ( v15 )
      operator delete(v15, v21);
    CloseServiceHandle(v9);
    if ( Toolhelp32Snapshot )
      CloseHandle(Toolhelp32Snapshot);
    return ServiceSid;
  }
}

```

## disassembly

```asm
0x140022568  mov     rax, rsp
0x14002256b  mov     [rax+8], rbx
0x14002256f  mov     [rax+18h], rsi
0x140022573  mov     [rax+20h], rdi
0x140022577  push    rbp
0x140022578  push    r12
0x14002257a  push    r13
0x14002257c  push    r14
0x14002257e  push    r15
0x140022580  lea     rbp, [rax-1E8h]
0x140022587  sub     rsp, 2C0h
0x14002258e  mov     rax, cs:__security_cookie
0x140022595  xor     rax, rsp
0x140022598  mov     [rbp+1E0h+var_30], rax
0x14002259f  mov     r14, rdx
0x1400225a2  mov     qword ptr [rsp+2E0h+var_290], rdx
0x1400225a7  xor     r15d, r15d
0x1400225aa  mov     [rdx], r15d
0x1400225ad  xor     edx, edx; th32ProcessID
0x1400225af  lea     ecx, [rdx+2]; dwFlags
0x1400225b2  call    cs:__imp_CreateToolhelp32Snapshot
0x1400225b8  mov     rbx, rax
0x1400225bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400225bf  jnz     short loc_140022618
0x1400225c1  call    cs:__imp_GetLastError
0x1400225c7  mov     ebx, eax
0x1400225c9  test    eax, eax
0x1400225cb  jle     short loc_1400225D6
0x1400225cd  movzx   ebx, ax
0x1400225d0  or      ebx, 80070000h
0x1400225d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400225dd  lea     rax, WPP_GLOBAL_Control
0x1400225e4  cmp     rcx, rax
0x1400225e7  jz      short loc_140022607
0x1400225e9  test    byte ptr [rcx+1Ch], 1
0x1400225ed  jz      short loc_140022607
0x1400225ef  mov     rcx, [rcx+10h]
0x1400225f3  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x1400225fa  mov     edx, 10h
0x1400225ff  mov     r9d, ebx
0x140022602  call    WPP_SF_d
0x140022607  or      rcx, 0FFFFFFFFFFFFFFFFh; hObject
0x14002260b  call    cs:__imp_CloseHandle
0x140022611  mov     eax, ebx
0x140022613  jmp     loc_1400229D6
0x140022618  xor     edx, edx; Val
0x14002261a  lea     rcx, [rsp+2E0h+pe.cntUsage]; void *
0x14002261f  mov     r8d, 234h; Size
0x140022625  call    memset
0x14002262a  lea     rdx, [rsp+2E0h+pe]; lppe
0x14002262f  mov     [rsp+2E0h+pe.dwSize], 238h
0x140022637  mov     rcx, rbx; hSnapshot
0x14002263a  call    cs:__imp_Process32FirstW
0x140022640  test    eax, eax
0x140022642  jz      loc_140022980
0x140022648  call    cs:__imp_GetCurrentProcessId
0x14002264e  mov     edi, eax
0x140022650  cmp     [rsp+2E0h+pe.th32ProcessID], edi
0x140022654  jz      short loc_14002266A
0x140022656  lea     rdx, [rsp+2E0h+pe]; lppe
0x14002265b  mov     rcx, rbx; hSnapshot
0x14002265e  call    cs:__imp_Process32NextW
0x140022664  test    eax, eax
0x140022666  jnz     short loc_140022650
0x140022668  jmp     short loc_140022674
0x14002266a  mov     r13d, [rbp+1E0h+pe.th32ParentProcessID]
0x14002266e  cmp     r13d, 0FFFFFFFFh
0x140022672  jnz     short loc_1400226C0
0x140022674  mov     rcx, cs:WPP_GLOBAL_Control
0x14002267b  lea     rax, WPP_GLOBAL_Control
0x140022682  cmp     rcx, rax
0x140022685  jz      short loc_1400226A8
0x140022687  test    byte ptr [rcx+1Ch], 1
0x14002268b  jz      short loc_1400226A8
0x14002268d  mov     rcx, [rcx+10h]
0x140022691  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x140022698  mov     edx, 11h
0x14002269d  mov     r9d, 80004005h
0x1400226a3  call    WPP_SF_d
0x1400226a8  test    rbx, rbx
0x1400226ab  jz      short loc_1400226B6
0x1400226ad  mov     rcx, rbx; hObject
0x1400226b0  call    cs:__imp_CloseHandle
0x1400226b6  mov     eax, 80070002h
0x1400226bb  jmp     loc_1400229D6
0x1400226c0  xor     edx, edx; lpDatabaseName
0x1400226c2  xor     ecx, ecx; lpMachineName
0x1400226c4  lea     r8d, [rdx+4]; dwDesiredAccess
0x1400226c8  call    cs:__imp_OpenSCManagerW
0x1400226ce  mov     rsi, rax
0x1400226d1  test    rax, rax
0x1400226d4  jnz     short loc_140022716
0x1400226d6  call    cs:__imp_GetLastError
0x1400226dc  mov     edi, eax
0x1400226de  test    eax, eax
0x1400226e0  jle     short loc_1400226EB
0x1400226e2  movzx   edi, ax
0x1400226e5  or      edi, 80070000h
0x1400226eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400226f2  lea     rax, WPP_GLOBAL_Control
0x1400226f9  cmp     rcx, rax
0x1400226fc  jz      loc_1400229C6
0x140022702  test    byte ptr [rcx+1Ch], 1
0x140022706  jz      loc_1400229C6
0x14002270c  mov     edx, 12h
0x140022711  jmp     loc_1400229B3
0x140022716  mov     [rsp+2E0h+pszGroupName], r15; pszGroupName
0x14002271b  lea     rax, [rsp+2E0h+ServicesReturned+4]
0x140022720  mov     [rsp+2E0h+lpResumeHandle], r15; lpResumeHandle
0x140022725  mov     r9d, 1; dwServiceState
0x14002272b  mov     [rsp+2E0h+lpServicesReturned], rax; lpServicesReturned
0x140022730  xor     edx, edx; InfoLevel
0x140022732  lea     rax, [rsp+2E0h+ServicesReturned]
0x140022737  mov     [rsp+2E0h+ServicesReturned+4], r15d
0x14002273c  mov     [rsp+2E0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140022741  mov     rcx, rsi; hSCManager
0x140022744  lea     r12d, [r9+2Fh]
0x140022748  mov     [rsp+2E0h+cbBufSize], r15d; cbBufSize
0x14002274d  mov     r8d, r12d; dwServiceType
0x140022750  mov     [rsp+2E0h+ServicesReturned], r15d
0x140022755  mov     [rsp+2E0h+lpServices], r15; lpServices
0x14002275a  call    cs:__imp_EnumServicesStatusExW
0x140022760  mov     edx, [rsp+2E0h+ServicesReturned]
0x140022764  lea     rcx, [rsp+2E0h+var_280]
0x140022769  mov     [rsp+2E0h+var_280], r15
0x14002276e  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x140022773  mov     edi, eax
0x140022775  test    eax, eax
0x140022777  jns     short loc_140022796
0x140022779  mov     rcx, [rsp+2E0h+var_280]; void *
0x14002277e  test    rcx, rcx
0x140022781  jz      short loc_140022788
0x140022783  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140022788  mov     rcx, rsi; hSCObject
0x14002278b  call    cs:__imp_CloseServiceHandle
0x140022791  jmp     loc_1400229C6
0x140022796  mov     eax, [rsp+2E0h+ServicesReturned]
0x14002279a  lea     rcx, [rsp+2E0h+ServicesReturned+4]
0x14002279f  mov     rdi, [rsp+2E0h+var_280]
0x1400227a4  mov     r9d, 1; dwServiceState
0x1400227aa  mov     [rsp+2E0h+pszGroupName], r15; pszGroupName
0x1400227af  mov     r8d, r12d; dwServiceType
0x1400227b2  mov     [rsp+2E0h+lpResumeHandle], r15; lpResumeHandle
0x1400227b7  xor     edx, edx; InfoLevel
0x1400227b9  mov     [rsp+2E0h+lpServicesReturned], rcx; lpServicesReturned
0x1400227be  lea     rcx, [rsp+2E0h+ServicesReturned]
0x1400227c3  mov     [rsp+2E0h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x1400227c8  mov     rcx, rsi; hSCManager
0x1400227cb  mov     [rsp+2E0h+cbBufSize], eax; cbBufSize
0x1400227cf  mov     [rsp+2E0h+lpServices], rdi; lpServices
0x1400227d4  call    cs:__imp_EnumServicesStatusExW
0x1400227da  test    eax, eax
0x1400227dc  jz      loc_140022935
0x1400227e2  mov     ecx, [rsp+2E0h+ServicesReturned+4]
0x1400227e6  mov     r12, r15
0x1400227e9  test    ecx, ecx
0x1400227eb  jz      loc_1400228C5
0x1400227f1  mov     r15, rdi
0x1400227f4  cmp     dword ptr [r14], 1
0x1400227f8  jz      loc_1400228C5
0x1400227fe  cmp     [r15+2Ch], r13d
0x140022802  jnz     loc_1400228B3
0x140022808  mov     rcx, [r15]; wchar_t **
0x14002280b  lea     rdx, [rsp+2E0h+var_280]; pSid
0x140022810  mov     [rsp+2E0h+var_280], 0
0x140022819  call    ?MpCreateServiceSid@@YAJPEA_WPEAPEAX@Z; MpCreateServiceSid(wchar_t *,void * *)
0x14002281e  mov     rcx, [rsp+2E0h+var_280]; hMem
0x140022823  mov     r14d, eax
0x140022826  test    eax, eax
0x140022828  js      loc_1400228FE
0x14002282e  lea     rdx, [rsp+2E0h+StringSid]; StringSid
0x140022833  mov     [rsp+2E0h+StringSid], 0
0x14002283c  call    cs:__imp_ConvertSidToStringSidW
0x140022842  mov     rcx, [rsp+2E0h+StringSid]; hMem
0x140022847  xor     eax, eax
0x140022849  lea     r8, ?g_IdentityList@@3PAUtagMPIDENTITY_ITEM@@A; tagMPIDENTITY_ITEM near * g_IdentityList
0x140022850  test    byte ptr [rax+r8], 10h
0x140022855  jz      short loc_140022883
0x140022857  mov     r8, [rax+r8+8]
0x14002285c  test    r8, r8
0x14002285f  jz      short loc_140022883
0x140022861  mov     rdx, rcx
0x140022864  sub     r8, rcx
0x140022867  movzx   r10d, word ptr [rdx]
0x14002286b  movzx   r9d, word ptr [rdx+r8]
0x140022870  sub     r10d, r9d
0x140022873  jnz     short loc_14002287E
0x140022875  add     rdx, 2
0x140022879  test    r9d, r9d
0x14002287c  jnz     short loc_140022867
0x14002287e  test    r10d, r10d
0x140022881  jz      short loc_1400228F0
0x140022883  add     rax, 10h
0x140022887  cmp     rax, 0A0h
0x14002288d  jb      short loc_140022849
0x14002288f  mov     r14, qword ptr [rsp+2E0h+var_290]
0x140022894  test    rcx, rcx
0x140022897  jz      short loc_14002289F
0x140022899  call    cs:__imp_LocalFree
0x14002289f  mov     rcx, [rsp+2E0h+var_280]; hMem
0x1400228a4  test    rcx, rcx
0x1400228a7  jz      short loc_1400228AF
0x1400228a9  call    cs:__imp_LocalFree
0x1400228af  mov     ecx, [rsp+2E0h+ServicesReturned+4]
0x1400228b3  inc     r12
0x1400228b6  mov     eax, ecx
0x1400228b8  add     r15, 38h ; '8'
0x1400228bc  cmp     r12, rax
0x1400228bf  jb      loc_1400227F4
0x1400228c5  test    rdi, rdi
0x1400228c8  jz      short loc_1400228D2
0x1400228ca  mov     rcx, rdi; void *
0x1400228cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400228d2  mov     rcx, rsi; hSCObject
0x1400228d5  call    cs:__imp_CloseServiceHandle
0x1400228db  test    rbx, rbx
0x1400228de  jz      short loc_1400228E9
0x1400228e0  mov     rcx, rbx; hObject
0x1400228e3  call    cs:__imp_CloseHandle
0x1400228e9  xor     eax, eax
0x1400228eb  jmp     loc_1400229D6
0x1400228f0  mov     r14, qword ptr [rsp+2E0h+var_290]
0x1400228f5  mov     dword ptr [r14], 1
0x1400228fc  jmp     short loc_140022894
0x1400228fe  test    rcx, rcx
0x140022901  jz      short loc_140022909
0x140022903  call    cs:__imp_LocalFree
0x140022909  test    rdi, rdi
0x14002290c  jz      short loc_140022916
0x14002290e  mov     rcx, rdi; void *
0x140022911  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140022916  mov     rcx, rsi; hSCObject
0x140022919  call    cs:__imp_CloseServiceHandle
0x14002291f  test    rbx, rbx
0x140022922  jz      short loc_14002292D
0x140022924  mov     rcx, rbx; hObject
0x140022927  call    cs:__imp_CloseHandle
0x14002292d  mov     eax, r14d
0x140022930  jmp     loc_1400229D6
0x140022935  call    cs:__imp_GetLastError
0x14002293b  mov     r14d, eax
0x14002293e  test    eax, eax
0x140022940  jle     short loc_14002294D
0x140022942  movzx   r14d, ax
0x140022946  or      r14d, 80070000h
0x14002294d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022954  lea     rax, WPP_GLOBAL_Control
0x14002295b  cmp     rcx, rax
0x14002295e  jz      short loc_140022909
0x140022960  test    byte ptr [rcx+1Ch], 1
0x140022964  jz      short loc_140022909
0x140022966  mov     rcx, [rcx+10h]
0x14002296a  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x140022971  mov     edx, 13h
0x140022976  mov     r9d, r14d
0x140022979  call    WPP_SF_d
0x14002297e  jmp     short loc_140022909
0x140022980  call    cs:__imp_GetLastError
0x140022986  mov     edi, eax
0x140022988  test    eax, eax
0x14002298a  jle     short loc_140022995
0x14002298c  movzx   edi, ax
0x14002298f  or      edi, 80070000h
0x140022995  mov     rcx, cs:WPP_GLOBAL_Control
0x14002299c  lea     rax, WPP_GLOBAL_Control
0x1400229a3  cmp     rcx, rax
0x1400229a6  jz      short loc_1400229C6
0x1400229a8  test    byte ptr [rcx+1Ch], 1
0x1400229ac  jz      short loc_1400229C6
0x1400229ae  mov     edx, 14h
0x1400229b3  mov     rcx, [rcx+10h]
0x1400229b7  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x1400229be  mov     r9d, edi
0x1400229c1  call    WPP_SF_d
0x1400229c6  test    rbx, rbx
0x1400229c9  jz      short loc_1400229D4
0x1400229cb  mov     rcx, rbx; hObject
0x1400229ce  call    cs:__imp_CloseHandle
0x1400229d4  mov     eax, edi
0x1400229d6  mov     rcx, [rbp+1E0h+var_30]
0x1400229dd  xor     rcx, rsp; StackCookie
0x1400229e0  call    __security_check_cookie
0x1400229e5  lea     r11, [rsp+2E0h+var_20]
0x1400229ed  mov     rbx, [r11+30h]
0x1400229f1  mov     rsi, [r11+40h]
0x1400229f5  mov     rdi, [r11+48h]
0x1400229f9  mov     rsp, r11
0x1400229fc  pop     r15
0x1400229fe  pop     r14
0x140022a00  pop     r13
0x140022a02  pop     r12
0x140022a04  pop     rbp
0x140022a05  retn
```
