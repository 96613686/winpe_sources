# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f560`
- end: `0x18000f710`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f4dc`

## callees

- `0x1800033d0`
- `0x180006900`
- `0x180009484`
- `0x18000b990`
- `0x18000e30c`
- `0x18000ebd0`
- `0x18000ecc4`
- `0x18000f560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f5c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f662`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f5c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d9`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000f560  mov     [rsp-8+arg_8], rbx
0x18000f565  push    rbp
0x18000f566  push    rdi
0x18000f567  push    r14
0x18000f569  lea     rbp, [rsp-160h]
0x18000f571  sub     rsp, 260h
0x18000f578  mov     rax, cs:__security_cookie
0x18000f57f  xor     rax, rsp
0x18000f582  mov     [rbp+170h+var_20], rax
0x18000f589  mov     rdi, r8
0x18000f58c  mov     qword ptr [r8], 0
0x18000f593  mov     r8, rcx; unsigned __int16 *
0x18000f596  mov     r14d, 104h
0x18000f59c  mov     edx, r14d; unsigned __int64
0x18000f59f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f5a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f5a9  lea     r8, aP0; "_p0"
0x18000f5b0  mov     edx, r14d; unsigned __int64
0x18000f5b3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f5b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f5bd  lea     r8, [rsp+270h+Name]; lpName
0x18000f5c2  xor     edx, edx; bInheritHandle
0x18000f5c4  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f5c9  call    cs:__imp_OpenSemaphoreW
0x18000f5cf  mov     [rsp+270h+var_240], rax
0x18000f5d4  test    rax, rax
0x18000f5d7  jnz     short loc_18000F5FF
0x18000f5d9  call    cs:__imp_GetLastError
0x18000f5df  cmp     eax, 2
0x18000f5e2  jz      loc_18000F6DF
0x18000f5e8  mov     rcx, [rbp+178h]; this
0x18000f5ef  lea     edx, [r14-34h]; void *
0x18000f5f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f5f8  mov     ebx, eax
0x18000f5fa  jmp     loc_18000F6E1
0x18000f5ff  lea     rdx, [rsp+270h+var_24C]; int *
0x18000f604  mov     [rsp+270h+var_24C], 0
0x18000f60c  mov     rcx, rax; hHandle
0x18000f60f  mov     [rsp+270h+var_250], 0; int
0x18000f617  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f61c  mov     ebx, eax
0x18000f61e  test    eax, eax
0x18000f620  jns     short loc_18000F642
0x18000f622  mov     rcx, [rbp+178h]; this
0x18000f629  lea     r8, aWil; "wil"
0x18000f630  mov     r9d, eax; char *
0x18000f633  mov     edx, 0D6h; void *
0x18000f638  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f63d  jmp     loc_18000F6E1
0x18000f642  lea     r8, asc_180058C50; "h"
0x18000f649  mov     rdx, r14; unsigned __int64
0x18000f64c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f651  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f656  lea     r8, [rsp+270h+Name]; lpName
0x18000f65b  xor     edx, edx; bInheritHandle
0x18000f65d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f662  call    cs:__imp_OpenSemaphoreW
0x18000f668  mov     [rsp+270h+var_248], rax
0x18000f66d  test    rax, rax
0x18000f670  jnz     short loc_18000F691
0x18000f672  mov     rcx, [rbp+178h]; this
0x18000f679  mov     edx, 0DCh; void *
0x18000f67e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f683  mov     ebx, eax
0x18000f685  lea     rcx, [rsp+270h+var_248]
0x18000f68a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f68f  jmp     short loc_18000F6E1
0x18000f691  lea     rdx, [rsp+270h+var_250]; int *
0x18000f696  mov     rcx, rax; hHandle
0x18000f699  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f69e  mov     ebx, eax
0x18000f6a0  test    eax, eax
0x18000f6a2  jns     short loc_18000F6C1
0x18000f6a4  mov     rcx, [rbp+178h]; this
0x18000f6ab  lea     r8, aWil; "wil"
0x18000f6b2  mov     r9d, eax; char *
0x18000f6b5  mov     edx, 0DEh; void *
0x18000f6ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6bf  jmp     short loc_18000F685
0x18000f6c1  lea     rcx, [rsp+270h+var_248]
0x18000f6c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f6cb  movsxd  rcx, [rsp+270h+var_250]
0x18000f6d0  movsxd  rax, [rsp+270h+var_24C]
0x18000f6d5  shl     rcx, 1Fh
0x18000f6d9  or      rcx, rax
0x18000f6dc  mov     [rdi], rcx
0x18000f6df  xor     ebx, ebx
0x18000f6e1  lea     rcx, [rsp+270h+var_240]
0x18000f6e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f6eb  mov     eax, ebx
0x18000f6ed  mov     rcx, [rbp+170h+var_20]
0x18000f6f4  xor     rcx, rsp; StackCookie
0x18000f6f7  call    __security_check_cookie
0x18000f6fc  mov     rbx, [rsp+270h+arg_8]
0x18000f704  add     rsp, 260h
0x18000f70b  pop     r14
0x18000f70d  pop     rdi
0x18000f70e  pop     rbp
0x18000f70f  retn
```
