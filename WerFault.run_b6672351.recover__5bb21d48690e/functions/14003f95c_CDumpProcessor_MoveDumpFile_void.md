# CDumpProcessor::MoveDumpFile(void)

- ea: `0x14003f95c`
- end: `0x14003fc68`
- name: `?MoveDumpFile@CDumpProcessor@@AEAAJXZ`
- size: `780`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400401fc`

## callees

- `0x140002748`
- `0x14000e9d4`
- `0x14003ecdc`
- `0x14003f93c`
- `0x14003f95c`
- `0x140040830`
- `0x140040868`
- `0x1400408b0`
- `0x140046fdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003f9dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003fa85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003fc1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003f9dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003fa85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003fc1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003f9f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003fa99`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003fc33`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003f9f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003fa99`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003fc33`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003fb96`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003fc0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003fb96`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003fc0d`

## string_xrefs

- `0x14003fab1`: `CDumpProcessor::MoveDumpFile::<lambda_1eade39ae7b65d92b4df486b68c178e2>::operator ()`
- `0x14003fc47`: `CDumpProcessor::MoveDumpFile::<lambda_1eade39ae7b65d92b4df486b68c178e2>::operator ()`
- `0x14003f994`: `CDumpProcessor::MoveDumpFile`
- `0x14003fa04`: `CDumpProcessor::MoveDumpFile`
- `0x14003faef`: `CDumpProcessor::MoveDumpFile`
- `0x14003fbb6`: `CDumpProcessor::MoveDumpFile`
- `0x14003fba6`: `MoveAndSecureFile failed`

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
      (void *)0x2E0,
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
        (void *)0x2F9,
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
        MiniDumpFile = CDumpProcessor::CreateMiniDumpFile(this, lpFileName, 0);
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
            (void *)0x326,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
            "CDumpProcessor::MoveDumpFile",
            v22,
            (int)"MoveAndSecureFile failed",
            (const char *)lpFileName[0]);
        }
        else
        {
          LODWORD(v22) = MiniDumpFile;
          wil::details::in1diag4::Return_Hr(retaddr, (void *)0x31C, v18, v19, v22, v24);
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
               (void *)0x309,
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
        wil::details::in1diag4::Return_Hr(retaddr, (void *)0x30F, v12, v13, v22, v24);
LABEL_14:
        v14 = v5 == 0;
LABEL_15:
        if ( !v14 )
        {
          v15 = GetCurrentThread();
          if ( !SetThreadPriority(v15, 0x20000) )
            wil::details::in1diag4::_Log_GetLastError(
              retaddr,
              (void *)0x2F4,
              v16,
              "CDumpProcessor::MoveDumpFile::<lambda_1eade39ae7b65d92b4df486b68c178e2>::operator ()",
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
          (void *)0x2F4,
          v21,
          "CDumpProcessor::MoveDumpFile::<lambda_1eade39ae7b65d92b4df486b68c178e2>::operator ()",
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
0x14003f95c  push    rbp
0x14003f95e  push    rbx
0x14003f95f  push    rsi
0x14003f960  push    rdi
0x14003f961  push    r14
0x14003f963  push    r15
0x14003f965  mov     rbp, rsp
0x14003f968  sub     rsp, 58h
0x14003f96c  mov     rdi, rcx
0x14003f96f  cmp     dword ptr [rcx+0D0h], 45474150h
0x14003f979  jz      short loc_14003F9B3
0x14003f97b  mov     rcx, [rbp+30h]; this
0x14003f97f  lea     rax, aDumpNotPresent; "Dump not present or invalid"
0x14003f986  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003f98b  mov     ebx, 80004005h
0x14003f990  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003f994  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003f99b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f9a2  mov     edx, 2E0h; void *
0x14003f9a7  call    ?Return_HrMsg@in1diag4@details@wil@@YAXPEAXIPEBD1J1ZZ; wil::details::in1diag4::Return_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003f9ac  mov     eax, ebx
0x14003f9ae  jmp     loc_14003FC5A
0x14003f9b3  xor     r15d, r15d
0x14003f9b6  cmp     [rcx+0ACh], r15d
0x14003f9bd  jnz     short loc_14003F9D2
0x14003f9bf  mov     rax, [rcx+0B0h]
0x14003f9c6  mov     [rcx+2130h], rax
0x14003f9cd  jmp     loc_14003FC58
0x14003f9d2  mov     sil, 1
0x14003f9d5  mov     [rbp+arg_1], sil
0x14003f9d9  mov     r14b, sil
0x14003f9dc  call    cs:__imp_GetCurrentThread
0x14003f9e3  nop     dword ptr [rax+rax+00h]
0x14003f9e8  mov     rcx, rax; hThread
0x14003f9eb  mov     edx, 10000h; nPriority
0x14003f9f0  call    cs:__imp_SetThreadPriority
0x14003f9f7  nop     dword ptr [rax+rax+00h]
0x14003f9fc  test    eax, eax
0x14003f9fe  jnz     short loc_14003FA1F
0x14003fa00  mov     rcx, [rbp+30h]; this
0x14003fa04  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003fa0b  mov     edx, 2F9h; void *
0x14003fa10  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003fa15  mov     sil, r15b
0x14003fa18  mov     [rbp+arg_1], r15b
0x14003fa1c  mov     r14b, r15b
0x14003fa1f  mov     ecx, [rdi+1068h]
0x14003fa25  lea     eax, [rcx-1]
0x14003fa28  test    eax, 0FFFFFFFAh
0x14003fa2d  jnz     loc_14003FB0E
0x14003fa33  cmp     ecx, 2
0x14003fa36  jz      loc_14003FB0E
0x14003fa3c  mov     rdx, [rdi+78h]; wchar_t *
0x14003fa40  test    rdx, rdx
0x14003fa43  jz      loc_14003FAD7
0x14003fa49  cmp     [rdx], r15w
0x14003fa4d  jz      loc_14003FAD7
0x14003fa53  mov     r8d, [rdi+54h]; int
0x14003fa57  mov     rcx, [rdi+0B0h]; wchar_t *
0x14003fa5e  call    ?MoveAndSecureFile@@YAJPEB_W0HH@Z; MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)
0x14003fa63  mov     ebx, eax
0x14003fa65  test    eax, eax
0x14003fa67  jns     short loc_14003FAC7
0x14003fa69  mov     rcx, [rbp+30h]; this
0x14003fa6d  mov     dword ptr [rsp+58h+var_38], eax; char *
0x14003fa71  mov     edx, 30Fh; void *
0x14003fa76  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14003fa7b  nop
0x14003fa7c  test    r14b, r14b
0x14003fa7f  jz      loc_14003F9AC
0x14003fa85  call    cs:__imp_GetCurrentThread
0x14003fa8c  nop     dword ptr [rax+rax+00h]
0x14003fa91  mov     rcx, rax; hThread
0x14003fa94  mov     edx, 20000h; nPriority
0x14003fa99  call    cs:__imp_SetThreadPriority
0x14003faa0  nop     dword ptr [rax+rax+00h]
0x14003faa5  test    eax, eax
0x14003faa7  jnz     loc_14003F9AC
0x14003faad  mov     rcx, [rbp+30h]; this
0x14003fab1  lea     r9, aCdumpprocessor_1; "CDumpProcessor::MoveDumpFile::<lambda_1"...
0x14003fab8  mov     edx, 2F4h; void *
0x14003fabd  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003fac2  jmp     loc_14003F9AC
0x14003fac7  mov     rax, [rdi+78h]
0x14003facb  mov     [rdi+2130h], rax
0x14003fad2  jmp     loc_14003FC06
0x14003fad7  mov     rcx, [rbp+30h]; this
0x14003fadb  lea     rax, aNoDumpFilePres; "No dump file present in crash control"
0x14003fae2  mov     qword ptr [rsp+58h+var_30], rax; unsigned int
0x14003fae7  mov     dword ptr [rsp+58h+var_38], 2; wil::details *
0x14003faef  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003faf6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003fafd  mov     edx, 309h; void *
0x14003fb02  call    ?Return_Win32Msg@in1diag4@details@wil@@YAJPEAXIPEBD1K1ZZ; wil::details::in1diag4::Return_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003fb07  mov     ebx, eax
0x14003fb09  jmp     loc_14003FA7C
0x14003fb0e  cmp     ecx, 4
0x14003fb11  jnz     loc_14003FC06
0x14003fb17  lea     rax, [rbp+var_18]
0x14003fb1b  mov     [rbp+lpFileName], rax
0x14003fb1f  lea     rax, [rbp+var_18]
0x14003fb23  mov     [rbp+var_20], rax
0x14003fb27  mov     [rbp+var_18], r15w
0x14003fb2c  xor     r8d, r8d
0x14003fb2f  lea     rdx, [rbp+lpFileName]
0x14003fb33  mov     rcx, rdi
0x14003fb36  call    ?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x14003fb3b  mov     ebx, eax
0x14003fb3d  test    eax, eax
0x14003fb3f  jns     short loc_14003FB76
0x14003fb41  mov     rcx, [rbp+30h]; this
0x14003fb45  mov     dword ptr [rsp+58h+var_38], eax; wil::details *
0x14003fb49  mov     edx, 31Ch; void *
0x14003fb4e  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14003fb53  nop
0x14003fb54  lea     rax, [rbp+var_18]
0x14003fb58  mov     rcx, [rbp+lpFileName]; void *
0x14003fb5c  cmp     rcx, rax
0x14003fb5f  jz      short loc_14003FB6E
0x14003fb61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003fb68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003fb6d  nop
0x14003fb6e  test    sil, sil
0x14003fb71  jmp     loc_14003FA7F
0x14003fb76  mov     r8d, 1; int
0x14003fb7c  mov     rdx, [rbp+lpFileName]; wchar_t *
0x14003fb80  mov     rcx, [rdi+0B0h]; wchar_t *
0x14003fb87  call    ?MoveAndSecureFile@@YAJPEB_W0HH@Z; MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)
0x14003fb8c  mov     ebx, eax
0x14003fb8e  test    eax, eax
0x14003fb90  jns     short loc_14003FBD0
0x14003fb92  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003fb96  call    cs:__imp_DeleteFileW
0x14003fb9d  nop     dword ptr [rax+rax+00h]
0x14003fba2  mov     rcx, [rbp+30h]; this
0x14003fba6  lea     rax, aMoveandsecuref; "MoveAndSecureFile failed"
0x14003fbad  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003fbb2  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003fbb6  lea     r9, aCdumpprocessor_5; "CDumpProcessor::MoveDumpFile"
0x14003fbbd  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003fbc4  mov     edx, 326h; void *
0x14003fbc9  call    ?Return_HrMsg@in1diag4@details@wil@@YAXPEAXIPEBD1J1ZZ; wil::details::in1diag4::Return_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003fbce  jmp     short loc_14003FB54
0x14003fbd0  lea     rbx, [rdi+2110h]
0x14003fbd7  lea     rdx, [rbp+lpFileName]
0x14003fbdb  mov     rcx, rbx
0x14003fbde  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14003fbe3  mov     rax, [rbx]
0x14003fbe6  mov     [rdi+2130h], rax
0x14003fbed  lea     rax, [rbp+var_18]
0x14003fbf1  mov     rcx, [rbp+lpFileName]; void *
0x14003fbf5  cmp     rcx, rax
0x14003fbf8  jz      short loc_14003FC06
0x14003fbfa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003fc01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003fc06  mov     rcx, [rdi+0B0h]; lpFileName
0x14003fc0d  call    cs:__imp_DeleteFileW
0x14003fc14  nop     dword ptr [rax+rax+00h]
0x14003fc19  nop
0x14003fc1a  test    sil, sil
0x14003fc1d  jz      short loc_14003FC58
0x14003fc1f  call    cs:__imp_GetCurrentThread
0x14003fc26  nop     dword ptr [rax+rax+00h]
0x14003fc2b  mov     rcx, rax; hThread
0x14003fc2e  mov     edx, 20000h; nPriority
0x14003fc33  call    cs:__imp_SetThreadPriority
0x14003fc3a  nop     dword ptr [rax+rax+00h]
0x14003fc3f  test    eax, eax
0x14003fc41  jnz     short loc_14003FC58
0x14003fc43  mov     rcx, [rbp+30h]; this
0x14003fc47  lea     r9, aCdumpprocessor_1; "CDumpProcessor::MoveDumpFile::<lambda_1"...
0x14003fc4e  mov     edx, 2F4h; void *
0x14003fc53  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003fc58  xor     eax, eax
0x14003fc5a  add     rsp, 58h
0x14003fc5e  pop     r15
0x14003fc60  pop     r14
0x14003fc62  pop     rdi
0x14003fc63  pop     rsi
0x14003fc64  pop     rbx
0x14003fc65  pop     rbp
0x14003fc66  retn
```
