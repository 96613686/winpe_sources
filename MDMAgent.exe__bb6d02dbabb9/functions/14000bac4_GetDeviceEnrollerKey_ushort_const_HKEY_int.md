# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x14000bac4`
- end: `0x14000bc82`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `446`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x140010cf0`
- `0x1400112b0`

## callees

- `0x1400029c0`
- `0x14000353c`
- `0x140004b94`
- `0x140006bf4`
- `0x140006c1c`
- `0x140007e3c`
- `0x14000b784`
- `0x14000bac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000bc02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000bc02`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14000bb8a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14000bb8a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14000bb60`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14000bb60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x14000bac4  mov     [rsp-8+arg_10], rbx
0x14000bac9  mov     [rsp-8+arg_18], rdi
0x14000bace  push    rbp
0x14000bacf  lea     rbp, [rsp-180h]
0x14000bad7  sub     rsp, 280h
0x14000bade  mov     rax, cs:__security_cookie
0x14000bae5  xor     rax, rsp
0x14000bae8  mov     [rbp+180h+var_10], rax
0x14000baef  mov     rdi, rdx
0x14000baf2  mov     rbx, rcx
0x14000baf5  test    rcx, rcx
0x14000baf8  jnz     short loc_14000BB21
0x14000bafa  mov     edx, 0FF5h; void *
0x14000baff  mov     ebx, 80070057h
0x14000bb04  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000bb0b  mov     r9d, ebx; char *
0x14000bb0e  mov     rcx, [rbp+188h]; this
0x14000bb15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb1a  mov     eax, ebx
0x14000bb1c  jmp     loc_14000BC5D
0x14000bb21  test    rdi, rdi
0x14000bb24  jnz     short loc_14000BB2D
0x14000bb26  mov     edx, 0FF6h
0x14000bb2b  jmp     short loc_14000BAFF
0x14000bb2d  mov     qword ptr [rdx], 0
0x14000bb34  xor     edx, edx; Val
0x14000bb36  mov     r8d, 208h; Size
0x14000bb3c  lea     rcx, [rsp+280h+pszPathOut]; void *
0x14000bb41  call    memset_0
0x14000bb46  mov     ecx, 2
0x14000bb4b  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x14000bb50  mov     r8, rax; pszPathIn
0x14000bb53  mov     r9, rbx; pszMore
0x14000bb56  mov     edx, 104h; cchPathOut
0x14000bb5b  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x14000bb60  call    cs:__imp_PathCchCombine
0x14000bb67  nop     dword ptr [rax+rax+00h]
0x14000bb6c  mov     ebx, eax
0x14000bb6e  test    eax, eax
0x14000bb70  jns     short loc_14000BB79
0x14000bb72  mov     edx, 0FFBh
0x14000bb77  jmp     short loc_14000BB04
0x14000bb79  lea     r8, pszMore; "DeviceEnroller"
0x14000bb80  mov     edx, 104h; cchPath
0x14000bb85  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x14000bb8a  call    cs:__imp_PathCchAppend
0x14000bb91  nop     dword ptr [rax+rax+00h]
0x14000bb96  mov     ebx, eax
0x14000bb98  test    eax, eax
0x14000bb9a  jns     short loc_14000BBA6
0x14000bb9c  mov     edx, 0FFCh
0x14000bba1  jmp     loc_14000BB04
0x14000bba6  mov     [rsp+280h+var_230], 0
0x14000bbaf  mov     [rsp+280h+dwDisposition], 0
0x14000bbb7  xor     edx, edx
0x14000bbb9  lea     rcx, [rsp+280h+var_230]
0x14000bbbe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14000bbc3  lea     rax, [rsp+280h+dwDisposition]
0x14000bbc8  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x14000bbcd  lea     rax, [rsp+280h+var_230]
0x14000bbd2  mov     [rsp+280h+phkResult], rax; phkResult
0x14000bbd7  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000bbe0  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x14000bbe8  mov     [rsp+280h+dwOptions], 0; unsigned int
0x14000bbf0  xor     r9d, r9d; lpClass
0x14000bbf3  xor     r8d, r8d; Reserved
0x14000bbf6  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x14000bbfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000bc02  call    cs:__imp_RegCreateKeyExW
0x14000bc09  nop     dword ptr [rax+rax+00h]
0x14000bc0e  test    eax, eax
0x14000bc10  jz      short loc_14000BC3F
0x14000bc12  mov     rcx, [rbp+188h]; this
0x14000bc19  mov     r9d, eax; char *
0x14000bc1c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000bc23  mov     edx, 1002h; void *
0x14000bc28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000bc2d  mov     ebx, eax
0x14000bc2f  lea     rcx, [rsp+280h+var_230]
0x14000bc34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000bc39  nop
0x14000bc3a  jmp     loc_14000BB1A
0x14000bc3f  mov     rax, [rsp+280h+var_230]
0x14000bc44  mov     [rsp+280h+var_230], 0
0x14000bc4d  mov     [rdi], rax
0x14000bc50  lea     rcx, [rsp+280h+var_230]
0x14000bc55  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000bc5a  nop
0x14000bc5b  xor     eax, eax
0x14000bc5d  mov     rcx, [rbp+180h+var_10]
0x14000bc64  xor     rcx, rsp; StackCookie
0x14000bc67  call    __security_check_cookie
0x14000bc6c  lea     r11, [rsp+280h+var_s0]
0x14000bc74  mov     rbx, [r11+20h]
0x14000bc78  mov     rdi, [r11+28h]
0x14000bc7c  mov     rsp, r11
0x14000bc7f  pop     rbp
0x14000bc80  retn
```
