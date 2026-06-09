# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008f54`
- end: `0x18000910c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008ed0`

## callees

- `0x180003530`
- `0x180007248`
- `0x1800080e0`
- `0x180008a18`
- `0x180008a38`
- `0x180008c70`
- `0x180008cec`
- `0x180008f54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fb8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009056`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fb8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc8`

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
0x180008f54  mov     [rsp-8+arg_8], rbx
0x180008f59  mov     [rsp-8+arg_18], rdi
0x180008f5e  push    rbp
0x180008f5f  lea     rbp, [rsp-170h]
0x180008f67  sub     rsp, 270h
0x180008f6e  mov     rax, cs:__security_cookie
0x180008f75  xor     rax, rsp
0x180008f78  mov     [rbp+170h+var_10], rax
0x180008f7f  mov     r9, rcx; pszSrc
0x180008f82  mov     qword ptr [r8], 0
0x180008f89  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180008f8e  mov     edx, 104h; cchDest
0x180008f93  mov     rdi, r8
0x180008f96  call    StringCopyWorkerW
0x180008f9b  lea     r8, aP0; "_p0"
0x180008fa2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180008fa7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008fac  lea     r8, [rsp+270h+pszDest]; lpName
0x180008fb1  xor     edx, edx; bInheritHandle
0x180008fb3  mov     ecx, 1F0003h; dwDesiredAccess
0x180008fb8  call    cs:__imp_OpenSemaphoreW
0x180008fbe  mov     [rsp+270h+var_230], rax
0x180008fc3  test    rax, rax
0x180008fc6  jnz     short loc_180008FF6
0x180008fc8  call    cs:__imp_GetLastError
0x180008fce  cmp     eax, 2
0x180008fd1  jz      loc_1800090DA
0x180008fd7  mov     rcx, [rbp+178h]; this
0x180008fde  lea     r8, aWil; "wil"
0x180008fe5  mov     edx, 0D0h; void *
0x180008fea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008fef  mov     ebx, eax
0x180008ff1  jmp     loc_1800090DC
0x180008ff6  lea     rdx, [rsp+270h+var_23C]; int *
0x180008ffb  mov     [rsp+270h+var_23C], 0
0x180009003  mov     rcx, rax; hHandle
0x180009006  mov     [rsp+270h+var_240], 0
0x18000900e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009013  mov     ebx, eax
0x180009015  test    eax, eax
0x180009017  jns     short loc_180009039
0x180009019  mov     rcx, [rbp+178h]; this
0x180009020  lea     r8, aWil; "wil"
0x180009027  mov     r9d, eax; char *
0x18000902a  mov     edx, 0D6h; void *
0x18000902f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009034  jmp     loc_1800090DC
0x180009039  lea     r8, asc_180029538; "h"
0x180009040  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009045  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000904a  lea     r8, [rsp+270h+pszDest]; lpName
0x18000904f  xor     edx, edx; bInheritHandle
0x180009051  mov     ecx, 1F0003h; dwDesiredAccess
0x180009056  call    cs:__imp_OpenSemaphoreW
0x18000905c  mov     [rsp+270h+var_238], rax
0x180009061  test    rax, rax
0x180009064  jnz     short loc_18000908C
0x180009066  mov     rcx, [rbp+178h]; this
0x18000906d  lea     r8, aWil; "wil"
0x180009074  mov     edx, 0DCh; void *
0x180009079  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000907e  mov     ebx, eax
0x180009080  lea     rcx, [rsp+270h+var_238]
0x180009085  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000908a  jmp     short loc_1800090DC
0x18000908c  lea     rdx, [rsp+270h+var_240]; int *
0x180009091  mov     rcx, rax; hHandle
0x180009094  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009099  mov     ebx, eax
0x18000909b  test    eax, eax
0x18000909d  jns     short loc_1800090BC
0x18000909f  mov     rcx, [rbp+178h]; this
0x1800090a6  lea     r8, aWil; "wil"
0x1800090ad  mov     r9d, eax; char *
0x1800090b0  mov     edx, 0DEh; void *
0x1800090b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090ba  jmp     short loc_180009080
0x1800090bc  lea     rcx, [rsp+270h+var_238]
0x1800090c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090c6  movsxd  rcx, [rsp+270h+var_240]
0x1800090cb  movsxd  rax, [rsp+270h+var_23C]
0x1800090d0  shl     rcx, 1Fh
0x1800090d4  or      rcx, rax
0x1800090d7  mov     [rdi], rcx
0x1800090da  xor     ebx, ebx
0x1800090dc  lea     rcx, [rsp+270h+var_230]
0x1800090e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090e6  mov     eax, ebx
0x1800090e8  mov     rcx, [rbp+170h+var_10]
0x1800090ef  xor     rcx, rsp; StackCookie
0x1800090f2  call    __security_check_cookie
0x1800090f7  lea     r11, [rsp+270h+var_s0]
0x1800090ff  mov     rbx, [r11+18h]
0x180009103  mov     rdi, [r11+28h]
0x180009107  mov     rsp, r11
0x18000910a  pop     rbp
0x18000910b  retn
```
