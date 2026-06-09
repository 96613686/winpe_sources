# FindAppActivationFailedHandler

- ea: `0x18004c7d0`
- end: `0x18004c96c`
- name: `FindAppActivationFailedHandler`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800803f4`

## callees

- `0x18000b5c0`
- `0x180010514`
- `0x18003ab00`
- `0x1800445ac`
- `0x18004c7d0`
- `0x18005ae90`
- `0x18007ac88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004c8e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004c8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c947`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c947`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c89b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c8d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c89b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c8d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c85b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c85b`

## pseudocode

```c
__int64 __fastcall FindAppActivationFailedHandler(unsigned int a1, GUID *a2)
{
  int v3; // eax
  unsigned int ValueW; // eax
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-31h] BYREF
  WCHAR Value[16]; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = GUID_NULL;
  v3 = StringCchPrintfW(Value, 9u, L"%08x", a1);
  if ( v3 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x271,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\AppActivationErrorHandlers",
             0,
             0x20119u,
             &hkey);
  if ( ValueW )
    goto LABEL_9;
  pcbData = 78;
  ValueW = RegGetValueW(hkey, 0, Value, 2u, 0, sz, &pcbData);
  if ( ValueW == 2 )
  {
    pcbData = 78;
    ValueW = RegGetValueW(hkey, 0, 0, 2u, 0, sz, &pcbData);
  }
  if ( ValueW )
  {
LABEL_9:
    if ( ValueW != 2 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x28C,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
             (const char *)ValueW,
             phkResulta);
      goto LABEL_11;
    }
  }
  else
  {
    v5 = CLSIDFromString(sz, a2);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x286,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
        (const char *)(unsigned int)v5,
        phkResulta);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v6;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x18004c7d0  mov     [rsp-8+arg_10], rbx
0x18004c7d5  push    rbp
0x18004c7d6  lea     rbp, [rsp-57h]
0x18004c7db  sub     rsp, 0D0h
0x18004c7e2  mov     rax, cs:__security_cookie
0x18004c7e9  xor     rax, rsp
0x18004c7ec  mov     [rbp+57h+var_10], rax
0x18004c7f0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c7f7  mov     rbx, rdx
0x18004c7fa  lea     r8, a08x; "%08x"
0x18004c801  mov     r9d, ecx
0x18004c804  lea     rcx, [rbp+57h+Value]; unsigned __int16 *
0x18004c808  movdqu  xmmword ptr [rdx], xmm0
0x18004c80c  mov     edx, 9; unsigned __int64
0x18004c811  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c816  test    eax, eax
0x18004c818  jns     short loc_18004C833
0x18004c81a  mov     rcx, [rbp+5Fh]; this
0x18004c81e  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004c825  mov     r9d, eax; char *
0x18004c828  mov     edx, 271h; void *
0x18004c82d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004c833  lea     rax, [rbp+57h+hkey]
0x18004c837  mov     [rbp+57h+hkey], 0
0x18004c83f  mov     r9d, 20119h; samDesired
0x18004c845  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18004c84a  xor     r8d, r8d; ulOptions
0x18004c84d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004c854  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c85b  call    cs:__imp_RegOpenKeyExW
0x18004c861  test    eax, eax
0x18004c863  jnz     loc_18004C90E
0x18004c869  mov     rcx, [rbp+57h+hkey]; hkey
0x18004c86d  lea     rax, [rbp+57h+var_90]
0x18004c871  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18004c876  lea     r8, [rbp+57h+Value]; lpValue
0x18004c87a  lea     rax, [rbp+57h+sz]
0x18004c87e  mov     [rbp+57h+var_90], 4Eh ; 'N'
0x18004c885  mov     [rsp+0D0h+pvData], rax; pvData
0x18004c88a  mov     r9d, 2; dwFlags
0x18004c890  xor     edx, edx; lpSubKey
0x18004c892  mov     [rsp+0D0h+phkResult], 0; pdwType
0x18004c89b  call    cs:__imp_RegGetValueW
0x18004c8a1  cmp     eax, 2
0x18004c8a4  jnz     short loc_18004C8DD
0x18004c8a6  mov     rcx, [rbp+57h+hkey]; hkey
0x18004c8aa  lea     rax, [rbp+57h+var_90]
0x18004c8ae  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18004c8b3  mov     r9d, 2; dwFlags
0x18004c8b9  lea     rax, [rbp+57h+sz]
0x18004c8bd  mov     [rbp+57h+var_90], 4Eh ; 'N'
0x18004c8c4  mov     [rsp+0D0h+pvData], rax; pvData
0x18004c8c9  xor     r8d, r8d; lpValue
0x18004c8cc  xor     edx, edx; lpSubKey
0x18004c8ce  mov     [rsp+0D0h+phkResult], 0; int
0x18004c8d7  call    cs:__imp_RegGetValueW
0x18004c8dd  test    eax, eax
0x18004c8df  jnz     short loc_18004C90E
0x18004c8e1  mov     rdx, rbx; pclsid
0x18004c8e4  lea     rcx, [rbp+57h+sz]; lpsz
0x18004c8e8  call    cs:__imp_CLSIDFromString
0x18004c8ee  mov     ebx, eax
0x18004c8f0  test    eax, eax
0x18004c8f2  jns     short loc_18004C93E
0x18004c8f4  mov     rcx, [rbp+5Fh]; this
0x18004c8f8  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004c8ff  mov     r9d, eax; char *
0x18004c902  mov     edx, 286h; void *
0x18004c907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c90c  jmp     short loc_18004C931
0x18004c90e  cmp     eax, 2
0x18004c911  jz      short loc_18004C93E
0x18004c913  test    eax, eax
0x18004c915  jz      short loc_18004C93E
0x18004c917  mov     rcx, [rbp+5Fh]; this
0x18004c91b  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004c922  mov     r9d, eax; char *
0x18004c925  mov     edx, 28Ch; void *
0x18004c92a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c92f  mov     ebx, eax
0x18004c931  lea     rcx, [rbp+57h+hkey]
0x18004c935  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004c93a  mov     eax, ebx
0x18004c93c  jmp     short loc_18004C94F
0x18004c93e  mov     rcx, [rbp+57h+hkey]; hKey
0x18004c942  test    rcx, rcx
0x18004c945  jz      short loc_18004C94D
0x18004c947  call    cs:__imp_RegCloseKey
0x18004c94d  xor     eax, eax
0x18004c94f  mov     rcx, [rbp+57h+var_10]
0x18004c953  xor     rcx, rsp; StackCookie
0x18004c956  call    __security_check_cookie
0x18004c95b  mov     rbx, [rsp+0D0h+arg_10]
0x18004c963  add     rsp, 0D0h
0x18004c96a  pop     rbp
0x18004c96b  retn
```
