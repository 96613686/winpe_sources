# IsAuthenticated(HWND__ *,SystemSettings::XamlHost::IXamlHostHelper *)

- ea: `0x14003007c`
- end: `0x1400302f4`
- name: `?IsAuthenticated@@YAJPEAUHWND__@@PEAUIXamlHostHelper@XamlHost@SystemSettings@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(HWND, struct SystemSettings::XamlHost::IXamlHostHelper *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140030338`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14001f3d4`
- `0x14002fe4c`
- `0x14002ff00`
- `0x140030000`
- `0x14003007c`
- `0x140030364`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140030102`
- `KERNEL32!GetLastError` at `0x14003010d`
- `KERNEL32!GetLastError` at `0x14003016e`
- `KERNEL32!GetLastError` at `0x140030102`
- `KERNEL32!GetLastError` at `0x14003010d`
- `KERNEL32!GetLastError` at `0x14003016e`
- `ole32!CoTaskMemAlloc` at `0x14003012c`
- `ole32!CoTaskMemAlloc` at `0x14003012c`
- `SspiCli!LsaConnectUntrusted` at `0x1400301a1`
- `SspiCli!LsaConnectUntrusted` at `0x1400301a1`
- `credui!CredPackAuthenticationBufferW` at `0x1400300f8`
- `credui!CredPackAuthenticationBufferW` at `0x140030164`
- `credui!CredPackAuthenticationBufferW` at `0x1400300f8`
- `credui!CredPackAuthenticationBufferW` at `0x140030164`

## string_xrefs

- `0x1400301bb`: `pcshell\shell\systemsettings\adminflows\common\autologonsetup.cpp`
- `0x14003020a`: `pcshell\shell\systemsettings\adminflows\common\autologonsetup.cpp`
- `0x14003028c`: `pcshell\shell\systemsettings\adminflows\common\autologonsetup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall IsAuthenticated(HWND a1, struct SystemSettings::XamlHost::IXamlHostHelper *a2)
{
  signed int result; // eax
  _BYTE *v5; // rax
  _BYTE *v6; // rbx
  signed int LastError; // eax
  __int64 v8; // rcx
  unsigned int v9; // edi
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  int Package; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int pcbPackedCredentials; // [rsp+20h] [rbp-E0h]
  int pcbPackedCredentialsa; // [rsp+20h] [rbp-E0h]
  DWORD v19; // [rsp+40h] [rbp-C0h] BYREF
  void *LsaHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh] BYREF
  void *v23[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPassword[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszUserName[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v19 = 0;
  memset_0(pszPassword, 0, 0x208u);
  memset_0(pszUserName, 0, 0x208u);
  if ( CredPackAuthenticationBufferW(0, pszUserName, pszPassword, 0, &v19) || GetLastError() == 122 )
  {
    v5 = CoTaskMemAlloc(v19);
    v6 = v5;
    if ( !v5 )
      return -2147024882;
    v23[1] = v5;
    if ( CredPackAuthenticationBufferW(0, pszUserName, pszPassword, v5, &v19) )
    {
      LsaHandle = 0;
      v10 = LsaConnectUntrusted(&LsaHandle);
      v9 = v10 | 0x10000000;
      if ( v10 >= 0 )
      {
        v21 = 0;
        Package = GetPackage(LsaHandle, &v21);
        v9 = Package;
        if ( Package >= 0 )
        {
          v23[0] = 0;
          v22 = 0;
          v14 = VerifyCredUiCredential(a1, LsaHandle, v21, v6, v19, v23, &v22, a2);
          v9 = v14;
          if ( v14 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
            wil::cotaskmem_secure_deleter::operator()<void>(v16, v6);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA4,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\autologonsetup.cpp",
            (const char *)(unsigned int)v14,
            pcbPackedCredentialsa);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
          wil::cotaskmem_secure_deleter::operator()<void>(v15, v6);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9E,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\autologonsetup.cpp",
            (const char *)(unsigned int)Package,
            pcbPackedCredentials);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
          wil::cotaskmem_secure_deleter::operator()<void>(v13, v6);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\autologonsetup.cpp",
          (const char *)v9,
          pcbPackedCredentials);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
        wil::cotaskmem_secure_deleter::operator()<void>(v11, v6);
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      wil::cotaskmem_secure_deleter::operator()<void>(v8, v6);
    }
    return v9;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14003007c  mov     [rsp-8+arg_10], rbx
0x140030081  mov     [rsp-8+arg_18], rsi
0x140030086  push    rbp
0x140030087  push    rdi
0x140030088  push    r14
0x14003008a  lea     rbp, [rsp-3A0h]
0x140030092  sub     rsp, 4A0h
0x140030099  mov     rax, cs:__security_cookie
0x1400300a0  xor     rax, rsp
0x1400300a3  mov     [rbp+3B0h+var_20], rax
0x1400300aa  mov     r14, rdx
0x1400300ad  mov     rsi, rcx
0x1400300b0  mov     [rsp+4B0h+var_470], 0
0x1400300b8  mov     ebx, 208h
0x1400300bd  mov     r8d, ebx; Size
0x1400300c0  xor     edx, edx; Val
0x1400300c2  lea     rcx, [rsp+4B0h+pszPassword]; void *
0x1400300c7  call    memset_0
0x1400300cc  mov     r8d, ebx; Size
0x1400300cf  xor     edx, edx; Val
0x1400300d1  lea     rcx, [rbp+3B0h+pszUserName]; void *
0x1400300d8  call    memset_0
0x1400300dd  lea     rax, [rsp+4B0h+var_470]
0x1400300e2  mov     [rsp+4B0h+pcbPackedCredentials], rax; pcbPackedCredentials
0x1400300e7  xor     r9d, r9d; pPackedCredentials
0x1400300ea  lea     r8, [rsp+4B0h+pszPassword]; pszPassword
0x1400300ef  lea     rdx, [rbp+3B0h+pszUserName]; pszUserName
0x1400300f6  xor     ecx, ecx; dwFlags
0x1400300f8  call    cs:__imp_CredPackAuthenticationBufferW
0x1400300fe  test    eax, eax
0x140030100  jnz     short loc_140030128
0x140030102  call    cs:__imp_GetLastError
0x140030108  cmp     eax, 7Ah ; 'z'
0x14003010b  jz      short loc_140030128
0x14003010d  call    cs:__imp_GetLastError
0x140030113  test    eax, eax
0x140030115  jle     loc_1400302CD
0x14003011b  movzx   eax, ax
0x14003011e  or      eax, 80070000h
0x140030123  jmp     loc_1400302CD
0x140030128  mov     ecx, [rsp+4B0h+var_470]; cb
0x14003012c  call    cs:__imp_CoTaskMemAlloc
0x140030132  mov     rbx, rax
0x140030135  test    rax, rax
0x140030138  jnz     short loc_140030144
0x14003013a  mov     eax, 8007000Eh
0x14003013f  jmp     loc_1400302CD
0x140030144  mov     [rsp+4B0h+var_450], rbx
0x140030149  lea     rax, [rsp+4B0h+var_470]
0x14003014e  mov     [rsp+4B0h+pcbPackedCredentials], rax; int
0x140030153  mov     r9, rbx; pPackedCredentials
0x140030156  lea     r8, [rsp+4B0h+pszPassword]; pszPassword
0x14003015b  lea     rdx, [rbp+3B0h+pszUserName]; pszUserName
0x140030162  xor     ecx, ecx; dwFlags
0x140030164  call    cs:__imp_CredPackAuthenticationBufferW
0x14003016a  test    eax, eax
0x14003016c  jnz     short loc_140030193
0x14003016e  call    cs:__imp_GetLastError
0x140030174  mov     edi, eax
0x140030176  test    eax, eax
0x140030178  jle     short loc_140030183
0x14003017a  movzx   edi, ax
0x14003017d  or      edi, 80070000h
0x140030183  mov     rdx, rbx
0x140030186  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x14003018b  nop
0x14003018c  mov     eax, edi
0x14003018e  jmp     loc_1400302CD
0x140030193  mov     [rsp+4B0h+LsaHandle], 0
0x14003019c  lea     rcx, [rsp+4B0h+LsaHandle]; LsaHandle
0x1400301a1  call    cs:__imp_LsaConnectUntrusted
0x1400301a7  mov     edi, eax
0x1400301a9  or      edi, 10000000h
0x1400301af  jge     short loc_1400301E3
0x1400301b1  mov     rcx, [rbp+3B8h]; this
0x1400301b8  mov     r9d, edi; char *
0x1400301bb  lea     r8, aPcshellShellSy_10; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400301c2  mov     edx, 9Ah; void *
0x1400301c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400301cc  nop
0x1400301cd  lea     rcx, [rsp+4B0h+LsaHandle]
0x1400301d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400301d7  nop
0x1400301d8  mov     rdx, rbx
0x1400301db  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x1400301e0  nop
0x1400301e1  jmp     short loc_14003018C
0x1400301e3  mov     [rsp+4B0h+var_460], 0
0x1400301eb  lea     rdx, [rsp+4B0h+var_460]; unsigned int *
0x1400301f0  mov     rcx, [rsp+4B0h+LsaHandle]; void *
0x1400301f5  call    ?GetPackage@@YAJPEAXPEAK@Z; GetPackage(void *,ulong *)
0x1400301fa  mov     edi, eax
0x1400301fc  test    eax, eax
0x1400301fe  jns     short loc_140030235
0x140030200  mov     rcx, [rbp+3B8h]; this
0x140030207  mov     r9d, eax; char *
0x14003020a  lea     r8, aPcshellShellSy_10; "pcshell\\shell\\systemsettings\\adminfl"...
0x140030211  mov     edx, 9Eh; void *
0x140030216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003021b  nop
0x14003021c  lea     rcx, [rsp+4B0h+LsaHandle]
0x140030221  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140030226  nop
0x140030227  mov     rdx, rbx
0x14003022a  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x14003022f  nop
0x140030230  jmp     loc_14003018C
0x140030235  mov     [rsp+4B0h+var_458], 0
0x14003023e  mov     [rsp+4B0h+var_45C], 0
0x140030246  mov     eax, [rsp+4B0h+var_470]
0x14003024a  mov     [rsp+4B0h+var_478], r14; struct SystemSettings::XamlHost::IXamlHostHelper *
0x14003024f  lea     rcx, [rsp+4B0h+var_45C]
0x140030254  mov     [rsp+4B0h+var_480], rcx; unsigned int *
0x140030259  lea     rcx, [rsp+4B0h+var_458]
0x14003025e  mov     [rsp+4B0h+var_488], rcx; void **
0x140030263  mov     dword ptr [rsp+4B0h+pcbPackedCredentials], eax; int
0x140030267  mov     r9, rbx; void *
0x14003026a  mov     r8d, [rsp+4B0h+var_460]; unsigned int
0x14003026f  mov     rdx, [rsp+4B0h+LsaHandle]; void *
0x140030274  mov     rcx, rsi; HWND
0x140030277  call    ?VerifyCredUiCredential@@YAJPEAUHWND__@@PEAXK1KAEAPEAXAEAKPEAUIXamlHostHelper@XamlHost@SystemSettings@@@Z; VerifyCredUiCredential(HWND__ *,void *,ulong,void *,ulong,void * &,ulong &,SystemSettings::XamlHost::IXamlHostHelper *)
0x14003027c  mov     edi, eax
0x14003027e  test    eax, eax
0x140030280  jns     short loc_1400302B7
0x140030282  mov     rcx, [rbp+3B8h]; this
0x140030289  mov     r9d, eax; char *
0x14003028c  lea     r8, aPcshellShellSy_10; "pcshell\\shell\\systemsettings\\adminfl"...
0x140030293  mov     edx, 0A4h; void *
0x140030298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003029d  nop
0x14003029e  lea     rcx, [rsp+4B0h+LsaHandle]
0x1400302a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400302a8  nop
0x1400302a9  mov     rdx, rbx
0x1400302ac  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x1400302b1  nop
0x1400302b2  jmp     loc_14003018C
0x1400302b7  lea     rcx, [rsp+4B0h+LsaHandle]
0x1400302bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400302c1  nop
0x1400302c2  mov     rdx, rbx
0x1400302c5  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x1400302ca  nop
0x1400302cb  xor     eax, eax
0x1400302cd  mov     rcx, [rbp+3B0h+var_20]
0x1400302d4  xor     rcx, rsp; StackCookie
0x1400302d7  call    __security_check_cookie
0x1400302dc  lea     r11, [rsp+4B0h+var_10]
0x1400302e4  mov     rbx, [r11+30h]
0x1400302e8  mov     rsi, [r11+38h]
0x1400302ec  mov     rsp, r11
0x1400302ef  pop     r14
0x1400302f1  pop     rdi
0x1400302f2  pop     rbp
0x1400302f3  retn
```
