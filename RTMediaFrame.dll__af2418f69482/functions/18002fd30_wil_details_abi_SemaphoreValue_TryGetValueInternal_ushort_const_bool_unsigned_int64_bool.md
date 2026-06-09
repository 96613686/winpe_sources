# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002fd30`
- end: `0x18002fed5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002fcac`

## callees

- `0x180020c48`
- `0x180026920`
- `0x180029488`
- `0x18002c4c4`
- `0x18002f0cc`
- `0x18002f790`
- `0x18002f7dc`
- `0x18002fd30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd9f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002fd8f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002fe26`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002fd8f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002fe26`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18002fd30  mov     [rsp-8+arg_8], rbx
0x18002fd35  mov     [rsp-8+arg_18], rdi
0x18002fd3a  push    rbp
0x18002fd3b  lea     rbp, [rsp-160h]
0x18002fd43  sub     rsp, 260h
0x18002fd4a  mov     rax, cs:__security_cookie
0x18002fd51  xor     rax, rsp
0x18002fd54  mov     [rbp+160h+var_10], rax
0x18002fd5b  mov     rdi, r8
0x18002fd5e  mov     qword ptr [r8], 0
0x18002fd65  mov     r8, rcx; unsigned __int16 *
0x18002fd68  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002fd6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fd72  lea     r8, aP0; "_p0"
0x18002fd79  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002fd7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fd83  lea     r8, [rsp+260h+Name]; lpName
0x18002fd88  xor     edx, edx; bInheritHandle
0x18002fd8a  mov     ecx, 1F0003h; dwDesiredAccess
0x18002fd8f  call    cs:__imp_OpenSemaphoreW
0x18002fd95  mov     [rsp+260h+var_230], rax
0x18002fd9a  test    rax, rax
0x18002fd9d  jnz     short loc_18002FDC6
0x18002fd9f  call    cs:__imp_GetLastError
0x18002fda5  cmp     eax, 2
0x18002fda8  jz      loc_18002FEA3
0x18002fdae  mov     rcx, [rbp+168h]; this
0x18002fdb5  mov     edx, 0D0h; void *
0x18002fdba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fdbf  mov     ebx, eax
0x18002fdc1  jmp     loc_18002FEA5
0x18002fdc6  lea     rdx, [rsp+260h+var_23C]; int *
0x18002fdcb  mov     [rsp+260h+var_23C], 0
0x18002fdd3  mov     rcx, rax; hHandle
0x18002fdd6  mov     [rsp+260h+var_240], 0; int
0x18002fdde  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002fde3  mov     ebx, eax
0x18002fde5  test    eax, eax
0x18002fde7  jns     short loc_18002FE09
0x18002fde9  mov     rcx, [rbp+168h]; this
0x18002fdf0  lea     r8, aWil; "wil"
0x18002fdf7  mov     r9d, eax; char *
0x18002fdfa  mov     edx, 0D6h; void *
0x18002fdff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe04  jmp     loc_18002FEA5
0x18002fe09  lea     r8, asc_180061360; "h"
0x18002fe10  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002fe15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe1a  lea     r8, [rsp+260h+Name]; lpName
0x18002fe1f  xor     edx, edx; bInheritHandle
0x18002fe21  mov     ecx, 1F0003h; dwDesiredAccess
0x18002fe26  call    cs:__imp_OpenSemaphoreW
0x18002fe2c  mov     [rsp+260h+var_238], rax
0x18002fe31  test    rax, rax
0x18002fe34  jnz     short loc_18002FE55
0x18002fe36  mov     rcx, [rbp+168h]; this
0x18002fe3d  mov     edx, 0DCh; void *
0x18002fe42  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fe47  mov     ebx, eax
0x18002fe49  lea     rcx, [rsp+260h+var_238]
0x18002fe4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002fe53  jmp     short loc_18002FEA5
0x18002fe55  lea     rdx, [rsp+260h+var_240]; int *
0x18002fe5a  mov     rcx, rax; hHandle
0x18002fe5d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002fe62  mov     ebx, eax
0x18002fe64  test    eax, eax
0x18002fe66  jns     short loc_18002FE85
0x18002fe68  mov     rcx, [rbp+168h]; this
0x18002fe6f  lea     r8, aWil; "wil"
0x18002fe76  mov     r9d, eax; char *
0x18002fe79  mov     edx, 0DEh; void *
0x18002fe7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe83  jmp     short loc_18002FE49
0x18002fe85  lea     rcx, [rsp+260h+var_238]
0x18002fe8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002fe8f  movsxd  rcx, [rsp+260h+var_240]
0x18002fe94  movsxd  rax, [rsp+260h+var_23C]
0x18002fe99  shl     rcx, 1Fh
0x18002fe9d  or      rcx, rax
0x18002fea0  mov     [rdi], rcx
0x18002fea3  xor     ebx, ebx
0x18002fea5  lea     rcx, [rsp+260h+var_230]
0x18002feaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002feaf  mov     eax, ebx
0x18002feb1  mov     rcx, [rbp+160h+var_10]
0x18002feb8  xor     rcx, rsp; StackCookie
0x18002febb  call    __security_check_cookie
0x18002fec0  lea     r11, [rsp+260h+var_s0]
0x18002fec8  mov     rbx, [r11+18h]
0x18002fecc  mov     rdi, [r11+28h]
0x18002fed0  mov     rsp, r11
0x18002fed3  pop     rbp
0x18002fed4  retn
```
