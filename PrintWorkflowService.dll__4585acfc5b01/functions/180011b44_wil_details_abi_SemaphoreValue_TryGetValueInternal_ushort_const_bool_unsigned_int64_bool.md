# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011b44`
- end: `0x180011d02`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011ac0`

## callees

- `0x180003ca0`
- `0x18000a128`
- `0x18000db14`
- `0x180010aec`
- `0x180010b0c`
- `0x1800113d4`
- `0x180011460`
- `0x180011b44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011bad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011c4d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011bad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bbd`

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
0x180011b44  mov     [rsp-8+arg_8], rbx
0x180011b49  push    rbp
0x180011b4a  push    rdi
0x180011b4b  push    r14
0x180011b4d  lea     rbp, [rsp-160h]
0x180011b55  sub     rsp, 260h
0x180011b5c  mov     rax, cs:__security_cookie
0x180011b63  xor     rax, rsp
0x180011b66  mov     [rbp+170h+var_20], rax
0x180011b6d  mov     rdi, r8
0x180011b70  mov     qword ptr [r8], 0
0x180011b77  mov     r8, rcx; unsigned __int16 *
0x180011b7a  mov     r14d, 104h
0x180011b80  mov     edx, r14d; unsigned __int64
0x180011b83  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011b88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011b8d  lea     r8, aP0; "_p0"
0x180011b94  mov     edx, r14d; unsigned __int64
0x180011b97  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011b9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011ba1  lea     r8, [rsp+270h+Name]; lpName
0x180011ba6  xor     edx, edx; bInheritHandle
0x180011ba8  mov     ecx, 1F0003h; dwDesiredAccess
0x180011bad  call    cs:__imp_OpenSemaphoreW
0x180011bb3  mov     [rsp+270h+var_240], rax
0x180011bb8  test    rax, rax
0x180011bbb  jnz     short loc_180011BEA
0x180011bbd  call    cs:__imp_GetLastError
0x180011bc3  cmp     eax, 2
0x180011bc6  jz      loc_180011CD1
0x180011bcc  mov     rcx, [rbp+178h]; this
0x180011bd3  lea     r8, aWil; "wil"
0x180011bda  lea     edx, [r14-34h]; void *
0x180011bde  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011be3  mov     ebx, eax
0x180011be5  jmp     loc_180011CD3
0x180011bea  lea     rdx, [rsp+270h+var_24C]; int *
0x180011bef  mov     [rsp+270h+var_24C], 0
0x180011bf7  mov     rcx, rax; hHandle
0x180011bfa  mov     [rsp+270h+var_250], 0; int
0x180011c02  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011c07  mov     ebx, eax
0x180011c09  test    eax, eax
0x180011c0b  jns     short loc_180011C2D
0x180011c0d  mov     rcx, [rbp+178h]; this
0x180011c14  lea     r8, aWil; "wil"
0x180011c1b  mov     r9d, eax; char *
0x180011c1e  mov     edx, 0D6h; void *
0x180011c23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c28  jmp     loc_180011CD3
0x180011c2d  lea     r8, asc_1800674E0; "h"
0x180011c34  mov     rdx, r14; unsigned __int64
0x180011c37  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011c3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011c41  lea     r8, [rsp+270h+Name]; lpName
0x180011c46  xor     edx, edx; bInheritHandle
0x180011c48  mov     ecx, 1F0003h; dwDesiredAccess
0x180011c4d  call    cs:__imp_OpenSemaphoreW
0x180011c53  mov     [rsp+270h+var_248], rax
0x180011c58  test    rax, rax
0x180011c5b  jnz     short loc_180011C83
0x180011c5d  mov     rcx, [rbp+178h]; this
0x180011c64  lea     r8, aWil; "wil"
0x180011c6b  mov     edx, 0DCh; void *
0x180011c70  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011c75  mov     ebx, eax
0x180011c77  lea     rcx, [rsp+270h+var_248]
0x180011c7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011c81  jmp     short loc_180011CD3
0x180011c83  lea     rdx, [rsp+270h+var_250]; int *
0x180011c88  mov     rcx, rax; hHandle
0x180011c8b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011c90  mov     ebx, eax
0x180011c92  test    eax, eax
0x180011c94  jns     short loc_180011CB3
0x180011c96  mov     rcx, [rbp+178h]; this
0x180011c9d  lea     r8, aWil; "wil"
0x180011ca4  mov     r9d, eax; char *
0x180011ca7  mov     edx, 0DEh; void *
0x180011cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cb1  jmp     short loc_180011C77
0x180011cb3  lea     rcx, [rsp+270h+var_248]
0x180011cb8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011cbd  movsxd  rcx, [rsp+270h+var_250]
0x180011cc2  movsxd  rax, [rsp+270h+var_24C]
0x180011cc7  shl     rcx, 1Fh
0x180011ccb  or      rcx, rax
0x180011cce  mov     [rdi], rcx
0x180011cd1  xor     ebx, ebx
0x180011cd3  lea     rcx, [rsp+270h+var_240]
0x180011cd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011cdd  mov     eax, ebx
0x180011cdf  mov     rcx, [rbp+170h+var_20]
0x180011ce6  xor     rcx, rsp; StackCookie
0x180011ce9  call    __security_check_cookie
0x180011cee  mov     rbx, [rsp+270h+arg_8]
0x180011cf6  add     rsp, 260h
0x180011cfd  pop     r14
0x180011cff  pop     rdi
0x180011d00  pop     rbp
0x180011d01  retn
```
