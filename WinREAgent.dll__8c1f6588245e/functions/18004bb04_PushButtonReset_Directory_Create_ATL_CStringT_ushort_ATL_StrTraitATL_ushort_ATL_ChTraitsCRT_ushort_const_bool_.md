# PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18004bb04`
- end: `0x18004c02c`
- name: `?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z`
- size: `1320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009c7c`
- `0x180015740`
- `0x1800173a0`
- `0x180019904`
- `0x180019b84`
- `0x18001eecc`
- `0x18001f4e0`
- `0x1800204b8`
- `0x180021590`
- `0x180027c6c`
- `0x18002a4d0`
- `0x1800308cc`
- `0x18004aabc`
- `0x18004bb04`
- `0x18004c034`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x1800074b8`
- `0x1800089d0`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002476c`
- `0x180033b18`
- `0x180037344`
- `0x18004bb04`
- `0x18004d1fc`
- `0x18004d404`
- `0x18004d7a0`
- `0x18004ebec`
- `0x18004fa50`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004bebf`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004bebf`
- `KERNEL32!GetLastError` at `0x18004becd`
- `KERNEL32!GetLastError` at `0x18004bf11`
- `KERNEL32!GetLastError` at `0x18004bf90`
- `KERNEL32!GetLastError` at `0x18004becd`
- `KERNEL32!GetLastError` at `0x18004bf11`
- `KERNEL32!GetLastError` at `0x18004bf90`
- `KERNEL32!CreateDirectoryW` at `0x18004bf67`
- `KERNEL32!CreateDirectoryW` at `0x18004bf84`
- `KERNEL32!CreateDirectoryW` at `0x18004bf67`
- `KERNEL32!CreateDirectoryW` at `0x18004bf84`

## string_xrefs

- `0x18004bfbf`: `Failed to create [%s]`
- `0x18004bb50`: `Failed to get canonical form for path [%s]`
- `0x18004bb6b`: `PushButtonReset::Directory::Create`
- `0x18004bd83`: `PushButtonReset::Directory::Create`
- `0x18004bdcf`: `PushButtonReset::Directory::Create`
- `0x18004be72`: `PushButtonReset::Directory::Create`
- `0x18004bf01`: `PushButtonReset::Directory::Create`
- `0x18004bfda`: `PushButtonReset::Directory::Create`
- `0x18004bdb4`: `Invalid volume root directory [%s]`
- `0x18004be18`: `Failed to construct parent path for [%s]`
- `0x18004be57`: `Failed to create parent directory [%s] for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PushButtonReset::Directory::Create(_QWORD *a1, char a2, LPCWSTR *a3)
{
  char v4; // r14
  signed int Canonical; // ebx
  ATL::CStringData *v7; // rcx
  __int64 v8; // rdi
  const WCHAR *v9; // r15
  int v10; // edx
  const WCHAR *v11; // rbx
  int *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  int *v16; // rdi
  __int64 v17; // rbx
  ATL::CStringData *v18; // r14
  int *v19; // rsi
  __int64 v20; // rbx
  PSECURITY_DESCRIPTOR *v21; // rax
  LPCWSTR v22; // rbx
  signed int LastError; // eax
  signed int v24; // eax
  BOOL DirectoryW; // esi
  signed int v26; // eax
  LPCWSTR lpPathName; // [rsp+40h] [rbp-40h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  __int64 v30; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-28h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-18h] BYREF
  __int64 SecurityDescriptorSize; // [rsp+D8h] [rbp+58h] BYREF

  v4 = a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v30);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &v30);
  if ( Canonical >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpPathName);
    v8 = v30;
    v9 = (const WCHAR *)(v30 - 24);
    v10 = *(_DWORD *)(v30 - 24 + 8);
    if ( v10 > 0 && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v30, (unsigned int)(v10 - 1)) == 92 )
    {
      v11 = lpPathName;
      v12 = (int *)(lpPathName - 12);
      if ( v9 != lpPathName - 12 )
      {
        if ( v12[4] >= 0 && *(_QWORD *)v9 == *(_QWORD *)v12 )
        {
          v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v9);
          ATL::CStringData::Release((ATL::CStringData *)v12);
          v11 = (const WCHAR *)(v13 + 24);
          lpPathName = v11;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, v8, *(unsigned int *)(v8 - 16));
          v11 = lpPathName;
        }
      }
    }
    else
    {
      v14 = *(_QWORD *)ATL::operator+(&SecurityDescriptorSize, &v30, L"\\");
      v15 = (_QWORD *)(v14 - 24);
      v11 = lpPathName;
      v16 = (int *)(lpPathName - 12);
      if ( (LPCWSTR)(v14 - 24) != lpPathName - 12 )
      {
        if ( v16[4] >= 0 && *v15 == *(_QWORD *)v16 )
        {
          v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15);
          ATL::CStringData::Release((ATL::CStringData *)v16);
          v11 = (const WCHAR *)(v17 + 24);
          lpPathName = v11;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, v14, *(unsigned int *)(v14 - 16));
          v11 = lpPathName;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(SecurityDescriptorSize - 24));
    }
    if ( *((int *)v11 - 4) >= 260
      && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&lpPathName, 0) != 92
      || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&lpPathName, 1) != 92
      || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&lpPathName, 2) != 63
      || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&lpPathName, 3) != 92 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&SecurityDescriptorSize);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &SecurityDescriptorSize,
        L"\\\\?\\%s",
        v11);
      v18 = (ATL::CStringData *)(SecurityDescriptorSize - 24);
      v19 = (int *)(v11 - 12);
      if ( (const WCHAR *)(SecurityDescriptorSize - 24) != v11 - 12 )
      {
        if ( v19[4] >= 0 && *(_QWORD *)v18 == *(_QWORD *)v19 )
        {
          v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(SecurityDescriptorSize - 24);
          ATL::CStringData::Release((ATL::CStringData *)v19);
          lpPathName = (LPCWSTR)(v20 + 24);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            &lpPathName,
            SecurityDescriptorSize,
            *(unsigned int *)(SecurityDescriptorSize - 16));
        }
      }
      ATL::CStringData::Release(v18);
      v4 = a2;
    }
    LOBYTE(SecurityDescriptorSize) = 0;
    Canonical = PushButtonReset::Path::IsRoot(&lpPathName, &SecurityDescriptorSize);
    if ( Canonical < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Canonical,
        "PushButtonReset::Directory::Create",
        "base\\reset\\util\\src\\filesystem.cpp",
        2226,
        L"Failed to check whether [%s] is the root of its volume",
        lpPathName);
LABEL_54:
      ATL::CStringData::Release((ATL::CStringData *)(lpPathName - 12));
      v7 = (ATL::CStringData *)v9;
      goto LABEL_55;
    }
    if ( (_BYTE)SecurityDescriptorSize )
    {
      if ( (unsigned __int8)PushButtonReset::Directory::Exists(&lpPathName) )
      {
        Canonical = 0;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942403LL,
          "PushButtonReset::Directory::Create",
          "base\\reset\\util\\src\\filesystem.cpp",
          2234,
          L"Invalid volume root directory [%s]",
          lpPathName);
        Canonical = -2147024893;
      }
      goto LABEL_54;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v29);
    Canonical = PushButtonReset::Path::GetDirectory(a1, &v29);
    if ( Canonical >= 0 )
    {
      Canonical = PushButtonReset::Directory::Create(&v29, 0, a3);
      if ( Canonical >= 0 )
      {
        if ( *((int *)*a3 - 4) <= 0 )
        {
          DirectoryW = CreateDirectoryW(lpPathName, 0);
        }
        else
        {
          v31[1] = 0;
          v31[0] = &RAII::CAutoLocalFree<void *>::`vftable';
          LODWORD(SecurityDescriptorSize) = 0;
          v21 = (PSECURITY_DESCRIPTOR *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v31);
          if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(*a3, 1u, v21, (PULONG)&SecurityDescriptorSize) )
          {
            v22 = *a3;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)LastError,
              "PushButtonReset::Directory::Create",
              "base\\reset\\util\\src\\filesystem.cpp",
              2264,
              L"Failed to parse SDDL string [%s]",
              v22);
            v24 = GetLastError();
            Canonical = v24;
            if ( v24 > 0 )
              Canonical = (unsigned __int16)v24 | 0x80070000;
            v31[0] = &RAII::CAutoLocalFree<void *>::`vftable';
            RAII::CAutoLocalFree<unsigned short *>::Release(v31);
            goto LABEL_53;
          }
          memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
          SecurityAttributes.lpSecurityDescriptor = (LPVOID)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 32LL))(v31);
          SecurityAttributes.nLength = SecurityDescriptorSize;
          SecurityAttributes.bInheritHandle = 0;
          DirectoryW = CreateDirectoryW(lpPathName, &SecurityAttributes);
          v31[0] = &RAII::CAutoLocalFree<void *>::`vftable';
          RAII::CAutoLocalFree<unsigned short *>::Release(v31);
        }
        if ( !DirectoryW )
        {
          v26 = GetLastError();
          Canonical = v26;
          if ( v26 > 0 )
            Canonical = (unsigned __int16)v26 | 0x80070000;
          if ( Canonical != -2147024713 || v4 )
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Canonical,
              "PushButtonReset::Directory::Create",
              "base\\reset\\util\\src\\filesystem.cpp",
              2289,
              L"Failed to create [%s]",
              lpPathName);
          else
            Canonical = 0;
        }
        goto LABEL_53;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Canonical,
        "PushButtonReset::Directory::Create",
        "base\\reset\\util\\src\\filesystem.cpp",
        2250,
        L"Failed to create parent directory [%s] for [%s]",
        v29,
        *a1);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Canonical,
        "PushButtonReset::Directory::Create",
        "base\\reset\\util\\src\\filesystem.cpp",
        2245,
        L"Failed to construct parent path for [%s]",
        *a1);
    }
LABEL_53:
    ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
    goto LABEL_54;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Canonical,
    "PushButtonReset::Directory::Create",
    "base\\reset\\util\\src\\filesystem.cpp",
    2199,
    L"Failed to get canonical form for path [%s]",
    *a1);
  v7 = (ATL::CStringData *)(v30 - 24);
LABEL_55:
  ATL::CStringData::Release(v7);
  return (unsigned int)Canonical;
}

```

## disassembly

```asm
0x18004bb04  mov     [rsp-38h+arg_0], rbx
0x18004bb09  mov     [rsp-38h+arg_8], dl
0x18004bb0d  push    rbp
0x18004bb0e  push    rsi
0x18004bb0f  push    rdi
0x18004bb10  push    r12
0x18004bb12  push    r13
0x18004bb14  push    r14
0x18004bb16  push    r15
0x18004bb18  mov     rbp, rsp
0x18004bb1b  sub     rsp, 80h
0x18004bb22  mov     r13, r8
0x18004bb25  mov     r14b, dl
0x18004bb28  mov     r12, rcx
0x18004bb2b  lea     rcx, [rbp+var_30]
0x18004bb2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004bb34  nop
0x18004bb35  lea     rdx, [rbp+var_30]
0x18004bb39  mov     rcx, r12
0x18004bb3c  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004bb41  mov     ebx, eax
0x18004bb43  test    eax, eax
0x18004bb45  jns     short loc_18004BB8C
0x18004bb47  mov     rcx, [r12]
0x18004bb4b  mov     [rsp+80h+var_50], rcx
0x18004bb50  lea     rax, aFailedToGetCan; "Failed to get canonical form for path ["...
0x18004bb57  mov     [rsp+80h+var_58], rax
0x18004bb5c  mov     [rsp+80h+var_60], 897h
0x18004bb64  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004bb6b  lea     r8, aPushbuttonrese_70; "PushButtonReset::Directory::Create"
0x18004bb72  mov     edx, ebx
0x18004bb74  mov     ecx, 2
0x18004bb79  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004bb7e  nop
0x18004bb7f  mov     rcx, [rbp+var_30]
0x18004bb83  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18004bb87  jmp     loc_18004C00A
0x18004bb8c  lea     rcx, [rbp+lpPathName]
0x18004bb90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004bb95  nop
0x18004bb96  mov     rdi, [rbp+var_30]
0x18004bb9a  lea     r15, [rdi-18h]
0x18004bb9e  mov     edx, [r15+8]
0x18004bba2  test    edx, edx
0x18004bba4  jle     short loc_18004BC0C
0x18004bba6  dec     edx
0x18004bba8  lea     rcx, [rbp+var_30]
0x18004bbac  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004bbb1  cmp     ax, 5Ch ; '\'
0x18004bbb5  jnz     short loc_18004BC0C
0x18004bbb7  mov     rbx, [rbp+lpPathName]
0x18004bbbb  lea     rsi, [rbx-18h]
0x18004bbbf  cmp     r15, rsi
0x18004bbc2  jz      loc_18004BC7B
0x18004bbc8  cmp     dword ptr [rsi+10h], 0
0x18004bbcc  jl      short loc_18004BBF6
0x18004bbce  mov     rax, [rsi]
0x18004bbd1  cmp     [r15], rax
0x18004bbd4  jnz     short loc_18004BBF6
0x18004bbd6  mov     rcx, r15
0x18004bbd9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004bbde  mov     rbx, rax
0x18004bbe1  mov     rcx, rsi; this
0x18004bbe4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004bbe9  add     rbx, 18h
0x18004bbed  mov     [rbp+lpPathName], rbx
0x18004bbf1  jmp     loc_18004BC7B
0x18004bbf6  mov     r8d, [rdi-10h]
0x18004bbfa  mov     rdx, rdi
0x18004bbfd  lea     rcx, [rbp+lpPathName]
0x18004bc01  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004bc06  mov     rbx, [rbp+lpPathName]
0x18004bc0a  jmp     short loc_18004BC7B
0x18004bc0c  lea     r8, SubBlock; "\\"
0x18004bc13  lea     rdx, [rbp+var_30]
0x18004bc17  lea     rcx, [rbp+SecurityDescriptorSize]
0x18004bc1b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18004bc20  nop
0x18004bc21  mov     rdx, [rax]
0x18004bc24  lea     rcx, [rdx-18h]
0x18004bc28  mov     rbx, [rbp+lpPathName]
0x18004bc2c  lea     rdi, [rbx-18h]
0x18004bc30  cmp     rcx, rdi
0x18004bc33  jz      short loc_18004BC6E
0x18004bc35  cmp     dword ptr [rdi+10h], 0
0x18004bc39  jl      short loc_18004BC5D
0x18004bc3b  mov     rax, [rdi]
0x18004bc3e  cmp     [rcx], rax
0x18004bc41  jnz     short loc_18004BC5D
0x18004bc43  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004bc48  mov     rbx, rax
0x18004bc4b  mov     rcx, rdi; this
0x18004bc4e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004bc53  add     rbx, 18h
0x18004bc57  mov     [rbp+lpPathName], rbx
0x18004bc5b  jmp     short loc_18004BC6E
0x18004bc5d  mov     r8d, [rdx-10h]
0x18004bc61  lea     rcx, [rbp+lpPathName]
0x18004bc65  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004bc6a  mov     rbx, [rbp+lpPathName]
0x18004bc6e  mov     rcx, [rbp+SecurityDescriptorSize]
0x18004bc72  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004bc76  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004bc7b  mov     edi, 2
0x18004bc80  cmp     dword ptr [rbx-10h], 104h
0x18004bc87  jl      short loc_18004BC9A
0x18004bc89  xor     edx, edx
0x18004bc8b  lea     rcx, [rbp+lpPathName]
0x18004bc8f  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004bc94  cmp     ax, 5Ch ; '\'
0x18004bc98  jnz     short loc_18004BCD3
0x18004bc9a  mov     edx, 1
0x18004bc9f  lea     rcx, [rbp+lpPathName]
0x18004bca3  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004bca8  cmp     ax, 5Ch ; '\'
0x18004bcac  jnz     short loc_18004BCD3
0x18004bcae  mov     edx, edi
0x18004bcb0  lea     rcx, [rbp+lpPathName]
0x18004bcb4  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004bcb9  cmp     ax, 3Fh ; '?'
0x18004bcbd  jnz     short loc_18004BCD3
0x18004bcbf  mov     edx, 3
0x18004bcc4  lea     rcx, [rbp+lpPathName]
0x18004bcc8  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004bccd  cmp     ax, 5Ch ; '\'
0x18004bcd1  jz      short loc_18004BD46
0x18004bcd3  lea     rcx, [rbp+SecurityDescriptorSize]
0x18004bcd7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004bcdc  nop
0x18004bcdd  mov     r8, rbx
0x18004bce0  lea     rdx, aS; "\\\\?\\%s"
0x18004bce7  lea     rcx, [rbp+SecurityDescriptorSize]
0x18004bceb  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18004bcf0  mov     rdx, [rbp+SecurityDescriptorSize]
0x18004bcf4  lea     r14, [rdx-18h]
0x18004bcf8  lea     rsi, [rbx-18h]
0x18004bcfc  cmp     r14, rsi
0x18004bcff  jz      short loc_18004BD3A
0x18004bd01  cmp     dword ptr [rsi+10h], 0
0x18004bd05  jl      short loc_18004BD2C
0x18004bd07  mov     rax, [rsi]
0x18004bd0a  cmp     [r14], rax
0x18004bd0d  jnz     short loc_18004BD2C
0x18004bd0f  mov     rcx, r14
0x18004bd12  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004bd17  mov     rbx, rax
0x18004bd1a  mov     rcx, rsi; this
0x18004bd1d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004bd22  lea     rax, [rbx+18h]
0x18004bd26  mov     [rbp+lpPathName], rax
0x18004bd2a  jmp     short loc_18004BD3A
0x18004bd2c  mov     r8d, [rdx-10h]
0x18004bd30  lea     rcx, [rbp+lpPathName]
0x18004bd34  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004bd39  nop
0x18004bd3a  mov     rcx, r14; this
0x18004bd3d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004bd42  mov     r14b, [rbp+arg_8]
0x18004bd46  xor     esi, esi
0x18004bd48  mov     byte ptr [rbp+SecurityDescriptorSize], sil
0x18004bd4c  lea     rdx, [rbp+SecurityDescriptorSize]
0x18004bd50  lea     rcx, [rbp+lpPathName]
0x18004bd54  call    ?IsRoot@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@Z; PushButtonReset::Path::IsRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x18004bd59  mov     ebx, eax
0x18004bd5b  test    eax, eax
0x18004bd5d  jns     short loc_18004BD98
0x18004bd5f  mov     rcx, [rbp+lpPathName]
0x18004bd63  mov     [rsp+80h+var_50], rcx
0x18004bd68  lea     rax, aFailedToCheckW_3; "Failed to check whether [%s] is the roo"...
0x18004bd6f  mov     [rsp+80h+var_58], rax
0x18004bd74  mov     [rsp+80h+var_60], 8B2h
0x18004bd7c  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004bd83  lea     r8, aPushbuttonrese_70; "PushButtonReset::Directory::Create"
0x18004bd8a  mov     edx, ebx
0x18004bd8c  mov     ecx, edi
0x18004bd8e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004bd93  jmp     loc_18004BFF9
0x18004bd98  cmp     byte ptr [rbp+SecurityDescriptorSize], sil
0x18004bd9c  jz      short loc_18004BDF3
0x18004bd9e  lea     rcx, [rbp+lpPathName]
0x18004bda2  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004bda7  test    al, al
0x18004bda9  jnz     short loc_18004BDEC
0x18004bdab  mov     rax, [rbp+lpPathName]
0x18004bdaf  mov     [rsp+80h+var_50], rax
0x18004bdb4  lea     rax, aInvalidVolumeR; "Invalid volume root directory [%s]"
0x18004bdbb  mov     [rsp+80h+var_58], rax
0x18004bdc0  mov     [rsp+80h+var_60], 8BAh
0x18004bdc8  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004bdcf  lea     r8, aPushbuttonrese_70; "PushButtonReset::Directory::Create"
0x18004bdd6  mov     edx, 80070003h
0x18004bddb  mov     ecx, edi
0x18004bddd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004bde2  mov     ebx, 80070003h
0x18004bde7  jmp     loc_18004BFF9
0x18004bdec  mov     ebx, esi
0x18004bdee  jmp     loc_18004BFF9
0x18004bdf3  lea     rcx, [rbp+var_38]
0x18004bdf7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004bdfc  nop
0x18004bdfd  lea     rdx, [rbp+var_38]
0x18004be01  mov     rcx, r12
0x18004be04  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004be09  mov     ebx, eax
0x18004be0b  test    eax, eax
0x18004be0d  jns     short loc_18004BE31
0x18004be0f  mov     rcx, [r12]
0x18004be13  mov     [rsp+80h+var_50], rcx
0x18004be18  lea     rax, aFailedToConstr_8; "Failed to construct parent path for [%s"...
0x18004be1f  mov     [rsp+80h+var_58], rax
0x18004be24  mov     [rsp+80h+var_60], 8C5h
0x18004be2c  jmp     loc_18004BFD3
0x18004be31  mov     r8, r13
0x18004be34  xor     edx, edx
0x18004be36  lea     rcx, [rbp+var_38]
0x18004be3a  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004be3f  mov     ebx, eax
0x18004be41  test    eax, eax
0x18004be43  jns     short loc_18004BE87
0x18004be45  mov     rcx, [r12]
0x18004be49  mov     [rsp+80h+var_48], rcx
0x18004be4e  mov     rcx, [rbp+var_38]
0x18004be52  mov     [rsp+80h+var_50], rcx
0x18004be57  lea     rax, aFailedToCreate_4; "Failed to create parent directory [%s] "...
0x18004be5e  mov     [rsp+80h+var_58], rax
0x18004be63  mov     [rsp+80h+var_60], 8CAh
0x18004be6b  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004be72  lea     r8, aPushbuttonrese_70; "PushButtonReset::Directory::Create"
0x18004be79  mov     edx, ebx
0x18004be7b  mov     ecx, edi
0x18004be7d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004be82  jmp     loc_18004BFEB
0x18004be87  mov     rax, [r13+0]
0x18004be8b  cmp     [rax-10h], esi
0x18004be8e  jle     loc_18004BF7E
0x18004be94  mov     [rbp+var_20], rsi
0x18004be98  lea     r12, ??_7?$CAutoLocalFree@PEAX@RAII@@6B@; const RAII::CAutoLocalFree<void *>::`vftable'
0x18004be9f  mov     [rbp+var_28], r12
0x18004bea3  mov     dword ptr [rbp+SecurityDescriptorSize], esi
0x18004bea6  lea     rcx, [rbp+var_28]
0x18004beaa  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004beaf  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18004beb3  mov     r8, rax; SecurityDescriptor
0x18004beb6  mov     edx, 1; StringSDRevision
0x18004bebb  mov     rcx, [r13+0]; StringSecurityDescriptor
0x18004bebf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004bec5  test    eax, eax
0x18004bec7  jnz     short loc_18004BF34
0x18004bec9  mov     rbx, [r13+0]
0x18004becd  call    cs:__imp_GetLastError
0x18004bed3  mov     esi, 80070000h
0x18004bed8  test    eax, eax
0x18004beda  jle     short loc_18004BEE1
0x18004bedc  movzx   eax, ax
0x18004bedf  or      eax, esi
0x18004bee1  mov     [rsp+80h+var_50], rbx
0x18004bee6  lea     rcx, aFailedToParseS; "Failed to parse SDDL string [%s]"
0x18004beed  mov     [rsp+80h+var_58], rcx
0x18004bef2  mov     [rsp+80h+var_60], 8D8h
0x18004befa  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004bf01  lea     r8, aPushbuttonrese_70; "PushButtonReset::Directory::Create"
0x18004bf08  mov     edx, eax
0x18004bf0a  mov     ecx, edi
0x18004bf0c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004bf11  call    cs:__imp_GetLastError
0x18004bf17  mov     ebx, eax
0x18004bf19  test    eax, eax
0x18004bf1b  jle     short loc_18004BF22
0x18004bf1d  movzx   ebx, ax
0x18004bf20  or      ebx, esi
0x18004bf22  mov     [rbp+var_28], r12
0x18004bf26  lea     rcx, [rbp+var_28]
0x18004bf2a  call    ?Release@?$CAutoLocalFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoLocalFree<ushort *>::Release(void)
0x18004bf2f  jmp     loc_18004BFEB
0x18004bf34  xorps   xmm0, xmm0
0x18004bf37  xor     eax, eax
0x18004bf39  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18004bf3d  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x18004bf41  mov     rax, [rbp+var_28]
0x18004bf45  lea     rcx, [rbp+var_28]
0x18004bf49  mov     rax, [rax+20h]
0x18004bf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf52  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18004bf56  mov     eax, dword ptr [rbp+SecurityDescriptorSize]
0x18004bf59  mov     [rbp+SecurityAttributes.nLength], eax
0x18004bf5c  mov     [rbp+SecurityAttributes.bInheritHandle], esi
0x18004bf5f  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18004bf63  mov     rcx, [rbp+lpPathName]; lpPathName
0x18004bf67  call    cs:__imp_CreateDirectoryW
0x18004bf6d  mov     esi, eax
0x18004bf6f  mov     [rbp+var_28], r12
0x18004bf73  lea     rcx, [rbp+var_28]
0x18004bf77  call    ?Release@?$CAutoLocalFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoLocalFree<ushort *>::Release(void)
0x18004bf7c  jmp     short loc_18004BF8C
0x18004bf7e  xor     edx, edx; lpSecurityAttributes
0x18004bf80  mov     rcx, [rbp+lpPathName]; lpPathName
0x18004bf84  call    cs:__imp_CreateDirectoryW
0x18004bf8a  mov     esi, eax
0x18004bf8c  test    esi, esi
0x18004bf8e  jnz     short loc_18004BFEB
  ... truncated ...
```
