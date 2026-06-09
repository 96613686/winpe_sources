# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180041654`
- end: `0x180041825`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800415d0`

## callees

- `0x18001e4fc`
- `0x18001e51c`
- `0x1800293a0`
- `0x18003d7f8`
- `0x18003e834`
- `0x1800406c4`
- `0x180040e68`
- `0x180041654`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800416d3`
- `KERNEL32!GetLastError` at `0x1800416d3`
- `KERNEL32!OpenSemaphoreW` at `0x1800416bd`
- `KERNEL32!OpenSemaphoreW` at `0x180041769`
- `KERNEL32!OpenSemaphoreW` at `0x1800416bd`
- `KERNEL32!OpenSemaphoreW` at `0x180041769`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x180041654  mov     [rsp-8+arg_8], rbx
0x180041659  push    rbp
0x18004165a  push    rdi
0x18004165b  push    r14
0x18004165d  lea     rbp, [rsp-160h]
0x180041665  sub     rsp, 260h
0x18004166c  mov     rax, cs:__security_cookie
0x180041673  xor     rax, rsp
0x180041676  mov     [rbp+170h+var_20], rax
0x18004167d  mov     rdi, r8
0x180041680  mov     qword ptr [r8], 0
0x180041687  mov     r8, rcx; wchar_t *
0x18004168a  mov     r14d, 104h
0x180041690  mov     edx, r14d; unsigned __int64
0x180041693  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180041698  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004169d  lea     r8, aP0; "_p0"
0x1800416a4  mov     edx, r14d; unsigned __int64
0x1800416a7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800416ac  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800416b1  lea     r8, [rsp+270h+Name]; lpName
0x1800416b6  xor     edx, edx; bInheritHandle
0x1800416b8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800416bd  call    cs:__imp_OpenSemaphoreW
0x1800416c4  nop     dword ptr [rax+rax+00h]
0x1800416c9  mov     [rsp+270h+var_240], rax
0x1800416ce  test    rax, rax
0x1800416d1  jnz     short loc_180041706
0x1800416d3  call    cs:__imp_GetLastError
0x1800416da  nop     dword ptr [rax+rax+00h]
0x1800416df  cmp     eax, 2
0x1800416e2  jz      loc_1800417F3
0x1800416e8  mov     rcx, [rbp+178h]; this
0x1800416ef  lea     r8, aWil; "wil"
0x1800416f6  lea     edx, [r14-34h]; void *
0x1800416fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800416ff  mov     ebx, eax
0x180041701  jmp     loc_1800417F5
0x180041706  lea     rdx, [rsp+270h+var_24C]; int *
0x18004170b  mov     [rsp+270h+var_24C], 0
0x180041713  mov     rcx, rax; hHandle
0x180041716  mov     [rsp+270h+var_250], 0; int
0x18004171e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180041723  mov     ebx, eax
0x180041725  test    eax, eax
0x180041727  jns     short loc_180041749
0x180041729  mov     rcx, [rbp+178h]; this
0x180041730  lea     r8, aWil; "wil"
0x180041737  mov     r9d, eax; char *
0x18004173a  mov     edx, 0D6h; void *
0x18004173f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041744  jmp     loc_1800417F5
0x180041749  lea     r8, asc_1800AFA40; "h"
0x180041750  mov     rdx, r14; unsigned __int64
0x180041753  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180041758  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004175d  lea     r8, [rsp+270h+Name]; lpName
0x180041762  xor     edx, edx; bInheritHandle
0x180041764  mov     ecx, 1F0003h; dwDesiredAccess
0x180041769  call    cs:__imp_OpenSemaphoreW
0x180041770  nop     dword ptr [rax+rax+00h]
0x180041775  mov     [rsp+270h+var_248], rax
0x18004177a  test    rax, rax
0x18004177d  jnz     short loc_1800417A5
0x18004177f  mov     rcx, [rbp+178h]; this
0x180041786  lea     r8, aWil; "wil"
0x18004178d  mov     edx, 0DCh; void *
0x180041792  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180041797  mov     ebx, eax
0x180041799  lea     rcx, [rsp+270h+var_248]
0x18004179e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800417a3  jmp     short loc_1800417F5
0x1800417a5  lea     rdx, [rsp+270h+var_250]; int *
0x1800417aa  mov     rcx, rax; hHandle
0x1800417ad  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800417b2  mov     ebx, eax
0x1800417b4  test    eax, eax
0x1800417b6  jns     short loc_1800417D5
0x1800417b8  mov     rcx, [rbp+178h]; this
0x1800417bf  lea     r8, aWil; "wil"
0x1800417c6  mov     r9d, eax; char *
0x1800417c9  mov     edx, 0DEh; void *
0x1800417ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417d3  jmp     short loc_180041799
0x1800417d5  lea     rcx, [rsp+270h+var_248]
0x1800417da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800417df  movsxd  rcx, [rsp+270h+var_250]
0x1800417e4  movsxd  rax, [rsp+270h+var_24C]
0x1800417e9  shl     rcx, 1Fh
0x1800417ed  or      rcx, rax
0x1800417f0  mov     [rdi], rcx
0x1800417f3  xor     ebx, ebx
0x1800417f5  lea     rcx, [rsp+270h+var_240]
0x1800417fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800417ff  mov     eax, ebx
0x180041801  mov     rcx, [rbp+170h+var_20]
0x180041808  xor     rcx, rsp; StackCookie
0x18004180b  call    __security_check_cookie
0x180041810  mov     rbx, [rsp+270h+arg_8]
0x180041818  add     rsp, 260h
0x18004181f  pop     r14
0x180041821  pop     rdi
0x180041822  pop     rbp
0x180041823  retn
```
