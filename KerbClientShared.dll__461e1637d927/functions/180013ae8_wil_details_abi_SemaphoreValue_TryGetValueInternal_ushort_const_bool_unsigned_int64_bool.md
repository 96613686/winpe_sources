# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013ae8`
- end: `0x180013c7f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180013a74`

## callees

- `0x18000eb70`
- `0x18001053c`
- `0x180011830`
- `0x1800130d8`
- `0x1800130f8`
- `0x1800135a0`
- `0x1800135ec`
- `0x180013ae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b57`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013b47`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013bd7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013b47`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013bd7`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
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
  StringCchCopyW(Name, a2, a1);
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
0x180013ae8  mov     [rsp-8+arg_8], rbx
0x180013aed  mov     [rsp-8+arg_18], rdi
0x180013af2  push    rbp
0x180013af3  lea     rbp, [rsp-160h]
0x180013afb  sub     rsp, 260h
0x180013b02  mov     rax, cs:__security_cookie
0x180013b09  xor     rax, rsp
0x180013b0c  mov     [rbp+160h+var_10], rax
0x180013b13  mov     rdi, r8
0x180013b16  mov     qword ptr [r8], 0
0x180013b1d  mov     r8, rcx; unsigned __int16 *
0x180013b20  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013b25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013b2a  lea     r8, aP0; "_p0"
0x180013b31  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013b36  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013b3b  lea     r8, [rsp+260h+Name]; lpName
0x180013b40  xor     edx, edx; bInheritHandle
0x180013b42  mov     ecx, 1F0003h; dwDesiredAccess
0x180013b47  call    cs:__imp_OpenSemaphoreW
0x180013b4d  mov     [rsp+260h+var_230], rax
0x180013b52  test    rax, rax
0x180013b55  jnz     short loc_180013B7E
0x180013b57  call    cs:__imp_GetLastError
0x180013b5d  cmp     eax, 2
0x180013b60  jz      loc_180013C4D
0x180013b66  mov     rcx, [rbp+168h]; this
0x180013b6d  mov     edx, 0D0h; void *
0x180013b72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013b77  mov     ebx, eax
0x180013b79  jmp     loc_180013C4F
0x180013b7e  lea     rdx, [rsp+260h+var_23C]; int *
0x180013b83  mov     [rsp+260h+var_23C], 0
0x180013b8b  mov     rcx, rax; hHandle
0x180013b8e  mov     [rsp+260h+var_240], 0; int
0x180013b96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013b9b  mov     ebx, eax
0x180013b9d  test    eax, eax
0x180013b9f  jns     short loc_180013BBA
0x180013ba1  mov     rcx, [rbp+168h]; this
0x180013ba8  mov     r9d, eax; char *
0x180013bab  mov     edx, 0D6h; void *
0x180013bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bb5  jmp     loc_180013C4F
0x180013bba  lea     r8, asc_18002D410; "h"
0x180013bc1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013bc6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013bcb  lea     r8, [rsp+260h+Name]; lpName
0x180013bd0  xor     edx, edx; bInheritHandle
0x180013bd2  mov     ecx, 1F0003h; dwDesiredAccess
0x180013bd7  call    cs:__imp_OpenSemaphoreW
0x180013bdd  mov     [rsp+260h+var_238], rax
0x180013be2  test    rax, rax
0x180013be5  jnz     short loc_180013C06
0x180013be7  mov     rcx, [rbp+168h]; this
0x180013bee  mov     edx, 0DCh; void *
0x180013bf3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013bf8  mov     ebx, eax
0x180013bfa  lea     rcx, [rsp+260h+var_238]
0x180013bff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013c04  jmp     short loc_180013C4F
0x180013c06  lea     rdx, [rsp+260h+var_240]; int *
0x180013c0b  mov     rcx, rax; hHandle
0x180013c0e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013c13  mov     ebx, eax
0x180013c15  test    eax, eax
0x180013c17  jns     short loc_180013C2F
0x180013c19  mov     rcx, [rbp+168h]; this
0x180013c20  mov     r9d, eax; char *
0x180013c23  mov     edx, 0DEh; void *
0x180013c28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c2d  jmp     short loc_180013BFA
0x180013c2f  lea     rcx, [rsp+260h+var_238]
0x180013c34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013c39  movsxd  rcx, [rsp+260h+var_240]
0x180013c3e  movsxd  rax, [rsp+260h+var_23C]
0x180013c43  shl     rcx, 1Fh
0x180013c47  or      rcx, rax
0x180013c4a  mov     [rdi], rcx
0x180013c4d  xor     ebx, ebx
0x180013c4f  lea     rcx, [rsp+260h+var_230]
0x180013c54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013c59  mov     eax, ebx
0x180013c5b  mov     rcx, [rbp+160h+var_10]
0x180013c62  xor     rcx, rsp; StackCookie
0x180013c65  call    __security_check_cookie
0x180013c6a  lea     r11, [rsp+260h+var_s0]
0x180013c72  mov     rbx, [r11+18h]
0x180013c76  mov     rdi, [r11+28h]
0x180013c7a  mov     rsp, r11
0x180013c7d  pop     rbp
0x180013c7e  retn
```
