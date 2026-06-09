# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18009bb08`
- end: `0x18009bc45`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `317`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009bc4c`
- `0x18009bd98`

## callees

- `0x180004d50`
- `0x180008dac`
- `0x18000a83c`
- `0x180015f70`
- `0x1800169b8`
- `0x180024c2c`
- `0x18009bb08`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x18009bbd8`
- `DMCmnUtils!UnicodeToMB` at `0x18009bbd8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bb95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bb95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bb61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bb61`

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
0x18009bb08  mov     [rsp-8+arg_0], rbx
0x18009bb0d  push    rbp
0x18009bb0e  push    rsi
0x18009bb0f  push    rdi
0x18009bb10  lea     rbp, [rsp-80h]
0x18009bb15  sub     rsp, 180h
0x18009bb1c  mov     rax, cs:__security_cookie
0x18009bb23  xor     rax, rsp
0x18009bb26  mov     [rbp+90h+var_20], rax
0x18009bb2a  mov     rdi, r9
0x18009bb2d  mov     rsi, r8
0x18009bb30  mov     rbx, rdx
0x18009bb33  mov     [rsp+190h+hKey], 0
0x18009bb3c  xor     edx, edx
0x18009bb3e  lea     rcx, [rsp+190h+hKey]
0x18009bb43  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009bb48  lea     rax, [rsp+190h+hKey]
0x18009bb4d  mov     [rsp+190h+phkResult], rax; phkResult
0x18009bb52  mov     r9d, 20019h; samDesired
0x18009bb58  xor     r8d, r8d; ulOptions
0x18009bb5b  mov     rdx, rbx; lpSubKey
0x18009bb5e  mov     rcx, rdi; hKey
0x18009bb61  call    cs:__imp_RegOpenKeyExW
0x18009bb67  mov     [rsp+190h+cbData], 102h
0x18009bb6f  lea     rax, [rsp+190h+cbData]
0x18009bb74  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18009bb79  lea     rax, [rsp+190h+Data]
0x18009bb7e  mov     [rsp+190h+phkResult], rax; lpData
0x18009bb83  xor     r9d, r9d; lpType
0x18009bb86  xor     r8d, r8d; lpReserved
0x18009bb89  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x18009bb90  mov     rcx, [rsp+190h+hKey]; hKey
0x18009bb95  call    cs:__imp_RegQueryValueExW
0x18009bb9b  test    eax, eax
0x18009bb9d  jnz     short loc_18009BC1A
0x18009bb9f  mov     [rsp+190h+var_160], 0
0x18009bba8  mov     [rsp+190h+var_14C], eax
0x18009bbac  lea     rax, [rsp+190h+var_160]
0x18009bbb1  mov     [rsp+190h+var_148], rax
0x18009bbb6  mov     [rsp+190h+var_140], 0
0x18009bbbf  mov     [rsp+190h+var_138], 1
0x18009bbc4  lea     r9, [rsp+190h+var_14C]
0x18009bbc9  lea     r8, [rsp+190h+var_140]
0x18009bbce  mov     edx, 0FDE9h
0x18009bbd3  lea     rcx, [rsp+190h+Data]
0x18009bbd8  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18009bbde  mov     ebx, eax
0x18009bbe0  lea     rcx, [rsp+190h+var_148]
0x18009bbe5  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009bbea  test    ebx, ebx
0x18009bbec  js      short loc_18009BC01
0x18009bbee  mov     r8, [rsp+190h+var_160]; char *
0x18009bbf3  mov     edx, 81h; unsigned __int64
0x18009bbf8  mov     rcx, rsi; char *
0x18009bbfb  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18009bc00  nop
0x18009bc01  mov     rcx, [rsp+190h+var_160]; void *
0x18009bc06  mov     [rsp+190h+var_160], 0
0x18009bc0f  test    rcx, rcx
0x18009bc12  jz      short loc_18009BC1A
0x18009bc14  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18009bc19  nop
0x18009bc1a  lea     rcx, [rsp+190h+hKey]
0x18009bc1f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009bc24  xor     eax, eax
0x18009bc26  mov     rcx, [rbp+90h+var_20]
0x18009bc2a  xor     rcx, rsp; StackCookie
0x18009bc2d  call    __security_check_cookie
0x18009bc32  mov     rbx, [rsp+190h+arg_0]
0x18009bc3a  add     rsp, 180h
0x18009bc41  pop     rdi
0x18009bc42  pop     rsi
0x18009bc43  pop     rbp
0x18009bc44  retn
```
