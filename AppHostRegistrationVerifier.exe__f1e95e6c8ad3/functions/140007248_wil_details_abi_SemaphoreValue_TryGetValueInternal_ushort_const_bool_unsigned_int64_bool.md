# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007248`
- end: `0x1400073ea`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140004e08`

## callees

- `0x140002210`
- `0x140004b98`
- `0x140005ae4`
- `0x140006a34`
- `0x140006a54`
- `0x140006fc0`
- `0x14000704c`
- `0x140007248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400072b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007343`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400072b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400072c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400072c1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int v15; // r8d
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14);
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
0x140007248  mov     [rsp-8+arg_8], rbx
0x14000724d  push    rbp
0x14000724e  push    rdi
0x14000724f  push    r14
0x140007251  lea     rbp, [rsp-160h]
0x140007259  sub     rsp, 260h
0x140007260  mov     rax, cs:__security_cookie
0x140007267  xor     rax, rsp
0x14000726a  mov     [rbp+170h+var_20], rax
0x140007271  mov     rdi, r8
0x140007274  mov     qword ptr [r8], 0
0x14000727b  mov     r8, rcx; unsigned __int16 *
0x14000727e  mov     r14d, 104h
0x140007284  mov     edx, r14d; unsigned __int64
0x140007287  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000728c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007291  lea     r8, aP0; "_p0"
0x140007298  mov     edx, r14d; unsigned __int64
0x14000729b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400072a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400072a5  lea     r8, [rsp+270h+Name]; lpName
0x1400072aa  xor     edx, edx; bInheritHandle
0x1400072ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1400072b1  call    cs:__imp_OpenSemaphoreW
0x1400072b7  mov     [rsp+270h+var_240], rax
0x1400072bc  test    rax, rax
0x1400072bf  jnz     short loc_1400072E7
0x1400072c1  call    cs:__imp_GetLastError
0x1400072c7  cmp     eax, 2
0x1400072ca  jz      loc_1400073B9
0x1400072d0  mov     rcx, [rbp+178h]; this
0x1400072d7  lea     edx, [r14-34h]; void *
0x1400072db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400072e0  mov     ebx, eax
0x1400072e2  jmp     loc_1400073BB
0x1400072e7  lea     rdx, [rsp+270h+var_24C]; int *
0x1400072ec  mov     [rsp+270h+var_24C], 0
0x1400072f4  mov     rcx, rax; hHandle
0x1400072f7  mov     [rsp+270h+var_250], 0; int
0x1400072ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007304  mov     ebx, eax
0x140007306  test    eax, eax
0x140007308  jns     short loc_140007323
0x14000730a  mov     rcx, [rbp+178h]; this
0x140007311  mov     r9d, eax; char *
0x140007314  mov     edx, 0D6h; void *
0x140007319  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000731e  jmp     loc_1400073BB
0x140007323  lea     r8, asc_140014388; "h"
0x14000732a  mov     rdx, r14; unsigned __int64
0x14000732d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007332  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007337  lea     r8, [rsp+270h+Name]; lpName
0x14000733c  xor     edx, edx; bInheritHandle
0x14000733e  mov     ecx, 1F0003h; dwDesiredAccess
0x140007343  call    cs:__imp_OpenSemaphoreW
0x140007349  mov     [rsp+270h+var_248], rax
0x14000734e  test    rax, rax
0x140007351  jnz     short loc_140007372
0x140007353  mov     rcx, [rbp+178h]; this
0x14000735a  mov     edx, 0DCh; void *
0x14000735f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007364  mov     ebx, eax
0x140007366  lea     rcx, [rsp+270h+var_248]
0x14000736b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007370  jmp     short loc_1400073BB
0x140007372  lea     rdx, [rsp+270h+var_250]; int *
0x140007377  mov     rcx, rax; hHandle
0x14000737a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000737f  mov     ebx, eax
0x140007381  test    eax, eax
0x140007383  jns     short loc_14000739B
0x140007385  mov     rcx, [rbp+178h]; this
0x14000738c  mov     r9d, eax; char *
0x14000738f  mov     edx, 0DEh; void *
0x140007394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007399  jmp     short loc_140007366
0x14000739b  lea     rcx, [rsp+270h+var_248]
0x1400073a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400073a5  movsxd  rcx, [rsp+270h+var_250]
0x1400073aa  movsxd  rax, [rsp+270h+var_24C]
0x1400073af  shl     rcx, 1Fh
0x1400073b3  or      rcx, rax
0x1400073b6  mov     [rdi], rcx
0x1400073b9  xor     ebx, ebx
0x1400073bb  lea     rcx, [rsp+270h+var_240]
0x1400073c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400073c5  mov     eax, ebx
0x1400073c7  mov     rcx, [rbp+170h+var_20]
0x1400073ce  xor     rcx, rsp; StackCookie
0x1400073d1  call    __security_check_cookie
0x1400073d6  mov     rbx, [rsp+270h+arg_8]
0x1400073de  add     rsp, 260h
0x1400073e5  pop     r14
0x1400073e7  pop     rdi
0x1400073e8  pop     rbp
0x1400073e9  retn
```
