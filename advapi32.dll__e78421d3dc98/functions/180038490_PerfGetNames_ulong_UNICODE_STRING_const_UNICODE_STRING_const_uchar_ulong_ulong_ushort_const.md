# PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)

- ea: `0x180038490`
- end: `0x180038fb4`
- name: `?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z`
- size: `2852`
- prototype: `int(unsigned int, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8 *, unsigned int *, unsigned int *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800288a0`
- `0x180057560`

## callees

- `0x180001118`
- `0x180004990`
- `0x180005510`
- `0x180017100`
- `0x180017144`
- `0x18002b984`
- `0x18002bbd8`
- `0x180031970`
- `0x1800319d4`
- `0x18003846c`
- `0x180038490`
- `0x180039e5c`
- `0x18003b57c`
- `0x18003b748`
- `0x180057dfc`
- `0x180058508`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x180038f85`
- `ntdll!NtClose` at `0x180038f85`
- `ntdll!NtOpenFile` at `0x180038cd1`
- `ntdll!NtOpenFile` at `0x180038cd1`
- `ntdll!NtQueryInformationFile` at `0x180038d41`
- `ntdll!NtQueryInformationFile` at `0x180038d41`
- `ntdll!NtCreateFile` at `0x180038856`
- `ntdll!NtCreateFile` at `0x180038856`
- `ntdll!NtWriteFile` at `0x180038912`
- `ntdll!NtWriteFile` at `0x180038912`
- `ntdll!NtFlushBuffersFile` at `0x18003899a`
- `ntdll!NtFlushBuffersFile` at `0x18003899a`
- `ntdll!NtSetInformationFile` at `0x180038aa5`
- `ntdll!NtSetInformationFile` at `0x180038aa5`
- `ntdll!NtReadFile` at `0x180038e34`
- `ntdll!NtReadFile` at `0x180038e34`
- `ntdll!RtlInitUnicodeString` at `0x180038780`
- `ntdll!RtlInitUnicodeString` at `0x180038c7c`
- `ntdll!RtlInitUnicodeString` at `0x180038780`
- `ntdll!RtlInitUnicodeString` at `0x180038c7c`
- `KERNEL32!LocalFree` at `0x180038862`
- `KERNEL32!LocalFree` at `0x180038bf7`
- `KERNEL32!LocalFree` at `0x180038cdc`
- `KERNEL32!LocalFree` at `0x180038f7a`
- `KERNEL32!LocalFree` at `0x180038862`
- `KERNEL32!LocalFree` at `0x180038bf7`
- `KERNEL32!LocalFree` at `0x180038cdc`
- `KERNEL32!LocalFree` at `0x180038f7a`

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
      if ( (unsigned int)dword_18009F6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
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
          (unsigned int)byte_18008B055,
          v46,
          v47,
          (__int64)&Handle,
          (__int64)&v58,
          (__int64)&Src);
      }
      goto LABEL_82;
    }
    v20 = StringCbPrintfW(v17, 0x44u, L"%.*ls\\%ls", 20, 0x180082BD0LL, L"perfTMP.dat");
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
    if ( (unsigned int)dword_18009F6E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
    {
      v58 = *a5;
      Src = v18;
      Handle = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v21,
        (unsigned int)&word_18008AFA6,
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
      if ( (unsigned int)dword_18009F6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
      {
        v58 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)word_18008AFE2,
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
          if ( (unsigned int)dword_18009F6E8 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
          {
            v58 = LowPart;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v42,
              (unsigned int)byte_18008AF3D,
              v43,
              v44,
              (__int64)&v58);
          }
          goto LABEL_53;
        }
        if ( (unsigned int)dword_18009F6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
        {
          v58 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v39,
            (unsigned int)&dword_18008AF6C,
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
        if ( (unsigned int)dword_18009F6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
        {
          v58 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)&dword_18008AF04,
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
      if ( (unsigned int)dword_18009F6E8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18009F6E8, 0x4000000000000000LL) )
      {
        v58 = LowPart;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)&dword_18008B01C,
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
0x180038490  mov     [rsp-8+arg_8], rbx
0x180038495  push    rbp
0x180038496  push    rsi
0x180038497  push    rdi
0x180038498  push    r12
0x18003849a  push    r13
0x18003849c  push    r14
0x18003849e  push    r15
0x1800384a0  lea     rbp, [rsp-60h]
0x1800384a5  sub     rsp, 160h
0x1800384ac  mov     rax, cs:__security_cookie
0x1800384b3  xor     rax, rsp
0x1800384b6  mov     [rbp+90h+var_40], rax
0x1800384ba  mov     rdi, [rbp+90h+arg_20]
0x1800384c1  mov     r11d, 7
0x1800384c7  mov     r13, [rbp+90h+arg_28]
0x1800384ce  movzx   eax, cx
0x1800384d1  mov     rbx, [rbp+90h+arg_30]
0x1800384d8  sub     ax, r11w
0x1800384dc  mov     r14, r8
0x1800384df  mov     edx, ecx
0x1800384e1  mov     r8d, ecx
0x1800384e4  lea     r10d, [r11-6]
0x1800384e8  and     r8d, 10000h
0x1800384ef  lea     esi, [r11+61h]
0x1800384f3  cmp     ax, r10w
0x1800384f7  mov     dword ptr [rsp+190h+FileHandle], r8d
0x1800384fc  lea     eax, [rcx-5]
0x1800384ff  mov     r12, r9
0x180038502  mov     ecx, 0FFFDh
0x180038507  setbe   [rsp+190h+var_12C]
0x18003850c  test    cx, ax
0x18003850f  jnz     short loc_180038515
0x180038511  lea     esi, [r11+5Ch]
0x180038515  mov     [rsp+190h+var_130], esi
0x180038519  mov     rcx, cs:WPP_GLOBAL_Control
0x180038520  test    dword ptr [rcx+1Ch], 200h
0x180038527  jz      short loc_180038550
0x180038529  cmp     byte ptr [rcx+19h], 4
0x18003852d  jb      short loc_180038550
0x18003852f  mov     rcx, [rcx+10h]
0x180038533  movzx   r9d, dx
0x180038537  mov     [rsp+190h+AllocationSize], r14
0x18003853c  call    WPP_SF_dZ
0x180038541  mov     r8d, dword ptr [rsp+190h+FileHandle]
0x180038546  mov     r10d, 1
0x18003854c  lea     r11d, [r10+6]
0x180038550  mov     r9d, 30h ; '0'
0x180038556  test    rbx, rbx
0x180038559  jz      short loc_18003858B
0x18003855b  mov     rcx, rbx; unsigned __int16 *
0x18003855e  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180038563  and     eax, 3FFh
0x180038568  cmp     eax, 4
0x18003856b  jz      short loc_180038586
0x18003856d  cmp     eax, 16h
0x180038570  jz      short loc_180038586
0x180038572  lea     rdx, [rbp+90h+var_50]
0x180038576  mov     rcx, rbx; unsigned __int16 *
0x180038579  call    PerflibCheckPerfFile
0x18003857e  mov     r15, rax
0x180038581  test    rax, rax
0x180038584  jnz     short loc_1800385EF
0x180038586  mov     r15, rbx
0x180038589  jmp     short loc_1800385EF
0x18003858b  mov     eax, r8d
0x18003858e  movzx   r8d, word ptr [r14]
0x180038592  neg     eax
0x180038594  mov     rax, [r14+8]
0x180038598  sbb     ecx, ecx
0x18003859a  and     ecx, 4
0x18003859d  add     ecx, r11d
0x1800385a0  mov     edx, ecx
0x1800385a2  lea     rbx, [rax+rcx*2]
0x1800385a6  add     ecx, 3
0x1800385a9  jmp     short loc_1800385C2
0x1800385ab  movzx   eax, word ptr [rbx]
0x1800385ae  sub     ax, r9w
0x1800385b2  cmp     ax, 9
0x1800385b6  jbe     short loc_1800385D1
0x1800385b8  add     rbx, 2
0x1800385bc  add     edx, r10d
0x1800385bf  lea     ecx, [rdx+3]
0x1800385c2  add     rcx, rcx
0x1800385c5  cmp     r8, rcx
0x1800385c8  jnb     short loc_1800385AB
0x1800385ca  lea     rbx, ?DefaultLangId@@3QBGB; "009"
0x1800385d1  mov     rcx, rbx
0x1800385d4  call    Perflib004Update
0x1800385d9  lea     rdx, [rbp+90h+var_50]
0x1800385dd  mov     rcx, rbx; unsigned __int16 *
0x1800385e0  call    PerflibCheckPerfFile
0x1800385e5  test    rax, rax
0x1800385e8  mov     r15, rax
0x1800385eb  cmovz   r15, rbx
0x1800385ef  movzx   eax, word ptr cs:a01234567Dat+18h; ""
0x1800385f6  mov     ecx, 30h ; '0'
0x1800385fb  movsd   xmm0, qword ptr cs:a01234567Dat+10h; ".dat"
0x180038603  mov     [rbp+90h+var_58], ax
0x180038607  movsd   [rbp+90h+var_60], xmm0
0x18003860c  mov     [rbp+90h+var_70], 310030h
0x180038613  mov     dword ptr [rbp+90h+var_6C], 330032h
0x18003861a  mov     dword ptr [rbp+90h+var_6C+4], 350034h
0x180038621  mov     [rbp+90h+var_64], 370036h
0x180038628  movzx   eax, word ptr [r15+6]
0x18003862d  sub     ax, cx
0x180038630  cmp     ax, 9
0x180038634  ja      short loc_180038669
0x180038636  mov     [rbp+90h+var_70], 720070h
0x18003863d  lea     eax, [rcx+36h]
0x180038640  mov     word ptr [rbp+90h+var_6C], ax
0x180038644  mov     word ptr [rbp+90h+var_6C+2], si
0x180038648  movzx   eax, word ptr [r15]
0x18003864c  mov     word ptr [rbp+90h+var_6C+4], ax
0x180038650  movzx   eax, word ptr [r15+2]
0x180038655  mov     word ptr [rbp+90h+var_6C+6], ax
0x180038659  movzx   eax, word ptr [r15+4]
0x18003865e  mov     word ptr [rbp+90h+var_64], ax
0x180038662  movzx   eax, word ptr [r15+6]
0x180038667  jmp     short loc_180038691
0x180038669  mov     [rbp+90h+var_70], 650070h
0x180038670  mov     dword ptr [rbp+90h+var_6C], 660072h
0x180038677  mov     word ptr [rbp+90h+var_6C+4], si
0x18003867b  movzx   eax, word ptr [r15]
0x18003867f  mov     word ptr [rbp+90h+var_6C+6], ax
0x180038683  movzx   eax, word ptr [r15+2]
0x180038688  mov     word ptr [rbp+90h+var_64], ax
0x18003868c  movzx   eax, word ptr [r15+4]
0x180038691  mov     ecx, 44h ; 'D'
0x180038696  mov     word ptr [rbp+90h+var_64+2], ax
0x18003869a  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18003869f  xor     esi, esi
0x1800386a1  mov     rbx, rax
0x1800386a4  test    rax, rax
0x1800386a7  jnz     short loc_1800386DC
0x1800386a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386b0  test    dword ptr [rcx+1Ch], 200h
0x1800386b7  jz      short loc_1800386D2
0x1800386b9  cmp     byte ptr [rcx+19h], 2
0x1800386bd  jb      short loc_1800386D2
0x1800386bf  mov     rcx, [rcx+10h]
0x1800386c3  lea     edx, [rax+0Bh]
0x1800386c6  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x1800386cd  call    WPP_SF_
0x1800386d2  mov     eax, 0C0000017h
0x1800386d7  jmp     loc_180038F8D
0x1800386dc  cmp     [rsp+190h+var_12C], sil
0x1800386e1  jz      loc_180038C07
0x1800386e7  xor     r15d, r15d
0x1800386ea  test    r12, r12
0x1800386ed  jz      loc_180038B5C
0x1800386f3  test    rdi, rdi
0x1800386f6  jz      loc_180038B5C
0x1800386fc  cmp     [rdi], r15d
0x1800386ff  jz      loc_180038B5C
0x180038705  lea     rax, aPerftmpDat; "perfTMP.dat"
0x18003870c  mov     rcx, rbx; unsigned __int16 *
0x18003870f  mov     qword ptr [rsp+190h+FileAttributes], rax
0x180038714  lea     r9d, [r15+14h]
0x180038718  mov     rax, cs:stru_180067610.Buffer
0x18003871f  lea     r8, aLsLs_1; "%.*ls\\%ls"
0x180038726  lea     edx, [r15+44h]; unsigned __int64
0x18003872a  mov     [rsp+190h+AllocationSize], rax
0x18003872f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038734  test    eax, eax
0x180038736  jns     short loc_180038772
0x180038738  mov     rcx, cs:WPP_GLOBAL_Control
0x18003873f  test    dword ptr [rcx+1Ch], 200h
0x180038746  jz      loc_180038BF4
0x18003874c  cmp     byte ptr [rcx+19h], 2
0x180038750  jb      loc_180038BF4
0x180038756  mov     rcx, [rcx+10h]
0x18003875a  lea     edx, [r15+0Dh]
0x18003875e  mov     r9d, eax
0x180038761  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x180038768  call    WPP_SF_d
0x18003876d  jmp     loc_180038BF4
0x180038772  xorps   xmm0, xmm0
0x180038775  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x180038779  mov     rdx, rbx; SourceString
0x18003877c  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180038780  call    cs:__imp_RtlInitUnicodeString
0x180038786  lea     rax, [rbp+90h+DestinationString]
0x18003878a  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x180038792  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x180038796  lea     rsi, dword_18009F6E8
0x18003879d  mov     eax, cs:dword_18009F6E8
0x1800387a3  xorps   xmm0, xmm0
0x1800387a6  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 40h ; '@'
0x1800387ae  mov     [rbp+90h+ObjectAttributes.RootDirectory], r15
0x1800387b2  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800387b7  cmp     eax, 5
0x1800387ba  jbe     short loc_18003880C
0x1800387bc  mov     rdx, 4000000000000000h
0x1800387c6  mov     rcx, rsi
0x1800387c9  call    _tlgKeywordOn
0x1800387ce  test    al, al
0x1800387d0  jz      short loc_18003880C
0x1800387d2  mov     eax, [rdi]
0x1800387d4  lea     rdx, word_18008AFA6
0x1800387db  mov     [rsp+190h+var_130], eax
0x1800387df  lea     rax, [rsp+190h+Src]
0x1800387e4  mov     qword ptr [rsp+190h+ShareAccess], rax
0x1800387e9  lea     rax, [rsp+190h+var_130]
0x1800387ee  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1800387f3  lea     rax, [rsp+190h+Handle]
0x1800387f8  mov     [rsp+190h+AllocationSize], rax
0x1800387fd  mov     [rsp+190h+Src], rbx
0x180038802  mov     [rsp+190h+Handle], r14
0x180038807  call    ??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003880c  mov     [rsp+190h+EaLength], r15d; EaLength
0x180038811  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x180038815  mov     [rsp+190h+EaBuffer], r15; EaBuffer
0x18003881a  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18003881e  mov     [rsp+190h+CreateOptions], 20h ; ' '; CreateOptions
0x180038826  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x18003882b  mov     [rsp+190h+CreateDisposition], r15d; CreateDisposition
0x180038830  xorps   xmm0, xmm0
0x180038833  mov     [rsp+190h+ShareAccess], 1; ShareAccess
0x18003883b  mov     edx, 40110000h; DesiredAccess
0x180038840  mov     [rsp+190h+FileAttributes], 80h; FileAttributes
0x180038848  mov     [rsp+190h+AllocationSize], r15; AllocationSize
0x18003884d  mov     [rsp+190h+FileHandle], r15
0x180038852  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x180038856  call    cs:__imp_NtCreateFile
0x18003885c  mov     rcx, rbx; hMem
0x18003885f  mov     r14d, eax
0x180038862  call    cs:__imp_LocalFree
0x180038868  test    r14d, r14d
0x18003886b  jns     short loc_1800388DF
0x18003886d  mov     edx, cs:dword_18009F6E8
0x180038873  cmp     edx, 2
0x180038876  jbe     short loc_1800388A9
0x180038878  mov     rdx, 4000000000000000h
0x180038882  mov     rcx, rsi
0x180038885  call    _tlgKeywordOn
0x18003888a  test    al, al
0x18003888c  jz      short loc_1800388A9
0x18003888e  lea     rax, [rsp+190h+var_130]
0x180038893  mov     [rsp+190h+var_130], r14d
0x180038898  lea     rdx, word_18008AFE2
0x18003889f  mov     [rsp+190h+AllocationSize], rax
0x1800388a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800388a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800388b0  test    dword ptr [rcx+1Ch], 200h
0x1800388b7  jz      short loc_1800388D7
0x1800388b9  cmp     byte ptr [rcx+19h], 2
0x1800388bd  jb      short loc_1800388D7
0x1800388bf  mov     rcx, [rcx+10h]
0x1800388c3  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x1800388ca  mov     edx, 0Eh
0x1800388cf  mov     r9d, r14d
0x1800388d2  call    WPP_SF_d
0x1800388d7  mov     eax, r14d
0x1800388da  jmp     loc_180038F8D
0x1800388df  mov     rcx, [rsp+190h+FileHandle]; FileHandle
0x1800388e4  lea     rax, [rbp+90h+ByteOffset]
0x1800388e8  mov     qword ptr [rsp+190h+CreateOptions], r15; Key
0x1800388ed  xor     r9d, r9d; ApcContext
0x1800388f0  mov     qword ptr [rsp+190h+CreateDisposition], rax; ByteOffset
0x1800388f5  xor     r8d, r8d; ApcRoutine
0x1800388f8  mov     eax, [rdi]
0x1800388fa  xor     edx, edx; Event
0x1800388fc  mov     [rsp+190h+ShareAccess], eax; Length
0x180038900  lea     rax, [rbp+90h+IoStatusBlock]
0x180038904  mov     qword ptr [rsp+190h+FileAttributes], r12; Buffer
0x180038909  mov     [rsp+190h+AllocationSize], rax; IoStatusBlock
0x18003890e  mov     qword ptr [rbp+90h+ByteOffset], r15
0x180038912  call    cs:__imp_NtWriteFile
0x180038918  mov     ebx, eax
0x18003891a  test    eax, eax
0x18003891c  jns     short loc_180038991
0x18003891e  mov     ecx, cs:dword_18009F6E8
0x180038924  cmp     ecx, 2
0x180038927  jbe     short loc_180038959
0x180038929  mov     rdx, 4000000000000000h
0x180038933  mov     rcx, rsi
0x180038936  call    _tlgKeywordOn
0x18003893b  test    al, al
0x18003893d  jz      short loc_180038959
0x18003893f  lea     rax, [rsp+190h+var_130]
0x180038944  mov     [rsp+190h+var_130], ebx
0x180038948  lea     rdx, dword_18008B01C
0x18003894f  mov     [rsp+190h+AllocationSize], rax
0x180038954  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038959  mov     rcx, cs:WPP_GLOBAL_Control
0x180038960  test    dword ptr [rcx+1Ch], 200h
0x180038967  jz      short loc_180038987
0x180038969  cmp     byte ptr [rcx+19h], 2
0x18003896d  jb      short loc_180038987
0x18003896f  mov     edx, 0Fh
0x180038974  mov     rcx, [rcx+10h]
0x180038978  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18003897f  mov     r9d, ebx
0x180038982  call    WPP_SF_d
0x180038987  mov     rcx, [rsp+190h+FileHandle]
0x18003898c  jmp     loc_180038F85
0x180038991  mov     rcx, [rsp+190h+FileHandle]; FileHandle
0x180038996  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x18003899a  call    cs:__imp_NtFlushBuffersFile
  ... truncated ...
```
