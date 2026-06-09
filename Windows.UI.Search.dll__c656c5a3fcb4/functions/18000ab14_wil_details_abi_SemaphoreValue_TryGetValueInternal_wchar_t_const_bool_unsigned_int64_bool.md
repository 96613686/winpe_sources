# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ab14`
- end: `0x18000acbe`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000aa90`

## callees

- `0x1800055d8`
- `0x1800077d0`
- `0x180009d4c`
- `0x180009d6c`
- `0x18000a42c`
- `0x18000a554`
- `0x18000ab14`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ab78`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac0f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ab78`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab88`

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
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x18000ab14  mov     [rsp-8+arg_8], rbx
0x18000ab19  mov     [rsp-8+arg_18], rdi
0x18000ab1e  push    rbp
0x18000ab1f  lea     rbp, [rsp-170h]
0x18000ab27  sub     rsp, 270h
0x18000ab2e  mov     rax, cs:__security_cookie
0x18000ab35  xor     rax, rsp
0x18000ab38  mov     [rbp+170h+var_10], rax
0x18000ab3f  mov     r9, rcx; pszSrc
0x18000ab42  mov     qword ptr [r8], 0
0x18000ab49  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000ab4e  mov     edx, 104h; cchDest
0x18000ab53  mov     rdi, r8
0x18000ab56  call    StringCopyWorkerW
0x18000ab5b  lea     r8, aP0; "_p0"
0x18000ab62  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000ab67  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ab6c  lea     r8, [rsp+270h+pszDest]; lpName
0x18000ab71  xor     edx, edx; bInheritHandle
0x18000ab73  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ab78  call    cs:__imp_OpenSemaphoreW
0x18000ab7e  mov     [rsp+270h+var_230], rax
0x18000ab83  test    rax, rax
0x18000ab86  jnz     short loc_18000ABAF
0x18000ab88  call    cs:__imp_GetLastError
0x18000ab8e  cmp     eax, 2
0x18000ab91  jz      loc_18000AC8C
0x18000ab97  mov     rcx, [rbp+178h]; this
0x18000ab9e  mov     edx, 0D0h; void *
0x18000aba3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000aba8  mov     ebx, eax
0x18000abaa  jmp     loc_18000AC8E
0x18000abaf  lea     rdx, [rsp+270h+var_23C]; int *
0x18000abb4  mov     [rsp+270h+var_23C], 0
0x18000abbc  mov     rcx, rax; hHandle
0x18000abbf  mov     [rsp+270h+var_240], 0
0x18000abc7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000abcc  mov     ebx, eax
0x18000abce  test    eax, eax
0x18000abd0  jns     short loc_18000ABF2
0x18000abd2  mov     rcx, [rbp+178h]; this
0x18000abd9  lea     r8, aWil; "wil"
0x18000abe0  mov     r9d, eax; char *
0x18000abe3  mov     edx, 0D6h; void *
0x18000abe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abed  jmp     loc_18000AC8E
0x18000abf2  lea     r8, asc_18008AD88; "h"
0x18000abf9  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000abfe  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ac03  lea     r8, [rsp+270h+pszDest]; lpName
0x18000ac08  xor     edx, edx; bInheritHandle
0x18000ac0a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ac0f  call    cs:__imp_OpenSemaphoreW
0x18000ac15  mov     [rsp+270h+var_238], rax
0x18000ac1a  test    rax, rax
0x18000ac1d  jnz     short loc_18000AC3E
0x18000ac1f  mov     rcx, [rbp+178h]; this
0x18000ac26  mov     edx, 0DCh; void *
0x18000ac2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ac30  mov     ebx, eax
0x18000ac32  lea     rcx, [rsp+270h+var_238]
0x18000ac37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac3c  jmp     short loc_18000AC8E
0x18000ac3e  lea     rdx, [rsp+270h+var_240]; int *
0x18000ac43  mov     rcx, rax; hHandle
0x18000ac46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ac4b  mov     ebx, eax
0x18000ac4d  test    eax, eax
0x18000ac4f  jns     short loc_18000AC6E
0x18000ac51  mov     rcx, [rbp+178h]; this
0x18000ac58  lea     r8, aWil; "wil"
0x18000ac5f  mov     r9d, eax; char *
0x18000ac62  mov     edx, 0DEh; void *
0x18000ac67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac6c  jmp     short loc_18000AC32
0x18000ac6e  lea     rcx, [rsp+270h+var_238]
0x18000ac73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac78  movsxd  rcx, [rsp+270h+var_240]
0x18000ac7d  movsxd  rax, [rsp+270h+var_23C]
0x18000ac82  shl     rcx, 1Fh
0x18000ac86  or      rcx, rax
0x18000ac89  mov     [rdi], rcx
0x18000ac8c  xor     ebx, ebx
0x18000ac8e  lea     rcx, [rsp+270h+var_230]
0x18000ac93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac98  mov     eax, ebx
0x18000ac9a  mov     rcx, [rbp+170h+var_10]
0x18000aca1  xor     rcx, rsp; StackCookie
0x18000aca4  call    __security_check_cookie
0x18000aca9  lea     r11, [rsp+270h+var_s0]
0x18000acb1  mov     rbx, [r11+18h]
0x18000acb5  mov     rdi, [r11+28h]
0x18000acb9  mov     rsp, r11
0x18000acbc  pop     rbp
0x18000acbd  retn
```
