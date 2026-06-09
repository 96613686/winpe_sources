# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006790`
- end: `0x1800069ba`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005828`

## callees

- `0x1800038f0`
- `0x180006790`
- `0x180007468`
- `0x180009784`
- `0x18000a114`
- `0x18000a924`
- `0x18000a934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006854`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800068f7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006854`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800068f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000693f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000693f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000694a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000694a`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
  const char *v31; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
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
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006790  mov     [rsp+arg_8], rbx
0x180006795  mov     [rsp+arg_10], rbp
0x18000679a  push    rsi
0x18000679b  push    rdi
0x18000679c  push    r12
0x18000679e  push    r14
0x1800067a0  push    r15
0x1800067a2  sub     rsp, 250h
0x1800067a9  mov     rax, cs:__security_cookie
0x1800067b0  xor     rax, rsp
0x1800067b3  mov     [rsp+278h+var_38], rax
0x1800067bb  mov     rax, 0C000000000000000h
0x1800067c5  mov     rbp, r9
0x1800067c8  mov     r8, rdx
0x1800067cb  mov     rbx, rcx
0x1800067ce  test    rax, r9
0x1800067d1  jnz     loc_1800069A1
0x1800067d7  xor     r12d, r12d
0x1800067da  lea     rax, [rsp+278h+Name]
0x1800067df  mov     ecx, 7FFFFFFEh
0x1800067e4  mov     edx, 104h
0x1800067e9  lea     esi, [r12+1]
0x1800067ee  test    rcx, rcx
0x1800067f1  jz      short loc_180006811
0x1800067f3  movzx   r9d, word ptr [r8]
0x1800067f7  test    r9w, r9w
0x1800067fb  jz      short loc_180006811
0x1800067fd  mov     [rax], r9w
0x180006801  add     r8, 2
0x180006805  add     rax, 2
0x180006809  sub     rcx, rsi
0x18000680c  sub     rdx, rsi; unsigned __int64
0x18000680f  jnz     short loc_1800067EE
0x180006811  test    rdx, rdx
0x180006814  lea     rcx, [rax-2]
0x180006818  lea     r8, aP0; "_p0"
0x18000681f  cmovnz  rcx, rax
0x180006823  mov     [rcx], r12w
0x180006827  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000682c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006831  mov     edx, ebp
0x180006833  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000683b  and     edx, 7FFFFFFFh; lInitialCount
0x180006841  mov     [rsp+278h+dwFlags], r12d; int
0x180006846  mov     r8d, esi
0x180006849  lea     r9, [rsp+278h+Name]; lpName
0x18000684e  cmova   r8d, edx; lMaximumCount
0x180006852  xor     ecx, ecx; lpSemaphoreAttributes
0x180006854  call    cs:__imp_CreateSemaphoreExW
0x18000685a  mov     r15, rax
0x18000685d  test    rax, rax
0x180006860  jnz     short loc_180006890
0x180006862  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006867  mov     edi, eax
0x180006869  test    eax, eax
0x18000686b  jns     short loc_1800068C4
0x18000686d  mov     rcx, [rsp+278h]; this
0x180006875  lea     r8, aWil; "wil"
0x18000687c  mov     r9d, eax; char *
0x18000687f  mov     edx, 8Bh; void *
0x180006884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006889  mov     eax, edi
0x18000688b  jmp     loc_180006962
0x180006890  call    cs:__imp_GetLastError
0x180006896  mov     rdi, [rbx]
0x180006899  test    rdi, rdi
0x18000689c  jz      short loc_1800068C1
0x18000689e  call    cs:__imp_GetLastError
0x1800068a4  mov     rcx, rdi; hObject
0x1800068a7  mov     r14d, eax
0x1800068aa  call    cs:__imp_CloseHandle
0x1800068b0  test    eax, eax
0x1800068b2  jz      loc_1800069A7
0x1800068b8  mov     ecx, r14d; dwErrCode
0x1800068bb  call    cs:__imp_SetLastError
0x1800068c1  mov     [rbx], r15
0x1800068c4  lea     r8, asc_1800239F8; "h"
0x1800068cb  shr     rbp, 1Fh
0x1800068cf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800068d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068d9  test    ebp, ebp
0x1800068db  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800068e3  lea     r9, [rsp+278h+Name]; lpName
0x1800068e8  mov     [rsp+278h+dwFlags], r12d; int
0x1800068ed  cmovnz  esi, ebp
0x1800068f0  mov     edx, ebp; lInitialCount
0x1800068f2  mov     r8d, esi; lMaximumCount
0x1800068f5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800068f7  call    cs:__imp_CreateSemaphoreExW
0x1800068fd  mov     rsi, rax
0x180006900  test    rax, rax
0x180006903  jnz     short loc_180006930
0x180006905  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000690a  mov     ebx, eax
0x18000690c  test    eax, eax
0x18000690e  jns     short loc_180006960
0x180006910  mov     rcx, [rsp+278h]; this
0x180006918  lea     r8, aWil; "wil"
0x18000691f  mov     r9d, eax; char *
0x180006922  mov     edx, 90h; void *
0x180006927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000692c  mov     eax, ebx
0x18000692e  jmp     short loc_180006962
0x180006930  call    cs:__imp_GetLastError
0x180006936  mov     rdi, [rbx+8]
0x18000693a  test    rdi, rdi
0x18000693d  jz      short loc_18000695C
0x18000693f  call    cs:__imp_GetLastError
0x180006945  mov     rcx, rdi; hObject
0x180006948  mov     ebp, eax
0x18000694a  call    cs:__imp_CloseHandle
0x180006950  test    eax, eax
0x180006952  jz      short loc_18000698E
0x180006954  mov     ecx, ebp; dwErrCode
0x180006956  call    cs:__imp_SetLastError
0x18000695c  mov     [rbx+8], rsi
0x180006960  xor     eax, eax
0x180006962  mov     rcx, [rsp+278h+var_38]
0x18000696a  xor     rcx, rsp; StackCookie
0x18000696d  call    __security_check_cookie
0x180006972  lea     r11, [rsp+278h+var_28]
0x18000697a  mov     rbx, [r11+38h]
0x18000697e  mov     rbp, [r11+40h]
0x180006982  mov     rsp, r11
0x180006985  pop     r15
0x180006987  pop     r14
0x180006989  pop     r12
0x18000698b  pop     rdi
0x18000698c  pop     rsi
0x18000698d  retn
0x18000698e  mov     rcx, [rsp+278h]; this
0x180006996  mov     edx, 0A0Bh; void *
0x18000699b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800069a1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800069a7  mov     rcx, [rsp+278h]; this
0x1800069af  mov     edx, 0A0Bh; void *
0x1800069b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
