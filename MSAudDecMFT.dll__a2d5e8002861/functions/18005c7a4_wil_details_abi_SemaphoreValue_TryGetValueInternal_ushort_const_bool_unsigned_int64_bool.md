# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18005c7a4`
- end: `0x18005c953`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180058c34`

## callees

- `0x18004d320`
- `0x18005673c`
- `0x180058b14`
- `0x18005b594`
- `0x18005c3e8`
- `0x18005c408`
- `0x18005c654`
- `0x18005c7a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c81e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c81e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c808`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c8a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c808`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c8a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x18005c7a4  mov     [rsp-8+arg_8], rbx
0x18005c7a9  mov     [rsp-8+arg_18], rdi
0x18005c7ae  push    rbp
0x18005c7af  lea     rbp, [rsp-160h]
0x18005c7b7  sub     rsp, 260h
0x18005c7be  mov     rax, cs:__security_cookie
0x18005c7c5  xor     rax, rsp
0x18005c7c8  mov     [rbp+160h+var_10], rax
0x18005c7cf  mov     rdi, r8
0x18005c7d2  mov     qword ptr [r8], 0
0x18005c7d9  mov     r8, rcx; unsigned __int16 *
0x18005c7dc  mov     edx, 104h; unsigned __int64
0x18005c7e1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005c7e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005c7eb  lea     r8, aP0; "_p0"
0x18005c7f2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005c7f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c7fc  lea     r8, [rsp+260h+Name]; lpName
0x18005c801  xor     edx, edx; bInheritHandle
0x18005c803  mov     ecx, 1F0003h; dwDesiredAccess
0x18005c808  call    cs:__imp_OpenSemaphoreW
0x18005c80f  nop     dword ptr [rax+rax+00h]
0x18005c814  mov     [rsp+260h+var_230], rax
0x18005c819  test    rax, rax
0x18005c81c  jnz     short loc_18005C84B
0x18005c81e  call    cs:__imp_GetLastError
0x18005c825  nop     dword ptr [rax+rax+00h]
0x18005c82a  cmp     eax, 2
0x18005c82d  jz      loc_18005C920
0x18005c833  mov     rcx, [rbp+168h]; this
0x18005c83a  mov     edx, 0D0h; void *
0x18005c83f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c844  mov     ebx, eax
0x18005c846  jmp     loc_18005C922
0x18005c84b  mov     [rsp+260h+var_23C], 0
0x18005c853  mov     [rsp+260h+var_240], 0; int
0x18005c85b  lea     rdx, [rsp+260h+var_23C]; int *
0x18005c860  mov     rcx, rax; hHandle
0x18005c863  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005c868  mov     ebx, eax
0x18005c86a  test    eax, eax
0x18005c86c  jns     short loc_18005C887
0x18005c86e  mov     rcx, [rbp+168h]; this
0x18005c875  mov     r9d, eax; char *
0x18005c878  mov     edx, 0D6h; void *
0x18005c87d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c882  jmp     loc_18005C922
0x18005c887  lea     r8, asc_1800B6080; "h"
0x18005c88e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005c893  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c898  lea     r8, [rsp+260h+Name]; lpName
0x18005c89d  xor     edx, edx; bInheritHandle
0x18005c89f  mov     ecx, 1F0003h; dwDesiredAccess
0x18005c8a4  call    cs:__imp_OpenSemaphoreW
0x18005c8ab  nop     dword ptr [rax+rax+00h]
0x18005c8b0  mov     [rsp+260h+var_238], rax
0x18005c8b5  test    rax, rax
0x18005c8b8  jnz     short loc_18005C8D9
0x18005c8ba  mov     rcx, [rbp+168h]; this
0x18005c8c1  mov     edx, 0DCh; void *
0x18005c8c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c8cb  mov     ebx, eax
0x18005c8cd  lea     rcx, [rsp+260h+var_238]
0x18005c8d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c8d7  jmp     short loc_18005C922
0x18005c8d9  lea     rdx, [rsp+260h+var_240]; int *
0x18005c8de  mov     rcx, rax; hHandle
0x18005c8e1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005c8e6  mov     ebx, eax
0x18005c8e8  test    eax, eax
0x18005c8ea  jns     short loc_18005C902
0x18005c8ec  mov     rcx, [rbp+168h]; this
0x18005c8f3  mov     r9d, eax; char *
0x18005c8f6  mov     edx, 0DEh; void *
0x18005c8fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c900  jmp     short loc_18005C8CD
0x18005c902  lea     rcx, [rsp+260h+var_238]
0x18005c907  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c90c  movsxd  rcx, [rsp+260h+var_240]
0x18005c911  shl     rcx, 1Fh
0x18005c915  movsxd  rax, [rsp+260h+var_23C]
0x18005c91a  or      rcx, rax
0x18005c91d  mov     [rdi], rcx
0x18005c920  xor     ebx, ebx
0x18005c922  lea     rcx, [rsp+260h+var_230]
0x18005c927  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c92c  mov     eax, ebx
0x18005c92e  mov     rcx, [rbp+160h+var_10]
0x18005c935  xor     rcx, rsp; StackCookie
0x18005c938  call    __security_check_cookie
0x18005c93d  lea     r11, [rsp+260h+var_s0]
0x18005c945  mov     rbx, [r11+18h]
0x18005c949  mov     rdi, [r11+28h]
0x18005c94d  mov     rsp, r11
0x18005c950  pop     rbp
0x18005c951  retn
```
