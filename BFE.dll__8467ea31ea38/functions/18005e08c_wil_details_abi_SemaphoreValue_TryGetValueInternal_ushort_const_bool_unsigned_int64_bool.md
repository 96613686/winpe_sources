# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18005e08c`
- end: `0x18005e244`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005e008`

## callees

- `0x1800545bc`
- `0x180058b30`
- `0x18005ac90`
- `0x18005c1a0`
- `0x18005d444`
- `0x18005db30`
- `0x18005dc24`
- `0x18005e08c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005e0f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005e18e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005e0f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005e18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e100`

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
  StringCopyWorkerW_0(pszDest, 0x104u, a3, pszSrc, v15);
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
0x18005e08c  mov     [rsp-8+arg_8], rbx
0x18005e091  mov     [rsp-8+arg_18], rdi
0x18005e096  push    rbp
0x18005e097  lea     rbp, [rsp-170h]
0x18005e09f  sub     rsp, 270h
0x18005e0a6  mov     rax, cs:__security_cookie
0x18005e0ad  xor     rax, rsp
0x18005e0b0  mov     [rbp+170h+var_10], rax
0x18005e0b7  mov     r9, rcx; pszSrc
0x18005e0ba  mov     qword ptr [r8], 0
0x18005e0c1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18005e0c6  mov     edx, 104h; cchDest
0x18005e0cb  mov     rdi, r8
0x18005e0ce  call    StringCopyWorkerW_0
0x18005e0d3  lea     r8, aP0; "_p0"
0x18005e0da  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005e0df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005e0e4  lea     r8, [rsp+270h+pszDest]; lpName
0x18005e0e9  xor     edx, edx; bInheritHandle
0x18005e0eb  mov     ecx, 1F0003h; dwDesiredAccess
0x18005e0f0  call    cs:__imp_OpenSemaphoreW
0x18005e0f6  mov     [rsp+270h+var_230], rax
0x18005e0fb  test    rax, rax
0x18005e0fe  jnz     short loc_18005E12E
0x18005e100  call    cs:__imp_GetLastError
0x18005e106  cmp     eax, 2
0x18005e109  jz      loc_18005E212
0x18005e10f  mov     rcx, [rbp+178h]; this
0x18005e116  lea     r8, aWil; "wil"
0x18005e11d  mov     edx, 0D0h; void *
0x18005e122  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e127  mov     ebx, eax
0x18005e129  jmp     loc_18005E214
0x18005e12e  lea     rdx, [rsp+270h+var_23C]; int *
0x18005e133  mov     [rsp+270h+var_23C], 0
0x18005e13b  mov     rcx, rax; hHandle
0x18005e13e  mov     [rsp+270h+var_240], 0
0x18005e146  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005e14b  mov     ebx, eax
0x18005e14d  test    eax, eax
0x18005e14f  jns     short loc_18005E171
0x18005e151  mov     rcx, [rbp+178h]; this
0x18005e158  lea     r8, aWil; "wil"
0x18005e15f  mov     r9d, eax; char *
0x18005e162  mov     edx, 0D6h; void *
0x18005e167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e16c  jmp     loc_18005E214
0x18005e171  lea     r8, asc_1800BF908; "h"
0x18005e178  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005e17d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005e182  lea     r8, [rsp+270h+pszDest]; lpName
0x18005e187  xor     edx, edx; bInheritHandle
0x18005e189  mov     ecx, 1F0003h; dwDesiredAccess
0x18005e18e  call    cs:__imp_OpenSemaphoreW
0x18005e194  mov     [rsp+270h+var_238], rax
0x18005e199  test    rax, rax
0x18005e19c  jnz     short loc_18005E1C4
0x18005e19e  mov     rcx, [rbp+178h]; this
0x18005e1a5  lea     r8, aWil; "wil"
0x18005e1ac  mov     edx, 0DCh; void *
0x18005e1b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e1b6  mov     ebx, eax
0x18005e1b8  lea     rcx, [rsp+270h+var_238]
0x18005e1bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e1c2  jmp     short loc_18005E214
0x18005e1c4  lea     rdx, [rsp+270h+var_240]; int *
0x18005e1c9  mov     rcx, rax; hHandle
0x18005e1cc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005e1d1  mov     ebx, eax
0x18005e1d3  test    eax, eax
0x18005e1d5  jns     short loc_18005E1F4
0x18005e1d7  mov     rcx, [rbp+178h]; this
0x18005e1de  lea     r8, aWil; "wil"
0x18005e1e5  mov     r9d, eax; char *
0x18005e1e8  mov     edx, 0DEh; void *
0x18005e1ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e1f2  jmp     short loc_18005E1B8
0x18005e1f4  lea     rcx, [rsp+270h+var_238]
0x18005e1f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e1fe  movsxd  rcx, [rsp+270h+var_240]
0x18005e203  movsxd  rax, [rsp+270h+var_23C]
0x18005e208  shl     rcx, 1Fh
0x18005e20c  or      rcx, rax
0x18005e20f  mov     [rdi], rcx
0x18005e212  xor     ebx, ebx
0x18005e214  lea     rcx, [rsp+270h+var_230]
0x18005e219  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e21e  mov     eax, ebx
0x18005e220  mov     rcx, [rbp+170h+var_10]
0x18005e227  xor     rcx, rsp; StackCookie
0x18005e22a  call    __security_check_cookie
0x18005e22f  lea     r11, [rsp+270h+var_s0]
0x18005e237  mov     rbx, [r11+18h]
0x18005e23b  mov     rdi, [r11+28h]
0x18005e23f  mov     rsp, r11
0x18005e242  pop     rbp
0x18005e243  retn
```
