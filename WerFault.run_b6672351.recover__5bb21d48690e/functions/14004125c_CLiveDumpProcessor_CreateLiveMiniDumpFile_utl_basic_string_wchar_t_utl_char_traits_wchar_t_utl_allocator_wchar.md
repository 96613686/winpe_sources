# CLiveDumpProcessor::CreateLiveMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x14004125c`
- end: `0x1400415b0`
- name: `?CreateLiveMiniDumpFile@CLiveDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140040e18`

## callees

- `0x140002748`
- `0x14000ca20`
- `0x140012fb0`
- `0x140014a88`
- `0x1400167a4`
- `0x1400372dc`
- `0x14004125c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004136b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004137e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004136b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004137e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400414b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400414b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041508`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14004135b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14004135b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041447`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041447`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14004151e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14004151e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400412f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400412f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041585`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041585`

## string_xrefs

- `0x140041327`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x1400413ac`: `Unable to create the folder %ws`
- `0x140041488`: `Copy failed`
- `0x1400413bc`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x1400414e0`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x140041549`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x1400414cb`: `Live minidump directory not set`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLiveDumpProcessor::CreateLiveMiniDumpFile(__int64 a1, __int64 a2, void **a3)
{
  char *v6; // rsi
  const wchar_t *v7; // rdi
  PSECURITY_DESCRIPTOR *v8; // rax
  signed int v9; // eax
  signed int v10; // ebx
  signed int LastError; // eax
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rdx
  void *v15; // rcx
  WCHAR *v16; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-60h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  const char *hTemplateFile; // [rsp+30h] [rbp-50h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-28h] BYREF
  const WCHAR *v24; // [rsp+60h] [rbp-20h]
  _WORD v25[12]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+B8h] [rbp+38h]
  HLOCAL hMem; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+58h]

  v6 = 0;
  v28 = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  lpFileName = v25;
  v24 = v25;
  v25[0] = 0;
  if ( !a2 || !a3 )
  {
    v10 = -2147024809;
    LODWORD(dwCreationDisposition) = -2147024809;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CreateLiveMiniDumpFile",
      dwCreationDisposition,
      (int)"Invalid args",
      hTemplateFile);
    v16 = (WCHAR *)lpFileName;
    goto LABEL_39;
  }
  v7 = *(const wchar_t **)(a1 + 40);
  if ( v7 && *v7 )
  {
    v8 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, v8, 0) )
    {
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = hMem;
      if ( CreateDirectoryW(v7, &SecurityAttributes) || GetLastError() == 183 )
      {
        UtilSetPathToSoftReserve(v7);
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( v7[v13] );
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&lpFileName, v7);
        v14 = *(_QWORD *)(a1 + 104);
        if ( v14 )
        {
          do
            ++v12;
          while ( *(_WORD *)(v14 + 2 * v12) );
        }
        else
        {
          v12 = 0;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpFileName, v14, v12);
        v6 = (char *)CreateFileW(lpFileName, 0x40040000u, 0, &SecurityAttributes, 1u, 0x80u, 0);
        if ( v6 == (char *)-1LL || v6 + 1 == (char *)1 )
        {
          v10 = -2147467259;
        }
        else
        {
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  a2,
                                  lpFileName) )
          {
            v28 = 0;
            v15 = *a3;
            *a3 = v6;
            if ( (unsigned __int64)v15 + 1 > 1 )
              CloseHandle(v15);
            v10 = 0;
            goto LABEL_36;
          }
          v10 = -2147024882;
          LODWORD(dwCreationDispositiona) = -2147024882;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0xD4,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
            "CLiveDumpProcessor::CreateLiveMiniDumpFile",
            dwCreationDispositiona,
            (int)"Copy failed",
            hTemplateFilea);
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( v10 >= 0 )
          v10 = -2147467259;
        LODWORD(dwCreationDisposition) = v10;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
          "CLiveDumpProcessor::CreateLiveMiniDumpFile",
          dwCreationDisposition,
          (int)"Unable to create the folder %ws",
          (const char *)v7);
      }
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      LODWORD(dwCreationDisposition) = v10;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::CreateLiveMiniDumpFile",
        dwCreationDisposition,
        (int)"ConvertStringSecurityDescriptorToSecurityDescriptor failed",
        hTemplateFile);
    }
  }
  else
  {
    v10 = -2147467259;
    LODWORD(dwCreationDisposition) = -2147467259;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CreateLiveMiniDumpFile",
      dwCreationDisposition,
      (int)"Live minidump directory not set",
      hTemplateFile);
  }
  v28 = 0;
  if ( (unsigned __int64)(v6 + 1) > 1 )
    CloseHandle(v6);
  v16 = (WCHAR *)lpFileName;
  if ( lpFileName != v24 )
  {
    DeleteFileW(lpFileName);
LABEL_36:
    v16 = (WCHAR *)lpFileName;
  }
LABEL_39:
  if ( v16 != v25 )
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14004125c  mov     [rsp-38h+arg_0], rbx
0x140041261  push    rbp
0x140041262  push    rsi
0x140041263  push    rdi
0x140041264  push    r12
0x140041266  push    r13
0x140041268  push    r14
0x14004126a  push    r15
0x14004126c  mov     rbp, rsp
0x14004126f  sub     rsp, 80h
0x140041276  mov     r14, r8
0x140041279  mov     r12, rdx
0x14004127c  mov     r15, rcx
0x14004127f  xor     r13d, r13d
0x140041282  mov     esi, r13d
0x140041285  mov     [rbp+arg_18], r13
0x140041289  mov     [rbp+hMem], r13
0x14004128d  xorps   xmm0, xmm0
0x140041290  xor     eax, eax
0x140041292  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x140041296  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x14004129a  lea     rax, [rbp+var_18]
0x14004129e  mov     [rbp+lpFileName], rax
0x1400412a2  lea     rax, [rbp+var_18]
0x1400412a6  mov     [rbp+var_20], rax
0x1400412aa  mov     [rbp+var_18], r13w
0x1400412af  test    rdx, rdx
0x1400412b2  jz      loc_140041530
0x1400412b8  test    r8, r8
0x1400412bb  jz      loc_140041530
0x1400412c1  mov     rdi, [rcx+28h]
0x1400412c5  test    rdi, rdi
0x1400412c8  jz      loc_1400414C4
0x1400412ce  cmp     [rdi], r13w
0x1400412d2  jz      loc_1400414C4
0x1400412d8  lea     rcx, [rbp+hMem]
0x1400412dc  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1400412e1  mov     r8, rax; SecurityDescriptor
0x1400412e4  xor     r9d, r9d; SecurityDescriptorSize
0x1400412e7  lea     edx, [r13+1]; StringSDRevision
0x1400412eb  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1400412f2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400412f9  nop     dword ptr [rax+rax+00h]
0x1400412fe  test    eax, eax
0x140041300  jnz     short loc_140041341
0x140041302  call    cs:__imp_GetLastError
0x140041309  nop     dword ptr [rax+rax+00h]
0x14004130e  mov     ebx, eax
0x140041310  test    eax, eax
0x140041312  jle     short loc_14004131D
0x140041314  movzx   ebx, ax
0x140041317  or      ebx, 80070000h
0x14004131d  mov     eax, 80004005h
0x140041322  test    ebx, ebx
0x140041324  cmovns  ebx, eax
0x140041327  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x14004132e  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x140041333  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx
0x140041337  mov     edx, 9Fh
0x14004133c  jmp     loc_1400414E0
0x140041341  mov     [rbp+SecurityAttributes.nLength], 18h
0x140041348  mov     [rbp+SecurityAttributes.bInheritHandle], r13d
0x14004134c  mov     rax, [rbp+hMem]
0x140041350  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x140041354  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140041358  mov     rcx, rdi; lpPathName
0x14004135b  call    cs:__imp_CreateDirectoryW
0x140041362  nop     dword ptr [rax+rax+00h]
0x140041367  test    eax, eax
0x140041369  jnz     short loc_1400413D9
0x14004136b  call    cs:__imp_GetLastError
0x140041372  nop     dword ptr [rax+rax+00h]
0x140041377  cmp     eax, 0B7h
0x14004137c  jz      short loc_1400413D9
0x14004137e  call    cs:__imp_GetLastError
0x140041385  nop     dword ptr [rax+rax+00h]
0x14004138a  mov     ebx, eax
0x14004138c  test    eax, eax
0x14004138e  jle     short loc_140041399
0x140041390  movzx   ebx, ax
0x140041393  or      ebx, 80070000h
0x140041399  mov     eax, 80004005h
0x14004139e  test    ebx, ebx
0x1400413a0  cmovns  ebx, eax
0x1400413a3  mov     rcx, [rbp+38h]; this
0x1400413a7  mov     [rsp+80h+hTemplateFile], rdi; char *
0x1400413ac  lea     rax, aUnableToCreate; "Unable to create the folder %ws"
0x1400413b3  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; int
0x1400413b8  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx; wil::details *
0x1400413bc  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x1400413c3  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x1400413ca  mov     edx, 0AFh; void *
0x1400413cf  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400413d4  jmp     loc_1400414F7
0x1400413d9  mov     rcx, rdi; wchar_t *
0x1400413dc  call    ?UtilSetPathToSoftReserve@@YAJPEB_W@Z; UtilSetPathToSoftReserve(wchar_t const *)
0x1400413e1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400413e5  mov     r8, rbx
0x1400413e8  inc     r8
0x1400413eb  cmp     [rdi+r8*2], r13w
0x1400413f0  jnz     short loc_1400413E8
0x1400413f2  mov     rdx, rdi
0x1400413f5  lea     rcx, [rbp+lpFileName]
0x1400413f9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400413fe  mov     rdx, [r15+68h]
0x140041402  test    rdx, rdx
0x140041405  jz      short loc_140041413
0x140041407  inc     rbx
0x14004140a  cmp     [rdx+rbx*2], r13w
0x14004140f  jnz     short loc_140041407
0x140041411  jmp     short loc_140041416
0x140041413  mov     rbx, r13
0x140041416  mov     r8, rbx
0x140041419  lea     rcx, [rbp+lpFileName]
0x14004141d  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140041422  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x140041427  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14004142f  mov     dword ptr [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x140041437  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x14004143b  xor     r8d, r8d; dwShareMode
0x14004143e  mov     edx, 40040000h; dwDesiredAccess
0x140041443  mov     rcx, [rbp+lpFileName]; lpFileName
0x140041447  call    cs:__imp_CreateFileW
0x14004144e  nop     dword ptr [rax+rax+00h]
0x140041453  mov     rsi, rax
0x140041456  inc     rax
0x140041459  cmp     rax, 1
0x14004145d  ja      short loc_140041469
0x14004145f  mov     ebx, 80004005h
0x140041464  jmp     loc_1400414F7
0x140041469  mov     r8, [rbp+var_20]
0x14004146d  mov     rdx, [rbp+lpFileName]
0x140041471  sub     r8, rdx
0x140041474  sar     r8, 1
0x140041477  mov     rcx, r12
0x14004147a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004147f  test    al, al
0x140041481  jnz     short loc_14004149F
0x140041483  mov     ebx, 8007000Eh
0x140041488  lea     rax, aCopyFailed; "Copy failed"
0x14004148f  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x140041494  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx
0x140041498  mov     edx, 0D4h
0x14004149d  jmp     short loc_1400414E0
0x14004149f  mov     [rbp+arg_18], r13
0x1400414a3  mov     rcx, [r14]; hObject
0x1400414a6  mov     [r14], rsi
0x1400414a9  lea     rax, [rcx+1]
0x1400414ad  cmp     rax, 1
0x1400414b1  jbe     short loc_1400414BF
0x1400414b3  call    cs:__imp_CloseHandle
0x1400414ba  nop     dword ptr [rax+rax+00h]
0x1400414bf  mov     ebx, r13d
0x1400414c2  jmp     short loc_14004152A
0x1400414c4  mov     eax, 80004005h
0x1400414c9  mov     ebx, eax
0x1400414cb  lea     rdx, aLiveMinidumpDi; "Live minidump directory not set"
0x1400414d2  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rdx; int
0x1400414d7  mov     dword ptr [rsp+80h+dwCreationDisposition], eax; wil::details *
0x1400414db  mov     edx, 92h; void *
0x1400414e0  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x1400414e7  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x1400414ee  mov     rcx, [rbp+38h]; this
0x1400414f2  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400414f7  mov     [rbp+arg_18], r13
0x1400414fb  lea     rax, [rsi+1]
0x1400414ff  cmp     rax, 1
0x140041503  jbe     short loc_140041514
0x140041505  mov     rcx, rsi; hObject
0x140041508  call    cs:__imp_CloseHandle
0x14004150f  nop     dword ptr [rax+rax+00h]
0x140041514  mov     rcx, [rbp+lpFileName]; lpFileName
0x140041518  cmp     rcx, [rbp+var_20]
0x14004151c  jz      short loc_14004152E
0x14004151e  call    cs:__imp_DeleteFileW
0x140041525  nop     dword ptr [rax+rax+00h]
0x14004152a  mov     rcx, [rbp+lpFileName]
0x14004152e  jmp     short loc_140041566
0x140041530  mov     rcx, [rbp+38h]; this
0x140041534  lea     rax, aInvalidArgs; "Invalid args"
0x14004153b  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; int
0x140041540  mov     ebx, 80070057h
0x140041545  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx; wil::details *
0x140041549  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x140041550  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041557  mov     edx, 87h; void *
0x14004155c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041561  nop
0x140041562  mov     rcx, [rbp+lpFileName]; void *
0x140041566  lea     rax, [rbp+var_18]
0x14004156a  cmp     rcx, rax
0x14004156d  jz      short loc_14004157C
0x14004156f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140041576  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004157b  nop
0x14004157c  mov     rcx, [rbp+hMem]; hMem
0x140041580  test    rcx, rcx
0x140041583  jz      short loc_140041592
0x140041585  call    cs:__imp_LocalFree
0x14004158c  nop     dword ptr [rax+rax+00h]
0x140041591  nop
0x140041592  mov     eax, ebx
0x140041594  mov     rbx, [rsp+80h+arg_0]
0x14004159c  add     rsp, 80h
0x1400415a3  pop     r15
0x1400415a5  pop     r14
0x1400415a7  pop     r13
0x1400415a9  pop     r12
0x1400415ab  pop     rdi
0x1400415ac  pop     rsi
0x1400415ad  pop     rbp
0x1400415ae  retn
```
