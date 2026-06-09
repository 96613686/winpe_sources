# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007538`
- end: `0x1800076f0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800074b4`

## callees

- `0x180004f78`
- `0x180005ff8`
- `0x180006e8c`
- `0x180006eac`
- `0x180007168`
- `0x1800071e4`
- `0x180007538`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000759c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000763a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000759c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000763a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ac`

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
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180007538  mov     [rsp-8+arg_8], rbx
0x18000753d  mov     [rsp-8+arg_18], rdi
0x180007542  push    rbp
0x180007543  lea     rbp, [rsp-160h]
0x18000754b  sub     rsp, 260h
0x180007552  mov     rax, cs:__security_cookie
0x180007559  xor     rax, rsp
0x18000755c  mov     [rbp+160h+var_10], rax
0x180007563  mov     rdi, r8
0x180007566  mov     qword ptr [r8], 0
0x18000756d  mov     r8, rcx; unsigned __int16 *
0x180007570  mov     edx, 104h; unsigned __int64
0x180007575  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000757a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000757f  lea     r8, aP0; "_p0"
0x180007586  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000758b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007590  lea     r8, [rsp+260h+Name]; lpName
0x180007595  xor     edx, edx; bInheritHandle
0x180007597  mov     ecx, 1F0003h; dwDesiredAccess
0x18000759c  call    cs:__imp_OpenSemaphoreW
0x1800075a2  mov     [rsp+260h+var_230], rax
0x1800075a7  test    rax, rax
0x1800075aa  jnz     short loc_1800075DA
0x1800075ac  call    cs:__imp_GetLastError
0x1800075b2  cmp     eax, 2
0x1800075b5  jz      loc_1800076BE
0x1800075bb  mov     rcx, [rbp+168h]; this
0x1800075c2  lea     r8, aWil; "wil"
0x1800075c9  mov     edx, 0D0h; void *
0x1800075ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800075d3  mov     ebx, eax
0x1800075d5  jmp     loc_1800076C0
0x1800075da  lea     rdx, [rsp+260h+var_23C]; int *
0x1800075df  mov     [rsp+260h+var_23C], 0
0x1800075e7  mov     rcx, rax; hHandle
0x1800075ea  mov     [rsp+260h+var_240], 0; int
0x1800075f2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800075f7  mov     ebx, eax
0x1800075f9  test    eax, eax
0x1800075fb  jns     short loc_18000761D
0x1800075fd  mov     rcx, [rbp+168h]; this
0x180007604  lea     r8, aWil; "wil"
0x18000760b  mov     r9d, eax; char *
0x18000760e  mov     edx, 0D6h; void *
0x180007613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007618  jmp     loc_1800076C0
0x18000761d  lea     r8, asc_18008CEB8; "h"
0x180007624  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007629  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000762e  lea     r8, [rsp+260h+Name]; lpName
0x180007633  xor     edx, edx; bInheritHandle
0x180007635  mov     ecx, 1F0003h; dwDesiredAccess
0x18000763a  call    cs:__imp_OpenSemaphoreW
0x180007640  mov     [rsp+260h+var_238], rax
0x180007645  test    rax, rax
0x180007648  jnz     short loc_180007670
0x18000764a  mov     rcx, [rbp+168h]; this
0x180007651  lea     r8, aWil; "wil"
0x180007658  mov     edx, 0DCh; void *
0x18000765d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007662  mov     ebx, eax
0x180007664  lea     rcx, [rsp+260h+var_238]
0x180007669  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000766e  jmp     short loc_1800076C0
0x180007670  lea     rdx, [rsp+260h+var_240]; int *
0x180007675  mov     rcx, rax; hHandle
0x180007678  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000767d  mov     ebx, eax
0x18000767f  test    eax, eax
0x180007681  jns     short loc_1800076A0
0x180007683  mov     rcx, [rbp+168h]; this
0x18000768a  lea     r8, aWil; "wil"
0x180007691  mov     r9d, eax; char *
0x180007694  mov     edx, 0DEh; void *
0x180007699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000769e  jmp     short loc_180007664
0x1800076a0  lea     rcx, [rsp+260h+var_238]
0x1800076a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800076aa  movsxd  rcx, [rsp+260h+var_240]
0x1800076af  movsxd  rax, [rsp+260h+var_23C]
0x1800076b4  shl     rcx, 1Fh
0x1800076b8  or      rcx, rax
0x1800076bb  mov     [rdi], rcx
0x1800076be  xor     ebx, ebx
0x1800076c0  lea     rcx, [rsp+260h+var_230]
0x1800076c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800076ca  mov     eax, ebx
0x1800076cc  mov     rcx, [rbp+160h+var_10]
0x1800076d3  xor     rcx, rsp; StackCookie
0x1800076d6  call    __security_check_cookie
0x1800076db  lea     r11, [rsp+260h+var_s0]
0x1800076e3  mov     rbx, [r11+18h]
0x1800076e7  mov     rdi, [r11+28h]
0x1800076eb  mov     rsp, r11
0x1800076ee  pop     rbp
0x1800076ef  retn
```
