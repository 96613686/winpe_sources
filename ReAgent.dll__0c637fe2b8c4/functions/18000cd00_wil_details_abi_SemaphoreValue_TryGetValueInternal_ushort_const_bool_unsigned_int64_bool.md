# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000cd00`
- end: `0x18000ceac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000cc8c`

## callees

- `0x180006ed8`
- `0x1800089f8`
- `0x18000a0b0`
- `0x18000bf1c`
- `0x18000bf44`
- `0x18000c658`
- `0x18000cd00`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cd83`
- `KERNEL32!GetLastError` at `0x18000cd83`
- `KERNEL32!OpenSemaphoreW` at `0x18000cd73`
- `KERNEL32!OpenSemaphoreW` at `0x18000ce05`
- `KERNEL32!OpenSemaphoreW` at `0x18000cd73`
- `KERNEL32!OpenSemaphoreW` at `0x18000ce05`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v17[2]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE v18; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v19[1] = -2;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19[0] = v5;
  if ( v5 )
  {
    v17[1] = 0;
    v17[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v17[1]);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        v10,
        (const char *)(unsigned int)ValueFromSemaphore,
        v17[0]);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v18 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
        *a3 = v17[1] | (unsigned __int64)((__int64)v17[0] << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17[0]);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
  return LastError;
}

```

## disassembly

```asm
0x18000cd00  mov     rax, rsp
0x18000cd03  push    rbp
0x18000cd04  push    rdi
0x18000cd05  push    r14
0x18000cd07  lea     rbp, [rax-178h]
0x18000cd0e  sub     rsp, 260h
0x18000cd15  mov     qword ptr [rsp+270h+var_238], 0FFFFFFFFFFFFFFFEh
0x18000cd1e  mov     [rax+10h], rbx
0x18000cd22  mov     rax, cs:__security_cookie
0x18000cd29  xor     rax, rsp
0x18000cd2c  mov     [rbp+170h+var_20], rax
0x18000cd33  mov     rdi, r8
0x18000cd36  mov     qword ptr [r8], 0
0x18000cd3d  mov     r8, rcx; unsigned __int16 *
0x18000cd40  mov     r14d, 104h
0x18000cd46  mov     edx, r14d; unsigned __int64
0x18000cd49  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000cd4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cd53  lea     r8, aP0; "_p0"
0x18000cd5a  mov     edx, r14d; unsigned __int64
0x18000cd5d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000cd62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd67  lea     r8, [rsp+270h+Name]; lpName
0x18000cd6c  xor     edx, edx; bInheritHandle
0x18000cd6e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cd73  call    cs:__imp_OpenSemaphoreW
0x18000cd79  mov     [rsp+270h+var_240], rax
0x18000cd7e  test    rax, rax
0x18000cd81  jnz     short loc_18000CDA9
0x18000cd83  call    cs:__imp_GetLastError
0x18000cd89  cmp     eax, 2
0x18000cd8c  jz      loc_18000CE7B
0x18000cd92  mov     rcx, [rbp+178h]; this
0x18000cd99  lea     edx, [r14-34h]; void *
0x18000cd9d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cda2  mov     ebx, eax
0x18000cda4  jmp     loc_18000CE7D
0x18000cda9  mov     [rsp+270h+var_250+4], 0
0x18000cdb1  mov     [rsp+270h+var_250], 0; int
0x18000cdb9  lea     rdx, [rsp+270h+var_250+4]; int *
0x18000cdbe  mov     rcx, rax; hHandle
0x18000cdc1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cdc6  mov     ebx, eax
0x18000cdc8  test    eax, eax
0x18000cdca  jns     short loc_18000CDE5
0x18000cdcc  mov     rcx, [rbp+178h]; this
0x18000cdd3  mov     r9d, eax; char *
0x18000cdd6  mov     edx, 0D6h; void *
0x18000cddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cde0  jmp     loc_18000CE7D
0x18000cde5  lea     r8, asc_180064548; "h"
0x18000cdec  mov     rdx, r14; unsigned __int64
0x18000cdef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000cdf4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cdf9  lea     r8, [rsp+270h+Name]; lpName
0x18000cdfe  xor     edx, edx; bInheritHandle
0x18000ce00  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ce05  call    cs:__imp_OpenSemaphoreW
0x18000ce0b  mov     [rsp+270h+var_248], rax
0x18000ce10  test    rax, rax
0x18000ce13  jnz     short loc_18000CE34
0x18000ce15  mov     rcx, [rbp+178h]; this
0x18000ce1c  mov     edx, 0DCh; void *
0x18000ce21  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ce26  mov     ebx, eax
0x18000ce28  lea     rcx, [rsp+270h+var_248]
0x18000ce2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ce32  jmp     short loc_18000CE7D
0x18000ce34  lea     rdx, [rsp+270h+var_250]; int *
0x18000ce39  mov     rcx, rax; hHandle
0x18000ce3c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ce41  mov     ebx, eax
0x18000ce43  test    eax, eax
0x18000ce45  jns     short loc_18000CE5D
0x18000ce47  mov     rcx, [rbp+178h]; this
0x18000ce4e  mov     r9d, eax; char *
0x18000ce51  mov     edx, 0DEh; void *
0x18000ce56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce5b  jmp     short loc_18000CE28
0x18000ce5d  lea     rcx, [rsp+270h+var_248]
0x18000ce62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ce67  movsxd  rcx, [rsp+270h+var_250]
0x18000ce6c  shl     rcx, 1Fh
0x18000ce70  movsxd  rax, [rsp+270h+var_250+4]
0x18000ce75  or      rcx, rax
0x18000ce78  mov     [rdi], rcx
0x18000ce7b  xor     ebx, ebx
0x18000ce7d  lea     rcx, [rsp+270h+var_240]
0x18000ce82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ce87  mov     eax, ebx
0x18000ce89  mov     rcx, [rbp+170h+var_20]
0x18000ce90  xor     rcx, rsp; StackCookie
0x18000ce93  call    __security_check_cookie
0x18000ce98  mov     rbx, [rsp+270h+arg_8]
0x18000cea0  add     rsp, 260h
0x18000cea7  pop     r14
0x18000cea9  pop     rdi
0x18000ceaa  pop     rbp
0x18000ceab  retn
```
