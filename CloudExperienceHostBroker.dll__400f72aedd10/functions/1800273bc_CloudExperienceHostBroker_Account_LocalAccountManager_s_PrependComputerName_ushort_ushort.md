# CloudExperienceHostBroker::Account::LocalAccountManager::s_PrependComputerName(ushort *,ushort * *)

- ea: `0x1800273bc`
- end: `0x180027509`
- name: `?s_PrependComputerName@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAGPEAPEAG@Z`
- size: `333`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002722c`

## callees

- `0x180008344`
- `0x18000a9ac`
- `0x18000e6f4`
- `0x180012408`
- `0x180022628`
- `0x1800273bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800273ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180027458`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800273ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180027458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002742e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002742e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027486`

## string_xrefs

- `0x180027415`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800274b6`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::s_PrependComputerName(
        unsigned __int16 *a1,
        unsigned __int16 **a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  size_t v8; // rdi
  unsigned __int16 *v9; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD nSize; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR lpBuffer; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *v14; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  lpBuffer = 0;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, 0, &nSize) )
  {
    v5 = 475;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                  v4);
    goto LABEL_13;
  }
  if ( GetLastError() != 234 )
  {
    v5 = 476;
    goto LABEL_5;
  }
  v14 = (wchar_t *)CoTaskMemAlloc(2LL * nSize);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &lpBuffer,
    &v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, lpBuffer, &nSize) )
  {
    v5 = 478;
    goto LABEL_5;
  }
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + nSize + 1 + 1LL;
  v14 = (wchar_t *)CoTaskMemAlloc(2 * v8);
  v9 = v14;
  if ( swprintf_s(v14, v8, L"%s\\%s", lpBuffer) >= 0 )
  {
    v14 = 0;
    *a2 = v9;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    LastError = 0;
  }
  else
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)0x80004005LL,
      (int)a1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x1800273bc  mov     [rsp-28h+arg_0], rbx
0x1800273c1  push    rbp
0x1800273c2  push    rsi
0x1800273c3  push    rdi
0x1800273c4  push    r14
0x1800273c6  push    r15
0x1800273c8  mov     rbp, rsp
0x1800273cb  sub     rsp, 30h
0x1800273cf  xor     r15d, r15d
0x1800273d2  lea     r8, [rbp+nSize]; nSize
0x1800273d6  mov     [rdx], r15
0x1800273d9  mov     rsi, rdx
0x1800273dc  xor     edx, edx; lpBuffer
0x1800273de  mov     [rbp+lpBuffer], r15
0x1800273e2  mov     r14, rcx
0x1800273e5  mov     [rbp+nSize], r15d
0x1800273e9  lea     ebx, [rdx+4]
0x1800273ec  mov     ecx, ebx; NameType
0x1800273ee  call    cs:__imp_GetComputerNameExW
0x1800273f4  test    eax, eax
0x1800273f6  jz      short loc_1800273FF
0x1800273f8  mov     edx, 1DBh
0x1800273fd  jmp     short loc_180027411
0x1800273ff  call    cs:__imp_GetLastError
0x180027405  cmp     eax, 0EAh
0x18002740a  jz      short loc_180027428
0x18002740c  mov     edx, 1DCh; void *
0x180027411  mov     rcx, [rbp+28h]; this
0x180027415  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002741c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027421  mov     ebx, eax
0x180027423  jmp     loc_1800274ED
0x180027428  mov     ecx, [rbp+nSize]
0x18002742b  add     rcx, rcx; cb
0x18002742e  call    cs:__imp_CoTaskMemAlloc
0x180027434  lea     rdx, [rbp+arg_18]
0x180027438  mov     [rbp+arg_18], rax
0x18002743c  lea     rcx, [rbp+lpBuffer]
0x180027440  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180027445  lea     rcx, [rbp+arg_18]
0x180027449  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002744e  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180027452  lea     r8, [rbp+nSize]; nSize
0x180027456  mov     ecx, ebx; NameType
0x180027458  call    cs:__imp_GetComputerNameExW
0x18002745e  test    eax, eax
0x180027460  jnz     short loc_180027469
0x180027462  mov     edx, 1DEh
0x180027467  jmp     short loc_180027411
0x180027469  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002746d  inc     rdx
0x180027470  cmp     [r14+rdx*2], r15w
0x180027475  jnz     short loc_18002746D
0x180027477  mov     edi, [rbp+nSize]
0x18002747a  inc     edi
0x18002747c  inc     rdi
0x18002747f  add     rdi, rdx
0x180027482  lea     rcx, [rdi+rdi]; cb
0x180027486  call    cs:__imp_CoTaskMemAlloc
0x18002748c  mov     r9, [rbp+lpBuffer]
0x180027490  lea     r8, aSS; "%s\\%s"
0x180027497  mov     rcx, rax; Buffer
0x18002749a  mov     [rbp+arg_18], rax
0x18002749e  mov     rdx, rdi; BufferCount
0x1800274a1  mov     qword ptr [rsp+30h+var_10], r14; int
0x1800274a6  mov     rbx, rax
0x1800274a9  call    swprintf_s
0x1800274ae  test    eax, eax
0x1800274b0  jns     short loc_1800274DA
0x1800274b2  mov     rcx, [rbp+28h]; this
0x1800274b6  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800274bd  mov     ebx, 80004005h
0x1800274c2  mov     edx, 1E3h; void *
0x1800274c7  mov     r9d, ebx; char *
0x1800274ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800274cf  lea     rcx, [rbp+arg_18]
0x1800274d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800274d8  jmp     short loc_1800274ED
0x1800274da  lea     rcx, [rbp+arg_18]
0x1800274de  mov     [rbp+arg_18], r15
0x1800274e2  mov     [rsi], rbx
0x1800274e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800274ea  mov     ebx, r15d
0x1800274ed  lea     rcx, [rbp+lpBuffer]
0x1800274f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800274f6  mov     eax, ebx
0x1800274f8  mov     rbx, [rsp+30h+arg_0]
0x1800274fd  add     rsp, 30h
0x180027501  pop     r15
0x180027503  pop     r14
0x180027505  pop     rdi
0x180027506  pop     rsi
0x180027507  pop     rbp
0x180027508  retn
```
