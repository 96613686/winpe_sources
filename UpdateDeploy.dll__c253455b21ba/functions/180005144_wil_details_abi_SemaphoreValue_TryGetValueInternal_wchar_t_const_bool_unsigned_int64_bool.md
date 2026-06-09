# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005144`
- end: `0x180005379`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180002214`
- `0x180003180`
- `0x180003bec`
- `0x180004d64`
- `0x180004fd0`
- `0x180005144`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052a6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005334`

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
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // [rsp+28h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+2Ch] [rbp-DCh] BYREF
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v27 = 0;
  v28[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
    goto LABEL_13;
  }
  StringCchCatW(Name, v15, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( v17 )
  {
    v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, v28);
    LastError = v20;
    if ( v20 >= 0 )
    {
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v23, v24);
      LastError = 0;
      *a3 = v27 | (unsigned __int64)((__int64)v28[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v20,
        v27);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v21, v22);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v18);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v25, v26);
  return LastError;
}

```

## disassembly

```asm
0x180005144  mov     rax, rsp
0x180005147  mov     [rax+8], rbx
0x18000514b  mov     [rax+10h], rsi
0x18000514f  mov     [rax+20h], rdi
0x180005153  push    rbp
0x180005154  push    r14
0x180005156  push    r15
0x180005158  lea     rbp, [rax-168h]
0x18000515f  sub     rsp, 250h
0x180005166  mov     rax, cs:__security_cookie
0x18000516d  xor     rax, rsp
0x180005170  mov     [rbp+160h+var_20], rax
0x180005177  xor     r15d, r15d
0x18000517a  lea     rax, [rsp+260h+Name]
0x18000517f  mov     [r8], r15
0x180005182  lea     rdx, [rsp+260h+Name]
0x180005187  sub     rcx, rax
0x18000518a  mov     r14, r8
0x18000518d  mov     r9d, 104h
0x180005193  lea     rax, [r9+7FFFFEFAh]
0x18000519a  test    rax, rax
0x18000519d  jz      short loc_1800051B5
0x18000519f  movzx   eax, word ptr [rdx+rcx]
0x1800051a3  test    ax, ax
0x1800051a6  jz      short loc_1800051B5
0x1800051a8  mov     [rdx], ax
0x1800051ab  add     rdx, 2; unsigned __int64
0x1800051af  sub     r9, 1
0x1800051b3  jnz     short loc_180005193
0x1800051b5  test    r9, r9
0x1800051b8  lea     rax, [rdx-2]
0x1800051bc  lea     r8, aP0; "_p0"
0x1800051c3  cmovnz  rax, rdx
0x1800051c7  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800051cc  mov     [rax], r15w
0x1800051d0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800051d5  mov     edi, 1F0003h
0x1800051da  lea     r8, [rsp+260h+Name]; lpName
0x1800051df  mov     ecx, edi; dwDesiredAccess
0x1800051e1  xor     edx, edx; bInheritHandle
0x1800051e3  call    cs:__imp_OpenSemaphoreW
0x1800051e9  mov     rsi, rax
0x1800051ec  test    rax, rax
0x1800051ef  jnz     short loc_18000521D
0x1800051f1  call    cs:__imp_GetLastError
0x1800051f7  cmp     eax, 2
0x1800051fa  jnz     short loc_180005201
0x1800051fc  mov     ebx, r15d
0x1800051ff  jmp     short loc_180005255
0x180005201  mov     rcx, [rbp+168h]; this
0x180005208  lea     r8, aWil; "wil"
0x18000520f  mov     edx, 0CDh; void *
0x180005214  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005219  mov     ebx, eax
0x18000521b  jmp     short loc_180005255
0x18000521d  lea     rdx, [rsp+260h+var_240]; int *
0x180005222  mov     [rsp+260h+var_240], r15d; int
0x180005227  mov     rcx, rsi; hHandle
0x18000522a  mov     [rsp+260h+var_23C], r15d
0x18000522f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005234  mov     ebx, eax
0x180005236  test    eax, eax
0x180005238  jns     short loc_18000528C
0x18000523a  mov     rcx, [rbp+168h]; this
0x180005241  lea     r8, aWil; "wil"
0x180005248  mov     r9d, eax; char *
0x18000524b  mov     edx, 0D3h; void *
0x180005250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005255  test    rsi, rsi
0x180005258  jnz     loc_180005331
0x18000525e  mov     eax, ebx
0x180005260  mov     rcx, [rbp+160h+var_20]
0x180005267  xor     rcx, rsp; StackCookie
0x18000526a  call    __security_check_cookie
0x18000526f  lea     r11, [rsp+260h+var_10]
0x180005277  mov     rbx, [r11+20h]
0x18000527b  mov     rsi, [r11+28h]
0x18000527f  mov     rdi, [r11+38h]
0x180005283  mov     rsp, r11
0x180005286  pop     r15
0x180005288  pop     r14
0x18000528a  pop     rbp
0x18000528b  retn
0x18000528c  lea     r8, asc_1800703A8; "h"
0x180005293  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180005298  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000529d  lea     r8, [rsp+260h+Name]; lpName
0x1800052a2  xor     edx, edx; bInheritHandle
0x1800052a4  mov     ecx, edi; dwDesiredAccess
0x1800052a6  call    cs:__imp_OpenSemaphoreW
0x1800052ac  mov     rdi, rax
0x1800052af  test    rax, rax
0x1800052b2  jnz     short loc_1800052D0
0x1800052b4  mov     rcx, [rbp+168h]; this
0x1800052bb  lea     r8, aWil; "wil"
0x1800052c2  mov     edx, 0D9h; void *
0x1800052c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800052cc  mov     ebx, eax
0x1800052ce  jmp     short loc_180005331
0x1800052d0  lea     rdx, [rsp+260h+var_23C]; int *
0x1800052d5  mov     rcx, rdi; hHandle
0x1800052d8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800052dd  mov     ebx, eax
0x1800052df  test    eax, eax
0x1800052e1  jns     short loc_18000530D
0x1800052e3  mov     rcx, [rbp+168h]; this
0x1800052ea  lea     r8, aWil; "wil"
0x1800052f1  mov     r9d, eax; char *
0x1800052f4  mov     edx, 0DBh; void *
0x1800052f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052fe  mov     rcx, rdi; hObject
0x180005301  call    cs:__imp_CloseHandle
0x180005307  test    eax, eax
0x180005309  jz      short loc_180005355
0x18000530b  jmp     short loc_180005331
0x18000530d  mov     rcx, rdi; hObject
0x180005310  call    cs:__imp_CloseHandle
0x180005316  test    eax, eax
0x180005318  jz      short loc_180005343
0x18000531a  movsxd  rcx, [rsp+260h+var_23C]
0x18000531f  mov     ebx, r15d
0x180005322  movsxd  rax, [rsp+260h+var_240]
0x180005327  shl     rcx, 1Fh
0x18000532b  or      rcx, rax
0x18000532e  mov     [r14], rcx
0x180005331  mov     rcx, rsi; hObject
0x180005334  call    cs:__imp_CloseHandle
0x18000533a  test    eax, eax
0x18000533c  jz      short loc_180005367
0x18000533e  jmp     loc_18000525E
0x180005343  mov     rcx, [rbp+168h]; this
0x18000534a  mov     edx, 9D1h; void *
0x18000534f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005355  mov     rcx, [rbp+168h]; this
0x18000535c  mov     edx, 9D1h; void *
0x180005361  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005367  mov     rcx, [rbp+168h]; this
0x18000536e  mov     edx, 9D1h; void *
0x180005373  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
