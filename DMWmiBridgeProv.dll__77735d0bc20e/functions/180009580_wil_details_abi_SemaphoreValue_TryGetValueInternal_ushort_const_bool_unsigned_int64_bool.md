# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009580`
- end: `0x180009722`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003c10`

## callees

- `0x180003ae4`
- `0x1800047fc`
- `0x180008e44`
- `0x180008e64`
- `0x18000933c`
- `0x1800093c8`
- `0x180009580`
- `0x18024d160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800095e9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000967b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800095e9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000967b`

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
0x180009580  mov     [rsp-8+arg_8], rbx
0x180009585  push    rbp
0x180009586  push    rdi
0x180009587  push    r14
0x180009589  lea     rbp, [rsp-160h]
0x180009591  sub     rsp, 260h
0x180009598  mov     rax, cs:__security_cookie
0x18000959f  xor     rax, rsp
0x1800095a2  mov     [rbp+170h+var_20], rax
0x1800095a9  mov     rdi, r8
0x1800095ac  mov     qword ptr [r8], 0
0x1800095b3  mov     r8, rcx; unsigned __int16 *
0x1800095b6  mov     r14d, 104h
0x1800095bc  mov     edx, r14d; unsigned __int64
0x1800095bf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800095c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800095c9  lea     r8, aP0; "_p0"
0x1800095d0  mov     edx, r14d; unsigned __int64
0x1800095d3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800095d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800095dd  lea     r8, [rsp+270h+Name]; lpName
0x1800095e2  xor     edx, edx; bInheritHandle
0x1800095e4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800095e9  call    cs:__imp_OpenSemaphoreW
0x1800095ef  mov     [rsp+270h+var_240], rax
0x1800095f4  test    rax, rax
0x1800095f7  jnz     short loc_18000961F
0x1800095f9  call    cs:__imp_GetLastError
0x1800095ff  cmp     eax, 2
0x180009602  jz      loc_1800096F1
0x180009608  mov     rcx, [rbp+178h]; this
0x18000960f  lea     edx, [r14-34h]; void *
0x180009613  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009618  mov     ebx, eax
0x18000961a  jmp     loc_1800096F3
0x18000961f  mov     [rsp+270h+var_24C], 0
0x180009627  mov     [rsp+270h+var_250], 0; int
0x18000962f  lea     rdx, [rsp+270h+var_24C]; int *
0x180009634  mov     rcx, rax; hHandle
0x180009637  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000963c  mov     ebx, eax
0x18000963e  test    eax, eax
0x180009640  jns     short loc_18000965B
0x180009642  mov     rcx, [rbp+178h]; this
0x180009649  mov     r9d, eax; char *
0x18000964c  mov     edx, 0D6h; void *
0x180009651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009656  jmp     loc_1800096F3
0x18000965b  lea     r8, asc_180322060; "h"
0x180009662  mov     rdx, r14; unsigned __int64
0x180009665  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000966a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000966f  lea     r8, [rsp+270h+Name]; lpName
0x180009674  xor     edx, edx; bInheritHandle
0x180009676  mov     ecx, 1F0003h; dwDesiredAccess
0x18000967b  call    cs:__imp_OpenSemaphoreW
0x180009681  mov     [rsp+270h+var_248], rax
0x180009686  test    rax, rax
0x180009689  jnz     short loc_1800096AA
0x18000968b  mov     rcx, [rbp+178h]; this
0x180009692  mov     edx, 0DCh; void *
0x180009697  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000969c  mov     ebx, eax
0x18000969e  lea     rcx, [rsp+270h+var_248]
0x1800096a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800096a8  jmp     short loc_1800096F3
0x1800096aa  lea     rdx, [rsp+270h+var_250]; int *
0x1800096af  mov     rcx, rax; hHandle
0x1800096b2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800096b7  mov     ebx, eax
0x1800096b9  test    eax, eax
0x1800096bb  jns     short loc_1800096D3
0x1800096bd  mov     rcx, [rbp+178h]; this
0x1800096c4  mov     r9d, eax; char *
0x1800096c7  mov     edx, 0DEh; void *
0x1800096cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096d1  jmp     short loc_18000969E
0x1800096d3  lea     rcx, [rsp+270h+var_248]
0x1800096d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800096dd  movsxd  rcx, [rsp+270h+var_250]
0x1800096e2  shl     rcx, 1Fh
0x1800096e6  movsxd  rax, [rsp+270h+var_24C]
0x1800096eb  or      rcx, rax
0x1800096ee  mov     [rdi], rcx
0x1800096f1  xor     ebx, ebx
0x1800096f3  lea     rcx, [rsp+270h+var_240]
0x1800096f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800096fd  mov     eax, ebx
0x1800096ff  mov     rcx, [rbp+170h+var_20]
0x180009706  xor     rcx, rsp; StackCookie
0x180009709  call    __security_check_cookie
0x18000970e  mov     rbx, [rsp+270h+arg_8]
0x180009716  add     rsp, 260h
0x18000971d  pop     r14
0x18000971f  pop     rdi
0x180009720  pop     rbp
0x180009721  retn
```
