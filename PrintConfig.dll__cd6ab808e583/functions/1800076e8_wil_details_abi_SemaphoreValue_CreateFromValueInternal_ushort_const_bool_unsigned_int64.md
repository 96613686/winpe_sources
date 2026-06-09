# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800076e8`
- end: `0x180007919`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006e28`
- `0x1800071fc`

## callees

- `0x1800032e0`
- `0x1800076e8`
- `0x1800088b0`
- `0x18000b29c`
- `0x18000be0c`
- `0x18000cce0`
- `0x18000ccf0`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800077b1`
- `KERNEL32!CreateSemaphoreExW` at `0x180007857`
- `KERNEL32!CreateSemaphoreExW` at `0x1800077b1`
- `KERNEL32!CreateSemaphoreExW` at `0x180007857`
- `KERNEL32!CloseHandle` at `0x180007807`
- `KERNEL32!CloseHandle` at `0x1800078aa`
- `KERNEL32!CloseHandle` at `0x180007807`
- `KERNEL32!CloseHandle` at `0x1800078aa`
- `KERNEL32!SetLastError` at `0x180007818`
- `KERNEL32!SetLastError` at `0x1800078b6`
- `KERNEL32!SetLastError` at `0x180007818`
- `KERNEL32!SetLastError` at `0x1800078b6`
- `KERNEL32!GetLastError` at `0x1800077ed`
- `KERNEL32!GetLastError` at `0x1800077fb`
- `KERNEL32!GetLastError` at `0x180007890`
- `KERNEL32!GetLastError` at `0x18000789f`
- `KERNEL32!GetLastError` at `0x1800077ed`
- `KERNEL32!GetLastError` at `0x1800077fb`
- `KERNEL32!GetLastError` at `0x180007890`
- `KERNEL32!GetLastError` at `0x18000789f`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
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
0x1800076e8  mov     [rsp+arg_8], rbx
0x1800076ed  push    rbp
0x1800076ee  push    rsi
0x1800076ef  push    rdi
0x1800076f0  push    r12
0x1800076f2  push    r13
0x1800076f4  push    r14
0x1800076f6  push    r15
0x1800076f8  sub     rsp, 250h
0x1800076ff  mov     rax, cs:__security_cookie
0x180007706  xor     rax, rsp
0x180007709  mov     [rsp+288h+var_48], rax
0x180007711  mov     rax, 0C000000000000000h
0x18000771b  mov     rsi, r9
0x18000771e  mov     r8, rdx
0x180007721  mov     rbx, rcx
0x180007724  test    rax, r9
0x180007727  jnz     loc_180007900
0x18000772d  xor     r12d, r12d
0x180007730  lea     rax, [rsp+288h+Name]
0x180007735  mov     r13d, 104h
0x18000773b  mov     ecx, 7FFFFFFEh
0x180007740  mov     edx, r13d
0x180007743  lea     ebp, [r12+1]
0x180007748  test    rcx, rcx
0x18000774b  jz      short loc_18000776B
0x18000774d  movzx   r9d, word ptr [r8]
0x180007751  test    r9w, r9w
0x180007755  jz      short loc_18000776B
0x180007757  mov     [rax], r9w
0x18000775b  add     r8, 2
0x18000775f  add     rax, 2
0x180007763  sub     rcx, rbp
0x180007766  sub     rdx, rbp
0x180007769  jnz     short loc_180007748
0x18000776b  test    rdx, rdx
0x18000776e  lea     rcx, [rax-2]
0x180007772  lea     r8, aP0; "_p0"
0x180007779  mov     rdx, r13; unsigned __int64
0x18000777c  cmovnz  rcx, rax
0x180007780  mov     [rcx], r12w
0x180007784  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007789  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000778e  mov     edx, esi
0x180007790  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007798  and     edx, 7FFFFFFFh; lInitialCount
0x18000779e  mov     [rsp+288h+dwFlags], r12d; int
0x1800077a3  mov     r8d, ebp
0x1800077a6  lea     r9, [rsp+288h+Name]; lpName
0x1800077ab  cmova   r8d, edx; lMaximumCount
0x1800077af  xor     ecx, ecx; lpSemaphoreAttributes
0x1800077b1  call    cs:__imp_CreateSemaphoreExW
0x1800077b7  mov     r15, rax
0x1800077ba  test    rax, rax
0x1800077bd  jnz     short loc_1800077ED
0x1800077bf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800077c4  mov     edi, eax
0x1800077c6  test    eax, eax
0x1800077c8  jns     short loc_180007821
0x1800077ca  mov     rcx, [rsp+288h]; this
0x1800077d2  lea     r8, aWil; "wil"
0x1800077d9  mov     r9d, eax; char *
0x1800077dc  mov     edx, 8Bh; void *
0x1800077e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077e6  mov     eax, edi
0x1800077e8  jmp     loc_1800078C2
0x1800077ed  call    cs:__imp_GetLastError
0x1800077f3  mov     rdi, [rbx]
0x1800077f6  test    rdi, rdi
0x1800077f9  jz      short loc_18000781E
0x1800077fb  call    cs:__imp_GetLastError
0x180007801  mov     rcx, rdi; hObject
0x180007804  mov     r14d, eax
0x180007807  call    cs:__imp_CloseHandle
0x18000780d  test    eax, eax
0x18000780f  jz      loc_180007906
0x180007815  mov     ecx, r14d; dwErrCode
0x180007818  call    cs:__imp_SetLastError
0x18000781e  mov     [rbx], r15
0x180007821  lea     r8, asc_1801DCF50; "h"
0x180007828  shr     rsi, 1Fh
0x18000782c  mov     rdx, r13; unsigned __int64
0x18000782f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007834  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007839  test    esi, esi
0x18000783b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007843  lea     r9, [rsp+288h+Name]; lpName
0x180007848  mov     [rsp+288h+dwFlags], r12d; int
0x18000784d  cmovnz  ebp, esi
0x180007850  mov     edx, esi; lInitialCount
0x180007852  mov     r8d, ebp; lMaximumCount
0x180007855  xor     ecx, ecx; lpSemaphoreAttributes
0x180007857  call    cs:__imp_CreateSemaphoreExW
0x18000785d  mov     rbp, rax
0x180007860  test    rax, rax
0x180007863  jnz     short loc_180007890
0x180007865  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000786a  mov     ebx, eax
0x18000786c  test    eax, eax
0x18000786e  jns     short loc_1800078C0
0x180007870  mov     rcx, [rsp+288h]; this
0x180007878  lea     r8, aWil; "wil"
0x18000787f  mov     r9d, eax; char *
0x180007882  mov     edx, 90h; void *
0x180007887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000788c  mov     eax, ebx
0x18000788e  jmp     short loc_1800078C2
0x180007890  call    cs:__imp_GetLastError
0x180007896  mov     rdi, [rbx+8]
0x18000789a  test    rdi, rdi
0x18000789d  jz      short loc_1800078BC
0x18000789f  call    cs:__imp_GetLastError
0x1800078a5  mov     rcx, rdi; hObject
0x1800078a8  mov     esi, eax
0x1800078aa  call    cs:__imp_CloseHandle
0x1800078b0  test    eax, eax
0x1800078b2  jz      short loc_1800078ED
0x1800078b4  mov     ecx, esi; dwErrCode
0x1800078b6  call    cs:__imp_SetLastError
0x1800078bc  mov     [rbx+8], rbp
0x1800078c0  xor     eax, eax
0x1800078c2  mov     rcx, [rsp+288h+var_48]
0x1800078ca  xor     rcx, rsp; StackCookie
0x1800078cd  call    __security_check_cookie
0x1800078d2  mov     rbx, [rsp+288h+arg_8]
0x1800078da  add     rsp, 250h
0x1800078e1  pop     r15
0x1800078e3  pop     r14
0x1800078e5  pop     r13
0x1800078e7  pop     r12
0x1800078e9  pop     rdi
0x1800078ea  pop     rsi
0x1800078eb  pop     rbp
0x1800078ec  retn
0x1800078ed  mov     rcx, [rsp+288h]; this
0x1800078f5  mov     edx, 0A0Bh; void *
0x1800078fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007900  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007906  mov     rcx, [rsp+288h]; this
0x18000790e  mov     edx, 0A0Bh; void *
0x180007913  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
