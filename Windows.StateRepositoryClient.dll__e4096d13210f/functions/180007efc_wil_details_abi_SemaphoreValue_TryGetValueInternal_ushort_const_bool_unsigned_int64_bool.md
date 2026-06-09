# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007efc`
- end: `0x1800080ba`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007e78`

## callees

- `0x180002980`
- `0x180005340`
- `0x1800066b8`
- `0x1800075c4`
- `0x1800075e4`
- `0x180007b2c`
- `0x180007c64`
- `0x180007efc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008005`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f75`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v10; // rax
  const char *v11; // r9
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  size_t v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v20; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v21; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v16);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v21 = v5;
  if ( v5 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v20 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v18);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v14);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v11);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v12);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180007efc  mov     [rsp-8+arg_8], rbx
0x180007f01  push    rbp
0x180007f02  push    rdi
0x180007f03  push    r14
0x180007f05  lea     rbp, [rsp-170h]
0x180007f0d  sub     rsp, 270h
0x180007f14  mov     rax, cs:__security_cookie
0x180007f1b  xor     rax, rsp
0x180007f1e  mov     [rbp+180h+var_20], rax
0x180007f25  mov     r9, rcx; pszSrc
0x180007f28  mov     qword ptr [r8], 0
0x180007f2f  mov     r14d, 104h
0x180007f35  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180007f3a  mov     edx, r14d; cchDest
0x180007f3d  mov     rdi, r8
0x180007f40  call    StringCopyWorkerW
0x180007f45  lea     r8, aP0; "_p0"
0x180007f4c  mov     edx, r14d; unsigned __int64
0x180007f4f  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180007f54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f59  lea     r8, [rsp+280h+pszDest]; lpName
0x180007f5e  xor     edx, edx; bInheritHandle
0x180007f60  mov     ecx, 1F0003h; dwDesiredAccess
0x180007f65  call    cs:__imp_OpenSemaphoreW
0x180007f6b  mov     [rsp+280h+var_240], rax
0x180007f70  test    rax, rax
0x180007f73  jnz     short loc_180007FA2
0x180007f75  call    cs:__imp_GetLastError
0x180007f7b  cmp     eax, 2
0x180007f7e  jz      loc_180008089
0x180007f84  mov     rcx, [rbp+188h]; this
0x180007f8b  lea     r8, aWil; "wil"
0x180007f92  lea     edx, [r14-34h]; void *
0x180007f96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007f9b  mov     ebx, eax
0x180007f9d  jmp     loc_18000808B
0x180007fa2  lea     rdx, [rsp+280h+var_24C]; int *
0x180007fa7  mov     [rsp+280h+var_24C], 0
0x180007faf  mov     rcx, rax; hHandle
0x180007fb2  mov     [rsp+280h+var_250], 0
0x180007fba  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007fbf  mov     ebx, eax
0x180007fc1  test    eax, eax
0x180007fc3  jns     short loc_180007FE5
0x180007fc5  mov     rcx, [rbp+188h]; this
0x180007fcc  lea     r8, aWil; "wil"
0x180007fd3  mov     r9d, eax; char *
0x180007fd6  mov     edx, 0D6h; void *
0x180007fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fe0  jmp     loc_18000808B
0x180007fe5  lea     r8, asc_18002C680; "h"
0x180007fec  mov     rdx, r14; unsigned __int64
0x180007fef  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180007ff4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007ff9  lea     r8, [rsp+280h+pszDest]; lpName
0x180007ffe  xor     edx, edx; bInheritHandle
0x180008000  mov     ecx, 1F0003h; dwDesiredAccess
0x180008005  call    cs:__imp_OpenSemaphoreW
0x18000800b  mov     [rsp+280h+var_248], rax
0x180008010  test    rax, rax
0x180008013  jnz     short loc_18000803B
0x180008015  mov     rcx, [rbp+188h]; this
0x18000801c  lea     r8, aWil; "wil"
0x180008023  mov     edx, 0DCh; void *
0x180008028  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000802d  mov     ebx, eax
0x18000802f  lea     rcx, [rsp+280h+var_248]
0x180008034  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008039  jmp     short loc_18000808B
0x18000803b  lea     rdx, [rsp+280h+var_250]; int *
0x180008040  mov     rcx, rax; hHandle
0x180008043  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008048  mov     ebx, eax
0x18000804a  test    eax, eax
0x18000804c  jns     short loc_18000806B
0x18000804e  mov     rcx, [rbp+188h]; this
0x180008055  lea     r8, aWil; "wil"
0x18000805c  mov     r9d, eax; char *
0x18000805f  mov     edx, 0DEh; void *
0x180008064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008069  jmp     short loc_18000802F
0x18000806b  lea     rcx, [rsp+280h+var_248]
0x180008070  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008075  movsxd  rcx, [rsp+280h+var_250]
0x18000807a  movsxd  rax, [rsp+280h+var_24C]
0x18000807f  shl     rcx, 1Fh
0x180008083  or      rcx, rax
0x180008086  mov     [rdi], rcx
0x180008089  xor     ebx, ebx
0x18000808b  lea     rcx, [rsp+280h+var_240]
0x180008090  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008095  mov     eax, ebx
0x180008097  mov     rcx, [rbp+180h+var_20]
0x18000809e  xor     rcx, rsp; StackCookie
0x1800080a1  call    __security_check_cookie
0x1800080a6  mov     rbx, [rsp+280h+arg_8]
0x1800080ae  add     rsp, 270h
0x1800080b5  pop     r14
0x1800080b7  pop     rdi
0x1800080b8  pop     rbp
0x1800080b9  retn
```
