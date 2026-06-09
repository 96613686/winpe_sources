# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400124ac`
- end: `0x14001267d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140012428`

## callees

- `0x140004870`
- `0x14000df28`
- `0x14000f760`
- `0x14001179c`
- `0x1400117bc`
- `0x140011eb8`
- `0x140011ff4`
- `0x1400124ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140012515`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400125c1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140012515`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400125c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001252b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001252b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v13);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
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
        v14);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v17 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v15);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x1400124ac  mov     [rsp-8+arg_8], rbx
0x1400124b1  push    rbp
0x1400124b2  push    rdi
0x1400124b3  push    r14
0x1400124b5  lea     rbp, [rsp-170h]
0x1400124bd  sub     rsp, 270h
0x1400124c4  mov     rax, cs:__security_cookie
0x1400124cb  xor     rax, rsp
0x1400124ce  mov     [rbp+180h+var_20], rax
0x1400124d5  mov     r9, rcx; pszSrc
0x1400124d8  mov     qword ptr [r8], 0
0x1400124df  mov     r14d, 104h
0x1400124e5  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1400124ea  mov     edx, r14d; cchDest
0x1400124ed  mov     rdi, r8
0x1400124f0  call    StringCopyWorkerW
0x1400124f5  lea     r8, aP0; "_p0"
0x1400124fc  mov     edx, r14d; unsigned __int64
0x1400124ff  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x140012504  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140012509  lea     r8, [rsp+280h+pszDest]; lpName
0x14001250e  xor     edx, edx; bInheritHandle
0x140012510  mov     ecx, 1F0003h; dwDesiredAccess
0x140012515  call    cs:__imp_OpenSemaphoreW
0x14001251c  nop     dword ptr [rax+rax+00h]
0x140012521  mov     [rsp+280h+var_240], rax
0x140012526  test    rax, rax
0x140012529  jnz     short loc_14001255E
0x14001252b  call    cs:__imp_GetLastError
0x140012532  nop     dword ptr [rax+rax+00h]
0x140012537  cmp     eax, 2
0x14001253a  jz      loc_14001264B
0x140012540  mov     rcx, [rbp+188h]; this
0x140012547  lea     r8, aWil; "wil"
0x14001254e  lea     edx, [r14-34h]; void *
0x140012552  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140012557  mov     ebx, eax
0x140012559  jmp     loc_14001264D
0x14001255e  lea     rdx, [rsp+280h+var_24C]; int *
0x140012563  mov     [rsp+280h+var_24C], 0
0x14001256b  mov     rcx, rax; hHandle
0x14001256e  mov     [rsp+280h+var_250], 0
0x140012576  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001257b  mov     ebx, eax
0x14001257d  test    eax, eax
0x14001257f  jns     short loc_1400125A1
0x140012581  mov     rcx, [rbp+188h]; this
0x140012588  lea     r8, aWil; "wil"
0x14001258f  mov     r9d, eax; char *
0x140012592  mov     edx, 0D6h; void *
0x140012597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001259c  jmp     loc_14001264D
0x1400125a1  lea     r8, asc_1401DDDE0; "h"
0x1400125a8  mov     rdx, r14; unsigned __int64
0x1400125ab  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x1400125b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400125b5  lea     r8, [rsp+280h+pszDest]; lpName
0x1400125ba  xor     edx, edx; bInheritHandle
0x1400125bc  mov     ecx, 1F0003h; dwDesiredAccess
0x1400125c1  call    cs:__imp_OpenSemaphoreW
0x1400125c8  nop     dword ptr [rax+rax+00h]
0x1400125cd  mov     [rsp+280h+var_248], rax
0x1400125d2  test    rax, rax
0x1400125d5  jnz     short loc_1400125FD
0x1400125d7  mov     rcx, [rbp+188h]; this
0x1400125de  lea     r8, aWil; "wil"
0x1400125e5  mov     edx, 0DCh; void *
0x1400125ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400125ef  mov     ebx, eax
0x1400125f1  lea     rcx, [rsp+280h+var_248]
0x1400125f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400125fb  jmp     short loc_14001264D
0x1400125fd  lea     rdx, [rsp+280h+var_250]; int *
0x140012602  mov     rcx, rax; hHandle
0x140012605  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001260a  mov     ebx, eax
0x14001260c  test    eax, eax
0x14001260e  jns     short loc_14001262D
0x140012610  mov     rcx, [rbp+188h]; this
0x140012617  lea     r8, aWil; "wil"
0x14001261e  mov     r9d, eax; char *
0x140012621  mov     edx, 0DEh; void *
0x140012626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001262b  jmp     short loc_1400125F1
0x14001262d  lea     rcx, [rsp+280h+var_248]
0x140012632  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140012637  movsxd  rcx, [rsp+280h+var_250]
0x14001263c  movsxd  rax, [rsp+280h+var_24C]
0x140012641  shl     rcx, 1Fh
0x140012645  or      rcx, rax
0x140012648  mov     [rdi], rcx
0x14001264b  xor     ebx, ebx
0x14001264d  lea     rcx, [rsp+280h+var_240]
0x140012652  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140012657  mov     eax, ebx
0x140012659  mov     rcx, [rbp+180h+var_20]
0x140012660  xor     rcx, rsp; StackCookie
0x140012663  call    __security_check_cookie
0x140012668  mov     rbx, [rsp+280h+arg_8]
0x140012670  add     rsp, 270h
0x140012677  pop     r14
0x140012679  pop     rdi
0x14001267a  pop     rbp
0x14001267b  retn
```
