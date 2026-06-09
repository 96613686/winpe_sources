# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x14000b5a0`
- end: `0x14000b74b`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `427`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400104c0`
- `0x140010a68`

## callees

- `0x140002930`
- `0x14000349c`
- `0x140004b0c`
- `0x140006984`
- `0x1400069a8`
- `0x140007b34`
- `0x14000b288`
- `0x14000b5a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000b6d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000b6d2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14000b660`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14000b660`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14000b63c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14000b63c`

## pseudocode

```c
__int64 __fastcall GetDeviceEnrollerKey(PCWSTR pszMore, HKEY *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  HKEY v9; // rax
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !pszMore )
  {
    v4 = 4085;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      dwOptions);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v4 = 4086;
    goto LABEL_3;
  }
  *a2 = 0;
  memset_0(pszPathOut, 0, 0x208u);
  v7 = (const WCHAR *)DMGetKnownRegPath(2);
  v5 = PathCchCombine(pszPathOut, 0x104u, v7, pszMore);
  if ( v5 < 0 )
  {
    v4 = 4091;
    goto LABEL_4;
  }
  v5 = PathCchAppend(pszPathOut, 0x104u, L"DeviceEnroller");
  if ( v5 < 0 )
  {
    v4 = 4092;
    goto LABEL_4;
  }
  phkResult = 0;
  dwDisposition = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  if ( v8 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1002,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
           (const char *)v8,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return (unsigned int)v5;
  }
  v9 = phkResult;
  phkResult = 0;
  *a2 = v9;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return 0;
}

```

## disassembly

```asm
0x14000b5a0  mov     [rsp-8+arg_10], rbx
0x14000b5a5  mov     [rsp-8+arg_18], rdi
0x14000b5aa  push    rbp
0x14000b5ab  lea     rbp, [rsp-180h]
0x14000b5b3  sub     rsp, 280h
0x14000b5ba  mov     rax, cs:__security_cookie
0x14000b5c1  xor     rax, rsp
0x14000b5c4  mov     [rbp+180h+var_10], rax
0x14000b5cb  mov     rdi, rdx
0x14000b5ce  mov     rbx, rcx
0x14000b5d1  test    rcx, rcx
0x14000b5d4  jnz     short loc_14000B5FD
0x14000b5d6  mov     edx, 0FF5h; void *
0x14000b5db  mov     ebx, 80070057h
0x14000b5e0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000b5e7  mov     r9d, ebx; char *
0x14000b5ea  mov     rcx, [rbp+188h]; this
0x14000b5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b5f6  mov     eax, ebx
0x14000b5f8  jmp     loc_14000B727
0x14000b5fd  test    rdi, rdi
0x14000b600  jnz     short loc_14000B609
0x14000b602  mov     edx, 0FF6h
0x14000b607  jmp     short loc_14000B5DB
0x14000b609  mov     qword ptr [rdx], 0
0x14000b610  xor     edx, edx; Val
0x14000b612  mov     r8d, 208h; Size
0x14000b618  lea     rcx, [rsp+280h+pszPathOut]; void *
0x14000b61d  call    memset_0
0x14000b622  mov     ecx, 2
0x14000b627  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x14000b62c  mov     r8, rax; pszPathIn
0x14000b62f  mov     r9, rbx; pszMore
0x14000b632  mov     edx, 104h; cchPathOut
0x14000b637  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x14000b63c  call    cs:__imp_PathCchCombine
0x14000b642  mov     ebx, eax
0x14000b644  test    eax, eax
0x14000b646  jns     short loc_14000B64F
0x14000b648  mov     edx, 0FFBh
0x14000b64d  jmp     short loc_14000B5E0
0x14000b64f  lea     r8, pszMore; "DeviceEnroller"
0x14000b656  mov     edx, 104h; cchPath
0x14000b65b  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x14000b660  call    cs:__imp_PathCchAppend
0x14000b666  mov     ebx, eax
0x14000b668  test    eax, eax
0x14000b66a  jns     short loc_14000B676
0x14000b66c  mov     edx, 0FFCh
0x14000b671  jmp     loc_14000B5E0
0x14000b676  mov     [rsp+280h+var_230], 0
0x14000b67f  mov     [rsp+280h+dwDisposition], 0
0x14000b687  xor     edx, edx
0x14000b689  lea     rcx, [rsp+280h+var_230]
0x14000b68e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14000b693  lea     rax, [rsp+280h+dwDisposition]
0x14000b698  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x14000b69d  lea     rax, [rsp+280h+var_230]
0x14000b6a2  mov     [rsp+280h+phkResult], rax; phkResult
0x14000b6a7  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000b6b0  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x14000b6b8  mov     [rsp+280h+dwOptions], 0; unsigned int
0x14000b6c0  xor     r9d, r9d; lpClass
0x14000b6c3  xor     r8d, r8d; Reserved
0x14000b6c6  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x14000b6cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b6d2  call    cs:__imp_RegCreateKeyExW
0x14000b6d8  test    eax, eax
0x14000b6da  jz      short loc_14000B709
0x14000b6dc  mov     rcx, [rbp+188h]; this
0x14000b6e3  mov     r9d, eax; char *
0x14000b6e6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000b6ed  mov     edx, 1002h; void *
0x14000b6f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000b6f7  mov     ebx, eax
0x14000b6f9  lea     rcx, [rsp+280h+var_230]
0x14000b6fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b703  nop
0x14000b704  jmp     loc_14000B5F6
0x14000b709  mov     rax, [rsp+280h+var_230]
0x14000b70e  mov     [rsp+280h+var_230], 0
0x14000b717  mov     [rdi], rax
0x14000b71a  lea     rcx, [rsp+280h+var_230]
0x14000b71f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b724  nop
0x14000b725  xor     eax, eax
0x14000b727  mov     rcx, [rbp+180h+var_10]
0x14000b72e  xor     rcx, rsp; StackCookie
0x14000b731  call    __security_check_cookie
0x14000b736  lea     r11, [rsp+280h+var_s0]
0x14000b73e  mov     rbx, [r11+20h]
0x14000b742  mov     rdi, [r11+28h]
0x14000b746  mov     rsp, r11
0x14000b749  pop     rbp
0x14000b74a  retn
```
