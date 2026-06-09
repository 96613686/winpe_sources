# DavAsyncCreateGet

- ea: `0x180016d24`
- end: `0x18001761b`
- name: `DavAsyncCreateGet`
- size: `2295`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001507c`
- `0x180017624`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b81c`
- `0x18000b93c`
- `0x18000bbec`
- `0x18000bc5c`
- `0x180016d24`
- `0x180019454`
- `0x18001bbe0`
- `0x18001befc`
- `0x18001c260`
- `0x18001c430`
- `0x18001c4f0`
- `0x1800297e4`
- `0x18002cfa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800175ad`
- `ntdll!RtlFreeHeap` at `0x1800175ad`
- `ntdll!NtQueryInformationFile` at `0x180017467`
- `ntdll!NtQueryInformationFile` at `0x180017467`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001727d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001727d`
- `ntdll!NtCreateFile` at `0x18001736b`
- `ntdll!NtCreateFile` at `0x18001736b`
- `ntdll!RtlNtStatusToDosError` at `0x18001737d`
- `ntdll!RtlNtStatusToDosError` at `0x180017478`
- `ntdll!RtlNtStatusToDosError` at `0x18001737d`
- `ntdll!RtlNtStatusToDosError` at `0x180017478`
- `ntdll!NtClose` at `0x180017484`
- `ntdll!NtClose` at `0x180017484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017214`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001704f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001704f`
- `KERNEL32!LocalFree` at `0x180016f98`
- `KERNEL32!LocalFree` at `0x180016f98`
- `ADVAPI32!EncryptFileW` at `0x1800171b2`
- `ADVAPI32!EncryptFileW` at `0x1800171b2`

## pseudocode

```c
__int64 __fastcall DavAsyncCreateGet(__int64 a1)
{
  __int64 v1; // rsi
  int v2; // r15d
  int v4; // r13d
  WCHAR *v5; // r14
  ULONG LastError; // eax
  ULONG v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  _QWORD *v11; // rcx
  _QWORD *v12; // rcx
  int v13; // edx
  void *v14; // rcx
  _WORD *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // rcx
  _BYTE *v19; // r14
  void *v20; // rcx
  int v21; // eax
  const WCHAR *v22; // rcx
  char v23; // al
  int v24; // r8d
  void *v25; // rax
  void *v26; // rcx
  unsigned int v27; // ecx
  int v28; // r12d
  NTSTATUS v29; // eax
  NTSTATUS v30; // esi
  int v31; // edx
  int v32; // r8d
  NTSTATUS v33; // eax
  int v34; // r8d
  unsigned int v35; // esi
  __int64 v36; // rcx
  void *v37; // rax
  ULONG v38; // eax
  ULONG v39; // ebx
  void *FileHandle; // [rsp+60h] [rbp-79h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-61h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-21h] BYREF
  int v46; // [rsp+C0h] [rbp-19h]
  __int128 FileInformation; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-1h]

  FileHandle = (void *)-1LL;
  *(_QWORD *)&NtPathName.Length = 0;
  NtPathName.Buffer = 0;
  v1 = a1 + 2312;
  v45 = 0;
  v46 = 0;
  v2 = 1;
  v4 = 0;
  v48 = 0;
  memset(&ObjectAttributes, 0, 32);
  *(_DWORD *)(a1 + 3888) = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( (*(_DWORD *)(a1 + 5504) & 0x4000) == 0 )
  {
    v20 = *(void **)(a1 + 536);
    if ( v20 )
    {
      if ( !CloseHandle(v20) )
      {
        LastError = GetLastError();
        v7 = LastError;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 195;
          goto LABEL_9;
        }
        goto LABEL_109;
      }
      *(_QWORD *)(a1 + 536) = 0;
    }
    v19 = (_BYTE *)(a1 + 704);
    if ( (*(_DWORD *)(a1 + 704) & 0x4000) != 0 )
    {
      if ( (*v19 & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
        v7 = 6009;
        goto LABEL_109;
      }
      v21 = *(_DWORD *)(a1 + 712);
      v7 = 0;
      v2 = 0;
      if ( (v21 & 0xFFFFFFFA) == 0 && v21 != 1 )
      {
        v7 = DavSetAclForEncryptedFile(*(LPCWSTR *)(a1 + 576));
        if ( v7 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_109;
          v13 = 197;
LABEL_21:
          WPP_SF_dS(
            v12[2],
            v13,
            (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            v7,
            *(_QWORD *)(a1 + 576));
          goto LABEL_109;
        }
        LastError = UMReflectorImpersonate(a1, *(_QWORD *)(a1 + 72));
        v7 = LastError;
        if ( LastError )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 198;
            goto LABEL_9;
          }
          goto LABEL_109;
        }
        v4 = 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            199,
            WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            &NtPathName);
        if ( !EncryptFileW(*(LPCWSTR *)(a1 + 576)) )
        {
          LastError = GetLastError();
          v7 = LastError;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 201;
            goto LABEL_9;
          }
          goto LABEL_109;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            200,
            WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            &NtPathName);
        *(_DWORD *)(a1 + 3892) = 1;
        *(_DWORD *)(v1 + 3192) |= 0x4000u;
        *(_DWORD *)v19 &= ~0x4000u;
        *(_DWORD *)(v1 + 3192) |= 0x4000u;
        *(_DWORD *)(a1 + 3892) = 1;
      }
    }
    else
    {
      v7 = 0;
      v2 = 0;
    }
LABEL_79:
    v22 = *(const WCHAR **)(a1 + 576);
    HIDWORD(v45) = *(_DWORD *)(a1 + 684);
    v23 = *(_BYTE *)(a1 + 688) & 2;
    LODWORD(v45) = 12;
    BYTE1(v46) = v23;
    LOBYTE(v46) = 0;
    if ( RtlDosPathNameToNtPathName_U(v22, &NtPathName, 0, 0) )
    {
      v24 = *(_DWORD *)v19;
      ObjectAttributes.ObjectName = &NtPathName;
      v25 = *(void **)(a1 + 672);
      ObjectAttributes.RootDirectory = 0;
      v26 = 0;
      ObjectAttributes.Length = 48;
      if ( v25 )
        v26 = v25;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.SecurityDescriptor = v26;
      v27 = *(_DWORD *)(a1 + 692) & 0xFEFFFFFB;
      ObjectAttributes.SecurityQualityOfService = &v45;
      v28 = v27 | ((v27 & 0x21) != 0 ? 130 : 128);
      v29 = NtCreateFile(
              &FileHandle,
              v28,
              &ObjectAttributes,
              &IoStatusBlock,
              (PLARGE_INTEGER)(a1 + 696),
              v24 & 0xFFFFFFFE,
              7u,
              *(_DWORD *)(a1 + 712),
              *(_DWORD *)(a1 + 716) | 8,
              *(PVOID *)(a1 + 720),
              *(_DWORD *)(a1 + 728));
      v30 = v29;
      if ( v29 )
      {
        v7 = RtlNtStatusToDosError(v29);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DDDqDDDDS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v31,
            v32,
            v30,
            *(_DWORD *)(a1 + 684),
            *(_DWORD *)(a1 + 688),
            *(_QWORD *)(a1 + 672),
            v28,
            *(_DWORD *)v19,
            *(_DWORD *)(a1 + 712),
            *(_DWORD *)(a1 + 716),
            *(_QWORD *)(a1 + 576));
        FileHandle = (void *)-1LL;
        *(_QWORD *)(a1 + 5456) = 0;
        *(_QWORD *)(a1 + 5464) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            209,
            WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            FileHandle);
        v33 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
        v35 = v33;
        if ( v33 )
        {
          v7 = RtlNtStatusToDosError(v33);
          NtClose(FileHandle);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v35);
          *(_QWORD *)(a1 + 5456) = 0;
          *(_QWORD *)(a1 + 5464) = 0;
          FileHandle = (void *)-1LL;
        }
        else
        {
          if ( v2 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                212,
                WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
                *(_QWORD *)(a1 + 632));
            *(_OWORD *)(a1 + 5512) = FileInformation;
          }
          else
          {
            v36 = *((_QWORD *)&FileInformation + 1);
            if ( *((_QWORD *)&FileInformation + 1) != *(_QWORD *)(a1 + 5520) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SDDDD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (_DWORD)WPP_GLOBAL_Control,
                  v34,
                  *(_QWORD *)(a1 + 632),
                  SBYTE12(FileInformation),
                  SBYTE8(FileInformation),
                  *(_DWORD *)(a1 + 5524),
                  *(_DWORD *)(a1 + 5520));
                v36 = *((_QWORD *)&FileInformation + 1);
              }
              *(_QWORD *)(a1 + 5512) = FileInformation;
              *(_QWORD *)(a1 + 5520) = v36;
            }
          }
          v37 = FileHandle;
          *(_QWORD *)(a1 + 5456) = FileHandle;
          *(_QWORD *)(a1 + 5464) = v37;
        }
      }
    }
    else
    {
      v7 = 161;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 207;
        v10 = 161;
        goto LABEL_10;
      }
    }
    goto LABEL_109;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
  v5 = *(WCHAR **)(a1 + 576);
  *(_QWORD *)(a1 + 576) = 0;
  LastError = DavCreateUrlCacheEntry((_QWORD *)a1);
  v7 = LastError;
  if ( LastError )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 188;
LABEL_9:
      v10 = LastError;
LABEL_10:
      WPP_SF_d(v8[2], v9, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v10);
      goto LABEL_109;
    }
    goto LABEL_109;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v5);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_S(v11[2], 190, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, *(_QWORD *)(a1 + 576));
  }
  v7 = DavSetAclForEncryptedFile(*(LPCWSTR *)(a1 + 576));
  if ( v7 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_109;
    v13 = 191;
    goto LABEL_21;
  }
  v14 = *(void **)(a1 + 536);
  if ( !v14 )
  {
LABEL_28:
    LastError = UMReflectorImpersonate(a1, *(_QWORD *)(a1 + 72));
    v7 = LastError;
    if ( LastError )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 193;
        goto LABEL_9;
      }
      goto LABEL_109;
    }
    v4 = 1;
    v7 = DavRestoreEncryptedFile(v5, *(LPCWSTR *)(a1 + 576));
    if ( v5 )
      LocalFree(v5);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 194);
      goto LABEL_109;
    }
    v15 = *(_WORD **)(a1 + 576);
    v16 = 2147483646;
    v17 = 260;
    do
    {
      if ( !v16 )
        break;
      if ( !*v15 )
        break;
      *(_WORD *)v1 = *v15++;
      v1 += 2;
      --v16;
      --v17;
    }
    while ( v17 );
    v18 = (_WORD *)(v1 - 2);
    v19 = (_BYTE *)(a1 + 704);
    if ( v17 )
      v18 = (_WORD *)v1;
    *v18 = 0;
    *(_DWORD *)(a1 + 3892) = 1;
    goto LABEL_79;
  }
  if ( CloseHandle(v14) )
  {
    *(_QWORD *)(a1 + 536) = 0;
    goto LABEL_28;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 192;
    goto LABEL_9;
  }
LABEL_109:
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( !v4 )
  {
    v38 = UMReflectorImpersonate(a1, *(_QWORD *)(a1 + 72));
    v39 = v38;
    if ( v38 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v38);
      if ( !v7 )
        return v39;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180016d24  push    rbp
0x180016d26  push    rbx
0x180016d27  push    rsi
0x180016d28  push    rdi
0x180016d29  push    r12
0x180016d2b  push    r13
0x180016d2d  push    r14
0x180016d2f  push    r15
0x180016d31  lea     rbp, [rsp-1Fh]
0x180016d36  sub     rsp, 0F8h
0x180016d3d  mov     rax, cs:__security_cookie
0x180016d44  xor     rax, rsp
0x180016d47  mov     [rbp+57h+var_50], rax
0x180016d4b  xor     r12d, r12d
0x180016d4e  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180016d56  xorps   xmm0, xmm0
0x180016d59  mov     qword ptr [rbp+57h+NtPathName.Length], r12
0x180016d5d  xor     eax, eax
0x180016d5f  mov     [rbp+57h+NtPathName.Buffer], r12
0x180016d63  lea     rsi, [rcx+908h]
0x180016d6a  mov     [rbp+57h+var_78], rax
0x180016d6e  mov     edi, 4000h
0x180016d73  mov     [rbp+57h+var_70], eax
0x180016d76  lea     r15d, [r12+1]
0x180016d7b  mov     rbx, rcx
0x180016d7e  lea     r14, WPP_GLOBAL_Control
0x180016d85  mov     r13d, r12d
0x180016d88  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180016d8c  mov     [rbp+57h+var_58], rax
0x180016d90  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180016d94  mov     [rsi+628h], r12d
0x180016d9b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180016d9f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180016da3  movups  [rbp+57h+FileInformation], xmm0
0x180016da7  test    [rsi+0C78h], edi
0x180016dad  jz      loc_180017043
0x180016db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dba  cmp     rcx, r14
0x180016dbd  jz      short loc_180016DDA
0x180016dbf  test    byte ptr [rcx+1Ch], 2
0x180016dc3  jz      short loc_180016DDA
0x180016dc5  mov     rcx, [rcx+10h]
0x180016dc9  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180016dd0  mov     edx, 0BBh
0x180016dd5  call    WPP_SF_
0x180016dda  mov     r14, [rbx+240h]
0x180016de1  mov     rcx, rbx
0x180016de4  mov     [rbx+240h], r12
0x180016deb  call    DavCreateUrlCacheEntry
0x180016df0  mov     edi, eax
0x180016df2  test    eax, eax
0x180016df4  jz      short loc_180016E34
0x180016df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dfd  lea     r14, WPP_GLOBAL_Control
0x180016e04  cmp     rcx, r14
0x180016e07  jz      loc_180017594
0x180016e0d  test    [rcx+1Ch], r15b
0x180016e11  jz      loc_180017594
0x180016e17  mov     edx, 0BCh
0x180016e1c  mov     r9d, eax
0x180016e1f  mov     rcx, [rcx+10h]
0x180016e23  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180016e2a  call    WPP_SF_d
0x180016e2f  jmp     loc_180017594
0x180016e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e3b  lea     rdi, WPP_GLOBAL_Control
0x180016e42  cmp     rcx, rdi
0x180016e45  jz      short loc_180016E93
0x180016e47  test    byte ptr [rcx+1Ch], 2
0x180016e4b  jz      short loc_180016E6C
0x180016e4d  mov     rcx, [rcx+10h]
0x180016e51  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180016e58  mov     edx, 0BDh
0x180016e5d  mov     r9, r14
0x180016e60  call    WPP_SF_S
0x180016e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e6c  cmp     rcx, rdi
0x180016e6f  jz      short loc_180016E93
0x180016e71  test    byte ptr [rcx+1Ch], 2
0x180016e75  jz      short loc_180016E93
0x180016e77  mov     r9, [rbx+240h]
0x180016e7e  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180016e85  mov     rcx, [rcx+10h]
0x180016e89  mov     edx, 0BEh
0x180016e8e  call    WPP_SF_S
0x180016e93  mov     rcx, [rbx+240h]; lpFileName
0x180016e9a  call    DavSetAclForEncryptedFile
0x180016e9f  mov     edi, eax
0x180016ea1  test    eax, eax
0x180016ea3  jz      short loc_180016EEF
0x180016ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eac  lea     r14, WPP_GLOBAL_Control
0x180016eb3  cmp     rcx, r14
0x180016eb6  jz      loc_180017594
0x180016ebc  test    [rcx+1Ch], r15b
0x180016ec0  jz      loc_180017594
0x180016ec6  mov     edx, 0BFh
0x180016ecb  mov     rax, [rbx+240h]
0x180016ed2  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180016ed9  mov     rcx, [rcx+10h]
0x180016edd  mov     r9d, edi
0x180016ee0  mov     [rsp+130h+AllocationSize], rax
0x180016ee5  call    WPP_SF_dS
0x180016eea  jmp     loc_180017594
0x180016eef  mov     rcx, [rbx+218h]; hObject
0x180016ef6  test    rcx, rcx
0x180016ef9  jz      short loc_180016F3F
0x180016efb  call    cs:__imp_CloseHandle
0x180016f01  test    eax, eax
0x180016f03  jnz     short loc_180016F38
0x180016f05  call    cs:__imp_GetLastError
0x180016f0b  mov     edi, eax
0x180016f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f14  lea     r14, WPP_GLOBAL_Control
0x180016f1b  cmp     rcx, r14
0x180016f1e  jz      loc_180017594
0x180016f24  test    [rcx+1Ch], r15b
0x180016f28  jz      loc_180017594
0x180016f2e  mov     edx, 0C0h
0x180016f33  jmp     loc_180016E1C
0x180016f38  mov     [rbx+218h], r12
0x180016f3f  mov     rdx, [rbx+48h]
0x180016f43  mov     rcx, rbx
0x180016f46  call    UMReflectorImpersonate
0x180016f4b  mov     edi, eax
0x180016f4d  test    eax, eax
0x180016f4f  jz      short loc_180016F7C
0x180016f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f58  lea     r14, WPP_GLOBAL_Control
0x180016f5f  cmp     rcx, r14
0x180016f62  jz      loc_180017594
0x180016f68  test    [rcx+1Ch], r15b
0x180016f6c  jz      loc_180017594
0x180016f72  mov     edx, 0C1h
0x180016f77  jmp     loc_180016E1C
0x180016f7c  mov     rdx, [rbx+240h]; LPCWSTR
0x180016f83  mov     rcx, r14; lpFileName
0x180016f86  mov     r13d, r15d
0x180016f89  call    DavRestoreEncryptedFile
0x180016f8e  mov     edi, eax
0x180016f90  test    r14, r14
0x180016f93  jz      short loc_180016F9E
0x180016f95  mov     rcx, r14; hMem
0x180016f98  call    cs:__imp_LocalFree
0x180016f9e  test    edi, edi
0x180016fa0  jz      short loc_180016FED
0x180016fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fa9  lea     r14, WPP_GLOBAL_Control
0x180016fb0  cmp     rcx, r14
0x180016fb3  jz      loc_180017594
0x180016fb9  test    [rcx+1Ch], r15b
0x180016fbd  jz      loc_180017594
0x180016fc3  mov     eax, [rsi+0C78h]
0x180016fc9  mov     edx, 0C2h
0x180016fce  mov     rcx, [rcx+10h]
0x180016fd2  mov     r9d, edi
0x180016fd5  mov     [rsp+130h+FileAttributes], eax
0x180016fd9  mov     eax, [rbx+2C0h]
0x180016fdf  mov     dword ptr [rsp+130h+AllocationSize], eax
0x180016fe3  call    WPP_SF_dDD
0x180016fe8  jmp     loc_180017594
0x180016fed  mov     rdx, [rbx+240h]
0x180016ff4  mov     ecx, 7FFFFFFEh
0x180016ff9  mov     eax, 104h
0x180016ffe  test    rcx, rcx
0x180017001  jz      short loc_180017021
0x180017003  movzx   r8d, word ptr [rdx]
0x180017007  test    r8w, r8w
0x18001700b  jz      short loc_180017021
0x18001700d  mov     [rsi], r8w
0x180017011  add     rdx, 2
0x180017015  add     rsi, 2
0x180017019  dec     rcx
0x18001701c  sub     rax, r13
0x18001701f  jnz     short loc_180016FFE
0x180017021  test    rax, rax
0x180017024  lea     rcx, [rsi-2]
0x180017028  lea     r14, [rbx+2C0h]
0x18001702f  cmovnz  rcx, rsi
0x180017033  mov     [rcx], r12w
0x180017037  mov     [rbx+0F34h], r13d
0x18001703e  jmp     loc_18001724D
0x180017043  mov     rcx, [rcx+218h]; hObject
0x18001704a  test    rcx, rcx
0x18001704d  jz      short loc_18001708C
0x18001704f  call    cs:__imp_CloseHandle
0x180017055  test    eax, eax
0x180017057  jnz     short loc_180017085
0x180017059  call    cs:__imp_GetLastError
0x18001705f  mov     edi, eax
0x180017061  mov     rcx, cs:WPP_GLOBAL_Control
0x180017068  cmp     rcx, r14
0x18001706b  jz      loc_180017594
0x180017071  test    [rcx+1Ch], r15b
0x180017075  jz      loc_180017594
0x18001707b  mov     edx, 0C3h
0x180017080  jmp     loc_180016E1C
0x180017085  mov     [rbx+218h], r12
0x18001708c  lea     r14, [rbx+2C0h]
0x180017093  test    [r14], edi
0x180017096  jz      loc_180017247
0x18001709c  test    [r14], r15b
0x18001709f  jz      short loc_1800170D9
0x1800170a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170a8  lea     r14, WPP_GLOBAL_Control
0x1800170af  cmp     rcx, r14
0x1800170b2  jz      short loc_1800170CF
0x1800170b4  test    byte ptr [rcx+1Ch], 2
0x1800170b8  jz      short loc_1800170CF
0x1800170ba  mov     rcx, [rcx+10h]
0x1800170be  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800170c5  mov     edx, 0C4h
0x1800170ca  call    WPP_SF_
0x1800170cf  mov     edi, 1779h
0x1800170d4  jmp     loc_180017594
0x1800170d9  mov     eax, [rbx+2C8h]
0x1800170df  mov     edi, r12d
0x1800170e2  mov     r15d, r12d
0x1800170e5  test    eax, 0FFFFFFFAh
0x1800170ea  jnz     loc_18001724D
0x1800170f0  cmp     eax, 1
0x1800170f3  jz      loc_18001724D
0x1800170f9  mov     rcx, [rbx+240h]; lpFileName
0x180017100  call    DavSetAclForEncryptedFile
0x180017105  mov     edi, eax
0x180017107  test    eax, eax
0x180017109  jz      short loc_180017136
0x18001710b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017112  lea     r14, WPP_GLOBAL_Control
0x180017119  cmp     rcx, r14
0x18001711c  jz      loc_180017594
0x180017122  test    byte ptr [rcx+1Ch], 1
0x180017126  jz      loc_180017594
0x18001712c  mov     edx, 0C5h
0x180017131  jmp     loc_180016ECB
0x180017136  mov     rdx, [rbx+48h]
0x18001713a  mov     rcx, rbx
0x18001713d  call    UMReflectorImpersonate
0x180017142  mov     edi, eax
0x180017144  test    eax, eax
0x180017146  jz      short loc_180017173
0x180017148  mov     rcx, cs:WPP_GLOBAL_Control
0x18001714f  lea     r14, WPP_GLOBAL_Control
0x180017156  cmp     rcx, r14
0x180017159  jz      loc_180017594
0x18001715f  test    byte ptr [rcx+1Ch], 1
0x180017163  jz      loc_180017594
0x180017169  mov     edx, 0C6h
0x18001716e  jmp     loc_180016E1C
0x180017173  mov     r13d, 1
0x180017179  mov     rcx, cs:WPP_GLOBAL_Control
0x180017180  lea     rax, WPP_GLOBAL_Control
0x180017187  cmp     rcx, rax
0x18001718a  jz      short loc_1800171AB
0x18001718c  test    byte ptr [rcx+1Ch], 2
0x180017190  jz      short loc_1800171AB
0x180017192  mov     rcx, [rcx+10h]
0x180017196  lea     r9, [rbp+57h+NtPathName]
0x18001719a  mov     edx, 0C7h
0x18001719f  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800171a6  call    WPP_SF_Z
0x1800171ab  mov     rcx, [rbx+240h]; lpFileName
0x1800171b2  call    cs:__imp_EncryptFileW
0x1800171b8  test    eax, eax
0x1800171ba  jz      short loc_180017214
0x1800171bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171c3  lea     rax, WPP_GLOBAL_Control
0x1800171ca  cmp     rcx, rax
0x1800171cd  jz      short loc_1800171EE
0x1800171cf  test    byte ptr [rcx+1Ch], 2
0x1800171d3  jz      short loc_1800171EE
0x1800171d5  mov     rcx, [rcx+10h]
0x1800171d9  lea     r9, [rbp+57h+NtPathName]
0x1800171dd  mov     edx, 0C8h
0x1800171e2  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800171e9  call    WPP_SF_Z
0x1800171ee  mov     eax, 4000h
0x1800171f3  mov     [rbx+0F34h], r13d
0x1800171fa  or      [rsi+0C78h], eax
0x180017200  btr     dword ptr [r14], 0Eh
0x180017205  or      [rsi+0C78h], eax
0x18001720b  mov     [rbx+0F34h], r13d
0x180017212  jmp     short loc_18001724D
0x180017214  call    cs:__imp_GetLastError
0x18001721a  mov     edi, eax
0x18001721c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017223  lea     r14, WPP_GLOBAL_Control
0x18001722a  cmp     rcx, r14
0x18001722d  jz      loc_180017594
0x180017233  test    [rcx+1Ch], r13b
0x180017237  jz      loc_180017594
0x18001723d  mov     edx, 0C9h
0x180017242  jmp     loc_180016E1C
0x180017247  mov     edi, r12d
0x18001724a  mov     r15d, r12d
0x18001724d  mov     eax, [rbx+2ACh]
0x180017253  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180017257  mov     rcx, [rbx+240h]; DosPathName
0x18001725e  xor     r9d, r9d; DirectoryInfo
0x180017261  mov     dword ptr [rbp+57h+var_78+4], eax
  ... truncated ...
```
