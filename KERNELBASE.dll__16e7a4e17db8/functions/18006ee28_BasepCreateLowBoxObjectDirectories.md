# BasepCreateLowBoxObjectDirectories

- ea: `0x18006ee28`
- end: `0x18006f911`
- name: `BasepCreateLowBoxObjectDirectories`
- size: `2793`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, HANDLE TokenHandle@<rdx>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180066d28`

## callees

- `0x18006ee28`
- `0x18006f918`
- `0x18006fd7c`
- `0x18006fe08`
- `0x1800703bc`
- `0x180070540`
- `0x1800706f4`
- `0x1800708cc`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18006f822`
- `ntdll!RtlSubAuthoritySid` at `0x18006f832`
- `ntdll!RtlSubAuthoritySid` at `0x18006f842`
- `ntdll!RtlSubAuthoritySid` at `0x18006f852`
- `ntdll!RtlSubAuthoritySid` at `0x18006f822`
- `ntdll!RtlSubAuthoritySid` at `0x18006f832`
- `ntdll!RtlSubAuthoritySid` at `0x18006f842`
- `ntdll!RtlSubAuthoritySid` at `0x18006f852`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6e4`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6ee`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6f8`
- `ntdll!RtlFreeUnicodeString` at `0x18006f8b1`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6e4`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6ee`
- `ntdll!RtlFreeUnicodeString` at `0x18006f6f8`
- `ntdll!RtlFreeUnicodeString` at `0x18006f8b1`
- `ntdll!RtlInitUnicodeString` at `0x18006f1d3`
- `ntdll!RtlInitUnicodeString` at `0x18006f305`
- `ntdll!RtlInitUnicodeString` at `0x18006f3e6`
- `ntdll!RtlInitUnicodeString` at `0x18006f4a0`
- `ntdll!RtlInitUnicodeString` at `0x18006f504`
- `ntdll!RtlInitUnicodeString` at `0x18006f890`
- `ntdll!RtlInitUnicodeString` at `0x18006f1d3`
- `ntdll!RtlInitUnicodeString` at `0x18006f305`
- `ntdll!RtlInitUnicodeString` at `0x18006f3e6`
- `ntdll!RtlInitUnicodeString` at `0x18006f4a0`
- `ntdll!RtlInitUnicodeString` at `0x18006f504`
- `ntdll!RtlInitUnicodeString` at `0x18006f890`
- `ntdll!NtQuerySecurityObject` at `0x18006f0c6`
- `ntdll!NtQuerySecurityObject` at `0x18006f11f`
- `ntdll!NtQuerySecurityObject` at `0x18006f0c6`
- `ntdll!NtQuerySecurityObject` at `0x18006f11f`
- `ntdll!NtCreateFile` at `0x18006f5e0`
- `ntdll!NtCreateFile` at `0x18006f5e0`
- `ntdll!RtlGetAce` at `0x18006f58e`
- `ntdll!RtlGetAce` at `0x18006f58e`
- `ntdll!NtQueryInformationToken` at `0x18006efa4`
- `ntdll!NtQueryInformationToken` at `0x18006efcc`
- `ntdll!NtQueryInformationToken` at `0x18006f017`
- `ntdll!NtQueryInformationToken` at `0x18006efa4`
- `ntdll!NtQueryInformationToken` at `0x18006efcc`
- `ntdll!NtQueryInformationToken` at `0x18006f017`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f031`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f06c`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f7f1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f031`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f06c`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006f7f1`
- `ntdll!NtClose` at `0x18006f6a0`
- `ntdll!NtClose` at `0x18006f6af`
- `ntdll!NtClose` at `0x18006f6be`
- `ntdll!NtClose` at `0x18006f6cd`
- `ntdll!NtClose` at `0x18006f905`
- `ntdll!NtClose` at `0x1801909c7`
- `ntdll!NtClose` at `0x18006f6a0`
- `ntdll!NtClose` at `0x18006f6af`
- `ntdll!NtClose` at `0x18006f6be`
- `ntdll!NtClose` at `0x18006f6cd`
- `ntdll!NtClose` at `0x18006f905`
- `ntdll!NtClose` at `0x1801909c7`
- `ntdll!RtlGetAppContainerSidType` at `0x18006f049`
- `ntdll!RtlGetAppContainerSidType` at `0x18006f049`
- `ntdll!RtlGetAppContainerParent` at `0x18006f7d8`
- `ntdll!RtlGetAppContainerParent` at `0x18006f7d8`
- `ntdll!RtlFreeHeap` at `0x18006f607`
- `ntdll!RtlFreeHeap` at `0x18006f629`
- `ntdll!RtlFreeHeap` at `0x18006f64e`
- `ntdll!RtlFreeHeap` at `0x18006f673`
- `ntdll!RtlFreeHeap` at `0x18006f690`
- `ntdll!RtlFreeHeap` at `0x18006f80c`
- `ntdll!RtlFreeHeap` at `0x18006f607`
- `ntdll!RtlFreeHeap` at `0x18006f629`
- `ntdll!RtlFreeHeap` at `0x18006f64e`
- `ntdll!RtlFreeHeap` at `0x18006f673`
- `ntdll!RtlFreeHeap` at `0x18006f690`
- `ntdll!RtlFreeHeap` at `0x18006f80c`
- `ntdll!NtOpenDirectoryObject` at `0x18006f21e`
- `ntdll!NtOpenDirectoryObject` at `0x18006f21e`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f277`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f359`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f43d`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f277`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f359`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18006f43d`
- `ntdll!RtlAllocateHeap` at `0x18006efed`
- `ntdll!RtlAllocateHeap` at `0x18006f0f1`
- `ntdll!RtlAllocateHeap` at `0x18006efed`
- `ntdll!RtlAllocateHeap` at `0x18006f0f1`

## pseudocode

```c
NTSTATUS __fastcall BasepCreateLowBoxObjectDirectories(
        PSID Sid,
        HANDLE TokenHandle,
        HANDLE *a3,
        HANDLE *a4,
        HANDLE *a5,
        __int64 a6,
        void *a7,
        HANDLE *a8,
        _QWORD *a9)
{
  PVOID v9; // r15
  PVOID v10; // rdi
  HANDLE *v11; // rsi
  NTSTATUS result; // eax
  PSID *Heap; // r14
  NTSTATUS v17; // ebx
  int v18; // eax
  ACL *v19; // rdi
  int v20; // ebx
  ULONG v21; // edx
  int *v22; // rdx
  int v23; // r8d
  int v24; // ecx
  HANDLE *v25; // rcx
  ULONG v26; // esi
  ULONG v27; // edi
  ULONG v28; // ebx
  PULONG v29; // rax
  HANDLE v30; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PWSTR FileAttributes; // [rsp+28h] [rbp-D8h]
  ULONG LengthNeeded; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE SourceHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID Ace; // [rsp+80h] [rbp-80h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES v42; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v43; // [rsp+C0h] [rbp-40h] BYREF
  PSID Sida; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v45; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v46; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE v47; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v49; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING v50; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v52[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v53; // [rsp+134h] [rbp+34h]
  PHANDLE v54; // [rsp+140h] [rbp+40h]
  _QWORD *v55; // [rsp+148h] [rbp+48h]
  HANDLE *v56; // [rsp+150h] [rbp+50h]
  _OWORD v57[2]; // [rsp+158h] [rbp+58h] BYREF
  PACL Acl; // [rsp+178h] [rbp+78h]
  HANDLE *v59; // [rsp+180h] [rbp+80h]
  struct _UNICODE_STRING v60; // [rsp+188h] [rbp+88h] BYREF
  struct _UNICODE_STRING v61; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v62; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v63; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C8h] [rbp+C8h] BYREF
  _OWORD v65[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  PVOID P; // [rsp+218h] [rbp+118h]
  _OWORD v67[2]; // [rsp+220h] [rbp+120h] BYREF
  PVOID v68; // [rsp+240h] [rbp+140h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+248h] [rbp+148h] BYREF
  WCHAR SourceString[256]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v71[256]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR v72[256]; // [rsp+660h] [rbp+560h] BYREF
  WCHAR v73[256]; // [rsp+860h] [rbp+760h] BYREF

  v9 = 0;
  v10 = a7;
  v11 = a3;
  v59 = a5;
  v54 = a8;
  v55 = a9;
  *(_QWORD *)&DestinationString.Length = a3;
  Acl = 0;
  v56 = a4;
  Ace = a7;
  LengthNeeded = 0;
  TokenInformation = 0;
  v35 = 0;
  Sida = 0;
  Handle = 0;
  memset(v57, 0, sizeof(v57));
  memset_0(SourceString, 0, sizeof(SourceString));
  *v11 = 0;
  FileHandle = 0;
  P = 0;
  v68 = 0;
  memset(&v42, 0, sizeof(v42));
  SourceHandle = 0;
  v52[0] = 4;
  v46 = 0;
  v43 = 0;
  v47 = 0;
  v45 = 0;
  v52[1] = 1048578;
  memset(v65, 0, sizeof(v65));
  v52[2] = 8;
  v53 = 1048580;
  v60 = 0;
  v36 = 0;
  v62 = 0;
  *a4 = 0;
  memset(v67, 0, sizeof(v67));
  v61 = 0;
  v63 = 0;
  IoStatusBlock = 0;
  v49 = 0;
  v50 = 0;
  UnicodeString = 0;
  result = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &LengthNeeded);
  if ( result >= 0 )
  {
    result = NtQueryInformationToken(TokenHandle, TokenIsRestricted|TokenGroups, &v36, 4u, &LengthNeeded);
    if ( result >= 0 )
    {
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x54u);
      if ( !Heap )
      {
        v17 = -1073741801;
        goto LABEL_43;
      }
      v17 = NtQueryInformationToken(TokenHandle, TokenUser, Heap, 0x54u, &LengthNeeded);
      if ( v17 < 0 )
        goto LABEL_41;
      v17 = RtlConvertSidToUnicodeString(&UnicodeString, *Heap, 1u);
      if ( v17 < 0 )
        goto LABEL_41;
      result = RtlGetAppContainerSidType(Sid, &v35);
      if ( result < 0 )
        return result;
      if ( v35 == 2 )
      {
        result = RtlConvertSidToUnicodeString(&v49, Sid, 1u);
        if ( result < 0 )
          return result;
        goto LABEL_9;
      }
      result = RtlGetAppContainerParent(Sid, &Sida);
      if ( result >= 0 )
      {
        v17 = RtlConvertSidToUnicodeString(&v50, Sida, 1u);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Sida);
        if ( v17 >= 0 )
        {
          v26 = *RtlSubAuthoritySid(Sid, 0xBu);
          v27 = *RtlSubAuthoritySid(Sid, 0xAu);
          v28 = *RtlSubAuthoritySid(Sid, 9u);
          v29 = RtlSubAuthoritySid(Sid, 8u);
          LODWORD(ReturnLength) = v28;
          v17 = RtlStringCchPrintfW(v72, 256, L"%u-%u-%u-%u", *v29, ReturnLength, v27, v26);
          if ( v17 >= 0 )
          {
            RtlInitUnicodeString(&v49, v72);
            v10 = Ace;
            v11 = *(HANDLE **)&DestinationString.Length;
LABEL_9:
            v17 = BasepOpenBaseObjectDirectory(v35, TokenInformation, (int)&v50, v36, (__int64)&UnicodeString, &Handle);
            if ( v17 >= 0 )
            {
              v17 = NtQuerySecurityObject(Handle, 4u, 0, 0, &LengthNeeded);
              if ( (int)(v17 + 0x80000000) < 0 || v17 == -1073741789 )
              {
                v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LengthNeeded);
                if ( !v9 )
                {
                  v17 = -1073741801;
                  goto LABEL_43;
                }
                v17 = NtQuerySecurityObject(Handle, 4u, v9, LengthNeeded, &LengthNeeded);
                if ( v17 >= 0 )
                {
                  v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 0, v57);
                  if ( v17 >= 0 )
                  {
                    DestinationString = 0;
                    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
                    if ( v35 != 2 && (v35 != 1 || !v50.Buffer) )
                    {
                      v17 = -1073741811;
                      goto LABEL_42;
                    }
                    if ( v36 )
                    {
                      if ( v35 != 2 )
                      {
                        LODWORD(ReturnLengtha) = TokenInformation;
                        v18 = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects\\%ws\\%ws",
                                L"\\Sessions",
                                ReturnLengtha,
                                UnicodeString.Buffer,
                                v50.Buffer);
LABEL_18:
                        v17 = v18;
                        if ( v18 < 0 )
                          goto LABEL_42;
                        RtlInitUnicodeString(&DestinationString, SourceString);
                        ObjectAttributes.Length = 48;
                        ObjectAttributes.ObjectName = &DestinationString;
                        ObjectAttributes.RootDirectory = 0;
                        ObjectAttributes.Attributes = 0;
                        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                        v17 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
                        if ( v17 < 0 )
                          goto LABEL_42;
                        v42.RootDirectory = FileHandle;
                        v42.Length = 48;
                        v42.ObjectName = &v49;
                        v42.SecurityDescriptor = v57;
                        v42.Attributes = 130;
                        v42.SecurityQualityOfService = 0;
                        v17 = NtCreateDirectoryObjectEx(&SourceHandle, 15, &v42, Handle, 1);
                        if ( v17 >= 0 )
                        {
                          v17 = BasepSetKernelIntegrityLabel(SourceHandle);
                          if ( v17 >= 0 )
                          {
                            v17 = BasepOpenShadowRpcControlDirectory(
                                    v35,
                                    TokenInformation,
                                    v36,
                                    (int)&UnicodeString,
                                    (__int64)FileHandle,
                                    &v46);
                            if ( v17 >= 0 )
                            {
                              v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 7, v65);
                              if ( v17 >= 0 )
                              {
                                RtlInitUnicodeString(&v60, L"RPC Control");
                                v42.RootDirectory = SourceHandle;
                                v42.Length = 48;
                                v42.ObjectName = &v60;
                                v42.SecurityDescriptor = v65;
                                v42.Attributes = 130;
                                v42.SecurityQualityOfService = 0;
                                v17 = NtCreateDirectoryObjectEx(&v43, 15, &v42, v46, 1);
                                if ( v17 >= 0 )
                                {
                                  v17 = BasepSetKernelIntegrityLabel(v43);
                                  if ( v17 >= 0 )
                                  {
                                    v17 = BasepOpenShadowGlobalDirectory(
                                            v35,
                                            TokenInformation,
                                            v36,
                                            (int)&UnicodeString,
                                            (__int64)FileHandle,
                                            &v47);
                                    if ( v17 >= 0 )
                                    {
                                      v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 7, v67);
                                      if ( v17 >= 0 )
                                      {
                                        RtlInitUnicodeString(&v61, L"Global");
                                        v42.RootDirectory = SourceHandle;
                                        v42.Length = 48;
                                        v42.ObjectName = &v61;
                                        v42.SecurityDescriptor = v67;
                                        v42.Attributes = 130;
                                        v42.SecurityQualityOfService = 0;
                                        v17 = NtCreateDirectoryObjectEx(&v45, 15, &v42, v47, 1);
                                        if ( v17 >= 0 )
                                        {
                                          v17 = BasepSetKernelIntegrityLabel(v45);
                                          if ( v17 >= 0 )
                                          {
                                            v17 = RtlStringCchPrintfW(v71, 256, L"%ws\\%ws", SourceString, v49.Buffer);
                                            if ( v17 >= 0 )
                                            {
                                              RtlInitUnicodeString(&v62, v71);
                                              v17 = BasepCreateLowBoxSymbolicLinks(SourceHandle, &v62, v57, a6, v10);
                                              if ( v17 >= 0 )
                                              {
                                                v17 = RtlStringCchPrintfW(v73, 256, L"\\Device\\NamedPipe%ws", v71);
                                                if ( v17 >= 0 )
                                                {
                                                  RtlInitUnicodeString(&v63, v73);
                                                  v19 = Acl;
                                                  v42.ObjectName = &v63;
                                                  v20 = 0;
                                                  v42.Length = 48;
                                                  v42.SecurityDescriptor = v57;
                                                  v21 = 0;
                                                  v42.RootDirectory = 0;
                                                  v42.Attributes = 66;
                                                  v42.SecurityQualityOfService = 0;
                                                  Ace = 0;
                                                  while ( RtlGetAce(v19, v21, &Ace) >= 0 )
                                                  {
                                                    v22 = v52;
                                                    v23 = *((_DWORD *)Ace + 1);
                                                    *((_WORD *)Ace + 2) = 0;
                                                    v24 = 4;
                                                    do
                                                    {
                                                      if ( v24 == (unsigned __int16)(v24 & v23) )
                                                        *((_DWORD *)Ace + 1) |= v22[1];
                                                      v22 += 2;
                                                      v24 = *v22;
                                                    }
                                                    while ( *v22 );
                                                    v21 = ++v20;
                                                  }
                                                  v17 = NtCreateFile(
                                                          v54,
                                                          0x1F0006u,
                                                          &v42,
                                                          &IoStatusBlock,
                                                          0,
                                                          0x80u,
                                                          3u,
                                                          3u,
                                                          1u,
                                                          0,
                                                          0);
                                                  if ( v17 >= 0 )
                                                  {
                                                    if ( v35 == 1 )
                                                    {
                                                      v30 = Handle;
                                                      Handle = 0;
                                                      *v55 = v30;
                                                    }
                                                    v25 = v56;
                                                    *v11 = SourceHandle;
                                                    *v25 = v43;
                                                    *v59 = v45;
                                                    goto LABEL_42;
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                        goto LABEL_41;
                      }
                      FileAttributes = UnicodeString.Buffer;
                    }
                    else
                    {
                      if ( v35 == 2 )
                      {
                        LODWORD(ReturnLengtha) = TokenInformation;
                        v18 = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects",
                                L"\\Sessions",
                                ReturnLengtha);
                        goto LABEL_18;
                      }
                      FileAttributes = v50.Buffer;
                    }
                    LODWORD(ReturnLengtha) = TokenInformation;
                    v18 = RtlStringCchPrintfW(
                            SourceString,
                            256,
                            L"%ws\\%ld\\AppContainerNamedObjects\\%ws",
                            L"\\Sessions",
                            ReturnLengtha,
                            FileAttributes);
                    goto LABEL_18;
                  }
                }
              }
            }
LABEL_41:
            if ( !v9 )
            {
LABEL_43:
              if ( Acl )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Acl);
              if ( P )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( v68 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v68);
              if ( Heap )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              if ( Handle )
                NtClose(Handle);
              if ( FileHandle )
                NtClose(FileHandle);
              if ( v46 )
                NtClose(v46);
              if ( v47 )
                NtClose(v47);
              if ( v49.Buffer != v72 )
                RtlFreeUnicodeString(&v49);
              RtlFreeUnicodeString(&v50);
              RtlFreeUnicodeString(&UnicodeString);
              if ( v17 < 0 )
              {
                if ( SourceHandle )
                  NtClose(SourceHandle);
                if ( v43 )
                  NtClose(v43);
              }
              return v17;
            }
LABEL_42:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            goto LABEL_43;
          }
          RtlFreeUnicodeString(&v50);
        }
        return v17;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006ee28  push    rbp
0x18006ee2a  push    rbx
0x18006ee2b  push    rsi
0x18006ee2c  push    rdi
0x18006ee2d  push    r12
0x18006ee2f  push    r13
0x18006ee31  push    r14
0x18006ee33  push    r15
0x18006ee35  lea     rbp, [rsp-978h]
0x18006ee3d  sub     rsp, 0A78h
0x18006ee44  mov     rax, cs:__security_cookie
0x18006ee4b  xor     rax, rsp
0x18006ee4e  mov     [rbp+9B0h+var_50], rax
0x18006ee55  mov     rax, [rbp+9B0h+arg_20]
0x18006ee5c  xor     r15d, r15d
0x18006ee5f  mov     rdi, [rbp+9B0h+arg_30]
0x18006ee66  xorps   xmm0, xmm0
0x18006ee69  mov     r13, [rbp+9B0h+arg_28]
0x18006ee70  mov     rsi, r8
0x18006ee73  mov     [rbp+9B0h+var_930], rax
0x18006ee7a  mov     rbx, rdx
0x18006ee7d  mov     rax, [rbp+9B0h+arg_38]
0x18006ee84  mov     r12, rcx
0x18006ee87  mov     [rbp+9B0h+var_970], rax
0x18006ee8b  lea     rcx, [rbp+9B0h+SourceString]; void *
0x18006ee92  mov     rax, [rbp+9B0h+arg_40]
0x18006ee99  xor     edx, edx; Val
0x18006ee9b  mov     [rbp+9B0h+var_968], rax
0x18006ee9f  mov     r14, r9
0x18006eea2  xor     eax, eax
0x18006eea4  mov     qword ptr [rbp+9B0h+DestinationString.Length], r8
0x18006eea8  mov     r8d, 200h; Size
0x18006eeae  mov     [rbp+9B0h+Acl], rax
0x18006eeb2  mov     [rbp+9B0h+var_960], r9
0x18006eeb6  mov     [rbp+9B0h+Ace], rdi
0x18006eeba  mov     [rsp+0AB0h+LengthNeeded], r15d
0x18006eebf  mov     [rsp+0AB0h+TokenInformation], r15d
0x18006eec4  mov     [rsp+0AB0h+var_A4C], r15d
0x18006eec9  mov     [rbp+9B0h+Sid], r15
0x18006eecd  mov     [rsp+0AB0h+Handle], r15
0x18006eed2  movups  [rbp+9B0h+var_958], xmm0
0x18006eed6  movups  [rbp+9B0h+var_948], xmm0
0x18006eeda  call    memset_0
0x18006eedf  xorps   xmm0, xmm0
0x18006eee2  mov     [rsi], r15
0x18006eee5  xor     eax, eax
0x18006eee7  mov     [rbp+9B0h+FileHandle], r15
0x18006eeeb  xorps   xmm1, xmm1
0x18006eeee  mov     [rbp+9B0h+P], rax
0x18006eef5  mov     [rbp+9B0h+var_870], rax
0x18006eefc  lea     r8, [rsp+0AB0h+TokenInformation]; TokenInformation
0x18006ef01  movups  xmmword ptr [rbp+9B0h+var_A20.Length], xmm0
0x18006ef05  lea     ecx, [rax+4]
0x18006ef08  mov     [rsp+0AB0h+SourceHandle], r15
0x18006ef0d  mov     [rbp+9B0h+var_988], ecx
0x18006ef10  lea     edx, [rcx+8]; TokenInformationClass
0x18006ef13  mov     r9d, ecx; TokenInformationLength
0x18006ef16  mov     [rbp+9B0h+var_9D8], r15
0x18006ef1a  lea     rax, [rsp+0AB0h+LengthNeeded]
0x18006ef1f  mov     [rbp+9B0h+var_9F0], r15
0x18006ef23  mov     rcx, rbx; TokenHandle
0x18006ef26  mov     [rbp+9B0h+var_9D0], r15
0x18006ef2a  movups  xmmword ptr [rbp+9B0h+var_A20.ObjectName], xmm0
0x18006ef2e  mov     [rbp+9B0h+var_9E0], r15
0x18006ef32  movups  xmmword ptr [rbp+9B0h+var_A20.SecurityDescriptor], xmm0
0x18006ef36  mov     [rbp+9B0h+var_984], 100002h
0x18006ef3d  movups  [rbp+9B0h+var_8B8], xmm0
0x18006ef44  mov     [rbp+9B0h+var_980], 8
0x18006ef4b  movups  [rbp+9B0h+var_8A8], xmm0
0x18006ef52  mov     [rbp+9B0h+var_97C], 100004h
0x18006ef5a  movups  xmmword ptr [rbp+9B0h+var_928.Length], xmm0
0x18006ef61  mov     [rsp+0AB0h+var_A48], r15d
0x18006ef66  movups  xmmword ptr [rbp+9B0h+var_908.Length], xmm1
0x18006ef6d  mov     [r14], r15
0x18006ef70  movups  [rbp+9B0h+var_890], xmm0
0x18006ef77  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x18006ef7c  movups  [rbp+9B0h+var_880], xmm0
0x18006ef83  movups  xmmword ptr [rbp+9B0h+var_918.Length], xmm0
0x18006ef8a  movups  xmmword ptr [rbp+9B0h+var_8F8.Length], xmm1
0x18006ef91  movups  xmmword ptr [rbp+9B0h+IoStatusBlock], xmm0
0x18006ef98  movups  xmmword ptr [rbp+9B0h+var_9B8.Length], xmm1
0x18006ef9c  movups  xmmword ptr [rbp+9B0h+var_9A8.Length], xmm0
0x18006efa0  movups  xmmword ptr [rbp+9B0h+UnicodeString.Length], xmm1
0x18006efa4  call    cs:__imp_NtQueryInformationToken
0x18006efaa  test    eax, eax
0x18006efac  js      loc_18006F708
0x18006efb2  lea     rax, [rsp+0AB0h+LengthNeeded]
0x18006efb7  mov     rcx, rbx; TokenHandle
0x18006efba  lea     r9d, [r15+4]; TokenInformationLength
0x18006efbe  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x18006efc3  lea     r8, [rsp+0AB0h+var_A48]; TokenInformation
0x18006efc8  lea     edx, [r15+2Ah]; TokenInformationClass
0x18006efcc  call    cs:__imp_NtQueryInformationToken
0x18006efd2  test    eax, eax
0x18006efd4  js      loc_18006F708
0x18006efda  mov     rcx, gs:60h
0x18006efe3  lea     r8d, [r15+54h]; Size
0x18006efe7  xor     edx, edx; Flags
0x18006efe9  mov     rcx, [rcx+30h]; HeapHandle
0x18006efed  call    cs:__imp_RtlAllocateHeap
0x18006eff3  mov     r14, rax
0x18006eff6  test    rax, rax
0x18006eff9  jz      loc_18006F8A3
0x18006efff  lea     rax, [rsp+0AB0h+LengthNeeded]
0x18006f004  mov     r8, r14; TokenInformation
0x18006f007  lea     r9d, [r15+54h]; TokenInformationLength
0x18006f00b  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x18006f010  lea     edx, [r15+1]; TokenInformationClass
0x18006f014  mov     rcx, rbx; TokenHandle
0x18006f017  call    cs:__imp_NtQueryInformationToken
0x18006f01d  mov     ebx, eax
0x18006f01f  test    eax, eax
0x18006f021  js      loc_18006F5F0
0x18006f027  mov     rdx, [r14]; Sid
0x18006f02a  lea     rcx, [rbp+9B0h+UnicodeString]; UnicodeString
0x18006f02e  mov     r8b, 1; AllocateDestinationString
0x18006f031  call    cs:__imp_RtlConvertSidToUnicodeString
0x18006f037  mov     ebx, eax
0x18006f039  test    eax, eax
0x18006f03b  js      loc_18006F5F0
0x18006f041  lea     rdx, [rsp+0AB0h+var_A4C]
0x18006f046  mov     rcx, r12
0x18006f049  call    cs:__imp_RtlGetAppContainerSidType
0x18006f04f  test    eax, eax
0x18006f051  js      loc_18006F708
0x18006f057  cmp     [rsp+0AB0h+var_A4C], 2
0x18006f05c  jnz     loc_18006F7D1
0x18006f062  mov     r8b, 1; AllocateDestinationString
0x18006f065  lea     rcx, [rbp+9B0h+var_9B8]; UnicodeString
0x18006f069  mov     rdx, r12; Sid
0x18006f06c  call    cs:__imp_RtlConvertSidToUnicodeString
0x18006f072  test    eax, eax
0x18006f074  js      loc_18006F708
0x18006f07a  mov     r9d, [rsp+0AB0h+var_A48]; int
0x18006f07f  lea     rax, [rsp+0AB0h+Handle]
0x18006f084  mov     edx, [rsp+0AB0h+TokenInformation]; int
0x18006f088  lea     r8, [rbp+9B0h+var_9A8]; int
0x18006f08c  mov     ecx, [rsp+0AB0h+var_A4C]; int
0x18006f090  mov     qword ptr [rsp+0AB0h+FileAttributes], rax; FileHandle
0x18006f095  lea     rax, [rbp+9B0h+UnicodeString]
0x18006f099  mov     [rsp+0AB0h+ReturnLength], rax; __int64
0x18006f09e  call    BasepOpenBaseObjectDirectory
0x18006f0a3  mov     ebx, eax
0x18006f0a5  test    eax, eax
0x18006f0a7  js      loc_18006F5F0
0x18006f0ad  mov     rcx, [rsp+0AB0h+Handle]; Handle
0x18006f0b2  lea     rax, [rsp+0AB0h+LengthNeeded]
0x18006f0b7  xor     r9d, r9d; Length
0x18006f0ba  mov     [rsp+0AB0h+ReturnLength], rax; LengthNeeded
0x18006f0bf  xor     r8d, r8d; SecurityDescriptor
0x18006f0c2  lea     edx, [r9+4]; SecurityInformation
0x18006f0c6  call    cs:__imp_NtQuerySecurityObject
0x18006f0cc  mov     ecx, 80000000h
0x18006f0d1  mov     ebx, eax
0x18006f0d3  add     eax, ecx
0x18006f0d5  test    ecx, eax
0x18006f0d7  jz      loc_18006F72B
0x18006f0dd  mov     rcx, gs:60h
0x18006f0e6  xor     edx, edx; Flags
0x18006f0e8  mov     r8d, [rsp+0AB0h+LengthNeeded]; Size
0x18006f0ed  mov     rcx, [rcx+30h]; HeapHandle
0x18006f0f1  call    cs:__imp_RtlAllocateHeap
0x18006f0f7  mov     r15, rax
0x18006f0fa  test    rax, rax
0x18006f0fd  jz      loc_18006F8BC
0x18006f103  mov     r9d, [rsp+0AB0h+LengthNeeded]; Length
0x18006f108  lea     rax, [rsp+0AB0h+LengthNeeded]
0x18006f10d  mov     rcx, [rsp+0AB0h+Handle]; Handle
0x18006f112  mov     r8, r15; SecurityDescriptor
0x18006f115  mov     edx, 4; SecurityInformation
0x18006f11a  mov     [rsp+0AB0h+ReturnLength], rax; LengthNeeded
0x18006f11f  call    cs:__imp_NtQuerySecurityObject
0x18006f125  mov     ebx, eax
0x18006f127  test    eax, eax
0x18006f129  js      loc_18006F5F0
0x18006f12f  mov     r8, [r14]; Sid1
0x18006f132  lea     rax, [rbp+9B0h+var_958]
0x18006f136  xor     r9d, r9d
0x18006f139  mov     [rsp+0AB0h+ReturnLength], rax; PSECURITY_DESCRIPTOR
0x18006f13e  mov     rdx, r12; Sid
0x18006f141  mov     rcx, r15; SecurityDescriptor
0x18006f144  call    BasepBuildPackageSecurityDescriptor
0x18006f149  mov     ebx, eax
0x18006f14b  test    eax, eax
0x18006f14d  js      loc_18006F5F0
0x18006f153  mov     eax, [rsp+0AB0h+var_A4C]
0x18006f157  xorps   xmm1, xmm1
0x18006f15a  mov     rdx, [rbp+9B0h+var_9A8.Buffer]
0x18006f15e  xorps   xmm0, xmm0
0x18006f161  movups  xmmword ptr [rbp+9B0h+DestinationString.Length], xmm0
0x18006f165  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.Length], xmm1
0x18006f16c  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.ObjectName], xmm1
0x18006f173  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18006f17a  cmp     eax, 2
0x18006f17d  jnz     loc_18006F8C6
0x18006f183  cmp     [rsp+0AB0h+var_A48], 0
0x18006f188  lea     r9, aSessions; "\\Sessions"
0x18006f18f  mov     ecx, [rsp+0AB0h+TokenInformation]
0x18006f193  jnz     loc_18006F73C
0x18006f199  cmp     eax, 2
0x18006f19c  jnz     loc_18006F7C7
0x18006f1a2  mov     dword ptr [rsp+0AB0h+ReturnLength], ecx
0x18006f1a6  lea     r8, aWsLdAppcontain_1; "%ws\\%ld\\AppContainerNamedObjects"
0x18006f1ad  lea     rcx, [rbp+9B0h+SourceString]
0x18006f1b4  mov     edx, 100h
0x18006f1b9  call    RtlStringCchPrintfW
0x18006f1be  mov     ebx, eax
0x18006f1c0  test    eax, eax
0x18006f1c2  js      loc_18006F5F5
0x18006f1c8  lea     rdx, [rbp+9B0h+SourceString]; SourceString
0x18006f1cf  lea     rcx, [rbp+9B0h+DestinationString]; DestinationString
0x18006f1d3  call    cs:__imp_RtlInitUnicodeString
0x18006f1d9  lea     rax, [rbp+9B0h+DestinationString]
0x18006f1dd  mov     [rbp+9B0h+ObjectAttributes.Length], 30h ; '0'
0x18006f1e7  xorps   xmm0, xmm0
0x18006f1ea  mov     [rbp+9B0h+ObjectAttributes.ObjectName], rax
0x18006f1f1  lea     r8, [rbp+9B0h+ObjectAttributes]; ObjectAttributes
0x18006f1f8  mov     [rbp+9B0h+ObjectAttributes.RootDirectory], 0
0x18006f203  mov     edx, 0Fh; DesiredAccess
0x18006f208  mov     [rbp+9B0h+ObjectAttributes.Attributes], 0
0x18006f212  lea     rcx, [rbp+9B0h+FileHandle]; FileHandle
0x18006f216  movdqu  xmmword ptr [rbp+9B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f21e  call    cs:__imp_NtOpenDirectoryObject
0x18006f224  mov     ebx, eax
0x18006f226  test    eax, eax
0x18006f228  js      loc_18006F5F5
0x18006f22e  mov     rax, [rbp+9B0h+FileHandle]
0x18006f232  lea     r8, [rbp+9B0h+var_A20]
0x18006f236  mov     r9, [rsp+0AB0h+Handle]
0x18006f23b  lea     rcx, [rsp+0AB0h+SourceHandle]
0x18006f240  mov     [rbp+9B0h+var_A20.RootDirectory], rax
0x18006f244  mov     edx, 0Fh
0x18006f249  lea     rax, [rbp+9B0h+var_9B8]
0x18006f24d  mov     [rbp+9B0h+var_A20.Length], 30h ; '0'
0x18006f254  mov     [rbp+9B0h+var_A20.ObjectName], rax
0x18006f258  lea     rax, [rbp+9B0h+var_958]
0x18006f25c  mov     [rbp+9B0h+var_A20.SecurityDescriptor], rax
0x18006f260  mov     [rbp+9B0h+var_A20.Attributes], 82h
0x18006f267  mov     [rbp+9B0h+var_A20.SecurityQualityOfService], 0
0x18006f26f  mov     dword ptr [rsp+0AB0h+ReturnLength], 1
0x18006f277  call    cs:__imp_NtCreateDirectoryObjectEx
0x18006f27d  mov     ebx, eax
0x18006f27f  test    eax, eax
0x18006f281  js      loc_18006F5F0
0x18006f287  mov     rcx, [rsp+0AB0h+SourceHandle]; SourceHandle
0x18006f28c  call    BasepSetKernelIntegrityLabel
0x18006f291  mov     ebx, eax
0x18006f293  test    eax, eax
0x18006f295  js      loc_18006F5F0
0x18006f29b  mov     r8d, [rsp+0AB0h+var_A48]; int
0x18006f2a0  lea     rax, [rbp+9B0h+var_9D8]
0x18006f2a4  mov     edx, [rsp+0AB0h+TokenInformation]; int
0x18006f2a8  lea     r9, [rbp+9B0h+UnicodeString]; int
0x18006f2ac  mov     ecx, [rsp+0AB0h+var_A4C]; int
0x18006f2b0  mov     qword ptr [rsp+0AB0h+FileAttributes], rax; FileHandle
0x18006f2b5  mov     rax, [rbp+9B0h+FileHandle]
0x18006f2b9  mov     [rsp+0AB0h+ReturnLength], rax; __int64
0x18006f2be  call    BasepOpenShadowRpcControlDirectory
0x18006f2c3  mov     ebx, eax
0x18006f2c5  test    eax, eax
0x18006f2c7  js      loc_18006F5F0
0x18006f2cd  mov     r8, [r14]; Sid1
0x18006f2d0  lea     rax, [rbp+9B0h+var_8B8]
0x18006f2d7  mov     r9d, 7
0x18006f2dd  mov     [rsp+0AB0h+ReturnLength], rax; PSECURITY_DESCRIPTOR
0x18006f2e2  mov     rdx, r12; Sid
0x18006f2e5  mov     rcx, r15; SecurityDescriptor
0x18006f2e8  call    BasepBuildPackageSecurityDescriptor
0x18006f2ed  mov     ebx, eax
0x18006f2ef  test    eax, eax
0x18006f2f1  js      loc_18006F5F0
0x18006f2f7  lea     rdx, aRpcControl; "RPC Control"
0x18006f2fe  lea     rcx, [rbp+9B0h+var_928]; DestinationString
0x18006f305  call    cs:__imp_RtlInitUnicodeString
0x18006f30b  mov     rax, [rsp+0AB0h+SourceHandle]
0x18006f310  lea     r8, [rbp+9B0h+var_A20]
0x18006f314  mov     r9, [rbp+9B0h+var_9D8]
0x18006f318  lea     rcx, [rbp+9B0h+var_9F0]
0x18006f31c  mov     [rbp+9B0h+var_A20.RootDirectory], rax
0x18006f320  mov     edx, 0Fh
0x18006f325  lea     rax, [rbp+9B0h+var_928]
0x18006f32c  mov     [rbp+9B0h+var_A20.Length], 30h ; '0'
0x18006f333  mov     [rbp+9B0h+var_A20.ObjectName], rax
0x18006f337  lea     rax, [rbp+9B0h+var_8B8]
0x18006f33e  mov     [rbp+9B0h+var_A20.SecurityDescriptor], rax
0x18006f342  mov     [rbp+9B0h+var_A20.Attributes], 82h
0x18006f349  mov     [rbp+9B0h+var_A20.SecurityQualityOfService], 0
0x18006f351  mov     dword ptr [rsp+0AB0h+ReturnLength], 1
0x18006f359  call    cs:__imp_NtCreateDirectoryObjectEx
0x18006f35f  mov     ebx, eax
0x18006f361  test    eax, eax
0x18006f363  js      loc_18006F5F0
0x18006f369  mov     rcx, [rbp+9B0h+var_9F0]; SourceHandle
0x18006f36d  call    BasepSetKernelIntegrityLabel
0x18006f372  mov     ebx, eax
0x18006f374  test    eax, eax
0x18006f376  js      loc_18006F5F0
0x18006f37c  mov     r8d, [rsp+0AB0h+var_A48]; int
0x18006f381  lea     rax, [rbp+9B0h+var_9D0]
0x18006f385  mov     edx, [rsp+0AB0h+TokenInformation]; int
  ... truncated ...
```
