# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18013a34c`
- end: `0x18013a4e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18013a2d8`

## callees

- `0x180076e30`
- `0x180134b70`
- `0x180136788`
- `0x180138024`
- `0x18013982c`
- `0x18013984c`
- `0x180139f0c`
- `0x18013a34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18013a3b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18013a440`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18013a3b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18013a440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a3c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
0x18013a34c  mov     [rsp-8+arg_8], rbx
0x18013a351  mov     [rsp-8+arg_18], rdi
0x18013a356  push    rbp
0x18013a357  lea     rbp, [rsp-160h]
0x18013a35f  sub     rsp, 260h
0x18013a366  mov     rax, cs:__security_cookie
0x18013a36d  xor     rax, rsp
0x18013a370  mov     [rbp+160h+var_10], rax
0x18013a377  mov     rdi, r8
0x18013a37a  mov     qword ptr [r8], 0
0x18013a381  mov     r8, rcx; wchar_t *
0x18013a384  mov     edx, 104h; unsigned __int64
0x18013a389  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18013a38e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18013a393  lea     r8, aP0; "_p0"
0x18013a39a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18013a39f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18013a3a4  lea     r8, [rsp+260h+Name]; lpName
0x18013a3a9  xor     edx, edx; bInheritHandle
0x18013a3ab  mov     ecx, 1F0003h; dwDesiredAccess
0x18013a3b0  call    cs:__imp_OpenSemaphoreW
0x18013a3b6  mov     [rsp+260h+var_230], rax
0x18013a3bb  test    rax, rax
0x18013a3be  jnz     short loc_18013A3E7
0x18013a3c0  call    cs:__imp_GetLastError
0x18013a3c6  cmp     eax, 2
0x18013a3c9  jz      loc_18013A4B6
0x18013a3cf  mov     rcx, [rbp+168h]; this
0x18013a3d6  mov     edx, 0D0h; void *
0x18013a3db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18013a3e0  mov     ebx, eax
0x18013a3e2  jmp     loc_18013A4B8
0x18013a3e7  lea     rdx, [rsp+260h+var_23C]; int *
0x18013a3ec  mov     [rsp+260h+var_23C], 0
0x18013a3f4  mov     rcx, rax; hHandle
0x18013a3f7  mov     [rsp+260h+var_240], 0; int
0x18013a3ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18013a404  mov     ebx, eax
0x18013a406  test    eax, eax
0x18013a408  jns     short loc_18013A423
0x18013a40a  mov     rcx, [rbp+168h]; this
0x18013a411  mov     r9d, eax; char *
0x18013a414  mov     edx, 0D6h; void *
0x18013a419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a41e  jmp     loc_18013A4B8
0x18013a423  lea     r8, asc_1801E1A64; "h"
0x18013a42a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18013a42f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18013a434  lea     r8, [rsp+260h+Name]; lpName
0x18013a439  xor     edx, edx; bInheritHandle
0x18013a43b  mov     ecx, 1F0003h; dwDesiredAccess
0x18013a440  call    cs:__imp_OpenSemaphoreW
0x18013a446  mov     [rsp+260h+var_238], rax
0x18013a44b  test    rax, rax
0x18013a44e  jnz     short loc_18013A46F
0x18013a450  mov     rcx, [rbp+168h]; this
0x18013a457  mov     edx, 0DCh; void *
0x18013a45c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18013a461  mov     ebx, eax
0x18013a463  lea     rcx, [rsp+260h+var_238]
0x18013a468  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013a46d  jmp     short loc_18013A4B8
0x18013a46f  lea     rdx, [rsp+260h+var_240]; int *
0x18013a474  mov     rcx, rax; hHandle
0x18013a477  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18013a47c  mov     ebx, eax
0x18013a47e  test    eax, eax
0x18013a480  jns     short loc_18013A498
0x18013a482  mov     rcx, [rbp+168h]; this
0x18013a489  mov     r9d, eax; char *
0x18013a48c  mov     edx, 0DEh; void *
0x18013a491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a496  jmp     short loc_18013A463
0x18013a498  lea     rcx, [rsp+260h+var_238]
0x18013a49d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013a4a2  movsxd  rcx, [rsp+260h+var_240]
0x18013a4a7  movsxd  rax, [rsp+260h+var_23C]
0x18013a4ac  shl     rcx, 1Fh
0x18013a4b0  or      rcx, rax
0x18013a4b3  mov     [rdi], rcx
0x18013a4b6  xor     ebx, ebx
0x18013a4b8  lea     rcx, [rsp+260h+var_230]
0x18013a4bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013a4c2  mov     eax, ebx
0x18013a4c4  mov     rcx, [rbp+160h+var_10]
0x18013a4cb  xor     rcx, rsp; StackCookie
0x18013a4ce  call    __security_check_cookie
0x18013a4d3  lea     r11, [rsp+260h+var_s0]
0x18013a4db  mov     rbx, [r11+18h]
0x18013a4df  mov     rdi, [r11+28h]
0x18013a4e3  mov     rsp, r11
0x18013a4e6  pop     rbp
0x18013a4e7  retn
```
