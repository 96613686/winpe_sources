# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180055aec`
- end: `0x180055c8e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180055a78`

## callees

- `0x18002da28`
- `0x18004ece0`
- `0x1800511d0`
- `0x180052f7c`
- `0x180054ddc`
- `0x180054e04`
- `0x1800556d0`
- `0x180055aec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180055b55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180055be7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180055b55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180055be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b65`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180055aec  mov     [rsp-8+arg_8], rbx
0x180055af1  push    rbp
0x180055af2  push    rdi
0x180055af3  push    r14
0x180055af5  lea     rbp, [rsp-160h]
0x180055afd  sub     rsp, 260h
0x180055b04  mov     rax, cs:__security_cookie
0x180055b0b  xor     rax, rsp
0x180055b0e  mov     [rbp+170h+var_20], rax
0x180055b15  mov     rdi, r8
0x180055b18  mov     qword ptr [r8], 0
0x180055b1f  mov     r8, rcx; unsigned __int16 *
0x180055b22  mov     r14d, 104h
0x180055b28  mov     edx, r14d; unsigned __int64
0x180055b2b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180055b30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055b35  lea     r8, aP0; "_p0"
0x180055b3c  mov     edx, r14d; unsigned __int64
0x180055b3f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180055b44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180055b49  lea     r8, [rsp+270h+Name]; lpName
0x180055b4e  xor     edx, edx; bInheritHandle
0x180055b50  mov     ecx, 1F0003h; dwDesiredAccess
0x180055b55  call    cs:__imp_OpenSemaphoreW
0x180055b5b  mov     [rsp+270h+var_240], rax
0x180055b60  test    rax, rax
0x180055b63  jnz     short loc_180055B8B
0x180055b65  call    cs:__imp_GetLastError
0x180055b6b  cmp     eax, 2
0x180055b6e  jz      loc_180055C5D
0x180055b74  mov     rcx, [rbp+178h]; this
0x180055b7b  lea     edx, [r14-34h]; void *
0x180055b7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055b84  mov     ebx, eax
0x180055b86  jmp     loc_180055C5F
0x180055b8b  lea     rdx, [rsp+270h+var_24C]; int *
0x180055b90  mov     [rsp+270h+var_24C], 0
0x180055b98  mov     rcx, rax; hHandle
0x180055b9b  mov     [rsp+270h+var_250], 0; int
0x180055ba3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055ba8  mov     ebx, eax
0x180055baa  test    eax, eax
0x180055bac  jns     short loc_180055BC7
0x180055bae  mov     rcx, [rbp+178h]; this
0x180055bb5  mov     r9d, eax; char *
0x180055bb8  mov     edx, 0D6h; void *
0x180055bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055bc2  jmp     loc_180055C5F
0x180055bc7  lea     r8, asc_18009A758; "h"
0x180055bce  mov     rdx, r14; unsigned __int64
0x180055bd1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180055bd6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180055bdb  lea     r8, [rsp+270h+Name]; lpName
0x180055be0  xor     edx, edx; bInheritHandle
0x180055be2  mov     ecx, 1F0003h; dwDesiredAccess
0x180055be7  call    cs:__imp_OpenSemaphoreW
0x180055bed  mov     [rsp+270h+var_248], rax
0x180055bf2  test    rax, rax
0x180055bf5  jnz     short loc_180055C16
0x180055bf7  mov     rcx, [rbp+178h]; this
0x180055bfe  mov     edx, 0DCh; void *
0x180055c03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055c08  mov     ebx, eax
0x180055c0a  lea     rcx, [rsp+270h+var_248]
0x180055c0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055c14  jmp     short loc_180055C5F
0x180055c16  lea     rdx, [rsp+270h+var_250]; int *
0x180055c1b  mov     rcx, rax; hHandle
0x180055c1e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055c23  mov     ebx, eax
0x180055c25  test    eax, eax
0x180055c27  jns     short loc_180055C3F
0x180055c29  mov     rcx, [rbp+178h]; this
0x180055c30  mov     r9d, eax; char *
0x180055c33  mov     edx, 0DEh; void *
0x180055c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055c3d  jmp     short loc_180055C0A
0x180055c3f  lea     rcx, [rsp+270h+var_248]
0x180055c44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055c49  movsxd  rcx, [rsp+270h+var_250]
0x180055c4e  movsxd  rax, [rsp+270h+var_24C]
0x180055c53  shl     rcx, 1Fh
0x180055c57  or      rcx, rax
0x180055c5a  mov     [rdi], rcx
0x180055c5d  xor     ebx, ebx
0x180055c5f  lea     rcx, [rsp+270h+var_240]
0x180055c64  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055c69  mov     eax, ebx
0x180055c6b  mov     rcx, [rbp+170h+var_20]
0x180055c72  xor     rcx, rsp; StackCookie
0x180055c75  call    __security_check_cookie
0x180055c7a  mov     rbx, [rsp+270h+arg_8]
0x180055c82  add     rsp, 260h
0x180055c89  pop     r14
0x180055c8b  pop     rdi
0x180055c8c  pop     rbp
0x180055c8d  retn
```
