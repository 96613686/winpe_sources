# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800108b8`
- end: `0x180010a76`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800204a8`

## callees

- `0x180007720`
- `0x1800108b8`
- `0x180010a7c`
- `0x180010b08`
- `0x1800112a4`
- `0x1800112c8`
- `0x18001af70`
- `0x18001e660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010921`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800109c1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010921`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800109c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010931`

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
0x1800108b8  mov     [rsp-8+arg_8], rbx
0x1800108bd  push    rbp
0x1800108be  push    rdi
0x1800108bf  push    r14
0x1800108c1  lea     rbp, [rsp-160h]
0x1800108c9  sub     rsp, 260h
0x1800108d0  mov     rax, cs:__security_cookie
0x1800108d7  xor     rax, rsp
0x1800108da  mov     [rbp+170h+var_20], rax
0x1800108e1  mov     rdi, r8
0x1800108e4  mov     qword ptr [r8], 0
0x1800108eb  mov     r8, rcx; unsigned __int16 *
0x1800108ee  mov     r14d, 104h
0x1800108f4  mov     edx, r14d; unsigned __int64
0x1800108f7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800108fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010901  lea     r8, aP0; "_p0"
0x180010908  mov     edx, r14d; unsigned __int64
0x18001090b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010910  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010915  lea     r8, [rsp+270h+Name]; lpName
0x18001091a  xor     edx, edx; bInheritHandle
0x18001091c  mov     ecx, 1F0003h; dwDesiredAccess
0x180010921  call    cs:__imp_OpenSemaphoreW
0x180010927  mov     [rsp+270h+var_240], rax
0x18001092c  test    rax, rax
0x18001092f  jnz     short loc_18001095E
0x180010931  call    cs:__imp_GetLastError
0x180010937  cmp     eax, 2
0x18001093a  jz      loc_180010A45
0x180010940  mov     rcx, [rbp+178h]; this
0x180010947  lea     r8, aWil; "wil"
0x18001094e  lea     edx, [r14-34h]; void *
0x180010952  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010957  mov     ebx, eax
0x180010959  jmp     loc_180010A47
0x18001095e  lea     rdx, [rsp+270h+var_24C]; int *
0x180010963  mov     [rsp+270h+var_24C], 0
0x18001096b  mov     rcx, rax; hHandle
0x18001096e  mov     [rsp+270h+var_250], 0; int
0x180010976  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001097b  mov     ebx, eax
0x18001097d  test    eax, eax
0x18001097f  jns     short loc_1800109A1
0x180010981  mov     rcx, [rbp+178h]; this
0x180010988  lea     r8, aWil; "wil"
0x18001098f  mov     r9d, eax; char *
0x180010992  mov     edx, 0D6h; void *
0x180010997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001099c  jmp     loc_180010A47
0x1800109a1  lea     r8, asc_180049078; "h"
0x1800109a8  mov     rdx, r14; unsigned __int64
0x1800109ab  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800109b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800109b5  lea     r8, [rsp+270h+Name]; lpName
0x1800109ba  xor     edx, edx; bInheritHandle
0x1800109bc  mov     ecx, 1F0003h; dwDesiredAccess
0x1800109c1  call    cs:__imp_OpenSemaphoreW
0x1800109c7  mov     [rsp+270h+var_248], rax
0x1800109cc  test    rax, rax
0x1800109cf  jnz     short loc_1800109F7
0x1800109d1  mov     rcx, [rbp+178h]; this
0x1800109d8  lea     r8, aWil; "wil"
0x1800109df  mov     edx, 0DCh; void *
0x1800109e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800109e9  mov     ebx, eax
0x1800109eb  lea     rcx, [rsp+270h+var_248]
0x1800109f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800109f5  jmp     short loc_180010A47
0x1800109f7  lea     rdx, [rsp+270h+var_250]; int *
0x1800109fc  mov     rcx, rax; hHandle
0x1800109ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010a04  mov     ebx, eax
0x180010a06  test    eax, eax
0x180010a08  jns     short loc_180010A27
0x180010a0a  mov     rcx, [rbp+178h]; this
0x180010a11  lea     r8, aWil; "wil"
0x180010a18  mov     r9d, eax; char *
0x180010a1b  mov     edx, 0DEh; void *
0x180010a20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a25  jmp     short loc_1800109EB
0x180010a27  lea     rcx, [rsp+270h+var_248]
0x180010a2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010a31  movsxd  rcx, [rsp+270h+var_250]
0x180010a36  movsxd  rax, [rsp+270h+var_24C]
0x180010a3b  shl     rcx, 1Fh
0x180010a3f  or      rcx, rax
0x180010a42  mov     [rdi], rcx
0x180010a45  xor     ebx, ebx
0x180010a47  lea     rcx, [rsp+270h+var_240]
0x180010a4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010a51  mov     eax, ebx
0x180010a53  mov     rcx, [rbp+170h+var_20]
0x180010a5a  xor     rcx, rsp; StackCookie
0x180010a5d  call    __security_check_cookie
0x180010a62  mov     rbx, [rsp+270h+arg_8]
0x180010a6a  add     rsp, 260h
0x180010a71  pop     r14
0x180010a73  pop     rdi
0x180010a74  pop     rbp
0x180010a75  retn
```
