# Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800338a0`
- end: `0x180033bcb`
- name: `?ReadWordsFromFile@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@_N@Z`
- size: `811`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18003ff68`
- `0x180040d88`
- `0x18004e3bc`
- `0x18007ff94`

## callees

- `0x18001fb20`
- `0x1800338a0`
- `0x18003a2ec`
- `0x1800414cc`
- `0x18004186c`
- `0x180046e94`
- `0x180047c48`
- `0x18004946c`
- `0x180061320`
- `0x18007d0dc`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180033b3d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180033b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033958`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18003396c`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18003396c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180033a92`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180033a92`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180033a0b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180033a0b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180033a67`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033949`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033949`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(
        __int64 a1,
        const WCHAR *a2,
        char a3)
{
  unsigned int v6; // esi
  DWORD i; // r14d
  __int64 FileW; // rbx
  _QWORD *v9; // rdx
  unsigned __int64 FileSizeFromHandle; // rdi
  HANDLE FileMappingW; // rbx
  _QWORD *v12; // rdx
  _WORD *v13; // rbx
  __int64 v14; // r9
  _QWORD *v15; // rdx
  __int64 WordsFromStream; // rax
  _QWORD v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v20; // [rsp+98h] [rbp-68h]
  _BYTE v21[64]; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hFile; // [rsp+E0h] [rbp-20h]
  _QWORD v23[7]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v24; // [rsp+128h] [rbp+28h]
  _QWORD v25[7]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v26; // [rsp+168h] [rbp+68h]
  _BYTE v27[56]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v28; // [rsp+1A8h] [rbp+A8h]
  _WORD *v29; // [rsp+1B0h] [rbp+B0h]
  _BYTE v30[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  HANDLE v31; // [rsp+200h] [rbp+100h]

  v18[2] = a1;
  std::map<std::wstring const,std::wstring>::map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(a1);
  v23[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
  v23[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
  v24 = v23;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v6 = 0;
  for ( i = 2; v6 < 5; i *= 2 )
  {
    FileW = (__int64)CreateFileW(a2, 0x80000000, 1u, 0, 3u, 1u, 0);
    if ( FileW != -1 )
      goto LABEL_9;
    if ( GetLastError() - 2 <= 1 )
      break;
    SleepEx(i, 1);
    ++v6;
  }
  FileW = -1;
LABEL_9:
  std::function<int (void *)>::function<int (void *)>(v21, v23);
  hFile = (HANDLE)FileW;
  if ( v24 )
  {
    v9 = v23;
    LOBYTE(v9) = v24 != v23;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v9);
    FileW = (__int64)hFile;
  }
  if ( FileW != -1 )
  {
    FileSizeFromHandle = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle((void *)FileW);
    if ( FileSizeFromHandle )
    {
      v25[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
      v25[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
      v26 = v25;
      FileMappingW = CreateFileMappingW(hFile, 0, 2u, 0, 0, 0);
      std::function<int (void *)>::function<int (void *)>(v30, v25);
      v31 = FileMappingW;
      if ( v26 )
      {
        v12 = v25;
        LOBYTE(v12) = v26 != v25;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v26 + 32LL))(v26, v12);
        FileMappingW = v31;
      }
      if ( FileMappingW != (HANDLE)-1LL )
      {
        v19[0] = &std::_Func_impl_no_alloc<int (*)(void const *),int,void const *>::`vftable';
        v19[1] = UnmapViewOfFile;
        v20 = v19;
        v13 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        std::function<int (void *)>::function<int (void *)>(v27, v19);
        v29 = v13;
        if ( v20 )
        {
          v15 = v19;
          LOBYTE(v15) = v20 != v19;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v20 + 32LL))(v20, v15);
          v20 = 0;
          v13 = v29;
        }
        if ( v13 && *v13 == 0xFEFF )
        {
          LOBYTE(v14) = a3;
          WordsFromStream = Windows::Globalization::Spelling::ReadWordsFromStream(
                              v18,
                              v13 + 1,
                              (FileSizeFromHandle >> 1) - 1,
                              v14);
          std::map<std::wstring const,std::wstring>::operator=(a1, WordsFromStream);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v18,
            v18);
          v13 = v29;
        }
        if ( v13 )
        {
          v18[0] = v13;
          if ( !v28 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v28 + 16LL))(v28, v18);
        }
        std::_Func_class<void,UserDictionary *>::_Tidy(v27);
        FileMappingW = v31;
      }
      if ( FileMappingW )
        std::_Func_class<int,void *>::operator()(v30);
      std::_Func_class<void,UserDictionary *>::_Tidy(v30);
    }
    FileW = (__int64)hFile;
  }
  if ( FileW )
    std::_Func_class<int,void *>::operator()(v21);
  std::_Func_class<void,UserDictionary *>::_Tidy(v21);
  return a1;
}

```

## disassembly

```asm
0x1800338a0  push    rbp
0x1800338a2  push    rbx
0x1800338a3  push    rsi
0x1800338a4  push    rdi
0x1800338a5  push    r12
0x1800338a7  push    r14
0x1800338a9  push    r15
0x1800338ab  lea     rbp, [rsp-120h]
0x1800338b3  sub     rsp, 220h
0x1800338ba  mov     rax, cs:__security_cookie
0x1800338c1  xor     rax, rsp
0x1800338c4  mov     [rbp+150h+var_40], rax
0x1800338cb  mov     r12b, r8b
0x1800338ce  mov     rdi, rdx
0x1800338d1  mov     r15, rcx
0x1800338d4  mov     [rsp+250h+var_1F8], rcx
0x1800338d9  mov     [rsp+250h+var_210], 0
0x1800338e1  call    ??0?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,std::wstring>::map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x1800338e6  mov     [rsp+250h+var_210], 1
0x1800338ee  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x1800338f5  mov     [rbp+150h+var_160], rax
0x1800338f9  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x180033900  mov     [rbp+150h+var_158], rax
0x180033904  lea     rax, [rbp+150h+var_160]
0x180033908  mov     [rbp+150h+var_128], rax
0x18003390c  cmp     qword ptr [rdi+18h], 7
0x180033911  jbe     short loc_180033916
0x180033913  mov     rdi, [rdi]
0x180033916  xor     esi, esi
0x180033918  lea     r14d, [rsi+2]
0x18003391c  cmp     esi, 5
0x18003391f  jnb     short loc_180033979
0x180033921  mov     [rsp+250h+hTemplateFile], 0; hTemplateFile
0x18003392a  mov     [rsp+250h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x180033932  mov     [rsp+250h+dwCreationDisposition], 3; dwCreationDisposition
0x18003393a  xor     r9d, r9d; lpSecurityAttributes
0x18003393d  mov     edx, 80000000h; dwDesiredAccess
0x180033942  lea     r8d, [r9+1]; dwShareMode
0x180033946  mov     rcx, rdi; lpFileName
0x180033949  call    cs:__imp_CreateFileW
0x18003394f  mov     rbx, rax
0x180033952  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033956  jnz     short loc_18003397D
0x180033958  call    cs:__imp_GetLastError
0x18003395e  add     eax, 0FFFFFFFEh
0x180033961  cmp     eax, 1
0x180033964  jbe     short loc_180033979
0x180033966  lea     edx, [rbx+2]; bAlertable
0x180033969  mov     ecx, r14d; dwMilliseconds
0x18003396c  call    cs:__imp_SleepEx
0x180033972  add     r14d, r14d
0x180033975  inc     esi
0x180033977  jmp     short loc_18003391C
0x180033979  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003397d  lea     rdx, [rbp+150h+var_160]
0x180033981  lea     rcx, [rbp+150h+var_1B0]
0x180033985  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x18003398a  mov     [rbp+150h+hFile], rbx
0x18003398e  mov     rcx, [rbp+150h+var_128]
0x180033992  test    rcx, rcx
0x180033995  jz      short loc_1800339B1
0x180033997  mov     rax, [rcx]
0x18003399a  lea     rdx, [rbp+150h+var_160]
0x18003399e  cmp     rcx, rdx
0x1800339a1  setnz   dl
0x1800339a4  mov     rax, [rax+20h]
0x1800339a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ad  mov     rbx, [rbp+150h+hFile]
0x1800339b1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800339b5  jz      loc_180033B8B
0x1800339bb  mov     rcx, rbx; void *
0x1800339be  call    ?GetFileSizeFromHandle@UserDictionaries@Spelling@Globalization@Windows@@SA_KPEAX@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle(void *)
0x1800339c3  mov     rdi, rax
0x1800339c6  test    rax, rax
0x1800339c9  jz      loc_180033B87
0x1800339cf  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x1800339d6  mov     [rbp+150h+var_120], rax
0x1800339da  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x1800339e1  mov     [rbp+150h+var_118], rax
0x1800339e5  lea     rax, [rbp+150h+var_120]
0x1800339e9  mov     [rbp+150h+var_E8], rax
0x1800339ed  mov     qword ptr [rsp+250h+dwFlagsAndAttributes], 0; lpName
0x1800339f6  mov     [rsp+250h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800339fe  xor     r9d, r9d; dwMaximumSizeHigh
0x180033a01  xor     edx, edx; lpFileMappingAttributes
0x180033a03  lea     r8d, [r9+2]; flProtect
0x180033a07  mov     rcx, [rbp+150h+hFile]; hFile
0x180033a0b  call    cs:__imp_CreateFileMappingW
0x180033a11  mov     rbx, rax
0x180033a14  lea     rdx, [rbp+150h+var_120]
0x180033a18  lea     rcx, [rbp+150h+var_90]
0x180033a1f  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x180033a24  mov     [rbp+150h+var_50], rbx
0x180033a2b  mov     rcx, [rbp+150h+var_E8]
0x180033a2f  test    rcx, rcx
0x180033a32  jz      short loc_180033A51
0x180033a34  mov     rax, [rcx]
0x180033a37  lea     rdx, [rbp+150h+var_120]
0x180033a3b  cmp     rcx, rdx
0x180033a3e  setnz   dl
0x180033a41  mov     rax, [rax+20h]
0x180033a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a4a  mov     rbx, [rbp+150h+var_50]
0x180033a51  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180033a55  jz      loc_180033B66
0x180033a5b  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEBX@ZHPEBX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void const *),int,void const *>::`vftable'
0x180033a62  mov     [rsp+250h+var_1F0], rax
0x180033a67  mov     rax, cs:__imp_UnmapViewOfFile
0x180033a6e  mov     [rsp+250h+var_1E8], rax
0x180033a73  lea     rax, [rsp+250h+var_1F0]
0x180033a78  mov     [rbp+150h+var_1B8], rax
0x180033a7c  mov     qword ptr [rsp+250h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180033a85  xor     r9d, r9d; dwFileOffsetLow
0x180033a88  xor     r8d, r8d; dwFileOffsetHigh
0x180033a8b  lea     edx, [r9+4]; dwDesiredAccess
0x180033a8f  mov     rcx, rbx; hFileMappingObject
0x180033a92  call    cs:__imp_MapViewOfFile
0x180033a98  mov     rbx, rax
0x180033a9b  lea     rdx, [rsp+250h+var_1F0]
0x180033aa0  lea     rcx, [rbp+150h+var_E0]
0x180033aa4  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x180033aa9  mov     [rbp+150h+var_A0], rbx
0x180033ab0  mov     rcx, [rbp+150h+var_1B8]
0x180033ab4  test    rcx, rcx
0x180033ab7  jz      short loc_180033ADF
0x180033ab9  mov     rax, [rcx]
0x180033abc  lea     rdx, [rsp+250h+var_1F0]
0x180033ac1  cmp     rcx, rdx
0x180033ac4  setnz   dl
0x180033ac7  mov     rax, [rax+20h]
0x180033acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ad0  mov     [rbp+150h+var_1B8], 0
0x180033ad8  mov     rbx, [rbp+150h+var_A0]
0x180033adf  test    rbx, rbx
0x180033ae2  jz      short loc_180033B27
0x180033ae4  mov     eax, 0FEFFh
0x180033ae9  cmp     [rbx], ax
0x180033aec  jnz     short loc_180033B27
0x180033aee  shr     rdi, 1
0x180033af1  lea     r8, [rdi-1]
0x180033af5  lea     rdx, [rbx+2]
0x180033af9  mov     r9b, r12b
0x180033afc  lea     rcx, [rsp+250h+var_208]
0x180033b01  call    Windows__Globalization__Spelling__ReadWordsFromStream
0x180033b06  mov     rdx, rax
0x180033b09  mov     rcx, r15
0x180033b0c  call    ??4?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::map<std::wstring const,std::wstring>::operator=(std::map<std::wstring const,std::wstring> &&)
0x180033b11  lea     rdx, [rsp+250h+var_208]
0x180033b16  lea     rcx, [rsp+250h+var_208]
0x180033b1b  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180033b20  mov     rbx, [rbp+150h+var_A0]
0x180033b27  test    rbx, rbx
0x180033b2a  jz      short loc_180033B55
0x180033b2c  mov     [rsp+250h+var_208], rbx
0x180033b31  mov     rcx, [rbp+150h+var_A8]
0x180033b38  test    rcx, rcx
0x180033b3b  jnz     short loc_180033B44
0x180033b3d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180033b43  int     3; Trap to Debugger
0x180033b44  mov     rax, [rcx]
0x180033b47  lea     rdx, [rsp+250h+var_208]
0x180033b4c  mov     rax, [rax+10h]
0x180033b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b55  lea     rcx, [rbp+150h+var_E0]
0x180033b59  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180033b5e  nop
0x180033b5f  mov     rbx, [rbp+150h+var_50]
0x180033b66  test    rbx, rbx
0x180033b69  jz      short loc_180033B7A
0x180033b6b  mov     rdx, rbx
0x180033b6e  lea     rcx, [rbp+150h+var_90]
0x180033b75  call    ??R?$_Func_class@HPEAX@std@@QEBAHPEAX@Z; std::_Func_class<int,void *>::operator()(void *)
0x180033b7a  lea     rcx, [rbp+150h+var_90]
0x180033b81  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180033b86  nop
0x180033b87  mov     rbx, [rbp+150h+hFile]
0x180033b8b  test    rbx, rbx
0x180033b8e  jz      short loc_180033B9C
0x180033b90  mov     rdx, rbx
0x180033b93  lea     rcx, [rbp+150h+var_1B0]
0x180033b97  call    ??R?$_Func_class@HPEAX@std@@QEBAHPEAX@Z; std::_Func_class<int,void *>::operator()(void *)
0x180033b9c  lea     rcx, [rbp+150h+var_1B0]
0x180033ba0  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180033ba5  nop
0x180033ba6  mov     rax, r15
0x180033ba9  mov     rcx, [rbp+150h+var_40]
0x180033bb0  xor     rcx, rsp; StackCookie
0x180033bb3  call    __security_check_cookie
0x180033bb8  add     rsp, 220h
0x180033bbf  pop     r15
0x180033bc1  pop     r14
0x180033bc3  pop     r12
0x180033bc5  pop     rdi
0x180033bc6  pop     rsi
0x180033bc7  pop     rbx
0x180033bc8  pop     rbp
0x180033bc9  retn
```
