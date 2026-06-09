# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c150`
- end: `0x18000c2ff`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008f7c`

## callees

- `0x180005210`
- `0x180006584`
- `0x180008c10`
- `0x180009fd0`
- `0x18000b344`
- `0x18000b364`
- `0x18000c150`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c1b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c250`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c1b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1c4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
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
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
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
0x18000c150  mov     [rsp-8+arg_8], rbx
0x18000c155  mov     [rsp-8+arg_18], rdi
0x18000c15a  push    rbp
0x18000c15b  lea     rbp, [rsp-160h]
0x18000c163  sub     rsp, 260h
0x18000c16a  mov     rax, cs:__security_cookie
0x18000c171  xor     rax, rsp
0x18000c174  mov     [rbp+160h+var_10], rax
0x18000c17b  mov     rdi, r8
0x18000c17e  mov     qword ptr [r8], 0
0x18000c185  mov     r8, rcx; unsigned __int16 *
0x18000c188  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c18d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c192  lea     r8, aP0; "_p0"
0x18000c199  mov     edx, 104h; unsigned __int64
0x18000c19e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c1a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c1a8  lea     r8, [rsp+260h+Name]; lpName
0x18000c1ad  xor     edx, edx; bInheritHandle
0x18000c1af  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c1b4  call    cs:__imp_OpenSemaphoreW
0x18000c1ba  mov     [rsp+260h+var_230], rax
0x18000c1bf  test    rax, rax
0x18000c1c2  jnz     short loc_18000C1EB
0x18000c1c4  call    cs:__imp_GetLastError
0x18000c1ca  cmp     eax, 2
0x18000c1cd  jz      loc_18000C2CD
0x18000c1d3  mov     rcx, [rbp+168h]; this
0x18000c1da  mov     edx, 0D0h; void *
0x18000c1df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c1e4  mov     ebx, eax
0x18000c1e6  jmp     loc_18000C2CF
0x18000c1eb  lea     rdx, [rsp+260h+var_23C]; int *
0x18000c1f0  mov     [rsp+260h+var_23C], 0
0x18000c1f8  mov     rcx, rax; hHandle
0x18000c1fb  mov     [rsp+260h+var_240], 0; int
0x18000c203  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c208  mov     ebx, eax
0x18000c20a  test    eax, eax
0x18000c20c  jns     short loc_18000C22E
0x18000c20e  mov     rcx, [rbp+168h]; this
0x18000c215  lea     r8, aWil; "wil"
0x18000c21c  mov     r9d, eax; char *
0x18000c21f  mov     edx, 0D6h; void *
0x18000c224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c229  jmp     loc_18000C2CF
0x18000c22e  lea     r8, asc_180013DC0; "h"
0x18000c235  mov     edx, 104h; unsigned __int64
0x18000c23a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c23f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c244  lea     r8, [rsp+260h+Name]; lpName
0x18000c249  xor     edx, edx; bInheritHandle
0x18000c24b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c250  call    cs:__imp_OpenSemaphoreW
0x18000c256  mov     [rsp+260h+var_238], rax
0x18000c25b  test    rax, rax
0x18000c25e  jnz     short loc_18000C27F
0x18000c260  mov     rcx, [rbp+168h]; this
0x18000c267  mov     edx, 0DCh; void *
0x18000c26c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c271  mov     ebx, eax
0x18000c273  lea     rcx, [rsp+260h+var_238]
0x18000c278  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c27d  jmp     short loc_18000C2CF
0x18000c27f  lea     rdx, [rsp+260h+var_240]; int *
0x18000c284  mov     rcx, rax; hHandle
0x18000c287  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c28c  mov     ebx, eax
0x18000c28e  test    eax, eax
0x18000c290  jns     short loc_18000C2AF
0x18000c292  mov     rcx, [rbp+168h]; this
0x18000c299  lea     r8, aWil; "wil"
0x18000c2a0  mov     r9d, eax; char *
0x18000c2a3  mov     edx, 0DEh; void *
0x18000c2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2ad  jmp     short loc_18000C273
0x18000c2af  lea     rcx, [rsp+260h+var_238]
0x18000c2b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c2b9  movsxd  rcx, [rsp+260h+var_240]
0x18000c2be  movsxd  rax, [rsp+260h+var_23C]
0x18000c2c3  shl     rcx, 1Fh
0x18000c2c7  or      rcx, rax
0x18000c2ca  mov     [rdi], rcx
0x18000c2cd  xor     ebx, ebx
0x18000c2cf  lea     rcx, [rsp+260h+var_230]
0x18000c2d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c2d9  mov     eax, ebx
0x18000c2db  mov     rcx, [rbp+160h+var_10]
0x18000c2e2  xor     rcx, rsp; StackCookie
0x18000c2e5  call    __security_check_cookie
0x18000c2ea  lea     r11, [rsp+260h+var_s0]
0x18000c2f2  mov     rbx, [r11+18h]
0x18000c2f6  mov     rdi, [r11+28h]
0x18000c2fa  mov     rsp, r11
0x18000c2fd  pop     rbp
0x18000c2fe  retn
```
