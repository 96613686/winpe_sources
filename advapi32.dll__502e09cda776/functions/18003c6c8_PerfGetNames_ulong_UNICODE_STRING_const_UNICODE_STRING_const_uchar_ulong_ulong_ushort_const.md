# PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)

- ea: `0x18003c6c8`
- end: `0x18003d241`
- name: `?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z`
- size: `2937`
- prototype: `int(unsigned int, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8 *, unsigned int *, unsigned int *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b280`
- `0x180063620`

## callees

- `0x180001120`
- `0x1800016f4`
- `0x180001978`
- `0x180002b34`
- `0x180002e40`
- `0x180004ec0`
- `0x180005a80`
- `0x1800350d4`
- `0x18003513c`
- `0x18003c6a0`
- `0x18003c6c8`
- `0x18003e250`
- `0x18003fb18`
- `0x18003fd04`
- `0x180063f10`
- `0x180064684`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x18003d20b`
- `ntdll!NtClose` at `0x18003d20b`
- `ntdll!NtOpenFile` at `0x18003cf39`
- `ntdll!NtOpenFile` at `0x18003cf39`
- `ntdll!NtQueryInformationFile` at `0x18003cfb5`
- `ntdll!NtQueryInformationFile` at `0x18003cfb5`
- `ntdll!NtCreateFile` at `0x18003ca94`
- `ntdll!NtCreateFile` at `0x18003ca94`
- `ntdll!NtWriteFile` at `0x18003cb5c`
- `ntdll!NtWriteFile` at `0x18003cb5c`
- `ntdll!NtFlushBuffersFile` at `0x18003cbea`
- `ntdll!NtFlushBuffersFile` at `0x18003cbea`
- `ntdll!NtSetInformationFile` at `0x18003ccfb`
- `ntdll!NtSetInformationFile` at `0x18003ccfb`
- `ntdll!NtReadFile` at `0x18003d0ae`
- `ntdll!NtReadFile` at `0x18003d0ae`
- `ntdll!RtlInitUnicodeString` at `0x18003c9b8`
- `ntdll!RtlInitUnicodeString` at `0x18003cede`
- `ntdll!RtlInitUnicodeString` at `0x18003c9b8`
- `ntdll!RtlInitUnicodeString` at `0x18003cede`
- `KERNEL32!LocalFree` at `0x18003caa6`
- `KERNEL32!LocalFree` at `0x18003ce53`
- `KERNEL32!LocalFree` at `0x18003cf4a`
- `KERNEL32!LocalFree` at `0x18003d1fa`
- `KERNEL32!LocalFree` at `0x18003caa6`
- `KERNEL32!LocalFree` at `0x18003ce53`
- `KERNEL32!LocalFree` at `0x18003cf4a`
- `KERNEL32!LocalFree` at `0x18003d1fa`

## pseudocode

```c
__int64 __fastcall PerfGetNames(
        int a1,
        const struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int16 *a7)
{
  int v8; // r8d
  int v9; // esi
  unsigned int v11; // eax
  unsigned __int16 *v12; // r15
  __int64 v13; // rdx
  WCHAR *v14; // rbx
  __int64 i; // rcx
  unsigned __int16 v16; // ax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbx
  int v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  NTSTATUS v24; // r14d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int LowPart; // ebx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  HANDLE v34; // rcx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  int v48; // eax
  int v49; // eax
  NTSTATUS v50; // esi
  __int64 Information_low; // rsi
  unsigned int v52; // r14d
  unsigned int LangIdFromSzLang; // eax
  unsigned int v54; // r15d
  NTSTATUS File; // eax
  _QWORD *v56; // rcx
  ULONG ShareAccess; // [rsp+30h] [rbp-D0h]
  int v58; // [rsp+60h] [rbp-A0h] BYREF
  bool v59; // [rsp+64h] [rbp-9Ch]
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER ByteOffset[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD FileInformation[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v67; // [rsp+E0h] [rbp-20h]
  int v68; // [rsp+E4h] [rbp-1Ch]
  _BYTE v69[26]; // [rsp+E8h] [rbp-18h] BYREF
  int v70; // [rsp+102h] [rbp+2h]
  __int16 v71; // [rsp+106h] [rbp+6h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  __int64 v73; // [rsp+118h] [rbp+18h]
  int v74; // [rsp+120h] [rbp+20h] BYREF
  __int64 v75; // [rsp+124h] [rbp+24h]
  int v76; // [rsp+12Ch] [rbp+2Ch]
  __int64 v77; // [rsp+130h] [rbp+30h]
  wchar_t v78; // [rsp+138h] [rbp+38h]

  v8 = a1 & 0x10000;
  v9 = 104;
  LODWORD(FileHandle) = a1 & 0x10000;
  v59 = (unsigned __int16)(a1 - 7) <= 1u;
  if ( (((_WORD)a1 - 5) & 0xFFFD) == 0 )
    v9 = 99;
  v58 = v9;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dZ(*((_QWORD *)WPP_GLOBAL_Control + 2), a1, v8, (unsigned __int16)a1, (__int64)a3);
    v8 = (int)FileHandle;
  }
  if ( a7 )
  {
    v11 = GetLangIdFromSzLang(a7) & 0x3FF;
    if ( v11 == 4 || v11 == 22 || (v12 = (unsigned __int16 *)PerflibCheckPerfFile(a7)) == 0 )
      v12 = a7;
  }
  else
  {
    v13 = v8 != 0 ? 11 : 7;
    v14 = &a3->Buffer[v13];
    for ( i = v8 != 0 ? 14 : 10; a3->Length >= (unsigned __int64)(2 * i); i = (unsigned int)(v13 + 3) )
    {
      if ( (unsigned __int16)(*v14 - 48) <= 9u )
        goto LABEL_16;
      ++v14;
      LODWORD(v13) = v13 + 1;
    }
    v14 = (WCHAR *)L"009";
LABEL_16:
    Perflib004Update(v14);
    v12 = (unsigned __int16 *)PerflibCheckPerfFile(v14);
    if ( !v12 )
      v12 = v14;
  }
  v78 = a01234567Dat[12];
  v77 = *(_QWORD *)L".dat";
  v74 = 3211312;
  v75 = 0x35003400330032LL;
  v76 = 3604534;
  if ( (unsigned __int16)(v12[3] - 48) > 9u )
  {
    v74 = 6619248;
    LODWORD(v75) = 6684786;
    WORD2(v75) = v9;
    HIWORD(v75) = *v12;
    LOWORD(v76) = v12[1];
    v16 = v12[2];
  }
  else
  {
    v74 = 7471216;
    LOWORD(v75) = 102;
    WORD1(v75) = v9;
    HIDWORD(v75) = *(_DWORD *)v12;
    LOWORD(v76) = v12[2];
    v16 = v12[3];
  }
  HIWORD(v76) = v16;
  v17 = (unsigned __int16 *)operator new(68);
  v18 = v17;
  if ( !v17 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids);
    return 3221225495LL;
  }
  if ( v59 )
  {
    if ( !a4 || !a5 || !*a5 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, a3);
      if ( (unsigned int)dword_1800AE6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
      {
        Src = a4;
        if ( a5 )
          v48 = *a5;
        else
          v48 = -1;
        v58 = v48;
        Handle = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v45,
          (unsigned int)byte_180099331,
          v46,
          v47,
          (__int64)&Handle,
          (__int64)&v58,
          (__int64)&Src);
      }
      goto LABEL_82;
    }
    v20 = StringCbPrintfW(v17, 0x44u, L"%.*ls\\%ls", 20, 0x180090D58LL, L"perfTMP.dat");
    if ( v20 < 0 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
          (unsigned int)v20);
LABEL_82:
      LocalFree(v18);
      return 3221225485LL;
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v18);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( (unsigned int)dword_1800AE6E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
    {
      v58 = *a5;
      Src = v18;
      Handle = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v21,
        (unsigned int)byte_180099369,
        v22,
        v23,
        (__int64)&Handle,
        (__int64)&v58,
        (__int64)&Src);
    }
    FileHandle = 0;
    IoStatusBlock = 0;
    v24 = NtCreateFile(&FileHandle, 0x40110000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 0, 0x20u, 0, 0);
    LocalFree(v18);
    if ( v24 < 0 )
    {
      if ( (unsigned int)dword_1800AE6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
      {
        v58 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)byte_18009924B,
          v26,
          v27,
          (__int64)&v58);
      }
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
          (unsigned int)v24);
      return (unsigned int)v24;
    }
    ShareAccess = *a5;
    ByteOffset[0].QuadPart = 0;
    LowPart = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, a4, ShareAccess, ByteOffset, 0);
    if ( LowPart >= 0 )
    {
      LowPart = NtFlushBuffersFile(FileHandle, &IoStatusBlock);
      if ( LowPart >= 0 )
      {
        FileInformation[0] = 3;
        v70 = 0;
        memset(v69, 0, sizeof(v69));
        v71 = 0;
        v38 = -1;
        FileInformation[1] = 0;
        do
          ++v38;
        while ( *((_WORD *)&v74 + v38) );
        *(_QWORD *)&v69[12] = v77;
        v67 = 2 * v38;
        v68 = v74;
        *(_QWORD *)v69 = v75;
        *(_DWORD *)&v69[8] = v76;
        *(_WORD *)&v69[20] = v78;
        LowPart = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x38u, (FILE_INFORMATION_CLASS)65);
        if ( LowPart >= 0 )
        {
          if ( (unsigned int)dword_1800AE6E8 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
          {
            v58 = LowPart;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v42,
              (unsigned int)&dword_18009921C,
              v43,
              v44,
              (__int64)&v58);
          }
          goto LABEL_53;
        }
        if ( (unsigned int)dword_1800AE6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
        {
          v58 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v39,
            (unsigned int)&byte_1800992F7,
            v40,
            v41,
            (__int64)&v58);
        }
        v32 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_53:
          v34 = FileHandle;
LABEL_138:
          NtClose(v34);
          return (unsigned int)LowPart;
        }
        v33 = 17;
      }
      else
      {
        if ( (unsigned int)dword_1800AE6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
        {
          v58 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)&word_1800992BE,
            v36,
            v37,
            (__int64)&v58);
        }
        v32 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_53;
        v33 = 16;
      }
    }
    else
    {
      if ( (unsigned int)dword_1800AE6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800AE6E8, 0x4000000000000000LL) )
      {
        v58 = LowPart;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)byte_180099285,
          v30,
          v31,
          (__int64)&v58);
      }
      v32 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_53;
      v33 = 15;
    }
    WPP_SF_d(v32[2], v33, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, (unsigned int)LowPart);
    goto LABEL_53;
  }
  v49 = StringCbPrintfW(v17, 0x44u, L"%.*ls\\%ls");
  if ( v49 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
        (unsigned int)&v74,
        v49);
    goto LABEL_82;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v18);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  Handle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_OWORD *)&ByteOffset[0].LowPart = 0;
  v50 = NtOpenFile(&Handle, 0x80100000, &ObjectAttributes, (PIO_STATUS_BLOCK)ByteOffset, 7u, 0x60u);
  LocalFree(v18);
  if ( v50 >= 0 )
  {
    v73 = 0;
    IoStatusBlock = 0;
    LowPart = NtQueryInformationFile(
                Handle,
                (PIO_STATUS_BLOCK)ByteOffset,
                &IoStatusBlock,
                0x18u,
                FileStandardInformation);
    if ( LowPart >= 0 && SHIDWORD(IoStatusBlock.Information) > 0 )
      LowPart = -2147483643;
    Information_low = (unsigned int)(LODWORD(IoStatusBlock.Information) - 2);
    if ( LODWORD(IoStatusBlock.Information) < 2 )
      Information_low = LODWORD(IoStatusBlock.Information);
    if ( LowPart >= 0 )
    {
      v52 = 0;
      Src = 0;
      if ( !(_DWORD)FileHandle )
      {
        LODWORD(FileHandle) = 0;
        LangIdFromSzLang = GetLangIdFromSzLang(v12);
        if ( PerflibciEnsurePerflibV2StringTable(
               LangIdFromSzLang,
               v58,
               (unsigned __int8 **)&Src,
               (unsigned int *)&FileHandle) )
        {
          LowPart = -1073741811;
        }
        else
        {
          v52 = (unsigned int)FileHandle;
          LowPart = 0;
        }
      }
      if ( a4 && a5 && (v54 = v52 + Information_low + 2, *a5 >= v54) )
      {
        File = NtReadFile(Handle, 0, 0, 0, (PIO_STATUS_BLOCK)ByteOffset, a4, Information_low, 0, 0);
        LowPart = File;
        if ( File < 0 )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
              (unsigned int)File);
        }
        else
        {
          LowPart = ByteOffset[0].LowPart;
          if ( (ByteOffset[0].LowPart & 0x80000000) == 0 )
          {
            if ( ByteOffset[1].QuadPart == (unsigned int)Information_low )
            {
              if ( Src && v52 )
                memcpy_0(&a4[Information_low], Src, v52);
              *(_WORD *)&a4[v52 + Information_low] = 0;
              *a5 = v54;
              if ( a6 )
                *a6 = v54;
            }
            else
            {
              LowPart = -1073741807;
            }
          }
        }
      }
      else
      {
        v56 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
            (unsigned int)LowPart);
          v56 = WPP_GLOBAL_Control;
        }
        if ( a6 )
        {
          *a6 = 0;
          v56 = WPP_GLOBAL_Control;
        }
        if ( a4 )
        {
          if ( (*((_DWORD *)v56 + 7) & 0x200) != 0 && *((_BYTE *)v56 + 25) >= 3u )
            WPP_SF_d(v56[2], 22, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, (unsigned int)LowPart);
          if ( a5 && a6 )
          {
            *a5 = v52 + Information_low + 2;
            *a6 = 0;
          }
          LowPart = -2147483643;
        }
        else
        {
          if ( a5 )
            *a5 = v52 + Information_low + 2;
          LowPart = 0;
        }
      }
      LocalFree(Src);
    }
    else if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
        (unsigned int)LowPart);
    }
    v34 = Handle;
    goto LABEL_138;
  }
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
      (unsigned int)v50);
  return (unsigned int)v50;
}

```

## disassembly

```asm
0x18003c6c8  mov     [rsp-8+arg_8], rbx
0x18003c6cd  push    rbp
0x18003c6ce  push    rsi
0x18003c6cf  push    rdi
0x18003c6d0  push    r12
0x18003c6d2  push    r13
0x18003c6d4  push    r14
0x18003c6d6  push    r15
0x18003c6d8  lea     rbp, [rsp-60h]
0x18003c6dd  sub     rsp, 160h
0x18003c6e4  mov     rax, cs:__security_cookie
0x18003c6eb  xor     rax, rsp
0x18003c6ee  mov     [rbp+90h+var_40], rax
0x18003c6f2  mov     rdi, [rbp+90h+arg_20]
0x18003c6f9  mov     r11d, 7
0x18003c6ff  mov     r13, [rbp+90h+arg_28]
0x18003c706  movzx   eax, cx
0x18003c709  mov     rbx, [rbp+90h+arg_30]
0x18003c710  sub     ax, r11w
0x18003c714  mov     r14, r8
0x18003c717  mov     edx, ecx
0x18003c719  mov     r8d, ecx
0x18003c71c  lea     r10d, [r11-6]
0x18003c720  and     r8d, 10000h
0x18003c727  lea     esi, [r11+61h]
0x18003c72b  cmp     ax, r10w
0x18003c72f  mov     dword ptr [rsp+190h+FileHandle], r8d
0x18003c734  lea     eax, [rcx-5]
0x18003c737  mov     r12, r9
0x18003c73a  mov     ecx, 0FFFDh
0x18003c73f  setbe   [rsp+190h+var_12C]
0x18003c744  test    cx, ax
0x18003c747  jnz     short loc_18003C74D
0x18003c749  lea     esi, [r11+5Ch]
0x18003c74d  mov     [rsp+190h+var_130], esi
0x18003c751  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c758  test    dword ptr [rcx+1Ch], 200h
0x18003c75f  jz      short loc_18003C788
0x18003c761  cmp     byte ptr [rcx+19h], 4
0x18003c765  jb      short loc_18003C788
0x18003c767  mov     rcx, [rcx+10h]
0x18003c76b  movzx   r9d, dx
0x18003c76f  mov     [rsp+190h+AllocationSize], r14
0x18003c774  call    WPP_SF_dZ
0x18003c779  mov     r8d, dword ptr [rsp+190h+FileHandle]
0x18003c77e  mov     r10d, 1
0x18003c784  lea     r11d, [r10+6]
0x18003c788  mov     r9d, 30h ; '0'
0x18003c78e  test    rbx, rbx
0x18003c791  jz      short loc_18003C7C3
0x18003c793  mov     rcx, rbx; unsigned __int16 *
0x18003c796  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18003c79b  and     eax, 3FFh
0x18003c7a0  cmp     eax, 4
0x18003c7a3  jz      short loc_18003C7BE
0x18003c7a5  cmp     eax, 16h
0x18003c7a8  jz      short loc_18003C7BE
0x18003c7aa  lea     rdx, [rbp+90h+var_50]
0x18003c7ae  mov     rcx, rbx; unsigned __int16 *
0x18003c7b1  call    PerflibCheckPerfFile
0x18003c7b6  mov     r15, rax
0x18003c7b9  test    rax, rax
0x18003c7bc  jnz     short loc_18003C827
0x18003c7be  mov     r15, rbx
0x18003c7c1  jmp     short loc_18003C827
0x18003c7c3  mov     eax, r8d
0x18003c7c6  movzx   r8d, word ptr [r14]
0x18003c7ca  neg     eax
0x18003c7cc  mov     rax, [r14+8]
0x18003c7d0  sbb     ecx, ecx
0x18003c7d2  and     ecx, 4
0x18003c7d5  add     ecx, r11d
0x18003c7d8  mov     edx, ecx
0x18003c7da  lea     rbx, [rax+rcx*2]
0x18003c7de  add     ecx, 3
0x18003c7e1  jmp     short loc_18003C7FA
0x18003c7e3  movzx   eax, word ptr [rbx]
0x18003c7e6  sub     ax, r9w
0x18003c7ea  cmp     ax, 9
0x18003c7ee  jbe     short loc_18003C809
0x18003c7f0  add     rbx, 2
0x18003c7f4  add     edx, r10d
0x18003c7f7  lea     ecx, [rdx+3]
0x18003c7fa  add     rcx, rcx
0x18003c7fd  cmp     r8, rcx
0x18003c800  jnb     short loc_18003C7E3
0x18003c802  lea     rbx, ?DefaultLangId@@3QBGB; "009"
0x18003c809  mov     rcx, rbx
0x18003c80c  call    Perflib004Update
0x18003c811  lea     rdx, [rbp+90h+var_50]
0x18003c815  mov     rcx, rbx; unsigned __int16 *
0x18003c818  call    PerflibCheckPerfFile
0x18003c81d  test    rax, rax
0x18003c820  mov     r15, rax
0x18003c823  cmovz   r15, rbx
0x18003c827  movzx   eax, word ptr cs:a01234567Dat+18h; ""
0x18003c82e  mov     ecx, 30h ; '0'
0x18003c833  movsd   xmm0, qword ptr cs:a01234567Dat+10h; ".dat"
0x18003c83b  mov     [rbp+90h+var_58], ax
0x18003c83f  movsd   [rbp+90h+var_60], xmm0
0x18003c844  mov     [rbp+90h+var_70], 310030h
0x18003c84b  mov     dword ptr [rbp+90h+var_6C], 330032h
0x18003c852  mov     dword ptr [rbp+90h+var_6C+4], 350034h
0x18003c859  mov     [rbp+90h+var_64], 370036h
0x18003c860  movzx   eax, word ptr [r15+6]
0x18003c865  sub     ax, cx
0x18003c868  cmp     ax, 9
0x18003c86c  ja      short loc_18003C8A1
0x18003c86e  mov     [rbp+90h+var_70], 720070h
0x18003c875  lea     eax, [rcx+36h]
0x18003c878  mov     word ptr [rbp+90h+var_6C], ax
0x18003c87c  mov     word ptr [rbp+90h+var_6C+2], si
0x18003c880  movzx   eax, word ptr [r15]
0x18003c884  mov     word ptr [rbp+90h+var_6C+4], ax
0x18003c888  movzx   eax, word ptr [r15+2]
0x18003c88d  mov     word ptr [rbp+90h+var_6C+6], ax
0x18003c891  movzx   eax, word ptr [r15+4]
0x18003c896  mov     word ptr [rbp+90h+var_64], ax
0x18003c89a  movzx   eax, word ptr [r15+6]
0x18003c89f  jmp     short loc_18003C8C9
0x18003c8a1  mov     [rbp+90h+var_70], 650070h
0x18003c8a8  mov     dword ptr [rbp+90h+var_6C], 660072h
0x18003c8af  mov     word ptr [rbp+90h+var_6C+4], si
0x18003c8b3  movzx   eax, word ptr [r15]
0x18003c8b7  mov     word ptr [rbp+90h+var_6C+6], ax
0x18003c8bb  movzx   eax, word ptr [r15+2]
0x18003c8c0  mov     word ptr [rbp+90h+var_64], ax
0x18003c8c4  movzx   eax, word ptr [r15+4]
0x18003c8c9  mov     ecx, 44h ; 'D'
0x18003c8ce  mov     word ptr [rbp+90h+var_64+2], ax
0x18003c8d2  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18003c8d7  xor     esi, esi
0x18003c8d9  mov     rbx, rax
0x18003c8dc  test    rax, rax
0x18003c8df  jnz     short loc_18003C914
0x18003c8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8e8  test    dword ptr [rcx+1Ch], 200h
0x18003c8ef  jz      short loc_18003C90A
0x18003c8f1  cmp     byte ptr [rcx+19h], 2
0x18003c8f5  jb      short loc_18003C90A
0x18003c8f7  mov     rcx, [rcx+10h]
0x18003c8fb  lea     edx, [rax+0Bh]
0x18003c8fe  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18003c905  call    WPP_SF_
0x18003c90a  mov     eax, 0C0000017h
0x18003c90f  jmp     loc_18003D219
0x18003c914  cmp     [rsp+190h+var_12C], sil
0x18003c919  jz      loc_18003CE69
0x18003c91f  xor     r15d, r15d
0x18003c922  test    r12, r12
0x18003c925  jz      loc_18003CDB8
0x18003c92b  test    rdi, rdi
0x18003c92e  jz      loc_18003CDB8
0x18003c934  cmp     [rdi], r15d
0x18003c937  jz      loc_18003CDB8
0x18003c93d  lea     rax, aPerftmpDat; "perfTMP.dat"
0x18003c944  mov     rcx, rbx; unsigned __int16 *
0x18003c947  mov     qword ptr [rsp+190h+FileAttributes], rax
0x18003c94c  lea     r9d, [r15+14h]
0x18003c950  mov     rax, cs:stru_1800755F0.Buffer
0x18003c957  lea     r8, aLsLs_1; "%.*ls\\%ls"
0x18003c95e  lea     edx, [r15+44h]; unsigned __int64
0x18003c962  mov     [rsp+190h+AllocationSize], rax
0x18003c967  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c96c  test    eax, eax
0x18003c96e  jns     short loc_18003C9AA
0x18003c970  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c977  test    dword ptr [rcx+1Ch], 200h
0x18003c97e  jz      loc_18003CE50
0x18003c984  cmp     byte ptr [rcx+19h], 2
0x18003c988  jb      loc_18003CE50
0x18003c98e  mov     rcx, [rcx+10h]
0x18003c992  lea     edx, [r15+0Dh]
0x18003c996  mov     r9d, eax
0x18003c999  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18003c9a0  call    WPP_SF_d
0x18003c9a5  jmp     loc_18003CE50
0x18003c9aa  xorps   xmm0, xmm0
0x18003c9ad  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18003c9b1  mov     rdx, rbx; SourceString
0x18003c9b4  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18003c9b8  call    cs:__imp_RtlInitUnicodeString
0x18003c9bf  nop     dword ptr [rax+rax+00h]
0x18003c9c4  lea     rax, [rbp+90h+DestinationString]
0x18003c9c8  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18003c9d0  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x18003c9d4  lea     rsi, dword_1800AE6E8
0x18003c9db  mov     eax, cs:dword_1800AE6E8
0x18003c9e1  xorps   xmm0, xmm0
0x18003c9e4  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 40h ; '@'
0x18003c9ec  mov     [rbp+90h+ObjectAttributes.RootDirectory], r15
0x18003c9f0  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c9f5  cmp     eax, 5
0x18003c9f8  jbe     short loc_18003CA4A
0x18003c9fa  mov     rdx, 4000000000000000h
0x18003ca04  mov     rcx, rsi
0x18003ca07  call    _tlgKeywordOn
0x18003ca0c  test    al, al
0x18003ca0e  jz      short loc_18003CA4A
0x18003ca10  mov     eax, [rdi]
0x18003ca12  lea     rdx, byte_180099369
0x18003ca19  mov     [rsp+190h+var_130], eax
0x18003ca1d  lea     rax, [rsp+190h+Src]
0x18003ca22  mov     qword ptr [rsp+190h+ShareAccess], rax
0x18003ca27  lea     rax, [rsp+190h+var_130]
0x18003ca2c  mov     qword ptr [rsp+190h+FileAttributes], rax
0x18003ca31  lea     rax, [rsp+190h+Handle]
0x18003ca36  mov     [rsp+190h+AllocationSize], rax
0x18003ca3b  mov     [rsp+190h+Src], rbx
0x18003ca40  mov     [rsp+190h+Handle], r14
0x18003ca45  call    ??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003ca4a  mov     [rsp+190h+EaLength], r15d; EaLength
0x18003ca4f  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x18003ca53  mov     [rsp+190h+EaBuffer], r15; EaBuffer
0x18003ca58  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18003ca5c  mov     [rsp+190h+CreateOptions], 20h ; ' '; CreateOptions
0x18003ca64  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x18003ca69  mov     [rsp+190h+CreateDisposition], r15d; CreateDisposition
0x18003ca6e  xorps   xmm0, xmm0
0x18003ca71  mov     [rsp+190h+ShareAccess], 1; ShareAccess
0x18003ca79  mov     edx, 40110000h; DesiredAccess
0x18003ca7e  mov     [rsp+190h+FileAttributes], 80h; FileAttributes
0x18003ca86  mov     [rsp+190h+AllocationSize], r15; AllocationSize
0x18003ca8b  mov     [rsp+190h+FileHandle], r15
0x18003ca90  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x18003ca94  call    cs:__imp_NtCreateFile
0x18003ca9b  nop     dword ptr [rax+rax+00h]
0x18003caa0  mov     rcx, rbx; hMem
0x18003caa3  mov     r14d, eax
0x18003caa6  call    cs:__imp_LocalFree
0x18003caad  nop     dword ptr [rax+rax+00h]
0x18003cab2  test    r14d, r14d
0x18003cab5  jns     short loc_18003CB29
0x18003cab7  mov     edx, cs:dword_1800AE6E8
0x18003cabd  cmp     edx, 2
0x18003cac0  jbe     short loc_18003CAF3
0x18003cac2  mov     rdx, 4000000000000000h
0x18003cacc  mov     rcx, rsi
0x18003cacf  call    _tlgKeywordOn
0x18003cad4  test    al, al
0x18003cad6  jz      short loc_18003CAF3
0x18003cad8  lea     rax, [rsp+190h+var_130]
0x18003cadd  mov     [rsp+190h+var_130], r14d
0x18003cae2  lea     rdx, byte_18009924B
0x18003cae9  mov     [rsp+190h+AllocationSize], rax
0x18003caee  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003caf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cafa  test    dword ptr [rcx+1Ch], 200h
0x18003cb01  jz      short loc_18003CB21
0x18003cb03  cmp     byte ptr [rcx+19h], 2
0x18003cb07  jb      short loc_18003CB21
0x18003cb09  mov     rcx, [rcx+10h]
0x18003cb0d  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18003cb14  mov     edx, 0Eh
0x18003cb19  mov     r9d, r14d
0x18003cb1c  call    WPP_SF_d
0x18003cb21  mov     eax, r14d
0x18003cb24  jmp     loc_18003D219
0x18003cb29  mov     rcx, [rsp+190h+FileHandle]; FileHandle
0x18003cb2e  lea     rax, [rbp+90h+ByteOffset]
0x18003cb32  mov     qword ptr [rsp+190h+CreateOptions], r15; Key
0x18003cb37  xor     r9d, r9d; ApcContext
0x18003cb3a  mov     qword ptr [rsp+190h+CreateDisposition], rax; ByteOffset
0x18003cb3f  xor     r8d, r8d; ApcRoutine
0x18003cb42  mov     eax, [rdi]
0x18003cb44  xor     edx, edx; Event
0x18003cb46  mov     [rsp+190h+ShareAccess], eax; Length
0x18003cb4a  lea     rax, [rbp+90h+IoStatusBlock]
0x18003cb4e  mov     qword ptr [rsp+190h+FileAttributes], r12; Buffer
0x18003cb53  mov     [rsp+190h+AllocationSize], rax; IoStatusBlock
0x18003cb58  mov     qword ptr [rbp+90h+ByteOffset], r15
0x18003cb5c  call    cs:__imp_NtWriteFile
0x18003cb63  nop     dword ptr [rax+rax+00h]
0x18003cb68  mov     ebx, eax
0x18003cb6a  test    eax, eax
0x18003cb6c  jns     short loc_18003CBE1
0x18003cb6e  mov     ecx, cs:dword_1800AE6E8
0x18003cb74  cmp     ecx, 2
0x18003cb77  jbe     short loc_18003CBA9
0x18003cb79  mov     rdx, 4000000000000000h
0x18003cb83  mov     rcx, rsi
0x18003cb86  call    _tlgKeywordOn
0x18003cb8b  test    al, al
0x18003cb8d  jz      short loc_18003CBA9
0x18003cb8f  lea     rax, [rsp+190h+var_130]
0x18003cb94  mov     [rsp+190h+var_130], ebx
0x18003cb98  lea     rdx, byte_180099285
0x18003cb9f  mov     [rsp+190h+AllocationSize], rax
0x18003cba4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003cba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbb0  test    dword ptr [rcx+1Ch], 200h
0x18003cbb7  jz      short loc_18003CBD7
0x18003cbb9  cmp     byte ptr [rcx+19h], 2
0x18003cbbd  jb      short loc_18003CBD7
0x18003cbbf  mov     edx, 0Fh
0x18003cbc4  mov     rcx, [rcx+10h]
0x18003cbc8  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18003cbcf  mov     r9d, ebx
0x18003cbd2  call    WPP_SF_d
0x18003cbd7  mov     rcx, [rsp+190h+FileHandle]
  ... truncated ...
```
