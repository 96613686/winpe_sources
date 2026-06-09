# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180002908`
- end: `0x180002ac0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007338`

## callees

- `0x180002908`
- `0x180002ac8`
- `0x180002bc8`
- `0x180002d38`
- `0x180002d7c`
- `0x1800033d0`
- `0x180005d80`
- `0x180006c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000296c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002a0a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000296c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000297c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000297c`

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
0x180002908  mov     [rsp-8+arg_8], rbx
0x18000290d  mov     [rsp-8+arg_18], rdi
0x180002912  push    rbp
0x180002913  lea     rbp, [rsp-160h]
0x18000291b  sub     rsp, 260h
0x180002922  mov     rax, cs:__security_cookie
0x180002929  xor     rax, rsp
0x18000292c  mov     [rbp+160h+var_10], rax
0x180002933  mov     rdi, r8
0x180002936  mov     qword ptr [r8], 0
0x18000293d  mov     r8, rcx; unsigned __int16 *
0x180002940  mov     edx, 104h; unsigned __int64
0x180002945  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000294a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000294f  lea     r8, aP0; "_p0"
0x180002956  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000295b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002960  lea     r8, [rsp+260h+Name]; lpName
0x180002965  xor     edx, edx; bInheritHandle
0x180002967  mov     ecx, 1F0003h; dwDesiredAccess
0x18000296c  call    cs:__imp_OpenSemaphoreW
0x180002972  mov     [rsp+260h+var_230], rax
0x180002977  test    rax, rax
0x18000297a  jnz     short loc_1800029AA
0x18000297c  call    cs:__imp_GetLastError
0x180002982  cmp     eax, 2
0x180002985  jz      loc_180002A8E
0x18000298b  mov     rcx, [rbp+168h]; this
0x180002992  lea     r8, aWil; "wil"
0x180002999  mov     edx, 0D0h; void *
0x18000299e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800029a3  mov     ebx, eax
0x1800029a5  jmp     loc_180002A90
0x1800029aa  lea     rdx, [rsp+260h+var_23C]; int *
0x1800029af  mov     [rsp+260h+var_23C], 0
0x1800029b7  mov     rcx, rax; hHandle
0x1800029ba  mov     [rsp+260h+var_240], 0; int
0x1800029c2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800029c7  mov     ebx, eax
0x1800029c9  test    eax, eax
0x1800029cb  jns     short loc_1800029ED
0x1800029cd  mov     rcx, [rbp+168h]; this
0x1800029d4  lea     r8, aWil; "wil"
0x1800029db  mov     r9d, eax; char *
0x1800029de  mov     edx, 0D6h; void *
0x1800029e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029e8  jmp     loc_180002A90
0x1800029ed  lea     r8, asc_18001A928; "h"
0x1800029f4  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800029f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800029fe  lea     r8, [rsp+260h+Name]; lpName
0x180002a03  xor     edx, edx; bInheritHandle
0x180002a05  mov     ecx, 1F0003h; dwDesiredAccess
0x180002a0a  call    cs:__imp_OpenSemaphoreW
0x180002a10  mov     [rsp+260h+var_238], rax
0x180002a15  test    rax, rax
0x180002a18  jnz     short loc_180002A40
0x180002a1a  mov     rcx, [rbp+168h]; this
0x180002a21  lea     r8, aWil; "wil"
0x180002a28  mov     edx, 0DCh; void *
0x180002a2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002a32  mov     ebx, eax
0x180002a34  lea     rcx, [rsp+260h+var_238]
0x180002a39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180002a3e  jmp     short loc_180002A90
0x180002a40  lea     rdx, [rsp+260h+var_240]; int *
0x180002a45  mov     rcx, rax; hHandle
0x180002a48  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180002a4d  mov     ebx, eax
0x180002a4f  test    eax, eax
0x180002a51  jns     short loc_180002A70
0x180002a53  mov     rcx, [rbp+168h]; this
0x180002a5a  lea     r8, aWil; "wil"
0x180002a61  mov     r9d, eax; char *
0x180002a64  mov     edx, 0DEh; void *
0x180002a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a6e  jmp     short loc_180002A34
0x180002a70  lea     rcx, [rsp+260h+var_238]
0x180002a75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180002a7a  movsxd  rcx, [rsp+260h+var_240]
0x180002a7f  movsxd  rax, [rsp+260h+var_23C]
0x180002a84  shl     rcx, 1Fh
0x180002a88  or      rcx, rax
0x180002a8b  mov     [rdi], rcx
0x180002a8e  xor     ebx, ebx
0x180002a90  lea     rcx, [rsp+260h+var_230]
0x180002a95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180002a9a  mov     eax, ebx
0x180002a9c  mov     rcx, [rbp+160h+var_10]
0x180002aa3  xor     rcx, rsp; StackCookie
0x180002aa6  call    __security_check_cookie
0x180002aab  lea     r11, [rsp+260h+var_s0]
0x180002ab3  mov     rbx, [r11+18h]
0x180002ab7  mov     rdi, [r11+28h]
0x180002abb  mov     rsp, r11
0x180002abe  pop     rbp
0x180002abf  retn
```
