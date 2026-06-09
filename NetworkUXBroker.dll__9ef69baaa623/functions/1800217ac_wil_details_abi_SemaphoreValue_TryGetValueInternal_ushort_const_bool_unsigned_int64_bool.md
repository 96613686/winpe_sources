# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800217ac`
- end: `0x180021964`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180021728`

## callees

- `0x180002520`
- `0x18000e768`
- `0x18001916c`
- `0x1800207ac`
- `0x180020f74`
- `0x180021610`
- `0x18002168c`
- `0x1800217ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021810`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800218ae`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021810`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800218ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021820`

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
0x1800217ac  mov     [rsp-8+arg_8], rbx
0x1800217b1  mov     [rsp-8+arg_18], rdi
0x1800217b6  push    rbp
0x1800217b7  lea     rbp, [rsp-160h]
0x1800217bf  sub     rsp, 260h
0x1800217c6  mov     rax, cs:__security_cookie
0x1800217cd  xor     rax, rsp
0x1800217d0  mov     [rbp+160h+var_10], rax
0x1800217d7  mov     rdi, r8
0x1800217da  mov     qword ptr [r8], 0
0x1800217e1  mov     r8, rcx; unsigned __int16 *
0x1800217e4  mov     edx, 104h; unsigned __int64
0x1800217e9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800217ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800217f3  lea     r8, aP0; "_p0"
0x1800217fa  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800217ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021804  lea     r8, [rsp+260h+Name]; lpName
0x180021809  xor     edx, edx; bInheritHandle
0x18002180b  mov     ecx, 1F0003h; dwDesiredAccess
0x180021810  call    cs:__imp_OpenSemaphoreW
0x180021816  mov     [rsp+260h+var_230], rax
0x18002181b  test    rax, rax
0x18002181e  jnz     short loc_18002184E
0x180021820  call    cs:__imp_GetLastError
0x180021826  cmp     eax, 2
0x180021829  jz      loc_180021932
0x18002182f  mov     rcx, [rbp+168h]; this
0x180021836  lea     r8, aWil; "wil"
0x18002183d  mov     edx, 0D0h; void *
0x180021842  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021847  mov     ebx, eax
0x180021849  jmp     loc_180021934
0x18002184e  lea     rdx, [rsp+260h+var_23C]; int *
0x180021853  mov     [rsp+260h+var_23C], 0
0x18002185b  mov     rcx, rax; hHandle
0x18002185e  mov     [rsp+260h+var_240], 0; int
0x180021866  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002186b  mov     ebx, eax
0x18002186d  test    eax, eax
0x18002186f  jns     short loc_180021891
0x180021871  mov     rcx, [rbp+168h]; this
0x180021878  lea     r8, aWil; "wil"
0x18002187f  mov     r9d, eax; char *
0x180021882  mov     edx, 0D6h; void *
0x180021887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002188c  jmp     loc_180021934
0x180021891  lea     r8, asc_180068A78; "h"
0x180021898  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002189d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800218a2  lea     r8, [rsp+260h+Name]; lpName
0x1800218a7  xor     edx, edx; bInheritHandle
0x1800218a9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800218ae  call    cs:__imp_OpenSemaphoreW
0x1800218b4  mov     [rsp+260h+var_238], rax
0x1800218b9  test    rax, rax
0x1800218bc  jnz     short loc_1800218E4
0x1800218be  mov     rcx, [rbp+168h]; this
0x1800218c5  lea     r8, aWil; "wil"
0x1800218cc  mov     edx, 0DCh; void *
0x1800218d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800218d6  mov     ebx, eax
0x1800218d8  lea     rcx, [rsp+260h+var_238]
0x1800218dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800218e2  jmp     short loc_180021934
0x1800218e4  lea     rdx, [rsp+260h+var_240]; int *
0x1800218e9  mov     rcx, rax; hHandle
0x1800218ec  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800218f1  mov     ebx, eax
0x1800218f3  test    eax, eax
0x1800218f5  jns     short loc_180021914
0x1800218f7  mov     rcx, [rbp+168h]; this
0x1800218fe  lea     r8, aWil; "wil"
0x180021905  mov     r9d, eax; char *
0x180021908  mov     edx, 0DEh; void *
0x18002190d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021912  jmp     short loc_1800218D8
0x180021914  lea     rcx, [rsp+260h+var_238]
0x180021919  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002191e  movsxd  rcx, [rsp+260h+var_240]
0x180021923  movsxd  rax, [rsp+260h+var_23C]
0x180021928  shl     rcx, 1Fh
0x18002192c  or      rcx, rax
0x18002192f  mov     [rdi], rcx
0x180021932  xor     ebx, ebx
0x180021934  lea     rcx, [rsp+260h+var_230]
0x180021939  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002193e  mov     eax, ebx
0x180021940  mov     rcx, [rbp+160h+var_10]
0x180021947  xor     rcx, rsp; StackCookie
0x18002194a  call    __security_check_cookie
0x18002194f  lea     r11, [rsp+260h+var_s0]
0x180021957  mov     rbx, [r11+18h]
0x18002195b  mov     rdi, [r11+28h]
0x18002195f  mov     rsp, r11
0x180021962  pop     rbp
0x180021963  retn
```
