# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008ba4`
- end: `0x140008d40`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140008b30`

## callees

- `0x1400046a8`
- `0x140005df0`
- `0x1400079ac`
- `0x1400079cc`
- `0x140008114`
- `0x140008190`
- `0x140008ba4`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008c18`
- `KERNEL32!GetLastError` at `0x140008c18`
- `KERNEL32!OpenSemaphoreW` at `0x140008c08`
- `KERNEL32!OpenSemaphoreW` at `0x140008c98`
- `KERNEL32!OpenSemaphoreW` at `0x140008c08`
- `KERNEL32!OpenSemaphoreW` at `0x140008c98`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140008ba4  mov     [rsp-8+arg_8], rbx
0x140008ba9  mov     [rsp-8+arg_18], rdi
0x140008bae  push    rbp
0x140008baf  lea     rbp, [rsp-160h]
0x140008bb7  sub     rsp, 260h
0x140008bbe  mov     rax, cs:__security_cookie
0x140008bc5  xor     rax, rsp
0x140008bc8  mov     [rbp+160h+var_10], rax
0x140008bcf  mov     rdi, r8
0x140008bd2  mov     qword ptr [r8], 0
0x140008bd9  mov     r8, rcx; unsigned __int16 *
0x140008bdc  mov     edx, 104h; unsigned __int64
0x140008be1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140008be6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008beb  lea     r8, aP0; "_p0"
0x140008bf2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140008bf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008bfc  lea     r8, [rsp+260h+Name]; lpName
0x140008c01  xor     edx, edx; bInheritHandle
0x140008c03  mov     ecx, 1F0003h; dwDesiredAccess
0x140008c08  call    cs:__imp_OpenSemaphoreW
0x140008c0e  mov     [rsp+260h+var_230], rax
0x140008c13  test    rax, rax
0x140008c16  jnz     short loc_140008C3F
0x140008c18  call    cs:__imp_GetLastError
0x140008c1e  cmp     eax, 2
0x140008c21  jz      loc_140008D0E
0x140008c27  mov     rcx, [rbp+168h]; this
0x140008c2e  mov     edx, 0D0h; void *
0x140008c33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008c38  mov     ebx, eax
0x140008c3a  jmp     loc_140008D10
0x140008c3f  lea     rdx, [rsp+260h+var_23C]; int *
0x140008c44  mov     [rsp+260h+var_23C], 0
0x140008c4c  mov     rcx, rax; hHandle
0x140008c4f  mov     [rsp+260h+var_240], 0; int
0x140008c57  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008c5c  mov     ebx, eax
0x140008c5e  test    eax, eax
0x140008c60  jns     short loc_140008C7B
0x140008c62  mov     rcx, [rbp+168h]; this
0x140008c69  mov     r9d, eax; char *
0x140008c6c  mov     edx, 0D6h; void *
0x140008c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c76  jmp     loc_140008D10
0x140008c7b  lea     r8, asc_140022190; "h"
0x140008c82  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140008c87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008c8c  lea     r8, [rsp+260h+Name]; lpName
0x140008c91  xor     edx, edx; bInheritHandle
0x140008c93  mov     ecx, 1F0003h; dwDesiredAccess
0x140008c98  call    cs:__imp_OpenSemaphoreW
0x140008c9e  mov     [rsp+260h+var_238], rax
0x140008ca3  test    rax, rax
0x140008ca6  jnz     short loc_140008CC7
0x140008ca8  mov     rcx, [rbp+168h]; this
0x140008caf  mov     edx, 0DCh; void *
0x140008cb4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008cb9  mov     ebx, eax
0x140008cbb  lea     rcx, [rsp+260h+var_238]
0x140008cc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008cc5  jmp     short loc_140008D10
0x140008cc7  lea     rdx, [rsp+260h+var_240]; int *
0x140008ccc  mov     rcx, rax; hHandle
0x140008ccf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008cd4  mov     ebx, eax
0x140008cd6  test    eax, eax
0x140008cd8  jns     short loc_140008CF0
0x140008cda  mov     rcx, [rbp+168h]; this
0x140008ce1  mov     r9d, eax; char *
0x140008ce4  mov     edx, 0DEh; void *
0x140008ce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008cee  jmp     short loc_140008CBB
0x140008cf0  lea     rcx, [rsp+260h+var_238]
0x140008cf5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008cfa  movsxd  rcx, [rsp+260h+var_240]
0x140008cff  movsxd  rax, [rsp+260h+var_23C]
0x140008d04  shl     rcx, 1Fh
0x140008d08  or      rcx, rax
0x140008d0b  mov     [rdi], rcx
0x140008d0e  xor     ebx, ebx
0x140008d10  lea     rcx, [rsp+260h+var_230]
0x140008d15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008d1a  mov     eax, ebx
0x140008d1c  mov     rcx, [rbp+160h+var_10]
0x140008d23  xor     rcx, rsp; StackCookie
0x140008d26  call    __security_check_cookie
0x140008d2b  lea     r11, [rsp+260h+var_s0]
0x140008d33  mov     rbx, [r11+18h]
0x140008d37  mov     rdi, [r11+28h]
0x140008d3b  mov     rsp, r11
0x140008d3e  pop     rbp
0x140008d3f  retn
```
