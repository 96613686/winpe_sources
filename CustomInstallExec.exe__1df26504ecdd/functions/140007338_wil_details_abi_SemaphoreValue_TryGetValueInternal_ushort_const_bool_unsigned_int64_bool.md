# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007338`
- end: `0x1400074f0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005508`

## callees

- `0x1400033b0`
- `0x1400053c0`
- `0x140006018`
- `0x140006c04`
- `0x140006c24`
- `0x1400070fc`
- `0x140007224`
- `0x140007338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000739c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000743a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000739c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000743a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073ac`

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
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
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
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140007338  mov     [rsp-8+arg_8], rbx
0x14000733d  mov     [rsp-8+arg_18], rdi
0x140007342  push    rbp
0x140007343  lea     rbp, [rsp-170h]
0x14000734b  sub     rsp, 270h
0x140007352  mov     rax, cs:__security_cookie
0x140007359  xor     rax, rsp
0x14000735c  mov     [rbp+170h+var_10], rax
0x140007363  mov     r9, rcx; pszSrc
0x140007366  mov     qword ptr [r8], 0
0x14000736d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140007372  mov     edx, 104h; cchDest
0x140007377  mov     rdi, r8
0x14000737a  call    StringCopyWorkerW
0x14000737f  lea     r8, aP0; "_p0"
0x140007386  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000738b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007390  lea     r8, [rsp+270h+pszDest]; lpName
0x140007395  xor     edx, edx; bInheritHandle
0x140007397  mov     ecx, 1F0003h; dwDesiredAccess
0x14000739c  call    cs:__imp_OpenSemaphoreW
0x1400073a2  mov     [rsp+270h+var_230], rax
0x1400073a7  test    rax, rax
0x1400073aa  jnz     short loc_1400073DA
0x1400073ac  call    cs:__imp_GetLastError
0x1400073b2  cmp     eax, 2
0x1400073b5  jz      loc_1400074BE
0x1400073bb  mov     rcx, [rbp+178h]; this
0x1400073c2  lea     r8, aWil; "wil"
0x1400073c9  mov     edx, 0D0h; void *
0x1400073ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400073d3  mov     ebx, eax
0x1400073d5  jmp     loc_1400074C0
0x1400073da  lea     rdx, [rsp+270h+var_23C]; int *
0x1400073df  mov     [rsp+270h+var_23C], 0
0x1400073e7  mov     rcx, rax; hHandle
0x1400073ea  mov     [rsp+270h+var_240], 0
0x1400073f2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400073f7  mov     ebx, eax
0x1400073f9  test    eax, eax
0x1400073fb  jns     short loc_14000741D
0x1400073fd  mov     rcx, [rbp+178h]; this
0x140007404  lea     r8, aWil; "wil"
0x14000740b  mov     r9d, eax; char *
0x14000740e  mov     edx, 0D6h; void *
0x140007413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007418  jmp     loc_1400074C0
0x14000741d  lea     r8, asc_140010FF8; "h"
0x140007424  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140007429  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000742e  lea     r8, [rsp+270h+pszDest]; lpName
0x140007433  xor     edx, edx; bInheritHandle
0x140007435  mov     ecx, 1F0003h; dwDesiredAccess
0x14000743a  call    cs:__imp_OpenSemaphoreW
0x140007440  mov     [rsp+270h+var_238], rax
0x140007445  test    rax, rax
0x140007448  jnz     short loc_140007470
0x14000744a  mov     rcx, [rbp+178h]; this
0x140007451  lea     r8, aWil; "wil"
0x140007458  mov     edx, 0DCh; void *
0x14000745d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007462  mov     ebx, eax
0x140007464  lea     rcx, [rsp+270h+var_238]
0x140007469  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000746e  jmp     short loc_1400074C0
0x140007470  lea     rdx, [rsp+270h+var_240]; int *
0x140007475  mov     rcx, rax; hHandle
0x140007478  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000747d  mov     ebx, eax
0x14000747f  test    eax, eax
0x140007481  jns     short loc_1400074A0
0x140007483  mov     rcx, [rbp+178h]; this
0x14000748a  lea     r8, aWil; "wil"
0x140007491  mov     r9d, eax; char *
0x140007494  mov     edx, 0DEh; void *
0x140007499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000749e  jmp     short loc_140007464
0x1400074a0  lea     rcx, [rsp+270h+var_238]
0x1400074a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400074aa  movsxd  rcx, [rsp+270h+var_240]
0x1400074af  movsxd  rax, [rsp+270h+var_23C]
0x1400074b4  shl     rcx, 1Fh
0x1400074b8  or      rcx, rax
0x1400074bb  mov     [rdi], rcx
0x1400074be  xor     ebx, ebx
0x1400074c0  lea     rcx, [rsp+270h+var_230]
0x1400074c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400074ca  mov     eax, ebx
0x1400074cc  mov     rcx, [rbp+170h+var_10]
0x1400074d3  xor     rcx, rsp; StackCookie
0x1400074d6  call    __security_check_cookie
0x1400074db  lea     r11, [rsp+270h+var_s0]
0x1400074e3  mov     rbx, [r11+18h]
0x1400074e7  mov     rdi, [r11+28h]
0x1400074eb  mov     rsp, r11
0x1400074ee  pop     rbp
0x1400074ef  retn
```
