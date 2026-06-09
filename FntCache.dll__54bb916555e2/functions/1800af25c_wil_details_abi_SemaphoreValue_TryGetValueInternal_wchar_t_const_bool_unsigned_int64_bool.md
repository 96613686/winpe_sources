# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800af25c`
- end: `0x1800af406`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800af1d8`

## callees

- `0x18008d1c0`
- `0x1800aa650`
- `0x1800ac1a4`
- `0x1800ad334`
- `0x1800ae73c`
- `0x1800ae75c`
- `0x1800aed30`
- `0x1800af25c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af2d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800af2c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800af357`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800af2c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800af357`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800af25c  mov     [rsp-8+arg_8], rbx
0x1800af261  mov     [rsp-8+arg_18], rdi
0x1800af266  push    rbp
0x1800af267  lea     rbp, [rsp-160h]
0x1800af26f  sub     rsp, 260h
0x1800af276  mov     rax, cs:__security_cookie
0x1800af27d  xor     rax, rsp
0x1800af280  mov     [rbp+160h+var_10], rax
0x1800af287  mov     rdi, r8
0x1800af28a  mov     qword ptr [r8], 0
0x1800af291  mov     r8, rcx; wchar_t *
0x1800af294  mov     edx, 104h; unsigned __int64
0x1800af299  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800af29e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800af2a3  lea     r8, aP0; "_p0"
0x1800af2aa  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800af2af  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800af2b4  lea     r8, [rsp+260h+Name]; lpName
0x1800af2b9  xor     edx, edx; bInheritHandle
0x1800af2bb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800af2c0  call    cs:__imp_OpenSemaphoreW
0x1800af2c6  mov     [rsp+260h+var_230], rax
0x1800af2cb  test    rax, rax
0x1800af2ce  jnz     short loc_1800AF2F7
0x1800af2d0  call    cs:__imp_GetLastError
0x1800af2d6  cmp     eax, 2
0x1800af2d9  jz      loc_1800AF3D4
0x1800af2df  mov     rcx, [rbp+168h]; this
0x1800af2e6  mov     edx, 0D0h; void *
0x1800af2eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800af2f0  mov     ebx, eax
0x1800af2f2  jmp     loc_1800AF3D6
0x1800af2f7  lea     rdx, [rsp+260h+var_23C]; int *
0x1800af2fc  mov     [rsp+260h+var_23C], 0
0x1800af304  mov     rcx, rax; hHandle
0x1800af307  mov     [rsp+260h+var_240], 0; int
0x1800af30f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800af314  mov     ebx, eax
0x1800af316  test    eax, eax
0x1800af318  jns     short loc_1800AF33A
0x1800af31a  mov     rcx, [rbp+168h]; this
0x1800af321  lea     r8, aWil; "wil"
0x1800af328  mov     r9d, eax; char *
0x1800af32b  mov     edx, 0D6h; void *
0x1800af330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af335  jmp     loc_1800AF3D6
0x1800af33a  lea     r8, asc_1801011F8; "h"
0x1800af341  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800af346  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800af34b  lea     r8, [rsp+260h+Name]; lpName
0x1800af350  xor     edx, edx; bInheritHandle
0x1800af352  mov     ecx, 1F0003h; dwDesiredAccess
0x1800af357  call    cs:__imp_OpenSemaphoreW
0x1800af35d  mov     [rsp+260h+var_238], rax
0x1800af362  test    rax, rax
0x1800af365  jnz     short loc_1800AF386
0x1800af367  mov     rcx, [rbp+168h]; this
0x1800af36e  mov     edx, 0DCh; void *
0x1800af373  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800af378  mov     ebx, eax
0x1800af37a  lea     rcx, [rsp+260h+var_238]
0x1800af37f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800af384  jmp     short loc_1800AF3D6
0x1800af386  lea     rdx, [rsp+260h+var_240]; int *
0x1800af38b  mov     rcx, rax; hHandle
0x1800af38e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800af393  mov     ebx, eax
0x1800af395  test    eax, eax
0x1800af397  jns     short loc_1800AF3B6
0x1800af399  mov     rcx, [rbp+168h]; this
0x1800af3a0  lea     r8, aWil; "wil"
0x1800af3a7  mov     r9d, eax; char *
0x1800af3aa  mov     edx, 0DEh; void *
0x1800af3af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af3b4  jmp     short loc_1800AF37A
0x1800af3b6  lea     rcx, [rsp+260h+var_238]
0x1800af3bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800af3c0  movsxd  rcx, [rsp+260h+var_240]
0x1800af3c5  movsxd  rax, [rsp+260h+var_23C]
0x1800af3ca  shl     rcx, 1Fh
0x1800af3ce  or      rcx, rax
0x1800af3d1  mov     [rdi], rcx
0x1800af3d4  xor     ebx, ebx
0x1800af3d6  lea     rcx, [rsp+260h+var_230]
0x1800af3db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800af3e0  mov     eax, ebx
0x1800af3e2  mov     rcx, [rbp+160h+var_10]
0x1800af3e9  xor     rcx, rsp; StackCookie
0x1800af3ec  call    __security_check_cookie
0x1800af3f1  lea     r11, [rsp+260h+var_s0]
0x1800af3f9  mov     rbx, [r11+18h]
0x1800af3fd  mov     rdi, [r11+28h]
0x1800af401  mov     rsp, r11
0x1800af404  pop     rbp
0x1800af405  retn
```
