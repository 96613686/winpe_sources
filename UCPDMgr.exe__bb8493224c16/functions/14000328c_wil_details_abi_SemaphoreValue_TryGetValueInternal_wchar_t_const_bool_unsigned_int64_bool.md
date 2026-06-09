# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000328c`
- end: `0x1400034a5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `537`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000503c`

## callees

- `0x1400011f8`
- `0x140002ba4`
- `0x140002bc8`
- `0x140002be8`
- `0x140003124`
- `0x14000328c`
- `0x14000a390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003339`
- `KERNEL32!GetLastError` at `0x140003339`
- `KERNEL32!OpenSemaphoreW` at `0x14000332b`
- `KERNEL32!OpenSemaphoreW` at `0x1400033e0`
- `KERNEL32!OpenSemaphoreW` at `0x14000332b`
- `KERNEL32!OpenSemaphoreW` at `0x1400033e0`
- `KERNEL32!CloseHandle` at `0x14000342d`
- `KERNEL32!CloseHandle` at `0x14000343c`
- `KERNEL32!CloseHandle` at `0x140003460`
- `KERNEL32!CloseHandle` at `0x14000342d`
- `KERNEL32!CloseHandle` at `0x14000343c`
- `KERNEL32!CloseHandle` at `0x140003460`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v16; // rdx
  int v17; // r8d
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  int v24; // r8d
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  int v31; // [rsp+28h] [rbp-E0h] BYREF
  int v32[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = (char *)a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v12, v13);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v31 = 0;
  v32[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v31);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v17, (const char *)(unsigned int)ValueFromSemaphore);
    goto LABEL_13;
  }
  StringCchCatW(Name, v16, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  if ( v19 )
  {
    v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, v32);
    LastError = v23;
    if ( v23 >= 0 )
    {
      if ( !CloseHandle(v22) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v27, v28);
      LastError = 0;
      *a3 = v31 | (unsigned __int64)((__int64)v32[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v24, (const char *)(unsigned int)v23);
      if ( !CloseHandle(v22) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v25, v26);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v20, v21);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v29, v30);
  return LastError;
}

```

## disassembly

```asm
0x14000328c  mov     rax, rsp
0x14000328f  mov     [rax+8], rbx
0x140003293  mov     [rax+10h], rsi
0x140003297  mov     [rax+20h], rdi
0x14000329b  push    rbp
0x14000329c  push    r14
0x14000329e  push    r15
0x1400032a0  lea     rbp, [rax-168h]
0x1400032a7  sub     rsp, 250h
0x1400032ae  mov     rax, cs:__security_cookie
0x1400032b5  xor     rax, rsp
0x1400032b8  mov     [rbp+160h+var_20], rax
0x1400032bf  xor     r15d, r15d
0x1400032c2  lea     rax, [rsp+260h+Name]
0x1400032c7  mov     [r8], r15
0x1400032ca  lea     rdx, [rsp+260h+Name]
0x1400032cf  sub     rcx, rax
0x1400032d2  mov     r14, r8
0x1400032d5  mov     r9d, 104h
0x1400032db  lea     rax, [r9+7FFFFEFAh]
0x1400032e2  test    rax, rax
0x1400032e5  jz      short loc_1400032FD
0x1400032e7  movzx   eax, word ptr [rdx+rcx]
0x1400032eb  test    ax, ax
0x1400032ee  jz      short loc_1400032FD
0x1400032f0  mov     [rdx], ax
0x1400032f3  add     rdx, 2; unsigned __int64
0x1400032f7  sub     r9, 1
0x1400032fb  jnz     short loc_1400032DB
0x1400032fd  test    r9, r9
0x140003300  lea     rax, [rdx-2]
0x140003304  lea     r8, aP0; "_p0"
0x14000330b  cmovnz  rax, rdx
0x14000330f  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140003314  mov     [rax], r15w
0x140003318  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000331d  mov     edi, 1F0003h
0x140003322  lea     r8, [rsp+260h+Name]; lpName
0x140003327  mov     ecx, edi; dwDesiredAccess
0x140003329  xor     edx, edx; bInheritHandle
0x14000332b  call    cs:__imp_OpenSemaphoreW
0x140003331  mov     rsi, rax
0x140003334  test    rax, rax
0x140003337  jnz     short loc_14000335E
0x140003339  call    cs:__imp_GetLastError
0x14000333f  cmp     eax, 2
0x140003342  jnz     short loc_140003349
0x140003344  mov     ebx, r15d
0x140003347  jmp     short loc_14000338F
0x140003349  mov     rcx, [rbp+168h]; this
0x140003350  mov     edx, 0CDh; void *
0x140003355  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000335a  mov     ebx, eax
0x14000335c  jmp     short loc_14000338F
0x14000335e  lea     rdx, [rsp+260h+var_240]; int *
0x140003363  mov     [rsp+260h+var_240], r15d; int
0x140003368  mov     rcx, rsi; hHandle
0x14000336b  mov     [rsp+260h+var_23C], r15d
0x140003370  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140003375  mov     ebx, eax
0x140003377  test    eax, eax
0x140003379  jns     short loc_1400033C6
0x14000337b  mov     rcx, [rbp+168h]; this
0x140003382  mov     r9d, eax; char *
0x140003385  mov     edx, 0D3h; void *
0x14000338a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000338f  test    rsi, rsi
0x140003392  jnz     loc_14000345D
0x140003398  mov     eax, ebx
0x14000339a  mov     rcx, [rbp+160h+var_20]
0x1400033a1  xor     rcx, rsp; StackCookie
0x1400033a4  call    __security_check_cookie
0x1400033a9  lea     r11, [rsp+260h+var_10]
0x1400033b1  mov     rbx, [r11+20h]
0x1400033b5  mov     rsi, [r11+28h]
0x1400033b9  mov     rdi, [r11+38h]
0x1400033bd  mov     rsp, r11
0x1400033c0  pop     r15
0x1400033c2  pop     r14
0x1400033c4  pop     rbp
0x1400033c5  retn
0x1400033c6  lea     r8, asc_140011958; "h"
0x1400033cd  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1400033d2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400033d7  lea     r8, [rsp+260h+Name]; lpName
0x1400033dc  xor     edx, edx; bInheritHandle
0x1400033de  mov     ecx, edi; dwDesiredAccess
0x1400033e0  call    cs:__imp_OpenSemaphoreW
0x1400033e6  mov     rdi, rax
0x1400033e9  test    rax, rax
0x1400033ec  jnz     short loc_140003403
0x1400033ee  mov     rcx, [rbp+168h]; this
0x1400033f5  mov     edx, 0D9h; void *
0x1400033fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400033ff  mov     ebx, eax
0x140003401  jmp     short loc_14000345D
0x140003403  lea     rdx, [rsp+260h+var_23C]; int *
0x140003408  mov     rcx, rdi; hHandle
0x14000340b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140003410  mov     ebx, eax
0x140003412  test    eax, eax
0x140003414  jns     short loc_140003439
0x140003416  mov     rcx, [rbp+168h]; this
0x14000341d  mov     r9d, eax; char *
0x140003420  mov     edx, 0DBh; void *
0x140003425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000342a  mov     rcx, rdi; hObject
0x14000342d  call    cs:__imp_CloseHandle
0x140003433  test    eax, eax
0x140003435  jz      short loc_140003481
0x140003437  jmp     short loc_14000345D
0x140003439  mov     rcx, rdi; hObject
0x14000343c  call    cs:__imp_CloseHandle
0x140003442  test    eax, eax
0x140003444  jz      short loc_14000346F
0x140003446  movsxd  rcx, [rsp+260h+var_23C]
0x14000344b  mov     ebx, r15d
0x14000344e  movsxd  rax, [rsp+260h+var_240]
0x140003453  shl     rcx, 1Fh
0x140003457  or      rcx, rax
0x14000345a  mov     [r14], rcx
0x14000345d  mov     rcx, rsi; hObject
0x140003460  call    cs:__imp_CloseHandle
0x140003466  test    eax, eax
0x140003468  jz      short loc_140003493
0x14000346a  jmp     loc_140003398
0x14000346f  mov     rcx, [rbp+168h]; this
0x140003476  mov     edx, 9CDh; void *
0x14000347b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003481  mov     rcx, [rbp+168h]; this
0x140003488  mov     edx, 9CDh; void *
0x14000348d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003493  mov     rcx, [rbp+168h]; this
0x14000349a  mov     edx, 9CDh; void *
0x14000349f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
