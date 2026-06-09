# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b8fc`
- end: `0x18000bacd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b878`

## callees

- `0x180006f60`
- `0x180009004`
- `0x18000a14c`
- `0x18000aff4`
- `0x18000b014`
- `0x18000b550`
- `0x18000b68c`
- `0x18000b8fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b965`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b965`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b97b`

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
0x18000b8fc  mov     [rsp-8+arg_8], rbx
0x18000b901  push    rbp
0x18000b902  push    rdi
0x18000b903  push    r14
0x18000b905  lea     rbp, [rsp-170h]
0x18000b90d  sub     rsp, 270h
0x18000b914  mov     rax, cs:__security_cookie
0x18000b91b  xor     rax, rsp
0x18000b91e  mov     [rbp+180h+var_20], rax
0x18000b925  mov     r9, rcx; pszSrc
0x18000b928  mov     qword ptr [r8], 0
0x18000b92f  mov     r14d, 104h
0x18000b935  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000b93a  mov     edx, r14d; cchDest
0x18000b93d  mov     rdi, r8
0x18000b940  call    StringCopyWorkerW
0x18000b945  lea     r8, aP0; "_p0"
0x18000b94c  mov     edx, r14d; unsigned __int64
0x18000b94f  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000b954  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b959  lea     r8, [rsp+280h+pszDest]; lpName
0x18000b95e  xor     edx, edx; bInheritHandle
0x18000b960  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b965  call    cs:__imp_OpenSemaphoreW
0x18000b96c  nop     dword ptr [rax+rax+00h]
0x18000b971  mov     [rsp+280h+var_240], rax
0x18000b976  test    rax, rax
0x18000b979  jnz     short loc_18000B9AE
0x18000b97b  call    cs:__imp_GetLastError
0x18000b982  nop     dword ptr [rax+rax+00h]
0x18000b987  cmp     eax, 2
0x18000b98a  jz      loc_18000BA9B
0x18000b990  mov     rcx, [rbp+188h]; this
0x18000b997  lea     r8, aWil; "wil"
0x18000b99e  lea     edx, [r14-34h]; void *
0x18000b9a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9a7  mov     ebx, eax
0x18000b9a9  jmp     loc_18000BA9D
0x18000b9ae  lea     rdx, [rsp+280h+var_24C]; int *
0x18000b9b3  mov     [rsp+280h+var_24C], 0
0x18000b9bb  mov     rcx, rax; hHandle
0x18000b9be  mov     [rsp+280h+var_250], 0
0x18000b9c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b9cb  mov     ebx, eax
0x18000b9cd  test    eax, eax
0x18000b9cf  jns     short loc_18000B9F1
0x18000b9d1  mov     rcx, [rbp+188h]; this
0x18000b9d8  lea     r8, aWil; "wil"
0x18000b9df  mov     r9d, eax; char *
0x18000b9e2  mov     edx, 0D6h; void *
0x18000b9e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9ec  jmp     loc_18000BA9D
0x18000b9f1  lea     r8, asc_180042618; "h"
0x18000b9f8  mov     rdx, r14; unsigned __int64
0x18000b9fb  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000ba00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ba05  lea     r8, [rsp+280h+pszDest]; lpName
0x18000ba0a  xor     edx, edx; bInheritHandle
0x18000ba0c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ba11  call    cs:__imp_OpenSemaphoreW
0x18000ba18  nop     dword ptr [rax+rax+00h]
0x18000ba1d  mov     [rsp+280h+var_248], rax
0x18000ba22  test    rax, rax
0x18000ba25  jnz     short loc_18000BA4D
0x18000ba27  mov     rcx, [rbp+188h]; this
0x18000ba2e  lea     r8, aWil; "wil"
0x18000ba35  mov     edx, 0DCh; void *
0x18000ba3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ba3f  mov     ebx, eax
0x18000ba41  lea     rcx, [rsp+280h+var_248]
0x18000ba46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ba4b  jmp     short loc_18000BA9D
0x18000ba4d  lea     rdx, [rsp+280h+var_250]; int *
0x18000ba52  mov     rcx, rax; hHandle
0x18000ba55  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ba5a  mov     ebx, eax
0x18000ba5c  test    eax, eax
0x18000ba5e  jns     short loc_18000BA7D
0x18000ba60  mov     rcx, [rbp+188h]; this
0x18000ba67  lea     r8, aWil; "wil"
0x18000ba6e  mov     r9d, eax; char *
0x18000ba71  mov     edx, 0DEh; void *
0x18000ba76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba7b  jmp     short loc_18000BA41
0x18000ba7d  lea     rcx, [rsp+280h+var_248]
0x18000ba82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ba87  movsxd  rcx, [rsp+280h+var_250]
0x18000ba8c  movsxd  rax, [rsp+280h+var_24C]
0x18000ba91  shl     rcx, 1Fh
0x18000ba95  or      rcx, rax
0x18000ba98  mov     [rdi], rcx
0x18000ba9b  xor     ebx, ebx
0x18000ba9d  lea     rcx, [rsp+280h+var_240]
0x18000baa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000baa7  mov     eax, ebx
0x18000baa9  mov     rcx, [rbp+180h+var_20]
0x18000bab0  xor     rcx, rsp; StackCookie
0x18000bab3  call    __security_check_cookie
0x18000bab8  mov     rbx, [rsp+280h+arg_8]
0x18000bac0  add     rsp, 270h
0x18000bac7  pop     r14
0x18000bac9  pop     rdi
0x18000baca  pop     rbp
0x18000bacb  retn
```
