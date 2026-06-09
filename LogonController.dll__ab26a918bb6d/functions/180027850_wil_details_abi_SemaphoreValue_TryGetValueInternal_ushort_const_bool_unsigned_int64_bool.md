# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027850`
- end: `0x180027b2b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `731`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180027038`
- `0x1800274f8`

## callees

- `0x180027850`
- `0x180027b34`
- `0x180027c8c`
- `0x18002a8b0`
- `0x18005d488`
- `0x18005d4e8`
- `0x18006c000`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18002793e`
- `KERNEL32!OpenSemaphoreW` at `0x180027a3d`
- `KERNEL32!OpenSemaphoreW` at `0x18002793e`
- `KERNEL32!OpenSemaphoreW` at `0x180027a3d`
- `KERNEL32!GetLastError` at `0x180027951`
- `KERNEL32!GetLastError` at `0x180027951`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rbp
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  _WORD *v14; // r9
  const unsigned __int16 *v15; // r8
  _WORD *v16; // rcx
  wil::details *v17; // rax
  wil::details *v18; // rdi
  const char *v19; // r9
  int ValueFromSemaphore; // eax
  unsigned int v22; // esi
  WCHAR *v23; // rax
  _WORD *v24; // r8
  const unsigned __int16 *v25; // rcx
  _WORD *v26; // rdx
  wil::details *v27; // rax
  const char *v28; // r9
  wil::details *v29; // rbx
  unsigned int LastError; // ebx
  void *v31; // rdx
  int v32; // eax
  void *v33; // rdx
  void *v34; // rdx
  int v35; // [rsp+20h] [rbp-258h] BYREF
  int v36; // [rsp+24h] [rbp-254h] BYREF
  wil::details *v37; // [rsp+28h] [rbp-250h] BYREF
  wil::details *v38; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[260]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v40[8]; // [rsp+248h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v10 = v4 - 1;
  v11 = 260;
  if ( v8 )
    v10 = v4;
  *v10 = 0;
  v12 = Name;
  while ( *v12 )
  {
    ++v12;
    if ( !--v11 )
      goto LABEL_18;
  }
  v13 = 2147483646;
  v14 = &v40[-2 * v11];
  v15 = L"_p0";
  do
  {
    if ( !v13 )
      break;
    if ( !*v15 )
      break;
    *v14++ = *v15++;
    --v13;
    --v11;
  }
  while ( v11 );
  v16 = v14 - 1;
  if ( v11 )
    v16 = v14;
  *v16 = 0;
LABEL_18:
  v17 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v37 = v17;
  v18 = v17;
  if ( v17 )
  {
    v36 = 0;
    v35 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
    v22 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v35);
    }
    else
    {
      v23 = Name;
      while ( *v23 )
      {
        ++v23;
        if ( !--v6 )
          goto LABEL_33;
      }
      v24 = &v40[-2 * v6];
      v25 = L"h";
      do
      {
        if ( !v5 )
          break;
        if ( !*v25 )
          break;
        *v24++ = *v25++;
        --v5;
        --v6;
      }
      while ( v6 );
      v26 = v24 - 1;
      if ( v6 )
        v26 = v24;
      *v26 = 0;
LABEL_33:
      v27 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v38 = v27;
      v29 = v27;
      if ( !v27 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v28);
        wil::details::CloseHandle(v18, v31);
        return LastError;
      }
      v32 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v27, &v35);
      v22 = v32;
      if ( v32 >= 0 )
      {
        wil::details::CloseHandle(v29, v33);
        *a3 = v36 | (unsigned __int64)((__int64)v35 << 31);
        wil::details::CloseHandle(v18, v34);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v32,
        v35);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v38);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v37);
    return v22;
  }
  else if ( GetLastError() == 2 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v37);
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v19);
  }
}

```

## disassembly

```asm
0x180027850  mov     [rsp+arg_8], rbx
0x180027855  mov     [rsp+arg_18], rbp
0x18002785a  push    rdi
0x18002785b  push    r14
0x18002785d  push    r15
0x18002785f  sub     rsp, 260h
0x180027866  mov     rax, cs:__security_cookie
0x18002786d  xor     rax, rsp
0x180027870  mov     [rsp+278h+var_28], rax
0x180027878  xor     r15d, r15d
0x18002787b  lea     r9, [rsp+278h+Name]
0x180027880  mov     ebp, 7FFFFFFEh
0x180027885  mov     [r8], r15
0x180027888  mov     ebx, 104h
0x18002788d  mov     edx, ebp
0x18002788f  mov     r10d, ebx
0x180027892  mov     r14, r8
0x180027895  test    rdx, rdx
0x180027898  jz      short loc_1800278B7
0x18002789a  movzx   eax, word ptr [rcx]
0x18002789d  test    ax, ax
0x1800278a0  jz      short loc_1800278B7
0x1800278a2  mov     [r9], ax
0x1800278a6  add     rcx, 2
0x1800278aa  add     r9, 2
0x1800278ae  dec     rdx
0x1800278b1  sub     r10, 1
0x1800278b5  jnz     short loc_180027895
0x1800278b7  test    r10, r10
0x1800278ba  lea     rcx, [r9-2]
0x1800278be  mov     rax, rbx
0x1800278c1  cmovnz  rcx, r9
0x1800278c5  mov     [rcx], r15w
0x1800278c9  lea     rcx, [rsp+278h+Name]
0x1800278ce  xchg    ax, ax
0x1800278d0  cmp     [rcx], r15w
0x1800278d4  jz      short loc_1800278E2
0x1800278d6  add     rcx, 2
0x1800278da  sub     rax, 1
0x1800278de  jnz     short loc_1800278D0
0x1800278e0  jmp     short loc_180027932
0x1800278e2  lea     rcx, [rax+rax]
0x1800278e6  mov     rdx, rbp
0x1800278e9  lea     r9, [rsp+278h+var_30]
0x1800278f1  sub     r9, rcx
0x1800278f4  lea     r8, aP0; "_p0"
0x1800278fb  test    rax, rax
0x1800278fe  jz      short loc_180027923
0x180027900  test    rdx, rdx
0x180027903  jz      short loc_180027923
0x180027905  movzx   ecx, word ptr [r8]
0x180027909  test    cx, cx
0x18002790c  jz      short loc_180027923
0x18002790e  mov     [r9], cx
0x180027912  add     r8, 2
0x180027916  add     r9, 2
0x18002791a  dec     rdx
0x18002791d  sub     rax, 1
0x180027921  jnz     short loc_180027900
0x180027923  test    rax, rax
0x180027926  lea     rcx, [r9-2]
0x18002792a  cmovnz  rcx, r9
0x18002792e  mov     [rcx], r15w
0x180027932  lea     r8, [rsp+278h+Name]; lpName
0x180027937  xor     edx, edx; bInheritHandle
0x180027939  mov     ecx, 1F0003h; dwDesiredAccess
0x18002793e  call    cs:__imp_OpenSemaphoreW
0x180027944  mov     [rsp+278h+var_250], rax
0x180027949  mov     rdi, rax
0x18002794c  test    rax, rax
0x18002794f  jnz     short loc_1800279A2
0x180027951  call    cs:__imp_GetLastError
0x180027957  cmp     eax, 2
0x18002795a  jz      loc_180027B1A
0x180027960  mov     rcx, [rsp+278h]; this
0x180027968  lea     r8, aWil; "wil"
0x18002796f  mov     edx, 0D0h; void *
0x180027974  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027979  mov     rcx, [rsp+278h+var_28]
0x180027981  xor     rcx, rsp; StackCookie
0x180027984  call    __security_check_cookie
0x180027989  lea     r11, [rsp+278h+var_18]
0x180027991  mov     rbx, [r11+28h]
0x180027995  mov     rbp, [r11+38h]
0x180027999  mov     rsp, r11
0x18002799c  pop     r15
0x18002799e  pop     r14
0x1800279a0  pop     rdi
0x1800279a1  retn
0x1800279a2  lea     rdx, [rsp+278h+var_254]; int *
0x1800279a7  mov     [rsp+278h+arg_0], rsi
0x1800279af  mov     rcx, rdi; hHandle
0x1800279b2  mov     [rsp+278h+var_254], r15d
0x1800279b7  mov     [rsp+278h+var_258], r15d; int
0x1800279bc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800279c1  mov     esi, eax
0x1800279c3  test    eax, eax
0x1800279c5  js      loc_180027AC8
0x1800279cb  lea     rax, [rsp+278h+Name]
0x1800279d0  cmp     [rax], r15w
0x1800279d4  jz      short loc_1800279E2
0x1800279d6  add     rax, 2
0x1800279da  sub     rbx, 1
0x1800279de  jnz     short loc_1800279D0
0x1800279e0  jmp     short loc_180027A31
0x1800279e2  lea     rax, [rbx+rbx]
0x1800279e6  lea     r8, [rsp+278h+var_30]
0x1800279ee  sub     r8, rax
0x1800279f1  lea     rcx, asc_1800A9394; "h"
0x1800279f8  test    rbx, rbx
0x1800279fb  jz      short loc_180027A22
0x1800279fd  nop     dword ptr [rax]
0x180027a00  test    rbp, rbp
0x180027a03  jz      short loc_180027A22
0x180027a05  movzx   eax, word ptr [rcx]
0x180027a08  test    ax, ax
0x180027a0b  jz      short loc_180027A22
0x180027a0d  mov     [r8], ax
0x180027a11  add     rcx, 2
0x180027a15  add     r8, 2
0x180027a19  dec     rbp
0x180027a1c  sub     rbx, 1
0x180027a20  jnz     short loc_180027A00
0x180027a22  test    rbx, rbx
0x180027a25  lea     rdx, [r8-2]
0x180027a29  cmovnz  rdx, r8
0x180027a2d  mov     [rdx], r15w
0x180027a31  lea     r8, [rsp+278h+Name]; lpName
0x180027a36  xor     edx, edx; bInheritHandle
0x180027a38  mov     ecx, 1F0003h; dwDesiredAccess
0x180027a3d  call    cs:__imp_OpenSemaphoreW
0x180027a43  mov     [rsp+278h+var_248], rax
0x180027a48  mov     rbx, rax
0x180027a4b  test    rax, rax
0x180027a4e  jnz     short loc_180027A82
0x180027a50  mov     rcx, [rsp+278h]; this
0x180027a58  lea     r8, aWil; "wil"
0x180027a5f  mov     edx, 0DCh; void *
0x180027a64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027a69  mov     rcx, rdi; this
0x180027a6c  mov     ebx, eax
0x180027a6e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180027a73  mov     eax, ebx
0x180027a75  mov     rsi, [rsp+278h+arg_0]
0x180027a7d  jmp     loc_180027979
0x180027a82  lea     rdx, [rsp+278h+var_258]; int *
0x180027a87  mov     rcx, rbx; hHandle
0x180027a8a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027a8f  mov     esi, eax
0x180027a91  test    eax, eax
0x180027a93  js      short loc_180027AF2
0x180027a95  mov     rcx, rbx; this
0x180027a98  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180027a9d  movsxd  rax, [rsp+278h+var_254]
0x180027aa2  movsxd  rcx, [rsp+278h+var_258]
0x180027aa7  shl     rcx, 1Fh
0x180027aab  or      rcx, rax
0x180027aae  mov     [r14], rcx
0x180027ab1  mov     rcx, rdi; this
0x180027ab4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180027ab9  mov     rsi, [rsp+278h+arg_0]
0x180027ac1  xor     eax, eax
0x180027ac3  jmp     loc_180027979
0x180027ac8  mov     rcx, [rsp+278h]; this
0x180027ad0  lea     r8, aWil; "wil"
0x180027ad7  mov     r9d, esi; char *
0x180027ada  mov     edx, 0D6h; void *
0x180027adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ae4  lea     rcx, [rsp+278h+var_250]
0x180027ae9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027aee  mov     eax, esi
0x180027af0  jmp     short loc_180027A75
0x180027af2  mov     rcx, [rsp+278h]; this
0x180027afa  lea     r8, aWil; "wil"
0x180027b01  mov     r9d, esi; char *
0x180027b04  mov     edx, 0DEh; void *
0x180027b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b0e  lea     rcx, [rsp+278h+var_248]
0x180027b13  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027b18  jmp     short loc_180027AE4
0x180027b1a  lea     rcx, [rsp+278h+var_250]
0x180027b1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027b24  xor     eax, eax
0x180027b26  jmp     loc_180027979
```
