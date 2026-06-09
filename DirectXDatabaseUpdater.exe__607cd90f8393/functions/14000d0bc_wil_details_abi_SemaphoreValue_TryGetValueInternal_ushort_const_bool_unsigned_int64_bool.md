# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000d0bc`
- end: `0x14000d27a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000d038`

## callees

- `0x140002f40`
- `0x140005e90`
- `0x140007980`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000cbc8`
- `0x14000cd00`
- `0x14000d0bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d125`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d1c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d125`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d135`

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
0x14000d0bc  mov     [rsp-8+arg_8], rbx
0x14000d0c1  push    rbp
0x14000d0c2  push    rdi
0x14000d0c3  push    r14
0x14000d0c5  lea     rbp, [rsp-170h]
0x14000d0cd  sub     rsp, 270h
0x14000d0d4  mov     rax, cs:__security_cookie
0x14000d0db  xor     rax, rsp
0x14000d0de  mov     [rbp+180h+var_20], rax
0x14000d0e5  mov     r9, rcx; pszSrc
0x14000d0e8  mov     qword ptr [r8], 0
0x14000d0ef  mov     r14d, 104h
0x14000d0f5  lea     rcx, [rsp+280h+pszDest]; pszDest
0x14000d0fa  mov     edx, r14d; cchDest
0x14000d0fd  mov     rdi, r8
0x14000d100  call    StringCopyWorkerW
0x14000d105  lea     r8, aP0; "_p0"
0x14000d10c  mov     edx, r14d; unsigned __int64
0x14000d10f  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x14000d114  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d119  lea     r8, [rsp+280h+pszDest]; lpName
0x14000d11e  xor     edx, edx; bInheritHandle
0x14000d120  mov     ecx, 1F0003h; dwDesiredAccess
0x14000d125  call    cs:__imp_OpenSemaphoreW
0x14000d12b  mov     [rsp+280h+var_240], rax
0x14000d130  test    rax, rax
0x14000d133  jnz     short loc_14000D162
0x14000d135  call    cs:__imp_GetLastError
0x14000d13b  cmp     eax, 2
0x14000d13e  jz      loc_14000D249
0x14000d144  mov     rcx, [rbp+188h]; this
0x14000d14b  lea     r8, aWil; "wil"
0x14000d152  lea     edx, [r14-34h]; void *
0x14000d156  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d15b  mov     ebx, eax
0x14000d15d  jmp     loc_14000D24B
0x14000d162  lea     rdx, [rsp+280h+var_24C]; int *
0x14000d167  mov     [rsp+280h+var_24C], 0
0x14000d16f  mov     rcx, rax; hHandle
0x14000d172  mov     [rsp+280h+var_250], 0
0x14000d17a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d17f  mov     ebx, eax
0x14000d181  test    eax, eax
0x14000d183  jns     short loc_14000D1A5
0x14000d185  mov     rcx, [rbp+188h]; this
0x14000d18c  lea     r8, aWil; "wil"
0x14000d193  mov     r9d, eax; char *
0x14000d196  mov     edx, 0D6h; void *
0x14000d19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d1a0  jmp     loc_14000D24B
0x14000d1a5  lea     r8, asc_14001C610; "h"
0x14000d1ac  mov     rdx, r14; unsigned __int64
0x14000d1af  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x14000d1b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d1b9  lea     r8, [rsp+280h+pszDest]; lpName
0x14000d1be  xor     edx, edx; bInheritHandle
0x14000d1c0  mov     ecx, 1F0003h; dwDesiredAccess
0x14000d1c5  call    cs:__imp_OpenSemaphoreW
0x14000d1cb  mov     [rsp+280h+var_248], rax
0x14000d1d0  test    rax, rax
0x14000d1d3  jnz     short loc_14000D1FB
0x14000d1d5  mov     rcx, [rbp+188h]; this
0x14000d1dc  lea     r8, aWil; "wil"
0x14000d1e3  mov     edx, 0DCh; void *
0x14000d1e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d1ed  mov     ebx, eax
0x14000d1ef  lea     rcx, [rsp+280h+var_248]
0x14000d1f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000d1f9  jmp     short loc_14000D24B
0x14000d1fb  lea     rdx, [rsp+280h+var_250]; int *
0x14000d200  mov     rcx, rax; hHandle
0x14000d203  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d208  mov     ebx, eax
0x14000d20a  test    eax, eax
0x14000d20c  jns     short loc_14000D22B
0x14000d20e  mov     rcx, [rbp+188h]; this
0x14000d215  lea     r8, aWil; "wil"
0x14000d21c  mov     r9d, eax; char *
0x14000d21f  mov     edx, 0DEh; void *
0x14000d224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d229  jmp     short loc_14000D1EF
0x14000d22b  lea     rcx, [rsp+280h+var_248]
0x14000d230  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000d235  movsxd  rcx, [rsp+280h+var_250]
0x14000d23a  movsxd  rax, [rsp+280h+var_24C]
0x14000d23f  shl     rcx, 1Fh
0x14000d243  or      rcx, rax
0x14000d246  mov     [rdi], rcx
0x14000d249  xor     ebx, ebx
0x14000d24b  lea     rcx, [rsp+280h+var_240]
0x14000d250  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000d255  mov     eax, ebx
0x14000d257  mov     rcx, [rbp+180h+var_20]
0x14000d25e  xor     rcx, rsp; StackCookie
0x14000d261  call    __security_check_cookie
0x14000d266  mov     rbx, [rsp+280h+arg_8]
0x14000d26e  add     rsp, 270h
0x14000d275  pop     r14
0x14000d277  pop     rdi
0x14000d278  pop     rbp
0x14000d279  retn
```
