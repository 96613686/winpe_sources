# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800284e8`
- end: `0x18002867f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027028`

## callees

- `0x1800094a0`
- `0x18002660c`
- `0x180026f2c`
- `0x180027910`
- `0x180027e54`
- `0x180027e74`
- `0x18002834c`
- `0x1800284e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028557`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180028547`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800285d7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180028547`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800285d7`

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
0x1800284e8  mov     [rsp-8+arg_8], rbx
0x1800284ed  mov     [rsp-8+arg_18], rdi
0x1800284f2  push    rbp
0x1800284f3  lea     rbp, [rsp-160h]
0x1800284fb  sub     rsp, 260h
0x180028502  mov     rax, cs:__security_cookie
0x180028509  xor     rax, rsp
0x18002850c  mov     [rbp+160h+var_10], rax
0x180028513  mov     rdi, r8
0x180028516  mov     qword ptr [r8], 0
0x18002851d  mov     r8, rcx; unsigned __int16 *
0x180028520  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180028525  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002852a  lea     r8, aP0; "_p0"
0x180028531  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180028536  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002853b  lea     r8, [rsp+260h+Name]; lpName
0x180028540  xor     edx, edx; bInheritHandle
0x180028542  mov     ecx, 1F0003h; dwDesiredAccess
0x180028547  call    cs:__imp_OpenSemaphoreW
0x18002854d  mov     [rsp+260h+var_230], rax
0x180028552  test    rax, rax
0x180028555  jnz     short loc_18002857E
0x180028557  call    cs:__imp_GetLastError
0x18002855d  cmp     eax, 2
0x180028560  jz      loc_18002864D
0x180028566  mov     rcx, [rbp+168h]; this
0x18002856d  mov     edx, 0D0h; void *
0x180028572  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028577  mov     ebx, eax
0x180028579  jmp     loc_18002864F
0x18002857e  lea     rdx, [rsp+260h+var_23C]; int *
0x180028583  mov     [rsp+260h+var_23C], 0
0x18002858b  mov     rcx, rax; hHandle
0x18002858e  mov     [rsp+260h+var_240], 0; int
0x180028596  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002859b  mov     ebx, eax
0x18002859d  test    eax, eax
0x18002859f  jns     short loc_1800285BA
0x1800285a1  mov     rcx, [rbp+168h]; this
0x1800285a8  mov     r9d, eax; char *
0x1800285ab  mov     edx, 0D6h; void *
0x1800285b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285b5  jmp     loc_18002864F
0x1800285ba  lea     r8, asc_180068A50; "h"
0x1800285c1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800285c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800285cb  lea     r8, [rsp+260h+Name]; lpName
0x1800285d0  xor     edx, edx; bInheritHandle
0x1800285d2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800285d7  call    cs:__imp_OpenSemaphoreW
0x1800285dd  mov     [rsp+260h+var_238], rax
0x1800285e2  test    rax, rax
0x1800285e5  jnz     short loc_180028606
0x1800285e7  mov     rcx, [rbp+168h]; this
0x1800285ee  mov     edx, 0DCh; void *
0x1800285f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800285f8  mov     ebx, eax
0x1800285fa  lea     rcx, [rsp+260h+var_238]
0x1800285ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028604  jmp     short loc_18002864F
0x180028606  lea     rdx, [rsp+260h+var_240]; int *
0x18002860b  mov     rcx, rax; hHandle
0x18002860e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180028613  mov     ebx, eax
0x180028615  test    eax, eax
0x180028617  jns     short loc_18002862F
0x180028619  mov     rcx, [rbp+168h]; this
0x180028620  mov     r9d, eax; char *
0x180028623  mov     edx, 0DEh; void *
0x180028628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002862d  jmp     short loc_1800285FA
0x18002862f  lea     rcx, [rsp+260h+var_238]
0x180028634  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028639  movsxd  rcx, [rsp+260h+var_240]
0x18002863e  movsxd  rax, [rsp+260h+var_23C]
0x180028643  shl     rcx, 1Fh
0x180028647  or      rcx, rax
0x18002864a  mov     [rdi], rcx
0x18002864d  xor     ebx, ebx
0x18002864f  lea     rcx, [rsp+260h+var_230]
0x180028654  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028659  mov     eax, ebx
0x18002865b  mov     rcx, [rbp+160h+var_10]
0x180028662  xor     rcx, rsp; StackCookie
0x180028665  call    __security_check_cookie
0x18002866a  lea     r11, [rsp+260h+var_s0]
0x180028672  mov     rbx, [r11+18h]
0x180028676  mov     rdi, [r11+28h]
0x18002867a  mov     rsp, r11
0x18002867d  pop     rbp
0x18002867e  retn
```
