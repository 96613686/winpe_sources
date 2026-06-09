# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007af4`
- end: `0x180007cb2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007a70`

## callees

- `0x180005e58`
- `0x180006ac0`
- `0x180007540`
- `0x180007560`
- `0x180007828`
- `0x18000791c`
- `0x180007af4`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007b5d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007bfd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007b5d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b6d`

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
0x180007af4  mov     [rsp-8+arg_8], rbx
0x180007af9  push    rbp
0x180007afa  push    rdi
0x180007afb  push    r14
0x180007afd  lea     rbp, [rsp-160h]
0x180007b05  sub     rsp, 260h
0x180007b0c  mov     rax, cs:__security_cookie
0x180007b13  xor     rax, rsp
0x180007b16  mov     [rbp+170h+var_20], rax
0x180007b1d  mov     rdi, r8
0x180007b20  mov     qword ptr [r8], 0
0x180007b27  mov     r8, rcx; unsigned __int16 *
0x180007b2a  mov     r14d, 104h
0x180007b30  mov     edx, r14d; unsigned __int64
0x180007b33  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007b38  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007b3d  lea     r8, aP0; "_p0"
0x180007b44  mov     edx, r14d; unsigned __int64
0x180007b47  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007b4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007b51  lea     r8, [rsp+270h+Name]; lpName
0x180007b56  xor     edx, edx; bInheritHandle
0x180007b58  mov     ecx, 1F0003h; dwDesiredAccess
0x180007b5d  call    cs:__imp_OpenSemaphoreW
0x180007b63  mov     [rsp+270h+var_240], rax
0x180007b68  test    rax, rax
0x180007b6b  jnz     short loc_180007B9A
0x180007b6d  call    cs:__imp_GetLastError
0x180007b73  cmp     eax, 2
0x180007b76  jz      loc_180007C81
0x180007b7c  mov     rcx, [rbp+178h]; this
0x180007b83  lea     r8, aWil; "wil"
0x180007b8a  lea     edx, [r14-34h]; void *
0x180007b8e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007b93  mov     ebx, eax
0x180007b95  jmp     loc_180007C83
0x180007b9a  lea     rdx, [rsp+270h+var_24C]; int *
0x180007b9f  mov     [rsp+270h+var_24C], 0
0x180007ba7  mov     rcx, rax; hHandle
0x180007baa  mov     [rsp+270h+var_250], 0; int
0x180007bb2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007bb7  mov     ebx, eax
0x180007bb9  test    eax, eax
0x180007bbb  jns     short loc_180007BDD
0x180007bbd  mov     rcx, [rbp+178h]; this
0x180007bc4  lea     r8, aWil; "wil"
0x180007bcb  mov     r9d, eax; char *
0x180007bce  mov     edx, 0D6h; void *
0x180007bd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bd8  jmp     loc_180007C83
0x180007bdd  lea     r8, asc_1800630F8; "h"
0x180007be4  mov     rdx, r14; unsigned __int64
0x180007be7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007bec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bf1  lea     r8, [rsp+270h+Name]; lpName
0x180007bf6  xor     edx, edx; bInheritHandle
0x180007bf8  mov     ecx, 1F0003h; dwDesiredAccess
0x180007bfd  call    cs:__imp_OpenSemaphoreW
0x180007c03  mov     [rsp+270h+var_248], rax
0x180007c08  test    rax, rax
0x180007c0b  jnz     short loc_180007C33
0x180007c0d  mov     rcx, [rbp+178h]; this
0x180007c14  lea     r8, aWil; "wil"
0x180007c1b  mov     edx, 0DCh; void *
0x180007c20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007c25  mov     ebx, eax
0x180007c27  lea     rcx, [rsp+270h+var_248]
0x180007c2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007c31  jmp     short loc_180007C83
0x180007c33  lea     rdx, [rsp+270h+var_250]; int *
0x180007c38  mov     rcx, rax; hHandle
0x180007c3b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007c40  mov     ebx, eax
0x180007c42  test    eax, eax
0x180007c44  jns     short loc_180007C63
0x180007c46  mov     rcx, [rbp+178h]; this
0x180007c4d  lea     r8, aWil; "wil"
0x180007c54  mov     r9d, eax; char *
0x180007c57  mov     edx, 0DEh; void *
0x180007c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c61  jmp     short loc_180007C27
0x180007c63  lea     rcx, [rsp+270h+var_248]
0x180007c68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007c6d  movsxd  rcx, [rsp+270h+var_250]
0x180007c72  movsxd  rax, [rsp+270h+var_24C]
0x180007c77  shl     rcx, 1Fh
0x180007c7b  or      rcx, rax
0x180007c7e  mov     [rdi], rcx
0x180007c81  xor     ebx, ebx
0x180007c83  lea     rcx, [rsp+270h+var_240]
0x180007c88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007c8d  mov     eax, ebx
0x180007c8f  mov     rcx, [rbp+170h+var_20]
0x180007c96  xor     rcx, rsp; StackCookie
0x180007c99  call    __security_check_cookie
0x180007c9e  mov     rbx, [rsp+270h+arg_8]
0x180007ca6  add     rsp, 260h
0x180007cad  pop     r14
0x180007caf  pop     rdi
0x180007cb0  pop     rbp
0x180007cb1  retn
```
