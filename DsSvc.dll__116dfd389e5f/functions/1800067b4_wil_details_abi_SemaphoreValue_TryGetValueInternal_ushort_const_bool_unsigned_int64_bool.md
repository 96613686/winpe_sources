# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800067b4`
- end: `0x18000695e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006740`

## callees

- `0x1800043e4`
- `0x1800051f4`
- `0x18000602c`
- `0x18000604c`
- `0x180006528`
- `0x1800065a4`
- `0x1800067b4`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006818`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800068af`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006818`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800068af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006828`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  HANDLE v12; // rax
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800067b4  mov     [rsp-8+arg_8], rbx
0x1800067b9  mov     [rsp-8+arg_18], rdi
0x1800067be  push    rbp
0x1800067bf  lea     rbp, [rsp-160h]
0x1800067c7  sub     rsp, 260h
0x1800067ce  mov     rax, cs:__security_cookie
0x1800067d5  xor     rax, rsp
0x1800067d8  mov     [rbp+160h+var_10], rax
0x1800067df  mov     rdi, r8
0x1800067e2  mov     qword ptr [r8], 0
0x1800067e9  mov     r8, rcx; unsigned __int16 *
0x1800067ec  mov     edx, 104h; unsigned __int64
0x1800067f1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800067f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800067fb  lea     r8, aP0; "_p0"
0x180006802  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180006807  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000680c  lea     r8, [rsp+260h+Name]; lpName
0x180006811  xor     edx, edx; bInheritHandle
0x180006813  mov     ecx, 1F0003h; dwDesiredAccess
0x180006818  call    cs:__imp_OpenSemaphoreW
0x18000681e  mov     [rsp+260h+var_230], rax
0x180006823  test    rax, rax
0x180006826  jnz     short loc_180006856
0x180006828  call    cs:__imp_GetLastError
0x18000682e  cmp     eax, 2
0x180006831  jz      loc_18000692C
0x180006837  mov     rcx, [rbp+168h]; this
0x18000683e  lea     r8, aWil; "wil"
0x180006845  mov     edx, 0D0h; void *
0x18000684a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000684f  mov     ebx, eax
0x180006851  jmp     loc_18000692E
0x180006856  lea     rdx, [rsp+260h+var_23C]; int *
0x18000685b  mov     [rsp+260h+var_23C], 0
0x180006863  mov     rcx, rax; hHandle
0x180006866  mov     [rsp+260h+var_240], 0; int
0x18000686e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006873  mov     ebx, eax
0x180006875  test    eax, eax
0x180006877  jns     short loc_180006892
0x180006879  mov     rcx, [rbp+168h]; this
0x180006880  mov     r9d, eax; char *
0x180006883  mov     edx, 0D6h; void *
0x180006888  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000688d  jmp     loc_18000692E
0x180006892  lea     r8, asc_18001ECC8; "h"
0x180006899  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000689e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068a3  lea     r8, [rsp+260h+Name]; lpName
0x1800068a8  xor     edx, edx; bInheritHandle
0x1800068aa  mov     ecx, 1F0003h; dwDesiredAccess
0x1800068af  call    cs:__imp_OpenSemaphoreW
0x1800068b5  mov     [rsp+260h+var_238], rax
0x1800068ba  test    rax, rax
0x1800068bd  jnz     short loc_1800068E5
0x1800068bf  mov     rcx, [rbp+168h]; this
0x1800068c6  lea     r8, aWil; "wil"
0x1800068cd  mov     edx, 0DCh; void *
0x1800068d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800068d7  mov     ebx, eax
0x1800068d9  lea     rcx, [rsp+260h+var_238]
0x1800068de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068e3  jmp     short loc_18000692E
0x1800068e5  lea     rdx, [rsp+260h+var_240]; int *
0x1800068ea  mov     rcx, rax; hHandle
0x1800068ed  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800068f2  mov     ebx, eax
0x1800068f4  test    eax, eax
0x1800068f6  jns     short loc_18000690E
0x1800068f8  mov     rcx, [rbp+168h]; this
0x1800068ff  mov     r9d, eax; char *
0x180006902  mov     edx, 0DEh; void *
0x180006907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000690c  jmp     short loc_1800068D9
0x18000690e  lea     rcx, [rsp+260h+var_238]
0x180006913  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006918  movsxd  rcx, [rsp+260h+var_240]
0x18000691d  movsxd  rax, [rsp+260h+var_23C]
0x180006922  shl     rcx, 1Fh
0x180006926  or      rcx, rax
0x180006929  mov     [rdi], rcx
0x18000692c  xor     ebx, ebx
0x18000692e  lea     rcx, [rsp+260h+var_230]
0x180006933  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006938  mov     eax, ebx
0x18000693a  mov     rcx, [rbp+160h+var_10]
0x180006941  xor     rcx, rsp; StackCookie
0x180006944  call    __security_check_cookie
0x180006949  lea     r11, [rsp+260h+var_s0]
0x180006951  mov     rbx, [r11+18h]
0x180006955  mov     rdi, [r11+28h]
0x180006959  mov     rsp, r11
0x18000695c  pop     rbp
0x18000695d  retn
```
