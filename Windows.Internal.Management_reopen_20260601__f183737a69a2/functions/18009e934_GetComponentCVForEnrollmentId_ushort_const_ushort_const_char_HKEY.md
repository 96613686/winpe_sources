# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18009e934`
- end: `0x18009ea88`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `340`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ea90`
- `0x18009ebe8`

## callees

- `0x180004eb0`
- `0x180008fe4`
- `0x18000ab80`
- `0x180016698`
- `0x180017118`
- `0x1800232b8`
- `0x18009e934`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x18009ea14`
- `DMCmnUtils!UnicodeToMB` at `0x18009ea14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009e9c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009e9c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e98d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e98d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetComponentCVForEnrollmentId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        HKEY a4)
{
  int v7; // ebx
  char *v8; // rcx
  char *v10; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-BCh] BYREF
  char **v14; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, L"OmaDmSession", 0, 0, (LPBYTE)Data, &cbData) )
  {
    v10 = 0;
    v13 = 0;
    v14 = &v10;
    v15 = 0;
    v16 = 1;
    v7 = UnicodeToMB(Data, 0xFDE9u, &v15, &v13);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v14);
    if ( v7 >= 0 )
      StringCchCopyA(a3, 0x81u, v10);
    v8 = v10;
    v10 = 0;
    if ( v8 )
      MemoryFree(v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18009e934  mov     [rsp-8+arg_0], rbx
0x18009e939  push    rbp
0x18009e93a  push    rsi
0x18009e93b  push    rdi
0x18009e93c  lea     rbp, [rsp-80h]
0x18009e941  sub     rsp, 180h
0x18009e948  mov     rax, cs:__security_cookie
0x18009e94f  xor     rax, rsp
0x18009e952  mov     [rbp+90h+var_20], rax
0x18009e956  mov     rdi, r9
0x18009e959  mov     rsi, r8
0x18009e95c  mov     rbx, rdx
0x18009e95f  mov     [rsp+190h+hKey], 0
0x18009e968  xor     edx, edx
0x18009e96a  lea     rcx, [rsp+190h+hKey]
0x18009e96f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009e974  lea     rax, [rsp+190h+hKey]
0x18009e979  mov     [rsp+190h+phkResult], rax; phkResult
0x18009e97e  mov     r9d, 20019h; samDesired
0x18009e984  xor     r8d, r8d; ulOptions
0x18009e987  mov     rdx, rbx; lpSubKey
0x18009e98a  mov     rcx, rdi; hKey
0x18009e98d  call    cs:__imp_RegOpenKeyExW
0x18009e994  nop     dword ptr [rax+rax+00h]
0x18009e999  mov     [rsp+190h+cbData], 102h
0x18009e9a1  lea     rax, [rsp+190h+cbData]
0x18009e9a6  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18009e9ab  lea     rax, [rsp+190h+Data]
0x18009e9b0  mov     [rsp+190h+phkResult], rax; lpData
0x18009e9b5  xor     r9d, r9d; lpType
0x18009e9b8  xor     r8d, r8d; lpReserved
0x18009e9bb  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x18009e9c2  mov     rcx, [rsp+190h+hKey]; hKey
0x18009e9c7  call    cs:__imp_RegQueryValueExW
0x18009e9ce  nop     dword ptr [rax+rax+00h]
0x18009e9d3  test    eax, eax
0x18009e9d5  jnz     loc_18009EA5C
0x18009e9db  mov     [rsp+190h+var_160], 0
0x18009e9e4  mov     [rsp+190h+var_14C], eax
0x18009e9e8  lea     rax, [rsp+190h+var_160]
0x18009e9ed  mov     [rsp+190h+var_148], rax
0x18009e9f2  mov     [rsp+190h+var_140], 0
0x18009e9fb  mov     [rsp+190h+var_138], 1
0x18009ea00  lea     r9, [rsp+190h+var_14C]
0x18009ea05  lea     r8, [rsp+190h+var_140]
0x18009ea0a  mov     edx, 0FDE9h
0x18009ea0f  lea     rcx, [rsp+190h+Data]
0x18009ea14  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18009ea1b  nop     dword ptr [rax+rax+00h]
0x18009ea20  mov     ebx, eax
0x18009ea22  lea     rcx, [rsp+190h+var_148]
0x18009ea27  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009ea2c  test    ebx, ebx
0x18009ea2e  js      short loc_18009EA43
0x18009ea30  mov     r8, [rsp+190h+var_160]; char *
0x18009ea35  mov     edx, 81h; unsigned __int64
0x18009ea3a  mov     rcx, rsi; char *
0x18009ea3d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18009ea42  nop
0x18009ea43  mov     rcx, [rsp+190h+var_160]; void *
0x18009ea48  mov     [rsp+190h+var_160], 0
0x18009ea51  test    rcx, rcx
0x18009ea54  jz      short loc_18009EA5C
0x18009ea56  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18009ea5b  nop
0x18009ea5c  lea     rcx, [rsp+190h+hKey]
0x18009ea61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ea66  xor     eax, eax
0x18009ea68  mov     rcx, [rbp+90h+var_20]
0x18009ea6c  xor     rcx, rsp; StackCookie
0x18009ea6f  call    __security_check_cookie
0x18009ea74  mov     rbx, [rsp+190h+arg_0]
0x18009ea7c  add     rsp, 180h
0x18009ea83  pop     rdi
0x18009ea84  pop     rsi
0x18009ea85  pop     rbp
0x18009ea86  retn
```
