# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f0a0`
- end: `0x18000f25e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f01c`

## callees

- `0x180003c80`
- `0x18000aa7c`
- `0x18000c394`
- `0x18000e1fc`
- `0x18000e21c`
- `0x18000e938`
- `0x18000ea2c`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f109`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f1a9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f109`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f119`

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
0x18000f0a0  mov     [rsp-8+arg_8], rbx
0x18000f0a5  push    rbp
0x18000f0a6  push    rdi
0x18000f0a7  push    r14
0x18000f0a9  lea     rbp, [rsp-160h]
0x18000f0b1  sub     rsp, 260h
0x18000f0b8  mov     rax, cs:__security_cookie
0x18000f0bf  xor     rax, rsp
0x18000f0c2  mov     [rbp+170h+var_20], rax
0x18000f0c9  mov     rdi, r8
0x18000f0cc  mov     qword ptr [r8], 0
0x18000f0d3  mov     r8, rcx; unsigned __int16 *
0x18000f0d6  mov     r14d, 104h
0x18000f0dc  mov     edx, r14d; unsigned __int64
0x18000f0df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f0e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f0e9  lea     r8, aP0; "_p0"
0x18000f0f0  mov     edx, r14d; unsigned __int64
0x18000f0f3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f0f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f0fd  lea     r8, [rsp+270h+Name]; lpName
0x18000f102  xor     edx, edx; bInheritHandle
0x18000f104  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f109  call    cs:__imp_OpenSemaphoreW
0x18000f10f  mov     [rsp+270h+var_240], rax
0x18000f114  test    rax, rax
0x18000f117  jnz     short loc_18000F146
0x18000f119  call    cs:__imp_GetLastError
0x18000f11f  cmp     eax, 2
0x18000f122  jz      loc_18000F22D
0x18000f128  mov     rcx, [rbp+178h]; this
0x18000f12f  lea     r8, aWil; "wil"
0x18000f136  lea     edx, [r14-34h]; void *
0x18000f13a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f13f  mov     ebx, eax
0x18000f141  jmp     loc_18000F22F
0x18000f146  lea     rdx, [rsp+270h+var_24C]; int *
0x18000f14b  mov     [rsp+270h+var_24C], 0
0x18000f153  mov     rcx, rax; hHandle
0x18000f156  mov     [rsp+270h+var_250], 0; int
0x18000f15e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f163  mov     ebx, eax
0x18000f165  test    eax, eax
0x18000f167  jns     short loc_18000F189
0x18000f169  mov     rcx, [rbp+178h]; this
0x18000f170  lea     r8, aWil; "wil"
0x18000f177  mov     r9d, eax; char *
0x18000f17a  mov     edx, 0D6h; void *
0x18000f17f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f184  jmp     loc_18000F22F
0x18000f189  lea     r8, asc_18004E1E0; "h"
0x18000f190  mov     rdx, r14; unsigned __int64
0x18000f193  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f198  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f19d  lea     r8, [rsp+270h+Name]; lpName
0x18000f1a2  xor     edx, edx; bInheritHandle
0x18000f1a4  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f1a9  call    cs:__imp_OpenSemaphoreW
0x18000f1af  mov     [rsp+270h+var_248], rax
0x18000f1b4  test    rax, rax
0x18000f1b7  jnz     short loc_18000F1DF
0x18000f1b9  mov     rcx, [rbp+178h]; this
0x18000f1c0  lea     r8, aWil; "wil"
0x18000f1c7  mov     edx, 0DCh; void *
0x18000f1cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f1d1  mov     ebx, eax
0x18000f1d3  lea     rcx, [rsp+270h+var_248]
0x18000f1d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f1dd  jmp     short loc_18000F22F
0x18000f1df  lea     rdx, [rsp+270h+var_250]; int *
0x18000f1e4  mov     rcx, rax; hHandle
0x18000f1e7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f1ec  mov     ebx, eax
0x18000f1ee  test    eax, eax
0x18000f1f0  jns     short loc_18000F20F
0x18000f1f2  mov     rcx, [rbp+178h]; this
0x18000f1f9  lea     r8, aWil; "wil"
0x18000f200  mov     r9d, eax; char *
0x18000f203  mov     edx, 0DEh; void *
0x18000f208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f20d  jmp     short loc_18000F1D3
0x18000f20f  lea     rcx, [rsp+270h+var_248]
0x18000f214  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f219  movsxd  rcx, [rsp+270h+var_250]
0x18000f21e  movsxd  rax, [rsp+270h+var_24C]
0x18000f223  shl     rcx, 1Fh
0x18000f227  or      rcx, rax
0x18000f22a  mov     [rdi], rcx
0x18000f22d  xor     ebx, ebx
0x18000f22f  lea     rcx, [rsp+270h+var_240]
0x18000f234  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f239  mov     eax, ebx
0x18000f23b  mov     rcx, [rbp+170h+var_20]
0x18000f242  xor     rcx, rsp; StackCookie
0x18000f245  call    __security_check_cookie
0x18000f24a  mov     rbx, [rsp+270h+arg_8]
0x18000f252  add     rsp, 260h
0x18000f259  pop     r14
0x18000f25b  pop     rdi
0x18000f25c  pop     rbp
0x18000f25d  retn
```
