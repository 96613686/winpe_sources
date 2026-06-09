# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400d6774`
- end: `0x1400d6945`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140138c8c`

## callees

- `0x140027a4c`
- `0x1400b42b0`
- `0x1400d6774`
- `0x1400d694c`
- `0x1400d69d8`
- `0x1400d6a74`
- `0x140132940`
- `0x140136eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400d67dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400d6889`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400d67dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400d6889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d67f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d67f3`

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
0x1400d6774  mov     [rsp-8+arg_8], rbx
0x1400d6779  push    rbp
0x1400d677a  push    rdi
0x1400d677b  push    r14
0x1400d677d  lea     rbp, [rsp-160h]
0x1400d6785  sub     rsp, 260h
0x1400d678c  mov     rax, cs:__security_cookie
0x1400d6793  xor     rax, rsp
0x1400d6796  mov     [rbp+170h+var_20], rax
0x1400d679d  mov     rdi, r8
0x1400d67a0  mov     qword ptr [r8], 0
0x1400d67a7  mov     r8, rcx; unsigned __int16 *
0x1400d67aa  mov     r14d, 104h
0x1400d67b0  mov     edx, r14d; unsigned __int64
0x1400d67b3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400d67b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d67bd  lea     r8, aP0; "_p0"
0x1400d67c4  mov     edx, r14d; unsigned __int64
0x1400d67c7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400d67cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d67d1  lea     r8, [rsp+270h+Name]; lpName
0x1400d67d6  xor     edx, edx; bInheritHandle
0x1400d67d8  mov     ecx, 1F0003h; dwDesiredAccess
0x1400d67dd  call    cs:__imp_OpenSemaphoreW
0x1400d67e4  nop     dword ptr [rax+rax+00h]
0x1400d67e9  mov     [rsp+270h+var_240], rax
0x1400d67ee  test    rax, rax
0x1400d67f1  jnz     short loc_1400D6826
0x1400d67f3  call    cs:__imp_GetLastError
0x1400d67fa  nop     dword ptr [rax+rax+00h]
0x1400d67ff  cmp     eax, 2
0x1400d6802  jz      loc_1400D6913
0x1400d6808  mov     rcx, [rbp+178h]; this
0x1400d680f  lea     r8, aWil; "wil"
0x1400d6816  lea     edx, [r14-34h]; void *
0x1400d681a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400d681f  mov     ebx, eax
0x1400d6821  jmp     loc_1400D6915
0x1400d6826  lea     rdx, [rsp+270h+var_24C]; int *
0x1400d682b  mov     [rsp+270h+var_24C], 0
0x1400d6833  mov     rcx, rax; hHandle
0x1400d6836  mov     [rsp+270h+var_250], 0; int
0x1400d683e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400d6843  mov     ebx, eax
0x1400d6845  test    eax, eax
0x1400d6847  jns     short loc_1400D6869
0x1400d6849  mov     rcx, [rbp+178h]; this
0x1400d6850  lea     r8, aWil; "wil"
0x1400d6857  mov     r9d, eax; char *
0x1400d685a  mov     edx, 0D6h; void *
0x1400d685f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400d6864  jmp     loc_1400D6915
0x1400d6869  lea     r8, asc_1402EAE98; "h"
0x1400d6870  mov     rdx, r14; unsigned __int64
0x1400d6873  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400d6878  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d687d  lea     r8, [rsp+270h+Name]; lpName
0x1400d6882  xor     edx, edx; bInheritHandle
0x1400d6884  mov     ecx, 1F0003h; dwDesiredAccess
0x1400d6889  call    cs:__imp_OpenSemaphoreW
0x1400d6890  nop     dword ptr [rax+rax+00h]
0x1400d6895  mov     [rsp+270h+var_248], rax
0x1400d689a  test    rax, rax
0x1400d689d  jnz     short loc_1400D68C5
0x1400d689f  mov     rcx, [rbp+178h]; this
0x1400d68a6  lea     r8, aWil; "wil"
0x1400d68ad  mov     edx, 0DCh; void *
0x1400d68b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400d68b7  mov     ebx, eax
0x1400d68b9  lea     rcx, [rsp+270h+var_248]
0x1400d68be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400d68c3  jmp     short loc_1400D6915
0x1400d68c5  lea     rdx, [rsp+270h+var_250]; int *
0x1400d68ca  mov     rcx, rax; hHandle
0x1400d68cd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400d68d2  mov     ebx, eax
0x1400d68d4  test    eax, eax
0x1400d68d6  jns     short loc_1400D68F5
0x1400d68d8  mov     rcx, [rbp+178h]; this
0x1400d68df  lea     r8, aWil; "wil"
0x1400d68e6  mov     r9d, eax; char *
0x1400d68e9  mov     edx, 0DEh; void *
0x1400d68ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400d68f3  jmp     short loc_1400D68B9
0x1400d68f5  lea     rcx, [rsp+270h+var_248]
0x1400d68fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400d68ff  movsxd  rcx, [rsp+270h+var_250]
0x1400d6904  movsxd  rax, [rsp+270h+var_24C]
0x1400d6909  shl     rcx, 1Fh
0x1400d690d  or      rcx, rax
0x1400d6910  mov     [rdi], rcx
0x1400d6913  xor     ebx, ebx
0x1400d6915  lea     rcx, [rsp+270h+var_240]
0x1400d691a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400d691f  mov     eax, ebx
0x1400d6921  mov     rcx, [rbp+170h+var_20]
0x1400d6928  xor     rcx, rsp; StackCookie
0x1400d692b  call    __security_check_cookie
0x1400d6930  mov     rbx, [rsp+270h+arg_8]
0x1400d6938  add     rsp, 260h
0x1400d693f  pop     r14
0x1400d6941  pop     rdi
0x1400d6942  pop     rbp
0x1400d6943  retn
```
