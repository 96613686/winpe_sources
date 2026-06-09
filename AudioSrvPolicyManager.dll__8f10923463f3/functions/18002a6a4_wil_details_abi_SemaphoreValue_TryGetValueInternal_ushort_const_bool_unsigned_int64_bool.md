# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002a6a4`
- end: `0x18002a85c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180036488`

## callees

- `0x18000a384`
- `0x1800273c4`
- `0x18002a6a4`
- `0x18002a864`
- `0x18002a8e0`
- `0x18002acfc`
- `0x180031960`
- `0x180034910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a708`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a7a6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a708`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a718`

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
0x18002a6a4  mov     [rsp-8+arg_8], rbx
0x18002a6a9  mov     [rsp-8+arg_18], rdi
0x18002a6ae  push    rbp
0x18002a6af  lea     rbp, [rsp-170h]
0x18002a6b7  sub     rsp, 270h
0x18002a6be  mov     rax, cs:__security_cookie
0x18002a6c5  xor     rax, rsp
0x18002a6c8  mov     [rbp+170h+var_10], rax
0x18002a6cf  mov     r9, rcx; pszSrc
0x18002a6d2  mov     qword ptr [r8], 0
0x18002a6d9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18002a6de  mov     edx, 104h; cchDest
0x18002a6e3  mov     rdi, r8
0x18002a6e6  call    StringCopyWorkerW
0x18002a6eb  lea     r8, aP0; "_p0"
0x18002a6f2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002a6f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a6fc  lea     r8, [rsp+270h+pszDest]; lpName
0x18002a701  xor     edx, edx; bInheritHandle
0x18002a703  mov     ecx, 1F0003h; dwDesiredAccess
0x18002a708  call    cs:__imp_OpenSemaphoreW
0x18002a70e  mov     [rsp+270h+var_230], rax
0x18002a713  test    rax, rax
0x18002a716  jnz     short loc_18002A746
0x18002a718  call    cs:__imp_GetLastError
0x18002a71e  cmp     eax, 2
0x18002a721  jz      loc_18002A82A
0x18002a727  mov     rcx, [rbp+178h]; this
0x18002a72e  lea     r8, aWil; "wil"
0x18002a735  mov     edx, 0D0h; void *
0x18002a73a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a73f  mov     ebx, eax
0x18002a741  jmp     loc_18002A82C
0x18002a746  lea     rdx, [rsp+270h+var_23C]; int *
0x18002a74b  mov     [rsp+270h+var_23C], 0
0x18002a753  mov     rcx, rax; hHandle
0x18002a756  mov     [rsp+270h+var_240], 0
0x18002a75e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002a763  mov     ebx, eax
0x18002a765  test    eax, eax
0x18002a767  jns     short loc_18002A789
0x18002a769  mov     rcx, [rbp+178h]; this
0x18002a770  lea     r8, aWil; "wil"
0x18002a777  mov     r9d, eax; char *
0x18002a77a  mov     edx, 0D6h; void *
0x18002a77f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a784  jmp     loc_18002A82C
0x18002a789  lea     r8, asc_180053D98; "h"
0x18002a790  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002a795  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a79a  lea     r8, [rsp+270h+pszDest]; lpName
0x18002a79f  xor     edx, edx; bInheritHandle
0x18002a7a1  mov     ecx, 1F0003h; dwDesiredAccess
0x18002a7a6  call    cs:__imp_OpenSemaphoreW
0x18002a7ac  mov     [rsp+270h+var_238], rax
0x18002a7b1  test    rax, rax
0x18002a7b4  jnz     short loc_18002A7DC
0x18002a7b6  mov     rcx, [rbp+178h]; this
0x18002a7bd  lea     r8, aWil; "wil"
0x18002a7c4  mov     edx, 0DCh; void *
0x18002a7c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a7ce  mov     ebx, eax
0x18002a7d0  lea     rcx, [rsp+270h+var_238]
0x18002a7d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a7da  jmp     short loc_18002A82C
0x18002a7dc  lea     rdx, [rsp+270h+var_240]; int *
0x18002a7e1  mov     rcx, rax; hHandle
0x18002a7e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002a7e9  mov     ebx, eax
0x18002a7eb  test    eax, eax
0x18002a7ed  jns     short loc_18002A80C
0x18002a7ef  mov     rcx, [rbp+178h]; this
0x18002a7f6  lea     r8, aWil; "wil"
0x18002a7fd  mov     r9d, eax; char *
0x18002a800  mov     edx, 0DEh; void *
0x18002a805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a80a  jmp     short loc_18002A7D0
0x18002a80c  lea     rcx, [rsp+270h+var_238]
0x18002a811  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a816  movsxd  rcx, [rsp+270h+var_240]
0x18002a81b  movsxd  rax, [rsp+270h+var_23C]
0x18002a820  shl     rcx, 1Fh
0x18002a824  or      rcx, rax
0x18002a827  mov     [rdi], rcx
0x18002a82a  xor     ebx, ebx
0x18002a82c  lea     rcx, [rsp+270h+var_230]
0x18002a831  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a836  mov     eax, ebx
0x18002a838  mov     rcx, [rbp+170h+var_10]
0x18002a83f  xor     rcx, rsp; StackCookie
0x18002a842  call    __security_check_cookie
0x18002a847  lea     r11, [rsp+270h+var_s0]
0x18002a84f  mov     rbx, [r11+18h]
0x18002a853  mov     rdi, [r11+28h]
0x18002a857  mov     rsp, r11
0x18002a85a  pop     rbp
0x18002a85b  retn
```
