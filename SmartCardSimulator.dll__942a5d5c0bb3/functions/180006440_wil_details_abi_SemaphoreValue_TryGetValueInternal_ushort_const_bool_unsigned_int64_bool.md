# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006440`
- end: `0x1800065dc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004488`

## callees

- `0x18000438c`
- `0x18000506c`
- `0x180005d54`
- `0x180005d74`
- `0x18000624c`
- `0x18000632c`
- `0x180006440`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006534`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b4`

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
0x180006440  mov     [rsp-8+arg_8], rbx
0x180006445  mov     [rsp-8+arg_18], rdi
0x18000644a  push    rbp
0x18000644b  lea     rbp, [rsp-170h]
0x180006453  sub     rsp, 270h
0x18000645a  mov     rax, cs:__security_cookie
0x180006461  xor     rax, rsp
0x180006464  mov     [rbp+170h+var_10], rax
0x18000646b  mov     r9, rcx; pszSrc
0x18000646e  mov     qword ptr [r8], 0
0x180006475  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000647a  mov     edx, 104h; cchDest
0x18000647f  mov     rdi, r8
0x180006482  call    StringCopyWorkerW
0x180006487  lea     r8, aP0; "_p0"
0x18000648e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006493  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006498  lea     r8, [rsp+270h+pszDest]; lpName
0x18000649d  xor     edx, edx; bInheritHandle
0x18000649f  mov     ecx, 1F0003h; dwDesiredAccess
0x1800064a4  call    cs:__imp_OpenSemaphoreW
0x1800064aa  mov     [rsp+270h+var_230], rax
0x1800064af  test    rax, rax
0x1800064b2  jnz     short loc_1800064DB
0x1800064b4  call    cs:__imp_GetLastError
0x1800064ba  cmp     eax, 2
0x1800064bd  jz      loc_1800065AA
0x1800064c3  mov     rcx, [rbp+178h]; this
0x1800064ca  mov     edx, 0D0h; void *
0x1800064cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800064d4  mov     ebx, eax
0x1800064d6  jmp     loc_1800065AC
0x1800064db  lea     rdx, [rsp+270h+var_23C]; int *
0x1800064e0  mov     [rsp+270h+var_23C], 0
0x1800064e8  mov     rcx, rax; hHandle
0x1800064eb  mov     [rsp+270h+var_240], 0
0x1800064f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800064f8  mov     ebx, eax
0x1800064fa  test    eax, eax
0x1800064fc  jns     short loc_180006517
0x1800064fe  mov     rcx, [rbp+178h]; this
0x180006505  mov     r9d, eax; char *
0x180006508  mov     edx, 0D6h; void *
0x18000650d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006512  jmp     loc_1800065AC
0x180006517  lea     r8, asc_180063708; "h"
0x18000651e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006523  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006528  lea     r8, [rsp+270h+pszDest]; lpName
0x18000652d  xor     edx, edx; bInheritHandle
0x18000652f  mov     ecx, 1F0003h; dwDesiredAccess
0x180006534  call    cs:__imp_OpenSemaphoreW
0x18000653a  mov     [rsp+270h+var_238], rax
0x18000653f  test    rax, rax
0x180006542  jnz     short loc_180006563
0x180006544  mov     rcx, [rbp+178h]; this
0x18000654b  mov     edx, 0DCh; void *
0x180006550  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006555  mov     ebx, eax
0x180006557  lea     rcx, [rsp+270h+var_238]
0x18000655c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006561  jmp     short loc_1800065AC
0x180006563  lea     rdx, [rsp+270h+var_240]; int *
0x180006568  mov     rcx, rax; hHandle
0x18000656b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006570  mov     ebx, eax
0x180006572  test    eax, eax
0x180006574  jns     short loc_18000658C
0x180006576  mov     rcx, [rbp+178h]; this
0x18000657d  mov     r9d, eax; char *
0x180006580  mov     edx, 0DEh; void *
0x180006585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000658a  jmp     short loc_180006557
0x18000658c  lea     rcx, [rsp+270h+var_238]
0x180006591  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006596  movsxd  rcx, [rsp+270h+var_240]
0x18000659b  movsxd  rax, [rsp+270h+var_23C]
0x1800065a0  shl     rcx, 1Fh
0x1800065a4  or      rcx, rax
0x1800065a7  mov     [rdi], rcx
0x1800065aa  xor     ebx, ebx
0x1800065ac  lea     rcx, [rsp+270h+var_230]
0x1800065b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800065b6  mov     eax, ebx
0x1800065b8  mov     rcx, [rbp+170h+var_10]
0x1800065bf  xor     rcx, rsp; StackCookie
0x1800065c2  call    __security_check_cookie
0x1800065c7  lea     r11, [rsp+270h+var_s0]
0x1800065cf  mov     rbx, [r11+18h]
0x1800065d3  mov     rdi, [r11+28h]
0x1800065d7  mov     rsp, r11
0x1800065da  pop     rbp
0x1800065db  retn
```
