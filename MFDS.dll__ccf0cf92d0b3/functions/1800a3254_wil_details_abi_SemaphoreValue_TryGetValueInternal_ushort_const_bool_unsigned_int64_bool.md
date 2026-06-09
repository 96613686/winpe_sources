# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a3254`
- end: `0x1800a3417`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009d08c`

## callees

- `0x180037a10`
- `0x18006d298`
- `0x180074160`
- `0x180086fcc`
- `0x18009c7bc`
- `0x1800a0650`
- `0x1800a2f2c`
- `0x1800a3254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a32bd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a3362`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a32bd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a3362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a32d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a32d3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x1800a3254  mov     [rsp-8+arg_8], rbx
0x1800a3259  push    rbp
0x1800a325a  push    rdi
0x1800a325b  push    r14
0x1800a325d  lea     rbp, [rsp-160h]
0x1800a3265  sub     rsp, 260h
0x1800a326c  mov     rax, cs:__security_cookie
0x1800a3273  xor     rax, rsp
0x1800a3276  mov     [rbp+170h+var_20], rax
0x1800a327d  mov     rdi, r8
0x1800a3280  mov     qword ptr [r8], 0
0x1800a3287  mov     r8, rcx; unsigned __int16 *
0x1800a328a  mov     r14d, 104h
0x1800a3290  mov     edx, r14d; unsigned __int64
0x1800a3293  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800a3298  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a329d  lea     r8, aP0; "_p0"
0x1800a32a4  mov     edx, r14d; unsigned __int64
0x1800a32a7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800a32ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a32b1  lea     r8, [rsp+270h+Name]; lpName
0x1800a32b6  xor     edx, edx; bInheritHandle
0x1800a32b8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a32bd  call    cs:__imp_OpenSemaphoreW
0x1800a32c4  nop     dword ptr [rax+rax+00h]
0x1800a32c9  mov     [rsp+270h+var_240], rax
0x1800a32ce  test    rax, rax
0x1800a32d1  jnz     short loc_1800A32FF
0x1800a32d3  call    cs:__imp_GetLastError
0x1800a32da  nop     dword ptr [rax+rax+00h]
0x1800a32df  cmp     eax, 2
0x1800a32e2  jz      loc_1800A33E5
0x1800a32e8  mov     rcx, [rbp+178h]; this
0x1800a32ef  lea     edx, [r14-34h]; void *
0x1800a32f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a32f8  mov     ebx, eax
0x1800a32fa  jmp     loc_1800A33E7
0x1800a32ff  lea     rdx, [rsp+270h+var_24C]; int *
0x1800a3304  mov     [rsp+270h+var_24C], 0
0x1800a330c  mov     rcx, rax; hHandle
0x1800a330f  mov     [rsp+270h+var_250], 0; int
0x1800a3317  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a331c  mov     ebx, eax
0x1800a331e  test    eax, eax
0x1800a3320  jns     short loc_1800A3342
0x1800a3322  mov     rcx, [rbp+178h]; this
0x1800a3329  lea     r8, aWil; "wil"
0x1800a3330  mov     r9d, eax; char *
0x1800a3333  mov     edx, 0D6h; void *
0x1800a3338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a333d  jmp     loc_1800A33E7
0x1800a3342  lea     r8, asc_1800DBA70; "h"
0x1800a3349  mov     rdx, r14; unsigned __int64
0x1800a334c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800a3351  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a3356  lea     r8, [rsp+270h+Name]; lpName
0x1800a335b  xor     edx, edx; bInheritHandle
0x1800a335d  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a3362  call    cs:__imp_OpenSemaphoreW
0x1800a3369  nop     dword ptr [rax+rax+00h]
0x1800a336e  mov     [rsp+270h+var_248], rax
0x1800a3373  test    rax, rax
0x1800a3376  jnz     short loc_1800A3397
0x1800a3378  mov     rcx, [rbp+178h]; this
0x1800a337f  mov     edx, 0DCh; void *
0x1800a3384  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a3389  mov     ebx, eax
0x1800a338b  lea     rcx, [rsp+270h+var_248]
0x1800a3390  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a3395  jmp     short loc_1800A33E7
0x1800a3397  lea     rdx, [rsp+270h+var_250]; int *
0x1800a339c  mov     rcx, rax; hHandle
0x1800a339f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a33a4  mov     ebx, eax
0x1800a33a6  test    eax, eax
0x1800a33a8  jns     short loc_1800A33C7
0x1800a33aa  mov     rcx, [rbp+178h]; this
0x1800a33b1  lea     r8, aWil; "wil"
0x1800a33b8  mov     r9d, eax; char *
0x1800a33bb  mov     edx, 0DEh; void *
0x1800a33c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a33c5  jmp     short loc_1800A338B
0x1800a33c7  lea     rcx, [rsp+270h+var_248]
0x1800a33cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a33d1  movsxd  rcx, [rsp+270h+var_250]
0x1800a33d6  movsxd  rax, [rsp+270h+var_24C]
0x1800a33db  shl     rcx, 1Fh
0x1800a33df  or      rcx, rax
0x1800a33e2  mov     [rdi], rcx
0x1800a33e5  xor     ebx, ebx
0x1800a33e7  lea     rcx, [rsp+270h+var_240]
0x1800a33ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a33f1  mov     eax, ebx
0x1800a33f3  mov     rcx, [rbp+170h+var_20]
0x1800a33fa  xor     rcx, rsp; StackCookie
0x1800a33fd  call    __security_check_cookie
0x1800a3402  mov     rbx, [rsp+270h+arg_8]
0x1800a340a  add     rsp, 260h
0x1800a3411  pop     r14
0x1800a3413  pop     rdi
0x1800a3414  pop     rbp
0x1800a3415  retn
```
