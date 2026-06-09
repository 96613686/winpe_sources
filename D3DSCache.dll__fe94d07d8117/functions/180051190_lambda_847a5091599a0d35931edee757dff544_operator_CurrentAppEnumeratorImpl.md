# _lambda_847a5091599a0d35931edee757dff544_::operator()_CurrentAppEnumeratorImpl_

- ea: `0x180051190`
- end: `0x1800513ba`
- name: `_lambda_847a5091599a0d35931edee757dff544_::operator()_CurrentAppEnumeratorImpl_`
- size: `554`
- prototype: `void __fastcall __noreturn(__int64, CurrentAppEnumeratorImpl *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180001d70`

## callees

- `0x180001bd0`
- `0x180001ce0`
- `0x180003794`
- `0x18001a700`
- `0x180021a70`
- `0x180029170`
- `0x18002a1e0`
- `0x18003b704`
- `0x18003ed98`
- `0x18003fec0`
- `0x1800449f0`
- `0x180045374`
- `0x180051190`
- `0x180051668`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800512e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800512e8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180051337`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180051337`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180051325`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180051325`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005129d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005129d`

## string_xrefs

- `0x18005125f`: `*.dxcache`

## pseudocode

```c
void __fastcall __noreturn lambda_847a5091599a0d35931edee757dff544_::operator()_CurrentAppEnumeratorImpl_(
        __int64 a1,
        CurrentAppEnumeratorImpl *a2,
        int a3)
{
  unsigned int v6; // r8d
  const wchar_t **v7; // rdi
  HANDLE FirstFileW; // r14
  unsigned int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // r8
  const wchar_t *v12; // [rsp+40h] [rbp-C0h] BYREF
  char v13; // [rsp+48h] [rbp-B8h]
  const wchar_t *v14; // [rsp+50h] [rbp-B0h]
  char v15; // [rsp+58h] [rbp-A8h]
  const wchar_t *v16; // [rsp+60h] [rbp-A0h]
  char v17; // [rsp+68h] [rbp-98h]
  const wchar_t *v18; // [rsp+70h] [rbp-90h]
  char v19; // [rsp+78h] [rbp-88h]
  _BYTE v20[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-60h]
  _BYTE v22[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[32]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v24[3]; // [rsp+F0h] [rbp-10h] BYREF
  int v25; // [rsp+108h] [rbp+8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+110h] [rbp+10h] BYREF

  while ( *(_BYTE *)a2 )
  {
    AppData::AppData((AppData *)v22);
    std::wstring::wstring(v20, &qword_1800ACF70);
    std::wstring::operator=(v22, v20);
    std::wstring::~wstring(v20);
    v25 = a3;
    std::wstring::wstring(v20, (char *)a2 + 2);
    std::wstring::operator=(v23, v20);
    std::wstring::~wstring(v20);
    v12 = L"*.idx";
    v13 = 0;
    v14 = L"*.lock";
    v15 = 0;
    v16 = L"*.val";
    v17 = 0;
    v18 = L"*.dxcache";
    v19 = 1;
    v7 = &v12;
    do
    {
      CurrentAppEnumeratorImpl::GetCurrentPackagePathCached(a2, *(unsigned __int16 **)(a1 + 8), v6, *v7);
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(*(LPCWSTR *)(a1 + 8), &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          std::wstring::wstring(v20);
          v21 = 0;
          CurrentAppEnumeratorImpl::GetCurrentPackagePathCached(
            a2,
            *(unsigned __int16 **)(a1 + 8),
            v9,
            FindFileData.cFileName);
          v10 = *(_QWORD *)(a1 + 8);
          if ( *((_BYTE *)v7 + 8) )
          {
            v11 = -1;
            do
              ++v11;
            while ( *(_WORD *)(v10 + 2 * v11) );
            std::wstring::_Assign<unsigned short>(v20, v10);
            std::vector<AppCacheData>::push_back(v24, v20);
          }
          else
          {
            DeleteFileW(*(LPCWSTR *)(a1 + 8));
          }
          std::wstring::~wstring(v20);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
      }
      v7 += 2;
    }
    while ( v7 != (const wchar_t **)v20 );
    std::_Func_class<void,AppData &>::operator()(*(_QWORD *)(a1 + 16), v22);
    if ( a3 == 1 || v24[0] != v24[1] )
      std::vector<AppData>::push_back(*(_QWORD *)a1 + 8LL, v22);
    *(_BYTE *)a2 = 0;
    AppData::~AppData((AppData *)v22);
  }
}

```

## disassembly

```asm
0x180051190  mov     [rsp-8+arg_18], rbx
0x180051195  push    rbp
0x180051196  push    rsi
0x180051197  push    rdi
0x180051198  push    r12
0x18005119a  push    r13
0x18005119c  push    r14
0x18005119e  push    r15
0x1800511a0  lea     rbp, [rsp-270h]
0x1800511a8  sub     rsp, 370h
0x1800511af  mov     rax, cs:__security_cookie
0x1800511b6  xor     rax, rsp
0x1800511b9  mov     [rbp+2A0h+var_40], rax
0x1800511c0  mov     r15d, r8d
0x1800511c3  mov     rbx, rdx
0x1800511c6  mov     rsi, rcx
0x1800511c9  xor     r13d, r13d
0x1800511cc  cmp     [rdx], r13b
0x1800511cf  jz      loc_180051390
0x1800511d5  lea     rcx, [rbp+2A0h+var_2F0]; this
0x1800511d9  call    ??0AppData@@QEAA@XZ
0x1800511de  nop
0x1800511df  lea     rdx, qword_1800ACF70
0x1800511e6  lea     rcx, [rbp+2A0h+var_320]
0x1800511ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z
0x1800511ef  lea     rdx, [rbp+2A0h+var_320]
0x1800511f3  lea     rcx, [rbp+2A0h+var_2F0]
0x1800511f7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x1800511fc  lea     rcx, [rbp+2A0h+var_320]
0x180051200  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180051205  mov     [rbp+2A0h+var_298], r15d
0x180051209  lea     rdx, [rbx+2]
0x18005120d  lea     rcx, [rbp+2A0h+var_320]
0x180051211  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z
0x180051216  lea     rdx, [rbp+2A0h+var_320]
0x18005121a  lea     rcx, [rbp+2A0h+var_2D0]
0x18005121e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180051223  lea     rcx, [rbp+2A0h+var_320]
0x180051227  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18005122c  lea     rax, aIdx
0x180051233  mov     [rsp+3A0h+var_360], rax
0x180051238  mov     [rsp+3A0h+var_358], r13b
0x18005123d  lea     rax, aLock
0x180051244  mov     [rsp+3A0h+var_350], rax
0x180051249  mov     [rsp+3A0h+var_348], r13b
0x18005124e  lea     rax, aVal
0x180051255  mov     [rsp+3A0h+var_340], rax
0x18005125a  mov     [rsp+3A0h+var_338], r13b
0x18005125f  lea     rax, aDxcache_0
0x180051266  mov     [rsp+3A0h+var_330], rax
0x18005126b  mov     [rsp+3A0h+var_328], 1
0x180051270  lea     rdi, [rsp+3A0h+var_360]
0x180051275  mov     r9, [rdi]; unsigned __int16 *
0x180051278  mov     rdx, [rsi+8]; unsigned __int16 *
0x18005127c  mov     rcx, rbx; this
0x18005127f  call    ?GetCurrentPackagePathCached@CurrentAppEnumeratorImpl@@QEAAXPEAGIPEBG@Z
0x180051284  xor     edx, edx; Val
0x180051286  mov     r8d, 250h; Size
0x18005128c  lea     rcx, [rbp+2A0h+FindFileData]; void *
0x180051290  call    memset_0
0x180051295  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x180051299  mov     rcx, [rsi+8]; lpFileName
0x18005129d  call    cs:__imp_FindFirstFileW
0x1800512a3  mov     r14, rax
0x1800512a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800512aa  jz      loc_18005133D
0x1800512b0  mov     [rsp+3A0h+var_378], rax
0x1800512b5  mov     [rsp+3A0h+var_370], 1
0x1800512ba  lea     rcx, [rbp+2A0h+var_320]
0x1800512be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800512c3  nop
0x1800512c4  xorps   xmm1, xmm1
0x1800512c7  movups  [rbp+2A0h+var_300], xmm1
0x1800512cb  lea     r9, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x1800512cf  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800512d3  mov     rcx, rbx; this
0x1800512d6  call    ?GetCurrentPackagePathCached@CurrentAppEnumeratorImpl@@QEAAXPEAGIPEBG@Z
0x1800512db  mov     rdx, [rsi+8]
0x1800512df  cmp     [rdi+8], r13b
0x1800512e3  jnz     short loc_1800512F0
0x1800512e5  mov     rcx, rdx; lpFileName
0x1800512e8  call    cs:__imp_DeleteFileW
0x1800512ee  jmp     short loc_180051315
0x1800512f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800512f4  inc     r8
0x1800512f7  cmp     [rdx+r8*2], r13w
0x1800512fc  jnz     short loc_1800512F4
0x1800512fe  lea     rcx, [rbp+2A0h+var_320]
0x180051302  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z
0x180051307  lea     rdx, [rbp+2A0h+var_320]
0x18005130b  lea     rcx, [rbp+2A0h+var_2B0]
0x18005130f  call    ?push_back@?$vector@UAppCacheData@@V?$allocator@UAppCacheData@@@std@@@std@@QEAAX$$QEAUAppCacheData@@@Z
0x180051314  nop
0x180051315  lea     rcx, [rbp+2A0h+var_320]
0x180051319  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18005131e  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x180051322  mov     rcx, r14; hFindFile
0x180051325  call    cs:__imp_FindNextFileW
0x18005132b  test    eax, eax
0x18005132d  jnz     short loc_1800512BA
0x18005132f  mov     [rsp+3A0h+var_370], r13b
0x180051334  mov     rcx, r14; hFindFile
0x180051337  call    cs:__imp_FindClose
0x18005133d  add     rdi, 10h
0x180051341  lea     rax, [rbp+2A0h+var_320]
0x180051345  cmp     rdi, rax
0x180051348  jnz     loc_180051275
0x18005134e  lea     rdx, [rbp+2A0h+var_2F0]
0x180051352  mov     rcx, [rsi+10h]
0x180051356  call    ??R?$_Func_class@XAEAUAppData@@@std@@QEBAXAEAUAppData@@@Z
0x18005135b  cmp     r15d, 1
0x18005135f  jz      short loc_18005136B
0x180051361  mov     rax, [rbp+2A0h+var_2A8]
0x180051365  cmp     [rbp+2A0h+var_2B0], rax
0x180051369  jz      short loc_18005137B
0x18005136b  mov     rcx, [rsi]
0x18005136e  add     rcx, 8
0x180051372  lea     rdx, [rbp+2A0h+var_2F0]
0x180051376  call    ?push_back@?$vector@UAppData@@V?$allocator@UAppData@@@std@@@std@@QEAAX$$QEAUAppData@@@Z
0x18005137b  mov     [rbx], r13b
0x18005137e  lea     rcx, [rbp+2A0h+var_2F0]; this
0x180051382  call    ??1AppData@@QEAA@XZ
0x180051387  cmp     [rbx], r13b
0x18005138a  jnz     loc_1800511D5
0x180051390  mov     rcx, [rbp+2A0h+var_40]
0x180051397  xor     rcx, rsp; StackCookie
0x18005139a  call    __security_check_cookie
0x18005139f  mov     rbx, [rsp+3A0h+arg_18]
0x1800513a7  add     rsp, 370h
0x1800513ae  pop     r15
0x1800513b0  pop     r14
0x1800513b2  pop     r13
0x1800513b4  pop     r12
0x1800513b6  pop     rdi
0x1800513b7  pop     rsi
0x1800513b8  pop     rbp
0x1800513b9  retn
```
