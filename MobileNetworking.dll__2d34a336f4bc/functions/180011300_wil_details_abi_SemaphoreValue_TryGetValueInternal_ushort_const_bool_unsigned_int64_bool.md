# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011300`
- end: `0x1800114a2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000fc40`

## callees

- `0x1800065f0`
- `0x180006630`
- `0x180009850`
- `0x18000fbe0`
- `0x180010684`
- `0x180010ec8`
- `0x180010ee8`
- `0x180011300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011379`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011369`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800113fb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011369`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800113fb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, (size_t *)L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, (size_t *)L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v12;
    if ( v12 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v17);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180011300  mov     [rsp-8+arg_8], rbx
0x180011305  push    rbp
0x180011306  push    rdi
0x180011307  push    r14
0x180011309  lea     rbp, [rsp-160h]
0x180011311  sub     rsp, 260h
0x180011318  mov     rax, cs:__security_cookie
0x18001131f  xor     rax, rsp
0x180011322  mov     [rbp+170h+var_20], rax
0x180011329  mov     rdi, r8
0x18001132c  mov     qword ptr [r8], 0
0x180011333  mov     r8, rcx; unsigned __int16 *
0x180011336  mov     r14d, 104h
0x18001133c  mov     edx, r14d; unsigned __int64
0x18001133f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011344  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011349  lea     r8, aP0; "_p0"
0x180011350  mov     edx, r14d; unsigned __int64
0x180011353  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011358  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001135d  lea     r8, [rsp+270h+Name]; lpName
0x180011362  xor     edx, edx; bInheritHandle
0x180011364  mov     ecx, 1F0003h; dwDesiredAccess
0x180011369  call    cs:__imp_OpenSemaphoreW
0x18001136f  mov     [rsp+270h+var_240], rax
0x180011374  test    rax, rax
0x180011377  jnz     short loc_18001139F
0x180011379  call    cs:__imp_GetLastError
0x18001137f  cmp     eax, 2
0x180011382  jz      loc_180011471
0x180011388  mov     rcx, [rbp+178h]; this
0x18001138f  lea     edx, [r14-34h]; void *
0x180011393  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011398  mov     ebx, eax
0x18001139a  jmp     loc_180011473
0x18001139f  lea     rdx, [rsp+270h+var_24C]; int *
0x1800113a4  mov     [rsp+270h+var_24C], 0
0x1800113ac  mov     rcx, rax; hHandle
0x1800113af  mov     [rsp+270h+var_250], 0; int
0x1800113b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800113bc  mov     ebx, eax
0x1800113be  test    eax, eax
0x1800113c0  jns     short loc_1800113DB
0x1800113c2  mov     rcx, [rbp+178h]; this
0x1800113c9  mov     r9d, eax; char *
0x1800113cc  mov     edx, 0D6h; void *
0x1800113d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113d6  jmp     loc_180011473
0x1800113db  lea     r8, asc_180015AB8; "h"
0x1800113e2  mov     rdx, r14; unsigned __int64
0x1800113e5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800113ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800113ef  lea     r8, [rsp+270h+Name]; lpName
0x1800113f4  xor     edx, edx; bInheritHandle
0x1800113f6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800113fb  call    cs:__imp_OpenSemaphoreW
0x180011401  mov     [rsp+270h+var_248], rax
0x180011406  test    rax, rax
0x180011409  jnz     short loc_18001142A
0x18001140b  mov     rcx, [rbp+178h]; this
0x180011412  mov     edx, 0DCh; void *
0x180011417  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001141c  mov     ebx, eax
0x18001141e  lea     rcx, [rsp+270h+var_248]
0x180011423  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011428  jmp     short loc_180011473
0x18001142a  lea     rdx, [rsp+270h+var_250]; int *
0x18001142f  mov     rcx, rax; hHandle
0x180011432  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011437  mov     ebx, eax
0x180011439  test    eax, eax
0x18001143b  jns     short loc_180011453
0x18001143d  mov     rcx, [rbp+178h]; this
0x180011444  mov     r9d, eax; char *
0x180011447  mov     edx, 0DEh; void *
0x18001144c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011451  jmp     short loc_18001141E
0x180011453  lea     rcx, [rsp+270h+var_248]
0x180011458  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001145d  movsxd  rcx, [rsp+270h+var_250]
0x180011462  movsxd  rax, [rsp+270h+var_24C]
0x180011467  shl     rcx, 1Fh
0x18001146b  or      rcx, rax
0x18001146e  mov     [rdi], rcx
0x180011471  xor     ebx, ebx
0x180011473  lea     rcx, [rsp+270h+var_240]
0x180011478  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001147d  mov     eax, ebx
0x18001147f  mov     rcx, [rbp+170h+var_20]
0x180011486  xor     rcx, rsp; StackCookie
0x180011489  call    __security_check_cookie
0x18001148e  mov     rbx, [rsp+270h+arg_8]
0x180011496  add     rsp, 260h
0x18001149d  pop     r14
0x18001149f  pop     rdi
0x1800114a0  pop     rbp
0x1800114a1  retn
```
