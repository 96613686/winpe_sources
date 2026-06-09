# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011058`
- end: `0x1800111f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f0a4`

## callees

- `0x18000d090`
- `0x18000ef38`
- `0x18000fc8c`
- `0x180010974`
- `0x180010994`
- `0x180010e6c`
- `0x180010f4c`
- `0x180011058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800110bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001114c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800110bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001114c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110cc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x180011058  mov     [rsp-8+arg_8], rbx
0x18001105d  mov     [rsp-8+arg_18], rdi
0x180011062  push    rbp
0x180011063  lea     rbp, [rsp-170h]
0x18001106b  sub     rsp, 270h
0x180011072  mov     rax, cs:__security_cookie
0x180011079  xor     rax, rsp
0x18001107c  mov     [rbp+170h+var_10], rax
0x180011083  mov     r9, rcx; pszSrc
0x180011086  mov     qword ptr [r8], 0
0x18001108d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180011092  mov     edx, 104h; cchDest
0x180011097  mov     rdi, r8
0x18001109a  call    StringCopyWorkerW
0x18001109f  lea     r8, aP0; "_p0"
0x1800110a6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800110ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800110b0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800110b5  xor     edx, edx; bInheritHandle
0x1800110b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800110bc  call    cs:__imp_OpenSemaphoreW
0x1800110c2  mov     [rsp+270h+var_230], rax
0x1800110c7  test    rax, rax
0x1800110ca  jnz     short loc_1800110F3
0x1800110cc  call    cs:__imp_GetLastError
0x1800110d2  cmp     eax, 2
0x1800110d5  jz      loc_1800111C2
0x1800110db  mov     rcx, [rbp+178h]; this
0x1800110e2  mov     edx, 0D0h; void *
0x1800110e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800110ec  mov     ebx, eax
0x1800110ee  jmp     loc_1800111C4
0x1800110f3  lea     rdx, [rsp+270h+var_23C]; int *
0x1800110f8  mov     [rsp+270h+var_23C], 0
0x180011100  mov     rcx, rax; hHandle
0x180011103  mov     [rsp+270h+var_240], 0
0x18001110b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011110  mov     ebx, eax
0x180011112  test    eax, eax
0x180011114  jns     short loc_18001112F
0x180011116  mov     rcx, [rbp+178h]; this
0x18001111d  mov     r9d, eax; char *
0x180011120  mov     edx, 0D6h; void *
0x180011125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001112a  jmp     loc_1800111C4
0x18001112f  lea     r8, asc_1800A0A08; "h"
0x180011136  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001113b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011140  lea     r8, [rsp+270h+pszDest]; lpName
0x180011145  xor     edx, edx; bInheritHandle
0x180011147  mov     ecx, 1F0003h; dwDesiredAccess
0x18001114c  call    cs:__imp_OpenSemaphoreW
0x180011152  mov     [rsp+270h+var_238], rax
0x180011157  test    rax, rax
0x18001115a  jnz     short loc_18001117B
0x18001115c  mov     rcx, [rbp+178h]; this
0x180011163  mov     edx, 0DCh; void *
0x180011168  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001116d  mov     ebx, eax
0x18001116f  lea     rcx, [rsp+270h+var_238]
0x180011174  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011179  jmp     short loc_1800111C4
0x18001117b  lea     rdx, [rsp+270h+var_240]; int *
0x180011180  mov     rcx, rax; hHandle
0x180011183  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011188  mov     ebx, eax
0x18001118a  test    eax, eax
0x18001118c  jns     short loc_1800111A4
0x18001118e  mov     rcx, [rbp+178h]; this
0x180011195  mov     r9d, eax; char *
0x180011198  mov     edx, 0DEh; void *
0x18001119d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111a2  jmp     short loc_18001116F
0x1800111a4  lea     rcx, [rsp+270h+var_238]
0x1800111a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800111ae  movsxd  rcx, [rsp+270h+var_240]
0x1800111b3  movsxd  rax, [rsp+270h+var_23C]
0x1800111b8  shl     rcx, 1Fh
0x1800111bc  or      rcx, rax
0x1800111bf  mov     [rdi], rcx
0x1800111c2  xor     ebx, ebx
0x1800111c4  lea     rcx, [rsp+270h+var_230]
0x1800111c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800111ce  mov     eax, ebx
0x1800111d0  mov     rcx, [rbp+170h+var_10]
0x1800111d7  xor     rcx, rsp; StackCookie
0x1800111da  call    __security_check_cookie
0x1800111df  lea     r11, [rsp+270h+var_s0]
0x1800111e7  mov     rbx, [r11+18h]
0x1800111eb  mov     rdi, [r11+28h]
0x1800111ef  mov     rsp, r11
0x1800111f2  pop     rbp
0x1800111f3  retn
```
