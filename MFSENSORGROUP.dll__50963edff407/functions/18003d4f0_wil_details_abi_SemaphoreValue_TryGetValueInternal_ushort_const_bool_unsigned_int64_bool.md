# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003d4f0`
- end: `0x18003d69a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003d340`

## callees

- `0x180015e80`
- `0x18003d4f0`
- `0x18003d6a0`
- `0x18003d71c`
- `0x18003d8cc`
- `0x18003de18`
- `0x180044f30`
- `0x180046e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d554`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d5eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d554`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d564`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18003d4f0  mov     [rsp-8+arg_8], rbx
0x18003d4f5  mov     [rsp-8+arg_18], rdi
0x18003d4fa  push    rbp
0x18003d4fb  lea     rbp, [rsp-160h]
0x18003d503  sub     rsp, 260h
0x18003d50a  mov     rax, cs:__security_cookie
0x18003d511  xor     rax, rsp
0x18003d514  mov     [rbp+160h+var_10], rax
0x18003d51b  mov     rdi, r8
0x18003d51e  mov     qword ptr [r8], 0
0x18003d525  mov     r8, rcx; unsigned __int16 *
0x18003d528  mov     edx, 104h; unsigned __int64
0x18003d52d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003d532  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d537  lea     r8, aP0; "_p0"
0x18003d53e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003d543  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d548  lea     r8, [rsp+260h+Name]; lpName
0x18003d54d  xor     edx, edx; bInheritHandle
0x18003d54f  mov     ecx, 1F0003h; dwDesiredAccess
0x18003d554  call    cs:__imp_OpenSemaphoreW
0x18003d55a  mov     [rsp+260h+var_230], rax
0x18003d55f  test    rax, rax
0x18003d562  jnz     short loc_18003D58B
0x18003d564  call    cs:__imp_GetLastError
0x18003d56a  cmp     eax, 2
0x18003d56d  jz      loc_18003D668
0x18003d573  mov     rcx, [rbp+168h]; this
0x18003d57a  mov     edx, 0D0h; void *
0x18003d57f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d584  mov     ebx, eax
0x18003d586  jmp     loc_18003D66A
0x18003d58b  lea     rdx, [rsp+260h+var_23C]; int *
0x18003d590  mov     [rsp+260h+var_23C], 0
0x18003d598  mov     rcx, rax; hHandle
0x18003d59b  mov     [rsp+260h+var_240], 0; int
0x18003d5a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003d5a8  mov     ebx, eax
0x18003d5aa  test    eax, eax
0x18003d5ac  jns     short loc_18003D5CE
0x18003d5ae  mov     rcx, [rbp+168h]; this
0x18003d5b5  lea     r8, aWil; "wil"
0x18003d5bc  mov     r9d, eax; char *
0x18003d5bf  mov     edx, 0D6h; void *
0x18003d5c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d5c9  jmp     loc_18003D66A
0x18003d5ce  lea     r8, asc_18007D340; "h"
0x18003d5d5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003d5da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d5df  lea     r8, [rsp+260h+Name]; lpName
0x18003d5e4  xor     edx, edx; bInheritHandle
0x18003d5e6  mov     ecx, 1F0003h; dwDesiredAccess
0x18003d5eb  call    cs:__imp_OpenSemaphoreW
0x18003d5f1  mov     [rsp+260h+var_238], rax
0x18003d5f6  test    rax, rax
0x18003d5f9  jnz     short loc_18003D61A
0x18003d5fb  mov     rcx, [rbp+168h]; this
0x18003d602  mov     edx, 0DCh; void *
0x18003d607  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d60c  mov     ebx, eax
0x18003d60e  lea     rcx, [rsp+260h+var_238]
0x18003d613  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d618  jmp     short loc_18003D66A
0x18003d61a  lea     rdx, [rsp+260h+var_240]; int *
0x18003d61f  mov     rcx, rax; hHandle
0x18003d622  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003d627  mov     ebx, eax
0x18003d629  test    eax, eax
0x18003d62b  jns     short loc_18003D64A
0x18003d62d  mov     rcx, [rbp+168h]; this
0x18003d634  lea     r8, aWil; "wil"
0x18003d63b  mov     r9d, eax; char *
0x18003d63e  mov     edx, 0DEh; void *
0x18003d643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d648  jmp     short loc_18003D60E
0x18003d64a  lea     rcx, [rsp+260h+var_238]
0x18003d64f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d654  movsxd  rcx, [rsp+260h+var_240]
0x18003d659  movsxd  rax, [rsp+260h+var_23C]
0x18003d65e  shl     rcx, 1Fh
0x18003d662  or      rcx, rax
0x18003d665  mov     [rdi], rcx
0x18003d668  xor     ebx, ebx
0x18003d66a  lea     rcx, [rsp+260h+var_230]
0x18003d66f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d674  mov     eax, ebx
0x18003d676  mov     rcx, [rbp+160h+var_10]
0x18003d67d  xor     rcx, rsp; StackCookie
0x18003d680  call    __security_check_cookie
0x18003d685  lea     r11, [rsp+260h+var_s0]
0x18003d68d  mov     rbx, [r11+18h]
0x18003d691  mov     rdi, [r11+28h]
0x18003d695  mov     rsp, r11
0x18003d698  pop     rbp
0x18003d699  retn
```
