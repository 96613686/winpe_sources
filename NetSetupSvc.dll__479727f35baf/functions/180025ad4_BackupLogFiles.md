# BackupLogFiles

- ea: `0x180025ad4`
- end: `0x180025cf3`
- name: `BackupLogFiles`
- size: `543`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800260a4`

## callees

- `0x1800027c0`
- `0x18000d954`
- `0x18000d9b4`
- `0x1800177d0`
- `0x1800182b0`
- `0x180019c64`
- `0x180025ad4`
- `0x180025cfc`
- `0x180025db4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025bf1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025bf1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025b94`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025b94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025b60`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025b60`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180025ca3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180025ca3`

## pseudocode

```c
__int64 __fastcall BackupLogFiles(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  unsigned __int64 v5; // rbx
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 LogFileName; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  const WCHAR *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  const WCHAR *v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  const WCHAR *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // r8
  const WCHAR *v38; // rax
  LPCWSTR v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rax
  _BYTE v44[32]; // [rsp+20h] [rbp-61h] BYREF
  _BYTE v45[16]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v46; // [rsp+50h] [rbp-31h]
  _BYTE v47[32]; // [rsp+60h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp-1h] BYREF
  __int128 v49; // [rsp+90h] [rbp+Fh]
  unsigned int v50; // [rsp+A0h] [rbp+1Fh]

  v5 = a4;
  std::wstring::wstring(v45, a5);
  v7 = v46;
  LogFileName = MakeLogFileName(v47, v8, 0);
  v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(LogFileName, v10, *(_QWORD *)(LogFileName + 16));
  std::wstring::_Append<wchar_t>(v45, v11);
  std::wstring::_Tidy_deallocate(v47);
  FileInformation = 0;
  v49 = 0;
  v50 = 0;
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45, v12, v13);
  if ( GetFileAttributesExW(v14, GetFileExInfoStandard, &FileInformation)
    && v50 + ((unsigned __int64)HIDWORD(v49) << 32) > v5 )
  {
    if ( a3 )
    {
      v18 = 1;
      if ( a3 <= 1 )
        goto LABEL_9;
      do
      {
        std::wstring::resize(v45, v7, 0);
        v20 = MakeLogFileName(v47, v19, v18);
        v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20, v21, *(_QWORD *)(v20 + 16));
        std::wstring::_Append<wchar_t>(v45, v22);
        std::wstring::_Tidy_deallocate(v47);
        v25 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45, v23, v24);
        if ( GetFileAttributesW(v25) == -1 )
          break;
        ++v18;
      }
      while ( v18 < a3 );
      while ( v18 )
      {
LABEL_9:
        std::wstring::wstring(v47, a5);
        v27 = MakeLogFileName(v44, v26, v18);
        v29 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27, v28, *(_QWORD *)(v27 + 16));
        std::wstring::_Append<wchar_t>(v47, v29);
        std::wstring::_Tidy_deallocate(v44);
        --v18;
        std::wstring::resize(v45, v7, 0);
        v31 = MakeLogFileName(v44, v30, v18);
        v33 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31, v32, *(_QWORD *)(v31 + 16));
        std::wstring::_Append<wchar_t>(v45, v33);
        std::wstring::_Tidy_deallocate(v44);
        v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47, v34, v35);
        v38 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45, v36, v37);
        if ( MoveFileExW(v38, v39, 1u) )
        {
          v42 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47, v40, v41);
          CompressLogFile(v42);
        }
        std::wstring::_Tidy_deallocate(v47);
      }
    }
    else
    {
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45, v15, v16);
      DeleteFileW(v17);
    }
  }
  return std::wstring::_Tidy_deallocate(v45);
}

```

## disassembly

```asm
0x180025ad4  push    rbp
0x180025ad6  push    rbx
0x180025ad7  push    rsi
0x180025ad8  push    rdi
0x180025ad9  push    r14
0x180025adb  lea     rbp, [rsp-2Fh]
0x180025ae0  sub     rsp, 0B0h
0x180025ae7  mov     rax, cs:__security_cookie
0x180025aee  xor     rax, rsp
0x180025af1  mov     [rbp+4Fh+var_28], rax
0x180025af5  mov     ebx, r9d
0x180025af8  mov     edi, r8d
0x180025afb  mov     r14, [rbp+4Fh+arg_20]
0x180025aff  mov     rdx, r14
0x180025b02  lea     rcx, [rbp+4Fh+var_90]
0x180025b06  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180025b0b  nop
0x180025b0c  mov     rsi, [rbp+4Fh+var_80]
0x180025b10  xor     r8d, r8d
0x180025b13  lea     rcx, [rbp+4Fh+var_70]
0x180025b17  call    MakeLogFileName
0x180025b1c  mov     r8, [rax+10h]
0x180025b20  mov     rcx, rax
0x180025b23  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025b28  mov     rdx, rax
0x180025b2b  lea     rcx, [rbp+4Fh+var_90]
0x180025b2f  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180025b34  nop
0x180025b35  lea     rcx, [rbp+4Fh+var_70]
0x180025b39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025b3e  xorps   xmm0, xmm0
0x180025b41  xor     eax, eax
0x180025b43  movups  [rbp+4Fh+FileInformation], xmm0
0x180025b47  movups  [rbp+4Fh+var_40], xmm0
0x180025b4b  mov     [rbp+4Fh+var_30], eax
0x180025b4e  lea     rcx, [rbp+4Fh+var_90]
0x180025b52  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025b57  mov     rcx, rax; lpFileName
0x180025b5a  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180025b5e  xor     edx, edx; fInfoLevelId
0x180025b60  call    cs:__imp_GetFileAttributesExW
0x180025b66  test    eax, eax
0x180025b68  jz      loc_180025CD0
0x180025b6e  mov     ecx, dword ptr [rbp+4Fh+var_40+0Ch]
0x180025b71  shl     rcx, 20h
0x180025b75  mov     eax, [rbp+4Fh+var_30]
0x180025b78  add     rcx, rax
0x180025b7b  cmp     rcx, rbx
0x180025b7e  jbe     loc_180025CD0
0x180025b84  test    edi, edi
0x180025b86  jnz     short loc_180025B9F
0x180025b88  lea     rcx, [rbp+4Fh+var_90]
0x180025b8c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025b91  mov     rcx, rax; lpFileName
0x180025b94  call    cs:__imp_DeleteFileW
0x180025b9a  jmp     loc_180025CD0
0x180025b9f  mov     ebx, 1
0x180025ba4  cmp     edi, ebx
0x180025ba6  jbe     short loc_180025C0B
0x180025ba8  xor     r8d, r8d
0x180025bab  mov     rdx, rsi
0x180025bae  lea     rcx, [rbp+4Fh+var_90]
0x180025bb2  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180025bb7  mov     r8d, ebx
0x180025bba  lea     rcx, [rbp+4Fh+var_70]
0x180025bbe  call    MakeLogFileName
0x180025bc3  mov     r8, [rax+10h]
0x180025bc7  mov     rcx, rax
0x180025bca  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025bcf  mov     rdx, rax
0x180025bd2  lea     rcx, [rbp+4Fh+var_90]
0x180025bd6  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180025bdb  nop
0x180025bdc  lea     rcx, [rbp+4Fh+var_70]
0x180025be0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025be5  lea     rcx, [rbp+4Fh+var_90]
0x180025be9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025bee  mov     rcx, rax; lpFileName
0x180025bf1  call    cs:__imp_GetFileAttributesW
0x180025bf7  cmp     eax, 0FFFFFFFFh
0x180025bfa  jz      loc_180025CC8
0x180025c00  inc     ebx
0x180025c02  cmp     ebx, edi
0x180025c04  jb      short loc_180025BA8
0x180025c06  jmp     loc_180025CC8
0x180025c0b  mov     rdx, r14
0x180025c0e  lea     rcx, [rbp+4Fh+var_70]
0x180025c12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180025c17  nop
0x180025c18  mov     r8d, ebx
0x180025c1b  lea     rcx, [rbp+4Fh+var_B0]
0x180025c1f  call    MakeLogFileName
0x180025c24  mov     r8, [rax+10h]
0x180025c28  mov     rcx, rax
0x180025c2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025c30  mov     rdx, rax
0x180025c33  lea     rcx, [rbp+4Fh+var_70]
0x180025c37  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180025c3c  nop
0x180025c3d  lea     rcx, [rbp+4Fh+var_B0]
0x180025c41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025c46  dec     ebx
0x180025c48  xor     r8d, r8d
0x180025c4b  mov     rdx, rsi
0x180025c4e  lea     rcx, [rbp+4Fh+var_90]
0x180025c52  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180025c57  mov     r8d, ebx
0x180025c5a  lea     rcx, [rbp+4Fh+var_B0]
0x180025c5e  call    MakeLogFileName
0x180025c63  mov     r8, [rax+10h]
0x180025c67  mov     rcx, rax
0x180025c6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025c6f  mov     rdx, rax
0x180025c72  lea     rcx, [rbp+4Fh+var_90]
0x180025c76  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180025c7b  nop
0x180025c7c  lea     rcx, [rbp+4Fh+var_B0]
0x180025c80  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025c85  lea     rcx, [rbp+4Fh+var_70]
0x180025c89  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025c8e  mov     rdx, rax
0x180025c91  lea     rcx, [rbp+4Fh+var_90]
0x180025c95  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025c9a  mov     rcx, rax; lpExistingFileName
0x180025c9d  mov     r8d, 1; dwFlags
0x180025ca3  call    cs:__imp_MoveFileExW
0x180025ca9  test    eax, eax
0x180025cab  jz      short loc_180025CBF
0x180025cad  lea     rcx, [rbp+4Fh+var_70]
0x180025cb1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025cb6  mov     rcx, rax
0x180025cb9  call    CompressLogFile
0x180025cbe  nop
0x180025cbf  lea     rcx, [rbp+4Fh+var_70]
0x180025cc3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025cc8  test    ebx, ebx
0x180025cca  jnz     loc_180025C0B
0x180025cd0  lea     rcx, [rbp+4Fh+var_90]
0x180025cd4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025cd9  mov     rcx, [rbp+4Fh+var_28]
0x180025cdd  xor     rcx, rsp; StackCookie
0x180025ce0  call    __security_check_cookie
0x180025ce5  add     rsp, 0B0h
0x180025cec  pop     r14
0x180025cee  pop     rdi
0x180025cef  pop     rsi
0x180025cf0  pop     rbx
0x180025cf1  pop     rbp
0x180025cf2  retn
```
