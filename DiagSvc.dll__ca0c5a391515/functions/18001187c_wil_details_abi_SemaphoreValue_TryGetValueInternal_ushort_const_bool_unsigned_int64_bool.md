# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001187c`
- end: `0x180011a18`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011808`

## callees

- `0x180003fc0`
- `0x180009f80`
- `0x18000d514`
- `0x18001023c`
- `0x18001025c`
- `0x1800112d0`
- `0x18001134c`
- `0x18001187c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011970`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118f0`

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
0x18001187c  mov     [rsp-8+arg_8], rbx
0x180011881  mov     [rsp-8+arg_18], rdi
0x180011886  push    rbp
0x180011887  lea     rbp, [rsp-160h]
0x18001188f  sub     rsp, 260h
0x180011896  mov     rax, cs:__security_cookie
0x18001189d  xor     rax, rsp
0x1800118a0  mov     [rbp+160h+var_10], rax
0x1800118a7  mov     rdi, r8
0x1800118aa  mov     qword ptr [r8], 0
0x1800118b1  mov     r8, rcx; unsigned __int16 *
0x1800118b4  mov     edx, 104h; unsigned __int64
0x1800118b9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800118be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800118c3  lea     r8, aP0; "_p0"
0x1800118ca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800118cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800118d4  lea     r8, [rsp+260h+Name]; lpName
0x1800118d9  xor     edx, edx; bInheritHandle
0x1800118db  mov     ecx, 1F0003h; dwDesiredAccess
0x1800118e0  call    cs:__imp_OpenSemaphoreW
0x1800118e6  mov     [rsp+260h+var_230], rax
0x1800118eb  test    rax, rax
0x1800118ee  jnz     short loc_180011917
0x1800118f0  call    cs:__imp_GetLastError
0x1800118f6  cmp     eax, 2
0x1800118f9  jz      loc_1800119E6
0x1800118ff  mov     rcx, [rbp+168h]; this
0x180011906  mov     edx, 0D0h; void *
0x18001190b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011910  mov     ebx, eax
0x180011912  jmp     loc_1800119E8
0x180011917  lea     rdx, [rsp+260h+var_23C]; int *
0x18001191c  mov     [rsp+260h+var_23C], 0
0x180011924  mov     rcx, rax; hHandle
0x180011927  mov     [rsp+260h+var_240], 0; int
0x18001192f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011934  mov     ebx, eax
0x180011936  test    eax, eax
0x180011938  jns     short loc_180011953
0x18001193a  mov     rcx, [rbp+168h]; this
0x180011941  mov     r9d, eax; char *
0x180011944  mov     edx, 0D6h; void *
0x180011949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001194e  jmp     loc_1800119E8
0x180011953  lea     r8, asc_18002BD90; "h"
0x18001195a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001195f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011964  lea     r8, [rsp+260h+Name]; lpName
0x180011969  xor     edx, edx; bInheritHandle
0x18001196b  mov     ecx, 1F0003h; dwDesiredAccess
0x180011970  call    cs:__imp_OpenSemaphoreW
0x180011976  mov     [rsp+260h+var_238], rax
0x18001197b  test    rax, rax
0x18001197e  jnz     short loc_18001199F
0x180011980  mov     rcx, [rbp+168h]; this
0x180011987  mov     edx, 0DCh; void *
0x18001198c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011991  mov     ebx, eax
0x180011993  lea     rcx, [rsp+260h+var_238]
0x180011998  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001199d  jmp     short loc_1800119E8
0x18001199f  lea     rdx, [rsp+260h+var_240]; int *
0x1800119a4  mov     rcx, rax; hHandle
0x1800119a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800119ac  mov     ebx, eax
0x1800119ae  test    eax, eax
0x1800119b0  jns     short loc_1800119C8
0x1800119b2  mov     rcx, [rbp+168h]; this
0x1800119b9  mov     r9d, eax; char *
0x1800119bc  mov     edx, 0DEh; void *
0x1800119c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119c6  jmp     short loc_180011993
0x1800119c8  lea     rcx, [rsp+260h+var_238]
0x1800119cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800119d2  movsxd  rcx, [rsp+260h+var_240]
0x1800119d7  movsxd  rax, [rsp+260h+var_23C]
0x1800119dc  shl     rcx, 1Fh
0x1800119e0  or      rcx, rax
0x1800119e3  mov     [rdi], rcx
0x1800119e6  xor     ebx, ebx
0x1800119e8  lea     rcx, [rsp+260h+var_230]
0x1800119ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800119f2  mov     eax, ebx
0x1800119f4  mov     rcx, [rbp+160h+var_10]
0x1800119fb  xor     rcx, rsp; StackCookie
0x1800119fe  call    __security_check_cookie
0x180011a03  lea     r11, [rsp+260h+var_s0]
0x180011a0b  mov     rbx, [r11+18h]
0x180011a0f  mov     rdi, [r11+28h]
0x180011a13  mov     rsp, r11
0x180011a16  pop     rbp
0x180011a17  retn
```
