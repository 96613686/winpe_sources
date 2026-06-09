# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004694`
- end: `0x140004830`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400029f4`

## callees

- `0x140001600`
- `0x140002974`
- `0x1400035dc`
- `0x1400040d8`
- `0x1400040f8`
- `0x140004508`
- `0x1400045e8`
- `0x140004694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400046f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004788`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400046f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004708`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v22);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v6;
  if ( v6 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v25 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v25,
          v19);
        *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v25,
      v17);
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
    &v26,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140004694  mov     [rsp-8+arg_8], rbx
0x140004699  mov     [rsp-8+arg_18], rdi
0x14000469e  push    rbp
0x14000469f  lea     rbp, [rsp-170h]
0x1400046a7  sub     rsp, 270h
0x1400046ae  mov     rax, cs:__security_cookie
0x1400046b5  xor     rax, rsp
0x1400046b8  mov     [rbp+170h+var_10], rax
0x1400046bf  mov     r9, rcx; pszSrc
0x1400046c2  mov     qword ptr [r8], 0
0x1400046c9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1400046ce  mov     edx, 104h; cchDest
0x1400046d3  mov     rdi, r8
0x1400046d6  call    StringCopyWorkerW
0x1400046db  lea     r8, aP0; "_p0"
0x1400046e2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1400046e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400046ec  lea     r8, [rsp+270h+pszDest]; lpName
0x1400046f1  xor     edx, edx; bInheritHandle
0x1400046f3  mov     ecx, 1F0003h; dwDesiredAccess
0x1400046f8  call    cs:__imp_OpenSemaphoreW
0x1400046fe  mov     [rsp+270h+var_230], rax
0x140004703  test    rax, rax
0x140004706  jnz     short loc_14000472F
0x140004708  call    cs:__imp_GetLastError
0x14000470e  cmp     eax, 2
0x140004711  jz      loc_1400047FE
0x140004717  mov     rcx, [rbp+178h]; this
0x14000471e  mov     edx, 0D0h; void *
0x140004723  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004728  mov     ebx, eax
0x14000472a  jmp     loc_140004800
0x14000472f  lea     rdx, [rsp+270h+var_23C]; int *
0x140004734  mov     [rsp+270h+var_23C], 0
0x14000473c  mov     rcx, rax; hHandle
0x14000473f  mov     [rsp+270h+var_240], 0
0x140004747  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000474c  mov     ebx, eax
0x14000474e  test    eax, eax
0x140004750  jns     short loc_14000476B
0x140004752  mov     rcx, [rbp+178h]; this
0x140004759  mov     r9d, eax; char *
0x14000475c  mov     edx, 0D6h; void *
0x140004761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004766  jmp     loc_140004800
0x14000476b  lea     r8, asc_140008848; "h"
0x140004772  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140004777  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000477c  lea     r8, [rsp+270h+pszDest]; lpName
0x140004781  xor     edx, edx; bInheritHandle
0x140004783  mov     ecx, 1F0003h; dwDesiredAccess
0x140004788  call    cs:__imp_OpenSemaphoreW
0x14000478e  mov     [rsp+270h+var_238], rax
0x140004793  test    rax, rax
0x140004796  jnz     short loc_1400047B7
0x140004798  mov     rcx, [rbp+178h]; this
0x14000479f  mov     edx, 0DCh; void *
0x1400047a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400047a9  mov     ebx, eax
0x1400047ab  lea     rcx, [rsp+270h+var_238]
0x1400047b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400047b5  jmp     short loc_140004800
0x1400047b7  lea     rdx, [rsp+270h+var_240]; int *
0x1400047bc  mov     rcx, rax; hHandle
0x1400047bf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400047c4  mov     ebx, eax
0x1400047c6  test    eax, eax
0x1400047c8  jns     short loc_1400047E0
0x1400047ca  mov     rcx, [rbp+178h]; this
0x1400047d1  mov     r9d, eax; char *
0x1400047d4  mov     edx, 0DEh; void *
0x1400047d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400047de  jmp     short loc_1400047AB
0x1400047e0  lea     rcx, [rsp+270h+var_238]
0x1400047e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400047ea  movsxd  rcx, [rsp+270h+var_240]
0x1400047ef  movsxd  rax, [rsp+270h+var_23C]
0x1400047f4  shl     rcx, 1Fh
0x1400047f8  or      rcx, rax
0x1400047fb  mov     [rdi], rcx
0x1400047fe  xor     ebx, ebx
0x140004800  lea     rcx, [rsp+270h+var_230]
0x140004805  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000480a  mov     eax, ebx
0x14000480c  mov     rcx, [rbp+170h+var_10]
0x140004813  xor     rcx, rsp; StackCookie
0x140004816  call    __security_check_cookie
0x14000481b  lea     r11, [rsp+270h+var_s0]
0x140004823  mov     rbx, [r11+18h]
0x140004827  mov     rdi, [r11+28h]
0x14000482b  mov     rsp, r11
0x14000482e  pop     rbp
0x14000482f  retn
```
