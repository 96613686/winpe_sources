# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006728`
- end: `0x1800068d8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800047b8`

## callees

- `0x180002420`
- `0x180004624`
- `0x18000534c`
- `0x180005ff4`
- `0x180006014`
- `0x1800064ec`
- `0x180006624`
- `0x180006728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006791`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000682a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006791`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000682a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067a1`

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
0x180006728  mov     [rsp-8+arg_8], rbx
0x18000672d  push    rbp
0x18000672e  push    rdi
0x18000672f  push    r14
0x180006731  lea     rbp, [rsp-170h]
0x180006739  sub     rsp, 270h
0x180006740  mov     rax, cs:__security_cookie
0x180006747  xor     rax, rsp
0x18000674a  mov     [rbp+180h+var_20], rax
0x180006751  mov     r9, rcx; pszSrc
0x180006754  mov     qword ptr [r8], 0
0x18000675b  mov     r14d, 104h
0x180006761  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180006766  mov     edx, r14d; cchDest
0x180006769  mov     rdi, r8
0x18000676c  call    StringCopyWorkerW
0x180006771  lea     r8, aP0; "_p0"
0x180006778  mov     edx, r14d; unsigned __int64
0x18000677b  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180006780  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006785  lea     r8, [rsp+280h+pszDest]; lpName
0x18000678a  xor     edx, edx; bInheritHandle
0x18000678c  mov     ecx, 1F0003h; dwDesiredAccess
0x180006791  call    cs:__imp_OpenSemaphoreW
0x180006797  mov     [rsp+280h+var_240], rax
0x18000679c  test    rax, rax
0x18000679f  jnz     short loc_1800067C7
0x1800067a1  call    cs:__imp_GetLastError
0x1800067a7  cmp     eax, 2
0x1800067aa  jz      loc_1800068A7
0x1800067b0  mov     rcx, [rbp+188h]; this
0x1800067b7  lea     edx, [r14-34h]; void *
0x1800067bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067c0  mov     ebx, eax
0x1800067c2  jmp     loc_1800068A9
0x1800067c7  lea     rdx, [rsp+280h+var_24C]; int *
0x1800067cc  mov     [rsp+280h+var_24C], 0
0x1800067d4  mov     rcx, rax; hHandle
0x1800067d7  mov     [rsp+280h+var_250], 0
0x1800067df  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800067e4  mov     ebx, eax
0x1800067e6  test    eax, eax
0x1800067e8  jns     short loc_18000680A
0x1800067ea  mov     rcx, [rbp+188h]; this
0x1800067f1  lea     r8, aWil; "wil"
0x1800067f8  mov     r9d, eax; char *
0x1800067fb  mov     edx, 0D6h; void *
0x180006800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006805  jmp     loc_1800068A9
0x18000680a  lea     r8, asc_18014B050; "h"
0x180006811  mov     rdx, r14; unsigned __int64
0x180006814  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180006819  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000681e  lea     r8, [rsp+280h+pszDest]; lpName
0x180006823  xor     edx, edx; bInheritHandle
0x180006825  mov     ecx, 1F0003h; dwDesiredAccess
0x18000682a  call    cs:__imp_OpenSemaphoreW
0x180006830  mov     [rsp+280h+var_248], rax
0x180006835  test    rax, rax
0x180006838  jnz     short loc_180006859
0x18000683a  mov     rcx, [rbp+188h]; this
0x180006841  mov     edx, 0DCh; void *
0x180006846  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000684b  mov     ebx, eax
0x18000684d  lea     rcx, [rsp+280h+var_248]
0x180006852  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006857  jmp     short loc_1800068A9
0x180006859  lea     rdx, [rsp+280h+var_250]; int *
0x18000685e  mov     rcx, rax; hHandle
0x180006861  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006866  mov     ebx, eax
0x180006868  test    eax, eax
0x18000686a  jns     short loc_180006889
0x18000686c  mov     rcx, [rbp+188h]; this
0x180006873  lea     r8, aWil; "wil"
0x18000687a  mov     r9d, eax; char *
0x18000687d  mov     edx, 0DEh; void *
0x180006882  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006887  jmp     short loc_18000684D
0x180006889  lea     rcx, [rsp+280h+var_248]
0x18000688e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006893  movsxd  rcx, [rsp+280h+var_250]
0x180006898  movsxd  rax, [rsp+280h+var_24C]
0x18000689d  shl     rcx, 1Fh
0x1800068a1  or      rcx, rax
0x1800068a4  mov     [rdi], rcx
0x1800068a7  xor     ebx, ebx
0x1800068a9  lea     rcx, [rsp+280h+var_240]
0x1800068ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068b3  mov     eax, ebx
0x1800068b5  mov     rcx, [rbp+180h+var_20]
0x1800068bc  xor     rcx, rsp; StackCookie
0x1800068bf  call    __security_check_cookie
0x1800068c4  mov     rbx, [rsp+280h+arg_8]
0x1800068cc  add     rsp, 270h
0x1800068d3  pop     r14
0x1800068d5  pop     rdi
0x1800068d6  pop     rbp
0x1800068d7  retn
```
