# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180016158`
- end: `0x1800162f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180013d08`

## callees

- `0x18000da80`
- `0x1800106c0`
- `0x180013b40`
- `0x180014b8c`
- `0x180015a74`
- `0x180015a94`
- `0x180015fd4`
- `0x180016158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800161bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001624c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800161bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001624c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161cc`

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
0x180016158  mov     [rsp-8+arg_8], rbx
0x18001615d  mov     [rsp-8+arg_18], rdi
0x180016162  push    rbp
0x180016163  lea     rbp, [rsp-160h]
0x18001616b  sub     rsp, 260h
0x180016172  mov     rax, cs:__security_cookie
0x180016179  xor     rax, rsp
0x18001617c  mov     [rbp+160h+var_10], rax
0x180016183  mov     rdi, r8
0x180016186  mov     qword ptr [r8], 0
0x18001618d  mov     r8, rcx; unsigned __int16 *
0x180016190  mov     edx, 104h; unsigned __int64
0x180016195  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001619a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001619f  lea     r8, aP0; "_p0"
0x1800161a6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800161ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800161b0  lea     r8, [rsp+260h+Name]; lpName
0x1800161b5  xor     edx, edx; bInheritHandle
0x1800161b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800161bc  call    cs:__imp_OpenSemaphoreW
0x1800161c2  mov     [rsp+260h+var_230], rax
0x1800161c7  test    rax, rax
0x1800161ca  jnz     short loc_1800161F3
0x1800161cc  call    cs:__imp_GetLastError
0x1800161d2  cmp     eax, 2
0x1800161d5  jz      loc_1800162C2
0x1800161db  mov     rcx, [rbp+168h]; this
0x1800161e2  mov     edx, 0D0h; void *
0x1800161e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800161ec  mov     ebx, eax
0x1800161ee  jmp     loc_1800162C4
0x1800161f3  lea     rdx, [rsp+260h+var_23C]; int *
0x1800161f8  mov     [rsp+260h+var_23C], 0
0x180016200  mov     rcx, rax; hHandle
0x180016203  mov     [rsp+260h+var_240], 0; int
0x18001620b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016210  mov     ebx, eax
0x180016212  test    eax, eax
0x180016214  jns     short loc_18001622F
0x180016216  mov     rcx, [rbp+168h]; this
0x18001621d  mov     r9d, eax; char *
0x180016220  mov     edx, 0D6h; void *
0x180016225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001622a  jmp     loc_1800162C4
0x18001622f  lea     r8, asc_180025B08; "h"
0x180016236  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001623b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016240  lea     r8, [rsp+260h+Name]; lpName
0x180016245  xor     edx, edx; bInheritHandle
0x180016247  mov     ecx, 1F0003h; dwDesiredAccess
0x18001624c  call    cs:__imp_OpenSemaphoreW
0x180016252  mov     [rsp+260h+var_238], rax
0x180016257  test    rax, rax
0x18001625a  jnz     short loc_18001627B
0x18001625c  mov     rcx, [rbp+168h]; this
0x180016263  mov     edx, 0DCh; void *
0x180016268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001626d  mov     ebx, eax
0x18001626f  lea     rcx, [rsp+260h+var_238]
0x180016274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016279  jmp     short loc_1800162C4
0x18001627b  lea     rdx, [rsp+260h+var_240]; int *
0x180016280  mov     rcx, rax; hHandle
0x180016283  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016288  mov     ebx, eax
0x18001628a  test    eax, eax
0x18001628c  jns     short loc_1800162A4
0x18001628e  mov     rcx, [rbp+168h]; this
0x180016295  mov     r9d, eax; char *
0x180016298  mov     edx, 0DEh; void *
0x18001629d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162a2  jmp     short loc_18001626F
0x1800162a4  lea     rcx, [rsp+260h+var_238]
0x1800162a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800162ae  movsxd  rcx, [rsp+260h+var_240]
0x1800162b3  movsxd  rax, [rsp+260h+var_23C]
0x1800162b8  shl     rcx, 1Fh
0x1800162bc  or      rcx, rax
0x1800162bf  mov     [rdi], rcx
0x1800162c2  xor     ebx, ebx
0x1800162c4  lea     rcx, [rsp+260h+var_230]
0x1800162c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800162ce  mov     eax, ebx
0x1800162d0  mov     rcx, [rbp+160h+var_10]
0x1800162d7  xor     rcx, rsp; StackCookie
0x1800162da  call    __security_check_cookie
0x1800162df  lea     r11, [rsp+260h+var_s0]
0x1800162e7  mov     rbx, [r11+18h]
0x1800162eb  mov     rdi, [r11+28h]
0x1800162ef  mov     rsp, r11
0x1800162f2  pop     rbp
0x1800162f3  retn
```
