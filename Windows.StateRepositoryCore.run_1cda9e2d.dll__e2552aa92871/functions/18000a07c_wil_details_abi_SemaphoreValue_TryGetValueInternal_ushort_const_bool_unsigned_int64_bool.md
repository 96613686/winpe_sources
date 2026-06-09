# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a07c`
- end: `0x18000a234`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009ff8`

## callees

- `0x180001ed0`
- `0x180003df0`
- `0x180006bc8`
- `0x1800093ec`
- `0x18000940c`
- `0x180009ad8`
- `0x180009b54`
- `0x18000a07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a17e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a17e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f0`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000a07c  mov     [rsp-8+arg_8], rbx
0x18000a081  mov     [rsp-8+arg_18], rdi
0x18000a086  push    rbp
0x18000a087  lea     rbp, [rsp-160h]
0x18000a08f  sub     rsp, 260h
0x18000a096  mov     rax, cs:__security_cookie
0x18000a09d  xor     rax, rsp
0x18000a0a0  mov     [rbp+160h+var_10], rax
0x18000a0a7  mov     rdi, r8
0x18000a0aa  mov     qword ptr [r8], 0
0x18000a0b1  mov     r8, rcx; unsigned __int16 *
0x18000a0b4  mov     edx, 104h; unsigned __int64
0x18000a0b9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a0be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a0c3  lea     r8, aP0; "_p0"
0x18000a0ca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a0cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a0d4  lea     r8, [rsp+260h+Name]; lpName
0x18000a0d9  xor     edx, edx; bInheritHandle
0x18000a0db  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a0e0  call    cs:__imp_OpenSemaphoreW
0x18000a0e6  mov     [rsp+260h+var_230], rax
0x18000a0eb  test    rax, rax
0x18000a0ee  jnz     short loc_18000A11E
0x18000a0f0  call    cs:__imp_GetLastError
0x18000a0f6  cmp     eax, 2
0x18000a0f9  jz      loc_18000A202
0x18000a0ff  mov     rcx, [rbp+168h]; this
0x18000a106  lea     r8, aWil; "wil"
0x18000a10d  mov     edx, 0D0h; void *
0x18000a112  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a117  mov     ebx, eax
0x18000a119  jmp     loc_18000A204
0x18000a11e  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a123  mov     [rsp+260h+var_23C], 0
0x18000a12b  mov     rcx, rax; hHandle
0x18000a12e  mov     [rsp+260h+var_240], 0; int
0x18000a136  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a13b  mov     ebx, eax
0x18000a13d  test    eax, eax
0x18000a13f  jns     short loc_18000A161
0x18000a141  mov     rcx, [rbp+168h]; this
0x18000a148  lea     r8, aWil; "wil"
0x18000a14f  mov     r9d, eax; char *
0x18000a152  mov     edx, 0D6h; void *
0x18000a157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a15c  jmp     loc_18000A204
0x18000a161  lea     r8, asc_1800130C0; "h"
0x18000a168  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a16d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a172  lea     r8, [rsp+260h+Name]; lpName
0x18000a177  xor     edx, edx; bInheritHandle
0x18000a179  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a17e  call    cs:__imp_OpenSemaphoreW
0x18000a184  mov     [rsp+260h+var_238], rax
0x18000a189  test    rax, rax
0x18000a18c  jnz     short loc_18000A1B4
0x18000a18e  mov     rcx, [rbp+168h]; this
0x18000a195  lea     r8, aWil; "wil"
0x18000a19c  mov     edx, 0DCh; void *
0x18000a1a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1a6  mov     ebx, eax
0x18000a1a8  lea     rcx, [rsp+260h+var_238]
0x18000a1ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a1b2  jmp     short loc_18000A204
0x18000a1b4  lea     rdx, [rsp+260h+var_240]; int *
0x18000a1b9  mov     rcx, rax; hHandle
0x18000a1bc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a1c1  mov     ebx, eax
0x18000a1c3  test    eax, eax
0x18000a1c5  jns     short loc_18000A1E4
0x18000a1c7  mov     rcx, [rbp+168h]; this
0x18000a1ce  lea     r8, aWil; "wil"
0x18000a1d5  mov     r9d, eax; char *
0x18000a1d8  mov     edx, 0DEh; void *
0x18000a1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1e2  jmp     short loc_18000A1A8
0x18000a1e4  lea     rcx, [rsp+260h+var_238]
0x18000a1e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a1ee  movsxd  rcx, [rsp+260h+var_240]
0x18000a1f3  movsxd  rax, [rsp+260h+var_23C]
0x18000a1f8  shl     rcx, 1Fh
0x18000a1fc  or      rcx, rax
0x18000a1ff  mov     [rdi], rcx
0x18000a202  xor     ebx, ebx
0x18000a204  lea     rcx, [rsp+260h+var_230]
0x18000a209  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a20e  mov     eax, ebx
0x18000a210  mov     rcx, [rbp+160h+var_10]
0x18000a217  xor     rcx, rsp; StackCookie
0x18000a21a  call    __security_check_cookie
0x18000a21f  lea     r11, [rsp+260h+var_s0]
0x18000a227  mov     rbx, [r11+18h]
0x18000a22b  mov     rdi, [r11+28h]
0x18000a22f  mov     rsp, r11
0x18000a232  pop     rbp
0x18000a233  retn
```
