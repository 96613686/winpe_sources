# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400319a4`
- end: `0x140031b5c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140031920`

## callees

- `0x140005240`
- `0x14000f3d8`
- `0x14001e0e0`
- `0x14002801c`
- `0x140028044`
- `0x1400299fc`
- `0x140029a48`
- `0x1400319a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140031a08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140031aa6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140031a08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140031aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031a18`

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
0x1400319a4  mov     [rsp-8+arg_8], rbx
0x1400319a9  mov     [rsp-8+arg_18], rdi
0x1400319ae  push    rbp
0x1400319af  lea     rbp, [rsp-160h]
0x1400319b7  sub     rsp, 260h
0x1400319be  mov     rax, cs:__security_cookie
0x1400319c5  xor     rax, rsp
0x1400319c8  mov     [rbp+160h+var_10], rax
0x1400319cf  mov     rdi, r8
0x1400319d2  mov     qword ptr [r8], 0
0x1400319d9  mov     r8, rcx; wchar_t *
0x1400319dc  mov     edx, 104h; unsigned __int64
0x1400319e1  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1400319e6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400319eb  lea     r8, aP0; "_p0"
0x1400319f2  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1400319f7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400319fc  lea     r8, [rsp+260h+Name]; lpName
0x140031a01  xor     edx, edx; bInheritHandle
0x140031a03  mov     ecx, 1F0003h; dwDesiredAccess
0x140031a08  call    cs:__imp_OpenSemaphoreW
0x140031a0e  mov     [rsp+260h+var_230], rax
0x140031a13  test    rax, rax
0x140031a16  jnz     short loc_140031A46
0x140031a18  call    cs:__imp_GetLastError
0x140031a1e  cmp     eax, 2
0x140031a21  jz      loc_140031B2A
0x140031a27  mov     rcx, [rbp+168h]; this
0x140031a2e  lea     r8, aWil; "wil"
0x140031a35  mov     edx, 0D0h; void *
0x140031a3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031a3f  mov     ebx, eax
0x140031a41  jmp     loc_140031B2C
0x140031a46  lea     rdx, [rsp+260h+var_23C]; int *
0x140031a4b  mov     [rsp+260h+var_23C], 0
0x140031a53  mov     rcx, rax; hHandle
0x140031a56  mov     [rsp+260h+var_240], 0; int
0x140031a5e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140031a63  mov     ebx, eax
0x140031a65  test    eax, eax
0x140031a67  jns     short loc_140031A89
0x140031a69  mov     rcx, [rbp+168h]; this
0x140031a70  lea     r8, aWil; "wil"
0x140031a77  mov     r9d, eax; char *
0x140031a7a  mov     edx, 0D6h; void *
0x140031a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031a84  jmp     loc_140031B2C
0x140031a89  lea     r8, asc_1400770F0; "h"
0x140031a90  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140031a95  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140031a9a  lea     r8, [rsp+260h+Name]; lpName
0x140031a9f  xor     edx, edx; bInheritHandle
0x140031aa1  mov     ecx, 1F0003h; dwDesiredAccess
0x140031aa6  call    cs:__imp_OpenSemaphoreW
0x140031aac  mov     [rsp+260h+var_238], rax
0x140031ab1  test    rax, rax
0x140031ab4  jnz     short loc_140031ADC
0x140031ab6  mov     rcx, [rbp+168h]; this
0x140031abd  lea     r8, aWil; "wil"
0x140031ac4  mov     edx, 0DCh; void *
0x140031ac9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031ace  mov     ebx, eax
0x140031ad0  lea     rcx, [rsp+260h+var_238]
0x140031ad5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140031ada  jmp     short loc_140031B2C
0x140031adc  lea     rdx, [rsp+260h+var_240]; int *
0x140031ae1  mov     rcx, rax; hHandle
0x140031ae4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140031ae9  mov     ebx, eax
0x140031aeb  test    eax, eax
0x140031aed  jns     short loc_140031B0C
0x140031aef  mov     rcx, [rbp+168h]; this
0x140031af6  lea     r8, aWil; "wil"
0x140031afd  mov     r9d, eax; char *
0x140031b00  mov     edx, 0DEh; void *
0x140031b05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031b0a  jmp     short loc_140031AD0
0x140031b0c  lea     rcx, [rsp+260h+var_238]
0x140031b11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140031b16  movsxd  rcx, [rsp+260h+var_240]
0x140031b1b  movsxd  rax, [rsp+260h+var_23C]
0x140031b20  shl     rcx, 1Fh
0x140031b24  or      rcx, rax
0x140031b27  mov     [rdi], rcx
0x140031b2a  xor     ebx, ebx
0x140031b2c  lea     rcx, [rsp+260h+var_230]
0x140031b31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140031b36  mov     eax, ebx
0x140031b38  mov     rcx, [rbp+160h+var_10]
0x140031b3f  xor     rcx, rsp; StackCookie
0x140031b42  call    __security_check_cookie
0x140031b47  lea     r11, [rsp+260h+var_s0]
0x140031b4f  mov     rbx, [r11+18h]
0x140031b53  mov     rdi, [r11+28h]
0x140031b57  mov     rsp, r11
0x140031b5a  pop     rbp
0x140031b5b  retn
```
