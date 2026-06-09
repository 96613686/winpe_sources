# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008284`
- end: `0x180008420`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008210`

## callees

- `0x180001e00`
- `0x18000373c`
- `0x180005478`
- `0x1800074ac`
- `0x1800074cc`
- `0x180007ca0`
- `0x180007dc8`
- `0x180008284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008378`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f8`

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
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
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
0x180008284  mov     [rsp-8+arg_8], rbx
0x180008289  mov     [rsp-8+arg_18], rdi
0x18000828e  push    rbp
0x18000828f  lea     rbp, [rsp-170h]
0x180008297  sub     rsp, 270h
0x18000829e  mov     rax, cs:__security_cookie
0x1800082a5  xor     rax, rsp
0x1800082a8  mov     [rbp+170h+var_10], rax
0x1800082af  mov     r9, rcx; pszSrc
0x1800082b2  mov     qword ptr [r8], 0
0x1800082b9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800082be  mov     edx, 104h; cchDest
0x1800082c3  mov     rdi, r8
0x1800082c6  call    StringCopyWorkerW
0x1800082cb  lea     r8, aP0; "_p0"
0x1800082d2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800082d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082dc  lea     r8, [rsp+270h+pszDest]; lpName
0x1800082e1  xor     edx, edx; bInheritHandle
0x1800082e3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800082e8  call    cs:__imp_OpenSemaphoreW
0x1800082ee  mov     [rsp+270h+var_230], rax
0x1800082f3  test    rax, rax
0x1800082f6  jnz     short loc_18000831F
0x1800082f8  call    cs:__imp_GetLastError
0x1800082fe  cmp     eax, 2
0x180008301  jz      loc_1800083EE
0x180008307  mov     rcx, [rbp+178h]; this
0x18000830e  mov     edx, 0D0h; void *
0x180008313  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008318  mov     ebx, eax
0x18000831a  jmp     loc_1800083F0
0x18000831f  lea     rdx, [rsp+270h+var_23C]; int *
0x180008324  mov     [rsp+270h+var_23C], 0
0x18000832c  mov     rcx, rax; hHandle
0x18000832f  mov     [rsp+270h+var_240], 0
0x180008337  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000833c  mov     ebx, eax
0x18000833e  test    eax, eax
0x180008340  jns     short loc_18000835B
0x180008342  mov     rcx, [rbp+178h]; this
0x180008349  mov     r9d, eax; char *
0x18000834c  mov     edx, 0D6h; void *
0x180008351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008356  jmp     loc_1800083F0
0x18000835b  lea     r8, asc_18000BAF8; "h"
0x180008362  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180008367  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000836c  lea     r8, [rsp+270h+pszDest]; lpName
0x180008371  xor     edx, edx; bInheritHandle
0x180008373  mov     ecx, 1F0003h; dwDesiredAccess
0x180008378  call    cs:__imp_OpenSemaphoreW
0x18000837e  mov     [rsp+270h+var_238], rax
0x180008383  test    rax, rax
0x180008386  jnz     short loc_1800083A7
0x180008388  mov     rcx, [rbp+178h]; this
0x18000838f  mov     edx, 0DCh; void *
0x180008394  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008399  mov     ebx, eax
0x18000839b  lea     rcx, [rsp+270h+var_238]
0x1800083a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083a5  jmp     short loc_1800083F0
0x1800083a7  lea     rdx, [rsp+270h+var_240]; int *
0x1800083ac  mov     rcx, rax; hHandle
0x1800083af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800083b4  mov     ebx, eax
0x1800083b6  test    eax, eax
0x1800083b8  jns     short loc_1800083D0
0x1800083ba  mov     rcx, [rbp+178h]; this
0x1800083c1  mov     r9d, eax; char *
0x1800083c4  mov     edx, 0DEh; void *
0x1800083c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083ce  jmp     short loc_18000839B
0x1800083d0  lea     rcx, [rsp+270h+var_238]
0x1800083d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083da  movsxd  rcx, [rsp+270h+var_240]
0x1800083df  movsxd  rax, [rsp+270h+var_23C]
0x1800083e4  shl     rcx, 1Fh
0x1800083e8  or      rcx, rax
0x1800083eb  mov     [rdi], rcx
0x1800083ee  xor     ebx, ebx
0x1800083f0  lea     rcx, [rsp+270h+var_230]
0x1800083f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083fa  mov     eax, ebx
0x1800083fc  mov     rcx, [rbp+170h+var_10]
0x180008403  xor     rcx, rsp; StackCookie
0x180008406  call    __security_check_cookie
0x18000840b  lea     r11, [rsp+270h+var_s0]
0x180008413  mov     rbx, [r11+18h]
0x180008417  mov     rdi, [r11+28h]
0x18000841b  mov     rsp, r11
0x18000841e  pop     rbp
0x18000841f  retn
```
