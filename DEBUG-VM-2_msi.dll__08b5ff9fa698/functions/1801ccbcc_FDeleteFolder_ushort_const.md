# FDeleteFolder(ushort const *)

- ea: `0x1801ccbcc`
- end: `0x1801cceef`
- name: `?FDeleteFolder@@YA_NPEBG@Z`
- size: `803`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801aff24`
- `0x1801ccbcc`
- `0x1801fff20`

## callees

- `0x180025560`
- `0x1800255e0`
- `0x180025688`
- `0x180025a18`
- `0x18004ceb0`
- `0x180066074`
- `0x18007b894`
- `0x1801ccbcc`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1801cce33`
- `KERNEL32!DeleteFileW` at `0x1801cce60`
- `KERNEL32!DeleteFileW` at `0x1801cce33`
- `KERNEL32!DeleteFileW` at `0x1801cce60`
- `KERNEL32!GetLastError` at `0x1801ccc98`
- `KERNEL32!GetLastError` at `0x1801ccca3`
- `KERNEL32!GetLastError` at `0x1801ccc98`
- `KERNEL32!GetLastError` at `0x1801ccca3`
- `KERNEL32!FindFirstFileW` at `0x1801ccc89`
- `KERNEL32!FindFirstFileW` at `0x1801ccc89`
- `KERNEL32!SetFileAttributesW` at `0x1801cce55`
- `KERNEL32!SetFileAttributesW` at `0x1801cceaf`
- `KERNEL32!SetFileAttributesW` at `0x1801cce55`
- `KERNEL32!SetFileAttributesW` at `0x1801cceaf`
- `KERNEL32!FindNextFileW` at `0x1801cce77`
- `KERNEL32!FindNextFileW` at `0x1801cce77`
- `KERNEL32!FindClose` at `0x1801cce88`
- `KERNEL32!FindClose` at `0x1801cce88`
- `KERNEL32!RemoveDirectoryW` at `0x1801cce91`
- `KERNEL32!RemoveDirectoryW` at `0x1801cceb8`
- `KERNEL32!RemoveDirectoryW` at `0x1801cce91`
- `KERNEL32!RemoveDirectoryW` at `0x1801cceb8`

## string_xrefs

- `0x1801ccd9b`: `FDeleteFolder: Deleting folder '%s'`
- `0x1801ccdf3`: `FDeleteFolder: Deleting file '%s'`

## pseudocode

```c
char __fastcall FDeleteFolder(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  char v3; // bl
  __int64 v5; // r8
  HANDLE FirstFileW; // rsi
  int v8; // edx
  int v9; // edx
  struct IMsiRecord *v10; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpPathName; // [rsp+68h] [rbp-98h] BYREF
  int v12; // [rsp+70h] [rbp-90h]
  char v13; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  char v16; // [rsp+90h] [rbp-70h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 1;
  lpFileName = (LPCWSTR)&v16;
  v15 = 1;
  lpPathName = (LPCWSTR)&v13;
  LOBYTE(a3) = 1;
  v12 = 1;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpFileName, 780, a3) )
    goto LABEL_8;
  LOBYTE(v5) = 1;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpPathName, 780, v5)
    || (int)StringCchCopyW((unsigned __int16 *)lpFileName, v15, a1) < 0
    || (int)StringCchCatW((unsigned __int16 *)lpFileName, v15, L"\\*.*") < 0 )
  {
    goto LABEL_8;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 5 || GetLastError() != 2 )
    {
LABEL_8:
      CAPITempBuffer<unsigned short,1>::Destroy(&lpPathName);
      CAPITempBuffer<unsigned short,1>::Destroy(&lpFileName);
      return 0;
    }
  }
  else
  {
    do
    {
      v8 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v8 = FindFileData.cFileName[1];
      if ( v8 )
      {
        v9 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v9 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v9 = FindFileData.cFileName[2];
        }
        if ( v9
          && (int)StringCchCopyW((unsigned __int16 *)lpPathName, v12, a1) >= 0
          && (int)StringCchCatW((unsigned __int16 *)lpPathName, v12, L"\\") >= 0
          && (int)StringCchCatW((unsigned __int16 *)lpPathName, v12, FindFileData.cFileName) >= 0 )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"FDeleteFolder: Deleting folder '%s'",
                lpPathName,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            FDeleteFolder(lpPathName);
          }
          else
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"FDeleteFolder: Deleting file '%s'",
                lpPathName,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            if ( !DeleteFileW(lpPathName) )
            {
              v10 = LockdownPath(lpPathName, 0);
              SetFileAttributesW(lpPathName, 0);
              DeleteFileW(lpPathName);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
            }
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
    if ( !RemoveDirectoryW(a1) )
    {
      v10 = LockdownPath(a1, 0);
      SetFileAttributesW(a1, 0);
      if ( RemoveDirectoryW(a1) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
      }
      else
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
        v3 = 0;
      }
    }
  }
  CAPITempBuffer<unsigned short,1>::Destroy(&lpPathName);
  CAPITempBuffer<unsigned short,1>::Destroy(&lpFileName);
  return v3;
}

```

## disassembly

```asm
0x1801ccbcc  push    rbp
0x1801ccbce  push    rbx
0x1801ccbcf  push    rsi
0x1801ccbd0  push    rdi
0x1801ccbd1  push    r12
0x1801ccbd3  push    r15
0x1801ccbd5  lea     rbp, [rsp-208h]
0x1801ccbdd  sub     rsp, 308h
0x1801ccbe4  mov     rax, cs:__security_cookie
0x1801ccbeb  xor     rax, rsp
0x1801ccbee  mov     [rbp+230h+var_40], rax
0x1801ccbf5  mov     ebx, 1
0x1801ccbfa  lea     rax, [rbp+230h+var_2A0]
0x1801ccbfe  mov     [rbp+230h+lpFileName], rax
0x1801ccc02  mov     rdi, rcx
0x1801ccc05  lea     rax, [rsp+330h+var_2B8]
0x1801ccc0a  mov     [rbp+230h+var_2A8], ebx
0x1801ccc0d  mov     esi, 30Ch
0x1801ccc12  mov     [rsp+330h+lpPathName], rax
0x1801ccc17  mov     r8b, bl
0x1801ccc1a  mov     [rsp+330h+var_2C0], ebx
0x1801ccc1e  mov     edx, esi
0x1801ccc20  lea     rcx, [rbp+230h+lpFileName]
0x1801ccc24  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x1801ccc29  test    al, al
0x1801ccc2b  jz      loc_1801CCCB2
0x1801ccc31  mov     r8b, bl
0x1801ccc34  lea     rcx, [rsp+330h+lpPathName]
0x1801ccc39  mov     edx, esi
0x1801ccc3b  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x1801ccc40  test    al, al
0x1801ccc42  jz      short loc_1801CCCB2
0x1801ccc44  movsxd  rdx, [rbp+230h+var_2A8]; unsigned __int64
0x1801ccc48  mov     r8, rdi; unsigned __int16 *
0x1801ccc4b  mov     rcx, [rbp+230h+lpFileName]; unsigned __int16 *
0x1801ccc4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ccc54  test    eax, eax
0x1801ccc56  js      short loc_1801CCCB2
0x1801ccc58  movsxd  rdx, [rbp+230h+var_2A8]; unsigned __int64
0x1801ccc5c  lea     r8, asc_1802B54A0; "\\*.*"
0x1801ccc63  mov     rcx, [rbp+230h+lpFileName]; unsigned __int16 *
0x1801ccc67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801ccc6c  test    eax, eax
0x1801ccc6e  js      short loc_1801CCCB2
0x1801ccc70  xor     edx, edx; Val
0x1801ccc72  lea     rcx, [rbp+230h+FindFileData]; void *
0x1801ccc76  mov     r8d, 250h; Size
0x1801ccc7c  call    memset_0
0x1801ccc81  mov     rcx, [rbp+230h+lpFileName]; lpFileName
0x1801ccc85  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1801ccc89  call    cs:__imp_FindFirstFileW
0x1801ccc8f  mov     rsi, rax
0x1801ccc92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ccc96  jnz     short loc_1801CCCE6
0x1801ccc98  call    cs:__imp_GetLastError
0x1801ccc9e  cmp     eax, 5
0x1801ccca1  jz      short loc_1801CCCB2
0x1801ccca3  call    cs:__imp_GetLastError
0x1801ccca9  cmp     eax, 2
0x1801cccac  jz      loc_1801CCECE
0x1801cccb2  lea     rcx, [rsp+330h+lpPathName]
0x1801cccb7  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801cccbc  lea     rcx, [rbp+230h+lpFileName]
0x1801cccc0  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801cccc5  xor     al, al
0x1801cccc7  mov     rcx, [rbp+230h+var_40]
0x1801cccce  xor     rcx, rsp; StackCookie
0x1801cccd1  call    __security_check_cookie
0x1801cccd6  add     rsp, 308h
0x1801cccdd  pop     r15
0x1801cccdf  pop     r12
0x1801ccce1  pop     rdi
0x1801ccce2  pop     rsi
0x1801ccce3  pop     rbx
0x1801ccce4  pop     rbp
0x1801ccce5  retn
0x1801ccce6  mov     r12d, 2Eh ; '.'
0x1801cccec  lea     r15, aNull; "(NULL)"
0x1801cccf3  movzx   edx, [rbp+230h+FindFileData.cFileName]
0x1801cccf7  sub     edx, r12d
0x1801cccfa  jnz     short loc_1801CCD07
0x1801cccfc  movzx   edx, [rbp+230h+FindFileData.cFileName+2]
0x1801ccd00  xor     eax, eax
0x1801ccd02  movzx   ecx, ax
0x1801ccd05  sub     edx, ecx
0x1801ccd07  test    edx, edx
0x1801ccd09  jz      loc_1801CCE70
0x1801ccd0f  movzx   edx, [rbp+230h+FindFileData.cFileName]
0x1801ccd13  sub     edx, r12d
0x1801ccd16  jnz     short loc_1801CCD2C
0x1801ccd18  movzx   edx, [rbp+230h+FindFileData.cFileName+2]
0x1801ccd1c  sub     edx, r12d
0x1801ccd1f  jnz     short loc_1801CCD2C
0x1801ccd21  movzx   edx, [rbp+230h+FindFileData.cFileName+4]
0x1801ccd25  xor     eax, eax
0x1801ccd27  movzx   ecx, ax
0x1801ccd2a  sub     edx, ecx
0x1801ccd2c  test    edx, edx
0x1801ccd2e  jz      loc_1801CCE70
0x1801ccd34  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801ccd39  mov     r8, rdi; unsigned __int16 *
0x1801ccd3c  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801ccd41  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ccd46  test    eax, eax
0x1801ccd48  js      loc_1801CCE70
0x1801ccd4e  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801ccd53  lea     r8, asc_18026F7A4; "\\"
0x1801ccd5a  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801ccd5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801ccd64  test    eax, eax
0x1801ccd66  js      loc_1801CCE70
0x1801ccd6c  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801ccd71  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x1801ccd75  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801ccd7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801ccd7f  test    eax, eax
0x1801ccd81  js      loc_1801CCE70
0x1801ccd87  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x1801ccd8b  jz      short loc_1801CCDE5
0x1801ccd8d  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801ccd94  jz      short loc_1801CCDD6
0x1801ccd96  mov     rax, [rsp+330h+lpPathName]
0x1801ccd9b  lea     r9, aFdeletefolderD; "FDeleteFolder: Deleting folder '%s'"
0x1801ccda2  xor     edx, edx; unsigned __int16
0x1801ccda4  xor     r8d, r8d; int
0x1801ccda7  mov     [rsp+330h+var_2D8], rdx; void *
0x1801ccdac  mov     [rsp+330h+var_2E0], edx; unsigned int
0x1801ccdb0  mov     [rsp+330h+var_2E8], r15; unsigned __int16 *
0x1801ccdb5  mov     [rsp+330h+var_2F0], r15; unsigned __int16 *
0x1801ccdba  lea     ecx, [rdx+0Ah]; int
0x1801ccdbd  mov     [rsp+330h+var_2F8], r15; unsigned __int16 *
0x1801ccdc2  mov     [rsp+330h+var_300], r15; unsigned __int16 *
0x1801ccdc7  mov     [rsp+330h+var_308], r15; unsigned __int16 *
0x1801ccdcc  mov     [rsp+330h+var_310], rax; unsigned __int16 *
0x1801ccdd1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ccdd6  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801ccddb  call    ?FDeleteFolder@@YA_NPEBG@Z; FDeleteFolder(ushort const *)
0x1801ccde0  jmp     loc_1801CCE70
0x1801ccde5  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801ccdec  jz      short loc_1801CCE2E
0x1801ccdee  mov     rax, [rsp+330h+lpPathName]
0x1801ccdf3  lea     r9, aFdeletefolderD_0; "FDeleteFolder: Deleting file '%s'"
0x1801ccdfa  xor     edx, edx; unsigned __int16
0x1801ccdfc  xor     r8d, r8d; int
0x1801ccdff  mov     [rsp+330h+var_2D8], rdx; void *
0x1801cce04  mov     [rsp+330h+var_2E0], edx; unsigned int
0x1801cce08  mov     [rsp+330h+var_2E8], r15; unsigned __int16 *
0x1801cce0d  mov     [rsp+330h+var_2F0], r15; unsigned __int16 *
0x1801cce12  lea     ecx, [rdx+0Ah]; int
0x1801cce15  mov     [rsp+330h+var_2F8], r15; unsigned __int16 *
0x1801cce1a  mov     [rsp+330h+var_300], r15; unsigned __int16 *
0x1801cce1f  mov     [rsp+330h+var_308], r15; unsigned __int16 *
0x1801cce24  mov     [rsp+330h+var_310], rax; unsigned __int16 *
0x1801cce29  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801cce2e  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801cce33  call    cs:__imp_DeleteFileW
0x1801cce39  test    eax, eax
0x1801cce3b  jnz     short loc_1801CCE70
0x1801cce3d  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801cce42  xor     edx, edx; bool
0x1801cce44  call    ?LockdownPath@@YAPEAVIMsiRecord@@PEBG_N@Z; LockdownPath(ushort const *,bool)
0x1801cce49  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801cce4e  xor     edx, edx; dwFileAttributes
0x1801cce50  mov     [rsp+330h+var_2D0], rax
0x1801cce55  call    cs:__imp_SetFileAttributesW
0x1801cce5b  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801cce60  call    cs:__imp_DeleteFileW
0x1801cce66  lea     rcx, [rsp+330h+var_2D0]
0x1801cce6b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801cce70  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1801cce74  mov     rcx, rsi; hFindFile
0x1801cce77  call    cs:__imp_FindNextFileW
0x1801cce7d  cmp     eax, ebx
0x1801cce7f  jz      loc_1801CCCF3
0x1801cce85  mov     rcx, rsi; hFindFile
0x1801cce88  call    cs:__imp_FindClose
0x1801cce8e  mov     rcx, rdi; lpPathName
0x1801cce91  call    cs:__imp_RemoveDirectoryW
0x1801cce97  test    eax, eax
0x1801cce99  jnz     short loc_1801CCECE
0x1801cce9b  xor     edx, edx; bool
0x1801cce9d  mov     rcx, rdi; lpFileName
0x1801ccea0  call    ?LockdownPath@@YAPEAVIMsiRecord@@PEBG_N@Z; LockdownPath(ushort const *,bool)
0x1801ccea5  xor     edx, edx; dwFileAttributes
0x1801ccea7  mov     [rsp+330h+var_2D0], rax
0x1801cceac  mov     rcx, rdi; lpFileName
0x1801cceaf  call    cs:__imp_SetFileAttributesW
0x1801cceb5  mov     rcx, rdi; lpPathName
0x1801cceb8  call    cs:__imp_RemoveDirectoryW
0x1801ccebe  lea     rcx, [rsp+330h+var_2D0]
0x1801ccec3  test    eax, eax
0x1801ccec5  jnz     short loc_1801CCEE8
0x1801ccec7  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801ccecc  xor     bl, bl
0x1801ccece  lea     rcx, [rsp+330h+lpPathName]
0x1801cced3  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801cced8  lea     rcx, [rbp+230h+lpFileName]
0x1801ccedc  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801ccee1  mov     al, bl
0x1801ccee3  jmp     loc_1801CCCC7
0x1801ccee8  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801cceed  jmp     short loc_1801CCECE
```
