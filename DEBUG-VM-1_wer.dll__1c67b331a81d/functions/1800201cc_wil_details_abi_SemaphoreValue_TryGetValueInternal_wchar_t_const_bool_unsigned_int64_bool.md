# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800201cc`
- end: `0x18002042a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `606`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001ffec`
- `0x18003d90c`

## callees

- `0x1800201cc`
- `0x180020430`
- `0x180029228`
- `0x18003db78`
- `0x18003ecfc`
- `0x18003f0c0`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800202cf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002033e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800202cf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002033e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const wchar_t *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v21; // rax
  const char *v22; // r9
  int v23; // eax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v28; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
    v15 = &Name[v13];
    v16 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v5;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v29[0] = v18;
  if ( v18 )
  {
    v27 = 0;
    v26 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v27);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v28 = v21;
      if ( v21 )
      {
        v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v26);
        LastError = v23;
        if ( v23 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
          *a3 = v27 | (unsigned __int64)((__int64)v26 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v23,
          v26);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v26);
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
}

```

## disassembly

```asm
0x1800201cc  mov     [rsp-8+arg_0], rbx
0x1800201d1  mov     [rsp-8+arg_8], rsi
0x1800201d6  push    rbp
0x1800201d7  push    rdi
0x1800201d8  push    r15
0x1800201da  lea     rbp, [rsp-160h]
0x1800201e2  sub     rsp, 260h
0x1800201e9  mov     rax, cs:__security_cookie
0x1800201f0  xor     rax, rsp
0x1800201f3  mov     [rbp+170h+var_20], rax
0x1800201fa  xor     esi, esi
0x1800201fc  lea     rax, [rsp+270h+Name]
0x180020201  mov     r10d, 7FFFFFFEh
0x180020207  mov     [r8], rsi
0x18002020a  mov     r15d, 104h
0x180020210  mov     r9d, r10d
0x180020213  mov     edx, r15d
0x180020216  mov     rdi, r8
0x180020219  test    r9, r9
0x18002021c  jz      short loc_18002023D
0x18002021e  movzx   r8d, word ptr [rcx]
0x180020222  test    r8w, r8w
0x180020226  jz      short loc_18002023D
0x180020228  mov     [rax], r8w
0x18002022c  add     rcx, 2
0x180020230  add     rax, 2
0x180020234  dec     r9
0x180020237  sub     rdx, 1
0x18002023b  jnz     short loc_180020219
0x18002023d  test    rdx, rdx
0x180020240  lea     rcx, [rax-2]
0x180020244  mov     rdx, r15
0x180020247  cmovnz  rcx, rax
0x18002024b  lea     rax, [rsp+270h+Name]
0x180020250  mov     [rcx], si
0x180020253  cmp     [rax], si
0x180020256  jz      short loc_180020262
0x180020258  add     rax, 2
0x18002025c  sub     rdx, 1
0x180020260  jnz     short loc_180020253
0x180020262  mov     rcx, r15
0x180020265  mov     rax, rdx
0x180020268  sub     rcx, rdx
0x18002026b  neg     rax
0x18002026e  sbb     r8, r8
0x180020271  and     r8, rcx
0x180020274  test    rdx, rdx
0x180020277  jz      short loc_1800202C3
0x180020279  mov     rax, r15
0x18002027c  lea     rdx, [rsp+270h+Name]
0x180020281  lea     rcx, aP0; "_p0"
0x180020288  lea     rdx, [rdx+r8*2]
0x18002028c  sub     rax, r8
0x18002028f  jz      short loc_1800202B5
0x180020291  test    r10, r10
0x180020294  jz      short loc_1800202B5
0x180020296  movzx   r8d, word ptr [rcx]
0x18002029a  test    r8w, r8w
0x18002029e  jz      short loc_1800202B5
0x1800202a0  mov     [rdx], r8w
0x1800202a4  add     rcx, 2
0x1800202a8  add     rdx, 2
0x1800202ac  dec     r10
0x1800202af  sub     rax, 1
0x1800202b3  jnz     short loc_180020291
0x1800202b5  test    rax, rax
0x1800202b8  lea     rcx, [rdx-2]
0x1800202bc  cmovnz  rcx, rdx
0x1800202c0  mov     [rcx], si
0x1800202c3  lea     r8, [rsp+270h+Name]; lpName
0x1800202c8  xor     edx, edx; bInheritHandle
0x1800202ca  mov     ecx, 1F0003h; dwDesiredAccess
0x1800202cf  call    cs:__imp_OpenSemaphoreW
0x1800202d5  mov     [rsp+270h+var_240], rax
0x1800202da  test    rax, rax
0x1800202dd  jz      loc_1800203D0
0x1800202e3  lea     rdx, [rsp+270h+var_24C]; int *
0x1800202e8  mov     [rsp+270h+var_24C], esi
0x1800202ec  mov     rcx, rax; hHandle
0x1800202ef  mov     [rsp+270h+var_250], esi; int
0x1800202f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800202f8  mov     ebx, eax
0x1800202fa  test    eax, eax
0x1800202fc  jns     short loc_18002031E
0x1800202fe  mov     rcx, [rbp+178h]; this
0x180020305  lea     r8, aWil; "wil"
0x18002030c  mov     r9d, eax; char *
0x18002030f  mov     edx, 0D6h; void *
0x180020314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020319  jmp     loc_1800203DD
0x18002031e  lea     r8, asc_1800B3E80; "h"
0x180020325  mov     rdx, r15; unsigned __int64
0x180020328  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002032d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180020332  lea     r8, [rsp+270h+Name]; lpName
0x180020337  xor     edx, edx; bInheritHandle
0x180020339  mov     ecx, 1F0003h; dwDesiredAccess
0x18002033e  call    cs:__imp_OpenSemaphoreW
0x180020344  mov     [rsp+270h+var_248], rax
0x180020349  test    rax, rax
0x18002034c  jz      short loc_1800203AA
0x18002034e  lea     rdx, [rsp+270h+var_250]; int *
0x180020353  mov     rcx, rax; hHandle
0x180020356  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002035b  mov     ebx, eax
0x18002035d  test    eax, eax
0x18002035f  jns     short loc_18002037E
0x180020361  mov     rcx, [rbp+178h]; this
0x180020368  lea     r8, aWil; "wil"
0x18002036f  mov     r9d, eax; char *
0x180020372  mov     edx, 0DEh; void *
0x180020377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002037c  jmp     short loc_1800203C4
0x18002037e  lea     rcx, [rsp+270h+var_248]
0x180020383  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020388  movsxd  rax, [rsp+270h+var_24C]
0x18002038d  movsxd  rcx, [rsp+270h+var_250]
0x180020392  shl     rcx, 1Fh
0x180020396  or      rcx, rax
0x180020399  mov     [rdi], rcx
0x18002039c  lea     rcx, [rsp+270h+var_240]
0x1800203a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800203a6  xor     eax, eax
0x1800203a8  jmp     short loc_180020403
0x1800203aa  mov     rcx, [rbp+178h]; this
0x1800203b1  lea     r8, aWil; "wil"
0x1800203b8  mov     edx, 0DCh; void *
0x1800203bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800203c2  mov     ebx, eax
0x1800203c4  lea     rcx, [rsp+270h+var_248]
0x1800203c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800203ce  jmp     short loc_1800203DD
0x1800203d0  call    cs:__imp_GetLastError
0x1800203d6  cmp     eax, 2
0x1800203d9  jnz     short loc_1800203EB
0x1800203db  mov     ebx, esi
0x1800203dd  lea     rcx, [rsp+270h+var_240]
0x1800203e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800203e7  mov     eax, ebx
0x1800203e9  jmp     short loc_180020403
0x1800203eb  mov     rcx, [rbp+178h]; this
0x1800203f2  lea     r8, aWil; "wil"
0x1800203f9  mov     edx, 0D0h; void *
0x1800203fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020403  mov     rcx, [rbp+170h+var_20]
0x18002040a  xor     rcx, rsp; StackCookie
0x18002040d  call    __security_check_cookie
0x180020412  lea     r11, [rsp+270h+var_10]
0x18002041a  mov     rbx, [r11+20h]
0x18002041e  mov     rsi, [r11+28h]
0x180020422  mov     rsp, r11
0x180020425  pop     r15
0x180020427  pop     rdi
0x180020428  pop     rbp
0x180020429  retn
```
