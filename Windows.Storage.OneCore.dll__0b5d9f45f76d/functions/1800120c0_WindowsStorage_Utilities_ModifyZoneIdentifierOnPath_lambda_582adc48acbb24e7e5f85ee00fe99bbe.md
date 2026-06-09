# WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_582adc48acbb24e7e5f85ee00fe99bbe___

- ea: `0x1800120c0`
- end: `0x180012397`
- name: `WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_582adc48acbb24e7e5f85ee00fe99bbe___`
- size: `727`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _GUID *, __int64, WindowsStorage::Utilities::Identity **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017940`

## callees

- `0x180002be0`
- `0x180007f8c`
- `0x180007fac`
- `0x180011fd4`
- `0x1800120c0`
- `0x1800134b0`
- `0x1800139b4`
- `0x180013b3c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180012120`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180012120`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001219d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001233d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001219d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001233d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180012172`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180012172`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_582adc48acbb24e7e5f85ee00fe99bbe___(
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
      v18 = 296;
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
      v18 = 297;
      goto LABEL_18;
    }
    v26 = 0;
    v21 = Microsoft::WRL::ComPtr<IZoneIdentifier2>::As<IPersistFile>(&lpFileSystemFlags, &v26);
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
0x1800120c0  push    rbp
0x1800120c2  push    rbx
0x1800120c3  push    rsi
0x1800120c4  push    rdi
0x1800120c5  push    r12
0x1800120c7  push    r14
0x1800120c9  push    r15
0x1800120cb  lea     rbp, [rsp-27h]
0x1800120d0  sub     rsp, 90h
0x1800120d7  mov     rax, cs:__security_cookie
0x1800120de  xor     rax, rsp
0x1800120e1  mov     [rbp+57h+var_40], rax
0x1800120e5  mov     r12, r9
0x1800120e8  mov     r15, rdx
0x1800120eb  mov     r14, rcx
0x1800120ee  mov     dword ptr [rbp+57h+var_78.Data4], 0
0x1800120f5  mov     [rsp+0C0h+nFileSystemNameSize], 0; nFileSystemNameSize
0x1800120fd  mov     [rsp+0C0h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x180012106  lea     rax, [rbp+57h+var_78.Data4]
0x18001210a  mov     [rsp+0C0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18001210f  mov     [rsp+0C0h+lpMaximumComponentLength], 0; int
0x180012118  xor     r9d, r9d; lpVolumeSerialNumber
0x18001211b  xor     r8d, r8d; nVolumeNameSize
0x18001211e  xor     edx, edx; lpVolumeNameBuffer
0x180012120  call    cs:__imp_GetVolumeInformationByHandleW
0x180012126  test    eax, eax
0x180012128  jnz     short loc_180012142
0x18001212a  lea     edx, [rax+7Dh]; void *
0x18001212d  mov     rcx, [rbp+5Fh]; this
0x180012131  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012138  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001213d  jmp     loc_180012379
0x180012142  test    dword ptr [rbp+57h+var_78.Data4], 40000h
0x180012149  jnz     short loc_180012152
0x18001214b  xor     eax, eax
0x18001214d  jmp     loc_180012379
0x180012152  xorps   xmm0, xmm0
0x180012155  xor     eax, eax
0x180012157  movups  [rbp+57h+FileInformation], xmm0
0x18001215b  movups  [rbp+57h+var_58], xmm0
0x18001215f  mov     [rbp+57h+var_48], rax
0x180012163  lea     ebx, [rax+28h]
0x180012166  mov     r9d, ebx; dwBufferSize
0x180012169  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18001216d  xor     edx, edx; FileInformationClass
0x18001216f  mov     rcx, r14; hFile
0x180012172  call    cs:__imp_GetFileInformationByHandleEx
0x180012178  test    eax, eax
0x18001217a  jnz     short loc_180012181
0x18001217c  lea     edx, [rbx+5Ch]
0x18001217f  jmp     short loc_18001212D
0x180012181  xor     dil, dil
0x180012184  mov     eax, dword ptr [rbp+57h+var_48]
0x180012187  test    al, 1
0x180012189  jz      short loc_1800121B4
0x18001218b  and     eax, 0FFFFFFFEh
0x18001218e  mov     dword ptr [rbp+57h+var_48], eax
0x180012191  mov     r9d, ebx; dwBufferSize
0x180012194  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180012198  xor     edx, edx; FileInformationClass
0x18001219a  mov     rcx, r14; hFile
0x18001219d  call    cs:__imp_SetFileInformationByHandle
0x1800121a3  test    eax, eax
0x1800121a5  jnz     short loc_1800121B1
0x1800121a7  mov     edx, 8Ah
0x1800121ac  jmp     loc_18001212D
0x1800121b1  mov     dil, 1
0x1800121b4  mov     qword ptr [rbp+57h+var_78.Data1], 0
0x1800121bc  lea     rcx, [rbp+57h+var_78]
0x1800121c0  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x1800121c5  lea     r9, [rbp+57h+var_78]; struct _GUID *
0x1800121c9  mov     rdx, r15; struct _GUID *
0x1800121cc  call    ?CoCreateInstanceAndLoadFromFile@Utilities@WindowsStorage@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z; WindowsStorage::Utilities::CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)
0x1800121d1  mov     ebx, eax
0x1800121d3  test    eax, eax
0x1800121d5  jns     short loc_1800121E1
0x1800121d7  mov     r9d, eax
0x1800121da  mov     edx, 91h
0x1800121df  jmp     short loc_18001224A
0x1800121e1  mov     rsi, qword ptr [rbp+57h+var_78.Data1]
0x1800121e5  mov     rax, [rsi]
0x1800121e8  mov     edx, 3
0x1800121ed  mov     rcx, rsi
0x1800121f0  mov     rax, [rax+20h]
0x1800121f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f9  mov     ebx, eax
0x1800121fb  test    eax, eax
0x1800121fd  jns     short loc_180012206
0x1800121ff  mov     edx, 128h
0x180012204  jmp     short loc_18001222F
0x180012206  mov     rax, [rsi]
0x180012209  mov     rbx, [rax+38h]
0x18001220d  mov     rcx, [r12]; this
0x180012211  call    ?PackageFamilyName@Identity@Utilities@WindowsStorage@@QEAAPEBGXZ; WindowsStorage::Utilities::Identity::PackageFamilyName(void)
0x180012216  mov     rdx, rax
0x180012219  mov     rcx, rsi
0x18001221c  mov     rax, rbx
0x18001221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012224  mov     ebx, eax
0x180012226  test    eax, eax
0x180012228  jns     short loc_18001225F
0x18001222a  mov     edx, 129h; void *
0x18001222f  mov     r9d, ebx; char *
0x180012232  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180012239  mov     rcx, [rbp+5Fh]; this
0x18001223d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012242  mov     r9d, ebx; char *
0x180012245  mov     edx, 98h; void *
0x18001224a  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012251  mov     rcx, [rbp+5Fh]; this
0x180012255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001225a  jmp     loc_18001236E
0x18001225f  mov     [rbp+57h+var_80], 0
0x180012267  lea     rdx, [rbp+57h+var_80]
0x18001226b  lea     rcx, [rbp+57h+var_78]
0x18001226f  call    ??$As@UIPersistFile@@@?$ComPtr@UIZoneIdentifier2@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPersistFile@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IZoneIdentifier2>::As<IPersistFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistFile>>)
0x180012274  mov     ebx, eax
0x180012276  test    eax, eax
0x180012278  jns     short loc_1800122A1
0x18001227a  mov     edx, 9Bh; void *
0x18001227f  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012286  mov     r9d, eax; char *
0x180012289  mov     rcx, [rbp+5Fh]; this
0x18001228d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012292  nop
0x180012293  lea     rcx, [rbp+57h+var_80]
0x180012297  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001229c  jmp     loc_18001236E
0x1800122a1  mov     rcx, [rbp+57h+var_80]
0x1800122a5  mov     rax, [rcx]
0x1800122a8  mov     rax, [rax+20h]
0x1800122ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b1  test    eax, eax
0x1800122b3  jnz     short loc_180012325
0x1800122b5  mov     dword ptr [rbp+57h+var_78.Data4+4], eax
0x1800122b8  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x1800122bc  mov     rax, [rcx]
0x1800122bf  lea     rdx, [rbp+57h+var_78.Data4+4]
0x1800122c3  mov     rax, [rax+18h]
0x1800122c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122cc  mov     ebx, eax
0x1800122ce  test    eax, eax
0x1800122d0  jns     short loc_1800122D9
0x1800122d2  mov     edx, 9Fh
0x1800122d7  jmp     short loc_18001227F
0x1800122d9  cmp     dword ptr [rbp+57h+var_78.Data4+4], 0
0x1800122dd  jnz     short loc_1800122FC
0x1800122df  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x1800122e3  mov     rax, [rcx]
0x1800122e6  mov     rax, [rax+28h]
0x1800122ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ef  mov     ebx, eax
0x1800122f1  test    eax, eax
0x1800122f3  jns     short loc_1800122FC
0x1800122f5  mov     edx, 0A2h
0x1800122fa  jmp     short loc_18001227F
0x1800122fc  mov     rcx, [rbp+57h+var_80]
0x180012300  mov     rax, [rcx]
0x180012303  mov     r8d, 1
0x180012309  mov     rdx, r15
0x18001230c  mov     rax, [rax+30h]
0x180012310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012315  mov     ebx, eax
0x180012317  test    eax, eax
0x180012319  jns     short loc_180012325
0x18001231b  mov     edx, 0A4h
0x180012320  jmp     loc_18001227F
0x180012325  test    dil, dil
0x180012328  jz      short loc_18001232E
0x18001232a  or      dword ptr [rbp+57h+var_48], 1
0x18001232e  mov     r9d, 28h ; '('; dwBufferSize
0x180012334  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180012338  xor     edx, edx; FileInformationClass
0x18001233a  mov     rcx, r14; hFile
0x18001233d  call    cs:__imp_SetFileInformationByHandle
0x180012343  test    eax, eax
0x180012345  jnz     short loc_180012363
0x180012347  mov     rcx, [rbp+5Fh]; this
0x18001234b  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\windows.storage\\src\\Id"...
0x180012352  mov     edx, 0ABh; void *
0x180012357  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001235c  mov     ebx, eax
0x18001235e  jmp     loc_180012293
0x180012363  lea     rcx, [rbp+57h+var_80]
0x180012367  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001236c  xor     ebx, ebx
0x18001236e  lea     rcx, [rbp+57h+var_78]
0x180012372  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x180012377  mov     eax, ebx
0x180012379  mov     rcx, [rbp+57h+var_40]
0x18001237d  xor     rcx, rsp; StackCookie
0x180012380  call    __security_check_cookie
0x180012385  add     rsp, 90h
0x18001238c  pop     r15
0x18001238e  pop     r14
0x180012390  pop     r12
0x180012392  pop     rdi
0x180012393  pop     rsi
0x180012394  pop     rbx
0x180012395  pop     rbp
0x180012396  retn
```
