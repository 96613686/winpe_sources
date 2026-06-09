# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005440`
- end: `0x1400055ea`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140003440`

## callees

- `0x14000330c`
- `0x14000402c`
- `0x140004d54`
- `0x140004d74`
- `0x14000524c`
- `0x14000532c`
- `0x140005440`
- `0x1400094d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400054a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000553b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400054a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000553b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400054b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400054b4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  wil::details *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  size_t v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v20);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24 = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v23,
          v18);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v23,
      v16);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v24,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140005440  mov     [rsp-8+arg_8], rbx
0x140005445  mov     [rsp-8+arg_18], rdi
0x14000544a  push    rbp
0x14000544b  lea     rbp, [rsp-170h]
0x140005453  sub     rsp, 270h
0x14000545a  mov     rax, cs:__security_cookie
0x140005461  xor     rax, rsp
0x140005464  mov     [rbp+170h+var_10], rax
0x14000546b  mov     r9, rcx; pszSrc
0x14000546e  mov     qword ptr [r8], 0
0x140005475  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14000547a  mov     edx, 104h; cchDest
0x14000547f  mov     rdi, r8
0x140005482  call    StringCopyWorkerW
0x140005487  lea     r8, aP0; "_p0"
0x14000548e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140005493  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005498  lea     r8, [rsp+270h+pszDest]; lpName
0x14000549d  xor     edx, edx; bInheritHandle
0x14000549f  mov     ecx, 1F0003h; dwDesiredAccess
0x1400054a4  call    cs:__imp_OpenSemaphoreW
0x1400054aa  mov     [rsp+270h+var_230], rax
0x1400054af  test    rax, rax
0x1400054b2  jnz     short loc_1400054DB
0x1400054b4  call    cs:__imp_GetLastError
0x1400054ba  cmp     eax, 2
0x1400054bd  jz      loc_1400055B8
0x1400054c3  mov     rcx, [rbp+178h]; this
0x1400054ca  mov     edx, 0D0h; void *
0x1400054cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400054d4  mov     ebx, eax
0x1400054d6  jmp     loc_1400055BA
0x1400054db  lea     rdx, [rsp+270h+var_23C]; int *
0x1400054e0  mov     [rsp+270h+var_23C], 0
0x1400054e8  mov     rcx, rax; hHandle
0x1400054eb  mov     [rsp+270h+var_240], 0
0x1400054f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400054f8  mov     ebx, eax
0x1400054fa  test    eax, eax
0x1400054fc  jns     short loc_14000551E
0x1400054fe  mov     rcx, [rbp+178h]; this
0x140005505  lea     r8, aWil; "wil"
0x14000550c  mov     r9d, eax; char *
0x14000550f  mov     edx, 0D6h; void *
0x140005514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005519  jmp     loc_1400055BA
0x14000551e  lea     r8, asc_14000D3F8; "h"
0x140005525  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000552a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000552f  lea     r8, [rsp+270h+pszDest]; lpName
0x140005534  xor     edx, edx; bInheritHandle
0x140005536  mov     ecx, 1F0003h; dwDesiredAccess
0x14000553b  call    cs:__imp_OpenSemaphoreW
0x140005541  mov     [rsp+270h+var_238], rax
0x140005546  test    rax, rax
0x140005549  jnz     short loc_14000556A
0x14000554b  mov     rcx, [rbp+178h]; this
0x140005552  mov     edx, 0DCh; void *
0x140005557  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000555c  mov     ebx, eax
0x14000555e  lea     rcx, [rsp+270h+var_238]
0x140005563  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005568  jmp     short loc_1400055BA
0x14000556a  lea     rdx, [rsp+270h+var_240]; int *
0x14000556f  mov     rcx, rax; hHandle
0x140005572  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005577  mov     ebx, eax
0x140005579  test    eax, eax
0x14000557b  jns     short loc_14000559A
0x14000557d  mov     rcx, [rbp+178h]; this
0x140005584  lea     r8, aWil; "wil"
0x14000558b  mov     r9d, eax; char *
0x14000558e  mov     edx, 0DEh; void *
0x140005593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005598  jmp     short loc_14000555E
0x14000559a  lea     rcx, [rsp+270h+var_238]
0x14000559f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400055a4  movsxd  rcx, [rsp+270h+var_240]
0x1400055a9  movsxd  rax, [rsp+270h+var_23C]
0x1400055ae  shl     rcx, 1Fh
0x1400055b2  or      rcx, rax
0x1400055b5  mov     [rdi], rcx
0x1400055b8  xor     ebx, ebx
0x1400055ba  lea     rcx, [rsp+270h+var_230]
0x1400055bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400055c4  mov     eax, ebx
0x1400055c6  mov     rcx, [rbp+170h+var_10]
0x1400055cd  xor     rcx, rsp; StackCookie
0x1400055d0  call    __security_check_cookie
0x1400055d5  lea     r11, [rsp+270h+var_s0]
0x1400055dd  mov     rbx, [r11+18h]
0x1400055e1  mov     rdi, [r11+28h]
0x1400055e5  mov     rsp, r11
0x1400055e8  pop     rbp
0x1400055e9  retn
```
