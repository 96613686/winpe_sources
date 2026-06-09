# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027b34`
- end: `0x180027cde`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027ab0`

## callees

- `0x1800150dc`
- `0x18001be80`
- `0x180024144`
- `0x1800258cc`
- `0x180026fdc`
- `0x1800276bc`
- `0x180027b34`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027b98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027c2f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027b98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ba8`

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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
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
0x180027b34  mov     [rsp-8+arg_8], rbx
0x180027b39  mov     [rsp-8+arg_18], rdi
0x180027b3e  push    rbp
0x180027b3f  lea     rbp, [rsp-160h]
0x180027b47  sub     rsp, 260h
0x180027b4e  mov     rax, cs:__security_cookie
0x180027b55  xor     rax, rsp
0x180027b58  mov     [rbp+160h+var_10], rax
0x180027b5f  mov     rdi, r8
0x180027b62  mov     qword ptr [r8], 0
0x180027b69  mov     r8, rcx; unsigned __int16 *
0x180027b6c  mov     edx, 104h; unsigned __int64
0x180027b71  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180027b76  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027b7b  lea     r8, aP0; "_p0"
0x180027b82  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180027b87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027b8c  lea     r8, [rsp+260h+Name]; lpName
0x180027b91  xor     edx, edx; bInheritHandle
0x180027b93  mov     ecx, 1F0003h; dwDesiredAccess
0x180027b98  call    cs:__imp_OpenSemaphoreW
0x180027b9e  mov     [rsp+260h+var_230], rax
0x180027ba3  test    rax, rax
0x180027ba6  jnz     short loc_180027BCF
0x180027ba8  call    cs:__imp_GetLastError
0x180027bae  cmp     eax, 2
0x180027bb1  jz      loc_180027CAC
0x180027bb7  mov     rcx, [rbp+168h]; this
0x180027bbe  mov     edx, 0D0h; void *
0x180027bc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027bc8  mov     ebx, eax
0x180027bca  jmp     loc_180027CAE
0x180027bcf  lea     rdx, [rsp+260h+var_23C]; int *
0x180027bd4  mov     [rsp+260h+var_23C], 0
0x180027bdc  mov     rcx, rax; hHandle
0x180027bdf  mov     [rsp+260h+var_240], 0; int
0x180027be7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027bec  mov     ebx, eax
0x180027bee  test    eax, eax
0x180027bf0  jns     short loc_180027C12
0x180027bf2  mov     rcx, [rbp+168h]; this
0x180027bf9  lea     r8, aWil; "wil"
0x180027c00  mov     r9d, eax; char *
0x180027c03  mov     edx, 0D6h; void *
0x180027c08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c0d  jmp     loc_180027CAE
0x180027c12  lea     r8, asc_180040478; "h"
0x180027c19  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180027c1e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027c23  lea     r8, [rsp+260h+Name]; lpName
0x180027c28  xor     edx, edx; bInheritHandle
0x180027c2a  mov     ecx, 1F0003h; dwDesiredAccess
0x180027c2f  call    cs:__imp_OpenSemaphoreW
0x180027c35  mov     [rsp+260h+var_238], rax
0x180027c3a  test    rax, rax
0x180027c3d  jnz     short loc_180027C5E
0x180027c3f  mov     rcx, [rbp+168h]; this
0x180027c46  mov     edx, 0DCh; void *
0x180027c4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027c50  mov     ebx, eax
0x180027c52  lea     rcx, [rsp+260h+var_238]
0x180027c57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027c5c  jmp     short loc_180027CAE
0x180027c5e  lea     rdx, [rsp+260h+var_240]; int *
0x180027c63  mov     rcx, rax; hHandle
0x180027c66  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027c6b  mov     ebx, eax
0x180027c6d  test    eax, eax
0x180027c6f  jns     short loc_180027C8E
0x180027c71  mov     rcx, [rbp+168h]; this
0x180027c78  lea     r8, aWil; "wil"
0x180027c7f  mov     r9d, eax; char *
0x180027c82  mov     edx, 0DEh; void *
0x180027c87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c8c  jmp     short loc_180027C52
0x180027c8e  lea     rcx, [rsp+260h+var_238]
0x180027c93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027c98  movsxd  rcx, [rsp+260h+var_240]
0x180027c9d  movsxd  rax, [rsp+260h+var_23C]
0x180027ca2  shl     rcx, 1Fh
0x180027ca6  or      rcx, rax
0x180027ca9  mov     [rdi], rcx
0x180027cac  xor     ebx, ebx
0x180027cae  lea     rcx, [rsp+260h+var_230]
0x180027cb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027cb8  mov     eax, ebx
0x180027cba  mov     rcx, [rbp+160h+var_10]
0x180027cc1  xor     rcx, rsp; StackCookie
0x180027cc4  call    __security_check_cookie
0x180027cc9  lea     r11, [rsp+260h+var_s0]
0x180027cd1  mov     rbx, [r11+18h]
0x180027cd5  mov     rdi, [r11+28h]
0x180027cd9  mov     rsp, r11
0x180027cdc  pop     rbp
0x180027cdd  retn
```
