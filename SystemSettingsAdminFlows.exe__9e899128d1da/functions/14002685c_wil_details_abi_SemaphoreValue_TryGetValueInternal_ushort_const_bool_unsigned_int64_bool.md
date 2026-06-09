# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14002685c`
- end: `0x140026a1a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400267d8`

## callees

- `0x140005f30`
- `0x14000ee0c`
- `0x140019d74`
- `0x14001f3b4`
- `0x14001f3d4`
- `0x140026058`
- `0x1400260c0`
- `0x14002685c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400268d5`
- `KERNEL32!GetLastError` at `0x1400268d5`
- `KERNEL32!OpenSemaphoreW` at `0x1400268c5`
- `KERNEL32!OpenSemaphoreW` at `0x140026965`
- `KERNEL32!OpenSemaphoreW` at `0x1400268c5`
- `KERNEL32!OpenSemaphoreW` at `0x140026965`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x14002685c  mov     [rsp-8+arg_8], rbx
0x140026861  push    rbp
0x140026862  push    rdi
0x140026863  push    r14
0x140026865  lea     rbp, [rsp-160h]
0x14002686d  sub     rsp, 260h
0x140026874  mov     rax, cs:__security_cookie
0x14002687b  xor     rax, rsp
0x14002687e  mov     [rbp+170h+var_20], rax
0x140026885  mov     rdi, r8
0x140026888  mov     qword ptr [r8], 0
0x14002688f  mov     r8, rcx; unsigned __int16 *
0x140026892  mov     r14d, 104h
0x140026898  mov     edx, r14d; unsigned __int64
0x14002689b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400268a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400268a5  lea     r8, aP0; "_p0"
0x1400268ac  mov     edx, r14d; unsigned __int64
0x1400268af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400268b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400268b9  lea     r8, [rsp+270h+Name]; lpName
0x1400268be  xor     edx, edx; bInheritHandle
0x1400268c0  mov     ecx, 1F0003h; dwDesiredAccess
0x1400268c5  call    cs:__imp_OpenSemaphoreW
0x1400268cb  mov     [rsp+270h+var_240], rax
0x1400268d0  test    rax, rax
0x1400268d3  jnz     short loc_140026902
0x1400268d5  call    cs:__imp_GetLastError
0x1400268db  cmp     eax, 2
0x1400268de  jz      loc_1400269E9
0x1400268e4  mov     rcx, [rbp+178h]; this
0x1400268eb  lea     r8, aWil; "wil"
0x1400268f2  lea     edx, [r14-34h]; void *
0x1400268f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400268fb  mov     ebx, eax
0x1400268fd  jmp     loc_1400269EB
0x140026902  lea     rdx, [rsp+270h+var_24C]; int *
0x140026907  mov     [rsp+270h+var_24C], 0
0x14002690f  mov     rcx, rax; hHandle
0x140026912  mov     [rsp+270h+var_250], 0; int
0x14002691a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14002691f  mov     ebx, eax
0x140026921  test    eax, eax
0x140026923  jns     short loc_140026945
0x140026925  mov     rcx, [rbp+178h]; this
0x14002692c  lea     r8, aWil; "wil"
0x140026933  mov     r9d, eax; char *
0x140026936  mov     edx, 0D6h; void *
0x14002693b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026940  jmp     loc_1400269EB
0x140026945  lea     r8, asc_140085538; "h"
0x14002694c  mov     rdx, r14; unsigned __int64
0x14002694f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140026954  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140026959  lea     r8, [rsp+270h+Name]; lpName
0x14002695e  xor     edx, edx; bInheritHandle
0x140026960  mov     ecx, 1F0003h; dwDesiredAccess
0x140026965  call    cs:__imp_OpenSemaphoreW
0x14002696b  mov     [rsp+270h+var_248], rax
0x140026970  test    rax, rax
0x140026973  jnz     short loc_14002699B
0x140026975  mov     rcx, [rbp+178h]; this
0x14002697c  lea     r8, aWil; "wil"
0x140026983  mov     edx, 0DCh; void *
0x140026988  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002698d  mov     ebx, eax
0x14002698f  lea     rcx, [rsp+270h+var_248]
0x140026994  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140026999  jmp     short loc_1400269EB
0x14002699b  lea     rdx, [rsp+270h+var_250]; int *
0x1400269a0  mov     rcx, rax; hHandle
0x1400269a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400269a8  mov     ebx, eax
0x1400269aa  test    eax, eax
0x1400269ac  jns     short loc_1400269CB
0x1400269ae  mov     rcx, [rbp+178h]; this
0x1400269b5  lea     r8, aWil; "wil"
0x1400269bc  mov     r9d, eax; char *
0x1400269bf  mov     edx, 0DEh; void *
0x1400269c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400269c9  jmp     short loc_14002698F
0x1400269cb  lea     rcx, [rsp+270h+var_248]
0x1400269d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400269d5  movsxd  rcx, [rsp+270h+var_250]
0x1400269da  movsxd  rax, [rsp+270h+var_24C]
0x1400269df  shl     rcx, 1Fh
0x1400269e3  or      rcx, rax
0x1400269e6  mov     [rdi], rcx
0x1400269e9  xor     ebx, ebx
0x1400269eb  lea     rcx, [rsp+270h+var_240]
0x1400269f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400269f5  mov     eax, ebx
0x1400269f7  mov     rcx, [rbp+170h+var_20]
0x1400269fe  xor     rcx, rsp; StackCookie
0x140026a01  call    __security_check_cookie
0x140026a06  mov     rbx, [rsp+270h+arg_8]
0x140026a0e  add     rsp, 260h
0x140026a15  pop     r14
0x140026a17  pop     rdi
0x140026a18  pop     rbp
0x140026a19  retn
```
