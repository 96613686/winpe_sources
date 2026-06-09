# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d13c`
- end: `0x18000d2fa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d0b8`

## callees

- `0x180005890`
- `0x180008614`
- `0x180009fb8`
- `0x18000c35c`
- `0x18000c37c`
- `0x18000ca3c`
- `0x18000cb30`
- `0x18000d13c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d1a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d245`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d1a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1b5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x18000d13c  mov     [rsp-8+arg_8], rbx
0x18000d141  push    rbp
0x18000d142  push    rdi
0x18000d143  push    r14
0x18000d145  lea     rbp, [rsp-160h]
0x18000d14d  sub     rsp, 260h
0x18000d154  mov     rax, cs:__security_cookie
0x18000d15b  xor     rax, rsp
0x18000d15e  mov     [rbp+170h+var_20], rax
0x18000d165  mov     rdi, r8
0x18000d168  mov     qword ptr [r8], 0
0x18000d16f  mov     r8, rcx; unsigned __int16 *
0x18000d172  mov     r14d, 104h
0x18000d178  mov     edx, r14d; unsigned __int64
0x18000d17b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d180  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d185  lea     r8, aP0; "_p0"
0x18000d18c  mov     edx, r14d; unsigned __int64
0x18000d18f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d194  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d199  lea     r8, [rsp+270h+Name]; lpName
0x18000d19e  xor     edx, edx; bInheritHandle
0x18000d1a0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d1a5  call    cs:__imp_OpenSemaphoreW
0x18000d1ab  mov     [rsp+270h+var_240], rax
0x18000d1b0  test    rax, rax
0x18000d1b3  jnz     short loc_18000D1E2
0x18000d1b5  call    cs:__imp_GetLastError
0x18000d1bb  cmp     eax, 2
0x18000d1be  jz      loc_18000D2C9
0x18000d1c4  mov     rcx, [rbp+178h]; this
0x18000d1cb  lea     r8, aWil; "wil"
0x18000d1d2  lea     edx, [r14-34h]; void *
0x18000d1d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d1db  mov     ebx, eax
0x18000d1dd  jmp     loc_18000D2CB
0x18000d1e2  lea     rdx, [rsp+270h+var_24C]; int *
0x18000d1e7  mov     [rsp+270h+var_24C], 0
0x18000d1ef  mov     rcx, rax; hHandle
0x18000d1f2  mov     [rsp+270h+var_250], 0; int
0x18000d1fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d1ff  mov     ebx, eax
0x18000d201  test    eax, eax
0x18000d203  jns     short loc_18000D225
0x18000d205  mov     rcx, [rbp+178h]; this
0x18000d20c  lea     r8, aWil; "wil"
0x18000d213  mov     r9d, eax; char *
0x18000d216  mov     edx, 0D6h; void *
0x18000d21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d220  jmp     loc_18000D2CB
0x18000d225  lea     r8, asc_1800F34F8; "h"
0x18000d22c  mov     rdx, r14; unsigned __int64
0x18000d22f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d234  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d239  lea     r8, [rsp+270h+Name]; lpName
0x18000d23e  xor     edx, edx; bInheritHandle
0x18000d240  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d245  call    cs:__imp_OpenSemaphoreW
0x18000d24b  mov     [rsp+270h+var_248], rax
0x18000d250  test    rax, rax
0x18000d253  jnz     short loc_18000D27B
0x18000d255  mov     rcx, [rbp+178h]; this
0x18000d25c  lea     r8, aWil; "wil"
0x18000d263  mov     edx, 0DCh; void *
0x18000d268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d26d  mov     ebx, eax
0x18000d26f  lea     rcx, [rsp+270h+var_248]
0x18000d274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d279  jmp     short loc_18000D2CB
0x18000d27b  lea     rdx, [rsp+270h+var_250]; int *
0x18000d280  mov     rcx, rax; hHandle
0x18000d283  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d288  mov     ebx, eax
0x18000d28a  test    eax, eax
0x18000d28c  jns     short loc_18000D2AB
0x18000d28e  mov     rcx, [rbp+178h]; this
0x18000d295  lea     r8, aWil; "wil"
0x18000d29c  mov     r9d, eax; char *
0x18000d29f  mov     edx, 0DEh; void *
0x18000d2a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d2a9  jmp     short loc_18000D26F
0x18000d2ab  lea     rcx, [rsp+270h+var_248]
0x18000d2b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d2b5  movsxd  rcx, [rsp+270h+var_250]
0x18000d2ba  movsxd  rax, [rsp+270h+var_24C]
0x18000d2bf  shl     rcx, 1Fh
0x18000d2c3  or      rcx, rax
0x18000d2c6  mov     [rdi], rcx
0x18000d2c9  xor     ebx, ebx
0x18000d2cb  lea     rcx, [rsp+270h+var_240]
0x18000d2d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d2d5  mov     eax, ebx
0x18000d2d7  mov     rcx, [rbp+170h+var_20]
0x18000d2de  xor     rcx, rsp; StackCookie
0x18000d2e1  call    __security_check_cookie
0x18000d2e6  mov     rbx, [rsp+270h+arg_8]
0x18000d2ee  add     rsp, 260h
0x18000d2f5  pop     r14
0x18000d2f7  pop     rdi
0x18000d2f8  pop     rbp
0x18000d2f9  retn
```
