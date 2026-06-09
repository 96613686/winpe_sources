# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180084af4`
- end: `0x180084cfd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `521`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800bcfb8`

## callees

- `0x1800238b0`
- `0x1800448f4`
- `0x180062848`
- `0x180065b50`
- `0x180084ac8`
- `0x180084af4`
- `0x18009c310`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180084b5d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180084c21`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180084b5d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180084c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084b6d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v8; // rax
  int v9; // eax
  wil::details *v11; // [rsp+28h] [rbp-D8h]
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v14; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v15[0] = v5;
  if ( v5 )
  {
    v13 = 0;
    v12 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v13);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      LODWORD(v11) = ValueFromSemaphore;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::TryGetValueInternal",
        "GetValueFromSemaphore(semaphoreLow.get(), &countLow)",
        v11,
        v12);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v8 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v14 = v8;
    if ( v8 )
    {
      v9 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v8, &v12);
      LastError = v9;
      if ( v9 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
        *a3 = v13 | (unsigned __int64)((__int64)v12 << 31);
        goto LABEL_12;
      }
      LODWORD(v11) = v9;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::TryGetValueInternal",
        "GetValueFromSemaphore(semaphoreHigh.get(), &countHigh)",
        v11,
        v12);
    }
    else
    {
      LastError = wil::details::in1diag5::Return_GetLastError(
                    retaddr,
                    (void *)0xDC,
                    (unsigned int)"wil",
                    "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                    "semaphoreHigh",
                    (const char *)v11);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag5::Return_GetLastError(
                retaddr,
                (void *)0xD0,
                (unsigned int)"wil",
                "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                0,
                (const char *)v11);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
  return LastError;
}

```

## disassembly

```asm
0x180084af4  mov     [rsp-8+arg_8], rbx
0x180084af9  push    rbp
0x180084afa  push    rdi
0x180084afb  push    r14
0x180084afd  lea     rbp, [rsp-170h]
0x180084b05  sub     rsp, 270h
0x180084b0c  mov     rax, cs:__security_cookie
0x180084b13  xor     rax, rsp
0x180084b16  mov     [rbp+180h+var_20], rax
0x180084b1d  mov     rdi, r8
0x180084b20  mov     qword ptr [r8], 0
0x180084b27  mov     r8, rcx; unsigned __int16 *
0x180084b2a  mov     r14d, 104h
0x180084b30  mov     edx, r14d; unsigned __int64
0x180084b33  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180084b38  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180084b3d  lea     r8, aP0; "_p0"
0x180084b44  mov     edx, r14d; unsigned __int64
0x180084b47  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180084b4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180084b51  lea     r8, [rsp+280h+Name]; lpName
0x180084b56  xor     edx, edx; bInheritHandle
0x180084b58  mov     ecx, 1F0003h; dwDesiredAccess
0x180084b5d  call    cs:__imp_OpenSemaphoreW
0x180084b63  mov     [rsp+280h+var_240], rax
0x180084b68  test    rax, rax
0x180084b6b  jnz     short loc_180084BAA
0x180084b6d  call    cs:__imp_GetLastError
0x180084b73  cmp     eax, 2
0x180084b76  jz      loc_180084CCC
0x180084b7c  mov     rcx, [rbp+188h]; this
0x180084b83  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180084b8a  lea     r8, aWil; "wil"
0x180084b91  mov     [rsp+280h+var_260], 0; char *
0x180084b9a  lea     edx, [r14-34h]; void *
0x180084b9e  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180084ba3  mov     ebx, eax
0x180084ba5  jmp     loc_180084CCE
0x180084baa  lea     rdx, [rsp+280h+var_24C]; int *
0x180084baf  mov     [rsp+280h+var_24C], 0
0x180084bb7  mov     rcx, rax; hHandle
0x180084bba  mov     [rsp+280h+var_250], 0; int
0x180084bc2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180084bc7  mov     ebx, eax
0x180084bc9  test    eax, eax
0x180084bcb  jns     short loc_180084C01
0x180084bcd  mov     rcx, [rbp+188h]; this
0x180084bd4  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180084bdb  mov     dword ptr [rsp+280h+var_258], eax; wil::details *
0x180084bdf  lea     r8, aWil; "wil"
0x180084be6  lea     rax, aGetvaluefromse_0; "GetValueFromSemaphore(semaphoreLow.get("...
0x180084bed  mov     edx, 0D6h; void *
0x180084bf2  mov     [rsp+280h+var_260], rax; char *
0x180084bf7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180084bfc  jmp     loc_180084CCE
0x180084c01  lea     r8, asc_180172790; "h"
0x180084c08  mov     rdx, r14; unsigned __int64
0x180084c0b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180084c10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180084c15  lea     r8, [rsp+280h+Name]; lpName
0x180084c1a  xor     edx, edx; bInheritHandle
0x180084c1c  mov     ecx, 1F0003h; dwDesiredAccess
0x180084c21  call    cs:__imp_OpenSemaphoreW
0x180084c27  mov     [rsp+280h+var_248], rax
0x180084c2c  test    rax, rax
0x180084c2f  jnz     short loc_180084C6A
0x180084c31  mov     rcx, [rbp+188h]; this
0x180084c38  lea     rax, aSemaphorehigh; "semaphoreHigh"
0x180084c3f  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180084c46  mov     [rsp+280h+var_260], rax; char *
0x180084c4b  lea     r8, aWil; "wil"
0x180084c52  mov     edx, 0DCh; void *
0x180084c57  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180084c5c  mov     ebx, eax
0x180084c5e  lea     rcx, [rsp+280h+var_248]
0x180084c63  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180084c68  jmp     short loc_180084CCE
0x180084c6a  lea     rdx, [rsp+280h+var_250]; int *
0x180084c6f  mov     rcx, rax; hHandle
0x180084c72  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180084c77  mov     ebx, eax
0x180084c79  test    eax, eax
0x180084c7b  jns     short loc_180084CAE
0x180084c7d  mov     rcx, [rbp+188h]; this
0x180084c84  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180084c8b  mov     dword ptr [rsp+280h+var_258], eax; wil::details *
0x180084c8f  lea     r8, aWil; "wil"
0x180084c96  lea     rax, aGetvaluefromse; "GetValueFromSemaphore(semaphoreHigh.get"...
0x180084c9d  mov     edx, 0DEh; void *
0x180084ca2  mov     [rsp+280h+var_260], rax; char *
0x180084ca7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180084cac  jmp     short loc_180084C5E
0x180084cae  lea     rcx, [rsp+280h+var_248]
0x180084cb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180084cb8  movsxd  rcx, [rsp+280h+var_250]
0x180084cbd  movsxd  rax, [rsp+280h+var_24C]
0x180084cc2  shl     rcx, 1Fh
0x180084cc6  or      rcx, rax
0x180084cc9  mov     [rdi], rcx
0x180084ccc  xor     ebx, ebx
0x180084cce  lea     rcx, [rsp+280h+var_240]
0x180084cd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180084cd8  mov     eax, ebx
0x180084cda  mov     rcx, [rbp+180h+var_20]
0x180084ce1  xor     rcx, rsp; StackCookie
0x180084ce4  call    __security_check_cookie
0x180084ce9  mov     rbx, [rsp+280h+arg_8]
0x180084cf1  add     rsp, 270h
0x180084cf8  pop     r14
0x180084cfa  pop     rdi
0x180084cfb  pop     rbp
0x180084cfc  retn
```
