# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003e08`
- end: `0x140004032`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a38`

## callees

- `0x140002120`
- `0x140003e08`
- `0x140004698`
- `0x140005454`
- `0x140005d30`
- `0x14000629c`
- `0x1400062ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003ecc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f6f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003ecc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003fce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003fce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fc2`

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
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
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
0x140003e08  mov     [rsp+arg_8], rbx
0x140003e0d  mov     [rsp+arg_10], rbp
0x140003e12  push    rsi
0x140003e13  push    rdi
0x140003e14  push    r12
0x140003e16  push    r14
0x140003e18  push    r15
0x140003e1a  sub     rsp, 250h
0x140003e21  mov     rax, cs:__security_cookie
0x140003e28  xor     rax, rsp
0x140003e2b  mov     [rsp+278h+var_38], rax
0x140003e33  mov     rax, 0C000000000000000h
0x140003e3d  mov     rbp, r9
0x140003e40  mov     r8, rdx
0x140003e43  mov     rbx, rcx
0x140003e46  test    rax, r9
0x140003e49  jnz     loc_140004019
0x140003e4f  xor     r12d, r12d
0x140003e52  lea     rax, [rsp+278h+Name]
0x140003e57  mov     ecx, 7FFFFFFEh
0x140003e5c  mov     edx, 104h
0x140003e61  lea     esi, [r12+1]
0x140003e66  test    rcx, rcx
0x140003e69  jz      short loc_140003E89
0x140003e6b  movzx   r9d, word ptr [r8]
0x140003e6f  test    r9w, r9w
0x140003e73  jz      short loc_140003E89
0x140003e75  mov     [rax], r9w
0x140003e79  add     r8, 2
0x140003e7d  add     rax, 2
0x140003e81  sub     rcx, rsi
0x140003e84  sub     rdx, rsi; unsigned __int64
0x140003e87  jnz     short loc_140003E66
0x140003e89  test    rdx, rdx
0x140003e8c  lea     rcx, [rax-2]
0x140003e90  lea     r8, aP0; "_p0"
0x140003e97  cmovnz  rcx, rax
0x140003e9b  mov     [rcx], r12w
0x140003e9f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003ea4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003ea9  mov     edx, ebp
0x140003eab  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003eb3  and     edx, 7FFFFFFFh; lInitialCount
0x140003eb9  mov     [rsp+278h+dwFlags], r12d; int
0x140003ebe  mov     r8d, esi
0x140003ec1  lea     r9, [rsp+278h+Name]; lpName
0x140003ec6  cmova   r8d, edx; lMaximumCount
0x140003eca  xor     ecx, ecx; lpSemaphoreAttributes
0x140003ecc  call    cs:__imp_CreateSemaphoreExW
0x140003ed2  mov     r15, rax
0x140003ed5  test    rax, rax
0x140003ed8  jnz     short loc_140003F08
0x140003eda  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003edf  mov     edi, eax
0x140003ee1  test    eax, eax
0x140003ee3  jns     short loc_140003F3C
0x140003ee5  mov     rcx, [rsp+278h]; this
0x140003eed  lea     r8, aWil; "wil"
0x140003ef4  mov     r9d, eax; char *
0x140003ef7  mov     edx, 8Bh; void *
0x140003efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f01  mov     eax, edi
0x140003f03  jmp     loc_140003FDA
0x140003f08  call    cs:__imp_GetLastError
0x140003f0e  mov     rdi, [rbx]
0x140003f11  test    rdi, rdi
0x140003f14  jz      short loc_140003F39
0x140003f16  call    cs:__imp_GetLastError
0x140003f1c  mov     rcx, rdi; hObject
0x140003f1f  mov     r14d, eax
0x140003f22  call    cs:__imp_CloseHandle
0x140003f28  test    eax, eax
0x140003f2a  jz      loc_14000401F
0x140003f30  mov     ecx, r14d; dwErrCode
0x140003f33  call    cs:__imp_SetLastError
0x140003f39  mov     [rbx], r15
0x140003f3c  lea     r8, asc_14000DC48; "h"
0x140003f43  shr     rbp, 1Fh
0x140003f47  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003f4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003f51  test    ebp, ebp
0x140003f53  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003f5b  lea     r9, [rsp+278h+Name]; lpName
0x140003f60  mov     [rsp+278h+dwFlags], r12d; int
0x140003f65  cmovnz  esi, ebp
0x140003f68  mov     edx, ebp; lInitialCount
0x140003f6a  mov     r8d, esi; lMaximumCount
0x140003f6d  xor     ecx, ecx; lpSemaphoreAttributes
0x140003f6f  call    cs:__imp_CreateSemaphoreExW
0x140003f75  mov     rsi, rax
0x140003f78  test    rax, rax
0x140003f7b  jnz     short loc_140003FA8
0x140003f7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f82  mov     ebx, eax
0x140003f84  test    eax, eax
0x140003f86  jns     short loc_140003FD8
0x140003f88  mov     rcx, [rsp+278h]; this
0x140003f90  lea     r8, aWil; "wil"
0x140003f97  mov     r9d, eax; char *
0x140003f9a  mov     edx, 90h; void *
0x140003f9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fa4  mov     eax, ebx
0x140003fa6  jmp     short loc_140003FDA
0x140003fa8  call    cs:__imp_GetLastError
0x140003fae  mov     rdi, [rbx+8]
0x140003fb2  test    rdi, rdi
0x140003fb5  jz      short loc_140003FD4
0x140003fb7  call    cs:__imp_GetLastError
0x140003fbd  mov     rcx, rdi; hObject
0x140003fc0  mov     ebp, eax
0x140003fc2  call    cs:__imp_CloseHandle
0x140003fc8  test    eax, eax
0x140003fca  jz      short loc_140004006
0x140003fcc  mov     ecx, ebp; dwErrCode
0x140003fce  call    cs:__imp_SetLastError
0x140003fd4  mov     [rbx+8], rsi
0x140003fd8  xor     eax, eax
0x140003fda  mov     rcx, [rsp+278h+var_38]
0x140003fe2  xor     rcx, rsp; StackCookie
0x140003fe5  call    __security_check_cookie
0x140003fea  lea     r11, [rsp+278h+var_28]
0x140003ff2  mov     rbx, [r11+38h]
0x140003ff6  mov     rbp, [r11+40h]
0x140003ffa  mov     rsp, r11
0x140003ffd  pop     r15
0x140003fff  pop     r14
0x140004001  pop     r12
0x140004003  pop     rdi
0x140004004  pop     rsi
0x140004005  retn
0x140004006  mov     rcx, [rsp+278h]; this
0x14000400e  mov     edx, 0A0Bh; void *
0x140004013  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004019  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000401f  mov     rcx, [rsp+278h]; this
0x140004027  mov     edx, 0A0Bh; void *
0x14000402c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
