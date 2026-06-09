# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ba70`
- end: `0x18001bc2e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001b9ec`

## callees

- `0x1800094c0`
- `0x180016dcc`
- `0x180018ab0`
- `0x18001ab7c`
- `0x18001ab9c`
- `0x18001b30c`
- `0x18001b4ac`
- `0x18001ba70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bad9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bb79`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bad9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae9`

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
0x18001ba70  mov     [rsp-8+arg_8], rbx
0x18001ba75  push    rbp
0x18001ba76  push    rdi
0x18001ba77  push    r14
0x18001ba79  lea     rbp, [rsp-170h]
0x18001ba81  sub     rsp, 270h
0x18001ba88  mov     rax, cs:__security_cookie
0x18001ba8f  xor     rax, rsp
0x18001ba92  mov     [rbp+180h+var_20], rax
0x18001ba99  mov     r9, rcx; pszSrc
0x18001ba9c  mov     qword ptr [r8], 0
0x18001baa3  mov     r14d, 104h
0x18001baa9  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18001baae  mov     edx, r14d; cchDest
0x18001bab1  mov     rdi, r8
0x18001bab4  call    StringCopyWorkerW
0x18001bab9  lea     r8, aP0; "_p0"
0x18001bac0  mov     edx, r14d; unsigned __int64
0x18001bac3  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001bac8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bacd  lea     r8, [rsp+280h+pszDest]; lpName
0x18001bad2  xor     edx, edx; bInheritHandle
0x18001bad4  mov     ecx, 1F0003h; dwDesiredAccess
0x18001bad9  call    cs:__imp_OpenSemaphoreW
0x18001badf  mov     [rsp+280h+var_240], rax
0x18001bae4  test    rax, rax
0x18001bae7  jnz     short loc_18001BB16
0x18001bae9  call    cs:__imp_GetLastError
0x18001baef  cmp     eax, 2
0x18001baf2  jz      loc_18001BBFD
0x18001baf8  mov     rcx, [rbp+188h]; this
0x18001baff  lea     r8, aWil; "wil"
0x18001bb06  lea     edx, [r14-34h]; void *
0x18001bb0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bb0f  mov     ebx, eax
0x18001bb11  jmp     loc_18001BBFF
0x18001bb16  lea     rdx, [rsp+280h+var_24C]; int *
0x18001bb1b  mov     [rsp+280h+var_24C], 0
0x18001bb23  mov     rcx, rax; hHandle
0x18001bb26  mov     [rsp+280h+var_250], 0
0x18001bb2e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001bb33  mov     ebx, eax
0x18001bb35  test    eax, eax
0x18001bb37  jns     short loc_18001BB59
0x18001bb39  mov     rcx, [rbp+188h]; this
0x18001bb40  lea     r8, aWil; "wil"
0x18001bb47  mov     r9d, eax; char *
0x18001bb4a  mov     edx, 0D6h; void *
0x18001bb4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb54  jmp     loc_18001BBFF
0x18001bb59  lea     r8, asc_1800D38D8; "h"
0x18001bb60  mov     rdx, r14; unsigned __int64
0x18001bb63  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001bb68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bb6d  lea     r8, [rsp+280h+pszDest]; lpName
0x18001bb72  xor     edx, edx; bInheritHandle
0x18001bb74  mov     ecx, 1F0003h; dwDesiredAccess
0x18001bb79  call    cs:__imp_OpenSemaphoreW
0x18001bb7f  mov     [rsp+280h+var_248], rax
0x18001bb84  test    rax, rax
0x18001bb87  jnz     short loc_18001BBAF
0x18001bb89  mov     rcx, [rbp+188h]; this
0x18001bb90  lea     r8, aWil; "wil"
0x18001bb97  mov     edx, 0DCh; void *
0x18001bb9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bba1  mov     ebx, eax
0x18001bba3  lea     rcx, [rsp+280h+var_248]
0x18001bba8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbad  jmp     short loc_18001BBFF
0x18001bbaf  lea     rdx, [rsp+280h+var_250]; int *
0x18001bbb4  mov     rcx, rax; hHandle
0x18001bbb7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001bbbc  mov     ebx, eax
0x18001bbbe  test    eax, eax
0x18001bbc0  jns     short loc_18001BBDF
0x18001bbc2  mov     rcx, [rbp+188h]; this
0x18001bbc9  lea     r8, aWil; "wil"
0x18001bbd0  mov     r9d, eax; char *
0x18001bbd3  mov     edx, 0DEh; void *
0x18001bbd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbdd  jmp     short loc_18001BBA3
0x18001bbdf  lea     rcx, [rsp+280h+var_248]
0x18001bbe4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbe9  movsxd  rcx, [rsp+280h+var_250]
0x18001bbee  movsxd  rax, [rsp+280h+var_24C]
0x18001bbf3  shl     rcx, 1Fh
0x18001bbf7  or      rcx, rax
0x18001bbfa  mov     [rdi], rcx
0x18001bbfd  xor     ebx, ebx
0x18001bbff  lea     rcx, [rsp+280h+var_240]
0x18001bc04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bc09  mov     eax, ebx
0x18001bc0b  mov     rcx, [rbp+180h+var_20]
0x18001bc12  xor     rcx, rsp; StackCookie
0x18001bc15  call    __security_check_cookie
0x18001bc1a  mov     rbx, [rsp+280h+arg_8]
0x18001bc22  add     rsp, 270h
0x18001bc29  pop     r14
0x18001bc2b  pop     rdi
0x18001bc2c  pop     rbp
0x18001bc2d  retn
```
