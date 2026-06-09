# CMedicEtwConsumer::_GetExistingLogFiles(bool,std::map<unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18002f874`
- end: `0x18002fa28`
- name: `?_GetExistingLogFiles@CMedicEtwConsumer@@AEAAJ_NAEAV?$map@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180039350`

## callees

- `0x1800050a0`
- `0x180005584`
- `0x180005bbc`
- `0x180009cd0`
- `0x18002eca4`
- `0x18002f584`
- `0x18002f874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9c3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002f993`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002f993`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002f9f0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002f9f0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002f948`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002f948`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002f919`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002f919`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CMedicEtwConsumer::_GetExistingLogFiles(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  void *v7; // rbx
  _QWORD *v8; // rcx
  const WCHAR **v9; // rsi
  const WCHAR *v10; // r8
  int v11; // edi
  __int64 v12; // rcx
  char *FirstFileW; // rbx
  __int64 v14; // rdx
  signed int v15; // eax
  signed int LastError; // eax
  char *v18; // [rsp+20h] [rbp-498h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-488h] BYREF
  WCHAR pszPathOut[264]; // [rsp+280h] [rbp-238h] BYREF

  v5 = (_QWORD *)*a3;
  v6 = *(_QWORD **)(*a3 + 8LL);
  while ( !*((_BYTE *)v6 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::wstring>,void *>>>(
      a3,
      a3,
      v6[2]);
    v7 = v6;
    v8 = v6;
    v6 = (_QWORD *)*v6;
    std::wstring::~wstring(v8 + 5);
    operator delete(v7, (const struct std::nothrow_t *)0x48);
  }
  v5[1] = v5;
  *v5 = v5;
  v5[2] = v5;
  a3[1] = 0;
  v9 = (const WCHAR **)(a1 + 48);
  if ( *(_QWORD *)(a1 + 72) <= 7u )
    v10 = (const WCHAR *)(a1 + 48);
  else
    v10 = *v9;
  v11 = PathCchCombine(pszPathOut, 0x104u, v10, L"waasmedic*.etl");
  if ( v11 >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = (char *)FindFirstFileW(pszPathOut, &FindFileData);
    v18 = FirstFileW;
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 == -2147024894 )
        v11 = 0;
    }
    else
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x410) == 0 )
        {
          v14 = *(_QWORD *)(a1 + 72) <= 7u ? a1 + 48 : (__int64)*v9;
          v11 = CMedicEtwConsumer::_AddFileToMap(v12, v14, &FindFileData, a3, v18);
          if ( v11 < 0 )
            break;
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          if ( GetLastError() != 18 )
          {
            v15 = GetLastError();
            v11 = v15;
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
          }
          break;
        }
      }
    }
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(FirstFileW);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002f874  mov     [rsp+arg_8], rbx
0x18002f879  mov     [rsp+arg_18], rsi
0x18002f87e  push    rdi
0x18002f87f  push    r14
0x18002f881  push    r15
0x18002f883  sub     rsp, 4A0h
0x18002f88a  mov     rax, cs:__security_cookie
0x18002f891  xor     rax, rsp
0x18002f894  mov     [rsp+4B8h+var_28], rax
0x18002f89c  mov     r14, r8
0x18002f89f  mov     r15, rcx
0x18002f8a2  mov     rdi, [r8]
0x18002f8a5  mov     rsi, [rdi+8]
0x18002f8a9  jmp     short loc_18002F8D9
0x18002f8ab  mov     r8, [rsi+10h]
0x18002f8af  mov     rdx, r14
0x18002f8b2  mov     rcx, r14
0x18002f8b5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::wstring>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::wstring>,void *> *)
0x18002f8ba  mov     rbx, rsi
0x18002f8bd  mov     rcx, rsi
0x18002f8c0  mov     rsi, [rsi]
0x18002f8c3  add     rcx, 28h ; '('; void *
0x18002f8c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f8cc  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18002f8d1  mov     rcx, rbx; void *
0x18002f8d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f8d9  cmp     byte ptr [rsi+19h], 0
0x18002f8dd  jz      short loc_18002F8AB
0x18002f8df  mov     [rdi+8], rdi
0x18002f8e3  mov     [rdi], rdi
0x18002f8e6  mov     [rdi+10h], rdi
0x18002f8ea  mov     qword ptr [r14+8], 0
0x18002f8f2  lea     rsi, [r15+30h]
0x18002f8f6  cmp     qword ptr [rsi+18h], 7
0x18002f8fb  jbe     short loc_18002F902
0x18002f8fd  mov     r8, [rsi]
0x18002f900  jmp     short loc_18002F905
0x18002f902  mov     r8, rsi; pszPathIn
0x18002f905  lea     r9, aWaasmedicEtl; "waasmedic*.etl"
0x18002f90c  mov     edx, 104h; cchPathOut
0x18002f911  lea     rcx, [rsp+4B8h+pszPathOut]; pszPathOut
0x18002f919  call    cs:__imp_PathCchCombine
0x18002f91f  mov     edi, eax
0x18002f921  test    eax, eax
0x18002f923  js      loc_18002F9F6
0x18002f929  xor     edx, edx; Val
0x18002f92b  mov     r8d, 250h; Size
0x18002f931  lea     rcx, [rsp+4B8h+FindFileData]; void *
0x18002f936  call    memset_0
0x18002f93b  lea     rdx, [rsp+4B8h+FindFileData]; lpFindFileData
0x18002f940  lea     rcx, [rsp+4B8h+pszPathOut]; lpFileName
0x18002f948  call    cs:__imp_FindFirstFileW
0x18002f94e  mov     rbx, rax
0x18002f951  mov     [rsp+4B8h+var_498], rax
0x18002f956  dec     rax
0x18002f959  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f95d  ja      short loc_18002F9C3
0x18002f95f  test    [rsp+4B8h+FindFileData.dwFileAttributes], 410h
0x18002f967  jnz     short loc_18002F98B
0x18002f969  cmp     qword ptr [rsi+18h], 7
0x18002f96e  jbe     short loc_18002F975
0x18002f970  mov     rdx, [rsi]
0x18002f973  jmp     short loc_18002F978
0x18002f975  mov     rdx, rsi
0x18002f978  mov     r9, r14
0x18002f97b  lea     r8, [rsp+4B8h+FindFileData]
0x18002f980  call    ?_AddFileToMap@CMedicEtwConsumer@@AEAAJPEBGPEBU_WIN32_FIND_DATAW@@AEAV?$map@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@@Z; CMedicEtwConsumer::_AddFileToMap(ushort const *,_WIN32_FIND_DATAW const *,std::map<unsigned __int64,std::wstring> &)
0x18002f985  mov     edi, eax
0x18002f987  test    eax, eax
0x18002f989  js      short loc_18002F9E3
0x18002f98b  lea     rdx, [rsp+4B8h+FindFileData]; lpFindFileData
0x18002f990  mov     rcx, rbx; hFindFile
0x18002f993  call    cs:__imp_FindNextFileW
0x18002f999  test    eax, eax
0x18002f99b  jnz     short loc_18002F95F
0x18002f99d  test    edi, edi
0x18002f99f  js      short loc_18002F9E3
0x18002f9a1  call    cs:__imp_GetLastError
0x18002f9a7  cmp     eax, 12h
0x18002f9aa  jz      short loc_18002F9E3
0x18002f9ac  call    cs:__imp_GetLastError
0x18002f9b2  mov     edi, eax
0x18002f9b4  test    eax, eax
0x18002f9b6  jle     short loc_18002F9E3
0x18002f9b8  movzx   edi, ax
0x18002f9bb  or      edi, 80070000h
0x18002f9c1  jmp     short loc_18002F9E3
0x18002f9c3  call    cs:__imp_GetLastError
0x18002f9c9  mov     edi, eax
0x18002f9cb  test    eax, eax
0x18002f9cd  jle     short loc_18002F9D8
0x18002f9cf  movzx   edi, ax
0x18002f9d2  or      edi, 80070000h
0x18002f9d8  xor     eax, eax
0x18002f9da  cmp     edi, 80070002h
0x18002f9e0  cmovz   edi, eax
0x18002f9e3  lea     rax, [rbx-1]
0x18002f9e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f9eb  ja      short loc_18002F9F6
0x18002f9ed  mov     rcx, rbx; hFindFile
0x18002f9f0  call    cs:__imp_FindClose
0x18002f9f6  mov     eax, edi
0x18002f9f8  jmp     short loc_18002F9FE
0x18002f9fa  mov     eax, dword ptr [rsp+4B8h+var_498]
0x18002f9fe  mov     rcx, [rsp+4B8h+var_28]
0x18002fa06  xor     rcx, rsp; StackCookie
0x18002fa09  call    __security_check_cookie
0x18002fa0e  lea     r11, [rsp+4B8h+var_18]
0x18002fa16  mov     rbx, [r11+28h]
0x18002fa1a  mov     rsi, [r11+38h]
0x18002fa1e  mov     rsp, r11
0x18002fa21  pop     r15
0x18002fa23  pop     r14
0x18002fa25  pop     rdi
0x18002fa26  retn
```
