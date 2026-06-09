# CFSFolder::_GetSize(CFSFolder *,_ITEMID_CHILD const *,IDFOLDER const *,tagPROPVARIANT *)

- ea: `0x180092990`
- end: `0x180092d80`
- name: `?_GetSize@CFSFolder@@KAJPEAV1@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@PEAUtagPROPVARIANT@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(struct CFSFolder *, const struct _ITEMID_CHILD *, const struct IDFOLDER *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1805159d8`
- `0x180515e60`

## callees

- `0x180043320`
- `0x180092990`
- `0x180093d60`
- `0x180093ef0`
- `0x1800a3080`
- `0x1800b72b0`
- `0x1800d13a0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180092a38`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180092a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092c18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092c18`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180092ae9`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180092ae9`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180092d5c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180092d5c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180092aa7`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180092aa7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180092a8a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180092a8a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180092bfa`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180092bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092bd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092ce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092bd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092ce3`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180092a9e`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180092a9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFSFolder::_GetSize(
        struct CFSFolder *a1,
        const struct _ITEMID_CHILD *a2,
        const struct IDFOLDER *a3,
        struct tagPROPVARIANT *a4)
{
  BOOL v8; // r12d
  unsigned int ReparsePointTag; // ebx
  unsigned int FullFileAttributes; // eax
  int (__fastcall *v11)(char *, const struct IDFOLDER *, __int64, __int64); // rbx
  __int64 v12; // rax
  int DriveNumberW; // eax
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v21; // rdx
  LARGE_INTEGER v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD v26[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v27; // [rsp+40h] [rbp-C0h]
  LPVOID v28; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  LPCWSTR pszPath; // [rsp+2E0h] [rbp+1E0h] BYREF
  PWSTR v36; // [rsp+2E8h] [rbp+1E8h] BYREF
  WCHAR pszRoot[4]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR DirectoryName[264]; // [rsp+370h] [rbp+270h] BYREF

  DirectoryName[0] = 0;
  if ( (GetFullFileAttributes(a3) & 0x400) == 0 )
    goto LABEL_26;
  v8 = 0;
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v26, a1, a3, a3);
  if ( a3 )
  {
    if ( CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v26) != -1610612724 )
    {
      ReparsePointTag = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v26);
      FullFileAttributes = GetFullFileAttributes(a3);
      if ( !(unsigned __int8)RtlIsCloudFilesPlaceholder(FullFileAttributes, ReparsePointTag) )
      {
        pszPath = 0;
        v11 = *(int (__fastcall **)(char *, const struct IDFOLDER *, __int64, __int64))(*((_QWORD *)a1 + 39) + 112LL);
        v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
        if ( v11((char *)a1 + 312, a3, 1, v12) >= 0 )
        {
          DriveNumberW = PathGetDriveNumberW(pszPath);
          if ( DriveNumberW != -1 )
          {
            v14 = PathBuildRootW(pszRoot, DriveNumberW);
            if ( GetDriveTypeW(v14) != 4 )
            {
              v15 = -1;
              do
                ++v15;
              while ( pszPath[v15] );
              v16 = v15 + 1;
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v36,
                pszPath,
                v15 + 1);
              PathCchAddBackslash(v36, v16 + 1);
              if ( v36 )
              {
                if ( GetVolumeNameForVolumeMountPointW(v36, szVolumeName, 0x32u) )
                  v8 = (int)StringCchCopyW(DirectoryName, 0x104u, v36) >= 0;
                if ( v36 )
                  LocalFree(v36);
              }
            }
          }
        }
        if ( pszPath )
          CoTaskMemFree((LPVOID)pszPath);
      }
    }
  }
  v26[0] = &CFileSysItemString::`vftable';
  v17 = v32;
  v32 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = v30;
  v30 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = v31;
  v31 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v28 )
    CoTaskMemFree(v28);
  if ( v27 )
    CoTaskMemFree(v27);
  if ( v8 )
  {
    *(_QWORD *)pszRoot = 0;
    pszPath = 0;
    v36 = 0;
    if ( GetDiskFreeSpaceExW(DirectoryName, (PULARGE_INTEGER)pszRoot, (PULARGE_INTEGER)&pszPath, (PULARGE_INTEGER)&v36) )
    {
      a4->vt = 21;
      a4->hVal.QuadPart = (LONGLONG)pszPath;
    }
  }
  else
  {
LABEL_26:
    if ( (((*((_BYTE *)a3 + 2) & 0x37) - 49) & 0xFB) != 0 )
    {
      CFileSysItemString::CFileSysItemString((CFileSysItemString *)v26, a1, a2, a3);
      if ( v34 && *(_WORD *)(v34 + 2) >= 7u )
        v21 = (unsigned __int64)*(unsigned int *)(v34 + 28) << 32;
      else
        v21 = 0;
      v22.QuadPart = v21 + *(unsigned int *)(v33 + 4);
      if ( v22.QuadPart != -1 )
      {
        a4->vt = 21;
        a4->hVal = v22;
      }
      v26[0] = &CFileSysItemString::`vftable';
      v23 = v32;
      v32 = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v24 = v30;
      v30 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v25 = v31;
      v31 = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v28 )
        CoTaskMemFree(v28);
      if ( v27 )
        CoTaskMemFree(v27);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180092990  push    rbp
0x180092992  push    rbx
0x180092993  push    rsi
0x180092994  push    rdi
0x180092995  push    r12
0x180092997  push    r13
0x180092999  push    r14
0x18009299b  push    r15
0x18009299d  lea     rbp, [rsp-498h]
0x1800929a5  sub     rsp, 598h
0x1800929ac  mov     rax, cs:__security_cookie
0x1800929b3  xor     rax, rsp
0x1800929b6  mov     [rbp+4D0h+var_50], rax
0x1800929bd  mov     r14, r9
0x1800929c0  mov     rsi, r8
0x1800929c3  mov     r13, rdx
0x1800929c6  mov     r15, rcx
0x1800929c9  xor     edi, edi
0x1800929cb  mov     [rbp+4D0h+DirectoryName], di
0x1800929d2  mov     rcx, r8; struct IDFOLDER *
0x1800929d5  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x1800929da  lea     r12, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800929e1  bt      eax, 0Ah
0x1800929e5  jnb     loc_180092BA2
0x1800929eb  mov     r12d, edi
0x1800929ee  mov     r9, rsi; struct IDFOLDER *
0x1800929f1  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800929f4  mov     rdx, r15; struct CFSFolder *
0x1800929f7  lea     rcx, [rsp+5D0h+var_5A0]; this
0x1800929fc  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180092a01  nop
0x180092a02  test    rsi, rsi
0x180092a05  jz      loc_180092B13
0x180092a0b  lea     rcx, [rsp+5D0h+var_5A0]; this
0x180092a10  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x180092a15  cmp     eax, 0A000000Ch
0x180092a1a  jz      loc_180092B13
0x180092a20  lea     rcx, [rsp+5D0h+var_5A0]; this
0x180092a25  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x180092a2a  mov     ebx, eax
0x180092a2c  mov     rcx, rsi; struct IDFOLDER *
0x180092a2f  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180092a34  mov     edx, ebx
0x180092a36  mov     ecx, eax
0x180092a38  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x180092a3e  test    al, al
0x180092a40  jnz     loc_180092B13
0x180092a46  mov     [rbp+4D0h+pszPath], rdi
0x180092a4d  mov     rax, [r15+138h]
0x180092a54  mov     rbx, [rax+70h]
0x180092a58  lea     rcx, [rbp+4D0h+pszPath]
0x180092a5f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180092a64  mov     r9, rax
0x180092a67  mov     r8d, 1
0x180092a6d  mov     rdx, rsi
0x180092a70  lea     rcx, [r15+138h]
0x180092a77  mov     rax, rbx
0x180092a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a7f  test    eax, eax
0x180092a81  js      short loc_180092AFF
0x180092a83  mov     rcx, [rbp+4D0h+pszPath]; pszPath
0x180092a8a  call    cs:__imp_PathGetDriveNumberW
0x180092a90  cmp     eax, 0FFFFFFFFh
0x180092a93  jz      short loc_180092AFF
0x180092a95  mov     edx, eax; iDrive
0x180092a97  lea     rcx, [rbp+4D0h+pszRoot]; pszRoot
0x180092a9e  call    cs:__imp_PathBuildRootW
0x180092aa4  mov     rcx, rax; lpRootPathName
0x180092aa7  call    cs:__imp_GetDriveTypeW
0x180092aad  cmp     eax, 4
0x180092ab0  jz      short loc_180092AFF
0x180092ab2  mov     rdx, [rbp+4D0h+pszPath]
0x180092ab9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180092ac0  lea     rax, [rax+1]
0x180092ac4  cmp     word ptr [rdx+rax*2], 0
0x180092ac9  jnz     short loc_180092AC0
0x180092acb  lea     rbx, [rax+1]
0x180092acf  mov     r8, rbx
0x180092ad2  lea     rcx, [rbp+4D0h+var_2E8]
0x180092ad9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180092ade  lea     rdx, [rbx+1]; cchPath
0x180092ae2  mov     rcx, [rbp+4D0h+var_2E8]; pszPath
0x180092ae9  call    cs:__imp_PathCchAddBackslash
0x180092aef  mov     rcx, [rbp+4D0h+var_2E8]; lpszVolumeMountPoint
0x180092af6  test    rcx, rcx
0x180092af9  jnz     loc_180092BED
0x180092aff  mov     rcx, [rbp+4D0h+pszPath]; pv
0x180092b06  test    rcx, rcx
0x180092b09  jz      short loc_180092B11
0x180092b0b  call    cs:__imp_CoTaskMemFree
0x180092b11  xor     edi, edi
0x180092b13  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180092b1a  mov     [rsp+5D0h+var_5A0], rax
0x180092b1f  mov     rcx, [rsp+5D0h+var_558]
0x180092b24  mov     [rsp+5D0h+var_558], rdi
0x180092b29  test    rcx, rcx
0x180092b2c  jz      short loc_180092B3A
0x180092b2e  mov     rax, [rcx]
0x180092b31  mov     rax, [rax+10h]
0x180092b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b3a  mov     rcx, [rsp+5D0h+var_568]
0x180092b3f  mov     [rsp+5D0h+var_568], rdi
0x180092b44  test    rcx, rcx
0x180092b47  jnz     loc_180092BDC
0x180092b4d  mov     rcx, [rsp+5D0h+var_560]
0x180092b52  mov     [rsp+5D0h+var_560], rdi
0x180092b57  test    rcx, rcx
0x180092b5a  jz      short loc_180092B68
0x180092b5c  mov     rax, [rcx]
0x180092b5f  mov     rax, [rax+10h]
0x180092b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b68  mov     rcx, [rsp+5D0h+pv]; pv
0x180092b6d  test    rcx, rcx
0x180092b70  jz      short loc_180092B78
0x180092b72  call    cs:__imp_CoTaskMemFree
0x180092b78  mov     rcx, [rsp+5D0h+var_588]; pv
0x180092b7d  test    rcx, rcx
0x180092b80  jz      short loc_180092B88
0x180092b82  call    cs:__imp_CoTaskMemFree
0x180092b88  mov     rcx, [rsp+5D0h+var_590]; pv
0x180092b8d  test    rcx, rcx
0x180092b90  jnz     short loc_180092BD3
0x180092b92  test    r12d, r12d
0x180092b95  jnz     loc_180092D2B
0x180092b9b  lea     r12, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180092ba2  movzx   eax, byte ptr [rsi+2]
0x180092ba6  and     al, 37h
0x180092ba8  sub     al, 31h ; '1'
0x180092baa  test    al, 0FBh
0x180092bac  jnz     short loc_180092C23
0x180092bae  xor     eax, eax
0x180092bb0  mov     rcx, [rbp+4D0h+var_50]
0x180092bb7  xor     rcx, rsp; StackCookie
0x180092bba  call    __security_check_cookie
0x180092bbf  add     rsp, 598h
0x180092bc6  pop     r15
0x180092bc8  pop     r14
0x180092bca  pop     r13
0x180092bcc  pop     r12
0x180092bce  pop     rdi
0x180092bcf  pop     rsi
0x180092bd0  pop     rbx
0x180092bd1  pop     rbp
0x180092bd2  retn
0x180092bd3  call    cs:__imp_CoTaskMemFree
0x180092bd9  nop
0x180092bda  jmp     short loc_180092B92
0x180092bdc  mov     rax, [rcx]
0x180092bdf  mov     rax, [rax+10h]
0x180092be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092be8  jmp     loc_180092B4D
0x180092bed  mov     r8d, 32h ; '2'; cchBufferLength
0x180092bf3  lea     rdx, [rbp+4D0h+szVolumeName]; lpszVolumeName
0x180092bfa  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180092c00  test    eax, eax
0x180092c02  jnz     loc_180092D05
0x180092c08  mov     rcx, [rbp+4D0h+var_2E8]; hMem
0x180092c0f  test    rcx, rcx
0x180092c12  jz      loc_180092AFF
0x180092c18  call    cs:__imp_LocalFree
0x180092c1e  jmp     loc_180092AFF
0x180092c23  mov     r9, rsi; struct IDFOLDER *
0x180092c26  mov     r8, r13; struct _ITEMIDLIST_RELATIVE *
0x180092c29  mov     rdx, r15; struct CFSFolder *
0x180092c2c  lea     rcx, [rsp+5D0h+var_5A0]; this
0x180092c31  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180092c36  mov     rax, [rbp+4D0h+var_548]
0x180092c3a  test    rax, rax
0x180092c3d  jz      loc_180092CFD
0x180092c43  cmp     word ptr [rax+2], 7
0x180092c48  jb      loc_180092CFD
0x180092c4e  mov     edx, [rax+1Ch]
0x180092c51  shl     rdx, 20h
0x180092c55  mov     rax, [rbp+4D0h+var_550]
0x180092c59  mov     eax, [rax+4]
0x180092c5c  add     rax, rdx
0x180092c5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180092c63  jz      short loc_180092C6F
0x180092c65  mov     word ptr [r14], 15h
0x180092c6b  mov     [r14+8], rax
0x180092c6f  mov     [rsp+5D0h+var_5A0], r12
0x180092c74  mov     rcx, [rsp+5D0h+var_558]
0x180092c79  mov     [rsp+5D0h+var_558], rdi
0x180092c7e  test    rcx, rcx
0x180092c81  jz      short loc_180092C8F
0x180092c83  mov     rax, [rcx]
0x180092c86  mov     rax, [rax+10h]
0x180092c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c8f  mov     rcx, [rsp+5D0h+var_568]
0x180092c94  mov     [rsp+5D0h+var_568], rdi
0x180092c99  test    rcx, rcx
0x180092c9c  jnz     short loc_180092CEF
0x180092c9e  mov     rcx, [rsp+5D0h+var_560]
0x180092ca3  mov     [rsp+5D0h+var_560], rdi
0x180092ca8  test    rcx, rcx
0x180092cab  jz      short loc_180092CB9
0x180092cad  mov     rax, [rcx]
0x180092cb0  mov     rax, [rax+10h]
0x180092cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092cb9  mov     rcx, [rsp+5D0h+pv]; pv
0x180092cbe  test    rcx, rcx
0x180092cc1  jz      short loc_180092CC9
0x180092cc3  call    cs:__imp_CoTaskMemFree
0x180092cc9  mov     rcx, [rsp+5D0h+var_588]; pv
0x180092cce  test    rcx, rcx
0x180092cd1  jz      short loc_180092CD9
0x180092cd3  call    cs:__imp_CoTaskMemFree
0x180092cd9  mov     rcx, [rsp+5D0h+var_590]; pv
0x180092cde  test    rcx, rcx
0x180092ce1  jz      short loc_180092CEA
0x180092ce3  call    cs:__imp_CoTaskMemFree
0x180092ce9  nop
0x180092cea  jmp     loc_180092BAE
0x180092cef  mov     rax, [rcx]
0x180092cf2  mov     rax, [rax+10h]
0x180092cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092cfb  jmp     short loc_180092C9E
0x180092cfd  mov     rdx, rdi
0x180092d00  jmp     loc_180092C55
0x180092d05  mov     r8, [rbp+4D0h+var_2E8]; unsigned __int16 *
0x180092d0c  mov     edx, 104h; unsigned __int64
0x180092d11  lea     rcx, [rbp+4D0h+DirectoryName]; unsigned __int16 *
0x180092d18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180092d1d  xor     r12d, r12d
0x180092d20  test    eax, eax
0x180092d22  setns   r12b
0x180092d26  jmp     loc_180092C08
0x180092d2b  mov     qword ptr [rbp+4D0h+pszRoot], rdi
0x180092d32  mov     [rbp+4D0h+pszPath], rdi
0x180092d39  mov     [rbp+4D0h+var_2E8], rdi
0x180092d40  lea     r9, [rbp+4D0h+var_2E8]; lpTotalNumberOfFreeBytes
0x180092d47  lea     r8, [rbp+4D0h+pszPath]; lpTotalNumberOfBytes
0x180092d4e  lea     rdx, [rbp+4D0h+pszRoot]; lpFreeBytesAvailableToCaller
0x180092d55  lea     rcx, [rbp+4D0h+DirectoryName]; lpDirectoryName
0x180092d5c  call    cs:__imp_GetDiskFreeSpaceExW
0x180092d62  test    eax, eax
0x180092d64  jz      loc_180092BAE
0x180092d6a  mov     word ptr [r14], 15h
0x180092d70  mov     rax, [rbp+4D0h+pszPath]
0x180092d77  mov     [r14+8], rax
0x180092d7b  jmp     loc_180092BAE
```
