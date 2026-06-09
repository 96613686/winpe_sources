# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800115e8`
- end: `0x1800117a6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000eb28`

## callees

- `0x1800035d4`
- `0x18000e904`
- `0x18000fddc`
- `0x180010f34`
- `0x180010f54`
- `0x1800115e8`
- `0x180012978`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011651`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800116f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011651`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800116f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011661`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x1800115e8  mov     [rsp-8+arg_8], rbx
0x1800115ed  push    rbp
0x1800115ee  push    rdi
0x1800115ef  push    r14
0x1800115f1  lea     rbp, [rsp-160h]
0x1800115f9  sub     rsp, 260h
0x180011600  mov     rax, cs:__security_cookie
0x180011607  xor     rax, rsp
0x18001160a  mov     [rbp+170h+var_20], rax
0x180011611  mov     rdi, r8
0x180011614  mov     qword ptr [r8], 0
0x18001161b  mov     r8, rcx; pszSrc
0x18001161e  mov     r14d, 104h
0x180011624  mov     edx, r14d; cchDest
0x180011627  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001162c  call    StringCchCopyW
0x180011631  lea     r8, aP0; "_p0"
0x180011638  mov     edx, r14d; cchDest
0x18001163b  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180011640  call    StringCchCatW
0x180011645  lea     r8, [rsp+270h+pszDest]; lpName
0x18001164a  xor     edx, edx; bInheritHandle
0x18001164c  mov     ecx, 1F0003h; dwDesiredAccess
0x180011651  call    cs:__imp_OpenSemaphoreW
0x180011657  mov     [rsp+270h+var_240], rax
0x18001165c  test    rax, rax
0x18001165f  jnz     short loc_18001168E
0x180011661  call    cs:__imp_GetLastError
0x180011667  cmp     eax, 2
0x18001166a  jz      loc_180011775
0x180011670  mov     rcx, [rbp+178h]; this
0x180011677  lea     r8, aWil; "wil"
0x18001167e  lea     edx, [r14-34h]; void *
0x180011682  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011687  mov     ebx, eax
0x180011689  jmp     loc_180011777
0x18001168e  lea     rdx, [rsp+270h+var_24C]; int *
0x180011693  mov     [rsp+270h+var_24C], 0
0x18001169b  mov     rcx, rax; hHandle
0x18001169e  mov     [rsp+270h+var_250], 0; int
0x1800116a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800116ab  mov     ebx, eax
0x1800116ad  test    eax, eax
0x1800116af  jns     short loc_1800116D1
0x1800116b1  mov     rcx, [rbp+178h]; this
0x1800116b8  lea     r8, aWil; "wil"
0x1800116bf  mov     r9d, eax; char *
0x1800116c2  mov     edx, 0D6h; void *
0x1800116c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116cc  jmp     loc_180011777
0x1800116d1  lea     r8, asc_180026E60; "h"
0x1800116d8  mov     rdx, r14; cchDest
0x1800116db  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800116e0  call    StringCchCatW
0x1800116e5  lea     r8, [rsp+270h+pszDest]; lpName
0x1800116ea  xor     edx, edx; bInheritHandle
0x1800116ec  mov     ecx, 1F0003h; dwDesiredAccess
0x1800116f1  call    cs:__imp_OpenSemaphoreW
0x1800116f7  mov     [rsp+270h+var_248], rax
0x1800116fc  test    rax, rax
0x1800116ff  jnz     short loc_180011727
0x180011701  mov     rcx, [rbp+178h]; this
0x180011708  lea     r8, aWil; "wil"
0x18001170f  mov     edx, 0DCh; void *
0x180011714  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011719  mov     ebx, eax
0x18001171b  lea     rcx, [rsp+270h+var_248]
0x180011720  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011725  jmp     short loc_180011777
0x180011727  lea     rdx, [rsp+270h+var_250]; int *
0x18001172c  mov     rcx, rax; hHandle
0x18001172f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011734  mov     ebx, eax
0x180011736  test    eax, eax
0x180011738  jns     short loc_180011757
0x18001173a  mov     rcx, [rbp+178h]; this
0x180011741  lea     r8, aWil; "wil"
0x180011748  mov     r9d, eax; char *
0x18001174b  mov     edx, 0DEh; void *
0x180011750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011755  jmp     short loc_18001171B
0x180011757  lea     rcx, [rsp+270h+var_248]
0x18001175c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011761  movsxd  rcx, [rsp+270h+var_250]
0x180011766  movsxd  rax, [rsp+270h+var_24C]
0x18001176b  shl     rcx, 1Fh
0x18001176f  or      rcx, rax
0x180011772  mov     [rdi], rcx
0x180011775  xor     ebx, ebx
0x180011777  lea     rcx, [rsp+270h+var_240]
0x18001177c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011781  mov     eax, ebx
0x180011783  mov     rcx, [rbp+170h+var_20]
0x18001178a  xor     rcx, rsp; StackCookie
0x18001178d  call    __security_check_cookie
0x180011792  mov     rbx, [rsp+270h+arg_8]
0x18001179a  add     rsp, 260h
0x1800117a1  pop     r14
0x1800117a3  pop     rdi
0x1800117a4  pop     rbp
0x1800117a5  retn
```
