# RegistryOwnershipManager::EnablePrivileges(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180114bd4`
- end: `0x180114f2e`
- name: `?EnablePrivileges@RegistryOwnershipManager@@AEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180115cfc`

## callees

- `0x180005704`
- `0x180008d04`
- `0x18000da68`
- `0x18000da88`
- `0x18002e2b4`
- `0x1800fdcc4`
- `0x1800fdd8c`
- `0x180100928`
- `0x180114b24`
- `0x180114bd4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180114d40`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180114e34`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180114d40`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180114e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180114c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180114c07`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180114c1e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180114c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114f06`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180114cf6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180114cf6`

## string_xrefs

- `0x180114c32`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180114d71`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180114da2`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180114e48`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180114e84`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryOwnershipManager::EnablePrivileges(__int64 a1, _QWORD *a2)
{
  void **v4; // rbx
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v9; // rdi
  PTOKEN_PRIVILEGES v10; // rbx
  struct _TOKEN_PRIVILEGES *v11; // rsi
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  const char *v14; // r9
  HANDLE v15; // rcx
  bool v16; // cc
  DWORD v17; // r9d
  __int64 v18; // rdi
  PTOKEN_PRIVILEGES v19; // rbx
  const char *v20; // r9
  int PreviousState; // [rsp+20h] [rbp-50h]
  int PreviousStatea; // [rsp+20h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-40h] BYREF
  PTOKEN_PRIVILEGES NewState[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h]
  PTOKEN_PRIVILEGES v26[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD BufferLength; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp+48h] BYREF

  hObject = 0;
  v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, v4) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x45,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
                  v6);
LABEL_3:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return LastError;
  }
  v9 = (__int64)(a2[1] - *a2) >> 5;
  *(_OWORD *)NewState = 0;
  v25 = 0;
  if ( 12 * v9 != -4 )
  {
    std::vector<unsigned char>::_Buy_nonzero(NewState, 12 * v9 + 4);
    v10 = NewState[0];
    memset_0(NewState[0], 0, 12 * v9 + 4);
    NewState[1] = (PTOKEN_PRIVILEGES)&v10->Privileges[v9];
    v23 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v23);
  }
  v11 = NewState[0];
  NewState[0]->PrivilegeCount = v9;
  v12 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v13 = *a2 + 32 * v12;
      if ( *(_QWORD *)(v13 + 24) > 7u )
        v13 = *(_QWORD *)v13;
      if ( !LookupPrivilegeValueW(0, (LPCWSTR)v13, &v11->Privileges[v12].Luid) )
        break;
      v11->Privileges[v12++].Attributes = 2;
      if ( v12 >= v9 )
        goto LABEL_13;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x53,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
                  v14);
    goto LABEL_17;
  }
LABEL_13:
  BufferLength = 0;
  if ( AdjustTokenPrivileges(hObject, 0, v11, 0, 0, &BufferLength) )
  {
    if ( GetLastError() == 1300 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
        (const char *)0x80070514LL,
        PreviousState);
      std::vector<unsigned char>::~vector<unsigned char>(NewState);
      v15 = hObject;
      v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_24:
      if ( v16 )
        CloseHandle(v15);
      return 2147943700LL;
    }
  }
  else
  {
    v17 = BufferLength;
    v18 = BufferLength;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    if ( BufferLength )
    {
      std::vector<unsigned char>::_Buy_nonzero(v26, BufferLength);
      v19 = v26[0];
      memset_0(v26[0], 0, (unsigned int)v18);
      v26[1] = (PTOKEN_PRIVILEGES)((char *)v19 + v18);
      v23 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v23);
      v17 = BufferLength;
    }
    if ( !AdjustTokenPrivileges(hObject, 0, v11, v17, v26[0], &BufferLength) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x68,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
                    v20);
      std::vector<unsigned char>::~vector<unsigned char>(v26);
LABEL_17:
      std::vector<unsigned char>::~vector<unsigned char>(NewState);
      goto LABEL_3;
    }
    if ( GetLastError() == 1300 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
        (const char *)0x80070514LL,
        PreviousStatea);
      std::vector<unsigned char>::~vector<unsigned char>(v26);
      std::vector<unsigned char>::~vector<unsigned char>(NewState);
      v15 = hObject;
      v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_24;
    }
    std::vector<unsigned char>::operator=(a1 + 80, v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1 + 104,
      &hObject);
    std::vector<unsigned char>::~vector<unsigned char>(v26);
  }
  std::vector<unsigned char>::~vector<unsigned char>(NewState);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180114bd4  mov     [rsp-28h+arg_0], rbx
0x180114bd9  mov     [rsp-28h+arg_8], rsi
0x180114bde  push    rbp
0x180114bdf  push    rdi
0x180114be0  push    r13
0x180114be2  push    r14
0x180114be4  push    r15
0x180114be6  mov     rbp, rsp
0x180114be9  sub     rsp, 70h
0x180114bed  mov     r14, rdx
0x180114bf0  mov     r13, rcx
0x180114bf3  mov     [rbp+hObject], 0
0x180114bfb  lea     rcx, [rbp+hObject]
0x180114bff  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180114c04  mov     rbx, rax
0x180114c07  call    cs:__imp_GetCurrentProcess
0x180114c0e  nop     dword ptr [rax+rax+00h]
0x180114c13  mov     r8, rbx; TokenHandle
0x180114c16  mov     edx, 28h ; '('; DesiredAccess
0x180114c1b  mov     rcx, rax; ProcessHandle
0x180114c1e  call    cs:__imp_OpenProcessToken
0x180114c25  nop     dword ptr [rax+rax+00h]
0x180114c2a  test    eax, eax
0x180114c2c  jnz     short loc_180114C64
0x180114c2e  mov     rcx, [rbp+28h]; this
0x180114c32  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114c39  lea     edx, [rax+45h]; void *
0x180114c3c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180114c41  mov     ebx, eax
0x180114c43  mov     rcx, [rbp+hObject]; hObject
0x180114c47  lea     rdx, [rcx-1]
0x180114c4b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180114c4f  ja      short loc_180114C5D
0x180114c51  call    cs:__imp_CloseHandle
0x180114c58  nop     dword ptr [rax+rax+00h]
0x180114c5d  mov     eax, ebx
0x180114c5f  jmp     loc_180114F14
0x180114c64  mov     rdi, [r14+8]
0x180114c68  sub     rdi, [r14]
0x180114c6b  sar     rdi, 5
0x180114c6f  lea     rax, [rdi+rdi*2]
0x180114c73  lea     rsi, ds:4[rax*4]
0x180114c7b  xorps   xmm0, xmm0
0x180114c7e  movdqu  xmmword ptr [rbp+NewState], xmm0
0x180114c83  mov     [rbp+var_28], 0
0x180114c8b  test    rsi, rsi
0x180114c8e  jz      short loc_180114CC7
0x180114c90  mov     rdx, rsi
0x180114c93  lea     rcx, [rbp+NewState]
0x180114c97  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180114c9c  mov     rbx, [rbp+NewState]
0x180114ca0  mov     r8, rsi; Size
0x180114ca3  xor     edx, edx; Val
0x180114ca5  mov     rcx, rbx; void *
0x180114ca8  call    memset_0
0x180114cad  lea     rax, [rsi+rbx]
0x180114cb1  mov     [rbp+NewState+8], rax
0x180114cb5  mov     [rbp+var_40], 0
0x180114cbd  lea     rcx, [rbp+var_40]
0x180114cc1  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180114cc6  nop
0x180114cc7  mov     rsi, [rbp+NewState]
0x180114ccb  mov     [rsi], edi
0x180114ccd  xor     ebx, ebx
0x180114ccf  test    rdi, rdi
0x180114cd2  jz      short loc_180114D1B
0x180114cd4  mov     rdx, rbx
0x180114cd7  shl     rdx, 5
0x180114cdb  add     rdx, [r14]
0x180114cde  cmp     qword ptr [rdx+18h], 7
0x180114ce3  jbe     short loc_180114CE8
0x180114ce5  mov     rdx, [rdx]; lpName
0x180114ce8  lea     r15, [rbx+rbx*2]
0x180114cec  lea     r8, [rsi+4]
0x180114cf0  lea     r8, [r8+r15*4]; lpLuid
0x180114cf4  xor     ecx, ecx; lpSystemName
0x180114cf6  call    cs:__imp_LookupPrivilegeValueW
0x180114cfd  nop     dword ptr [rax+rax+00h]
0x180114d02  test    eax, eax
0x180114d04  jz      loc_180114D9E
0x180114d0a  mov     dword ptr [rsi+r15*4+0Ch], 2
0x180114d13  inc     rbx
0x180114d16  cmp     rbx, rdi
0x180114d19  jb      short loc_180114CD4
0x180114d1b  mov     [rbp+BufferLength], 0
0x180114d22  lea     rax, [rbp+BufferLength]
0x180114d26  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180114d2b  mov     [rsp+70h+PreviousState], 0; int
0x180114d34  xor     r9d, r9d; BufferLength
0x180114d37  mov     r8, rsi; NewState
0x180114d3a  xor     edx, edx; DisableAllPrivileges
0x180114d3c  mov     rcx, [rbp+hObject]; TokenHandle
0x180114d40  call    cs:__imp_AdjustTokenPrivileges
0x180114d47  nop     dword ptr [rax+rax+00h]
0x180114d4c  test    eax, eax
0x180114d4e  jz      short loc_180114DC3
0x180114d50  call    cs:__imp_GetLastError
0x180114d57  nop     dword ptr [rax+rax+00h]
0x180114d5c  cmp     eax, 514h
0x180114d61  jnz     loc_180114EEE
0x180114d67  mov     rcx, [rbp+28h]; this
0x180114d6b  mov     r9d, 80070514h; char *
0x180114d71  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114d78  mov     edx, 5Dh ; ']'; void *
0x180114d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114d82  nop
0x180114d83  lea     rcx, [rbp+NewState]
0x180114d87  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114d8c  nop
0x180114d8d  mov     rcx, [rbp+hObject]
0x180114d91  lea     rax, [rcx-1]
0x180114d95  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180114d99  jmp     loc_180114EB5
0x180114d9e  mov     rcx, [rbp+28h]; this
0x180114da2  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114da9  mov     edx, 53h ; 'S'; void *
0x180114dae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180114db3  mov     ebx, eax
0x180114db5  lea     rcx, [rbp+NewState]
0x180114db9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114dbe  jmp     loc_180114C43
0x180114dc3  mov     r9d, [rbp+BufferLength]
0x180114dc7  mov     edi, r9d
0x180114dca  xorps   xmm0, xmm0
0x180114dcd  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180114dd2  mov     [rbp+var_10], 0
0x180114dda  test    r9d, r9d
0x180114ddd  jz      short loc_180114E19
0x180114ddf  mov     edx, r9d
0x180114de2  lea     rcx, [rbp+var_20]
0x180114de6  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180114deb  mov     rbx, [rbp+var_20]
0x180114def  mov     r8d, edi; Size
0x180114df2  xor     edx, edx; Val
0x180114df4  mov     rcx, rbx; void *
0x180114df7  call    memset_0
0x180114dfc  lea     rax, [rdi+rbx]
0x180114e00  mov     [rbp+var_20+8], rax
0x180114e04  mov     [rbp+var_40], 0
0x180114e0c  lea     rcx, [rbp+var_40]
0x180114e10  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180114e15  mov     r9d, [rbp+BufferLength]; BufferLength
0x180114e19  mov     rax, [rbp+var_20]
0x180114e1d  lea     rcx, [rbp+BufferLength]
0x180114e21  mov     [rsp+70h+ReturnLength], rcx; ReturnLength
0x180114e26  mov     [rsp+70h+PreviousState], rax; int
0x180114e2b  mov     r8, rsi; NewState
0x180114e2e  xor     edx, edx; DisableAllPrivileges
0x180114e30  mov     rcx, [rbp+hObject]; TokenHandle
0x180114e34  call    cs:__imp_AdjustTokenPrivileges
0x180114e3b  nop     dword ptr [rax+rax+00h]
0x180114e40  test    eax, eax
0x180114e42  jnz     short loc_180114E67
0x180114e44  mov     rcx, [rbp+28h]; this
0x180114e48  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114e4f  lea     edx, [rax+68h]; void *
0x180114e52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180114e57  mov     ebx, eax
0x180114e59  lea     rcx, [rbp+var_20]
0x180114e5d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114e62  jmp     loc_180114DB5
0x180114e67  call    cs:__imp_GetLastError
0x180114e6e  nop     dword ptr [rax+rax+00h]
0x180114e73  cmp     eax, 514h
0x180114e78  jnz     short loc_180114ECA
0x180114e7a  mov     rcx, [rbp+28h]; this
0x180114e7e  mov     r9d, 80070514h; char *
0x180114e84  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114e8b  mov     edx, 6Ch ; 'l'; void *
0x180114e90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114e95  lea     rcx, [rbp+var_20]
0x180114e99  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114e9e  nop
0x180114e9f  lea     rcx, [rbp+NewState]
0x180114ea3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114ea8  nop
0x180114ea9  mov     rcx, [rbp+hObject]; hObject
0x180114ead  lea     rdx, [rcx-1]
0x180114eb1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180114eb5  ja      short loc_180114EC3
0x180114eb7  call    cs:__imp_CloseHandle
0x180114ebe  nop     dword ptr [rax+rax+00h]
0x180114ec3  mov     eax, 80070514h
0x180114ec8  jmp     short loc_180114F14
0x180114eca  lea     rcx, [r13+50h]
0x180114ece  lea     rdx, [rbp+var_20]
0x180114ed2  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180114ed7  lea     rcx, [r13+68h]
0x180114edb  lea     rdx, [rbp+hObject]
0x180114edf  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180114ee4  lea     rcx, [rbp+var_20]
0x180114ee8  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114eed  nop
0x180114eee  lea     rcx, [rbp+NewState]
0x180114ef2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114ef7  nop
0x180114ef8  mov     rcx, [rbp+hObject]; hObject
0x180114efc  lea     rax, [rcx-1]
0x180114f00  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180114f04  ja      short loc_180114F12
0x180114f06  call    cs:__imp_CloseHandle
0x180114f0d  nop     dword ptr [rax+rax+00h]
0x180114f12  xor     eax, eax
0x180114f14  lea     r11, [rsp+70h+var_s0]
0x180114f19  mov     rbx, [r11+30h]
0x180114f1d  mov     rsi, [r11+38h]
0x180114f21  mov     rsp, r11
0x180114f24  pop     r15
0x180114f26  pop     r14
0x180114f28  pop     r13
0x180114f2a  pop     rdi
0x180114f2b  pop     rbp
0x180114f2c  retn
```
