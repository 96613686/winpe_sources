# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005548`
- end: `0x18000570b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800031e4`

## callees

- `0x180003018`
- `0x180003fb8`
- `0x180004de4`
- `0x180004e04`
- `0x1800052f8`
- `0x180005384`
- `0x180005548`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005656`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c7`

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
0x180005548  mov     [rsp-8+arg_8], rbx
0x18000554d  push    rbp
0x18000554e  push    rdi
0x18000554f  push    r14
0x180005551  lea     rbp, [rsp-160h]
0x180005559  sub     rsp, 260h
0x180005560  mov     rax, cs:__security_cookie
0x180005567  xor     rax, rsp
0x18000556a  mov     [rbp+170h+var_20], rax
0x180005571  mov     rdi, r8
0x180005574  mov     qword ptr [r8], 0
0x18000557b  mov     r8, rcx; unsigned __int16 *
0x18000557e  mov     r14d, 104h
0x180005584  mov     edx, r14d; unsigned __int64
0x180005587  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000558c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005591  lea     r8, aP0; "_p0"
0x180005598  mov     edx, r14d; unsigned __int64
0x18000559b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800055a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800055a5  lea     r8, [rsp+270h+Name]; lpName
0x1800055aa  xor     edx, edx; bInheritHandle
0x1800055ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800055b1  call    cs:__imp_OpenSemaphoreW
0x1800055b8  nop     dword ptr [rax+rax+00h]
0x1800055bd  mov     [rsp+270h+var_240], rax
0x1800055c2  test    rax, rax
0x1800055c5  jnz     short loc_1800055F3
0x1800055c7  call    cs:__imp_GetLastError
0x1800055ce  nop     dword ptr [rax+rax+00h]
0x1800055d3  cmp     eax, 2
0x1800055d6  jz      loc_1800056D9
0x1800055dc  mov     rcx, [rbp+178h]; this
0x1800055e3  lea     edx, [r14-34h]; void *
0x1800055e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800055ec  mov     ebx, eax
0x1800055ee  jmp     loc_1800056DB
0x1800055f3  lea     rdx, [rsp+270h+var_24C]; int *
0x1800055f8  mov     [rsp+270h+var_24C], 0
0x180005600  mov     rcx, rax; hHandle
0x180005603  mov     [rsp+270h+var_250], 0; int
0x18000560b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005610  mov     ebx, eax
0x180005612  test    eax, eax
0x180005614  jns     short loc_180005636
0x180005616  mov     rcx, [rbp+178h]; this
0x18000561d  lea     r8, aWil; "wil"
0x180005624  mov     r9d, eax; char *
0x180005627  mov     edx, 0D6h; void *
0x18000562c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005631  jmp     loc_1800056DB
0x180005636  lea     r8, asc_18000D1C8; "h"
0x18000563d  mov     rdx, r14; unsigned __int64
0x180005640  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005645  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000564a  lea     r8, [rsp+270h+Name]; lpName
0x18000564f  xor     edx, edx; bInheritHandle
0x180005651  mov     ecx, 1F0003h; dwDesiredAccess
0x180005656  call    cs:__imp_OpenSemaphoreW
0x18000565d  nop     dword ptr [rax+rax+00h]
0x180005662  mov     [rsp+270h+var_248], rax
0x180005667  test    rax, rax
0x18000566a  jnz     short loc_18000568B
0x18000566c  mov     rcx, [rbp+178h]; this
0x180005673  mov     edx, 0DCh; void *
0x180005678  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000567d  mov     ebx, eax
0x18000567f  lea     rcx, [rsp+270h+var_248]
0x180005684  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005689  jmp     short loc_1800056DB
0x18000568b  lea     rdx, [rsp+270h+var_250]; int *
0x180005690  mov     rcx, rax; hHandle
0x180005693  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005698  mov     ebx, eax
0x18000569a  test    eax, eax
0x18000569c  jns     short loc_1800056BB
0x18000569e  mov     rcx, [rbp+178h]; this
0x1800056a5  lea     r8, aWil; "wil"
0x1800056ac  mov     r9d, eax; char *
0x1800056af  mov     edx, 0DEh; void *
0x1800056b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b9  jmp     short loc_18000567F
0x1800056bb  lea     rcx, [rsp+270h+var_248]
0x1800056c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056c5  movsxd  rcx, [rsp+270h+var_250]
0x1800056ca  movsxd  rax, [rsp+270h+var_24C]
0x1800056cf  shl     rcx, 1Fh
0x1800056d3  or      rcx, rax
0x1800056d6  mov     [rdi], rcx
0x1800056d9  xor     ebx, ebx
0x1800056db  lea     rcx, [rsp+270h+var_240]
0x1800056e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056e5  mov     eax, ebx
0x1800056e7  mov     rcx, [rbp+170h+var_20]
0x1800056ee  xor     rcx, rsp; StackCookie
0x1800056f1  call    __security_check_cookie
0x1800056f6  mov     rbx, [rsp+270h+arg_8]
0x1800056fe  add     rsp, 260h
0x180005705  pop     r14
0x180005707  pop     rdi
0x180005708  pop     rbp
0x180005709  retn
```
