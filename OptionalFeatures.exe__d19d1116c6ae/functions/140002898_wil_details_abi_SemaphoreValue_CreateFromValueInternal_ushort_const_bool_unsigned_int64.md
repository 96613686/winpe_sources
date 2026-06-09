# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002898`
- end: `0x140002aa5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400024f4`

## callees

- `0x140002898`
- `0x140003108`
- `0x140003e94`
- `0x140004144`
- `0x14000492c`
- `0x14000493c`
- `0x140004ba0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400029bc`
- `KERNEL32!SetLastError` at `0x140002a41`
- `KERNEL32!SetLastError` at `0x1400029bc`
- `KERNEL32!SetLastError` at `0x140002a41`
- `KERNEL32!GetLastError` at `0x140002991`
- `KERNEL32!GetLastError` at `0x14000299f`
- `KERNEL32!GetLastError` at `0x140002a1b`
- `KERNEL32!GetLastError` at `0x140002a2a`
- `KERNEL32!GetLastError` at `0x140002991`
- `KERNEL32!GetLastError` at `0x14000299f`
- `KERNEL32!GetLastError` at `0x140002a1b`
- `KERNEL32!GetLastError` at `0x140002a2a`
- `KERNEL32!CreateSemaphoreExW` at `0x14000295c`
- `KERNEL32!CreateSemaphoreExW` at `0x1400029f8`
- `KERNEL32!CreateSemaphoreExW` at `0x14000295c`
- `KERNEL32!CreateSemaphoreExW` at `0x1400029f8`
- `KERNEL32!CloseHandle` at `0x1400029ab`
- `KERNEL32!CloseHandle` at `0x140002a35`
- `KERNEL32!CloseHandle` at `0x1400029ab`
- `KERNEL32!CloseHandle` at `0x140002a35`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140002898  mov     [rsp+arg_8], rbx
0x14000289d  mov     [rsp+arg_10], rbp
0x1400028a2  push    rsi
0x1400028a3  push    rdi
0x1400028a4  push    r12
0x1400028a6  push    r14
0x1400028a8  push    r15
0x1400028aa  sub     rsp, 250h
0x1400028b1  mov     rax, cs:__security_cookie
0x1400028b8  xor     rax, rsp
0x1400028bb  mov     [rsp+278h+var_38], rax
0x1400028c3  mov     rax, 0C000000000000000h
0x1400028cd  mov     rbp, r9
0x1400028d0  mov     r8, rdx
0x1400028d3  mov     rdi, rcx
0x1400028d6  test    rax, r9
0x1400028d9  jnz     loc_140002A8C
0x1400028df  xor     r12d, r12d
0x1400028e2  lea     rax, [rsp+278h+Name]
0x1400028e7  mov     ecx, 7FFFFFFEh
0x1400028ec  mov     edx, 104h
0x1400028f1  lea     esi, [r12+1]
0x1400028f6  test    rcx, rcx
0x1400028f9  jz      short loc_140002919
0x1400028fb  movzx   r9d, word ptr [r8]
0x1400028ff  test    r9w, r9w
0x140002903  jz      short loc_140002919
0x140002905  mov     [rax], r9w
0x140002909  add     r8, 2
0x14000290d  add     rax, 2
0x140002911  sub     rcx, rsi
0x140002914  sub     rdx, rsi; unsigned __int64
0x140002917  jnz     short loc_1400028F6
0x140002919  test    rdx, rdx
0x14000291c  lea     rcx, [rax-2]
0x140002920  lea     r8, aP0; "_p0"
0x140002927  cmovnz  rcx, rax
0x14000292b  mov     [rcx], r12w
0x14000292f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140002934  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002939  mov     edx, ebp
0x14000293b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002943  and     edx, 7FFFFFFFh; lInitialCount
0x140002949  mov     [rsp+278h+dwFlags], r12d; int
0x14000294e  mov     r8d, esi
0x140002951  lea     r9, [rsp+278h+Name]; lpName
0x140002956  cmova   r8d, edx; lMaximumCount
0x14000295a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000295c  call    cs:__imp_CreateSemaphoreExW
0x140002962  mov     r15, rax
0x140002965  test    rax, rax
0x140002968  jnz     short loc_140002991
0x14000296a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000296f  mov     ebx, eax
0x140002971  test    eax, eax
0x140002973  jns     short loc_1400029C5
0x140002975  mov     edx, 8Bh; void *
0x14000297a  mov     rcx, [rsp+278h]; this
0x140002982  mov     r9d, ebx; char *
0x140002985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000298a  mov     eax, ebx
0x14000298c  jmp     loc_140002A4D
0x140002991  call    cs:__imp_GetLastError
0x140002997  mov     rbx, [rdi]
0x14000299a  test    rbx, rbx
0x14000299d  jz      short loc_1400029C2
0x14000299f  call    cs:__imp_GetLastError
0x1400029a5  mov     rcx, rbx; hObject
0x1400029a8  mov     r14d, eax
0x1400029ab  call    cs:__imp_CloseHandle
0x1400029b1  test    eax, eax
0x1400029b3  jz      loc_140002A92
0x1400029b9  mov     ecx, r14d; dwErrCode
0x1400029bc  call    cs:__imp_SetLastError
0x1400029c2  mov     [rdi], r15
0x1400029c5  lea     r8, asc_140006788; "h"
0x1400029cc  shr     rbp, 1Fh
0x1400029d0  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400029d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400029da  test    ebp, ebp
0x1400029dc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400029e4  lea     r9, [rsp+278h+Name]; lpName
0x1400029e9  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1400029ee  cmovnz  esi, ebp
0x1400029f1  mov     edx, ebp; lInitialCount
0x1400029f3  mov     r8d, esi; lMaximumCount
0x1400029f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1400029f8  call    cs:__imp_CreateSemaphoreExW
0x1400029fe  mov     rsi, rax
0x140002a01  test    rax, rax
0x140002a04  jnz     short loc_140002A1B
0x140002a06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002a0b  mov     ebx, eax
0x140002a0d  test    eax, eax
0x140002a0f  jns     short loc_140002A4B
0x140002a11  mov     edx, 90h
0x140002a16  jmp     loc_14000297A
0x140002a1b  call    cs:__imp_GetLastError
0x140002a21  mov     rbx, [rdi+8]
0x140002a25  test    rbx, rbx
0x140002a28  jz      short loc_140002A47
0x140002a2a  call    cs:__imp_GetLastError
0x140002a30  mov     rcx, rbx; hObject
0x140002a33  mov     ebp, eax
0x140002a35  call    cs:__imp_CloseHandle
0x140002a3b  test    eax, eax
0x140002a3d  jz      short loc_140002A79
0x140002a3f  mov     ecx, ebp; dwErrCode
0x140002a41  call    cs:__imp_SetLastError
0x140002a47  mov     [rdi+8], rsi
0x140002a4b  xor     eax, eax
0x140002a4d  mov     rcx, [rsp+278h+var_38]
0x140002a55  xor     rcx, rsp; StackCookie
0x140002a58  call    __security_check_cookie
0x140002a5d  lea     r11, [rsp+278h+var_28]
0x140002a65  mov     rbx, [r11+38h]
0x140002a69  mov     rbp, [r11+40h]
0x140002a6d  mov     rsp, r11
0x140002a70  pop     r15
0x140002a72  pop     r14
0x140002a74  pop     r12
0x140002a76  pop     rdi
0x140002a77  pop     rsi
0x140002a78  retn
0x140002a79  mov     rcx, [rsp+278h]; this
0x140002a81  mov     edx, 0A0Bh; void *
0x140002a86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a8c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002a92  mov     rcx, [rsp+278h]; this
0x140002a9a  mov     edx, 0A0Bh; void *
0x140002a9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
