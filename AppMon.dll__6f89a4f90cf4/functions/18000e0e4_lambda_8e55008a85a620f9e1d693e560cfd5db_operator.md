# _lambda_8e55008a85a620f9e1d693e560cfd5db_::operator()

- ea: `0x18000e0e4`
- end: `0x18000e41e`
- name: `_lambda_8e55008a85a620f9e1d693e560cfd5db_::operator()`
- size: `826`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000dfb8`

## callees

- `0x180001620`
- `0x180001fd0`
- `0x1800026fc`
- `0x18000516c`
- `0x180006308`
- `0x180006408`
- `0x18000798c`
- `0x180007a04`
- `0x1800087f0`
- `0x180008908`
- `0x180009da4`
- `0x18000e0e4`
- `0x18000e67c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e116`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e205`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e288`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e288`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e24c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e24c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e1fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e1fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e398`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e398`
- `profapi!__imp_GetAppContainerPath` at `0x18000e18e`
- `profapi!__imp_GetAppContainerPath` at `0x18000e18e`

## string_xrefs

- `0x18000e1c2`: `%s\Temp\`

## pseudocode

```c
__int64 __fastcall lambda_8e55008a85a620f9e1d693e560cfd5db_::operator()(RTL_SRWLOCK **a1)
{
  RTL_SRWLOCK *v2; // rbx
  _QWORD *v3; // rax
  int AppContainerPath; // eax
  int v5; // eax
  signed int LastError; // eax
  char v7; // cl
  HRESULT v8; // eax
  const char *v9; // r9
  int v10; // eax
  std::_Ref_count_base *v11; // rdi
  const WCHAR *Ptr; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  RTL_SRWLOCK *v15; // r9
  _QWORD *v16; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  RTL_SRWLOCK *v19; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v20; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v21; // [rsp+50h] [rbp-B0h]
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR PathName[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v25[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v2 = *a1 + 1;
  AcquireSRWLockExclusive(v2);
  v19 = v2;
  memset_0(v25, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(sz, 0, sizeof(sz));
  pguid = 0;
  v3 = (_QWORD *)(*(__int64 (__fastcall **)(PVOID, std::_Ref_count_base **))(*(_QWORD *)a1[1]->Ptr + 8LL))(
                   a1[1]->Ptr,
                   &v20);
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  AppContainerPath = GetAppContainerPath(v3, PathName, 260);
  if ( AppContainerPath < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      (const char *)(unsigned int)AppContainerPath,
      dwCreationDisposition);
  std::wstring::~wstring(&v20);
  v5 = StringCchPrintfW(PathName, 0x104u, L"%s\\Temp\\", PathName);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
  if ( !CreateDirectoryW(PathName, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 183 )
    {
      v7 = 0;
    }
    else
    {
      v7 = 1;
      if ( LastError <= 0 )
        goto LABEL_12;
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    if ( v7 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationDisposition);
  }
  v8 = CoCreateGuid(&pguid);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
  if ( !StringFromGUID2(&pguid, sz, 40) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x40,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      v9);
  v10 = StringCchPrintfW(v25, 0x104u, L"%s%s%s", PathName);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      (const char *)(unsigned int)v10,
      (int)sz);
  v11 = (std::_Ref_count_base *)operator new(0x30u);
  v20 = v11;
  *(_OWORD *)v11 = 0;
  *((_DWORD *)v11 + 2) = 1;
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<std::wstring>::`vftable';
  std::wstring::wstring((char *)v11 + 16, v25);
  v20 = (std::_Ref_count_base *)((char *)v11 + 16);
  v21 = v11;
  std::shared_ptr<std::wstring>::operator=(&(*a1)[2], &v20);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  Ptr = (const WCHAR *)(*a1)[2].Ptr;
  if ( *((_QWORD *)Ptr + 3) > 7u )
    Ptr = *(const WCHAR **)Ptr;
  (*a1)[4].Ptr = CreateFileW(Ptr, 0x40000000u, 7u, 0, 2u, 0x80u, 0);
  v15 = *a1;
  if ( (*a1)[4].Ptr == (PVOID)-1LL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\printstorage.cpp",
      (const char *)v15);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = v15[2].Ptr;
    if ( v16[3] > 7u )
      v16 = (_QWORD *)*v16;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v16);
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
}

```

## disassembly

```asm
0x18000e0e4  push    rbp
0x18000e0e6  push    rbx
0x18000e0e7  push    rsi
0x18000e0e8  push    rdi
0x18000e0e9  lea     rbp, [rsp-408h]
0x18000e0f1  sub     rsp, 508h
0x18000e0f8  mov     rax, cs:__security_cookie
0x18000e0ff  xor     rax, rsp
0x18000e102  mov     [rbp+420h+var_30], rax
0x18000e109  mov     rsi, rcx
0x18000e10c  mov     rbx, [rcx]
0x18000e10f  add     rbx, 8
0x18000e113  mov     rcx, rbx; SRWLock
0x18000e116  call    cs:__imp_AcquireSRWLockExclusive
0x18000e11c  mov     [rsp+520h+var_4E0], rbx
0x18000e121  mov     ebx, 208h
0x18000e126  mov     r8d, ebx; Size
0x18000e129  xor     edx, edx; Val
0x18000e12b  lea     rcx, [rbp+420h+var_240]; void *
0x18000e132  call    memset_0
0x18000e137  mov     r8d, ebx; Size
0x18000e13a  xor     edx, edx; Val
0x18000e13c  lea     rcx, [rbp+420h+PathName]; void *
0x18000e140  call    memset_0
0x18000e145  xor     edx, edx; Val
0x18000e147  lea     r8d, [rdx+50h]; Size
0x18000e14b  lea     rcx, [rbp+420h+sz]; void *
0x18000e14f  call    memset_0
0x18000e154  xorps   xmm0, xmm0
0x18000e157  movups  xmmword ptr [rsp+520h+pguid.Data1], xmm0
0x18000e15c  mov     rax, [rsi+8]
0x18000e160  mov     rcx, [rax]
0x18000e163  mov     rax, [rcx]
0x18000e166  lea     rdx, [rsp+520h+var_4D8]
0x18000e16b  mov     rax, [rax+8]
0x18000e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e174  nop
0x18000e175  cmp     qword ptr [rax+18h], 7
0x18000e17a  jbe     short loc_18000E17F
0x18000e17c  mov     rax, [rax]
0x18000e17f  mov     edi, 104h
0x18000e184  mov     r8d, edi
0x18000e187  lea     rdx, [rbp+420h+PathName]
0x18000e18b  mov     rcx, rax
0x18000e18e  call    cs:__imp_GetAppContainerPath
0x18000e194  mov     rcx, [rbp+428h]; this
0x18000e19b  test    eax, eax
0x18000e19d  jns     short loc_18000E1B4
0x18000e19f  mov     r9d, eax; char *
0x18000e1a2  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e1a9  mov     edx, 2Eh ; '.'; void *
0x18000e1ae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e1b4  lea     rcx, [rsp+520h+var_4D8]
0x18000e1b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e1be  lea     r9, [rbp+420h+PathName]
0x18000e1c2  lea     r8, aSTemp; "%s\\Temp\\"
0x18000e1c9  mov     rdx, rdi; unsigned __int64
0x18000e1cc  lea     rcx, [rbp+420h+PathName]; unsigned __int16 *
0x18000e1d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e1d5  mov     rcx, [rbp+428h]; this
0x18000e1dc  test    eax, eax
0x18000e1de  jns     short loc_18000E1F5
0x18000e1e0  mov     r9d, eax; char *
0x18000e1e3  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e1ea  mov     edx, 34h ; '4'; void *
0x18000e1ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e1f5  xor     edx, edx; lpSecurityAttributes
0x18000e1f7  lea     rcx, [rbp+420h+PathName]; lpPathName
0x18000e1fb  call    cs:__imp_CreateDirectoryW
0x18000e201  test    eax, eax
0x18000e203  jnz     short loc_18000E247
0x18000e205  call    cs:__imp_GetLastError
0x18000e20b  cmp     eax, 0B7h
0x18000e210  jnz     short loc_18000E216
0x18000e212  xor     cl, cl
0x18000e214  jmp     short loc_18000E21C
0x18000e216  mov     cl, 1
0x18000e218  test    eax, eax
0x18000e21a  jle     short loc_18000E224
0x18000e21c  movzx   eax, ax
0x18000e21f  or      eax, 80070000h
0x18000e224  mov     r10, [rbp+428h]
0x18000e22b  test    cl, cl
0x18000e22d  jz      short loc_18000E247
0x18000e22f  mov     r9d, eax; char *
0x18000e232  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e239  mov     edx, 3Ah ; ':'; void *
0x18000e23e  mov     rcx, r10; this
0x18000e241  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e247  lea     rcx, [rsp+520h+pguid]; pguid
0x18000e24c  call    cs:__imp_CoCreateGuid
0x18000e252  mov     rcx, [rbp+428h]; this
0x18000e259  test    eax, eax
0x18000e25b  jns     short loc_18000E272
0x18000e25d  mov     r9d, eax; char *
0x18000e260  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e267  mov     edx, 3Fh ; '?'; void *
0x18000e26c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e272  mov     rbx, [rbp+428h]
0x18000e279  mov     r8d, 28h ; '('; cchMax
0x18000e27f  lea     rdx, [rbp+420h+sz]; lpsz
0x18000e283  lea     rcx, [rsp+520h+pguid]; rguid
0x18000e288  call    cs:__imp_StringFromGUID2
0x18000e28e  test    eax, eax
0x18000e290  jnz     short loc_18000E2A5
0x18000e292  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e299  lea     edx, [rax+40h]; void *
0x18000e29c  mov     rcx, rbx; this
0x18000e29f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e2a5  lea     rax, aXps; ".xps"
0x18000e2ac  mov     qword ptr [rsp+520h+dwFlagsAndAttributes], rax
0x18000e2b1  lea     rax, [rbp+420h+sz]
0x18000e2b5  mov     qword ptr [rsp+520h+dwCreationDisposition], rax; int
0x18000e2ba  lea     r9, [rbp+420h+PathName]
0x18000e2be  lea     r8, aSSS; "%s%s%s"
0x18000e2c5  mov     rdx, rdi; unsigned __int64
0x18000e2c8  lea     rcx, [rbp+420h+var_240]; unsigned __int16 *
0x18000e2cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e2d4  mov     rcx, [rbp+428h]; this
0x18000e2db  test    eax, eax
0x18000e2dd  jns     short loc_18000E2F4
0x18000e2df  mov     r9d, eax; char *
0x18000e2e2  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e2e9  mov     edx, 48h ; 'H'; void *
0x18000e2ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e2f4  mov     ecx, 30h ; '0'; Size
0x18000e2f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2fe  mov     rdi, rax
0x18000e301  mov     [rsp+520h+var_4D8], rax
0x18000e306  xorps   xmm0, xmm0
0x18000e309  movups  xmmword ptr [rax], xmm0
0x18000e30c  mov     dword ptr [rax+8], 1
0x18000e313  mov     dword ptr [rax+0Ch], 1
0x18000e31a  lea     rax, ??_7?$_Ref_count_obj2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::wstring>::`vftable'
0x18000e321  mov     [rdi], rax
0x18000e324  lea     rbx, [rdi+10h]
0x18000e328  lea     rdx, [rbp+420h+var_240]
0x18000e32f  mov     rcx, rbx
0x18000e332  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000e337  nop
0x18000e338  mov     [rsp+520h+var_4D8], rbx
0x18000e33d  mov     [rsp+520h+var_4D0], rdi
0x18000e342  mov     rcx, [rsi]
0x18000e345  add     rcx, 10h
0x18000e349  lea     rdx, [rsp+520h+var_4D8]
0x18000e34e  call    ??4?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<std::wstring>::operator=(std::shared_ptr<std::wstring> &&)
0x18000e353  mov     rcx, [rsp+520h+var_4D0]; this
0x18000e358  test    rcx, rcx
0x18000e35b  jz      short loc_18000E362
0x18000e35d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e362  mov     rax, [rsi]
0x18000e365  mov     rcx, [rax+10h]
0x18000e369  cmp     qword ptr [rcx+18h], 7
0x18000e36e  jbe     short loc_18000E373
0x18000e370  mov     rcx, [rcx]; lpFileName
0x18000e373  mov     [rsp+520h+hTemplateFile], 0; hTemplateFile
0x18000e37c  mov     [rsp+520h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e384  mov     [rsp+520h+dwCreationDisposition], 2; dwCreationDisposition
0x18000e38c  xor     r9d, r9d; lpSecurityAttributes
0x18000e38f  mov     edx, 40000000h; dwDesiredAccess
0x18000e394  lea     r8d, [r9+7]; dwShareMode
0x18000e398  call    cs:__imp_CreateFileW
0x18000e39e  mov     rcx, [rsi]
0x18000e3a1  mov     [rcx+20h], rax
0x18000e3a5  mov     r9, [rsi]; char *
0x18000e3a8  mov     rcx, [rbp+428h]; this
0x18000e3af  cmp     qword ptr [r9+20h], 0FFFFFFFFFFFFFFFFh
0x18000e3b4  jnz     short loc_18000E3C8
0x18000e3b6  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\monitors\\ap"...
0x18000e3bd  mov     edx, 53h ; 'S'; void *
0x18000e3c2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e3c8  lea     rax, WPP_GLOBAL_Control
0x18000e3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3d6  cmp     rcx, rax
0x18000e3d9  jz      short loc_18000E3F9
0x18000e3db  test    byte ptr [rcx+1Ch], 1
0x18000e3df  jz      short loc_18000E3F9
0x18000e3e1  mov     r9, [r9+10h]
0x18000e3e5  cmp     qword ptr [r9+18h], 7
0x18000e3ea  jbe     short loc_18000E3EF
0x18000e3ec  mov     r9, [r9]
0x18000e3ef  mov     rcx, [rcx+10h]
0x18000e3f3  call    WPP_SF_S
0x18000e3f8  nop
0x18000e3f9  lea     rcx, [rsp+520h+var_4E0]
0x18000e3fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e403  mov     rcx, [rbp+420h+var_30]
0x18000e40a  xor     rcx, rsp; StackCookie
0x18000e40d  call    __security_check_cookie
0x18000e412  add     rsp, 508h
0x18000e419  pop     rdi
0x18000e41a  pop     rsi
0x18000e41b  pop     rbx
0x18000e41c  pop     rbp
0x18000e41d  retn
```
