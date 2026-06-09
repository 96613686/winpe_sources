# Microsoft::Resources::Runtime::RequestAutoMergeFile(ushort const *,ushort * *)

- ea: `0x1800530f8`
- end: `0x18005333c`
- name: `?RequestAutoMergeFile@Runtime@Resources@Microsoft@@YAJPEBGPEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(Microsoft::Resources::Runtime *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180015944`

## callees

- `0x18001be80`
- `0x18002c8d0`
- `0x180032980`
- `0x18003490c`
- `0x1800530f8`
- `0x180053344`
- `0x1800533e4`
- `0x180053468`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800532e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800532e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800531b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800531b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800531d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800531d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800531f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005328d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005332f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800531f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005328d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005332f`

## string_xrefs

- `0x18005313c`: `Windows.Management.Deployment.Internal.PackageManagerRepairAclsInternal`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::RequestAutoMergeFile(
        Microsoft::Resources::Runtime *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdi
  unsigned __int16 *v12; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v14; // eax
  unsigned int v15; // edi
  HSTRING v16; // rcx
  __int64 v17; // rcx
  unsigned int v19; // edi
  __int64 v20; // rcx
  HSTRING v21; // [rsp+20h] [rbp-40h] BYREF
  __int64 v22; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v23; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v23 = (unsigned __int16 *)this;
  *(_QWORD *)a2 = 0;
  v22 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Management.Deployment.Internal.PackageManagerRepairAclsInternal",
         0x47u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>>(
         string,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
  {
    v19 = -2147221008;
    if ( v5 != -2147221008 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)v5,
        (int)v21);
      goto LABEL_12;
    }
  }
  else
  {
    v7 = v22;
    v21 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v22 + 56LL);
    WindowsDeleteString(0);
    v21 = 0;
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v23);
    v10 = v8(v7, *(_QWORD *)(v9 + 24), &v21);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v11 = WindowsGetStringLen(v21) + 1;
      wil::make_unique_nothrow<unsigned short [0]>(&v23, v11);
      v12 = v23;
      if ( v23 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v21, 0);
        v14 = StringCchCopyW(v12, (unsigned int)v11, StringRawBuffer);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v16 = v21;
          *(_QWORD *)a2 = v12;
          WindowsDeleteString(v16);
          v17 = v22;
          v21 = 0;
          if ( v22 )
          {
            v22 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C8,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
          (const char *)(unsigned int)v14,
          (int)v21);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v23);
        WindowsDeleteString(v21);
        v6 = v15;
        goto LABEL_11;
      }
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)0x8007000ELL,
        (int)v21);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v23);
LABEL_10:
      WindowsDeleteString(v21);
LABEL_11:
      v21 = 0;
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(&v22);
      return v6;
    }
    v19 = -2147024894;
    if ( v10 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)v10,
        (int)v21);
      goto LABEL_10;
    }
    WindowsDeleteString(v21);
    v21 = 0;
  }
  v20 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return v19;
}

```

## disassembly

```asm
0x1800530f8  mov     [rsp-18h+arg_10], rbx
0x1800530fd  mov     [rsp-18h+arg_18], rsi
0x180053102  push    rbp
0x180053103  push    rdi
0x180053104  push    r14
0x180053106  mov     rbp, rsp
0x180053109  sub     rsp, 60h
0x18005310d  mov     rax, cs:__security_cookie
0x180053114  xor     rax, rsp
0x180053117  mov     [rbp+var_8], rax
0x18005311b  xor     r14d, r14d
0x18005311e  mov     [rbp+var_30], rcx
0x180053122  mov     rsi, rdx
0x180053125  mov     [rdx], r14
0x180053128  lea     r9, [rbp+string]; string
0x18005312c  mov     [rbp+var_38], r14
0x180053130  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053134  mov     [rbp+string], r14
0x180053138  lea     edx, [r14+47h]; length
0x18005313c  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerRepairAclsInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180053143  call    cs:__imp_WindowsCreateStringReference
0x180053149  test    eax, eax
0x18005314b  js      loc_1800532DA
0x180053151  mov     rcx, [rbp+string]
0x180053155  lea     rdx, [rbp+var_38]
0x180053159  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>>)
0x18005315e  mov     ebx, eax
0x180053160  test    eax, eax
0x180053162  js      loc_1800532B7
0x180053168  mov     rdi, [rbp+var_38]
0x18005316c  xor     ecx, ecx; string
0x18005316e  mov     [rbp+var_40], r14
0x180053172  mov     rax, [rdi]
0x180053175  mov     rbx, [rax+38h]
0x180053179  call    cs:__imp_WindowsDeleteString
0x18005317f  lea     rdx, [rbp+var_30]
0x180053183  mov     [rbp+var_40], r14
0x180053187  lea     rcx, [rbp+hstringHeader]
0x18005318b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180053190  lea     r8, [rbp+var_40]
0x180053194  mov     rcx, rdi
0x180053197  mov     rdx, [rax+18h]
0x18005319b  mov     rax, rbx
0x18005319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531a3  mov     ebx, eax
0x1800531a5  test    eax, eax
0x1800531a7  js      loc_180053280
0x1800531ad  mov     rcx, [rbp+var_40]; string
0x1800531b1  call    cs:__imp_WindowsGetStringLen
0x1800531b7  inc     eax
0x1800531b9  lea     rcx, [rbp+var_30]
0x1800531bd  mov     edx, eax
0x1800531bf  mov     edi, eax
0x1800531c1  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800531c6  mov     rbx, [rbp+var_30]
0x1800531ca  test    rbx, rbx
0x1800531cd  jz      short loc_18005323F
0x1800531cf  mov     rcx, [rbp+var_40]; string
0x1800531d3  xor     edx, edx; length
0x1800531d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800531db  mov     edx, edi; unsigned __int64
0x1800531dd  mov     rcx, rbx; unsigned __int16 *
0x1800531e0  mov     r8, rax; unsigned __int16 *
0x1800531e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800531e8  mov     edi, eax
0x1800531ea  test    eax, eax
0x1800531ec  js      loc_18005330A
0x1800531f2  mov     rcx, [rbp+var_40]; string
0x1800531f6  mov     [rsi], rbx
0x1800531f9  call    cs:__imp_WindowsDeleteString
0x1800531ff  mov     rcx, [rbp+var_38]
0x180053203  mov     [rbp+var_40], r14
0x180053207  test    rcx, rcx
0x18005320a  jz      short loc_18005321C
0x18005320c  mov     [rbp+var_38], r14
0x180053210  mov     rax, [rcx]
0x180053213  mov     rax, [rax+10h]
0x180053217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005321c  xor     eax, eax
0x18005321e  mov     rcx, [rbp+var_8]
0x180053222  xor     rcx, rsp; StackCookie
0x180053225  call    __security_check_cookie
0x18005322a  lea     r11, [rsp+60h+var_s0]
0x18005322f  mov     rbx, [r11+30h]
0x180053233  mov     rsi, [r11+38h]
0x180053237  mov     rsp, r11
0x18005323a  pop     r14
0x18005323c  pop     rdi
0x18005323d  pop     rbp
0x18005323e  retn
0x18005323f  mov     rcx, [rbp+18h]; this
0x180053243  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18005324a  mov     ebx, 8007000Eh
0x18005324f  mov     edx, 1C6h; void *
0x180053254  mov     r9d, ebx; char *
0x180053257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005325c  lea     rcx, [rbp+var_30]
0x180053260  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180053265  mov     rcx, [rbp+var_40]; string
0x180053269  call    cs:__imp_WindowsDeleteString
0x18005326f  mov     [rbp+var_40], r14
0x180053273  lea     rcx, [rbp+var_38]
0x180053277  call    ?InternalRelease@?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(void)
0x18005327c  mov     eax, ebx
0x18005327e  jmp     short loc_18005321E
0x180053280  mov     edi, 80070002h
0x180053285  cmp     eax, edi
0x180053287  jnz     short loc_1800532ED
0x180053289  mov     rcx, [rbp+var_40]; string
0x18005328d  call    cs:__imp_WindowsDeleteString
0x180053293  mov     [rbp+var_40], r14
0x180053297  mov     rcx, [rbp+var_38]
0x18005329b  test    rcx, rcx
0x18005329e  jz      short loc_1800532B0
0x1800532a0  mov     [rbp+var_38], r14
0x1800532a4  mov     rdx, [rcx]
0x1800532a7  mov     rax, [rdx+10h]
0x1800532ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532b0  mov     eax, edi
0x1800532b2  jmp     loc_18005321E
0x1800532b7  mov     edi, 800401F0h
0x1800532bc  cmp     eax, edi
0x1800532be  jz      short loc_180053297
0x1800532c0  mov     rcx, [rbp+18h]; this
0x1800532c4  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800532cb  mov     r9d, eax; char *
0x1800532ce  mov     edx, 1BDh; void *
0x1800532d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532d8  jmp     short loc_180053273
0x1800532da  xor     r9d, r9d; lpArguments
0x1800532dd  xor     r8d, r8d; nNumberOfArguments
0x1800532e0  mov     ecx, eax; dwExceptionCode
0x1800532e2  lea     edx, [r9+1]; dwExceptionFlags
0x1800532e6  call    cs:__imp_RaiseException
0x1800532ec  int     3; Trap to Debugger
0x1800532ed  mov     rcx, [rbp+18h]; this
0x1800532f1  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800532f8  mov     r9d, eax; char *
0x1800532fb  mov     edx, 1C2h; void *
0x180053300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053305  jmp     loc_180053265
0x18005330a  mov     rcx, [rbp+18h]; this
0x18005330e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180053315  mov     r9d, edi; char *
0x180053318  mov     edx, 1C8h; void *
0x18005331d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053322  lea     rcx, [rbp+var_30]
0x180053326  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18005332b  mov     rcx, [rbp+var_40]; string
0x18005332f  call    cs:__imp_WindowsDeleteString
0x180053335  mov     ebx, edi
0x180053337  jmp     loc_18005326F
```
