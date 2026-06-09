# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180050354`
- end: `0x180050636`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `738`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180058e2c`
- `0x18005c564`

## callees

- `0x18002a220`
- `0x180050354`
- `0x180058ca0`
- `0x180059090`
- `0x180059528`
- `0x180059d30`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180050460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180050518`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180050460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180050518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005057a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005057a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  void *v33; // rdx
  const char *v35; // r9
  int v36; // eax
  void *v37; // rdx
  int v38; // esi
  void *v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v35);
    LastError = 0;
LABEL_41:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    return LastError;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
    goto LABEL_41;
  }
  v23 = 260;
  v24 = Name;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (260 - v23) & -(__int64)(v23 != 0);
  if ( v23 )
  {
    v26 = &Name[v25];
    v27 = L"h";
    v28 = 260 - v25;
    if ( 260 != v25 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v27 )
          break;
        *v26++ = *v27++;
        --v5;
        --v28;
      }
      while ( v28 );
    }
    v29 = v26 - 1;
    if ( v28 )
      v29 = v26;
    *v29 = 0;
  }
  v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v30;
  v32 = v30;
  if ( !v30 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
    wil::details::CloseHandle(v20, v33);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
  v38 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    LastError = v38;
    goto LABEL_41;
  }
  wil::details::CloseHandle(v32, v37);
  *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
  wil::details::CloseHandle(v20, v39);
  return 0;
}

```

## disassembly

```asm
0x180050354  mov     [rsp-8+arg_0], rbx
0x180050359  mov     [rsp-8+arg_8], rsi
0x18005035e  push    rbp
0x18005035f  push    rdi
0x180050360  push    r12
0x180050362  push    r14
0x180050364  push    r15
0x180050366  lea     rbp, [rsp-160h]
0x18005036e  sub     rsp, 260h
0x180050375  mov     rax, cs:__security_cookie
0x18005037c  xor     rax, rsp
0x18005037f  mov     [rbp+180h+var_30], rax
0x180050386  xor     r12d, r12d
0x180050389  lea     rax, [rsp+280h+Name]
0x18005038e  mov     r14d, 7FFFFFFEh
0x180050394  mov     [r8], r12
0x180050397  mov     esi, 104h
0x18005039c  mov     r9d, r14d
0x18005039f  mov     edx, esi
0x1800503a1  mov     r15, r8
0x1800503a4  test    r9, r9
0x1800503a7  jz      short loc_1800503C8
0x1800503a9  movzx   r8d, word ptr [rcx]
0x1800503ad  test    r8w, r8w
0x1800503b1  jz      short loc_1800503C8
0x1800503b3  mov     [rax], r8w
0x1800503b7  add     rcx, 2
0x1800503bb  add     rax, 2
0x1800503bf  dec     r9
0x1800503c2  sub     rdx, 1
0x1800503c6  jnz     short loc_1800503A4
0x1800503c8  test    rdx, rdx
0x1800503cb  lea     rcx, [rax-2]
0x1800503cf  mov     rdx, rsi
0x1800503d2  cmovnz  rcx, rax
0x1800503d6  lea     rax, [rsp+280h+Name]
0x1800503db  mov     [rcx], r12w
0x1800503df  cmp     [rax], r12w
0x1800503e3  jz      short loc_1800503EF
0x1800503e5  add     rax, 2
0x1800503e9  sub     rdx, 1
0x1800503ed  jnz     short loc_1800503DF
0x1800503ef  mov     rcx, rsi
0x1800503f2  mov     rax, rdx
0x1800503f5  sub     rcx, rdx
0x1800503f8  neg     rax
0x1800503fb  sbb     r8, r8
0x1800503fe  and     r8, rcx
0x180050401  test    rdx, rdx
0x180050404  jz      short loc_180050454
0x180050406  mov     rax, rsi
0x180050409  lea     rdx, [rsp+280h+Name]
0x18005040e  lea     r9, aP0; "_p0"
0x180050415  mov     rcx, r14
0x180050418  lea     rdx, [rdx+r8*2]
0x18005041c  sub     rax, r8
0x18005041f  jz      short loc_180050445
0x180050421  test    rcx, rcx
0x180050424  jz      short loc_180050445
0x180050426  movzx   r8d, word ptr [r9]
0x18005042a  test    r8w, r8w
0x18005042e  jz      short loc_180050445
0x180050430  mov     [rdx], r8w
0x180050434  add     r9, 2
0x180050438  add     rdx, 2
0x18005043c  dec     rcx
0x18005043f  sub     rax, 1
0x180050443  jnz     short loc_180050421
0x180050445  test    rax, rax
0x180050448  lea     rcx, [rdx-2]
0x18005044c  cmovnz  rcx, rdx
0x180050450  mov     [rcx], r12w
0x180050454  lea     r8, [rsp+280h+Name]; lpName
0x180050459  xor     edx, edx; bInheritHandle
0x18005045b  mov     ecx, 1F0003h; dwDesiredAccess
0x180050460  call    cs:__imp_OpenSemaphoreW
0x180050466  mov     [rsp+280h+var_250], rax
0x18005046b  mov     rdi, rax
0x18005046e  test    rax, rax
0x180050471  jz      loc_18005057A
0x180050477  lea     rdx, [rsp+280h+var_25C]; int *
0x18005047c  mov     [rsp+280h+var_25C], r12d
0x180050481  mov     rcx, rax; hHandle
0x180050484  mov     [rsp+280h+var_260], r12d; int
0x180050489  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005048e  mov     ebx, eax
0x180050490  test    eax, eax
0x180050492  js      loc_1800505E1
0x180050498  mov     rdx, rsi
0x18005049b  lea     rax, [rsp+280h+Name]
0x1800504a0  cmp     [rax], r12w
0x1800504a4  jz      short loc_1800504B0
0x1800504a6  add     rax, 2
0x1800504aa  sub     rdx, 1
0x1800504ae  jnz     short loc_1800504A0
0x1800504b0  mov     rcx, rsi
0x1800504b3  mov     rax, rdx
0x1800504b6  sub     rcx, rdx
0x1800504b9  neg     rax
0x1800504bc  sbb     r8, r8
0x1800504bf  and     r8, rcx
0x1800504c2  test    rdx, rdx
0x1800504c5  jz      short loc_18005050C
0x1800504c7  lea     rax, [rsp+280h+Name]
0x1800504cc  lea     rax, [rax+r8*2]
0x1800504d0  lea     rcx, asc_18009C680; "h"
0x1800504d7  sub     rsi, r8
0x1800504da  jz      short loc_1800504FD
0x1800504dc  test    r14, r14
0x1800504df  jz      short loc_1800504FD
0x1800504e1  movzx   edx, word ptr [rcx]
0x1800504e4  test    dx, dx
0x1800504e7  jz      short loc_1800504FD
0x1800504e9  mov     [rax], dx
0x1800504ec  add     rcx, 2
0x1800504f0  add     rax, 2
0x1800504f4  dec     r14
0x1800504f7  sub     rsi, 1
0x1800504fb  jnz     short loc_1800504DC
0x1800504fd  test    rsi, rsi
0x180050500  lea     rdx, [rax-2]
0x180050504  cmovnz  rdx, rax
0x180050508  mov     [rdx], r12w
0x18005050c  lea     r8, [rsp+280h+Name]; lpName
0x180050511  xor     edx, edx; bInheritHandle
0x180050513  mov     ecx, 1F0003h; dwDesiredAccess
0x180050518  call    cs:__imp_OpenSemaphoreW
0x18005051e  mov     [rsp+280h+var_258], rax
0x180050523  mov     rbx, rax
0x180050526  test    rax, rax
0x180050529  jnz     short loc_1800505A3
0x18005052b  mov     rcx, [rbp+188h]; this
0x180050532  lea     r8, aWil; "wil"
0x180050539  mov     edx, 0DCh; void *
0x18005053e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050543  mov     rcx, rdi; this
0x180050546  mov     ebx, eax
0x180050548  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005054d  mov     eax, ebx
0x18005054f  mov     rcx, [rbp+180h+var_30]
0x180050556  xor     rcx, rsp; StackCookie
0x180050559  call    __security_check_cookie
0x18005055e  lea     r11, [rsp+280h+var_20]
0x180050566  mov     rbx, [r11+30h]
0x18005056a  mov     rsi, [r11+38h]
0x18005056e  mov     rsp, r11
0x180050571  pop     r15
0x180050573  pop     r14
0x180050575  pop     r12
0x180050577  pop     rdi
0x180050578  pop     rbp
0x180050579  retn
0x18005057a  call    cs:__imp_GetLastError
0x180050580  cmp     eax, 2
0x180050583  jz      loc_18005062E
0x180050589  mov     rcx, [rbp+188h]; this
0x180050590  lea     r8, aWil; "wil"
0x180050597  mov     edx, 0D0h; void *
0x18005059c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800505a1  jmp     short loc_18005054F
0x1800505a3  lea     rdx, [rsp+280h+var_260]; int *
0x1800505a8  mov     rcx, rbx; hHandle
0x1800505ab  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800505b0  mov     esi, eax
0x1800505b2  test    eax, eax
0x1800505b4  js      short loc_180050602
0x1800505b6  mov     rcx, rbx; this
0x1800505b9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800505be  movsxd  rax, [rsp+280h+var_25C]
0x1800505c3  movsxd  rcx, [rsp+280h+var_260]
0x1800505c8  shl     rcx, 1Fh
0x1800505cc  or      rcx, rax
0x1800505cf  mov     [r15], rcx
0x1800505d2  mov     rcx, rdi; this
0x1800505d5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800505da  xor     eax, eax
0x1800505dc  jmp     loc_18005054F
0x1800505e1  mov     rcx, [rbp+188h]; this
0x1800505e8  lea     r8, aWil; "wil"
0x1800505ef  mov     r9d, eax; char *
0x1800505f2  mov     edx, 0D6h; void *
0x1800505f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800505fc  nop
0x1800505fd  jmp     loc_18008AAB0
0x180050602  mov     rcx, [rbp+188h]; this
0x180050609  lea     r8, aWil; "wil"
0x180050610  mov     r9d, esi; char *
0x180050613  mov     edx, 0DEh; void *
0x180050618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005061d  lea     rcx, [rsp+280h+var_258]
0x180050622  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050627  mov     ebx, esi
0x180050629  jmp     loc_18008AAB0
0x18005062e  mov     ebx, r12d
0x180050631  jmp     loc_18008AAB0
0x18008aab0  lea     rcx, [rsp+280h+var_250]
0x18008aab5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008aaba  nop
0x18008aabb  jmp     loc_18005054D
```
