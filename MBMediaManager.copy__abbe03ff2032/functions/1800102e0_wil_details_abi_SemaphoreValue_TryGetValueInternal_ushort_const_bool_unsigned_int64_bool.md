# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800102e0`
- end: `0x1800105bc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `732`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ff1c`
- `0x18000ffa0`

## callees

- `0x1800102e0`
- `0x1800105c4`
- `0x1800105f0`
- `0x18001b1b4`
- `0x18001cb10`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800103d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800104dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800103d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800104dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e3`

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
  __int64 v6; // rax
  __int64 v7; // r10
  WCHAR *v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  const unsigned __int16 *v14; // r8
  bool v15; // zf
  __int64 v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // r9
  WCHAR *v19; // rcx
  wil::details *v20; // rax
  wil::details *v21; // rbx
  const char *v22; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v26; // rcx
  WCHAR *v27; // rax
  __int64 v28; // rdx
  WCHAR *v29; // r8
  const unsigned __int16 *v30; // rcx
  __int64 v31; // rsi
  WCHAR *v32; // rdx
  wil::details *v33; // rax
  const char *v34; // r9
  wil::details *v35; // rdi
  int v36; // eax
  void *v37; // rdx
  unsigned int v38; // esi
  void *v39; // rdx
  void *v40; // rdx
  void *v41; // rdx
  void *v42; // rdx
  int v43; // [rsp+20h] [rbp-248h] BYREF
  int v44[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

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
  v10 = v4 - 1;
  v11 = Name;
  if ( v7 )
    v10 = v4;
  *v10 = 0;
  v12 = 260;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = 260 - v12;
  if ( v12 )
  {
    v14 = L"_p0";
    v16 = v12;
    v15 = v13 == 260;
    v17 = 2147483646;
    v18 = &Name[v13];
    if ( !v15 )
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*v14 )
          break;
        *v18++ = *v14++;
        --v17;
        --v16;
      }
      while ( v16 );
    }
    v19 = v18 - 1;
    if ( v16 )
      v19 = v18;
    *v19 = 0;
  }
  v20 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v20;
  if ( !v20 )
  {
    if ( GetLastError() == 2 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v22);
  }
  v44[0] = 0;
  v43 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, v44);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v43);
    goto LABEL_38;
  }
  v26 = 260;
  v27 = Name;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  v28 = 260 - v26;
  if ( v26 )
  {
    v29 = &Name[v28];
    v30 = L"h";
    v31 = 260 - v28;
    if ( 260 != v28 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v30 )
          break;
        *v29++ = *v30++;
        --v5;
        --v31;
      }
      while ( v31 );
    }
    v32 = v29 - 1;
    if ( v31 )
      v32 = v29;
    *v32 = 0;
  }
  v33 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v35 = v33;
  if ( !v33 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v34);
LABEL_38:
    wil::details::CloseHandle(v21, v42);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v33, &v43);
  v38 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v43);
    wil::details::CloseHandle(v35, v40);
    wil::details::CloseHandle(v21, v41);
    return v38;
  }
  else
  {
    wil::details::CloseHandle(v35, v37);
    *a3 = v44[0] | (unsigned __int64)((__int64)v43 << 31);
    wil::details::CloseHandle(v21, v39);
    return 0;
  }
}

```

## disassembly

```asm
0x1800102e0  mov     [rsp+arg_8], rbx
0x1800102e5  mov     [rsp+arg_18], rbp
0x1800102ea  push    rsi
0x1800102eb  push    r14
0x1800102ed  push    r15
0x1800102ef  sub     rsp, 250h
0x1800102f6  mov     rax, cs:__security_cookie
0x1800102fd  xor     rax, rsp
0x180010300  mov     [rsp+268h+var_28], rax
0x180010308  xor     r15d, r15d
0x18001030b  lea     r9, [rsp+268h+Name]
0x180010310  mov     ebp, 7FFFFFFEh
0x180010315  mov     [r8], r15
0x180010318  mov     esi, 104h
0x18001031d  mov     eax, ebp
0x18001031f  mov     r10d, esi
0x180010322  mov     r14, r8
0x180010325  mov     rdx, rcx
0x180010328  test    rax, rax
0x18001032b  jz      short loc_18001034A
0x18001032d  movzx   ecx, word ptr [rdx]
0x180010330  test    cx, cx
0x180010333  jz      short loc_18001034A
0x180010335  mov     [r9], cx
0x180010339  add     rdx, 2
0x18001033d  add     r9, 2
0x180010341  dec     rax
0x180010344  sub     r10, 1
0x180010348  jnz     short loc_180010328
0x18001034a  test    r10, r10
0x18001034d  lea     rcx, [r9-2]
0x180010351  lea     rax, [rsp+268h+Name]
0x180010356  cmovnz  rcx, r9
0x18001035a  mov     [rcx], r15w
0x18001035e  mov     rcx, rsi
0x180010361  cmp     [rax], r15w
0x180010365  jz      short loc_180010371
0x180010367  add     rax, 2
0x18001036b  sub     rcx, 1
0x18001036f  jnz     short loc_180010361
0x180010371  mov     r9, rsi
0x180010374  sub     r9, rcx
0x180010377  test    rcx, rcx
0x18001037a  cmovz   r9, r15
0x18001037e  jz      short loc_1800103C9
0x180010380  mov     rdx, rsi
0x180010383  lea     r8, aP0; "_p0"
0x18001038a  sub     rdx, r9
0x18001038d  mov     rax, rbp
0x180010390  lea     r9, [rsp+r9*2+268h+Name]
0x180010395  jz      short loc_1800103BA
0x180010397  test    rax, rax
0x18001039a  jz      short loc_1800103BA
0x18001039c  movzx   ecx, word ptr [r8]
0x1800103a0  test    cx, cx
0x1800103a3  jz      short loc_1800103BA
0x1800103a5  mov     [r9], cx
0x1800103a9  add     r8, 2
0x1800103ad  add     r9, 2
0x1800103b1  dec     rax
0x1800103b4  sub     rdx, 1
0x1800103b8  jnz     short loc_180010397
0x1800103ba  test    rdx, rdx
0x1800103bd  lea     rcx, [r9-2]
0x1800103c1  cmovnz  rcx, r9
0x1800103c5  mov     [rcx], r15w
0x1800103c9  lea     r8, [rsp+268h+Name]; lpName
0x1800103ce  xor     edx, edx; bInheritHandle
0x1800103d0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800103d5  call    cs:__imp_OpenSemaphoreW
0x1800103db  mov     rbx, rax
0x1800103de  test    rax, rax
0x1800103e1  jnz     short loc_180010434
0x1800103e3  call    cs:__imp_GetLastError
0x1800103e9  cmp     eax, 2
0x1800103ec  jz      loc_1800105B5
0x1800103f2  mov     rcx, [rsp+268h]; this
0x1800103fa  lea     r8, aWil; "wil"
0x180010401  mov     edx, 0D0h; void *
0x180010406  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001040b  mov     rcx, [rsp+268h+var_28]
0x180010413  xor     rcx, rsp; StackCookie
0x180010416  call    __security_check_cookie
0x18001041b  lea     r11, [rsp+268h+var_18]
0x180010423  mov     rbx, [r11+28h]
0x180010427  mov     rbp, [r11+38h]
0x18001042b  mov     rsp, r11
0x18001042e  pop     r15
0x180010430  pop     r14
0x180010432  pop     rsi
0x180010433  retn
0x180010434  lea     rdx, [rsp+268h+var_244]; int *
0x180010439  mov     [rsp+268h+arg_0], rdi
0x180010441  mov     rcx, rbx; hHandle
0x180010444  mov     [rsp+268h+var_244], r15d
0x180010449  mov     [rsp+268h+var_248], r15d; int
0x18001044e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010453  mov     edi, eax
0x180010455  test    eax, eax
0x180010457  js      loc_180010597
0x18001045d  mov     rcx, rsi
0x180010460  lea     rax, [rsp+268h+Name]
0x180010465  cmp     [rax], r15w
0x180010469  jz      short loc_180010475
0x18001046b  add     rax, 2
0x18001046f  sub     rcx, 1
0x180010473  jnz     short loc_180010465
0x180010475  mov     rdx, rsi
0x180010478  sub     rdx, rcx
0x18001047b  test    rcx, rcx
0x18001047e  cmovz   rdx, r15
0x180010482  jz      short loc_1800104D1
0x180010484  lea     r8, [rsp+268h+Name]
0x180010489  lea     r8, [r8+rdx*2]
0x18001048d  lea     rcx, asc_180063478; "h"
0x180010494  sub     rsi, rdx
0x180010497  jz      short loc_1800104C2
0x180010499  nop     dword ptr [rax+00000000h]
0x1800104a0  test    rbp, rbp
0x1800104a3  jz      short loc_1800104C2
0x1800104a5  movzx   eax, word ptr [rcx]
0x1800104a8  test    ax, ax
0x1800104ab  jz      short loc_1800104C2
0x1800104ad  mov     [r8], ax
0x1800104b1  add     rcx, 2
0x1800104b5  add     r8, 2
0x1800104b9  dec     rbp
0x1800104bc  sub     rsi, 1
0x1800104c0  jnz     short loc_1800104A0
0x1800104c2  test    rsi, rsi
0x1800104c5  lea     rdx, [r8-2]
0x1800104c9  cmovnz  rdx, r8
0x1800104cd  mov     [rdx], r15w
0x1800104d1  lea     r8, [rsp+268h+Name]; lpName
0x1800104d6  xor     edx, edx; bInheritHandle
0x1800104d8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800104dd  call    cs:__imp_OpenSemaphoreW
0x1800104e3  mov     rdi, rax
0x1800104e6  test    rax, rax
0x1800104e9  jz      loc_180010570
0x1800104ef  lea     rdx, [rsp+268h+var_248]; int *
0x1800104f4  mov     rcx, rax; hHandle
0x1800104f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800104fc  mov     esi, eax
0x1800104fe  test    eax, eax
0x180010500  js      short loc_180010535
0x180010502  mov     rcx, rdi; this
0x180010505  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001050a  movsxd  rax, [rsp+268h+var_244]
0x18001050f  movsxd  rcx, [rsp+268h+var_248]
0x180010514  shl     rcx, 1Fh
0x180010518  or      rcx, rax
0x18001051b  mov     [r14], rcx
0x18001051e  mov     rcx, rbx; this
0x180010521  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010526  xor     eax, eax
0x180010528  mov     rdi, [rsp+268h+arg_0]
0x180010530  jmp     loc_18001040B
0x180010535  mov     rcx, [rsp+268h]; this
0x18001053d  lea     r8, aWil; "wil"
0x180010544  mov     r9d, esi; char *
0x180010547  mov     edx, 0DEh; void *
0x18001054c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010551  mov     rcx, rdi; this
0x180010554  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010559  mov     rcx, rbx; this
0x18001055c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010561  mov     rdi, [rsp+268h+arg_0]
0x180010569  mov     eax, esi
0x18001056b  jmp     loc_18001040B
0x180010570  mov     rcx, [rsp+268h]; this
0x180010578  lea     r8, aWil; "wil"
0x18001057f  mov     edx, 0DCh; void *
0x180010584  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010589  mov     edi, eax
0x18001058b  mov     rcx, rbx; this
0x18001058e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010593  mov     eax, edi
0x180010595  jmp     short loc_180010528
0x180010597  mov     rcx, [rsp+268h]; this
0x18001059f  lea     r8, aWil; "wil"
0x1800105a6  mov     r9d, edi; char *
0x1800105a9  mov     edx, 0D6h; void *
0x1800105ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105b3  jmp     short loc_18001058B
0x1800105b5  xor     eax, eax
0x1800105b7  jmp     loc_18001040B
```
