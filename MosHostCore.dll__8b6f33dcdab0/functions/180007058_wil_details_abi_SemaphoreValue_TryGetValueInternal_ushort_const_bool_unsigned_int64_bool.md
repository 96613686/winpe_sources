# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007058`
- end: `0x1800071f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005064`

## callees

- `0x180003410`
- `0x180004f10`
- `0x180005c4c`
- `0x180006934`
- `0x180006954`
- `0x180006e2c`
- `0x180006ea8`
- `0x180007058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000714c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000714c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070cc`

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
0x180007058  mov     [rsp-8+arg_8], rbx
0x18000705d  mov     [rsp-8+arg_18], rdi
0x180007062  push    rbp
0x180007063  lea     rbp, [rsp-160h]
0x18000706b  sub     rsp, 260h
0x180007072  mov     rax, cs:__security_cookie
0x180007079  xor     rax, rsp
0x18000707c  mov     [rbp+160h+var_10], rax
0x180007083  mov     rdi, r8
0x180007086  mov     qword ptr [r8], 0
0x18000708d  mov     r8, rcx; unsigned __int16 *
0x180007090  mov     edx, 104h; unsigned __int64
0x180007095  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000709a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000709f  lea     r8, aP0; "_p0"
0x1800070a6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800070ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070b0  lea     r8, [rsp+260h+Name]; lpName
0x1800070b5  xor     edx, edx; bInheritHandle
0x1800070b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800070bc  call    cs:__imp_OpenSemaphoreW
0x1800070c2  mov     [rsp+260h+var_230], rax
0x1800070c7  test    rax, rax
0x1800070ca  jnz     short loc_1800070F3
0x1800070cc  call    cs:__imp_GetLastError
0x1800070d2  cmp     eax, 2
0x1800070d5  jz      loc_1800071C2
0x1800070db  mov     rcx, [rbp+168h]; this
0x1800070e2  mov     edx, 0D0h; void *
0x1800070e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800070ec  mov     ebx, eax
0x1800070ee  jmp     loc_1800071C4
0x1800070f3  lea     rdx, [rsp+260h+var_23C]; int *
0x1800070f8  mov     [rsp+260h+var_23C], 0
0x180007100  mov     rcx, rax; hHandle
0x180007103  mov     [rsp+260h+var_240], 0; int
0x18000710b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007110  mov     ebx, eax
0x180007112  test    eax, eax
0x180007114  jns     short loc_18000712F
0x180007116  mov     rcx, [rbp+168h]; this
0x18000711d  mov     r9d, eax; char *
0x180007120  mov     edx, 0D6h; void *
0x180007125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000712a  jmp     loc_1800071C4
0x18000712f  lea     r8, asc_1800276F0; "h"
0x180007136  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000713b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007140  lea     r8, [rsp+260h+Name]; lpName
0x180007145  xor     edx, edx; bInheritHandle
0x180007147  mov     ecx, 1F0003h; dwDesiredAccess
0x18000714c  call    cs:__imp_OpenSemaphoreW
0x180007152  mov     [rsp+260h+var_238], rax
0x180007157  test    rax, rax
0x18000715a  jnz     short loc_18000717B
0x18000715c  mov     rcx, [rbp+168h]; this
0x180007163  mov     edx, 0DCh; void *
0x180007168  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000716d  mov     ebx, eax
0x18000716f  lea     rcx, [rsp+260h+var_238]
0x180007174  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007179  jmp     short loc_1800071C4
0x18000717b  lea     rdx, [rsp+260h+var_240]; int *
0x180007180  mov     rcx, rax; hHandle
0x180007183  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007188  mov     ebx, eax
0x18000718a  test    eax, eax
0x18000718c  jns     short loc_1800071A4
0x18000718e  mov     rcx, [rbp+168h]; this
0x180007195  mov     r9d, eax; char *
0x180007198  mov     edx, 0DEh; void *
0x18000719d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071a2  jmp     short loc_18000716F
0x1800071a4  lea     rcx, [rsp+260h+var_238]
0x1800071a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800071ae  movsxd  rcx, [rsp+260h+var_240]
0x1800071b3  movsxd  rax, [rsp+260h+var_23C]
0x1800071b8  shl     rcx, 1Fh
0x1800071bc  or      rcx, rax
0x1800071bf  mov     [rdi], rcx
0x1800071c2  xor     ebx, ebx
0x1800071c4  lea     rcx, [rsp+260h+var_230]
0x1800071c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800071ce  mov     eax, ebx
0x1800071d0  mov     rcx, [rbp+160h+var_10]
0x1800071d7  xor     rcx, rsp; StackCookie
0x1800071da  call    __security_check_cookie
0x1800071df  lea     r11, [rsp+260h+var_s0]
0x1800071e7  mov     rbx, [r11+18h]
0x1800071eb  mov     rdi, [r11+28h]
0x1800071ef  mov     rsp, r11
0x1800071f2  pop     rbp
0x1800071f3  retn
```
