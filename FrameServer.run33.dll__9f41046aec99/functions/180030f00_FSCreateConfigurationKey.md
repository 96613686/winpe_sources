# FSCreateConfigurationKey

- ea: `0x180030f00`
- end: `0x180031434`
- name: `FSCreateConfigurationKey`
- size: `1332`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IFSConfigurationKey **)`
- caller_count: `6`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002ef34`
- `0x180032934`
- `0x180032c84`
- `0x180033458`
- `0x180033ab0`
- `0x18007ef70`

## callees

- `0x1800041f0`
- `0x180008cf0`
- `0x180009608`
- `0x180009fac`
- `0x18000a600`
- `0x18000a91c`
- `0x180017014`
- `0x180017a3c`
- `0x1800198f4`
- `0x18001c444`
- `0x180027fd0`
- `0x180029710`
- `0x18002ba64`
- `0x18002ed08`
- `0x180030f00`
- `0x180036bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003123a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003123a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031199`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031199`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003122e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800312c5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003122e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800312c5`

## pseudocode

```c
__int64 __fastcall FSCreateConfigurationKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IFSConfigurationKey **a4)
{
  const unsigned __int16 *v5; // rdi
  unsigned __int16 *v8; // r12
  LPWSTR v9; // rsi
  signed int v10; // ebx
  int Key; // eax
  __int64 v12; // rdx
  __int64 unique; // rax
  const struct std::nothrow_t *v14; // rdx
  void *v15; // rcx
  __int64 v16; // rax
  const struct std::nothrow_t *v17; // rdx
  unsigned __int16 *v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // r14d
  HANDLE FileW; // rax
  HANDLE v22; // r15
  int v23; // eax
  __int64 v24; // rdx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v26; // rdi
  signed int LastError; // eax
  __int64 v28; // rdx
  __int64 v29; // rax
  const struct std::nothrow_t *v30; // rdx
  unsigned __int16 *v31; // rcx
  DWORD v32; // r14d
  signed int v33; // eax
  unsigned int v34; // ebx
  const struct std::nothrow_t *v35; // rdx
  unsigned int v37; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-21h] BYREF
  LPWSTR lpszFilePath; // [rsp+50h] [rbp-19h] BYREF
  void *v40; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v41; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-1h] BYREF
  __int64 v43; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v44[9]; // [rsp+78h] [rbp+Fh] BYREF
  HANDLE hFile; // [rsp+E8h] [rbp+7Fh] BYREF

  v44[0] = 0;
  v5 = a3;
  v41 = 0;
  v37 = 0;
  lpszFilePath = 0;
  v8 = 0;
  LODWORD(hFile) = 0;
  v9 = 0;
  v38 = 0;
  v42 = 0;
  v43 = 0;
  if ( !a4 )
  {
    v10 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        -2147467261);
    goto LABEL_80;
  }
  *a4 = 0;
  if ( !a1 )
  {
    Key = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 41;
    goto LABEL_79;
  }
  if ( a2 && a3 )
  {
    Key = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 42;
    goto LABEL_79;
  }
  Key = FSGetUniqueSymbolicName(a1, 0, 0, &v37);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 43;
    goto LABEL_79;
  }
  unique = wil::make_unique_nothrow<unsigned short [0]>(&v40, v37);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v41, unique);
  v15 = v40;
  v40 = 0;
  if ( v15 )
    operator delete(v15, v14);
  v8 = v41;
  if ( !v41 )
  {
    Key = -2147024882;
    v10 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = (unsigned int)((_DWORD)v41 + 44);
    goto LABEL_79;
  }
  Key = FSGetUniqueSymbolicName(a1, v41, v37, &v37);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 45;
    goto LABEL_79;
  }
  if ( a2 )
  {
    if ( v5 )
      goto LABEL_37;
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    v22 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v41 = 0;
      v23 = StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&v41);
      v10 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_46:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          goto LABEL_80;
        }
        v24 = 50;
LABEL_45:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v23);
        goto LABEL_46;
      }
      v5 = a2;
      v20 = (_DWORD)v41 + 1;
LABEL_67:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      goto LABEL_68;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 2u);
    v26 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW )
      goto LABEL_55;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_55:
      v29 = wil::make_unique_nothrow<unsigned short [0]>(&v41, v26);
      wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&lpszFilePath, v29);
      v31 = v41;
      v41 = 0;
      if ( v31 )
        operator delete(v31, v30);
      v9 = lpszFilePath;
      if ( !lpszFilePath )
      {
        v23 = -2147024882;
        v10 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_46;
        v24 = (unsigned int)((_DWORD)lpszFilePath + 52);
        goto LABEL_45;
      }
      v32 = GetFinalPathNameByHandleW(v22, lpszFilePath, v26, 2u);
      if ( v32 )
        goto LABEL_66;
      v33 = GetLastError();
      v10 = v33;
      if ( v33 > 0 )
        v10 = (unsigned __int16)v33 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_66:
        v5 = v9;
        v20 = v32 + 1;
        goto LABEL_67;
      }
      if ( !g_wppLevels )
        goto LABEL_46;
      v28 = 53;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_46;
      v28 = 51;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v10);
    goto LABEL_46;
  }
  if ( v5 )
  {
LABEL_37:
    hFile = 0;
    Key = StringCchLengthW(v5, 0x7FFFFFFFu, (unsigned __int64 *)&hFile);
    v10 = Key;
    if ( Key < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_80;
      v12 = 49;
      goto LABEL_79;
    }
    v20 = (_DWORD)hFile + 1;
    goto LABEL_68;
  }
  Key = FSGetCurrentProcessConfigurationInfo(0, 0, (unsigned int *)&hFile);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 46;
    goto LABEL_79;
  }
  v16 = wil::make_unique_nothrow<unsigned short [0]>(&v41, (unsigned int)hFile);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&lpszFilePath, v16);
  v18 = v41;
  v41 = 0;
  if ( v18 )
    operator delete(v18, v17);
  v9 = lpszFilePath;
  if ( !lpszFilePath )
  {
    Key = -2147024882;
    v10 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = (unsigned int)((_DWORD)lpszFilePath + 47);
    goto LABEL_79;
  }
  Key = FSGetCurrentProcessConfigurationInfo(lpszFilePath, (unsigned int)hFile, (unsigned int *)&hFile);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 48;
    goto LABEL_79;
  }
  v20 = (unsigned int)hFile;
  v5 = v9;
LABEL_68:
  Key = FSGetUserSidString(v19, &v38);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 54;
    goto LABEL_79;
  }
  Key = StringCchLengthW(v38, 0x7FFFFFFFu, &v42);
  v10 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_80;
    v12 = 55;
    goto LABEL_79;
  }
  v34 = v42 + 1;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v8, (__int64)v5);
  Key = FSConfigurationKey::CreateKey(v8, v37, v5, v20, v38, v34, a4);
  v10 = Key;
  if ( Key < 0 && g_wppLevels )
  {
    v12 = 57;
LABEL_79:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, Key);
  }
LABEL_80:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v43);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
  if ( v9 )
    operator delete(v9, v35);
  if ( v8 )
    operator delete(v8, v35);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v44);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180030f00  push    rbp
0x180030f02  push    rbx
0x180030f03  push    rsi
0x180030f04  push    rdi
0x180030f05  push    r12
0x180030f07  push    r13
0x180030f09  push    r14
0x180030f0b  push    r15
0x180030f0d  lea     rbp, [rsp-1Fh]
0x180030f12  sub     rsp, 88h
0x180030f19  xor     eax, eax
0x180030f1b  mov     r13, r9
0x180030f1e  mov     [rbp+57h+var_48], rax
0x180030f22  mov     rdi, r8
0x180030f25  mov     [rbp+57h+var_60], rax
0x180030f29  mov     r14, rdx
0x180030f2c  mov     [rbp+57h+var_80], eax
0x180030f2f  mov     r15, rcx
0x180030f32  mov     [rbp+57h+lpszFilePath], rax
0x180030f36  mov     r12d, eax
0x180030f39  mov     dword ptr [rbp+57h+hFile], eax
0x180030f3c  mov     esi, eax
0x180030f3e  mov     [rbp+57h+var_78], rax
0x180030f42  mov     [rbp+57h+var_58], rax
0x180030f46  mov     [rbp+57h+var_50], rax
0x180030f4a  test    r9, r9
0x180030f4d  jnz     short loc_180030F6D
0x180030f4f  mov     ebx, 80004003h
0x180030f54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030f5b  jb      loc_1800313E9
0x180030f61  lea     edx, [rax+28h]
0x180030f64  mov     [rsp+0C0h+dwCreationDisposition], ebx
0x180030f68  jmp     loc_1800313CF
0x180030f6d  mov     [r9], rax
0x180030f70  test    r15, r15
0x180030f73  jnz     short loc_180030F92
0x180030f75  mov     eax, 80070057h
0x180030f7a  mov     ebx, eax
0x180030f7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030f83  jb      loc_1800313E9
0x180030f89  lea     edx, [r15+29h]
0x180030f8d  jmp     loc_1800313CB
0x180030f92  test    r14, r14
0x180030f95  jz      short loc_180030FBA
0x180030f97  test    rdi, rdi
0x180030f9a  jz      short loc_180030FBA
0x180030f9c  mov     eax, 80070057h
0x180030fa1  mov     ebx, eax
0x180030fa3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030faa  jb      loc_1800313E9
0x180030fb0  mov     edx, 2Ah ; '*'
0x180030fb5  jmp     loc_1800313CB
0x180030fba  lea     r9, [rbp+57h+var_80]; unsigned int *
0x180030fbe  xor     r8d, r8d; unsigned int
0x180030fc1  xor     edx, edx; unsigned __int16 *
0x180030fc3  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180030fc8  mov     ebx, eax
0x180030fca  test    eax, eax
0x180030fcc  jns     short loc_180030FE5
0x180030fce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030fd5  jb      loc_1800313E9
0x180030fdb  mov     edx, 2Bh ; '+'
0x180030fe0  jmp     loc_1800313CB
0x180030fe5  mov     edx, [rbp+57h+var_80]
0x180030fe8  lea     rcx, [rbp+57h+var_68]
0x180030fec  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180030ff1  mov     rdx, rax
0x180030ff4  lea     rcx, [rbp+57h+var_60]
0x180030ff8  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x180030ffd  mov     rcx, [rbp+57h+var_68]; void *
0x180031001  mov     [rbp+57h+var_68], rsi
0x180031005  test    rcx, rcx
0x180031008  jz      short loc_18003100F
0x18003100a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003100f  mov     r12, [rbp+57h+var_60]
0x180031013  test    r12, r12
0x180031016  jnz     short loc_180031036
0x180031018  mov     eax, 8007000Eh
0x18003101d  mov     ebx, eax
0x18003101f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031026  jb      loc_1800313E9
0x18003102c  lea     edx, [r12+2Ch]
0x180031031  jmp     loc_1800313CB
0x180031036  mov     r8d, [rbp+57h+var_80]; unsigned int
0x18003103a  lea     r9, [rbp+57h+var_80]; unsigned int *
0x18003103e  mov     rdx, r12; unsigned __int16 *
0x180031041  mov     rcx, r15; unsigned __int16 *
0x180031044  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180031049  mov     ebx, eax
0x18003104b  test    eax, eax
0x18003104d  jns     short loc_180031066
0x18003104f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031056  jb      loc_1800313E9
0x18003105c  mov     edx, 2Dh ; '-'
0x180031061  jmp     loc_1800313CB
0x180031066  mov     ebx, 7FFFFFFFh
0x18003106b  test    r14, r14
0x18003106e  jnz     loc_18003112C
0x180031074  test    rdi, rdi
0x180031077  jnz     loc_180031131
0x18003107d  lea     r8, [rbp+57h+hFile]; unsigned int *
0x180031081  xor     edx, edx; unsigned int
0x180031083  xor     ecx, ecx; unsigned __int16 *
0x180031085  call    ?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z; FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)
0x18003108a  mov     ebx, eax
0x18003108c  test    eax, eax
0x18003108e  jns     short loc_1800310A5
0x180031090  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031097  jb      loc_1800313E9
0x18003109d  lea     edx, [rdi+2Eh]
0x1800310a0  jmp     loc_1800313CB
0x1800310a5  mov     edx, dword ptr [rbp+57h+hFile]
0x1800310a8  lea     rcx, [rbp+57h+var_60]
0x1800310ac  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800310b1  mov     rdx, rax
0x1800310b4  lea     rcx, [rbp+57h+lpszFilePath]
0x1800310b8  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x1800310bd  mov     rcx, [rbp+57h+var_60]; void *
0x1800310c1  mov     [rbp+57h+var_60], rsi
0x1800310c5  test    rcx, rcx
0x1800310c8  jz      short loc_1800310CF
0x1800310ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800310cf  mov     rsi, [rbp+57h+lpszFilePath]
0x1800310d3  test    rsi, rsi
0x1800310d6  jnz     short loc_1800310F4
0x1800310d8  mov     eax, 8007000Eh
0x1800310dd  mov     ebx, eax
0x1800310df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800310e6  jb      loc_1800313E9
0x1800310ec  lea     edx, [rsi+2Fh]
0x1800310ef  jmp     loc_1800313CB
0x1800310f4  mov     edx, dword ptr [rbp+57h+hFile]; unsigned int
0x1800310f7  lea     r8, [rbp+57h+hFile]; unsigned int *
0x1800310fb  mov     rcx, rsi; unsigned __int16 *
0x1800310fe  call    ?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z; FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)
0x180031103  mov     ebx, eax
0x180031105  test    eax, eax
0x180031107  jns     short loc_180031120
0x180031109  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031110  jb      loc_1800313E9
0x180031116  mov     edx, 30h ; '0'
0x18003111b  jmp     loc_1800313CB
0x180031120  mov     r14d, dword ptr [rbp+57h+hFile]
0x180031124  mov     rdi, rsi
0x180031127  jmp     loc_180031311
0x18003112c  test    rdi, rdi
0x18003112f  jz      short loc_18003116D
0x180031131  lea     r8, [rbp+57h+hFile]; unsigned __int64 *
0x180031135  mov     [rbp+57h+hFile], rsi
0x180031139  mov     rdx, rbx; unsigned __int64
0x18003113c  mov     rcx, rdi; unsigned __int16 *
0x18003113f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031144  mov     ebx, eax
0x180031146  test    eax, eax
0x180031148  jns     short loc_180031161
0x18003114a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031151  jb      loc_1800313E9
0x180031157  mov     edx, 31h ; '1'
0x18003115c  jmp     loc_1800313CB
0x180031161  mov     r14d, dword ptr [rbp+57h+hFile]
0x180031165  inc     r14d
0x180031168  jmp     loc_180031311
0x18003116d  xor     r9d, r9d; lpSecurityAttributes
0x180031170  mov     [rsp+0C0h+hTemplateFile], rsi; hTemplateFile
0x180031175  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003117d  mov     edx, 80000000h; dwDesiredAccess
0x180031182  mov     rcx, r14; lpFileName
0x180031185  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x18003118d  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180031195  lea     r8d, [r9+7]; dwShareMode
0x180031199  call    cs:__imp_CreateFileW
0x18003119f  mov     rdx, rax
0x1800311a2  lea     rcx, [rbp+57h+hFile]
0x1800311a6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800311ab  mov     r15, [rbp+57h+hFile]
0x1800311af  lea     rax, [r15+1]
0x1800311b3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800311b9  jnz     short loc_18003121D
0x1800311bb  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x1800311bf  mov     [rbp+57h+var_60], rsi
0x1800311c3  mov     rdx, rbx; unsigned __int64
0x1800311c6  mov     rcx, r14; unsigned __int16 *
0x1800311c9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800311ce  mov     ebx, eax
0x1800311d0  test    eax, eax
0x1800311d2  jns     short loc_18003120E
0x1800311d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800311db  jb      short loc_180031200
0x1800311dd  mov     edx, 32h ; '2'
0x1800311e2  mov     [rsp+0C0h+dwCreationDisposition], eax
0x1800311e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311ed  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800311f4  xor     r9d, r9d
0x1800311f7  mov     rcx, [rcx+10h]
0x1800311fb  call    WPP_SF_qD
0x180031200  lea     rcx, [rbp+57h+hFile]
0x180031204  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031209  jmp     loc_1800313E9
0x18003120e  mov     rdi, r14
0x180031211  mov     r14d, dword ptr [rbp+57h+var_60]
0x180031215  inc     r14d
0x180031218  jmp     loc_180031308
0x18003121d  mov     r14d, 2
0x180031223  xor     r8d, r8d; cchFilePath
0x180031226  mov     r9d, r14d; dwFlags
0x180031229  xor     edx, edx; lpszFilePath
0x18003122b  mov     rcx, r15; hFile
0x18003122e  call    cs:__imp_GetFinalPathNameByHandleW
0x180031234  mov     edi, eax
0x180031236  test    eax, eax
0x180031238  jnz     short loc_18003126A
0x18003123a  call    cs:__imp_GetLastError
0x180031240  mov     ebx, eax
0x180031242  test    eax, eax
0x180031244  jle     short loc_18003124F
0x180031246  movzx   ebx, ax
0x180031249  or      ebx, 80070000h
0x18003124f  test    ebx, ebx
0x180031251  jns     short loc_18003126A
0x180031253  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003125a  jb      short loc_180031200
0x18003125c  mov     edx, 33h ; '3'
0x180031261  mov     [rsp+0C0h+dwCreationDisposition], ebx
0x180031265  jmp     loc_1800311E6
0x18003126a  mov     rdx, rdi
0x18003126d  lea     rcx, [rbp+57h+var_60]
0x180031271  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180031276  mov     rdx, rax
0x180031279  lea     rcx, [rbp+57h+lpszFilePath]
0x18003127d  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x180031282  mov     rcx, [rbp+57h+var_60]; void *
0x180031286  mov     [rbp+57h+var_60], rsi
0x18003128a  test    rcx, rcx
0x18003128d  jz      short loc_180031294
0x18003128f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031294  mov     rsi, [rbp+57h+lpszFilePath]
0x180031298  test    rsi, rsi
0x18003129b  jnz     short loc_1800312B9
0x18003129d  mov     eax, 8007000Eh
0x1800312a2  mov     ebx, eax
0x1800312a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800312ab  jb      loc_180031200
0x1800312b1  lea     edx, [rsi+34h]
0x1800312b4  jmp     loc_1800311E2
0x1800312b9  mov     r9d, r14d; dwFlags
0x1800312bc  mov     r8d, edi; cchFilePath
0x1800312bf  mov     rdx, rsi; lpszFilePath
0x1800312c2  mov     rcx, r15; hFile
0x1800312c5  call    cs:__imp_GetFinalPathNameByHandleW
0x1800312cb  mov     r14d, eax
0x1800312ce  test    eax, eax
0x1800312d0  jnz     short loc_180031302
0x1800312d2  call    cs:__imp_GetLastError
0x1800312d8  mov     ebx, eax
0x1800312da  test    eax, eax
0x1800312dc  jle     short loc_1800312E7
0x1800312de  movzx   ebx, ax
0x1800312e1  or      ebx, 80070000h
0x1800312e7  test    ebx, ebx
0x1800312e9  jns     short loc_180031302
0x1800312eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800312f2  jb      loc_180031200
0x1800312f8  mov     edx, 35h ; '5'
0x1800312fd  jmp     loc_180031261
0x180031302  mov     rdi, rsi
0x180031305  inc     r14d
0x180031308  lea     rcx, [rbp+57h+hFile]
0x18003130c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031311  lea     rdx, [rbp+57h+var_78]
0x180031315  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003131a  mov     ebx, eax
0x18003131c  test    eax, eax
0x18003131e  jns     short loc_180031337
0x180031320  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031327  jb      loc_1800313E9
0x18003132d  mov     edx, 36h ; '6'
0x180031332  jmp     loc_1800313CB
0x180031337  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18003133b  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x18003133f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180031344  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031349  mov     ebx, eax
0x18003134b  test    eax, eax
0x18003134d  jns     short loc_180031363
0x18003134f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031356  jb      loc_1800313E9
0x18003135c  mov     edx, 37h ; '7'
0x180031361  jmp     short loc_1800313CB
0x180031363  mov     rbx, [rbp+57h+var_58]
0x180031367  inc     rbx
0x18003136a  cmp     cs:byte_18010EC4D, 8
0x180031371  jb      short loc_180031394
0x180031373  mov     rcx, cs:WPP_GLOBAL_Control
0x18003137a  mov     r9, [rbp+57h+var_78]
0x18003137e  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rdi; __int64
0x180031383  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r12; __int64
0x180031388  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003138f  call    WPP_SF_SSS
0x180031394  mov     rax, [rbp+57h+var_78]
0x180031398  mov     r9d, r14d; unsigned int
  ... truncated ...
```
