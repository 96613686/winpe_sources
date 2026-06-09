# SaveStreamToSystemDataFolder(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,ushort const *,ushort const *,IStream *,SAVE_STREAM_MODE,ushort * *)

- ea: `0x180004ae8`
- end: `0x180004dfa`
- name: `?SaveStreamToSystemDataFolder@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@PEBG3PEAUIStream@@W4SAVE_STREAM_MODE@@PEAPEAG@Z`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007a540`

## callees

- `0x180004ae8`
- `0x180005270`
- `0x180006210`
- `0x18000af94`
- `0x18003aa84`
- `0x180043564`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004dcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004dcf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004bec`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004bec`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004db3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004db3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180004d0a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180004d0a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180004ceb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180004ceb`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004c40`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004c40`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c0b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c0b`

## pseudocode

```c
__int64 __fastcall SaveStreamToSystemDataFolder(
        void *a1,
        __int64 a2,
        char a3,
        const WCHAR *a4,
        const WCHAR *pszMore,
        IStream *pstm,
        __int64 a7,
        _QWORD *a8)
{
  int v10; // r15d
  int SharedSystemDataFolder; // eax
  signed int Error; // ebx
  WCHAR *v13; // rdx
  __int64 v14; // r8
  WCHAR *v15; // rcx
  __int64 v16; // rax
  WCHAR *v17; // rdx
  IStream *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h]
  IStream *pstmTo; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v29[264]; // [rsp+280h] [rbp+180h] BYREF

  v10 = a2;
  if ( a8 )
    *a8 = 0;
  if ( (a3 & 1) != 0 )
    SharedSystemDataFolder = GetSharedSystemDataFolder(a4, a2, v29);
  else
    SharedSystemDataFolder = GetSystemDataFolderForUser(a1, a4, a2, v29, v22, 1);
  Error = SharedSystemDataFolder;
  if ( SharedSystemDataFolder >= 0 )
  {
    v13 = v29;
    v14 = 260;
    v15 = pszPath;
    v16 = 2147483646;
    do
    {
      if ( !v16 )
        break;
      if ( !*v13 )
        break;
      *v15++ = *v13++;
      --v16;
      --v14;
    }
    while ( v14 );
    v17 = v15 - 1;
    Error = v14 == 0 ? 0x8007007A : 0;
    if ( v14 )
      v17 = v15;
    *v17 = 0;
    if ( v14 )
    {
      Error = PathCchAppend(pszPath, 0x104u, pszMore);
      if ( Error >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          ppv = 0;
          Error = SHCreateItemFromParsingName(v29, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( Error >= 0 )
          {
            v24 = 0;
            Error = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      0,
                      &BHID_SFObject,
                      &GUID_0000000b_0000_0000_c000_000000000046,
                      &v24);
            if ( Error < 0 )
              goto LABEL_33;
            pstmTo = 0;
            Error = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64, _QWORD, _DWORD, IStream **))(*(_QWORD *)v24 + 24LL))(
                      v24,
                      pszMore,
                      69633,
                      0,
                      0,
                      &pstmTo);
            if ( Error >= 0 )
            {
              Error = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 48LL))(pstmTo, 0);
              if ( Error >= 0 )
              {
                pui.QuadPart = 0;
                Error = IStream_Size(pstm, &pui);
                if ( Error >= 0 )
                {
                  if ( pui.HighPart )
                  {
                    Error = -2147317563;
                  }
                  else
                  {
                    Error = IStream_Copy(pstm, pstmTo, pui.LowPart);
                    if ( Error >= 0 )
                    {
                      Error = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 64LL))(pstmTo, 0);
                      if ( Error >= 0 )
                        Error = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
                    }
                  }
                }
              }
            }
            v18 = pstmTo;
            pstmTo = 0;
            if ( v18 )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v18 + 16LL))(v18);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            if ( Error < 0
              || (Error = _SetSecurityOnFileOrFolder(pszPath, StringSid, v10, a3), Error < 0)
              || a8 && (Error = _AllocString<CTCoAllocPolicy>(v20, v19, pszPath, a8), Error < 0) )
            {
LABEL_33:
              DeleteFileW(pszPath);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          LocalFree(StringSid);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004ae8  push    rbp
0x180004aea  push    rbx
0x180004aeb  push    rsi
0x180004aec  push    rdi
0x180004aed  push    r12
0x180004aef  push    r13
0x180004af1  push    r14
0x180004af3  push    r15
0x180004af5  lea     rbp, [rsp-3A8h]
0x180004afd  sub     rsp, 4A8h
0x180004b04  mov     rax, cs:__security_cookie
0x180004b0b  xor     rax, rsp
0x180004b0e  mov     [rbp+3E0h+var_50], rax
0x180004b15  mov     rdi, [rbp+3E0h+arg_38]
0x180004b1c  mov     rsi, rcx
0x180004b1f  mov     r12, [rbp+3E0h+pszMore]
0x180004b26  xor     ecx, ecx
0x180004b28  mov     r14, [rbp+3E0h+pstm]
0x180004b2f  mov     rax, r9
0x180004b32  mov     r13d, r8d
0x180004b35  mov     r15d, edx
0x180004b38  test    rdi, rdi
0x180004b3b  jz      short loc_180004B40
0x180004b3d  mov     [rdi], rcx
0x180004b40  test    r13b, 1
0x180004b44  jz      short loc_180004B57
0x180004b46  lea     r8, [rbp+3E0h+var_260]
0x180004b4d  mov     rcx, rax
0x180004b50  call    ?GetSharedSystemDataFolder@@YAJPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z
0x180004b55  jmp     short loc_180004B71
0x180004b57  lea     r9, [rbp+3E0h+var_260]
0x180004b5e  mov     byte ptr [rsp+4E0h+var_4B8], 1
0x180004b63  mov     r8d, r15d
0x180004b66  mov     rdx, rax
0x180004b69  mov     rcx, rsi
0x180004b6c  call    ?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z
0x180004b71  xor     r10d, r10d
0x180004b74  mov     ebx, eax
0x180004b76  test    eax, eax
0x180004b78  js      loc_180004DD5
0x180004b7e  mov     r11d, 104h
0x180004b84  lea     rdx, [rbp+3E0h+var_260]
0x180004b8b  mov     r8d, r11d
0x180004b8e  lea     rcx, [rsp+4E0h+pszPath]
0x180004b93  mov     eax, 7FFFFFFEh
0x180004b98  test    rax, rax
0x180004b9b  jz      short loc_180004BBC
0x180004b9d  movzx   r9d, word ptr [rdx]
0x180004ba1  test    r9w, r9w
0x180004ba5  jz      short loc_180004BBC
0x180004ba7  mov     [rcx], r9w
0x180004bab  add     rdx, 2
0x180004baf  add     rcx, 2
0x180004bb3  dec     rax
0x180004bb6  sub     r8, 1
0x180004bba  jnz     short loc_180004B98
0x180004bbc  mov     rax, r8
0x180004bbf  lea     rdx, [rcx-2]
0x180004bc3  neg     rax
0x180004bc6  sbb     ebx, ebx
0x180004bc8  not     ebx
0x180004bca  and     ebx, 8007007Ah
0x180004bd0  test    r8, r8
0x180004bd3  cmovnz  rdx, rcx
0x180004bd7  mov     [rdx], r10w
0x180004bdb  jz      loc_180004DD5
0x180004be1  mov     r8, r12; pszMore
0x180004be4  lea     rcx, [rsp+4E0h+pszPath]; pszPath
0x180004be9  mov     rdx, r11; cchPath
0x180004bec  call    cs:__imp_PathCchAppend
0x180004bf2  xor     ecx, ecx
0x180004bf4  mov     ebx, eax
0x180004bf6  test    eax, eax
0x180004bf8  js      loc_180004DD5
0x180004bfe  mov     [rsp+4E0h+StringSid], rcx
0x180004c03  lea     rdx, [rsp+4E0h+StringSid]; StringSid
0x180004c08  mov     rcx, rsi; Sid
0x180004c0b  call    cs:__imp_ConvertSidToStringSidW
0x180004c11  xor     esi, esi
0x180004c13  test    eax, eax
0x180004c15  jnz     short loc_180004C26
0x180004c17  call    ?ResultFromKnownLastError@@YAJXZ
0x180004c1c  mov     ebx, eax
0x180004c1e  test    eax, eax
0x180004c20  js      loc_180004DD5
0x180004c26  lea     r9, [rsp+4E0h+ppv]; ppv
0x180004c2b  mov     [rsp+4E0h+ppv], rsi
0x180004c30  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180004c37  xor     edx, edx; pbc
0x180004c39  lea     rcx, [rbp+3E0h+var_260]; pszPath
0x180004c40  call    cs:__imp_SHCreateItemFromParsingName
0x180004c46  mov     ebx, eax
0x180004c48  test    eax, eax
0x180004c4a  js      loc_180004DCA
0x180004c50  mov     rcx, [rsp+4E0h+ppv]
0x180004c55  lea     rdx, [rsp+4E0h+var_498]
0x180004c5a  mov     [rsp+4E0h+var_4C0], rdx
0x180004c5f  lea     r9, _GUID_0000000b_0000_0000_c000_000000000046
0x180004c66  lea     r8, BHID_SFObject
0x180004c6d  mov     [rsp+4E0h+var_498], rsi
0x180004c72  xor     edx, edx
0x180004c74  mov     rax, [rcx]
0x180004c77  mov     rax, [rax+18h]
0x180004c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c80  mov     ebx, eax
0x180004c82  test    eax, eax
0x180004c84  js      loc_180004DAE
0x180004c8a  mov     rcx, [rsp+4E0h+var_498]
0x180004c8f  lea     r8, [rsp+4E0h+pstmTo]
0x180004c94  mov     [rsp+4E0h+var_4B8], r8
0x180004c99  xor     r9d, r9d
0x180004c9c  mov     [rsp+4E0h+pstmTo], rsi
0x180004ca1  mov     r8d, 11001h
0x180004ca7  mov     rdx, r12
0x180004caa  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x180004cae  mov     rax, [rcx]
0x180004cb1  mov     rax, [rax+18h]
0x180004cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cba  mov     ebx, eax
0x180004cbc  test    eax, eax
0x180004cbe  js      loc_180004D4B
0x180004cc4  mov     rcx, [rsp+4E0h+pstmTo]
0x180004cc9  mov     rdx, rsi
0x180004ccc  mov     rax, [rcx]
0x180004ccf  mov     rax, [rax+30h]
0x180004cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd8  mov     ebx, eax
0x180004cda  test    eax, eax
0x180004cdc  js      short loc_180004D4B
0x180004cde  lea     rdx, [rsp+4E0h+pui]; pui
0x180004ce3  mov     qword ptr [rsp+4E0h+pui], rsi
0x180004ce8  mov     rcx, r14; pstm
0x180004ceb  call    cs:__imp_IStream_Size
0x180004cf1  mov     ebx, eax
0x180004cf3  test    eax, eax
0x180004cf5  js      short loc_180004D4B
0x180004cf7  cmp     dword ptr [rsp+4E0h+pui+4], esi
0x180004cfb  jnz     short loc_180004D46
0x180004cfd  mov     r8d, dword ptr [rsp+4E0h+pui]; cb
0x180004d02  mov     rcx, r14; pstmFrom
0x180004d05  mov     rdx, [rsp+4E0h+pstmTo]; pstmTo
0x180004d0a  call    cs:__imp_IStream_Copy
0x180004d10  mov     ebx, eax
0x180004d12  test    eax, eax
0x180004d14  js      short loc_180004D4B
0x180004d16  mov     rcx, [rsp+4E0h+pstmTo]
0x180004d1b  xor     edx, edx
0x180004d1d  mov     rax, [rcx]
0x180004d20  mov     rax, [rax+40h]
0x180004d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d29  mov     ebx, eax
0x180004d2b  test    eax, eax
0x180004d2d  js      short loc_180004D4B
0x180004d2f  mov     rcx, [rsp+4E0h+var_498]
0x180004d34  xor     edx, edx
0x180004d36  mov     rax, [rcx]
0x180004d39  mov     rax, [rax+48h]
0x180004d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d42  mov     ebx, eax
0x180004d44  jmp     short loc_180004D4B
0x180004d46  mov     ebx, 800288C5h
0x180004d4b  mov     rcx, [rsp+4E0h+pstmTo]
0x180004d50  mov     [rsp+4E0h+pstmTo], rsi
0x180004d55  test    rcx, rcx
0x180004d58  jz      short loc_180004D66
0x180004d5a  mov     rax, [rcx]
0x180004d5d  mov     rax, [rax+10h]
0x180004d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d66  mov     rcx, [rsp+4E0h+var_498]
0x180004d6b  mov     rax, [rcx]
0x180004d6e  mov     rax, [rax+10h]
0x180004d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d77  test    ebx, ebx
0x180004d79  js      short loc_180004DAE
0x180004d7b  mov     rdx, [rsp+4E0h+StringSid]
0x180004d80  lea     rcx, [rsp+4E0h+pszPath]
0x180004d85  mov     r9d, r13d
0x180004d88  mov     r8d, r15d
0x180004d8b  call    ?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z
0x180004d90  mov     ebx, eax
0x180004d92  test    eax, eax
0x180004d94  js      short loc_180004DAE
0x180004d96  test    rdi, rdi
0x180004d99  jz      short loc_180004DB9
0x180004d9b  mov     r9, rdi
0x180004d9e  lea     r8, [rsp+4E0h+pszPath]
0x180004da3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z
0x180004da8  mov     ebx, eax
0x180004daa  test    eax, eax
0x180004dac  jns     short loc_180004DB9
0x180004dae  lea     rcx, [rsp+4E0h+pszPath]; lpFileName
0x180004db3  call    cs:__imp_DeleteFileW
0x180004db9  mov     rcx, [rsp+4E0h+ppv]
0x180004dbe  mov     rax, [rcx]
0x180004dc1  mov     rax, [rax+10h]
0x180004dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dca  mov     rcx, [rsp+4E0h+StringSid]; hMem
0x180004dcf  call    cs:__imp_LocalFree
0x180004dd5  mov     eax, ebx
0x180004dd7  mov     rcx, [rbp+3E0h+var_50]
0x180004dde  xor     rcx, rsp; StackCookie
0x180004de1  call    __security_check_cookie
0x180004de6  add     rsp, 4A8h
0x180004ded  pop     r15
0x180004def  pop     r14
0x180004df1  pop     r13
0x180004df3  pop     r12
0x180004df5  pop     rdi
0x180004df6  pop     rsi
0x180004df7  pop     rbx
0x180004df8  pop     rbp
0x180004df9  retn
```
