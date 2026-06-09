# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400030f8`
- end: `0x140003329`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d28`

## callees

- `0x140001480`
- `0x1400030f8`
- `0x140003998`
- `0x1400048e4`
- `0x1400051c0`
- `0x14000572c`
- `0x14000573c`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1400031c1`
- `KERNEL32!CreateSemaphoreExW` at `0x140003267`
- `KERNEL32!CreateSemaphoreExW` at `0x1400031c1`
- `KERNEL32!CreateSemaphoreExW` at `0x140003267`
- `KERNEL32!SetLastError` at `0x140003228`
- `KERNEL32!SetLastError` at `0x1400032c6`
- `KERNEL32!SetLastError` at `0x140003228`
- `KERNEL32!SetLastError` at `0x1400032c6`
- `KERNEL32!GetLastError` at `0x1400031fd`
- `KERNEL32!GetLastError` at `0x14000320b`
- `KERNEL32!GetLastError` at `0x1400032a0`
- `KERNEL32!GetLastError` at `0x1400032af`
- `KERNEL32!GetLastError` at `0x1400031fd`
- `KERNEL32!GetLastError` at `0x14000320b`
- `KERNEL32!GetLastError` at `0x1400032a0`
- `KERNEL32!GetLastError` at `0x1400032af`
- `KERNEL32!CloseHandle` at `0x140003217`
- `KERNEL32!CloseHandle` at `0x1400032ba`
- `KERNEL32!CloseHandle` at `0x140003217`
- `KERNEL32!CloseHandle` at `0x1400032ba`

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
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
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
0x1400030f8  mov     [rsp+arg_8], rbx
0x1400030fd  push    rbp
0x1400030fe  push    rsi
0x1400030ff  push    rdi
0x140003100  push    r12
0x140003102  push    r13
0x140003104  push    r14
0x140003106  push    r15
0x140003108  sub     rsp, 250h
0x14000310f  mov     rax, cs:__security_cookie
0x140003116  xor     rax, rsp
0x140003119  mov     [rsp+288h+var_48], rax
0x140003121  mov     rax, 0C000000000000000h
0x14000312b  mov     rsi, r9
0x14000312e  mov     r8, rdx
0x140003131  mov     rbx, rcx
0x140003134  test    rax, r9
0x140003137  jnz     loc_140003310
0x14000313d  xor     r12d, r12d
0x140003140  lea     rax, [rsp+288h+Name]
0x140003145  mov     r13d, 104h
0x14000314b  mov     ecx, 7FFFFFFEh
0x140003150  mov     edx, r13d
0x140003153  lea     ebp, [r12+1]
0x140003158  test    rcx, rcx
0x14000315b  jz      short loc_14000317B
0x14000315d  movzx   r9d, word ptr [r8]
0x140003161  test    r9w, r9w
0x140003165  jz      short loc_14000317B
0x140003167  mov     [rax], r9w
0x14000316b  add     r8, 2
0x14000316f  add     rax, 2
0x140003173  sub     rcx, rbp
0x140003176  sub     rdx, rbp
0x140003179  jnz     short loc_140003158
0x14000317b  test    rdx, rdx
0x14000317e  lea     rcx, [rax-2]
0x140003182  lea     r8, aP0; "_p0"
0x140003189  mov     rdx, r13; unsigned __int64
0x14000318c  cmovnz  rcx, rax
0x140003190  mov     [rcx], r12w
0x140003194  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140003199  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000319e  mov     edx, esi
0x1400031a0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400031a8  and     edx, 7FFFFFFFh; lInitialCount
0x1400031ae  mov     [rsp+288h+dwFlags], r12d; int
0x1400031b3  mov     r8d, ebp
0x1400031b6  lea     r9, [rsp+288h+Name]; lpName
0x1400031bb  cmova   r8d, edx; lMaximumCount
0x1400031bf  xor     ecx, ecx; lpSemaphoreAttributes
0x1400031c1  call    cs:__imp_CreateSemaphoreExW
0x1400031c7  mov     r15, rax
0x1400031ca  test    rax, rax
0x1400031cd  jnz     short loc_1400031FD
0x1400031cf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400031d4  mov     edi, eax
0x1400031d6  test    eax, eax
0x1400031d8  jns     short loc_140003231
0x1400031da  mov     rcx, [rsp+288h]; this
0x1400031e2  lea     r8, aWil; "wil"
0x1400031e9  mov     r9d, eax; char *
0x1400031ec  mov     edx, 8Bh; void *
0x1400031f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031f6  mov     eax, edi
0x1400031f8  jmp     loc_1400032D2
0x1400031fd  call    cs:__imp_GetLastError
0x140003203  mov     rdi, [rbx]
0x140003206  test    rdi, rdi
0x140003209  jz      short loc_14000322E
0x14000320b  call    cs:__imp_GetLastError
0x140003211  mov     rcx, rdi; hObject
0x140003214  mov     r14d, eax
0x140003217  call    cs:__imp_CloseHandle
0x14000321d  test    eax, eax
0x14000321f  jz      loc_140003316
0x140003225  mov     ecx, r14d; dwErrCode
0x140003228  call    cs:__imp_SetLastError
0x14000322e  mov     [rbx], r15
0x140003231  lea     r8, asc_140009880; "h"
0x140003238  shr     rsi, 1Fh
0x14000323c  mov     rdx, r13; unsigned __int64
0x14000323f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140003244  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003249  test    esi, esi
0x14000324b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003253  lea     r9, [rsp+288h+Name]; lpName
0x140003258  mov     [rsp+288h+dwFlags], r12d; int
0x14000325d  cmovnz  ebp, esi
0x140003260  mov     edx, esi; lInitialCount
0x140003262  mov     r8d, ebp; lMaximumCount
0x140003265  xor     ecx, ecx; lpSemaphoreAttributes
0x140003267  call    cs:__imp_CreateSemaphoreExW
0x14000326d  mov     rbp, rax
0x140003270  test    rax, rax
0x140003273  jnz     short loc_1400032A0
0x140003275  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000327a  mov     ebx, eax
0x14000327c  test    eax, eax
0x14000327e  jns     short loc_1400032D0
0x140003280  mov     rcx, [rsp+288h]; this
0x140003288  lea     r8, aWil; "wil"
0x14000328f  mov     r9d, eax; char *
0x140003292  mov     edx, 90h; void *
0x140003297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000329c  mov     eax, ebx
0x14000329e  jmp     short loc_1400032D2
0x1400032a0  call    cs:__imp_GetLastError
0x1400032a6  mov     rdi, [rbx+8]
0x1400032aa  test    rdi, rdi
0x1400032ad  jz      short loc_1400032CC
0x1400032af  call    cs:__imp_GetLastError
0x1400032b5  mov     rcx, rdi; hObject
0x1400032b8  mov     esi, eax
0x1400032ba  call    cs:__imp_CloseHandle
0x1400032c0  test    eax, eax
0x1400032c2  jz      short loc_1400032FD
0x1400032c4  mov     ecx, esi; dwErrCode
0x1400032c6  call    cs:__imp_SetLastError
0x1400032cc  mov     [rbx+8], rbp
0x1400032d0  xor     eax, eax
0x1400032d2  mov     rcx, [rsp+288h+var_48]
0x1400032da  xor     rcx, rsp; StackCookie
0x1400032dd  call    __security_check_cookie
0x1400032e2  mov     rbx, [rsp+288h+arg_8]
0x1400032ea  add     rsp, 250h
0x1400032f1  pop     r15
0x1400032f3  pop     r14
0x1400032f5  pop     r13
0x1400032f7  pop     r12
0x1400032f9  pop     rdi
0x1400032fa  pop     rsi
0x1400032fb  pop     rbp
0x1400032fc  retn
0x1400032fd  mov     rcx, [rsp+288h]; this
0x140003305  mov     edx, 0A0Bh; void *
0x14000330a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003310  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003316  mov     rcx, [rsp+288h]; this
0x14000331e  mov     edx, 0A0Bh; void *
0x140003323  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
