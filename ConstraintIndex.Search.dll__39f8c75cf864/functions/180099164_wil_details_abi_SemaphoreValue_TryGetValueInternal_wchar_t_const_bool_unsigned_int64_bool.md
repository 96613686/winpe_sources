# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180099164`
- end: `0x1800992fb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800990f0`

## callees

- `0x1800049e0`
- `0x18006cec0`
- `0x18008278c`
- `0x1800971d0`
- `0x1800987dc`
- `0x1800987fc`
- `0x180098e0c`
- `0x180099164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991d3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800991c3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180099253`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800991c3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180099253`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
0x180099164  mov     [rsp-8+arg_8], rbx
0x180099169  mov     [rsp-8+arg_18], rdi
0x18009916e  push    rbp
0x18009916f  lea     rbp, [rsp-160h]
0x180099177  sub     rsp, 260h
0x18009917e  mov     rax, cs:__security_cookie
0x180099185  xor     rax, rsp
0x180099188  mov     [rbp+160h+var_10], rax
0x18009918f  mov     rdi, r8
0x180099192  mov     qword ptr [r8], 0
0x180099199  mov     r8, rcx; wchar_t *
0x18009919c  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800991a1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800991a6  lea     r8, aP0; "_p0"
0x1800991ad  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800991b2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800991b7  lea     r8, [rsp+260h+Name]; lpName
0x1800991bc  xor     edx, edx; bInheritHandle
0x1800991be  mov     ecx, 1F0003h; dwDesiredAccess
0x1800991c3  call    cs:__imp_OpenSemaphoreW
0x1800991c9  mov     [rsp+260h+var_230], rax
0x1800991ce  test    rax, rax
0x1800991d1  jnz     short loc_1800991FA
0x1800991d3  call    cs:__imp_GetLastError
0x1800991d9  cmp     eax, 2
0x1800991dc  jz      loc_1800992C9
0x1800991e2  mov     rcx, [rbp+168h]; this
0x1800991e9  mov     edx, 0D0h; void *
0x1800991ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800991f3  mov     ebx, eax
0x1800991f5  jmp     loc_1800992CB
0x1800991fa  lea     rdx, [rsp+260h+var_23C]; int *
0x1800991ff  mov     [rsp+260h+var_23C], 0
0x180099207  mov     rcx, rax; hHandle
0x18009920a  mov     [rsp+260h+var_240], 0; int
0x180099212  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180099217  mov     ebx, eax
0x180099219  test    eax, eax
0x18009921b  jns     short loc_180099236
0x18009921d  mov     rcx, [rbp+168h]; this
0x180099224  mov     r9d, eax; char *
0x180099227  mov     edx, 0D6h; void *
0x18009922c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099231  jmp     loc_1800992CB
0x180099236  lea     r8, asc_180106640; "h"
0x18009923d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180099242  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180099247  lea     r8, [rsp+260h+Name]; lpName
0x18009924c  xor     edx, edx; bInheritHandle
0x18009924e  mov     ecx, 1F0003h; dwDesiredAccess
0x180099253  call    cs:__imp_OpenSemaphoreW
0x180099259  mov     [rsp+260h+var_238], rax
0x18009925e  test    rax, rax
0x180099261  jnz     short loc_180099282
0x180099263  mov     rcx, [rbp+168h]; this
0x18009926a  mov     edx, 0DCh; void *
0x18009926f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099274  mov     ebx, eax
0x180099276  lea     rcx, [rsp+260h+var_238]
0x18009927b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180099280  jmp     short loc_1800992CB
0x180099282  lea     rdx, [rsp+260h+var_240]; int *
0x180099287  mov     rcx, rax; hHandle
0x18009928a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18009928f  mov     ebx, eax
0x180099291  test    eax, eax
0x180099293  jns     short loc_1800992AB
0x180099295  mov     rcx, [rbp+168h]; this
0x18009929c  mov     r9d, eax; char *
0x18009929f  mov     edx, 0DEh; void *
0x1800992a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800992a9  jmp     short loc_180099276
0x1800992ab  lea     rcx, [rsp+260h+var_238]
0x1800992b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800992b5  movsxd  rcx, [rsp+260h+var_240]
0x1800992ba  movsxd  rax, [rsp+260h+var_23C]
0x1800992bf  shl     rcx, 1Fh
0x1800992c3  or      rcx, rax
0x1800992c6  mov     [rdi], rcx
0x1800992c9  xor     ebx, ebx
0x1800992cb  lea     rcx, [rsp+260h+var_230]
0x1800992d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800992d5  mov     eax, ebx
0x1800992d7  mov     rcx, [rbp+160h+var_10]
0x1800992de  xor     rcx, rsp; StackCookie
0x1800992e1  call    __security_check_cookie
0x1800992e6  lea     r11, [rsp+260h+var_s0]
0x1800992ee  mov     rbx, [r11+18h]
0x1800992f2  mov     rdi, [r11+28h]
0x1800992f6  mov     rsp, r11
0x1800992f9  pop     rbp
0x1800992fa  retn
```
