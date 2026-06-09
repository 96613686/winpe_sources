# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800221b8`
- end: `0x180022354`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001cee0`

## callees

- `0x180015b60`
- `0x1800174c0`
- `0x18001ccc0`
- `0x18001e8f8`
- `0x180021298`
- `0x180021fe8`
- `0x180022064`
- `0x1800221b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002222c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002222c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002221c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800222ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002221c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800222ac`

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
  StringCchCopyW(Name, 0x104u, a1);
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
0x1800221b8  mov     [rsp-8+arg_8], rbx
0x1800221bd  mov     [rsp-8+arg_18], rdi
0x1800221c2  push    rbp
0x1800221c3  lea     rbp, [rsp-160h]
0x1800221cb  sub     rsp, 260h
0x1800221d2  mov     rax, cs:__security_cookie
0x1800221d9  xor     rax, rsp
0x1800221dc  mov     [rbp+160h+var_10], rax
0x1800221e3  mov     rdi, r8
0x1800221e6  mov     qword ptr [r8], 0
0x1800221ed  mov     r8, rcx; unsigned __int16 *
0x1800221f0  mov     edx, 104h; unsigned __int64
0x1800221f5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800221fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800221ff  lea     r8, aP0; "_p0"
0x180022206  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002220b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022210  lea     r8, [rsp+260h+Name]; lpName
0x180022215  xor     edx, edx; bInheritHandle
0x180022217  mov     ecx, 1F0003h; dwDesiredAccess
0x18002221c  call    cs:__imp_OpenSemaphoreW
0x180022222  mov     [rsp+260h+var_230], rax
0x180022227  test    rax, rax
0x18002222a  jnz     short loc_180022253
0x18002222c  call    cs:__imp_GetLastError
0x180022232  cmp     eax, 2
0x180022235  jz      loc_180022322
0x18002223b  mov     rcx, [rbp+168h]; this
0x180022242  mov     edx, 0D0h; void *
0x180022247  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002224c  mov     ebx, eax
0x18002224e  jmp     loc_180022324
0x180022253  lea     rdx, [rsp+260h+var_23C]; int *
0x180022258  mov     [rsp+260h+var_23C], 0
0x180022260  mov     rcx, rax; hHandle
0x180022263  mov     [rsp+260h+var_240], 0; int
0x18002226b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180022270  mov     ebx, eax
0x180022272  test    eax, eax
0x180022274  jns     short loc_18002228F
0x180022276  mov     rcx, [rbp+168h]; this
0x18002227d  mov     r9d, eax; char *
0x180022280  mov     edx, 0D6h; void *
0x180022285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002228a  jmp     loc_180022324
0x18002228f  lea     r8, asc_1800611C8; "h"
0x180022296  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002229b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800222a0  lea     r8, [rsp+260h+Name]; lpName
0x1800222a5  xor     edx, edx; bInheritHandle
0x1800222a7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800222ac  call    cs:__imp_OpenSemaphoreW
0x1800222b2  mov     [rsp+260h+var_238], rax
0x1800222b7  test    rax, rax
0x1800222ba  jnz     short loc_1800222DB
0x1800222bc  mov     rcx, [rbp+168h]; this
0x1800222c3  mov     edx, 0DCh; void *
0x1800222c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800222cd  mov     ebx, eax
0x1800222cf  lea     rcx, [rsp+260h+var_238]
0x1800222d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800222d9  jmp     short loc_180022324
0x1800222db  lea     rdx, [rsp+260h+var_240]; int *
0x1800222e0  mov     rcx, rax; hHandle
0x1800222e3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800222e8  mov     ebx, eax
0x1800222ea  test    eax, eax
0x1800222ec  jns     short loc_180022304
0x1800222ee  mov     rcx, [rbp+168h]; this
0x1800222f5  mov     r9d, eax; char *
0x1800222f8  mov     edx, 0DEh; void *
0x1800222fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022302  jmp     short loc_1800222CF
0x180022304  lea     rcx, [rsp+260h+var_238]
0x180022309  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002230e  movsxd  rcx, [rsp+260h+var_240]
0x180022313  movsxd  rax, [rsp+260h+var_23C]
0x180022318  shl     rcx, 1Fh
0x18002231c  or      rcx, rax
0x18002231f  mov     [rdi], rcx
0x180022322  xor     ebx, ebx
0x180022324  lea     rcx, [rsp+260h+var_230]
0x180022329  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002232e  mov     eax, ebx
0x180022330  mov     rcx, [rbp+160h+var_10]
0x180022337  xor     rcx, rsp; StackCookie
0x18002233a  call    __security_check_cookie
0x18002233f  lea     r11, [rsp+260h+var_s0]
0x180022347  mov     rbx, [r11+18h]
0x18002234b  mov     rdi, [r11+28h]
0x18002234f  mov     rsp, r11
0x180022352  pop     rbp
0x180022353  retn
```
