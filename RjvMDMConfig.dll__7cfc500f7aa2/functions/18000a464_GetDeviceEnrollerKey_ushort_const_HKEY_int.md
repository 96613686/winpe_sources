# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x18000a464`
- end: `0x18000a607`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `419`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180010340`
- `0x180010804`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180005a38`
- `0x1800075e8`
- `0x18000a464`
- `0x18000c938`
- `0x18000c95c`
- `0x180011828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a5a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a5a0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a528`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a528`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000a4fe`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000a4fe`

## pseudocode

```c
__int64 __fastcall GetDeviceEnrollerKey(PCWSTR pszMore, HKEY *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
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
  v6 = (const WCHAR *)DMGetKnownRegPath(2);
  v5 = PathCchCombine(pszPathOut, 0x104u, v6, pszMore);
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
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  if ( v7 )
  {
    v5 = wil::details::in1diag3::Return_Win32(retaddr, v8, v9, (const char *)v7, dwOptionsa);
  }
  else
  {
    v5 = 0;
    *a2 = phkResult;
    phkResult = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a464  mov     [rsp-8+arg_10], rbx
0x18000a469  mov     [rsp-8+arg_18], rdi
0x18000a46e  push    rbp
0x18000a46f  lea     rbp, [rsp-180h]
0x18000a477  sub     rsp, 280h
0x18000a47e  mov     rax, cs:__security_cookie
0x18000a485  xor     rax, rsp
0x18000a488  mov     [rbp+180h+var_10], rax
0x18000a48f  mov     rdi, rdx
0x18000a492  mov     rbx, rcx
0x18000a495  test    rcx, rcx
0x18000a498  jnz     short loc_18000A4BF
0x18000a49a  mov     edx, 0FF5h; void *
0x18000a49f  mov     ebx, 80070057h
0x18000a4a4  mov     rcx, [rbp+188h]; this
0x18000a4ab  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18000a4b2  mov     r9d, ebx; char *
0x18000a4b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4ba  jmp     loc_18000A5E0
0x18000a4bf  test    rdi, rdi
0x18000a4c2  jnz     short loc_18000A4CB
0x18000a4c4  mov     edx, 0FF6h
0x18000a4c9  jmp     short loc_18000A49F
0x18000a4cb  mov     qword ptr [rdx], 0
0x18000a4d2  lea     rcx, [rsp+280h+pszPathOut]; void *
0x18000a4d7  xor     edx, edx; Val
0x18000a4d9  mov     r8d, 208h; Size
0x18000a4df  call    memset_0
0x18000a4e4  mov     ecx, 2
0x18000a4e9  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18000a4ee  mov     r8, rax; pszPathIn
0x18000a4f1  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x18000a4f6  mov     r9, rbx; pszMore
0x18000a4f9  mov     edx, 104h; cchPathOut
0x18000a4fe  call    cs:__imp_PathCchCombine
0x18000a505  nop     dword ptr [rax+rax+00h]
0x18000a50a  mov     ebx, eax
0x18000a50c  test    eax, eax
0x18000a50e  jns     short loc_18000A517
0x18000a510  mov     edx, 0FFBh
0x18000a515  jmp     short loc_18000A4A4
0x18000a517  lea     r8, pszMore; "DeviceEnroller"
0x18000a51e  mov     edx, 104h; cchPath
0x18000a523  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x18000a528  call    cs:__imp_PathCchAppend
0x18000a52f  nop     dword ptr [rax+rax+00h]
0x18000a534  mov     ebx, eax
0x18000a536  test    eax, eax
0x18000a538  jns     short loc_18000A544
0x18000a53a  mov     edx, 0FFCh
0x18000a53f  jmp     loc_18000A4A4
0x18000a544  xor     edx, edx
0x18000a546  mov     [rsp+280h+var_230], 0
0x18000a54f  lea     rcx, [rsp+280h+var_230]
0x18000a554  mov     [rsp+280h+dwDisposition], 0
0x18000a55c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a561  lea     rax, [rsp+280h+dwDisposition]
0x18000a566  xor     r9d, r9d; lpClass
0x18000a569  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x18000a56e  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x18000a573  lea     rax, [rsp+280h+var_230]
0x18000a578  xor     r8d, r8d; Reserved
0x18000a57b  mov     [rsp+280h+phkResult], rax; phkResult
0x18000a580  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a587  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a590  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x18000a598  mov     [rsp+280h+dwOptions], 0; unsigned int
0x18000a5a0  call    cs:__imp_RegCreateKeyExW
0x18000a5a7  nop     dword ptr [rax+rax+00h]
0x18000a5ac  test    eax, eax
0x18000a5ae  jz      short loc_18000A5C3
0x18000a5b0  mov     rcx, [rbp+188h]; this
0x18000a5b7  mov     r9d, eax; char *
0x18000a5ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a5bf  mov     ebx, eax
0x18000a5c1  jmp     short loc_18000A5D6
0x18000a5c3  mov     rax, [rsp+280h+var_230]
0x18000a5c8  xor     ebx, ebx
0x18000a5ca  mov     [rdi], rax
0x18000a5cd  mov     [rsp+280h+var_230], 0
0x18000a5d6  lea     rcx, [rsp+280h+var_230]
0x18000a5db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a5e0  mov     eax, ebx
0x18000a5e2  mov     rcx, [rbp+180h+var_10]
0x18000a5e9  xor     rcx, rsp; StackCookie
0x18000a5ec  call    __security_check_cookie
0x18000a5f1  lea     r11, [rsp+280h+var_s0]
0x18000a5f9  mov     rbx, [r11+20h]
0x18000a5fd  mov     rdi, [r11+28h]
0x18000a601  mov     rsp, r11
0x18000a604  pop     rbp
0x18000a605  retn
```
