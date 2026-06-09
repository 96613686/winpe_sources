# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000be8c`
- end: `0x18000c044`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000be08`

## callees

- `0x180006640`
- `0x180009cb8`
- `0x18000aa44`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000bbd0`
- `0x18000bcf8`
- `0x18000be8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bef0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bf8e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bef0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bf8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf00`

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
0x18000be8c  mov     [rsp-8+arg_8], rbx
0x18000be91  mov     [rsp-8+arg_18], rdi
0x18000be96  push    rbp
0x18000be97  lea     rbp, [rsp-170h]
0x18000be9f  sub     rsp, 270h
0x18000bea6  mov     rax, cs:__security_cookie
0x18000bead  xor     rax, rsp
0x18000beb0  mov     [rbp+170h+var_10], rax
0x18000beb7  mov     r9, rcx; pszSrc
0x18000beba  mov     qword ptr [r8], 0
0x18000bec1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000bec6  mov     edx, 104h; cchDest
0x18000becb  mov     rdi, r8
0x18000bece  call    StringCopyWorkerW
0x18000bed3  lea     r8, aP0; "_p0"
0x18000beda  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000bedf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bee4  lea     r8, [rsp+270h+pszDest]; lpName
0x18000bee9  xor     edx, edx; bInheritHandle
0x18000beeb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bef0  call    cs:__imp_OpenSemaphoreW
0x18000bef6  mov     [rsp+270h+var_230], rax
0x18000befb  test    rax, rax
0x18000befe  jnz     short loc_18000BF2E
0x18000bf00  call    cs:__imp_GetLastError
0x18000bf06  cmp     eax, 2
0x18000bf09  jz      loc_18000C012
0x18000bf0f  mov     rcx, [rbp+178h]; this
0x18000bf16  lea     r8, aWil; "wil"
0x18000bf1d  mov     edx, 0D0h; void *
0x18000bf22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bf27  mov     ebx, eax
0x18000bf29  jmp     loc_18000C014
0x18000bf2e  lea     rdx, [rsp+270h+var_23C]; int *
0x18000bf33  mov     [rsp+270h+var_23C], 0
0x18000bf3b  mov     rcx, rax; hHandle
0x18000bf3e  mov     [rsp+270h+var_240], 0
0x18000bf46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bf4b  mov     ebx, eax
0x18000bf4d  test    eax, eax
0x18000bf4f  jns     short loc_18000BF71
0x18000bf51  mov     rcx, [rbp+178h]; this
0x18000bf58  lea     r8, aWil; "wil"
0x18000bf5f  mov     r9d, eax; char *
0x18000bf62  mov     edx, 0D6h; void *
0x18000bf67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf6c  jmp     loc_18000C014
0x18000bf71  lea     r8, asc_1800A1950; "h"
0x18000bf78  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000bf7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bf82  lea     r8, [rsp+270h+pszDest]; lpName
0x18000bf87  xor     edx, edx; bInheritHandle
0x18000bf89  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bf8e  call    cs:__imp_OpenSemaphoreW
0x18000bf94  mov     [rsp+270h+var_238], rax
0x18000bf99  test    rax, rax
0x18000bf9c  jnz     short loc_18000BFC4
0x18000bf9e  mov     rcx, [rbp+178h]; this
0x18000bfa5  lea     r8, aWil; "wil"
0x18000bfac  mov     edx, 0DCh; void *
0x18000bfb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bfb6  mov     ebx, eax
0x18000bfb8  lea     rcx, [rsp+270h+var_238]
0x18000bfbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bfc2  jmp     short loc_18000C014
0x18000bfc4  lea     rdx, [rsp+270h+var_240]; int *
0x18000bfc9  mov     rcx, rax; hHandle
0x18000bfcc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bfd1  mov     ebx, eax
0x18000bfd3  test    eax, eax
0x18000bfd5  jns     short loc_18000BFF4
0x18000bfd7  mov     rcx, [rbp+178h]; this
0x18000bfde  lea     r8, aWil; "wil"
0x18000bfe5  mov     r9d, eax; char *
0x18000bfe8  mov     edx, 0DEh; void *
0x18000bfed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bff2  jmp     short loc_18000BFB8
0x18000bff4  lea     rcx, [rsp+270h+var_238]
0x18000bff9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bffe  movsxd  rcx, [rsp+270h+var_240]
0x18000c003  movsxd  rax, [rsp+270h+var_23C]
0x18000c008  shl     rcx, 1Fh
0x18000c00c  or      rcx, rax
0x18000c00f  mov     [rdi], rcx
0x18000c012  xor     ebx, ebx
0x18000c014  lea     rcx, [rsp+270h+var_230]
0x18000c019  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c01e  mov     eax, ebx
0x18000c020  mov     rcx, [rbp+170h+var_10]
0x18000c027  xor     rcx, rsp; StackCookie
0x18000c02a  call    __security_check_cookie
0x18000c02f  lea     r11, [rsp+270h+var_s0]
0x18000c037  mov     rbx, [r11+18h]
0x18000c03b  mov     rdi, [r11+28h]
0x18000c03f  mov     rsp, r11
0x18000c042  pop     rbp
0x18000c043  retn
```
