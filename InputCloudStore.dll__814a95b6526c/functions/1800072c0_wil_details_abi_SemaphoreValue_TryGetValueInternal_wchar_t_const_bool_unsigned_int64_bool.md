# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800072c0`
- end: `0x180007478`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000723c`

## callees

- `0x180003560`
- `0x180004fd8`
- `0x180005e3c`
- `0x180006af4`
- `0x180006b14`
- `0x180007064`
- `0x180007144`
- `0x1800072c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007324`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007324`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007334`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800072c0  mov     [rsp-8+arg_8], rbx
0x1800072c5  mov     [rsp-8+arg_18], rdi
0x1800072ca  push    rbp
0x1800072cb  lea     rbp, [rsp-170h]
0x1800072d3  sub     rsp, 270h
0x1800072da  mov     rax, cs:__security_cookie
0x1800072e1  xor     rax, rsp
0x1800072e4  mov     [rbp+170h+var_10], rax
0x1800072eb  mov     r9, rcx; pszSrc
0x1800072ee  mov     qword ptr [r8], 0
0x1800072f5  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800072fa  mov     edx, 104h; cchDest
0x1800072ff  mov     rdi, r8
0x180007302  call    StringCopyWorkerW
0x180007307  lea     r8, aP0; "_p0"
0x18000730e  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x180007313  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007318  lea     r8, [rsp+270h+pszDest]; lpName
0x18000731d  xor     edx, edx; bInheritHandle
0x18000731f  mov     ecx, 1F0003h; dwDesiredAccess
0x180007324  call    cs:__imp_OpenSemaphoreW
0x18000732a  mov     [rsp+270h+var_230], rax
0x18000732f  test    rax, rax
0x180007332  jnz     short loc_180007362
0x180007334  call    cs:__imp_GetLastError
0x18000733a  cmp     eax, 2
0x18000733d  jz      loc_180007446
0x180007343  mov     rcx, [rbp+178h]; this
0x18000734a  lea     r8, aWil; "wil"
0x180007351  mov     edx, 0D0h; void *
0x180007356  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000735b  mov     ebx, eax
0x18000735d  jmp     loc_180007448
0x180007362  lea     rdx, [rsp+270h+var_23C]; int *
0x180007367  mov     [rsp+270h+var_23C], 0
0x18000736f  mov     rcx, rax; hHandle
0x180007372  mov     [rsp+270h+var_240], 0
0x18000737a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000737f  mov     ebx, eax
0x180007381  test    eax, eax
0x180007383  jns     short loc_1800073A5
0x180007385  mov     rcx, [rbp+178h]; this
0x18000738c  lea     r8, aWil; "wil"
0x180007393  mov     r9d, eax; char *
0x180007396  mov     edx, 0D6h; void *
0x18000739b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073a0  jmp     loc_180007448
0x1800073a5  lea     r8, asc_180033EB0; "h"
0x1800073ac  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800073b1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800073b6  lea     r8, [rsp+270h+pszDest]; lpName
0x1800073bb  xor     edx, edx; bInheritHandle
0x1800073bd  mov     ecx, 1F0003h; dwDesiredAccess
0x1800073c2  call    cs:__imp_OpenSemaphoreW
0x1800073c8  mov     [rsp+270h+var_238], rax
0x1800073cd  test    rax, rax
0x1800073d0  jnz     short loc_1800073F8
0x1800073d2  mov     rcx, [rbp+178h]; this
0x1800073d9  lea     r8, aWil; "wil"
0x1800073e0  mov     edx, 0DCh; void *
0x1800073e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800073ea  mov     ebx, eax
0x1800073ec  lea     rcx, [rsp+270h+var_238]
0x1800073f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800073f6  jmp     short loc_180007448
0x1800073f8  lea     rdx, [rsp+270h+var_240]; int *
0x1800073fd  mov     rcx, rax; hHandle
0x180007400  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007405  mov     ebx, eax
0x180007407  test    eax, eax
0x180007409  jns     short loc_180007428
0x18000740b  mov     rcx, [rbp+178h]; this
0x180007412  lea     r8, aWil; "wil"
0x180007419  mov     r9d, eax; char *
0x18000741c  mov     edx, 0DEh; void *
0x180007421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007426  jmp     short loc_1800073EC
0x180007428  lea     rcx, [rsp+270h+var_238]
0x18000742d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007432  movsxd  rcx, [rsp+270h+var_240]
0x180007437  movsxd  rax, [rsp+270h+var_23C]
0x18000743c  shl     rcx, 1Fh
0x180007440  or      rcx, rax
0x180007443  mov     [rdi], rcx
0x180007446  xor     ebx, ebx
0x180007448  lea     rcx, [rsp+270h+var_230]
0x18000744d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007452  mov     eax, ebx
0x180007454  mov     rcx, [rbp+170h+var_10]
0x18000745b  xor     rcx, rsp; StackCookie
0x18000745e  call    __security_check_cookie
0x180007463  lea     r11, [rsp+270h+var_s0]
0x18000746b  mov     rbx, [r11+18h]
0x18000746f  mov     rdi, [r11+28h]
0x180007473  mov     rsp, r11
0x180007476  pop     rbp
0x180007477  retn
```
