# OrphanFileFinder::GetApplicationFilesFromRunningProcesses(void)

- ea: `0x18002a7a8`
- end: `0x18002a968`
- name: `?GetApplicationFilesFromRunningProcesses@OrphanFileFinder@@KA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800388dc`

## callees

- `0x1800197d4`
- `0x18002a7a8`
- `0x18003f628`
- `0x180043598`
- `0x18005007c`
- `0x180059920`
- `0x180059cf0`
- `0x180125400`

## import_xrefs

- `KERNEL32!K32EnumProcesses` at `0x18002a875`
- `KERNEL32!K32EnumProcesses` at `0x18002a875`
- `KERNEL32!OpenProcess` at `0x18002a8ce`
- `KERNEL32!OpenProcess` at `0x18002a8ce`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18002a8ff`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18002a8ff`
- `KERNEL32!CloseHandle` at `0x18002a92f`
- `KERNEL32!CloseHandle` at `0x18002a92f`
- `KERNEL32!GetLastError` at `0x18002a87f`
- `KERNEL32!GetLastError` at `0x18002a87f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OrphanFileFinder::GetApplicationFilesFromRunningProcesses(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  void *v3; // rsi
  DWORD *v4; // rcx
  DWORD v5; // eax
  void **unique; // rax
  const struct std::nothrow_t *v7; // rdx
  void *v8; // r14
  void *v9; // rcx
  void *v10; // rcx
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // r14
  char *v13; // rbx
  const struct wil::FailureInfo *v15; // r9
  DWORD cbNeeded; // [rsp+30h] [rbp-1378h] BYREF
  DWORD dwSize[2]; // [rsp+38h] [rbp-1370h] BYREF
  int v18; // [rsp+40h] [rbp-1368h]
  __int64 v19; // [rsp+48h] [rbp-1360h]
  void *v20[3]; // [rsp+50h] [rbp-1358h] BYREF
  void **v21; // [rsp+68h] [rbp-1340h] BYREF
  __int64 v22; // [rsp+70h] [rbp-1338h] BYREF
  _BYTE v23[16]; // [rsp+80h] [rbp-1328h] BYREF
  _BYTE v24[40]; // [rsp+90h] [rbp-1318h] BYREF
  __int128 v25; // [rsp+B8h] [rbp-12F0h]
  __int128 v26; // [rsp+C8h] [rbp-12E0h]
  __int128 v27; // [rsp+D8h] [rbp-12D0h]
  __int128 v28; // [rsp+E8h] [rbp-12C0h]
  __int128 v29; // [rsp+F8h] [rbp-12B0h]
  __int128 v30; // [rsp+108h] [rbp-12A0h]
  __int128 v31; // [rsp+118h] [rbp-1290h]
  __int128 v32; // [rsp+128h] [rbp-1280h]
  __int64 v33; // [rsp+138h] [rbp-1270h]
  _OWORD ExeName[9]; // [rsp+160h] [rbp-1248h] BYREF
  __int64 v35; // [rsp+1F0h] [rbp-11B8h]
  _BYTE v36[4096]; // [rsp+370h] [rbp-1038h] BYREF

  v20[1] = (void *)-2LL;
  v1 = a1;
  v19 = a1;
  std::set<std::wstring>::set<std::wstring>(a1);
  v18 = 1;
  cbNeeded = 0;
  LODWORD(v2) = 1024;
  wil::make_unique_failfast<unsigned long [0]>(v20, 1024);
  v3 = v20[0];
  v4 = (DWORD *)v20[0];
  try
  {
    while ( 1 )
    {
      if ( !K32EnumProcesses(v4, v2, &cbNeeded) )
      {
        GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"OrphanFileFinder::GetApplicationFilesFromRunningProcesses",
          982,
          (unsigned int)"EnumProcesses failed: %d");
        goto LABEL_10;
      }
      v5 = cbNeeded;
      if ( (_DWORD)v2 != cbNeeded )
        break;
      v2 = (unsigned int)(2 * v2);
      unique = (void **)wil::make_unique_failfast<unsigned long [0]>(dwSize, v2);
      v8 = *unique;
      *unique = 0;
      v9 = v3;
      v3 = v8;
      v20[0] = v8;
      if ( v9 )
        operator delete(v9, v7);
      v10 = *(void **)dwSize;
      *(_QWORD *)dwSize = 0;
      if ( v10 )
        operator delete(v10, v7);
      v4 = (DWORD *)v8;
    }
    v12 = 0;
    while ( (unsigned int)v12 < v5 )
    {
      v13 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)v3 + v12));
      v20[2] = v13;
      dwSize[0] = 260;
      if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
        && QueryFullProcessImageNameW(v13, 0, (LPWSTR)ExeName, dwSize) )
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<unsigned short (&)[260]>(
          v1,
          v23,
          ExeName);
      }
      if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v13);
      v12 = (unsigned int)(v12 + 1);
      v5 = cbNeeded;
    }
LABEL_10:
    if ( v3 )
      operator delete(v3, v11);
  }
  catch ( wil::ResultException v24 )
  {
    memset_0(v36, 0, sizeof(v36));
    ExeName[0] = *(_OWORD *)&v24[24];
    ExeName[1] = v25;
    ExeName[2] = v26;
    ExeName[3] = v27;
    ExeName[4] = v28;
    ExeName[5] = v29;
    ExeName[6] = v30;
    ExeName[7] = v31;
    ExeName[8] = v32;
    v35 = v33;
    wil::GetFailureLogString((wil *)v36, (unsigned __int16 *)0x800, (__int64)ExeName, v15);
    AslLogCallPrintf(
      1,
      (unsigned int)"OrphanFileFinder::GetApplicationFilesFromRunningProcesses",
      1005,
      (unsigned int)"%ws");
    wil::ResultException::~ResultException((wil::ResultException *)v24);
    return v19;
  }
  catch ( std::exception v21 )
  {
    GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"OrphanFileFinder::GetApplicationFilesFromRunningProcesses",
      1010,
      (unsigned int)"Exception: 0x%08x %s");
    v21 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v22);
    return v19;
  }
  catch ( ... )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"OrphanFileFinder::GetApplicationFilesFromRunningProcesses",
      1015,
      (unsigned int)"Exception: [0x%08x]");
    return v19;
  }
  return v1;
}

```

## disassembly

```asm
0x18002a7a8  push    rbx
0x18002a7aa  push    rsi
0x18002a7ab  push    rdi
0x18002a7ac  push    r14
0x18002a7ae  mov     eax, 1388h
0x18002a7b3  call    _alloca_probe
0x18002a7b8  sub     rsp, rax
0x18002a7bb  mov     [rsp+13A8h+var_1350], 0FFFFFFFFFFFFFFFEh
0x18002a7c4  mov     rax, cs:__security_cookie
0x18002a7cb  xor     rax, rsp
0x18002a7ce  mov     [rsp+13A8h+var_38], rax
0x18002a7d6  mov     rdi, rcx
0x18002a7d9  mov     [rsp+13A8h+var_1360], rcx
0x18002a7de  mov     [rsp+13A8h+var_1368], 0
0x18002a7e6  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18002a7eb  mov     [rsp+13A8h+var_1368], 1
0x18002a7f3  mov     [rsp+13A8h+cbNeeded], 0
0x18002a7fb  mov     ebx, 400h
0x18002a800  mov     edx, ebx
0x18002a802  lea     rcx, [rsp+13A8h+var_1358]
0x18002a807  call    ??$make_unique_failfast@$$BY0A@K@wil@@YA?AV?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@_K@Z; wil::make_unique_failfast<ulong [0]>(unsigned __int64)
0x18002a80c  nop
0x18002a80d  mov     rsi, [rsp+13A8h+var_1358]
0x18002a812  mov     rcx, rsi
0x18002a815  jmp     short loc_18002A86E
0x18002a817  mov     eax, [rsp+13A8h+cbNeeded]
0x18002a81b  cmp     ebx, eax
0x18002a81d  jnz     loc_18002A8BB
0x18002a823  lea     eax, [rbx+rbx]
0x18002a826  mov     ebx, eax
0x18002a828  mov     edx, eax
0x18002a82a  lea     rcx, [rsp+13A8h+dwSize]
0x18002a82f  call    ??$make_unique_failfast@$$BY0A@K@wil@@YA?AV?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@_K@Z; wil::make_unique_failfast<ulong [0]>(unsigned __int64)
0x18002a834  mov     r14, [rax]
0x18002a837  mov     qword ptr [rax], 0
0x18002a83e  mov     rcx, rsi; void *
0x18002a841  mov     rsi, r14
0x18002a844  mov     [rsp+13A8h+var_1358], r14
0x18002a849  test    rcx, rcx
0x18002a84c  jz      short loc_18002A853
0x18002a84e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a853  mov     rcx, qword ptr [rsp+13A8h+dwSize]; void *
0x18002a858  mov     qword ptr [rsp+13A8h+dwSize], 0
0x18002a861  test    rcx, rcx
0x18002a864  jz      short loc_18002A86B
0x18002a866  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a86b  mov     rcx, r14; lpidProcess
0x18002a86e  lea     r8, [rsp+13A8h+cbNeeded]; lpcbNeeded
0x18002a873  mov     edx, ebx; cb
0x18002a875  call    cs:__imp_K32EnumProcesses
0x18002a87b  test    eax, eax
0x18002a87d  jnz     short loc_18002A817
0x18002a87f  call    cs:__imp_GetLastError
0x18002a885  mov     [rsp+13A8h+var_1388], eax
0x18002a889  lea     r9, aEnumprocessesF; "EnumProcesses failed: %d"
0x18002a890  mov     r8d, 3D6h
0x18002a896  lea     rdx, aOrphanfilefind_1; "OrphanFileFinder::GetApplicationFilesFr"...
0x18002a89d  mov     ecx, 1
0x18002a8a2  call    AslLogCallPrintf
0x18002a8a7  nop
0x18002a8a8  test    rsi, rsi
0x18002a8ab  jz      short loc_18002A8B6
0x18002a8ad  mov     rcx, rsi; void *
0x18002a8b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a8b5  nop
0x18002a8b6  jmp     loc_18002A947
0x18002a8bb  xor     r14d, r14d
0x18002a8be  cmp     r14d, eax
0x18002a8c1  jnb     short loc_18002A8A8
0x18002a8c3  mov     r8d, [rsi+r14*4]; dwProcessId
0x18002a8c7  xor     edx, edx; bInheritHandle
0x18002a8c9  mov     ecx, 1000h; dwDesiredAccess
0x18002a8ce  call    cs:__imp_OpenProcess
0x18002a8d4  mov     rbx, rax
0x18002a8d7  mov     [rsp+13A8h+var_1348], rax
0x18002a8dc  mov     [rsp+13A8h+dwSize], 104h
0x18002a8e4  dec     rax
0x18002a8e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a8eb  ja      short loc_18002A922
0x18002a8ed  lea     r9, [rsp+13A8h+dwSize]; lpdwSize
0x18002a8f2  lea     r8, [rsp+13A8h+ExeName]; lpExeName
0x18002a8fa  xor     edx, edx; dwFlags
0x18002a8fc  mov     rcx, rbx; hProcess
0x18002a8ff  call    cs:__imp_QueryFullProcessImageNameW
0x18002a905  test    eax, eax
0x18002a907  jz      short loc_18002A922
0x18002a909  lea     r8, [rsp+13A8h+ExeName]
0x18002a911  lea     rdx, [rsp+13A8h+var_1328]
0x18002a919  mov     rcx, rdi
0x18002a91c  call    ??$_Emplace@AEAY0BAE@G@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEAY0BAE@G@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<ushort (&)[260]>(ushort (&)[260])
0x18002a921  nop
0x18002a922  lea     rax, [rbx-1]
0x18002a926  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a92a  ja      short loc_18002A935
0x18002a92c  mov     rcx, rbx; hObject
0x18002a92f  call    cs:__imp_CloseHandle
0x18002a935  inc     r14d
0x18002a938  mov     eax, [rsp+13A8h+cbNeeded]
0x18002a93c  jmp     short loc_18002A8BE
0x18002a93e  jmp     short loc_18002A942
0x18002a940  jmp     short $+2
0x18002a942  mov     rdi, [rsp+13A8h+var_1360]
0x18002a947  mov     rax, rdi
0x18002a94a  mov     rcx, [rsp+13A8h+var_38]
0x18002a952  xor     rcx, rsp; StackCookie
0x18002a955  call    __security_check_cookie
0x18002a95a  add     rsp, 1388h
0x18002a961  pop     r14
0x18002a963  pop     rdi
0x18002a964  pop     rsi
0x18002a965  pop     rbx
0x18002a966  retn
```
