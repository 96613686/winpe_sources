# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005748`
- end: `0x140005900`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140003728`

## callees

- `0x140001c80`
- `0x1400035e0`
- `0x140004364`
- `0x140005064`
- `0x140005084`
- `0x14000555c`
- `0x14000563c`
- `0x140005748`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400057ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000584a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400057ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000584a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057bc`

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
0x140005748  mov     [rsp-8+arg_8], rbx
0x14000574d  mov     [rsp-8+arg_18], rdi
0x140005752  push    rbp
0x140005753  lea     rbp, [rsp-170h]
0x14000575b  sub     rsp, 270h
0x140005762  mov     rax, cs:__security_cookie
0x140005769  xor     rax, rsp
0x14000576c  mov     [rbp+170h+var_10], rax
0x140005773  mov     r9, rcx; pszSrc
0x140005776  mov     qword ptr [r8], 0
0x14000577d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140005782  mov     edx, 104h; cchDest
0x140005787  mov     rdi, r8
0x14000578a  call    StringCopyWorkerW
0x14000578f  lea     r8, aP0; "_p0"
0x140005796  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000579b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400057a0  lea     r8, [rsp+270h+pszDest]; lpName
0x1400057a5  xor     edx, edx; bInheritHandle
0x1400057a7  mov     ecx, 1F0003h; dwDesiredAccess
0x1400057ac  call    cs:__imp_OpenSemaphoreW
0x1400057b2  mov     [rsp+270h+var_230], rax
0x1400057b7  test    rax, rax
0x1400057ba  jnz     short loc_1400057EA
0x1400057bc  call    cs:__imp_GetLastError
0x1400057c2  cmp     eax, 2
0x1400057c5  jz      loc_1400058CE
0x1400057cb  mov     rcx, [rbp+178h]; this
0x1400057d2  lea     r8, aWil; "wil"
0x1400057d9  mov     edx, 0D0h; void *
0x1400057de  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400057e3  mov     ebx, eax
0x1400057e5  jmp     loc_1400058D0
0x1400057ea  lea     rdx, [rsp+270h+var_23C]; int *
0x1400057ef  mov     [rsp+270h+var_23C], 0
0x1400057f7  mov     rcx, rax; hHandle
0x1400057fa  mov     [rsp+270h+var_240], 0
0x140005802  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005807  mov     ebx, eax
0x140005809  test    eax, eax
0x14000580b  jns     short loc_14000582D
0x14000580d  mov     rcx, [rbp+178h]; this
0x140005814  lea     r8, aWil; "wil"
0x14000581b  mov     r9d, eax; char *
0x14000581e  mov     edx, 0D6h; void *
0x140005823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005828  jmp     loc_1400058D0
0x14000582d  lea     r8, asc_140019740; "h"
0x140005834  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140005839  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000583e  lea     r8, [rsp+270h+pszDest]; lpName
0x140005843  xor     edx, edx; bInheritHandle
0x140005845  mov     ecx, 1F0003h; dwDesiredAccess
0x14000584a  call    cs:__imp_OpenSemaphoreW
0x140005850  mov     [rsp+270h+var_238], rax
0x140005855  test    rax, rax
0x140005858  jnz     short loc_140005880
0x14000585a  mov     rcx, [rbp+178h]; this
0x140005861  lea     r8, aWil; "wil"
0x140005868  mov     edx, 0DCh; void *
0x14000586d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005872  mov     ebx, eax
0x140005874  lea     rcx, [rsp+270h+var_238]
0x140005879  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000587e  jmp     short loc_1400058D0
0x140005880  lea     rdx, [rsp+270h+var_240]; int *
0x140005885  mov     rcx, rax; hHandle
0x140005888  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000588d  mov     ebx, eax
0x14000588f  test    eax, eax
0x140005891  jns     short loc_1400058B0
0x140005893  mov     rcx, [rbp+178h]; this
0x14000589a  lea     r8, aWil; "wil"
0x1400058a1  mov     r9d, eax; char *
0x1400058a4  mov     edx, 0DEh; void *
0x1400058a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058ae  jmp     short loc_140005874
0x1400058b0  lea     rcx, [rsp+270h+var_238]
0x1400058b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400058ba  movsxd  rcx, [rsp+270h+var_240]
0x1400058bf  movsxd  rax, [rsp+270h+var_23C]
0x1400058c4  shl     rcx, 1Fh
0x1400058c8  or      rcx, rax
0x1400058cb  mov     [rdi], rcx
0x1400058ce  xor     ebx, ebx
0x1400058d0  lea     rcx, [rsp+270h+var_230]
0x1400058d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400058da  mov     eax, ebx
0x1400058dc  mov     rcx, [rbp+170h+var_10]
0x1400058e3  xor     rcx, rsp; StackCookie
0x1400058e6  call    __security_check_cookie
0x1400058eb  lea     r11, [rsp+270h+var_s0]
0x1400058f3  mov     rbx, [r11+18h]
0x1400058f7  mov     rdi, [r11+28h]
0x1400058fb  mov     rsp, r11
0x1400058fe  pop     rbp
0x1400058ff  retn
```
