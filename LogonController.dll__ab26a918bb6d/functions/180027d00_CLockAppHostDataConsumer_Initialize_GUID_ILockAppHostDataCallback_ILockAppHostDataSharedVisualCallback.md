# CLockAppHostDataConsumer::Initialize(_GUID,ILockAppHostDataCallback *,ILockAppHostDataSharedVisualCallback *)

- ea: `0x180027d00`
- end: `0x180028257`
- name: `?Initialize@CLockAppHostDataConsumer@@QEAAJU_GUID@@PEAUILockAppHostDataCallback@@PEAUILockAppHostDataSharedVisualCallback@@@Z`
- size: `1367`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *Context, struct _GUID *, struct ILockAppHostDataCallback *, struct ILockAppHostDataSharedVisualCallback *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180028280`
- `0x18005caf4`

## callees

- `0x180027010`
- `0x180027d00`
- `0x18005d398`
- `0x18005d488`
- `0x18005d4e8`
- `0x1800630b0`
- `0x18006c000`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x1800280eb`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18002811b`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1800280eb`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18002811b`
- `KERNEL32!MapViewOfFile` at `0x1800280aa`
- `KERNEL32!MapViewOfFile` at `0x1800280aa`
- `KERNEL32!CreateFileMappingW` at `0x180028074`
- `KERNEL32!CreateFileMappingW` at `0x180028074`
- `KERNEL32!LocalFree` at `0x180027e62`
- `KERNEL32!LocalFree` at `0x180027f96`
- `KERNEL32!LocalFree` at `0x180028144`
- `KERNEL32!LocalFree` at `0x180028183`
- `KERNEL32!LocalFree` at `0x180027e62`
- `KERNEL32!LocalFree` at `0x180027f96`
- `KERNEL32!LocalFree` at `0x180028144`
- `KERNEL32!LocalFree` at `0x180028183`
- `KERNEL32!CreateEventW` at `0x180027eac`
- `KERNEL32!CreateEventW` at `0x180028013`
- `KERNEL32!CreateEventW` at `0x180027eac`
- `KERNEL32!CreateEventW` at `0x180028013`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027e70`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027fde`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028152`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028191`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027e70`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027fde`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028152`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028191`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027d43`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027d43`
- `KERNEL32!CloseHandle` at `0x1800281fa`
- `KERNEL32!CloseHandle` at `0x1800281fa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027e8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027ff7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027e8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027ff7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027d6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027d6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLockAppHostDataConsumer::Initialize(
        RTL_SRWLOCK *Context,
        struct _GUID *a2,
        struct ILockAppHostDataCallback *a3,
        struct ILockAppHostDataSharedVisualCallback *a4)
{
  RTL_SRWLOCK *v4; // r12
  __int128 v8; // xmm0
  const char *v9; // r9
  const wchar_t *v10; // rdx
  WCHAR *v11; // r9
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r10
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // edi
  __int64 v19; // rdx
  PSECURITY_DESCRIPTOR v20; // rcx
  HANDLE v22; // rax
  const char *v23; // r9
  char *Ptr; // rcx
  HANDLE v25; // rdi
  const wchar_t *v26; // rcx
  __int64 v27; // rdx
  WCHAR *v28; // r8
  __int64 v29; // r9
  WCHAR *v30; // rcx
  __int64 v31; // r10
  unsigned int LastError; // ebx
  __int64 v33; // rdx
  __int64 v34; // rdx
  PSECURITY_DESCRIPTOR v35; // rcx
  HANDLE v36; // rbx
  unsigned __int64 v37; // r8
  const char *v38; // r9
  HANDLE v39; // r14
  const char *v40; // r9
  LPVOID v41; // rbx
  PSECURITY_DESCRIPTOR v42; // rcx
  unsigned int v43; // eax
  PSECURITY_DESCRIPTOR v44; // rcx
  unsigned int v45; // ebx
  __int64 v46; // rdx
  unsigned int v47; // eax
  int dwMaximumSizeLow; // [rsp+20h] [rbp-E0h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-E0h]
  int dwMaximumSizeLowb; // [rsp+20h] [rbp-E0h]
  int dwMaximumSizeLowc; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct ILockAppHostDataCallback *v54; // [rsp+50h] [rbp-B0h]
  WCHAR Name[88]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v56[88]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR lpName[88]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = Context + 2;
  v54 = a3;
  AcquireSRWLockExclusive(Context + 2);
  v8 = (__int128)*a2;
  SecurityDescriptor = 0;
  *(_OWORD *)&Context->Ptr = v8;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;FA;;;SY)(A;;FA;;;IU)S:(ML;;NW;;;LW)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v10 = L"LockAppHostEvent";
    v11 = Name;
    v12 = 2147483646;
    *(_QWORD *)&EventAttributes.nLength = 24;
    v13 = 87;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    v14 = 2147483646;
    v15 = 0;
    do
    {
      if ( !v14 )
        break;
      if ( !*v10 )
        break;
      *v11++ = *v10++;
      --v14;
      ++v15;
      --v13;
    }
    while ( v13 );
    v16 = v11 - 1;
    v17 = v15 - 1;
    v18 = -2147024774;
    if ( v13 )
    {
      v16 = v11;
      v17 = v15;
      v18 = 0;
    }
    *v16 = 0;
    if ( !v13 )
    {
      v19 = 66;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)v18,
        dwMaximumSizeLow);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)v18,
        dwMaximumSizeLowa);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)v18,
        dwMaximumSizeLowb);
      v20 = SecurityDescriptor;
      SecurityDescriptor = 0;
      LocalFree(v20);
      if ( v4 )
        ReleaseSRWLockExclusive(v4);
      return v18;
    }
    if ( !StringFromGUID2((const GUID *const)Context, &Name[v17], 87 - v17) )
    {
      v18 = -2147024774;
      v19 = 67;
      goto LABEL_10;
    }
    v22 = CreateEventW(&EventAttributes, 0, 0, Name);
    Ptr = (char *)Context[5].Ptr;
    v25 = v22;
    Context[5].Ptr = 0;
    if ( (unsigned __int64)(Ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(Ptr);
    Context[5].Ptr = v25;
    if ( !v25 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7C,
                    (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
                    v23);
      goto LABEL_27;
    }
    v26 = L"LockAppHostSharedVisualEvent";
    v27 = 87;
    v28 = v56;
    v29 = 0;
    do
    {
      if ( !v12 )
        break;
      if ( !*v26 )
        break;
      *v28++ = *v26++;
      --v12;
      ++v29;
      --v27;
    }
    while ( v27 );
    v30 = v28 - 1;
    v31 = v29 - 1;
    LastError = -2147024774;
    if ( v27 )
    {
      v30 = v28;
      v31 = v29;
      LastError = 0;
    }
    *v30 = 0;
    if ( !v27 )
    {
      v33 = 66;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)LastError,
        dwMaximumSizeLow);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)LastError,
        dwMaximumSizeLowc);
      v34 = 128;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
        (const char *)LastError,
        dwMaximumSizeLow);
LABEL_27:
      v35 = SecurityDescriptor;
      SecurityDescriptor = 0;
LABEL_28:
      LocalFree(v35);
      if ( v4 )
        ReleaseSRWLockExclusive(v4);
      return LastError;
    }
    if ( !StringFromGUID2((const GUID *const)Context, &v56[v31], 87 - v31) )
    {
      LastError = -2147024774;
      v33 = 67;
      goto LABEL_25;
    }
    v36 = CreateEventW(&EventAttributes, 0, 0, v56);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&Context[7]);
    Context[7].Ptr = v36;
    if ( !v36 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x85,
                    (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
                    v38);
      goto LABEL_27;
    }
    LastError = LockAppHostData::GetMemoryName((GUID *)Context, lpName, v37);
    if ( (LastError & 0x80000000) != 0 )
    {
      v34 = 138;
      goto LABEL_26;
    }
    v39 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &EventAttributes, 4u, 0, 0x10u, lpName);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&Context[4]);
    Context[4].Ptr = v39;
    if ( v39 )
    {
      v41 = MapViewOfFile(v39, 6u, 0, 0, 0x10u);
      CTSmartObj<LockAppHostData *,CTSmartPtr_PolicyComplete<CTSmartPtr_UnmapViewOfFile>>::Release(&Context[3]);
      Context[3].Ptr = v41;
      if ( v41 )
      {
        if ( RegisterWaitForSingleObject(
               &Context[6].Ptr,
               Context[5].Ptr,
               CLockAppHostDataConsumer::_s_OnEvent,
               Context,
               0xFFFFFFFF,
               0) )
        {
          if ( RegisterWaitForSingleObject(
                 &Context[8].Ptr,
                 Context[7].Ptr,
                 CLockAppHostDataConsumer::_s_OnSharedVisualUpdate,
                 Context,
                 0xFFFFFFFF,
                 0) )
          {
            v42 = SecurityDescriptor;
            Context[9].Ptr = v54;
            Context[10].Ptr = a4;
            SecurityDescriptor = 0;
            LocalFree(v42);
            if ( v4 )
              ReleaseSRWLockExclusive(v4);
            return 0;
          }
          v46 = 148;
        }
        else
        {
          v46 = 145;
        }
      }
      else
      {
        v46 = 142;
      }
    }
    else
    {
      v46 = 140;
    }
    v47 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v46,
            (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
            v40);
    v35 = SecurityDescriptor;
    LastError = v47;
    SecurityDescriptor = 0;
    goto LABEL_28;
  }
  v43 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x71,
          (unsigned int)"shell\\lib\\lockapphostdata\\lockapphostdata.cpp",
          v9);
  v44 = SecurityDescriptor;
  v45 = v43;
  SecurityDescriptor = 0;
  LocalFree(v44);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  return v45;
}

```

## disassembly

```asm
0x180027d00  mov     [rsp-8+arg_18], rbx
0x180027d05  push    rbp
0x180027d06  push    r12
0x180027d08  push    r13
0x180027d0a  push    r14
0x180027d0c  push    r15
0x180027d0e  lea     rbp, [rsp-180h]
0x180027d16  sub     rsp, 280h
0x180027d1d  mov     rax, cs:__security_cookie
0x180027d24  xor     rax, rsp
0x180027d27  mov     [rbp+1A0h+var_30], rax
0x180027d2e  lea     r12, [rcx+10h]
0x180027d32  mov     [rsp+2A0h+var_250], r8
0x180027d37  mov     r15, rcx
0x180027d3a  mov     r13, r9
0x180027d3d  mov     rcx, r12; SRWLock
0x180027d40  mov     rbx, rdx
0x180027d43  call    cs:__imp_AcquireSRWLockExclusive
0x180027d49  movaps  xmm0, xmmword ptr [rbx]
0x180027d4c  lea     r8, [rsp+2A0h+SecurityDescriptor]; SecurityDescriptor
0x180027d51  xor     r14d, r14d
0x180027d54  lea     rcx, StringSecurityDescriptor; "D:(A;;FA;;;SY)(A;;FA;;;IU)S:(ML;;NW;;;L"...
0x180027d5b  xor     r9d, r9d; SecurityDescriptorSize
0x180027d5e  mov     [rsp+2A0h+SecurityDescriptor], r14
0x180027d63  mov     edx, 1; StringSDRevision
0x180027d68  movups  xmmword ptr [r15], xmm0
0x180027d6c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180027d72  test    eax, eax
0x180027d74  jz      loc_18002815F
0x180027d7a  mov     rax, [rsp+2A0h+SecurityDescriptor]
0x180027d7f  lea     rdx, aLockapphosteve; "LockAppHostEvent"
0x180027d86  mov     [rsp+2A0h+arg_8], rsi
0x180027d8e  lea     r9, [rsp+2A0h+Name]
0x180027d93  mov     esi, 57h ; 'W'
0x180027d98  mov     [rsp+2A0h+arg_10], rdi
0x180027da0  mov     ebx, 7FFFFFFEh
0x180027da5  mov     qword ptr [rsp+2A0h+EventAttributes.nLength], 18h
0x180027dae  mov     r8d, esi
0x180027db1  mov     [rsp+2A0h+EventAttributes.lpSecurityDescriptor], rax
0x180027db6  mov     qword ptr [rsp+2A0h+EventAttributes.bInheritHandle], r14
0x180027dbb  mov     ecx, ebx
0x180027dbd  mov     r10d, r14d
0x180027dc0  test    rcx, rcx
0x180027dc3  jz      short loc_180027DE5
0x180027dc5  movzx   eax, word ptr [rdx]
0x180027dc8  test    ax, ax
0x180027dcb  jz      short loc_180027DE5
0x180027dcd  mov     [r9], ax
0x180027dd1  add     rdx, 2
0x180027dd5  add     r9, 2
0x180027dd9  dec     rcx
0x180027ddc  inc     r10
0x180027ddf  sub     r8, 1
0x180027de3  jnz     short loc_180027DC0
0x180027de5  test    r8, r8
0x180027de8  lea     rcx, [r9-2]
0x180027dec  lea     rdx, [r10-1]
0x180027df0  mov     edi, 8007007Ah
0x180027df5  cmovnz  rcx, r9
0x180027df9  cmovnz  rdx, r10
0x180027dfd  cmovnz  edi, r14d
0x180027e01  mov     [rcx], r14w
0x180027e05  jnz     short loc_180027E7D
0x180027e07  mov     edx, 42h ; 'B'; void *
0x180027e0c  mov     rcx, [rbp+1A8h]; this
0x180027e13  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027e1a  mov     r9d, edi; char *
0x180027e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e22  mov     rcx, [rbp+1A8h]; this
0x180027e29  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027e30  mov     r9d, edi; char *
0x180027e33  mov     edx, 22h ; '"'; void *
0x180027e38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e3d  mov     rcx, [rbp+1A8h]; this
0x180027e44  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027e4b  mov     r9d, edi; char *
0x180027e4e  mov     edx, 77h ; 'w'; void *
0x180027e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e58  mov     rcx, [rsp+2A0h+SecurityDescriptor]; hMem
0x180027e5d  mov     [rsp+2A0h+SecurityDescriptor], r14
0x180027e62  call    cs:__imp_LocalFree
0x180027e68  test    r12, r12
0x180027e6b  jz      short loc_180027E76
0x180027e6d  mov     rcx, r12; SRWLock
0x180027e70  call    cs:__imp_ReleaseSRWLockExclusive
0x180027e76  mov     eax, edi
0x180027e78  jmp     loc_180027FA3
0x180027e7d  mov     r8d, esi
0x180027e80  lea     rax, [rsp+2A0h+Name]
0x180027e85  sub     r8d, edx; cchMax
0x180027e88  mov     rcx, r15; rguid
0x180027e8b  lea     rdx, [rax+rdx*2]; lpsz
0x180027e8f  call    cs:__imp_StringFromGUID2
0x180027e95  test    eax, eax
0x180027e97  jz      loc_18002819E
0x180027e9d  lea     r9, [rsp+2A0h+Name]; lpName
0x180027ea2  xor     r8d, r8d; bInitialState
0x180027ea5  xor     edx, edx; bManualReset
0x180027ea7  lea     rcx, [rsp+2A0h+EventAttributes]; lpEventAttributes
0x180027eac  call    cs:__imp_CreateEventW
0x180027eb2  mov     rcx, [r15+28h]; hObject
0x180027eb6  mov     rdi, rax
0x180027eb9  mov     [r15+28h], r14
0x180027ebd  lea     rdx, [rcx-1]
0x180027ec1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180027ec5  jbe     loc_1800281FA
0x180027ecb  mov     [r15+28h], rdi
0x180027ecf  test    rdi, rdi
0x180027ed2  jz      loc_180028205
0x180027ed8  lea     rcx, aLockapphostsha; "LockAppHostSharedVisualEvent"
0x180027edf  mov     rdx, rsi
0x180027ee2  lea     r8, [rbp+1A0h+var_190]
0x180027ee6  mov     r9, r14
0x180027ee9  nop     dword ptr [rax+00000000h]
0x180027ef0  test    rbx, rbx
0x180027ef3  jz      short loc_180027F15
0x180027ef5  movzx   eax, word ptr [rcx]
0x180027ef8  test    ax, ax
0x180027efb  jz      short loc_180027F15
0x180027efd  mov     [r8], ax
0x180027f01  add     rcx, 2
0x180027f05  add     r8, 2
0x180027f09  dec     rbx
0x180027f0c  inc     r9
0x180027f0f  sub     rdx, 1
0x180027f13  jnz     short loc_180027EF0
0x180027f15  test    rdx, rdx
0x180027f18  lea     rcx, [r8-2]
0x180027f1c  lea     r10, [r9-1]
0x180027f20  mov     ebx, 8007007Ah
0x180027f25  cmovnz  rcx, r8
0x180027f29  cmovnz  r10, r9
0x180027f2d  cmovnz  ebx, r14d
0x180027f31  mov     [rcx], r14w
0x180027f35  jnz     loc_180027FE6
0x180027f3b  mov     edx, 42h ; 'B'; void *
0x180027f40  mov     rcx, [rbp+1A8h]; this
0x180027f47  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027f4e  mov     r9d, ebx; char *
0x180027f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f56  mov     rcx, [rbp+1A8h]; this
0x180027f5d  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027f64  mov     r9d, ebx; char *
0x180027f67  mov     edx, 2Ch ; ','; void *
0x180027f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f71  mov     edx, 80h; void *
0x180027f76  mov     rcx, [rbp+1A8h]; this
0x180027f7d  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180027f84  mov     r9d, ebx; char *
0x180027f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f8c  mov     rcx, [rsp+2A0h+SecurityDescriptor]; hMem
0x180027f91  mov     [rsp+2A0h+SecurityDescriptor], r14
0x180027f96  call    cs:__imp_LocalFree
0x180027f9c  test    r12, r12
0x180027f9f  jnz     short loc_180027FDB
0x180027fa1  mov     eax, ebx
0x180027fa3  mov     rsi, [rsp+2A0h+arg_8]
0x180027fab  mov     rdi, [rsp+2A0h+arg_10]
0x180027fb3  mov     rcx, [rbp+1A0h+var_30]
0x180027fba  xor     rcx, rsp; StackCookie
0x180027fbd  call    __security_check_cookie
0x180027fc2  mov     rbx, [rsp+2A0h+arg_18]
0x180027fca  add     rsp, 280h
0x180027fd1  pop     r15
0x180027fd3  pop     r14
0x180027fd5  pop     r13
0x180027fd7  pop     r12
0x180027fd9  pop     rbp
0x180027fda  retn
0x180027fdb  mov     rcx, r12; SRWLock
0x180027fde  call    cs:__imp_ReleaseSRWLockExclusive
0x180027fe4  jmp     short loc_180027FA1
0x180027fe6  sub     esi, r10d
0x180027fe9  lea     rdx, [rbp+1A0h+var_190]
0x180027fed  lea     rdx, [rdx+r10*2]; lpsz
0x180027ff1  mov     r8d, esi; cchMax
0x180027ff4  mov     rcx, r15; rguid
0x180027ff7  call    cs:__imp_StringFromGUID2
0x180027ffd  test    eax, eax
0x180027fff  jz      loc_1800281AD
0x180028005  lea     r9, [rbp+1A0h+var_190]; lpName
0x180028009  xor     r8d, r8d; bInitialState
0x18002800c  xor     edx, edx; bManualReset
0x18002800e  lea     rcx, [rsp+2A0h+EventAttributes]; lpEventAttributes
0x180028013  call    cs:__imp_CreateEventW
0x180028019  lea     rcx, [r15+38h]
0x18002801d  mov     rbx, rax
0x180028020  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180028025  mov     [r15+38h], rbx
0x180028029  test    rbx, rbx
0x18002802c  jz      loc_180028224
0x180028032  lea     rdx, [rbp+1A0h+var_E0]; unsigned __int16 *
0x180028039  mov     rcx, r15; rguid
0x18002803c  call    ?GetMemoryName@LockAppHostData@@SAJAEBU_GUID@@PEAG_K@Z; LockAppHostData::GetMemoryName(_GUID const &,ushort *,unsigned __int64)
0x180028041  mov     ebx, eax
0x180028043  test    eax, eax
0x180028045  js      loc_1800281F0
0x18002804b  lea     rax, [rbp+1A0h+var_E0]
0x180028052  xor     r9d, r9d; dwMaximumSizeHigh
0x180028055  mov     [rsp+2A0h+lpName], rax; lpName
0x18002805a  lea     rdx, [rsp+2A0h+EventAttributes]; lpFileMappingAttributes
0x18002805f  mov     r8d, 4; flProtect
0x180028065  mov     [rsp+2A0h+dwMaximumSizeLow], 10h; dwMaximumSizeLow
0x18002806d  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180028074  call    cs:__imp_CreateFileMappingW
0x18002807a  lea     rcx, [r15+20h]
0x18002807e  mov     r14, rax
0x180028081  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180028086  mov     [r15+20h], r14
0x18002808a  test    r14, r14
0x18002808d  jz      loc_1800281E9
0x180028093  xor     r9d, r9d; dwFileOffsetLow
0x180028096  mov     qword ptr [rsp+2A0h+dwMaximumSizeLow], 10h; dwNumberOfBytesToMap
0x18002809f  xor     r8d, r8d; dwFileOffsetHigh
0x1800280a2  mov     edx, 6; dwDesiredAccess
0x1800280a7  mov     rcx, r14; hFileMappingObject
0x1800280aa  call    cs:__imp_MapViewOfFile
0x1800280b0  lea     rcx, [r15+18h]
0x1800280b4  mov     rbx, rax
0x1800280b7  call    ?Release@?$CTSmartObj@PEAULockAppHostData@@V?$CTSmartPtr_PolicyComplete@VCTSmartPtr_UnmapViewOfFile@@@@@@QEAAXXZ; CTSmartObj<LockAppHostData *,CTSmartPtr_PolicyComplete<CTSmartPtr_UnmapViewOfFile>>::Release(void)
0x1800280bc  mov     [r15+18h], rbx
0x1800280c0  test    rbx, rbx
0x1800280c3  jz      loc_180028243
0x1800280c9  mov     rdx, [r15+28h]; hObject
0x1800280cd  lea     rcx, [r15+30h]; phNewWaitObject
0x1800280d1  mov     dword ptr [rsp+2A0h+lpName], 0; dwFlags
0x1800280d9  lea     r8, ?_s_OnEvent@CLockAppHostDataConsumer@@CAXPEAXE@Z; Callback
0x1800280e0  mov     r9, r15; Context
0x1800280e3  mov     [rsp+2A0h+dwMaximumSizeLow], 0FFFFFFFFh; dwMilliseconds
0x1800280eb  call    cs:__imp_RegisterWaitForSingleObject
0x1800280f1  test    eax, eax
0x1800280f3  jz      loc_1800281BC
0x1800280f9  mov     rdx, [r15+38h]; hObject
0x1800280fd  lea     rcx, [r15+40h]; phNewWaitObject
0x180028101  mov     dword ptr [rsp+2A0h+lpName], 0; dwFlags
0x180028109  lea     r8, ?_s_OnSharedVisualUpdate@CLockAppHostDataConsumer@@CAXPEAXE@Z; Callback
0x180028110  mov     r9, r15; Context
0x180028113  mov     [rsp+2A0h+dwMaximumSizeLow], 0FFFFFFFFh; dwMilliseconds
0x18002811b  call    cs:__imp_RegisterWaitForSingleObject
0x180028121  test    eax, eax
0x180028123  jz      loc_18002824D
0x180028129  mov     rax, [rsp+2A0h+var_250]
0x18002812e  mov     rcx, [rsp+2A0h+SecurityDescriptor]; hMem
0x180028133  mov     [r15+48h], rax
0x180028137  mov     [r15+50h], r13
0x18002813b  mov     [rsp+2A0h+SecurityDescriptor], 0
0x180028144  call    cs:__imp_LocalFree
0x18002814a  test    r12, r12
0x18002814d  jz      short loc_180028158
0x18002814f  mov     rcx, r12; SRWLock
0x180028152  call    cs:__imp_ReleaseSRWLockExclusive
0x180028158  xor     eax, eax
0x18002815a  jmp     loc_180027FA3
0x18002815f  mov     rcx, [rbp+1A8h]; this
0x180028166  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x18002816d  mov     edx, 71h ; 'q'; void *
0x180028172  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028177  mov     rcx, [rsp+2A0h+SecurityDescriptor]; hMem
0x18002817c  mov     ebx, eax
0x18002817e  mov     [rsp+2A0h+SecurityDescriptor], r14
0x180028183  call    cs:__imp_LocalFree
0x180028189  test    r12, r12
0x18002818c  jz      short loc_180028197
0x18002818e  mov     rcx, r12; SRWLock
0x180028191  call    cs:__imp_ReleaseSRWLockExclusive
0x180028197  mov     eax, ebx
0x180028199  jmp     loc_180027FB3
0x18002819e  mov     edi, 8007007Ah
0x1800281a3  mov     edx, 43h ; 'C'
0x1800281a8  jmp     loc_180027E0C
0x1800281ad  mov     ebx, 8007007Ah
0x1800281b2  mov     edx, 43h ; 'C'
0x1800281b7  jmp     loc_180027F40
0x1800281bc  mov     edx, 91h; void *
0x1800281c1  mov     rcx, [rbp+1A8h]; this
0x1800281c8  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x1800281cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800281d4  mov     rcx, [rsp+2A0h+SecurityDescriptor]
0x1800281d9  mov     ebx, eax
0x1800281db  mov     [rsp+2A0h+SecurityDescriptor], 0
0x1800281e4  jmp     loc_180027F96
0x1800281e9  mov     edx, 8Ch
0x1800281ee  jmp     short loc_1800281C1
0x1800281f0  mov     edx, 8Ah
0x1800281f5  jmp     loc_180027F76
0x1800281fa  call    cs:__imp_CloseHandle
0x180028200  jmp     loc_180027ECB
0x180028205  mov     rcx, [rbp+1A8h]; this
0x18002820c  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180028213  mov     edx, 7Ch ; '|'; void *
0x180028218  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002821d  mov     ebx, eax
0x18002821f  jmp     loc_180027F8C
0x180028224  mov     rcx, [rbp+1A8h]; this
0x18002822b  lea     r8, aShellLibLockap_0; "shell\\lib\\lockapphostdata\\lockapphos"...
0x180028232  mov     edx, 85h; void *
0x180028237  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002823c  mov     ebx, eax
0x18002823e  jmp     loc_180027F8C
0x180028243  mov     edx, 8Eh
  ... truncated ...
```
