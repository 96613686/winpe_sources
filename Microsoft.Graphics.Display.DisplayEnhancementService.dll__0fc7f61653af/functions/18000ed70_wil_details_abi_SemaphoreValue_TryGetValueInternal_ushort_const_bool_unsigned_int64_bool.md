# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ed70`
- end: `0x18000ef2e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ecec`

## callees

- `0x180005860`
- `0x180009b3c`
- `0x18000b850`
- `0x18000deac`
- `0x18000decc`
- `0x18000e758`
- `0x18000e890`
- `0x18000ed70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ede9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ede9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000edd9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee79`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000edd9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee79`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v13);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v14);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v17 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v15);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp-8+arg_8], rbx
0x18000ed75  push    rbp
0x18000ed76  push    rdi
0x18000ed77  push    r14
0x18000ed79  lea     rbp, [rsp-170h]
0x18000ed81  sub     rsp, 270h
0x18000ed88  mov     rax, cs:__security_cookie
0x18000ed8f  xor     rax, rsp
0x18000ed92  mov     [rbp+180h+var_20], rax
0x18000ed99  mov     r9, rcx; pszSrc
0x18000ed9c  mov     qword ptr [r8], 0
0x18000eda3  mov     r14d, 104h
0x18000eda9  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000edae  mov     edx, r14d; cchDest
0x18000edb1  mov     rdi, r8
0x18000edb4  call    StringCopyWorkerW
0x18000edb9  lea     r8, aP0; "_p0"
0x18000edc0  mov     edx, r14d; unsigned __int64
0x18000edc3  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000edc8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000edcd  lea     r8, [rsp+280h+pszDest]; lpName
0x18000edd2  xor     edx, edx; bInheritHandle
0x18000edd4  mov     ecx, 1F0003h; dwDesiredAccess
0x18000edd9  call    cs:__imp_OpenSemaphoreW
0x18000eddf  mov     [rsp+280h+var_240], rax
0x18000ede4  test    rax, rax
0x18000ede7  jnz     short loc_18000EE16
0x18000ede9  call    cs:__imp_GetLastError
0x18000edef  cmp     eax, 2
0x18000edf2  jz      loc_18000EEFD
0x18000edf8  mov     rcx, [rbp+188h]; this
0x18000edff  lea     r8, aWil; "wil"
0x18000ee06  lea     edx, [r14-34h]; void *
0x18000ee0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ee0f  mov     ebx, eax
0x18000ee11  jmp     loc_18000EEFF
0x18000ee16  lea     rdx, [rsp+280h+var_24C]; int *
0x18000ee1b  mov     [rsp+280h+var_24C], 0
0x18000ee23  mov     rcx, rax; hHandle
0x18000ee26  mov     [rsp+280h+var_250], 0
0x18000ee2e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ee33  mov     ebx, eax
0x18000ee35  test    eax, eax
0x18000ee37  jns     short loc_18000EE59
0x18000ee39  mov     rcx, [rbp+188h]; this
0x18000ee40  lea     r8, aWil; "wil"
0x18000ee47  mov     r9d, eax; char *
0x18000ee4a  mov     edx, 0D6h; void *
0x18000ee4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee54  jmp     loc_18000EEFF
0x18000ee59  lea     r8, asc_1800FE908; "h"
0x18000ee60  mov     rdx, r14; unsigned __int64
0x18000ee63  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000ee68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee6d  lea     r8, [rsp+280h+pszDest]; lpName
0x18000ee72  xor     edx, edx; bInheritHandle
0x18000ee74  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ee79  call    cs:__imp_OpenSemaphoreW
0x18000ee7f  mov     [rsp+280h+var_248], rax
0x18000ee84  test    rax, rax
0x18000ee87  jnz     short loc_18000EEAF
0x18000ee89  mov     rcx, [rbp+188h]; this
0x18000ee90  lea     r8, aWil; "wil"
0x18000ee97  mov     edx, 0DCh; void *
0x18000ee9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000eea1  mov     ebx, eax
0x18000eea3  lea     rcx, [rsp+280h+var_248]
0x18000eea8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000eead  jmp     short loc_18000EEFF
0x18000eeaf  lea     rdx, [rsp+280h+var_250]; int *
0x18000eeb4  mov     rcx, rax; hHandle
0x18000eeb7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000eebc  mov     ebx, eax
0x18000eebe  test    eax, eax
0x18000eec0  jns     short loc_18000EEDF
0x18000eec2  mov     rcx, [rbp+188h]; this
0x18000eec9  lea     r8, aWil; "wil"
0x18000eed0  mov     r9d, eax; char *
0x18000eed3  mov     edx, 0DEh; void *
0x18000eed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eedd  jmp     short loc_18000EEA3
0x18000eedf  lea     rcx, [rsp+280h+var_248]
0x18000eee4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000eee9  movsxd  rcx, [rsp+280h+var_250]
0x18000eeee  movsxd  rax, [rsp+280h+var_24C]
0x18000eef3  shl     rcx, 1Fh
0x18000eef7  or      rcx, rax
0x18000eefa  mov     [rdi], rcx
0x18000eefd  xor     ebx, ebx
0x18000eeff  lea     rcx, [rsp+280h+var_240]
0x18000ef04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ef09  mov     eax, ebx
0x18000ef0b  mov     rcx, [rbp+180h+var_20]
0x18000ef12  xor     rcx, rsp; StackCookie
0x18000ef15  call    __security_check_cookie
0x18000ef1a  mov     rbx, [rsp+280h+arg_8]
0x18000ef22  add     rsp, 270h
0x18000ef29  pop     r14
0x18000ef2b  pop     rdi
0x18000ef2c  pop     rbp
0x18000ef2d  retn
```
