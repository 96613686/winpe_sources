# CFSTransfer::_SameVolumeMoveOrRename(ulong,bool,IShellItem * *)

- ea: `0x180215b78`
- end: `0x1802160d7`
- name: `?_SameVolumeMoveOrRename@CFSTransfer@@AEAAJK_NPEAPEAUIShellItem@@@Z`
- size: `1375`
- prototype: `__int64 __fastcall(CFSTransfer *__hidden this, unsigned int, bool, struct IShellItem **)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180215530`

## callees

- `0x18007ce8c`
- `0x18009d164`
- `0x1800a5580`
- `0x1800aa710`
- `0x1800d7650`
- `0x180105974`
- `0x18010a850`
- `0x18011cbf4`
- `0x18012c990`
- `0x18015adb0`
- `0x180215b78`
- `0x1802168b0`
- `0x180216ab4`
- `0x180216b08`
- `0x1802acff4`
- `0x18030a4d4`
- `0x180380d8c`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803aee20`
- `0x1805a7c48`
- `0x1805a7e84`
- `0x1805a8594`
- `0x1805d55d8`
- `0x18065a010`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x180215e31`
- `ntdll!RtlGetLastNtStatus` at `0x180215e31`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180216073`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180216073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180215d71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802160cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180215d71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802160cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180215e66`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180215ec0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180215e66`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180215ec0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180215e22`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180215e22`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x180215c5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x180215c5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180215bf2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180215bf2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x180215d4d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x180215d4d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18065104c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18065104c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180215f52`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180215f52`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180215f21`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180215f21`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHEncryptFile` at `0x1806510ea`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHEncryptFile` at `0x1806510ea`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_EncryptDirectory` at `0x180215ee9`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_EncryptDirectory` at `0x180215ee9`

## pseudocode

```c
__int64 __fastcall CFSTransfer::_SameVolumeMoveOrRename(
        CFSTransfer *this,
        unsigned int a2,
        char a3,
        struct IShellItem **a4)
{
  __int64 v5; // rcx
  char v7; // si
  __int64 result; // rax
  int v9; // eax
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  unsigned int v12; // r15d
  signed int v13; // r14d
  bool v14; // r13
  __int64 v15; // rcx
  int ItemDest; // esi
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // ebx
  BOOL v20; // eax
  int v21; // eax
  NTSTATUS LastNtStatus; // ebx
  __int64 v23; // r8
  unsigned int v24; // r9d
  DWORD FileAttributesW; // eax
  DWORD v26; // eax
  __int64 v27; // rcx
  signed int NamedSecurityInfoW; // eax
  void *v29; // rcx
  int v30; // ebx
  int Error; // ebx
  char v32; // [rsp+40h] [rbp-39h]
  int v34; // [rsp+48h] [rbp-31h]
  int v35; // [rsp+4Ch] [rbp-2Dh]
  PACL pAcl; // [rsp+58h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  WORD pControl[2]; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwRevision; // [rsp+6Ch] [rbp-Dh] BYREF
  __int64 v41; // [rsp+70h] [rbp-9h] BYREF
  int v42; // [rsp+78h] [rbp-1h]
  void *v43; // [rsp+80h] [rbp+7h]
  _BYTE v44[16]; // [rsp+88h] [rbp+Fh] BYREF

  *a4 = 0;
  v5 = *((_QWORD *)this + 9);
  v7 = a2;
  if ( v5 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
               v5,
               0,
               0,
               0,
               0,
               0,
               0);
    if ( (int)result < 0 )
      return result;
  }
  if ( PathIsRootW(*((LPCWSTR *)this + 27)) )
    return 2150039583LL;
  if ( !*((_QWORD *)this + 33) )
    return 2147942417LL;
  v35 = v7 & 4;
  if ( (v7 & 4) == 0 && !SHRestricted(REST_NOENCRYPTONMOVE) )
  {
    v9 = *((_DWORD *)this + 56);
    if ( (v9 & 4) == 0 && (v9 & 0x4000) == 0 )
    {
      FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 33));
      if ( FileAttributesW != -1 && (FileAttributesW & 0x4000) != 0 )
      {
        v41 = *((_QWORD *)this + 33);
        v43 = 0;
        v42 = 0;
        if ( CEfsUtil::IsDpapiNgProtectedFile((CEfsUtil *)&v41) )
        {
          operator delete(v43, (const struct std::nothrow_t *)1);
          return 2147942417LL;
        }
        operator delete(v43, (const struct std::nothrow_t *)1);
      }
    }
  }
  v10 = (const WCHAR *)*((_QWORD *)this + 33);
  v11 = (const WCHAR *)*((_QWORD *)this + 27);
  pAcl = 0;
  hMem = 0;
  pControl[0] = 0;
  if ( !PathIsSameRootW(v11, v10) )
    return 2147942417LL;
  v12 = 2;
  v34 = 0;
  v32 = 0;
  if ( *((_DWORD *)this + 42) != 1 )
  {
    v13 = -2147467259;
    goto LABEL_12;
  }
  if ( !CFSTransfer::_IsMoveSecurityAttributesEnabled() && !a3 )
  {
    v32 = 1;
    goto LABEL_79;
  }
  if ( (v7 & 8) != 0 )
  {
LABEL_79:
    v13 = CTLocalAllocPolicy::Alloc(v29, 0x40u, 8u, (void **)&pAcl);
    if ( v13 >= 0 )
    {
      v34 = 1;
      v13 = !InitializeAcl(pAcl, 8u, 2u) ? 0x80004005 : 0;
    }
    goto LABEL_12;
  }
  NamedSecurityInfoW = GetNamedSecurityInfoW(*((LPCWSTR *)this + 27), SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem);
  v13 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v13 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v13 >= 0 )
  {
    dwRevision = 0;
    GetSecurityDescriptorControl(hMem, pControl, &dwRevision);
  }
LABEL_12:
  AvoidCurrentDirectory(*((LPCWCH *)this + 27));
  v14 = IsFolderNotStreamItem(*((struct IShellItem **)this + 26));
  do
  {
    v15 = *((_QWORD *)this + 9);
    if ( v15 )
    {
      ItemDest = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
                   v15,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0);
      if ( ItemDest < 0 )
        break;
    }
    ItemDest = *((_DWORD *)this + 205);
    if ( ItemDest >= 0 )
    {
      if ( *((_DWORD *)this + 42) != 1
        || (*((_DWORD *)this + 56) & 0x4000) != 0
        || (ItemDest = CFSTransfer::_CheckEncryptionDest(this), ItemDest >= 0) )
      {
        v19 = !IsFolderNotStreamItem(*((struct IShellItem **)this + 26)) && (a2 & 2) != 0;
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x400000) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_Shell_Core_Provider_Context,
            Shell32_CopyEngine_CallMoveFile_Start,
            v18,
            1,
            v44);
        if ( *((_DWORD *)this + 46) || CFSTransfer::IsFileAvailableOnlineOnly(this) )
        {
          if ( CFSTransfer::IsFileAvailableOnlineOnly(this) || *((_DWORD *)this + 46) )
            v19 |= 2u;
          v21 = MoveFileWithUsnSourceInfo(
                  *((const unsigned __int16 **)this + 27),
                  *((const unsigned __int16 **)this + 34),
                  v19,
                  *((_DWORD *)this + 46));
        }
        else
        {
          v20 = MoveFileExW(*((LPCWSTR *)this + 27), *((LPCWSTR *)this + 34), v19);
          v21 = ResultFromWin32Bool(v20);
        }
        ItemDest = v21;
        LastNtStatus = RtlGetLastNtStatus();
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x400000) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_Shell_Core_Provider_Context,
            Shell32_CopyEngine_CallMoveFile_Stop,
            v23,
            1,
            &v41);
        if ( ItemDest < 0 )
        {
          if ( LastNtStatus == -1073741638 && ItemDest == -2147024891 )
          {
            ItemDest = -2147024879;
            break;
          }
          if ( v14 && ItemDest == -2147024891 && (unsigned int)CFSTransfer::_HasMoveAccess(this) )
          {
            ItemDest = -2147024864;
            break;
          }
          v30 = ItemDest;
          ItemDest = CFSTransfer::_HandleBaseApiErrors(this, ItemDest, a2, v24, 0);
          if ( ItemDest == 2555907 )
          {
            ItemDest = v30;
            break;
          }
        }
      }
    }
  }
  while ( ItemDest == 2555908 );
  if ( (unsigned int)ShouldProceedWithOperation(ItemDest) )
  {
    if ( (unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent() )
    {
      if ( !v35 && !SHRestricted(REST_NOENCRYPTONMOVE) )
      {
        v17 = *((_DWORD *)this + 56);
        if ( (v17 & 4) == 0 && (v17 & 0x4000) == 0 )
        {
          v26 = GetFileAttributesW(*((LPCWSTR *)this + 33));
          if ( v26 != -1 && (v26 & 0x4000) != 0 )
          {
            v27 = *((_QWORD *)this + 34);
            if ( v14 )
            {
              SHELL32_EncryptDirectory(v27);
            }
            else if ( !(unsigned int)SHELL32_SHEncryptFile(v27, 1, 0, *((_QWORD *)this + 107)) )
            {
              Error = ResultFromKnownLastError();
              SHMoveFile(*((LPCVOID *)this + 34), *((LPCVOID *)this + 27), v14 ? 0x20000 : 1);
              ItemDest = -2147018896;
              if ( Error == -2147023673 )
                ItemDest = -2144927744;
            }
          }
        }
      }
    }
    if ( v13 >= 0 && pAcl )
    {
      if ( !v32 )
        v12 = (a2 & 8) == 0;
      CFSTransfer::_ResetInheritedACL(this, pAcl, pControl[0], v12);
    }
    if ( PathMatchSpecW(*((LPCWSTR *)this + 34), L"*.ini;*.url") )
    {
      SHFlushPrivateProfile(*((_QWORD *)this + 34));
      if ( !StrCmpICW((LPCWSTR)this + 148, L"desktop.ini") )
        SHChangeNotify(0x2000, 5u, *((LPCVOID *)this + 33), 0);
    }
    if ( ItemDest != -2144927744 )
    {
      ItemDest = CFSTransfer::_GetItemDest(this, (const unsigned __int16 *)this + 148, *((_DWORD *)this + 56), a4);
      if ( ItemDest >= 0 )
        ItemDest = 2555912;
    }
  }
  if ( v34 )
    LocalFree(pAcl);
  LocalFree(hMem);
  return (unsigned int)ItemDest;
}

```

## disassembly

```asm
0x180215b78  mov     [rsp-8+arg_10], rbx
0x180215b7d  push    rbp
0x180215b7e  push    rsi
0x180215b7f  push    rdi
0x180215b80  push    r12
0x180215b82  push    r13
0x180215b84  push    r14
0x180215b86  push    r15
0x180215b88  lea     rbp, [rsp-27h]
0x180215b8d  sub     rsp, 0A0h
0x180215b94  mov     rax, cs:__security_cookie
0x180215b9b  xor     rax, rsp
0x180215b9e  mov     [rbp+57h+var_38], rax
0x180215ba2  xor     r12d, r12d
0x180215ba5  mov     [rbp+57h+var_80], r9
0x180215ba9  mov     [r9], r12
0x180215bac  mov     rdi, rcx
0x180215baf  mov     rcx, [rcx+48h]
0x180215bb3  mov     bl, r8b
0x180215bb6  mov     [rbp+57h+var_8C], edx
0x180215bb9  mov     esi, edx
0x180215bbb  test    rcx, rcx
0x180215bbe  jz      short loc_180215BEB
0x180215bc0  mov     rax, [rcx]
0x180215bc3  xor     r9d, r9d
0x180215bc6  mov     dword ptr [rsp+0D0h+ppSacl], r12d
0x180215bcb  xor     r8d, r8d
0x180215bce  mov     dword ptr [rsp+0D0h+ppDacl], r12d
0x180215bd3  xor     edx, edx
0x180215bd5  mov     dword ptr [rsp+0D0h+ppsidGroup], r12d
0x180215bda  mov     rax, [rax+18h]
0x180215bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215be3  test    eax, eax
0x180215be5  js      loc_180215D79
0x180215beb  mov     rcx, [rdi+0D8h]; pszPath
0x180215bf2  call    cs:__imp_PathIsRootW
0x180215bf8  test    eax, eax
0x180215bfa  jnz     loc_180215F5D
0x180215c00  cmp     [rdi+108h], r12
0x180215c07  jz      loc_180215EAF
0x180215c0d  mov     eax, esi
0x180215c0f  mov     r13d, 1
0x180215c15  and     eax, 4
0x180215c18  mov     [rbp+57h+var_84], eax
0x180215c1b  jnz     short loc_180215C3F
0x180215c1d  mov     ecx, 40000045h; rest
0x180215c22  call    SHRestricted
0x180215c27  test    eax, eax
0x180215c29  jnz     short loc_180215C3F
0x180215c2b  mov     eax, [rdi+0E0h]
0x180215c31  test    al, 4
0x180215c33  jnz     short loc_180215C3F
0x180215c35  bt      eax, 0Eh
0x180215c39  jnb     loc_180215E5F
0x180215c3f  mov     rdx, [rdi+108h]; pszPath2
0x180215c46  mov     rcx, [rdi+0D8h]; pszPath1
0x180215c4d  mov     [rbp+57h+pAcl], r12
0x180215c51  mov     [rbp+57h+hMem], r12
0x180215c55  mov     [rbp+57h+pControl], r12w
0x180215c5a  call    cs:__imp_PathIsSameRootW
0x180215c60  test    eax, eax
0x180215c62  jz      loc_180215EAF
0x180215c68  mov     r15d, 2
0x180215c6e  mov     [rbp+57h+var_88], r12d
0x180215c72  mov     [rbp+57h+var_90], r12b
0x180215c76  cmp     [rdi+0A8h], r13d
0x180215c7d  jz      loc_180215F67
0x180215c83  mov     r14d, 80004005h
0x180215c89  mov     rcx, [rdi+0D8h]; lpString2
0x180215c90  call    ?AvoidCurrentDirectory@@YAXPEBG@Z; AvoidCurrentDirectory(ushort const *)
0x180215c95  mov     rcx, [rdi+0D0h]; struct IShellItem *
0x180215c9c  call    ?IsFolderNotStreamItem@@YA_NPEAUIShellItem@@@Z; IsFolderNotStreamItem(IShellItem *)
0x180215ca1  mov     cl, al
0x180215ca3  mov     r13b, al
0x180215ca6  neg     cl
0x180215ca8  sbb     r12d, r12d
0x180215cab  and     r12d, 1FFFFh
0x180215cb2  mov     rcx, [rdi+48h]
0x180215cb6  test    rcx, rcx
0x180215cb9  jz      loc_180215DA0
0x180215cbf  mov     rax, [rcx]
0x180215cc2  xor     r9d, r9d
0x180215cc5  mov     dword ptr [rsp+0D0h+ppSacl], 0
0x180215ccd  xor     r8d, r8d
0x180215cd0  mov     dword ptr [rsp+0D0h+ppDacl], 0
0x180215cd8  xor     edx, edx
0x180215cda  mov     dword ptr [rsp+0D0h+ppsidGroup], 0
0x180215ce2  mov     rax, [rax+18h]
0x180215ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215ceb  mov     esi, eax
0x180215ced  test    eax, eax
0x180215cef  jns     loc_180215DA0
0x180215cf5  mov     ecx, esi; int
0x180215cf7  call    ?ShouldProceedWithOperation@@YAHJ@Z; ShouldProceedWithOperation(long)
0x180215cfc  test    eax, eax
0x180215cfe  jz      short loc_180215D63
0x180215d00  call    IsSHELL32_SHIsVirtualDevicePresent
0x180215d05  mov     ebx, 80270000h
0x180215d0a  test    al, al
0x180215d0c  jz      short loc_180215D36
0x180215d0e  cmp     [rbp+57h+var_84], 0
0x180215d12  jnz     short loc_180215D36
0x180215d14  mov     ecx, 40000045h; rest
0x180215d19  call    SHRestricted
0x180215d1e  test    eax, eax
0x180215d20  jnz     short loc_180215D36
0x180215d22  mov     eax, [rdi+0E0h]
0x180215d28  test    al, 4
0x180215d2a  jnz     short loc_180215D36
0x180215d2c  bt      eax, 0Eh
0x180215d30  jnb     loc_180215EB9
0x180215d36  test    r14d, r14d
0x180215d39  jns     loc_18021602B
0x180215d3f  mov     rcx, [rdi+110h]; pszFile
0x180215d46  lea     rdx, pszSpec; "*.ini;*.url"
0x180215d4d  call    cs:__imp_PathMatchSpecW
0x180215d53  test    eax, eax
0x180215d55  jnz     loc_180216059
0x180215d5b  cmp     esi, ebx
0x180215d5d  jnz     loc_18021609D
0x180215d63  cmp     [rbp+57h+var_88], 0
0x180215d67  jnz     loc_1802160C8
0x180215d6d  mov     rcx, [rbp+57h+hMem]; hMem
0x180215d71  call    cs:__imp_LocalFree
0x180215d77  mov     eax, esi
0x180215d79  mov     rcx, [rbp+57h+var_38]
0x180215d7d  xor     rcx, rsp; StackCookie
0x180215d80  call    __security_check_cookie
0x180215d85  mov     rbx, [rsp+0D0h+arg_10]
0x180215d8d  add     rsp, 0A0h
0x180215d94  pop     r15
0x180215d96  pop     r14
0x180215d98  pop     r13
0x180215d9a  pop     r12
0x180215d9c  pop     rdi
0x180215d9d  pop     rsi
0x180215d9e  pop     rbp
0x180215d9f  retn
0x180215da0  mov     esi, [rdi+334h]
0x180215da6  test    esi, esi
0x180215da8  js      loc_180215E4E
0x180215dae  cmp     dword ptr [rdi+0A8h], 1
0x180215db5  jnz     short loc_180215DD1
0x180215db7  test    dword ptr [rdi+0E0h], 4000h
0x180215dc1  jnz     short loc_180215DD1
0x180215dc3  mov     rcx, rdi; this
0x180215dc6  call    ?_CheckEncryptionDest@CFSTransfer@@AEAAJXZ; CFSTransfer::_CheckEncryptionDest(void)
0x180215dcb  mov     esi, eax
0x180215dcd  test    eax, eax
0x180215dcf  js      short loc_180215E4E
0x180215dd1  mov     rcx, [rdi+0D0h]; struct IShellItem *
0x180215dd8  call    ?IsFolderNotStreamItem@@YA_NPEAUIShellItem@@@Z; IsFolderNotStreamItem(IShellItem *)
0x180215ddd  test    al, al
0x180215ddf  jz      loc_180215F85
0x180215de5  xor     ebx, ebx
0x180215de7  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 40h
0x180215dee  jnz     loc_180215F99
0x180215df4  cmp     dword ptr [rdi+0B8h], 0
0x180215dfb  jnz     loc_180215FC0
0x180215e01  mov     rcx, rdi; this
0x180215e04  call    ?IsFileAvailableOnlineOnly@CFSTransfer@@AEAA_NXZ; CFSTransfer::IsFileAvailableOnlineOnly(void)
0x180215e09  test    al, al
0x180215e0b  jnz     loc_180215FC0
0x180215e11  mov     rdx, [rdi+110h]; lpNewFileName
0x180215e18  mov     r8d, ebx; dwFlags
0x180215e1b  mov     rcx, [rdi+0D8h]; lpExistingFileName
0x180215e22  call    cs:__imp_MoveFileExW
0x180215e28  mov     ecx, eax; int
0x180215e2a  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180215e2f  mov     esi, eax
0x180215e31  call    cs:__imp_RtlGetLastNtStatus
0x180215e37  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 40h
0x180215e3e  mov     ebx, eax
0x180215e40  jnz     loc_180215FE2
0x180215e46  test    esi, esi
0x180215e48  js      loc_180216009
0x180215e4e  cmp     esi, 270004h
0x180215e54  jnz     loc_180215CF5
0x180215e5a  jmp     loc_180215CB2
0x180215e5f  mov     rcx, [rdi+108h]; lpFileName
0x180215e66  call    cs:__imp_GetFileAttributesW
0x180215e6c  cmp     eax, 0FFFFFFFFh
0x180215e6f  jz      loc_180215C3F
0x180215e75  bt      eax, 0Eh
0x180215e79  jnb     loc_180215C3F
0x180215e7f  mov     rax, [rdi+108h]
0x180215e86  lea     rcx, [rbp+57h+var_60]; this
0x180215e8a  mov     [rbp+57h+var_60], rax
0x180215e8e  mov     [rbp+57h+var_50], r12
0x180215e92  mov     [rbp+57h+var_58], r12d
0x180215e96  call    ?IsDpapiNgProtectedFile@CEfsUtil@@QEAA_NXZ; CEfsUtil::IsDpapiNgProtectedFile(void)
0x180215e9b  mov     rcx, [rbp+57h+var_50]; void *
0x180215e9f  mov     rdx, r13; struct std::nothrow_t *
0x180215ea2  test    al, al
0x180215ea4  jz      loc_18065100A
0x180215eaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180215eaf  mov     eax, 80070011h
0x180215eb4  jmp     loc_180215D79
0x180215eb9  mov     rcx, [rdi+108h]; lpFileName
0x180215ec0  call    cs:__imp_GetFileAttributesW
0x180215ec6  cmp     eax, 0FFFFFFFFh
0x180215ec9  jz      loc_180215D36
0x180215ecf  bt      eax, 0Eh
0x180215ed3  jnb     loc_180215D36
0x180215ed9  mov     rcx, [rdi+110h]
0x180215ee0  test    r13b, r13b
0x180215ee3  jz      loc_1806510DC
0x180215ee9  call    cs:__imp_SHELL32_EncryptDirectory
0x180215eef  jmp     loc_180215D36
0x180215ef4  mov     rcx, [rdi+0D8h]; pObjectName
0x180215efb  lea     rax, [rbp+57h+hMem]
0x180215eff  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180215f04  xor     r9d, r9d; ppsidOwner
0x180215f07  lea     rax, [rbp+57h+pAcl]
0x180215f0b  mov     [rsp+0D0h+ppSacl], r12; ppSacl
0x180215f10  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x180215f15  mov     edx, r13d; ObjectType
0x180215f18  mov     [rsp+0D0h+ppsidGroup], r12; ppsidGroup
0x180215f1d  lea     r8d, [r9+4]; SecurityInfo
0x180215f21  call    cs:__imp_GetNamedSecurityInfoW
0x180215f27  mov     r14d, eax
0x180215f2a  test    eax, eax
0x180215f2c  jle     short loc_180215F39
0x180215f2e  movzx   r14d, ax
0x180215f32  or      r14d, 80070000h
0x180215f39  test    r14d, r14d
0x180215f3c  js      loc_180215C89
0x180215f42  mov     rcx, [rbp+57h+hMem]; pSecurityDescriptor
0x180215f46  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180215f4a  lea     rdx, [rbp+57h+pControl]; pControl
0x180215f4e  mov     [rbp+57h+dwRevision], r12d
0x180215f52  call    cs:__imp_GetSecurityDescriptorControl
0x180215f58  jmp     loc_180215C89
0x180215f5d  mov     eax, 8027001Fh
0x180215f62  jmp     loc_180215D79
0x180215f67  call    ?_IsMoveSecurityAttributesEnabled@CFSTransfer@@CA_NXZ; CFSTransfer::_IsMoveSecurityAttributesEnabled(void)
0x180215f6c  test    al, al
0x180215f6e  jnz     loc_180651015
0x180215f74  test    bl, bl
0x180215f76  jnz     loc_180651015
0x180215f7c  mov     [rbp+57h+var_90], r13b
0x180215f80  jmp     loc_18065101F
0x180215f85  test    byte ptr [rbp+57h+var_8C], r15b
0x180215f89  jz      loc_180215DE5
0x180215f8f  mov     ebx, 1
0x180215f94  jmp     loc_180215DE7
0x180215f99  lea     rax, [rbp+57h+var_48]
0x180215f9d  mov     r9d, 1
0x180215fa3  lea     rdx, Shell32_CopyEngine_CallMoveFile_Start
0x180215faa  mov     [rsp+0D0h+ppsidGroup], rax
0x180215faf  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180215fb6  call    McGenEventWrite_EventWriteTransfer
0x180215fbb  jmp     loc_180215DF4
0x180215fc0  mov     rcx, rdi; this
0x180215fc3  call    ?IsFileAvailableOnlineOnly@CFSTransfer@@AEAA_NXZ; CFSTransfer::IsFileAvailableOnlineOnly(void)
0x180215fc8  test    al, al
0x180215fca  jnz     loc_180651066
0x180215fd0  cmp     dword ptr [rdi+0B8h], 0
0x180215fd7  jnz     loc_180651066
0x180215fdd  jmp     loc_180651069
0x180215fe2  lea     rax, [rbp+57h+var_60]
0x180215fe6  mov     r9d, 1
0x180215fec  lea     rdx, Shell32_CopyEngine_CallMoveFile_Stop
0x180215ff3  mov     [rsp+0D0h+ppsidGroup], rax
0x180215ff8  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180215fff  call    McGenEventWrite_EventWriteTransfer
0x180216004  jmp     loc_180215E46
0x180216009  cmp     ebx, 0C00000BAh
0x18021600f  jnz     loc_18065108C
0x180216015  cmp     esi, 80070005h
0x18021601b  jnz     loc_18065108C
0x180216021  mov     esi, 80070011h
0x180216026  jmp     loc_180215CF5
0x18021602b  mov     rdx, [rbp+57h+pAcl]; pDacl
0x18021602f  test    rdx, rdx
0x180216032  jz      loc_180215D3F
0x180216038  cmp     [rbp+57h+var_90], 0
0x18021603c  jnz     loc_18065112F
0x180216042  test    byte ptr [rbp+57h+var_8C], 8
0x180216046  mov     r15d, 1
0x18021604c  lea     eax, [r15-1]
0x180216050  cmovnz  r15d, eax
0x180216054  jmp     loc_18065112F
0x180216059  mov     rcx, [rdi+110h]
0x180216060  call    SHFlushPrivateProfile
0x180216065  lea     rcx, [rdi+128h]; pszStr1
0x18021606c  lea     rdx, aDesktopIni_0; "desktop.ini"
0x180216073  call    cs:__imp_StrCmpICW
0x180216079  test    eax, eax
0x18021607b  jnz     loc_180215D5B
0x180216081  mov     r8, [rdi+108h]; dwItem1
0x180216088  lea     edx, [rax+5]; uFlags
0x18021608b  xor     r9d, r9d; dwItem2
0x18021608e  mov     ecx, 2000h; wEventId
0x180216093  call    SHChangeNotify
0x180216098  jmp     loc_180215D5B
0x18021609d  mov     r9, [rbp+57h+var_80]; struct IShellItem **
0x1802160a1  lea     rdx, [rdi+128h]; unsigned __int16 *
0x1802160a8  mov     r8d, [rdi+0E0h]; unsigned int
0x1802160af  mov     rcx, rdi; this
  ... truncated ...
```
