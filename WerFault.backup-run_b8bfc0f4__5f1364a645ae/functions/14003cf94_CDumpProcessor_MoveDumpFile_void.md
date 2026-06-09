# CDumpProcessor::MoveDumpFile(void)

- ea: `0x14003cf94`
- end: `0x14003d267`
- name: `?MoveDumpFile@CDumpProcessor@@AEAAJXZ`
- size: `723`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14003d7d4`

## callees

- `0x140002728`
- `0x14000e6dc`
- `0x14003c398`
- `0x14003cf74`
- `0x14003cf94`
- `0x14003de04`
- `0x14003de3c`
- `0x14003de80`
- `0x140044018`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d0a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d22b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d0a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d22b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d022`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d0b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d239`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d022`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d0b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003d239`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003d1ae`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003d21f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003d1ae`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003d21f`

## string_xrefs

- `0x14003d0c9`: `CDumpProcessor::MoveDumpFile::<lambda_9256f2b50b9a4ceb647f41f7a1830f9b>::operator ()`
- `0x14003d247`: `CDumpProcessor::MoveDumpFile::<lambda_9256f2b50b9a4ceb647f41f7a1830f9b>::operator ()`
- `0x14003cfcc`: `CDumpProcessor::MoveDumpFile`
- `0x14003d030`: `CDumpProcessor::MoveDumpFile`
- `0x14003d107`: `CDumpProcessor::MoveDumpFile`
- `0x14003d1c8`: `CDumpProcessor::MoveDumpFile`
- `0x14003d1b8`: `MoveAndSecureFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDumpProcessor::MoveDumpFile(CDumpProcessor *this)
{
  int v2; // ebx
  char v4; // si
  char v5; // r14
  HANDLE CurrentThread; // rax
  unsigned int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  const wchar_t *v10; // rdx
  int v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  bool v14; // zf
  HANDLE v15; // rax
  unsigned int v16; // r8d
  int MiniDumpFile; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  unsigned int v21; // r8d
  wil::details *v22; // [rsp+20h] [rbp-38h]
  wil::details *v23; // [rsp+20h] [rbp-38h]
  int v24; // [rsp+28h] [rbp-30h]
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-28h] BYREF
  _WORD v26[12]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+88h] [rbp+30h]

  if ( *((_DWORD *)this + 52) != 1162297680 )
  {
    v2 = -2147467259;
    LODWORD(v22) = -2147467259;
    wil::details::in1diag4::Return_HrMsg(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::MoveDumpFile",
      v22,
      (int)"Dump not present or invalid",
      (const char *)lpFileName[0]);
    return (unsigned int)v2;
  }
  if ( *((_DWORD *)this + 43) )
  {
    v4 = 1;
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 0x10000) )
    {
      wil::details::in1diag4::_Log_GetLastError(
        retaddr,
        (void *)0x2FD,
        v7,
        "CDumpProcessor::MoveDumpFile",
        (const char *)v22);
      v4 = 0;
      v5 = 0;
    }
    v9 = *((_DWORD *)this + 1050);
    if ( ((v9 - 1) & 0xFFFFFFFA) != 0 || v9 == 2 )
    {
      if ( v9 == 4 )
      {
        lpFileName[0] = v26;
        lpFileName[1] = v26;
        v26[0] = 0;
        MiniDumpFile = CDumpProcessor::CreateMiniDumpFile((__int64)this, (__int64)lpFileName, 0);
        v2 = MiniDumpFile;
        if ( MiniDumpFile >= 0 )
        {
          v2 = MoveAndSecureFile(*((const wchar_t **)this + 22), lpFileName[0], 1, (int)v19);
          if ( v2 >= 0 )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(
              (char *)this + 8464,
              lpFileName);
            *((_QWORD *)this + 1062) = *((_QWORD *)this + 1058);
            if ( lpFileName[0] != v26 )
              operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
            goto LABEL_30;
          }
          DeleteFileW(lpFileName[0]);
          LODWORD(v22) = v2;
          wil::details::in1diag4::Return_HrMsg(
            retaddr,
            (void *)0x32A,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
            "CDumpProcessor::MoveDumpFile",
            v22,
            (int)"MoveAndSecureFile failed",
            (const char *)lpFileName[0]);
        }
        else
        {
          LODWORD(v22) = MiniDumpFile;
          wil::details::in1diag4::Return_Hr(retaddr, (void *)0x320, v18, v19, v22, v24);
        }
        if ( lpFileName[0] != v26 )
          operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        v14 = v4 == 0;
        goto LABEL_15;
      }
    }
    else
    {
      v10 = (const wchar_t *)*((_QWORD *)this + 15);
      if ( !v10 || !*v10 )
      {
        LODWORD(v22) = 2;
        v2 = wil::details::in1diag4::Return_Win32Msg(
               retaddr,
               (void *)0x30D,
               (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
               "CDumpProcessor::MoveDumpFile",
               v22,
               (unsigned int)"No dump file present in crash control",
               (const char *)lpFileName[0]);
        goto LABEL_14;
      }
      v11 = MoveAndSecureFile(*((const wchar_t **)this + 22), v10, *((_DWORD *)this + 21), v8);
      v2 = v11;
      if ( v11 < 0 )
      {
        LODWORD(v22) = v11;
        wil::details::in1diag4::Return_Hr(retaddr, (void *)0x313, v12, v13, v22, v24);
LABEL_14:
        v14 = v5 == 0;
LABEL_15:
        if ( !v14 )
        {
          v15 = GetCurrentThread();
          if ( !SetThreadPriority(v15, 0x20000) )
            wil::details::in1diag4::_Log_GetLastError(
              retaddr,
              (void *)0x2F8,
              v16,
              "CDumpProcessor::MoveDumpFile::<lambda_9256f2b50b9a4ceb647f41f7a1830f9b>::operator ()",
              (const char *)v23);
        }
        return (unsigned int)v2;
      }
      *((_QWORD *)this + 1062) = *((_QWORD *)this + 15);
    }
LABEL_30:
    DeleteFileW(*((LPCWSTR *)this + 22));
    if ( v4 )
    {
      v20 = GetCurrentThread();
      if ( !SetThreadPriority(v20, 0x20000) )
        wil::details::in1diag4::_Log_GetLastError(
          retaddr,
          (void *)0x2F8,
          v21,
          "CDumpProcessor::MoveDumpFile::<lambda_9256f2b50b9a4ceb647f41f7a1830f9b>::operator ()",
          (const char *)v22);
    }
    return 0;
  }
  *((_QWORD *)this + 1062) = *((_QWORD *)this + 22);
  return 0;
}

```

## disassembly

```asm
0x14003cf94  push    rbp
0x14003cf96  push    rbx
0x14003cf97  push    rsi
0x14003cf98  push    rdi
0x14003cf99  push    r14
0x14003cf9b  push    r15
0x14003cf9d  mov     rbp, rsp
0x14003cfa0  sub     rsp, 58h
0x14003cfa4  mov     rdi, rcx
0x14003cfa7  cmp     dword ptr [rcx+0D0h], 45474150h
0x14003cfb1  jz      short loc_14003CFEB
0x14003cfb3  mov     rcx, [rbp+30h]; this
0x14003cfb7  lea     rax, aDumpNotPresent; "Dump not present or invalid"
0x14003cfbe  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003cfc3  mov     ebx, 80004005h
0x14003cfc8  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003cfcc  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003cfd3  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003cfda  mov     edx, 2E4h; void *
0x14003cfdf  call    ?Return_HrMsg@in1diag4@details@wil@@YAXPEAXIPEBD1J1ZZ; wil::details::in1diag4::Return_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003cfe4  mov     eax, ebx
0x14003cfe6  jmp     loc_14003D25A
0x14003cfeb  xor     r15d, r15d
0x14003cfee  cmp     [rcx+0ACh], r15d
0x14003cff5  jnz     short loc_14003D00A
0x14003cff7  mov     rax, [rcx+0B0h]
0x14003cffe  mov     [rcx+2130h], rax
0x14003d005  jmp     loc_14003D258
0x14003d00a  mov     sil, 1
0x14003d00d  mov     [rbp+arg_1], sil
0x14003d011  mov     r14b, sil
0x14003d014  call    cs:__imp_GetCurrentThread
0x14003d01a  mov     rcx, rax; hThread
0x14003d01d  mov     edx, 10000h; nPriority
0x14003d022  call    cs:__imp_SetThreadPriority
0x14003d028  test    eax, eax
0x14003d02a  jnz     short loc_14003D04B
0x14003d02c  mov     rcx, [rbp+30h]; this
0x14003d030  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003d037  mov     edx, 2FDh; void *
0x14003d03c  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003d041  mov     sil, r15b
0x14003d044  mov     [rbp+arg_1], r15b
0x14003d048  mov     r14b, r15b
0x14003d04b  mov     ecx, [rdi+1068h]
0x14003d051  lea     eax, [rcx-1]
0x14003d054  test    eax, 0FFFFFFFAh
0x14003d059  jnz     loc_14003D126
0x14003d05f  cmp     ecx, 2
0x14003d062  jz      loc_14003D126
0x14003d068  mov     rdx, [rdi+78h]; wchar_t *
0x14003d06c  test    rdx, rdx
0x14003d06f  jz      short loc_14003D0EF
0x14003d071  cmp     [rdx], r15w
0x14003d075  jz      short loc_14003D0EF
0x14003d077  mov     r8d, [rdi+54h]; int
0x14003d07b  mov     rcx, [rdi+0B0h]; wchar_t *
0x14003d082  call    ?MoveAndSecureFile@@YAJPEB_W0HH@Z; MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)
0x14003d087  mov     ebx, eax
0x14003d089  test    eax, eax
0x14003d08b  jns     short loc_14003D0DF
0x14003d08d  mov     rcx, [rbp+30h]; this
0x14003d091  mov     dword ptr [rsp+58h+var_38], eax; char *
0x14003d095  mov     edx, 313h; void *
0x14003d09a  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14003d09f  nop
0x14003d0a0  test    r14b, r14b
0x14003d0a3  jz      loc_14003CFE4
0x14003d0a9  call    cs:__imp_GetCurrentThread
0x14003d0af  mov     rcx, rax; hThread
0x14003d0b2  mov     edx, 20000h; nPriority
0x14003d0b7  call    cs:__imp_SetThreadPriority
0x14003d0bd  test    eax, eax
0x14003d0bf  jnz     loc_14003CFE4
0x14003d0c5  mov     rcx, [rbp+30h]; this
0x14003d0c9  lea     r9, aCdumpprocessor_1; "CDumpProcessor::MoveDumpFile::<lambda_9"...
0x14003d0d0  mov     edx, 2F8h; void *
0x14003d0d5  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003d0da  jmp     loc_14003CFE4
0x14003d0df  mov     rax, [rdi+78h]
0x14003d0e3  mov     [rdi+2130h], rax
0x14003d0ea  jmp     loc_14003D218
0x14003d0ef  mov     rcx, [rbp+30h]; this
0x14003d0f3  lea     rax, aNoDumpFilePres; "No dump file present in crash control"
0x14003d0fa  mov     qword ptr [rsp+58h+var_30], rax; unsigned int
0x14003d0ff  mov     dword ptr [rsp+58h+var_38], 2; wil::details *
0x14003d107  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003d10e  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d115  mov     edx, 30Dh; void *
0x14003d11a  call    ?Return_Win32Msg@in1diag4@details@wil@@YAJPEAXIPEBD1K1ZZ; wil::details::in1diag4::Return_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003d11f  mov     ebx, eax
0x14003d121  jmp     loc_14003D0A0
0x14003d126  cmp     ecx, 4
0x14003d129  jnz     loc_14003D218
0x14003d12f  lea     rax, [rbp+var_18]
0x14003d133  mov     [rbp+lpFileName], rax
0x14003d137  lea     rax, [rbp+var_18]
0x14003d13b  mov     [rbp+var_20], rax
0x14003d13f  mov     [rbp+var_18], r15w
0x14003d144  xor     r8d, r8d
0x14003d147  lea     rdx, [rbp+lpFileName]
0x14003d14b  mov     rcx, rdi
0x14003d14e  call    ?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x14003d153  mov     ebx, eax
0x14003d155  test    eax, eax
0x14003d157  jns     short loc_14003D18E
0x14003d159  mov     rcx, [rbp+30h]; this
0x14003d15d  mov     dword ptr [rsp+58h+var_38], eax; wil::details *
0x14003d161  mov     edx, 320h; void *
0x14003d166  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14003d16b  nop
0x14003d16c  lea     rax, [rbp+var_18]
0x14003d170  mov     rcx, [rbp+lpFileName]; void *
0x14003d174  cmp     rcx, rax
0x14003d177  jz      short loc_14003D186
0x14003d179  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003d180  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003d185  nop
0x14003d186  test    sil, sil
0x14003d189  jmp     loc_14003D0A3
0x14003d18e  mov     r8d, 1; int
0x14003d194  mov     rdx, [rbp+lpFileName]; wchar_t *
0x14003d198  mov     rcx, [rdi+0B0h]; wchar_t *
0x14003d19f  call    ?MoveAndSecureFile@@YAJPEB_W0HH@Z; MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)
0x14003d1a4  mov     ebx, eax
0x14003d1a6  test    eax, eax
0x14003d1a8  jns     short loc_14003D1E2
0x14003d1aa  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003d1ae  call    cs:__imp_DeleteFileW
0x14003d1b4  mov     rcx, [rbp+30h]; this
0x14003d1b8  lea     rax, aMoveandsecuref; "MoveAndSecureFile failed"
0x14003d1bf  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003d1c4  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003d1c8  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003d1cf  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d1d6  mov     edx, 32Ah; void *
0x14003d1db  call    ?Return_HrMsg@in1diag4@details@wil@@YAXPEAXIPEBD1J1ZZ; wil::details::in1diag4::Return_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d1e0  jmp     short loc_14003D16C
0x14003d1e2  lea     rbx, [rdi+2110h]
0x14003d1e9  lea     rdx, [rbp+lpFileName]
0x14003d1ed  mov     rcx, rbx
0x14003d1f0  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14003d1f5  mov     rax, [rbx]
0x14003d1f8  mov     [rdi+2130h], rax
0x14003d1ff  lea     rax, [rbp+var_18]
0x14003d203  mov     rcx, [rbp+lpFileName]; void *
0x14003d207  cmp     rcx, rax
0x14003d20a  jz      short loc_14003D218
0x14003d20c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003d213  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003d218  mov     rcx, [rdi+0B0h]; lpFileName
0x14003d21f  call    cs:__imp_DeleteFileW
0x14003d225  nop
0x14003d226  test    sil, sil
0x14003d229  jz      short loc_14003D258
0x14003d22b  call    cs:__imp_GetCurrentThread
0x14003d231  mov     rcx, rax; hThread
0x14003d234  mov     edx, 20000h; nPriority
0x14003d239  call    cs:__imp_SetThreadPriority
0x14003d23f  test    eax, eax
0x14003d241  jnz     short loc_14003D258
0x14003d243  mov     rcx, [rbp+30h]; this
0x14003d247  lea     r9, aCdumpprocessor_1; "CDumpProcessor::MoveDumpFile::<lambda_9"...
0x14003d24e  mov     edx, 2F8h; void *
0x14003d253  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003d258  xor     eax, eax
0x14003d25a  add     rsp, 58h
0x14003d25e  pop     r15
0x14003d260  pop     r14
0x14003d262  pop     rdi
0x14003d263  pop     rsi
0x14003d264  pop     rbx
0x14003d265  pop     rbp
0x14003d266  retn
```
