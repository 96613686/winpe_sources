# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800c7ac0`
- end: `0x1800c7c62`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c7a4c`

## callees

- `0x1800094d4`
- `0x180018924`
- `0x1800c4290`
- `0x1800c5624`
- `0x1800c704c`
- `0x1800c706c`
- `0x1800c7ac0`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c7b29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c7bbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c7b29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c7bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b39`

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
0x1800c7ac0  mov     [rsp-8+arg_8], rbx
0x1800c7ac5  push    rbp
0x1800c7ac6  push    rdi
0x1800c7ac7  push    r14
0x1800c7ac9  lea     rbp, [rsp-160h]
0x1800c7ad1  sub     rsp, 260h
0x1800c7ad8  mov     rax, cs:__security_cookie
0x1800c7adf  xor     rax, rsp
0x1800c7ae2  mov     [rbp+170h+var_20], rax
0x1800c7ae9  mov     rdi, r8
0x1800c7aec  mov     qword ptr [r8], 0
0x1800c7af3  mov     r8, rcx; unsigned __int16 *
0x1800c7af6  mov     r14d, 104h
0x1800c7afc  mov     edx, r14d; unsigned __int64
0x1800c7aff  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c7b04  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c7b09  lea     r8, aP0; "_p0"
0x1800c7b10  mov     edx, r14d; unsigned __int64
0x1800c7b13  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c7b18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c7b1d  lea     r8, [rsp+270h+Name]; lpName
0x1800c7b22  xor     edx, edx; bInheritHandle
0x1800c7b24  mov     ecx, 1F0003h; dwDesiredAccess
0x1800c7b29  call    cs:__imp_OpenSemaphoreW
0x1800c7b2f  mov     [rsp+270h+var_240], rax
0x1800c7b34  test    rax, rax
0x1800c7b37  jnz     short loc_1800C7B5F
0x1800c7b39  call    cs:__imp_GetLastError
0x1800c7b3f  cmp     eax, 2
0x1800c7b42  jz      loc_1800C7C31
0x1800c7b48  mov     rcx, [rbp+178h]; this
0x1800c7b4f  lea     edx, [r14-34h]; void *
0x1800c7b53  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c7b58  mov     ebx, eax
0x1800c7b5a  jmp     loc_1800C7C33
0x1800c7b5f  lea     rdx, [rsp+270h+var_24C]; int *
0x1800c7b64  mov     [rsp+270h+var_24C], 0
0x1800c7b6c  mov     rcx, rax; hHandle
0x1800c7b6f  mov     [rsp+270h+var_250], 0; int
0x1800c7b77  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800c7b7c  mov     ebx, eax
0x1800c7b7e  test    eax, eax
0x1800c7b80  jns     short loc_1800C7B9B
0x1800c7b82  mov     rcx, [rbp+178h]; this
0x1800c7b89  mov     r9d, eax; char *
0x1800c7b8c  mov     edx, 0D6h; void *
0x1800c7b91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7b96  jmp     loc_1800C7C33
0x1800c7b9b  lea     r8, asc_18017C728; "h"
0x1800c7ba2  mov     rdx, r14; unsigned __int64
0x1800c7ba5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c7baa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c7baf  lea     r8, [rsp+270h+Name]; lpName
0x1800c7bb4  xor     edx, edx; bInheritHandle
0x1800c7bb6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800c7bbb  call    cs:__imp_OpenSemaphoreW
0x1800c7bc1  mov     [rsp+270h+var_248], rax
0x1800c7bc6  test    rax, rax
0x1800c7bc9  jnz     short loc_1800C7BEA
0x1800c7bcb  mov     rcx, [rbp+178h]; this
0x1800c7bd2  mov     edx, 0DCh; void *
0x1800c7bd7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c7bdc  mov     ebx, eax
0x1800c7bde  lea     rcx, [rsp+270h+var_248]
0x1800c7be3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c7be8  jmp     short loc_1800C7C33
0x1800c7bea  lea     rdx, [rsp+270h+var_250]; int *
0x1800c7bef  mov     rcx, rax; hHandle
0x1800c7bf2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800c7bf7  mov     ebx, eax
0x1800c7bf9  test    eax, eax
0x1800c7bfb  jns     short loc_1800C7C13
0x1800c7bfd  mov     rcx, [rbp+178h]; this
0x1800c7c04  mov     r9d, eax; char *
0x1800c7c07  mov     edx, 0DEh; void *
0x1800c7c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7c11  jmp     short loc_1800C7BDE
0x1800c7c13  lea     rcx, [rsp+270h+var_248]
0x1800c7c18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c7c1d  movsxd  rcx, [rsp+270h+var_250]
0x1800c7c22  movsxd  rax, [rsp+270h+var_24C]
0x1800c7c27  shl     rcx, 1Fh
0x1800c7c2b  or      rcx, rax
0x1800c7c2e  mov     [rdi], rcx
0x1800c7c31  xor     ebx, ebx
0x1800c7c33  lea     rcx, [rsp+270h+var_240]
0x1800c7c38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c7c3d  mov     eax, ebx
0x1800c7c3f  mov     rcx, [rbp+170h+var_20]
0x1800c7c46  xor     rcx, rsp; StackCookie
0x1800c7c49  call    __security_check_cookie
0x1800c7c4e  mov     rbx, [rsp+270h+arg_8]
0x1800c7c56  add     rsp, 260h
0x1800c7c5d  pop     r14
0x1800c7c5f  pop     rdi
0x1800c7c60  pop     rbp
0x1800c7c61  retn
```
