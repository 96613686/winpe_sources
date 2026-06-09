# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007790`
- end: `0x1800079c8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800073b8`

## callees

- `0x1800016c0`
- `0x180006214`
- `0x180006958`
- `0x180007790`
- `0x180007ce4`
- `0x180008db0`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000789e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000789e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007956`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007854`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800078f7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007854`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800078f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000794a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000794a`

## string_xrefs

- `0x180007996`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800079b6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007790  mov     [rsp+arg_8], rbx
0x180007795  mov     [rsp+arg_10], rbp
0x18000779a  push    rsi
0x18000779b  push    rdi
0x18000779c  push    r12
0x18000779e  push    r14
0x1800077a0  push    r15
0x1800077a2  sub     rsp, 250h
0x1800077a9  mov     rax, cs:__security_cookie
0x1800077b0  xor     rax, rsp
0x1800077b3  mov     [rsp+278h+var_38], rax
0x1800077bb  mov     rax, 0C000000000000000h
0x1800077c5  mov     rbp, r9
0x1800077c8  mov     r8, rdx
0x1800077cb  mov     rbx, rcx
0x1800077ce  test    rax, r9
0x1800077d1  jnz     loc_1800079A8
0x1800077d7  xor     r12d, r12d
0x1800077da  lea     rax, [rsp+278h+Name]
0x1800077df  mov     ecx, 7FFFFFFEh
0x1800077e4  mov     edx, 104h
0x1800077e9  lea     esi, [r12+1]
0x1800077ee  test    rcx, rcx
0x1800077f1  jz      short loc_180007811
0x1800077f3  movzx   r9d, word ptr [r8]
0x1800077f7  test    r9w, r9w
0x1800077fb  jz      short loc_180007811
0x1800077fd  mov     [rax], r9w
0x180007801  add     r8, 2
0x180007805  add     rax, 2
0x180007809  sub     rcx, rsi
0x18000780c  sub     rdx, rsi; unsigned __int64
0x18000780f  jnz     short loc_1800077EE
0x180007811  test    rdx, rdx
0x180007814  lea     rcx, [rax-2]
0x180007818  lea     r8, aP0; "_p0"
0x18000781f  cmovnz  rcx, rax
0x180007823  mov     [rcx], r12w
0x180007827  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000782c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007831  mov     edx, ebp
0x180007833  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000783b  and     edx, 7FFFFFFFh; lInitialCount
0x180007841  mov     [rsp+278h+dwFlags], r12d; int
0x180007846  mov     r8d, esi
0x180007849  lea     r9, [rsp+278h+Name]; lpName
0x18000784e  cmova   r8d, edx; lMaximumCount
0x180007852  xor     ecx, ecx; lpSemaphoreAttributes
0x180007854  call    cs:__imp_CreateSemaphoreExW
0x18000785a  mov     r15, rax
0x18000785d  test    rax, rax
0x180007860  jnz     short loc_180007890
0x180007862  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007867  mov     edi, eax
0x180007869  test    eax, eax
0x18000786b  jns     short loc_1800078C4
0x18000786d  mov     rcx, [rsp+278h]; this
0x180007875  lea     r8, aWil; "wil"
0x18000787c  mov     r9d, eax; char *
0x18000787f  mov     edx, 8Bh; void *
0x180007884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007889  mov     eax, edi
0x18000788b  jmp     loc_180007962
0x180007890  call    cs:__imp_GetLastError
0x180007896  mov     rdi, [rbx]
0x180007899  test    rdi, rdi
0x18000789c  jz      short loc_1800078C1
0x18000789e  call    cs:__imp_GetLastError
0x1800078a4  mov     rcx, rdi; hObject
0x1800078a7  mov     r14d, eax
0x1800078aa  call    cs:__imp_CloseHandle
0x1800078b0  test    eax, eax
0x1800078b2  jz      loc_1800079AE
0x1800078b8  mov     ecx, r14d; dwErrCode
0x1800078bb  call    cs:__imp_SetLastError
0x1800078c1  mov     [rbx], r15
0x1800078c4  lea     r8, asc_180015C58; "h"
0x1800078cb  shr     rbp, 1Fh
0x1800078cf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800078d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800078d9  test    ebp, ebp
0x1800078db  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800078e3  lea     r9, [rsp+278h+Name]; lpName
0x1800078e8  mov     [rsp+278h+dwFlags], r12d; int
0x1800078ed  cmovnz  esi, ebp
0x1800078f0  mov     edx, ebp; lInitialCount
0x1800078f2  mov     r8d, esi; lMaximumCount
0x1800078f5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800078f7  call    cs:__imp_CreateSemaphoreExW
0x1800078fd  mov     rsi, rax
0x180007900  test    rax, rax
0x180007903  jnz     short loc_180007930
0x180007905  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000790a  mov     ebx, eax
0x18000790c  test    eax, eax
0x18000790e  jns     short loc_180007960
0x180007910  mov     rcx, [rsp+278h]; this
0x180007918  lea     r8, aWil; "wil"
0x18000791f  mov     r9d, eax; char *
0x180007922  mov     edx, 90h; void *
0x180007927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000792c  mov     eax, ebx
0x18000792e  jmp     short loc_180007962
0x180007930  call    cs:__imp_GetLastError
0x180007936  mov     rdi, [rbx+8]
0x18000793a  test    rdi, rdi
0x18000793d  jz      short loc_18000795C
0x18000793f  call    cs:__imp_GetLastError
0x180007945  mov     rcx, rdi; hObject
0x180007948  mov     ebp, eax
0x18000794a  call    cs:__imp_CloseHandle
0x180007950  test    eax, eax
0x180007952  jz      short loc_18000798E
0x180007954  mov     ecx, ebp; dwErrCode
0x180007956  call    cs:__imp_SetLastError
0x18000795c  mov     [rbx+8], rsi
0x180007960  xor     eax, eax
0x180007962  mov     rcx, [rsp+278h+var_38]
0x18000796a  xor     rcx, rsp; StackCookie
0x18000796d  call    __security_check_cookie
0x180007972  lea     r11, [rsp+278h+var_28]
0x18000797a  mov     rbx, [r11+38h]
0x18000797e  mov     rbp, [r11+40h]
0x180007982  mov     rsp, r11
0x180007985  pop     r15
0x180007987  pop     r14
0x180007989  pop     r12
0x18000798b  pop     rdi
0x18000798c  pop     rsi
0x18000798d  retn
0x18000798e  mov     rcx, [rsp+278h]; this
0x180007996  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000799d  mov     edx, 0A0Bh; void *
0x1800079a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800079a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800079ae  mov     rcx, [rsp+278h]; this
0x1800079b6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800079bd  mov     edx, 0A0Bh; void *
0x1800079c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
