# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d3cc`
- end: `0x18000d584`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d348`

## callees

- `0x180003a60`
- `0x180007520`
- `0x180009bb4`
- `0x18000c4ac`
- `0x18000c4cc`
- `0x18000ccc0`
- `0x18000cde8`
- `0x18000d3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d430`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d4ce`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d430`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d4ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d440`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
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
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18000d3cc  mov     [rsp-8+arg_8], rbx
0x18000d3d1  mov     [rsp-8+arg_18], rdi
0x18000d3d6  push    rbp
0x18000d3d7  lea     rbp, [rsp-170h]
0x18000d3df  sub     rsp, 270h
0x18000d3e6  mov     rax, cs:__security_cookie
0x18000d3ed  xor     rax, rsp
0x18000d3f0  mov     [rbp+170h+var_10], rax
0x18000d3f7  mov     r9, rcx; pszSrc
0x18000d3fa  mov     qword ptr [r8], 0
0x18000d401  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000d406  mov     edx, 104h; cchDest
0x18000d40b  mov     rdi, r8
0x18000d40e  call    StringCopyWorkerW
0x18000d413  lea     r8, aP0; "_p0"
0x18000d41a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000d41f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d424  lea     r8, [rsp+270h+pszDest]; lpName
0x18000d429  xor     edx, edx; bInheritHandle
0x18000d42b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d430  call    cs:__imp_OpenSemaphoreW
0x18000d436  mov     [rsp+270h+var_230], rax
0x18000d43b  test    rax, rax
0x18000d43e  jnz     short loc_18000D46E
0x18000d440  call    cs:__imp_GetLastError
0x18000d446  cmp     eax, 2
0x18000d449  jz      loc_18000D552
0x18000d44f  mov     rcx, [rbp+178h]; this
0x18000d456  lea     r8, aWil; "wil"
0x18000d45d  mov     edx, 0D0h; void *
0x18000d462  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d467  mov     ebx, eax
0x18000d469  jmp     loc_18000D554
0x18000d46e  lea     rdx, [rsp+270h+var_23C]; int *
0x18000d473  mov     [rsp+270h+var_23C], 0
0x18000d47b  mov     rcx, rax; hHandle
0x18000d47e  mov     [rsp+270h+var_240], 0
0x18000d486  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d48b  mov     ebx, eax
0x18000d48d  test    eax, eax
0x18000d48f  jns     short loc_18000D4B1
0x18000d491  mov     rcx, [rbp+178h]; this
0x18000d498  lea     r8, aWil; "wil"
0x18000d49f  mov     r9d, eax; char *
0x18000d4a2  mov     edx, 0D6h; void *
0x18000d4a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4ac  jmp     loc_18000D554
0x18000d4b1  lea     r8, asc_18002E218; "h"
0x18000d4b8  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000d4bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d4c2  lea     r8, [rsp+270h+pszDest]; lpName
0x18000d4c7  xor     edx, edx; bInheritHandle
0x18000d4c9  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d4ce  call    cs:__imp_OpenSemaphoreW
0x18000d4d4  mov     [rsp+270h+var_238], rax
0x18000d4d9  test    rax, rax
0x18000d4dc  jnz     short loc_18000D504
0x18000d4de  mov     rcx, [rbp+178h]; this
0x18000d4e5  lea     r8, aWil; "wil"
0x18000d4ec  mov     edx, 0DCh; void *
0x18000d4f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d4f6  mov     ebx, eax
0x18000d4f8  lea     rcx, [rsp+270h+var_238]
0x18000d4fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d502  jmp     short loc_18000D554
0x18000d504  lea     rdx, [rsp+270h+var_240]; int *
0x18000d509  mov     rcx, rax; hHandle
0x18000d50c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d511  mov     ebx, eax
0x18000d513  test    eax, eax
0x18000d515  jns     short loc_18000D534
0x18000d517  mov     rcx, [rbp+178h]; this
0x18000d51e  lea     r8, aWil; "wil"
0x18000d525  mov     r9d, eax; char *
0x18000d528  mov     edx, 0DEh; void *
0x18000d52d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d532  jmp     short loc_18000D4F8
0x18000d534  lea     rcx, [rsp+270h+var_238]
0x18000d539  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d53e  movsxd  rcx, [rsp+270h+var_240]
0x18000d543  movsxd  rax, [rsp+270h+var_23C]
0x18000d548  shl     rcx, 1Fh
0x18000d54c  or      rcx, rax
0x18000d54f  mov     [rdi], rcx
0x18000d552  xor     ebx, ebx
0x18000d554  lea     rcx, [rsp+270h+var_230]
0x18000d559  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d55e  mov     eax, ebx
0x18000d560  mov     rcx, [rbp+170h+var_10]
0x18000d567  xor     rcx, rsp; StackCookie
0x18000d56a  call    __security_check_cookie
0x18000d56f  lea     r11, [rsp+270h+var_s0]
0x18000d577  mov     rbx, [r11+18h]
0x18000d57b  mov     rdi, [r11+28h]
0x18000d57f  mov     rsp, r11
0x18000d582  pop     rbp
0x18000d583  retn
```
