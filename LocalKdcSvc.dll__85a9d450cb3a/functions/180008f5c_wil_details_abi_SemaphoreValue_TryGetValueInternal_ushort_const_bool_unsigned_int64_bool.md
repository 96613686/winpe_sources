# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008f5c`
- end: `0x1800090f3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008ee8`

## callees

- `0x180002ad0`
- `0x180005124`
- `0x1800067b8`
- `0x1800082cc`
- `0x1800082ec`
- `0x1800089ac`
- `0x1800089f8`
- `0x180008f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000904b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000904b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fcb`

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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180008f5c  mov     [rsp-8+arg_8], rbx
0x180008f61  mov     [rsp-8+arg_18], rdi
0x180008f66  push    rbp
0x180008f67  lea     rbp, [rsp-160h]
0x180008f6f  sub     rsp, 260h
0x180008f76  mov     rax, cs:__security_cookie
0x180008f7d  xor     rax, rsp
0x180008f80  mov     [rbp+160h+var_10], rax
0x180008f87  mov     rdi, r8
0x180008f8a  mov     qword ptr [r8], 0
0x180008f91  mov     r8, rcx; unsigned __int16 *
0x180008f94  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008f99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008f9e  lea     r8, aP0; "_p0"
0x180008fa5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008faa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008faf  lea     r8, [rsp+260h+Name]; lpName
0x180008fb4  xor     edx, edx; bInheritHandle
0x180008fb6  mov     ecx, 1F0003h; dwDesiredAccess
0x180008fbb  call    cs:__imp_OpenSemaphoreW
0x180008fc1  mov     [rsp+260h+var_230], rax
0x180008fc6  test    rax, rax
0x180008fc9  jnz     short loc_180008FF2
0x180008fcb  call    cs:__imp_GetLastError
0x180008fd1  cmp     eax, 2
0x180008fd4  jz      loc_1800090C1
0x180008fda  mov     rcx, [rbp+168h]; this
0x180008fe1  mov     edx, 0D0h; void *
0x180008fe6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008feb  mov     ebx, eax
0x180008fed  jmp     loc_1800090C3
0x180008ff2  lea     rdx, [rsp+260h+var_23C]; int *
0x180008ff7  mov     [rsp+260h+var_23C], 0
0x180008fff  mov     rcx, rax; hHandle
0x180009002  mov     [rsp+260h+var_240], 0; int
0x18000900a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000900f  mov     ebx, eax
0x180009011  test    eax, eax
0x180009013  jns     short loc_18000902E
0x180009015  mov     rcx, [rbp+168h]; this
0x18000901c  mov     r9d, eax; char *
0x18000901f  mov     edx, 0D6h; void *
0x180009024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009029  jmp     loc_1800090C3
0x18000902e  lea     r8, asc_1800A15E0; "h"
0x180009035  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000903a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000903f  lea     r8, [rsp+260h+Name]; lpName
0x180009044  xor     edx, edx; bInheritHandle
0x180009046  mov     ecx, 1F0003h; dwDesiredAccess
0x18000904b  call    cs:__imp_OpenSemaphoreW
0x180009051  mov     [rsp+260h+var_238], rax
0x180009056  test    rax, rax
0x180009059  jnz     short loc_18000907A
0x18000905b  mov     rcx, [rbp+168h]; this
0x180009062  mov     edx, 0DCh; void *
0x180009067  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000906c  mov     ebx, eax
0x18000906e  lea     rcx, [rsp+260h+var_238]
0x180009073  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009078  jmp     short loc_1800090C3
0x18000907a  lea     rdx, [rsp+260h+var_240]; int *
0x18000907f  mov     rcx, rax; hHandle
0x180009082  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009087  mov     ebx, eax
0x180009089  test    eax, eax
0x18000908b  jns     short loc_1800090A3
0x18000908d  mov     rcx, [rbp+168h]; this
0x180009094  mov     r9d, eax; char *
0x180009097  mov     edx, 0DEh; void *
0x18000909c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090a1  jmp     short loc_18000906E
0x1800090a3  lea     rcx, [rsp+260h+var_238]
0x1800090a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090ad  movsxd  rcx, [rsp+260h+var_240]
0x1800090b2  movsxd  rax, [rsp+260h+var_23C]
0x1800090b7  shl     rcx, 1Fh
0x1800090bb  or      rcx, rax
0x1800090be  mov     [rdi], rcx
0x1800090c1  xor     ebx, ebx
0x1800090c3  lea     rcx, [rsp+260h+var_230]
0x1800090c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090cd  mov     eax, ebx
0x1800090cf  mov     rcx, [rbp+160h+var_10]
0x1800090d6  xor     rcx, rsp; StackCookie
0x1800090d9  call    __security_check_cookie
0x1800090de  lea     r11, [rsp+260h+var_s0]
0x1800090e6  mov     rbx, [r11+18h]
0x1800090ea  mov     rdi, [r11+28h]
0x1800090ee  mov     rsp, r11
0x1800090f1  pop     rbp
0x1800090f2  retn
```
