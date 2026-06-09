# UserAwareCallerIdentity::GetCallingProcessPackageFullName(ushort * *)

- ea: `0x180043aac`
- end: `0x180043caa`
- name: `?GetCallingProcessPackageFullName@UserAwareCallerIdentity@@YAJPEAPEAG@Z`
- size: `510`
- prototype: `__int64 __fastcall(UserAwareCallerIdentity *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180043ee4`

## callees

- `0x180004110`
- `0x180006eac`
- `0x18000c0ec`
- `0x180019e0c`
- `0x18001c434`
- `0x180043a5c`
- `0x180043a8c`
- `0x180043aac`
- `0x1800680fc`
- `0x1800696f2`
- `0x180069730`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180043b5d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180043b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043b6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043b6c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180043bde`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180043bde`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180043bc1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180043bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UserAwareCallerIdentity::GetCallingProcessPackageFullName(
        UserAwareCallerIdentity *this,
        unsigned __int16 **a2)
{
  signed int CallingProcessPackageFullName; // ebx
  RPC_STATUS v4; // eax
  DWORD CurrentProcessId; // ebx
  __int64 v6; // rdx
  int PackageFullNameFromToken; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  bool v10; // sf
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-E0h]
  unsigned int Pid; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE token; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  char v20; // [rsp+58h] [rbp-A8h]
  WCHAR packageFullName[128]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *(_QWORD *)this = 0;
  v17 = 0;
  v18 = &v17;
  v19 = 0;
  v20 = 1;
  CallingProcessPackageFullName = CallerIdentity::GetCallingProcessPackageFullName((CallerIdentity *)&v19, a2);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
  if ( CallingProcessPackageFullName != -2147024891 )
  {
    if ( CallingProcessPackageFullName < 0 )
      goto LABEL_22;
    goto LABEL_21;
  }
  if ( (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
  {
    token = 0;
    memset_0(packageFullName, 0, sizeof(packageFullName));
    packageFullNameLength = 128;
    Pid = 0;
    v4 = I_RpcBindingInqLocalClientPID(0, &Pid);
    CallingProcessPackageFullName = v4;
    if ( v4 == 1725 )
    {
      CurrentProcessId = GetCurrentProcessId();
    }
    else
    {
      if ( v4 >= 1 )
        CallingProcessPackageFullName = (unsigned __int16)v4 | 0x80010000;
      if ( CallingProcessPackageFullName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
          (const char *)(unsigned int)CallingProcessPackageFullName,
          v13);
        v6 = 105;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
          (const char *)(unsigned int)CallingProcessPackageFullName,
          v13);
        goto LABEL_18;
      }
      CurrentProcessId = Pid;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &token,
      0);
    PackageFullNameFromToken = UMgrOpenProcessTokenForQuery(CurrentProcessId, &token);
    if ( PackageFullNameFromToken < 0 )
      goto LABEL_11;
    PackageFullNameFromToken = GetPackageFullNameFromToken(token, &packageFullNameLength, packageFullName);
    v10 = PackageFullNameFromToken < 0;
    if ( PackageFullNameFromToken > 0 )
    {
      PackageFullNameFromToken = (unsigned __int16)PackageFullNameFromToken | 0x80070000;
      v10 = PackageFullNameFromToken < 0;
    }
    if ( v10 )
    {
LABEL_11:
      CallingProcessPackageFullName = PackageFullNameFromToken;
LABEL_18:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
      goto LABEL_22;
    }
    v18 = &v17;
    v19 = 0;
    v20 = 1;
    CallingProcessPackageFullName = _AllocStringWorker<CTCoAllocPolicy>(v9, v8, packageFullName);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
    if ( CallingProcessPackageFullName < 0 )
    {
      v6 = 108;
      goto LABEL_17;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
LABEL_21:
    v11 = v17;
    v17 = 0;
    *(_QWORD *)this = v11;
    CallingProcessPackageFullName = 0;
  }
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  return (unsigned int)CallingProcessPackageFullName;
}

```

## disassembly

```asm
0x180043aac  mov     [rsp-8+arg_8], rbx
0x180043ab1  mov     [rsp-8+arg_10], rdi
0x180043ab6  push    rbp
0x180043ab7  lea     rbp, [rsp-70h]
0x180043abc  sub     rsp, 170h
0x180043ac3  mov     rax, cs:__security_cookie
0x180043aca  xor     rax, rsp
0x180043acd  mov     [rbp+70h+var_10], rax
0x180043ad1  mov     rdi, rcx
0x180043ad4  mov     qword ptr [rcx], 0
0x180043adb  mov     [rsp+170h+var_130], 0
0x180043ae4  lea     rax, [rsp+170h+var_130]
0x180043ae9  mov     [rsp+170h+var_128], rax
0x180043aee  mov     [rsp+170h+var_120], 0
0x180043af7  mov     [rsp+170h+var_118], 1
0x180043afc  lea     rcx, [rsp+170h+var_120]; this
0x180043b01  call    ?GetCallingProcessPackageFullName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x180043b06  mov     ebx, eax
0x180043b08  lea     rcx, [rsp+170h+var_128]
0x180043b0d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180043b12  cmp     ebx, 80070005h
0x180043b18  jnz     loc_180043C66
0x180043b1e  call    IsUMgrOpenProcessHandleForAccessPresent
0x180043b23  test    al, al
0x180043b25  jz      loc_180043C7D
0x180043b2b  mov     [rsp+170h+token], 0
0x180043b34  xor     edx, edx; Val
0x180043b36  mov     r8d, 100h; Size
0x180043b3c  lea     rcx, [rsp+170h+packageFullName]; void *
0x180043b41  call    memset_0
0x180043b46  mov     [rsp+170h+packageFullNameLength], 80h
0x180043b4e  mov     [rsp+170h+Pid], 0
0x180043b56  lea     rdx, [rsp+170h+Pid]; Pid
0x180043b5b  xor     ecx, ecx; Binding
0x180043b5d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180043b63  mov     ebx, eax
0x180043b65  cmp     eax, 6BDh
0x180043b6a  jnz     short loc_180043B76
0x180043b6c  call    cs:__imp_GetCurrentProcessId
0x180043b72  mov     ebx, eax
0x180043b74  jmp     short loc_180043BAE
0x180043b76  cmp     eax, 1
0x180043b79  jl      short loc_180043B84
0x180043b7b  movzx   ebx, ax
0x180043b7e  or      ebx, 80010000h
0x180043b84  test    ebx, ebx
0x180043b86  jns     short loc_180043BAA
0x180043b88  mov     rcx, [rbp+78h]; this
0x180043b8c  mov     r9d, ebx; char *
0x180043b8f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x180043b96  mov     edx, 39h ; '9'; void *
0x180043b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043ba0  mov     edx, 69h ; 'i'
0x180043ba5  jmp     loc_180043C3A
0x180043baa  mov     ebx, [rsp+170h+Pid]
0x180043bae  xor     edx, edx
0x180043bb0  lea     rcx, [rsp+170h+token]
0x180043bb5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180043bba  lea     rdx, [rsp+170h+token]
0x180043bbf  mov     ecx, ebx
0x180043bc1  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180043bc7  test    eax, eax
0x180043bc9  jns     short loc_180043BCF
0x180043bcb  mov     ebx, eax
0x180043bcd  jmp     short loc_180043C4E
0x180043bcf  lea     r8, [rsp+170h+packageFullName]; packageFullName
0x180043bd4  lea     rdx, [rsp+170h+packageFullNameLength]; packageFullNameLength
0x180043bd9  mov     rcx, [rsp+170h+token]; token
0x180043bde  call    cs:__imp_GetPackageFullNameFromToken
0x180043be4  test    eax, eax
0x180043be6  jle     short loc_180043BF2
0x180043be8  movzx   eax, ax
0x180043beb  or      eax, 80070000h
0x180043bf0  test    eax, eax
0x180043bf2  js      short loc_180043BCB
0x180043bf4  lea     rax, [rsp+170h+var_130]
0x180043bf9  mov     [rsp+170h+var_128], rax
0x180043bfe  mov     [rsp+170h+var_120], 0
0x180043c07  mov     [rsp+170h+var_118], 1
0x180043c0c  mov     r9d, [rsp+170h+packageFullNameLength]
0x180043c11  lea     rax, [rsp+170h+var_120]
0x180043c16  mov     [rsp+170h+var_148], rax
0x180043c1b  lea     r8, [rsp+170h+packageFullName]
0x180043c20  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180043c25  mov     ebx, eax
0x180043c27  lea     rcx, [rsp+170h+var_128]
0x180043c2c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180043c31  test    ebx, ebx
0x180043c33  jns     short loc_180043C5A
0x180043c35  mov     edx, 6Ch ; 'l'; void *
0x180043c3a  mov     r9d, ebx; char *
0x180043c3d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x180043c44  mov     rcx, [rbp+78h]; this
0x180043c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043c4d  nop
0x180043c4e  lea     rcx, [rsp+170h+token]
0x180043c53  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043c58  jmp     short loc_180043C7D
0x180043c5a  lea     rcx, [rsp+170h+token]
0x180043c5f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043c64  jmp     short loc_180043C6A
0x180043c66  test    ebx, ebx
0x180043c68  js      short loc_180043C7D
0x180043c6a  mov     rax, [rsp+170h+var_130]
0x180043c6f  mov     [rsp+170h+var_130], 0
0x180043c78  mov     [rdi], rax
0x180043c7b  xor     ebx, ebx
0x180043c7d  lea     rcx, [rsp+170h+var_130]
0x180043c82  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043c87  mov     eax, ebx
0x180043c89  mov     rcx, [rbp+70h+var_10]
0x180043c8d  xor     rcx, rsp; StackCookie
0x180043c90  call    __security_check_cookie
0x180043c95  lea     r11, [rsp+170h+var_s0]
0x180043c9d  mov     rbx, [r11+18h]
0x180043ca1  mov     rdi, [r11+20h]
0x180043ca5  mov     rsp, r11
0x180043ca8  pop     rbp
0x180043ca9  retn
```
