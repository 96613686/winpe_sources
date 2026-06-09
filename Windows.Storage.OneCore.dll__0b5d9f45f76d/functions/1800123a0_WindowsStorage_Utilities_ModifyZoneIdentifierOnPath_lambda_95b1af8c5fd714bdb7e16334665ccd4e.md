# WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_95b1af8c5fd714bdb7e16334665ccd4e___

- ea: `0x1800123a0`
- end: `0x180012677`
- name: `WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_95b1af8c5fd714bdb7e16334665ccd4e___`
- size: `727`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014134`

## callees

- `0x180002be0`
- `0x180007f8c`
- `0x180007fac`
- `0x180011fd4`
- `0x1800123a0`
- `0x1800134b0`
- `0x1800139b4`
- `0x180013b3c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180012400`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180012400`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001247d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001261d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001247d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001261d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180012452`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180012452`

## pseudocode

```c
__int64 __fastcall WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_95b1af8c5fd714bdb7e16334665ccd4e___(
        HANDLE hFile,
        struct _GUID *a2,
        __int64 a3,
        WindowsStorage::Utilities::Identity **a4)
{
  const char *v7; // r9
  __int64 v8; // rdx
  char v10; // di
  WindowsStorage::Utilities *v11; // rcx
  const unsigned __int16 *v12; // r8
  int v13; // eax
  int LastError; // ebx
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(__int64, const unsigned __int16 *); // rbx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  const char *v23; // r9
  void **lpMaximumComponentLength; // [rsp+20h] [rbp-49h]
  int lpMaximumComponentLengtha; // [rsp+20h] [rbp-49h]
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID lpFileSystemFlags; // [rsp+48h] [rbp-21h] BYREF
  _OWORD FileInformation[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v29; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_DWORD *)lpFileSystemFlags.Data4 = 0;
  if ( !GetVolumeInformationByHandleW(hFile, 0, 0, 0, 0, (LPDWORD)lpFileSystemFlags.Data4, 0, 0) )
  {
    v8 = 125;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
             v7);
  }
  if ( (*(_DWORD *)lpFileSystemFlags.Data4 & 0x40000) == 0 )
    return 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v29 = 0;
  if ( !GetFileInformationByHandleEx(hFile, FileBasicInfo, FileInformation, 0x28u) )
  {
    v8 = 132;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
             v7);
  }
  v10 = 0;
  if ( (v29 & 1) != 0 )
  {
    LODWORD(v29) = v29 & 0xFFFFFFFE;
    if ( !SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
    {
      v8 = 138;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v8,
               (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
               v7);
    }
    v10 = 1;
  }
  *(_QWORD *)&lpFileSystemFlags.Data1 = 0;
  Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&lpFileSystemFlags);
  v13 = WindowsStorage::Utilities::CoCreateInstanceAndLoadFromFile(
          v11,
          a2,
          v12,
          &lpFileSystemFlags,
          lpMaximumComponentLength);
  LastError = v13;
  if ( v13 >= 0 )
  {
    v17 = *(_QWORD *)&lpFileSystemFlags.Data1;
    LastError = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&lpFileSystemFlags.Data1 + 32LL))(
                  *(_QWORD *)&lpFileSystemFlags.Data1,
                  3);
    if ( LastError < 0 )
    {
      v18 = 326;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
        (const char *)(unsigned int)LastError,
        lpMaximumComponentLengtha);
      v15 = (unsigned int)LastError;
      v16 = 152;
      goto LABEL_19;
    }
    v19 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v17 + 56LL);
    v20 = WindowsStorage::Utilities::Identity::PackageFamilyName(*a4);
    LastError = v19(v17, v20);
    if ( LastError < 0 )
    {
      v18 = 327;
      goto LABEL_18;
    }
    v26 = 0;
    v21 = Microsoft::WRL::ComPtr<IZoneIdentifier2>::As<IPersistFile>(&lpFileSystemFlags, (__int64)&v26);
    LastError = v21;
    if ( v21 < 0 )
    {
      v22 = 155;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
        (const char *)(unsigned int)v21,
        lpMaximumComponentLengtha);
LABEL_23:
      Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v26);
      goto LABEL_37;
    }
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26) )
    {
      *(_DWORD *)&lpFileSystemFlags.Data4[4] = 0;
      v21 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *))(**(_QWORD **)&lpFileSystemFlags.Data1 + 24LL))(
              *(_QWORD *)&lpFileSystemFlags.Data1,
              &lpFileSystemFlags.Data4[4]);
      LastError = v21;
      if ( v21 < 0 )
      {
        v22 = 159;
        goto LABEL_22;
      }
      if ( !*(_DWORD *)&lpFileSystemFlags.Data4[4] )
      {
        v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&lpFileSystemFlags.Data1 + 40LL))(*(_QWORD *)&lpFileSystemFlags.Data1);
        LastError = v21;
        if ( v21 < 0 )
        {
          v22 = 162;
          goto LABEL_22;
        }
      }
      v21 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64))(*(_QWORD *)v26 + 48LL))(v26, a2, 1);
      LastError = v21;
      if ( v21 < 0 )
      {
        v22 = 164;
        goto LABEL_22;
      }
    }
    if ( v10 )
      LODWORD(v29) = v29 | 1;
    if ( SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
    {
      Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v26);
      LastError = 0;
      goto LABEL_37;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAB,
                  (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
                  v23);
    goto LABEL_23;
  }
  v15 = (unsigned int)v13;
  v16 = 145;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\base\\windows.storage\\src\\Identity.h",
    (const char *)v15,
    lpMaximumComponentLengtha);
LABEL_37:
  Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&lpFileSystemFlags);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800123a0  push    rbp
0x1800123a2  push    rbx
0x1800123a3  push    rsi
0x1800123a4  push    rdi
0x1800123a5  push    r12
0x1800123a7  push    r14
0x1800123a9  push    r15
0x1800123ab  lea     rbp, [rsp-27h]
0x1800123b0  sub     rsp, 90h
0x1800123b7  mov     rax, cs:__security_cookie
0x1800123be  xor     rax, rsp
0x1800123c1  mov     [rbp+57h+var_40], rax
0x1800123c5  mov     r12, r9
0x1800123c8  mov     r15, rdx
0x1800123cb  mov     r14, rcx
0x1800123ce  mov     dword ptr [rbp+57h+var_78.Data4], 0
0x1800123d5  mov     [rsp+0C0h+nFileSystemNameSize], 0; nFileSystemNameSize
0x1800123dd  mov     [rsp+0C0h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x1800123e6  lea     rax, [rbp+57h+var_78.Data4]
0x1800123ea  mov     [rsp+0C0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800123ef  mov     [rsp+0C0h+lpMaximumComponentLength], 0; int
0x1800123f8  xor     r9d, r9d; lpVolumeSerialNumber
0x1800123fb  xor     r8d, r8d; nVolumeNameSize
0x1800123fe  xor     edx, edx; lpVolumeNameBuffer
0x180012400  call    cs:__imp_GetVolumeInformationByHandleW
0x180012406  test    eax, eax
0x180012408  jnz     short loc_180012422
0x18001240a  lea     edx, [rax+7Dh]; void *
0x18001240d  mov     rcx, [rbp+5Fh]; this
0x180012411  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012418  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001241d  jmp     loc_180012659
0x180012422  test    dword ptr [rbp+57h+var_78.Data4], 40000h
0x180012429  jnz     short loc_180012432
0x18001242b  xor     eax, eax
0x18001242d  jmp     loc_180012659
0x180012432  xorps   xmm0, xmm0
0x180012435  xor     eax, eax
0x180012437  movups  [rbp+57h+FileInformation], xmm0
0x18001243b  movups  [rbp+57h+var_58], xmm0
0x18001243f  mov     [rbp+57h+var_48], rax
0x180012443  lea     ebx, [rax+28h]
0x180012446  mov     r9d, ebx; dwBufferSize
0x180012449  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18001244d  xor     edx, edx; FileInformationClass
0x18001244f  mov     rcx, r14; hFile
0x180012452  call    cs:__imp_GetFileInformationByHandleEx
0x180012458  test    eax, eax
0x18001245a  jnz     short loc_180012461
0x18001245c  lea     edx, [rbx+5Ch]
0x18001245f  jmp     short loc_18001240D
0x180012461  xor     dil, dil
0x180012464  mov     eax, dword ptr [rbp+57h+var_48]
0x180012467  test    al, 1
0x180012469  jz      short loc_180012494
0x18001246b  and     eax, 0FFFFFFFEh
0x18001246e  mov     dword ptr [rbp+57h+var_48], eax
0x180012471  mov     r9d, ebx; dwBufferSize
0x180012474  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180012478  xor     edx, edx; FileInformationClass
0x18001247a  mov     rcx, r14; hFile
0x18001247d  call    cs:__imp_SetFileInformationByHandle
0x180012483  test    eax, eax
0x180012485  jnz     short loc_180012491
0x180012487  mov     edx, 8Ah
0x18001248c  jmp     loc_18001240D
0x180012491  mov     dil, 1
0x180012494  mov     qword ptr [rbp+57h+var_78.Data1], 0
0x18001249c  lea     rcx, [rbp+57h+var_78]
0x1800124a0  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x1800124a5  lea     r9, [rbp+57h+var_78]; struct _GUID *
0x1800124a9  mov     rdx, r15; struct _GUID *
0x1800124ac  call    ?CoCreateInstanceAndLoadFromFile@Utilities@WindowsStorage@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z; WindowsStorage::Utilities::CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)
0x1800124b1  mov     ebx, eax
0x1800124b3  test    eax, eax
0x1800124b5  jns     short loc_1800124C1
0x1800124b7  mov     r9d, eax
0x1800124ba  mov     edx, 91h
0x1800124bf  jmp     short loc_18001252A
0x1800124c1  mov     rsi, qword ptr [rbp+57h+var_78.Data1]
0x1800124c5  mov     rax, [rsi]
0x1800124c8  mov     edx, 3
0x1800124cd  mov     rcx, rsi
0x1800124d0  mov     rax, [rax+20h]
0x1800124d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124d9  mov     ebx, eax
0x1800124db  test    eax, eax
0x1800124dd  jns     short loc_1800124E6
0x1800124df  mov     edx, 146h
0x1800124e4  jmp     short loc_18001250F
0x1800124e6  mov     rax, [rsi]
0x1800124e9  mov     rbx, [rax+38h]
0x1800124ed  mov     rcx, [r12]; this
0x1800124f1  call    ?PackageFamilyName@Identity@Utilities@WindowsStorage@@QEAAPEBGXZ; WindowsStorage::Utilities::Identity::PackageFamilyName(void)
0x1800124f6  mov     rdx, rax
0x1800124f9  mov     rcx, rsi
0x1800124fc  mov     rax, rbx
0x1800124ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012504  mov     ebx, eax
0x180012506  test    eax, eax
0x180012508  jns     short loc_18001253F
0x18001250a  mov     edx, 147h; void *
0x18001250f  mov     r9d, ebx; char *
0x180012512  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180012519  mov     rcx, [rbp+5Fh]; this
0x18001251d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012522  mov     r9d, ebx; char *
0x180012525  mov     edx, 98h; void *
0x18001252a  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012531  mov     rcx, [rbp+5Fh]; this
0x180012535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001253a  jmp     loc_18001264E
0x18001253f  mov     [rbp+57h+var_80], 0
0x180012547  lea     rdx, [rbp+57h+var_80]
0x18001254b  lea     rcx, [rbp+57h+var_78]
0x18001254f  call    ??$As@UIPersistFile@@@?$ComPtr@UIZoneIdentifier2@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPersistFile@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IZoneIdentifier2>::As<IPersistFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistFile>>)
0x180012554  mov     ebx, eax
0x180012556  test    eax, eax
0x180012558  jns     short loc_180012581
0x18001255a  mov     edx, 9Bh; void *
0x18001255f  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012566  mov     r9d, eax; char *
0x180012569  mov     rcx, [rbp+5Fh]; this
0x18001256d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012572  nop
0x180012573  lea     rcx, [rbp+57h+var_80]
0x180012577  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001257c  jmp     loc_18001264E
0x180012581  mov     rcx, [rbp+57h+var_80]
0x180012585  mov     rax, [rcx]
0x180012588  mov     rax, [rax+20h]
0x18001258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012591  test    eax, eax
0x180012593  jnz     short loc_180012605
0x180012595  mov     dword ptr [rbp+57h+var_78.Data4+4], eax
0x180012598  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x18001259c  mov     rax, [rcx]
0x18001259f  lea     rdx, [rbp+57h+var_78.Data4+4]
0x1800125a3  mov     rax, [rax+18h]
0x1800125a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ac  mov     ebx, eax
0x1800125ae  test    eax, eax
0x1800125b0  jns     short loc_1800125B9
0x1800125b2  mov     edx, 9Fh
0x1800125b7  jmp     short loc_18001255F
0x1800125b9  cmp     dword ptr [rbp+57h+var_78.Data4+4], 0
0x1800125bd  jnz     short loc_1800125DC
0x1800125bf  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x1800125c3  mov     rax, [rcx]
0x1800125c6  mov     rax, [rax+28h]
0x1800125ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cf  mov     ebx, eax
0x1800125d1  test    eax, eax
0x1800125d3  jns     short loc_1800125DC
0x1800125d5  mov     edx, 0A2h
0x1800125da  jmp     short loc_18001255F
0x1800125dc  mov     rcx, [rbp+57h+var_80]
0x1800125e0  mov     rax, [rcx]
0x1800125e3  mov     r8d, 1
0x1800125e9  mov     rdx, r15
0x1800125ec  mov     rax, [rax+30h]
0x1800125f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125f5  mov     ebx, eax
0x1800125f7  test    eax, eax
0x1800125f9  jns     short loc_180012605
0x1800125fb  mov     edx, 0A4h
0x180012600  jmp     loc_18001255F
0x180012605  test    dil, dil
0x180012608  jz      short loc_18001260E
0x18001260a  or      dword ptr [rbp+57h+var_48], 1
0x18001260e  mov     r9d, 28h ; '('; dwBufferSize
0x180012614  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180012618  xor     edx, edx; FileInformationClass
0x18001261a  mov     rcx, r14; hFile
0x18001261d  call    cs:__imp_SetFileInformationByHandle
0x180012623  test    eax, eax
0x180012625  jnz     short loc_180012643
0x180012627  mov     rcx, [rbp+5Fh]; this
0x18001262b  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012632  mov     edx, 0ABh; void *
0x180012637  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001263c  mov     ebx, eax
0x18001263e  jmp     loc_180012573
0x180012643  lea     rcx, [rbp+57h+var_80]
0x180012647  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001264c  xor     ebx, ebx
0x18001264e  lea     rcx, [rbp+57h+var_78]
0x180012652  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x180012657  mov     eax, ebx
0x180012659  mov     rcx, [rbp+57h+var_40]
0x18001265d  xor     rcx, rsp; StackCookie
0x180012660  call    __security_check_cookie
0x180012665  add     rsp, 90h
0x18001266c  pop     r15
0x18001266e  pop     r14
0x180012670  pop     r12
0x180012672  pop     rdi
0x180012673  pop     rsi
0x180012674  pop     rbx
0x180012675  pop     rbp
0x180012676  retn
```
