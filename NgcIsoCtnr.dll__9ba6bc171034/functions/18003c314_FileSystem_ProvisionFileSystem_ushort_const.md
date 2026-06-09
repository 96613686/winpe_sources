# FileSystem::ProvisionFileSystem(ushort const *)

- ea: `0x18003c314`
- end: `0x18003c5a2`
- name: `?ProvisionFileSystem@FileSystem@@YAJPEBG@Z`
- size: `654`
- prototype: `__int64 __fastcall(FileSystem *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018bf0`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180010360`
- `0x180011c9c`
- `0x180013088`
- `0x1800163e8`
- `0x18001cbe8`
- `0x18003b3fc`
- `0x18003bb68`
- `0x18003bbb8`
- `0x18003bc08`
- `0x18003c0d8`
- `0x18003c23c`
- `0x18003c298`
- `0x18003c314`
- `0x18003d044`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c3b1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c44d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c4e7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c3b1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c44d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c4e7`

## string_xrefs

- `0x18003c38d`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c3c2`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c412`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c45e`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c4ac`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c4f8`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FileSystem::ProvisionFileSystem(FileSystem *this, const unsigned __int16 *a2)
{
  int v2; // edi
  int KeysDirectoryPath; // eax
  unsigned int LastError; // ebx
  const WCHAR *v5; // rax
  const char *v6; // r9
  int TempDirectoryPath; // eax
  const WCHAR *v8; // rax
  const char *v9; // r9
  int GidsDirectoryPath; // eax
  const WCHAR *v11; // rax
  const char *v12; // r9
  int v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v15; // [rsp+28h] [rbp-D8h]
  _BYTE *v16; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+38h] [rbp-C8h]
  _BYTE *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v19; // [rsp+48h] [rbp-B8h]
  _BYTE v20[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  int v22[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v23[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v2 = (int)this;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
  v23[0] = &LogProvider::NgcIsoContainerProvisionFileSystem::`vftable';
  LogProvider::NgcIsoContainerProvisionFileSystem::StartActivity((LogProvider::NgcIsoContainerProvisionFileSystem *)v23);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v22);
  KeysDirectoryPath = FileSystem::GetKeysDirectoryPath(v2);
  LastError = KeysDirectoryPath;
  if ( KeysDirectoryPath >= 0 )
  {
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    if ( CreateDirectoryW(v5, 0) )
    {
      *(_QWORD *)v14 = v22;
      v15 = 256;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v20);
      TempDirectoryPath = FileSystem::GetTempDirectoryPath(v2);
      LastError = TempDirectoryPath;
      if ( TempDirectoryPath >= 0 )
      {
        v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
        if ( CreateDirectoryW(v8, 0) )
        {
          v16 = v20;
          v17 = 256;
          std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v21);
          GidsDirectoryPath = FileSystem::GetGidsDirectoryPath(v2);
          LastError = GidsDirectoryPath;
          if ( GidsDirectoryPath >= 0 )
          {
            v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
            if ( CreateDirectoryW(v11, 0) )
            {
              v18 = v21;
              v19 = 0;
              HIBYTE(v15) = 0;
              HIBYTE(v17) = 0;
              wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23);
              wil::details::ScopeExitFnGuard__lambda_fc669b96f1794fc875f6d7713677a049___::operator()(&v18);
              std::wstring::_Tidy_deallocate(v21);
              wil::details::ScopeExitFnGuard__lambda_2fa69a4b800f0e2e3f1a0afd5d6f2277___::operator()(&v16);
              std::wstring::_Tidy_deallocate(v20);
              wil::details::ScopeExitFnGuard__lambda_5f357a51a8633e69e113839c4fb87687___::operator()(v14);
              LastError = 0;
              goto LABEL_16;
            }
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xEA,
                          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
                          v12);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE6,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
              (const char *)(unsigned int)GidsDirectoryPath,
              v14[0]);
          }
          std::wstring::_Tidy_deallocate(v21);
          wil::details::ScopeExitFnGuard__lambda_2fa69a4b800f0e2e3f1a0afd5d6f2277___::operator()(&v16);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xD8,
                        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
                        v9);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
          (const char *)(unsigned int)TempDirectoryPath,
          v14[0]);
      }
      std::wstring::_Tidy_deallocate(v20);
      wil::details::ScopeExitFnGuard__lambda_5f357a51a8633e69e113839c4fb87687___::operator()(v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC6,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
                    v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
      (const char *)(unsigned int)KeysDirectoryPath,
      v14[0]);
  }
LABEL_16:
  std::wstring::_Tidy_deallocate(v22);
  LogProvider::NgcIsoContainerProvisionFileSystem::~NgcIsoContainerProvisionFileSystem((LogProvider::NgcIsoContainerProvisionFileSystem *)v23);
  return LastError;
}

```

## disassembly

```asm
0x18003c314  mov     [rsp-8+arg_8], rbx
0x18003c319  mov     [rsp-8+arg_10], rdi
0x18003c31e  push    rbp
0x18003c31f  lea     rbp, [rsp-110h]
0x18003c327  sub     rsp, 210h
0x18003c32e  mov     rax, cs:__security_cookie
0x18003c335  xor     rax, rsp
0x18003c338  mov     [rbp+110h+var_10], rax
0x18003c33f  mov     rdi, rcx
0x18003c342  lea     rdx, aNgcisocontaine_18; "NgcIsoContainerProvisionFileSystem"
0x18003c349  lea     rcx, [rbp+110h+var_160]; struct wil::details::IFailureCallback *
0x18003c34d  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003c352  lea     rax, ??_7NgcIsoContainerProvisionFileSystem@LogProvider@@6B@; const LogProvider::NgcIsoContainerProvisionFileSystem::`vftable'
0x18003c359  mov     [rbp+110h+var_160], rax
0x18003c35d  lea     rcx, [rbp+110h+var_160]; this
0x18003c361  call    ?StartActivity@NgcIsoContainerProvisionFileSystem@LogProvider@@QEAAXXZ; LogProvider::NgcIsoContainerProvisionFileSystem::StartActivity(void)
0x18003c366  nop
0x18003c367  lea     rcx, [rbp+110h+var_180]
0x18003c36b  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18003c370  nop
0x18003c371  lea     rdx, [rbp+110h+var_180]
0x18003c375  mov     rcx, rdi; int
0x18003c378  call    FileSystem__GetKeysDirectoryPath
0x18003c37d  mov     ebx, eax
0x18003c37f  test    eax, eax
0x18003c381  jns     short loc_18003C3A3
0x18003c383  mov     rcx, [rbp+118h]; this
0x18003c38a  mov     r9d, eax; char *
0x18003c38d  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c394  mov     edx, 0C2h; void *
0x18003c399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c39e  jmp     loc_18003C569
0x18003c3a3  lea     rcx, [rbp+110h+var_180]
0x18003c3a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c3ac  mov     rcx, rax; lpPathName
0x18003c3af  xor     edx, edx; lpSecurityAttributes
0x18003c3b1  call    cs:__imp_CreateDirectoryW
0x18003c3b7  test    eax, eax
0x18003c3b9  jnz     short loc_18003C3DA
0x18003c3bb  mov     rcx, [rbp+118h]; this
0x18003c3c2  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c3c9  mov     edx, 0C6h; void *
0x18003c3ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c3d3  mov     ebx, eax
0x18003c3d5  jmp     loc_18003C569
0x18003c3da  lea     rax, [rbp+110h+var_180]
0x18003c3de  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18003c3e3  mov     [rsp+210h+var_1E8], 100h
0x18003c3ea  lea     rcx, [rsp+210h+var_1C0]
0x18003c3ef  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18003c3f4  nop
0x18003c3f5  lea     rdx, [rsp+210h+var_1C0]
0x18003c3fa  mov     rcx, rdi; int
0x18003c3fd  call    FileSystem__GetTempDirectoryPath
0x18003c402  mov     ebx, eax
0x18003c404  test    eax, eax
0x18003c406  jns     short loc_18003C43E
0x18003c408  mov     rcx, [rbp+118h]; this
0x18003c40f  mov     r9d, eax; char *
0x18003c412  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c419  mov     edx, 0D4h; void *
0x18003c41e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c423  nop
0x18003c424  lea     rcx, [rsp+210h+var_1C0]
0x18003c429  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c42e  nop
0x18003c42f  lea     rcx, [rsp+210h+var_1F0]
0x18003c434  call    wil__details__ScopeExitFnGuard__lambda_5f357a51a8633e69e113839c4fb87687_____operator__
0x18003c439  jmp     loc_18003C569
0x18003c43e  lea     rcx, [rsp+210h+var_1C0]
0x18003c443  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c448  mov     rcx, rax; lpPathName
0x18003c44b  xor     edx, edx; lpSecurityAttributes
0x18003c44d  call    cs:__imp_CreateDirectoryW
0x18003c453  test    eax, eax
0x18003c455  jnz     short loc_18003C473
0x18003c457  mov     rcx, [rbp+118h]; this
0x18003c45e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c465  mov     edx, 0D8h; void *
0x18003c46a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c46f  mov     ebx, eax
0x18003c471  jmp     short loc_18003C424
0x18003c473  lea     rax, [rsp+210h+var_1C0]
0x18003c478  mov     [rsp+210h+var_1E0], rax
0x18003c47d  mov     [rsp+210h+var_1D8], 100h
0x18003c484  lea     rcx, [rsp+210h+var_1A0]
0x18003c489  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18003c48e  nop
0x18003c48f  lea     rdx, [rsp+210h+var_1A0]
0x18003c494  mov     rcx, rdi; int
0x18003c497  call    ?GetGidsDirectoryPath@FileSystem@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileSystem::GetGidsDirectoryPath(ushort const *,std::wstring *)
0x18003c49c  mov     ebx, eax
0x18003c49e  test    eax, eax
0x18003c4a0  jns     short loc_18003C4D8
0x18003c4a2  mov     rcx, [rbp+118h]; this
0x18003c4a9  mov     r9d, eax; char *
0x18003c4ac  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c4b3  mov     edx, 0E6h; void *
0x18003c4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c4bd  nop
0x18003c4be  lea     rcx, [rsp+210h+var_1A0]
0x18003c4c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c4c8  nop
0x18003c4c9  lea     rcx, [rsp+210h+var_1E0]
0x18003c4ce  call    wil__details__ScopeExitFnGuard__lambda_2fa69a4b800f0e2e3f1a0afd5d6f2277_____operator__
0x18003c4d3  jmp     loc_18003C424
0x18003c4d8  lea     rcx, [rsp+210h+var_1A0]
0x18003c4dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c4e2  mov     rcx, rax; lpPathName
0x18003c4e5  xor     edx, edx; lpSecurityAttributes
0x18003c4e7  call    cs:__imp_CreateDirectoryW
0x18003c4ed  test    eax, eax
0x18003c4ef  jnz     short loc_18003C50D
0x18003c4f1  mov     rcx, [rbp+118h]; this
0x18003c4f8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c4ff  mov     edx, 0EAh; void *
0x18003c504  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c509  mov     ebx, eax
0x18003c50b  jmp     short loc_18003C4BE
0x18003c50d  lea     rax, [rsp+210h+var_1A0]
0x18003c512  mov     [rsp+210h+var_1D0], rax
0x18003c517  mov     [rsp+210h+var_1C8], 0
0x18003c51e  mov     byte ptr [rsp+210h+var_1E8+1], 0
0x18003c523  mov     byte ptr [rsp+210h+var_1D8+1], 0
0x18003c528  lea     rcx, [rbp+110h+var_160]
0x18003c52c  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003c531  lea     rcx, [rsp+210h+var_1D0]
0x18003c536  call    wil__details__ScopeExitFnGuard__lambda_fc669b96f1794fc875f6d7713677a049_____operator__
0x18003c53b  nop
0x18003c53c  lea     rcx, [rsp+210h+var_1A0]
0x18003c541  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c546  nop
0x18003c547  lea     rcx, [rsp+210h+var_1E0]
0x18003c54c  call    wil__details__ScopeExitFnGuard__lambda_2fa69a4b800f0e2e3f1a0afd5d6f2277_____operator__
0x18003c551  nop
0x18003c552  lea     rcx, [rsp+210h+var_1C0]
0x18003c557  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c55c  nop
0x18003c55d  lea     rcx, [rsp+210h+var_1F0]
0x18003c562  call    wil__details__ScopeExitFnGuard__lambda_5f357a51a8633e69e113839c4fb87687_____operator__
0x18003c567  xor     ebx, ebx
0x18003c569  lea     rcx, [rbp+110h+var_180]
0x18003c56d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c572  nop
0x18003c573  lea     rcx, [rbp+110h+var_160]; this
0x18003c577  call    ??1NgcIsoContainerProvisionFileSystem@LogProvider@@QEAA@XZ; LogProvider::NgcIsoContainerProvisionFileSystem::~NgcIsoContainerProvisionFileSystem(void)
0x18003c57c  mov     eax, ebx
0x18003c57e  mov     rcx, [rbp+110h+var_10]
0x18003c585  xor     rcx, rsp; StackCookie
0x18003c588  call    __security_check_cookie
0x18003c58d  lea     r11, [rsp+210h+var_s0]
0x18003c595  mov     rbx, [r11+18h]
0x18003c599  mov     rdi, [r11+20h]
0x18003c59d  mov     rsp, r11
0x18003c5a0  pop     rbp
0x18003c5a1  retn
```
