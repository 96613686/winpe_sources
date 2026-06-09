# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004fa0`
- end: `0x1800051ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004038`

## callees

- `0x180002470`
- `0x180004fa0`
- `0x180005c78`
- `0x180007e24`
- `0x1800087b4`
- `0x180009004`
- `0x180009014`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005064`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005107`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005064`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000514f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000514f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000515a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000515a`

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
0x180004fa0  mov     [rsp+arg_8], rbx
0x180004fa5  mov     [rsp+arg_10], rbp
0x180004faa  push    rsi
0x180004fab  push    rdi
0x180004fac  push    r12
0x180004fae  push    r14
0x180004fb0  push    r15
0x180004fb2  sub     rsp, 250h
0x180004fb9  mov     rax, cs:__security_cookie
0x180004fc0  xor     rax, rsp
0x180004fc3  mov     [rsp+278h+var_38], rax
0x180004fcb  mov     rax, 0C000000000000000h
0x180004fd5  mov     rbp, r9
0x180004fd8  mov     r8, rdx
0x180004fdb  mov     rbx, rcx
0x180004fde  test    rax, r9
0x180004fe1  jnz     loc_1800051B1
0x180004fe7  xor     r12d, r12d
0x180004fea  lea     rax, [rsp+278h+Name]
0x180004fef  mov     ecx, 7FFFFFFEh
0x180004ff4  mov     edx, 104h
0x180004ff9  lea     esi, [r12+1]
0x180004ffe  test    rcx, rcx
0x180005001  jz      short loc_180005021
0x180005003  movzx   r9d, word ptr [r8]
0x180005007  test    r9w, r9w
0x18000500b  jz      short loc_180005021
0x18000500d  mov     [rax], r9w
0x180005011  add     r8, 2
0x180005015  add     rax, 2
0x180005019  sub     rcx, rsi
0x18000501c  sub     rdx, rsi; unsigned __int64
0x18000501f  jnz     short loc_180004FFE
0x180005021  test    rdx, rdx
0x180005024  lea     rcx, [rax-2]
0x180005028  lea     r8, aP0; "_p0"
0x18000502f  cmovnz  rcx, rax
0x180005033  mov     [rcx], r12w
0x180005037  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000503c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005041  mov     edx, ebp
0x180005043  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000504b  and     edx, 7FFFFFFFh; lInitialCount
0x180005051  mov     [rsp+278h+dwFlags], r12d; int
0x180005056  mov     r8d, esi
0x180005059  lea     r9, [rsp+278h+Name]; lpName
0x18000505e  cmova   r8d, edx; lMaximumCount
0x180005062  xor     ecx, ecx; lpSemaphoreAttributes
0x180005064  call    cs:__imp_CreateSemaphoreExW
0x18000506a  mov     r15, rax
0x18000506d  test    rax, rax
0x180005070  jnz     short loc_1800050A0
0x180005072  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005077  mov     edi, eax
0x180005079  test    eax, eax
0x18000507b  jns     short loc_1800050D4
0x18000507d  mov     rcx, [rsp+278h]; this
0x180005085  lea     r8, aWil; "wil"
0x18000508c  mov     r9d, eax; char *
0x18000508f  mov     edx, 8Bh; void *
0x180005094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005099  mov     eax, edi
0x18000509b  jmp     loc_180005172
0x1800050a0  call    cs:__imp_GetLastError
0x1800050a6  mov     rdi, [rbx]
0x1800050a9  test    rdi, rdi
0x1800050ac  jz      short loc_1800050D1
0x1800050ae  call    cs:__imp_GetLastError
0x1800050b4  mov     rcx, rdi; hObject
0x1800050b7  mov     r14d, eax
0x1800050ba  call    cs:__imp_CloseHandle
0x1800050c0  test    eax, eax
0x1800050c2  jz      loc_1800051B7
0x1800050c8  mov     ecx, r14d; dwErrCode
0x1800050cb  call    cs:__imp_SetLastError
0x1800050d1  mov     [rbx], r15
0x1800050d4  lea     r8, asc_180017A90; "h"
0x1800050db  shr     rbp, 1Fh
0x1800050df  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800050e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800050e9  test    ebp, ebp
0x1800050eb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800050f3  lea     r9, [rsp+278h+Name]; lpName
0x1800050f8  mov     [rsp+278h+dwFlags], r12d; int
0x1800050fd  cmovnz  esi, ebp
0x180005100  mov     edx, ebp; lInitialCount
0x180005102  mov     r8d, esi; lMaximumCount
0x180005105  xor     ecx, ecx; lpSemaphoreAttributes
0x180005107  call    cs:__imp_CreateSemaphoreExW
0x18000510d  mov     rsi, rax
0x180005110  test    rax, rax
0x180005113  jnz     short loc_180005140
0x180005115  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000511a  mov     ebx, eax
0x18000511c  test    eax, eax
0x18000511e  jns     short loc_180005170
0x180005120  mov     rcx, [rsp+278h]; this
0x180005128  lea     r8, aWil; "wil"
0x18000512f  mov     r9d, eax; char *
0x180005132  mov     edx, 90h; void *
0x180005137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000513c  mov     eax, ebx
0x18000513e  jmp     short loc_180005172
0x180005140  call    cs:__imp_GetLastError
0x180005146  mov     rdi, [rbx+8]
0x18000514a  test    rdi, rdi
0x18000514d  jz      short loc_18000516C
0x18000514f  call    cs:__imp_GetLastError
0x180005155  mov     rcx, rdi; hObject
0x180005158  mov     ebp, eax
0x18000515a  call    cs:__imp_CloseHandle
0x180005160  test    eax, eax
0x180005162  jz      short loc_18000519E
0x180005164  mov     ecx, ebp; dwErrCode
0x180005166  call    cs:__imp_SetLastError
0x18000516c  mov     [rbx+8], rsi
0x180005170  xor     eax, eax
0x180005172  mov     rcx, [rsp+278h+var_38]
0x18000517a  xor     rcx, rsp; StackCookie
0x18000517d  call    __security_check_cookie
0x180005182  lea     r11, [rsp+278h+var_28]
0x18000518a  mov     rbx, [r11+38h]
0x18000518e  mov     rbp, [r11+40h]
0x180005192  mov     rsp, r11
0x180005195  pop     r15
0x180005197  pop     r14
0x180005199  pop     r12
0x18000519b  pop     rdi
0x18000519c  pop     rsi
0x18000519d  retn
0x18000519e  mov     rcx, [rsp+278h]; this
0x1800051a6  mov     edx, 0A0Bh; void *
0x1800051ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800051b7  mov     rcx, [rsp+278h]; this
0x1800051bf  mov     edx, 0A0Bh; void *
0x1800051c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
