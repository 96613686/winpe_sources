# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005328`
- end: `0x1800054c4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800032f8`

## callees

- `0x180001620`
- `0x1800031a8`
- `0x180003eac`
- `0x180004bb4`
- `0x180004bd4`
- `0x1800050ac`
- `0x180005128`
- `0x180005328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000538c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000541c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000538c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000541c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000539c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000539c`

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
0x180005328  mov     [rsp-8+arg_8], rbx
0x18000532d  mov     [rsp-8+arg_18], rdi
0x180005332  push    rbp
0x180005333  lea     rbp, [rsp-160h]
0x18000533b  sub     rsp, 260h
0x180005342  mov     rax, cs:__security_cookie
0x180005349  xor     rax, rsp
0x18000534c  mov     [rbp+160h+var_10], rax
0x180005353  mov     rdi, r8
0x180005356  mov     qword ptr [r8], 0
0x18000535d  mov     r8, rcx; unsigned __int16 *
0x180005360  mov     edx, 104h; unsigned __int64
0x180005365  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000536a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000536f  lea     r8, aP0; "_p0"
0x180005376  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000537b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005380  lea     r8, [rsp+260h+Name]; lpName
0x180005385  xor     edx, edx; bInheritHandle
0x180005387  mov     ecx, 1F0003h; dwDesiredAccess
0x18000538c  call    cs:__imp_OpenSemaphoreW
0x180005392  mov     [rsp+260h+var_230], rax
0x180005397  test    rax, rax
0x18000539a  jnz     short loc_1800053C3
0x18000539c  call    cs:__imp_GetLastError
0x1800053a2  cmp     eax, 2
0x1800053a5  jz      loc_180005492
0x1800053ab  mov     rcx, [rbp+168h]; this
0x1800053b2  mov     edx, 0D0h; void *
0x1800053b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800053bc  mov     ebx, eax
0x1800053be  jmp     loc_180005494
0x1800053c3  lea     rdx, [rsp+260h+var_23C]; int *
0x1800053c8  mov     [rsp+260h+var_23C], 0
0x1800053d0  mov     rcx, rax; hHandle
0x1800053d3  mov     [rsp+260h+var_240], 0; int
0x1800053db  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800053e0  mov     ebx, eax
0x1800053e2  test    eax, eax
0x1800053e4  jns     short loc_1800053FF
0x1800053e6  mov     rcx, [rbp+168h]; this
0x1800053ed  mov     r9d, eax; char *
0x1800053f0  mov     edx, 0D6h; void *
0x1800053f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053fa  jmp     loc_180005494
0x1800053ff  lea     r8, asc_1800121D8; "h"
0x180005406  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000540b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005410  lea     r8, [rsp+260h+Name]; lpName
0x180005415  xor     edx, edx; bInheritHandle
0x180005417  mov     ecx, 1F0003h; dwDesiredAccess
0x18000541c  call    cs:__imp_OpenSemaphoreW
0x180005422  mov     [rsp+260h+var_238], rax
0x180005427  test    rax, rax
0x18000542a  jnz     short loc_18000544B
0x18000542c  mov     rcx, [rbp+168h]; this
0x180005433  mov     edx, 0DCh; void *
0x180005438  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000543d  mov     ebx, eax
0x18000543f  lea     rcx, [rsp+260h+var_238]
0x180005444  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005449  jmp     short loc_180005494
0x18000544b  lea     rdx, [rsp+260h+var_240]; int *
0x180005450  mov     rcx, rax; hHandle
0x180005453  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005458  mov     ebx, eax
0x18000545a  test    eax, eax
0x18000545c  jns     short loc_180005474
0x18000545e  mov     rcx, [rbp+168h]; this
0x180005465  mov     r9d, eax; char *
0x180005468  mov     edx, 0DEh; void *
0x18000546d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005472  jmp     short loc_18000543F
0x180005474  lea     rcx, [rsp+260h+var_238]
0x180005479  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000547e  movsxd  rcx, [rsp+260h+var_240]
0x180005483  movsxd  rax, [rsp+260h+var_23C]
0x180005488  shl     rcx, 1Fh
0x18000548c  or      rcx, rax
0x18000548f  mov     [rdi], rcx
0x180005492  xor     ebx, ebx
0x180005494  lea     rcx, [rsp+260h+var_230]
0x180005499  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000549e  mov     eax, ebx
0x1800054a0  mov     rcx, [rbp+160h+var_10]
0x1800054a7  xor     rcx, rsp; StackCookie
0x1800054aa  call    __security_check_cookie
0x1800054af  lea     r11, [rsp+260h+var_s0]
0x1800054b7  mov     rbx, [r11+18h]
0x1800054bb  mov     rdi, [r11+28h]
0x1800054bf  mov     rsp, r11
0x1800054c2  pop     rbp
0x1800054c3  retn
```
