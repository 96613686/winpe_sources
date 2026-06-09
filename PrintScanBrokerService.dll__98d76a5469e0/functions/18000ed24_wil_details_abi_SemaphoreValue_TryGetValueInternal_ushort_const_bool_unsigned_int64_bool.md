# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ed24`
- end: `0x18000eed4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000eca0`

## callees

- `0x180002d40`
- `0x1800082c8`
- `0x18000af44`
- `0x18000dd8c`
- `0x18000ddac`
- `0x18000e568`
- `0x18000e6a0`
- `0x18000ed24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ed8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee26`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ed8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
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
    StringCchCatW(pszDest, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v17);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18000ed24  mov     [rsp-8+arg_8], rbx
0x18000ed29  push    rbp
0x18000ed2a  push    rdi
0x18000ed2b  push    r14
0x18000ed2d  lea     rbp, [rsp-170h]
0x18000ed35  sub     rsp, 270h
0x18000ed3c  mov     rax, cs:__security_cookie
0x18000ed43  xor     rax, rsp
0x18000ed46  mov     [rbp+180h+var_20], rax
0x18000ed4d  mov     r9, rcx; pszSrc
0x18000ed50  mov     qword ptr [r8], 0
0x18000ed57  mov     r14d, 104h
0x18000ed5d  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000ed62  mov     edx, r14d; cchDest
0x18000ed65  mov     rdi, r8
0x18000ed68  call    StringCopyWorkerW
0x18000ed6d  lea     r8, aP0; "_p0"
0x18000ed74  mov     edx, r14d; unsigned __int64
0x18000ed77  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000ed7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ed81  lea     r8, [rsp+280h+pszDest]; lpName
0x18000ed86  xor     edx, edx; bInheritHandle
0x18000ed88  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ed8d  call    cs:__imp_OpenSemaphoreW
0x18000ed93  mov     [rsp+280h+var_240], rax
0x18000ed98  test    rax, rax
0x18000ed9b  jnz     short loc_18000EDC3
0x18000ed9d  call    cs:__imp_GetLastError
0x18000eda3  cmp     eax, 2
0x18000eda6  jz      loc_18000EEA3
0x18000edac  mov     rcx, [rbp+188h]; this
0x18000edb3  lea     edx, [r14-34h]; void *
0x18000edb7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000edbc  mov     ebx, eax
0x18000edbe  jmp     loc_18000EEA5
0x18000edc3  lea     rdx, [rsp+280h+var_24C]; int *
0x18000edc8  mov     [rsp+280h+var_24C], 0
0x18000edd0  mov     rcx, rax; hHandle
0x18000edd3  mov     [rsp+280h+var_250], 0
0x18000eddb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ede0  mov     ebx, eax
0x18000ede2  test    eax, eax
0x18000ede4  jns     short loc_18000EE06
0x18000ede6  mov     rcx, [rbp+188h]; this
0x18000eded  lea     r8, aWil; "wil"
0x18000edf4  mov     r9d, eax; char *
0x18000edf7  mov     edx, 0D6h; void *
0x18000edfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee01  jmp     loc_18000EEA5
0x18000ee06  lea     r8, asc_18004BCB0; "h"
0x18000ee0d  mov     rdx, r14; unsigned __int64
0x18000ee10  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000ee15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee1a  lea     r8, [rsp+280h+pszDest]; lpName
0x18000ee1f  xor     edx, edx; bInheritHandle
0x18000ee21  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ee26  call    cs:__imp_OpenSemaphoreW
0x18000ee2c  mov     [rsp+280h+var_248], rax
0x18000ee31  test    rax, rax
0x18000ee34  jnz     short loc_18000EE55
0x18000ee36  mov     rcx, [rbp+188h]; this
0x18000ee3d  mov     edx, 0DCh; void *
0x18000ee42  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ee47  mov     ebx, eax
0x18000ee49  lea     rcx, [rsp+280h+var_248]
0x18000ee4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ee53  jmp     short loc_18000EEA5
0x18000ee55  lea     rdx, [rsp+280h+var_250]; int *
0x18000ee5a  mov     rcx, rax; hHandle
0x18000ee5d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ee62  mov     ebx, eax
0x18000ee64  test    eax, eax
0x18000ee66  jns     short loc_18000EE85
0x18000ee68  mov     rcx, [rbp+188h]; this
0x18000ee6f  lea     r8, aWil; "wil"
0x18000ee76  mov     r9d, eax; char *
0x18000ee79  mov     edx, 0DEh; void *
0x18000ee7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee83  jmp     short loc_18000EE49
0x18000ee85  lea     rcx, [rsp+280h+var_248]
0x18000ee8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ee8f  movsxd  rcx, [rsp+280h+var_250]
0x18000ee94  movsxd  rax, [rsp+280h+var_24C]
0x18000ee99  shl     rcx, 1Fh
0x18000ee9d  or      rcx, rax
0x18000eea0  mov     [rdi], rcx
0x18000eea3  xor     ebx, ebx
0x18000eea5  lea     rcx, [rsp+280h+var_240]
0x18000eeaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000eeaf  mov     eax, ebx
0x18000eeb1  mov     rcx, [rbp+180h+var_20]
0x18000eeb8  xor     rcx, rsp; StackCookie
0x18000eebb  call    __security_check_cookie
0x18000eec0  mov     rbx, [rsp+280h+arg_8]
0x18000eec8  add     rsp, 270h
0x18000eecf  pop     r14
0x18000eed1  pop     rdi
0x18000eed2  pop     rbp
0x18000eed3  retn
```
