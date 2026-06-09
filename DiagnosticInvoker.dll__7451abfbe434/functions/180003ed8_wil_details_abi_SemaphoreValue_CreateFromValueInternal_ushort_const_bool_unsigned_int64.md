# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003ed8`
- end: `0x180004102`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b08`

## callees

- `0x180001e20`
- `0x180003ed8`
- `0x180004768`
- `0x180005524`
- `0x180005e64`
- `0x18000638c`
- `0x18000639c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f9c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000403f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f9c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000403f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004003`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004003`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004092`

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
0x180003ed8  mov     [rsp+arg_8], rbx
0x180003edd  mov     [rsp+arg_10], rbp
0x180003ee2  push    rsi
0x180003ee3  push    rdi
0x180003ee4  push    r12
0x180003ee6  push    r14
0x180003ee8  push    r15
0x180003eea  sub     rsp, 250h
0x180003ef1  mov     rax, cs:__security_cookie
0x180003ef8  xor     rax, rsp
0x180003efb  mov     [rsp+278h+var_38], rax
0x180003f03  mov     rax, 0C000000000000000h
0x180003f0d  mov     rbp, r9
0x180003f10  mov     r8, rdx
0x180003f13  mov     rbx, rcx
0x180003f16  test    rax, r9
0x180003f19  jnz     loc_1800040E9
0x180003f1f  xor     r12d, r12d
0x180003f22  lea     rax, [rsp+278h+Name]
0x180003f27  mov     ecx, 7FFFFFFEh
0x180003f2c  mov     edx, 104h
0x180003f31  lea     esi, [r12+1]
0x180003f36  test    rcx, rcx
0x180003f39  jz      short loc_180003F59
0x180003f3b  movzx   r9d, word ptr [r8]
0x180003f3f  test    r9w, r9w
0x180003f43  jz      short loc_180003F59
0x180003f45  mov     [rax], r9w
0x180003f49  add     r8, 2
0x180003f4d  add     rax, 2
0x180003f51  sub     rcx, rsi
0x180003f54  sub     rdx, rsi; unsigned __int64
0x180003f57  jnz     short loc_180003F36
0x180003f59  test    rdx, rdx
0x180003f5c  lea     rcx, [rax-2]
0x180003f60  lea     r8, aP0; "_p0"
0x180003f67  cmovnz  rcx, rax
0x180003f6b  mov     [rcx], r12w
0x180003f6f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003f74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003f79  mov     edx, ebp
0x180003f7b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003f83  and     edx, 7FFFFFFFh; lInitialCount
0x180003f89  mov     [rsp+278h+dwFlags], r12d; int
0x180003f8e  mov     r8d, esi
0x180003f91  lea     r9, [rsp+278h+Name]; lpName
0x180003f96  cmova   r8d, edx; lMaximumCount
0x180003f9a  xor     ecx, ecx; lpSemaphoreAttributes
0x180003f9c  call    cs:__imp_CreateSemaphoreExW
0x180003fa2  mov     r15, rax
0x180003fa5  test    rax, rax
0x180003fa8  jnz     short loc_180003FD8
0x180003faa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003faf  mov     edi, eax
0x180003fb1  test    eax, eax
0x180003fb3  jns     short loc_18000400C
0x180003fb5  mov     rcx, [rsp+278h]; this
0x180003fbd  lea     r8, aWil; "wil"
0x180003fc4  mov     r9d, eax; char *
0x180003fc7  mov     edx, 8Bh; void *
0x180003fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fd1  mov     eax, edi
0x180003fd3  jmp     loc_1800040AA
0x180003fd8  call    cs:__imp_GetLastError
0x180003fde  mov     rdi, [rbx]
0x180003fe1  test    rdi, rdi
0x180003fe4  jz      short loc_180004009
0x180003fe6  call    cs:__imp_GetLastError
0x180003fec  mov     rcx, rdi; hObject
0x180003fef  mov     r14d, eax
0x180003ff2  call    cs:__imp_CloseHandle
0x180003ff8  test    eax, eax
0x180003ffa  jz      loc_1800040EF
0x180004000  mov     ecx, r14d; dwErrCode
0x180004003  call    cs:__imp_SetLastError
0x180004009  mov     [rbx], r15
0x18000400c  lea     r8, asc_180015348; "h"
0x180004013  shr     rbp, 1Fh
0x180004017  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000401c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004021  test    ebp, ebp
0x180004023  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000402b  lea     r9, [rsp+278h+Name]; lpName
0x180004030  mov     [rsp+278h+dwFlags], r12d; int
0x180004035  cmovnz  esi, ebp
0x180004038  mov     edx, ebp; lInitialCount
0x18000403a  mov     r8d, esi; lMaximumCount
0x18000403d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000403f  call    cs:__imp_CreateSemaphoreExW
0x180004045  mov     rsi, rax
0x180004048  test    rax, rax
0x18000404b  jnz     short loc_180004078
0x18000404d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004052  mov     ebx, eax
0x180004054  test    eax, eax
0x180004056  jns     short loc_1800040A8
0x180004058  mov     rcx, [rsp+278h]; this
0x180004060  lea     r8, aWil; "wil"
0x180004067  mov     r9d, eax; char *
0x18000406a  mov     edx, 90h; void *
0x18000406f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004074  mov     eax, ebx
0x180004076  jmp     short loc_1800040AA
0x180004078  call    cs:__imp_GetLastError
0x18000407e  mov     rdi, [rbx+8]
0x180004082  test    rdi, rdi
0x180004085  jz      short loc_1800040A4
0x180004087  call    cs:__imp_GetLastError
0x18000408d  mov     rcx, rdi; hObject
0x180004090  mov     ebp, eax
0x180004092  call    cs:__imp_CloseHandle
0x180004098  test    eax, eax
0x18000409a  jz      short loc_1800040D6
0x18000409c  mov     ecx, ebp; dwErrCode
0x18000409e  call    cs:__imp_SetLastError
0x1800040a4  mov     [rbx+8], rsi
0x1800040a8  xor     eax, eax
0x1800040aa  mov     rcx, [rsp+278h+var_38]
0x1800040b2  xor     rcx, rsp; StackCookie
0x1800040b5  call    __security_check_cookie
0x1800040ba  lea     r11, [rsp+278h+var_28]
0x1800040c2  mov     rbx, [r11+38h]
0x1800040c6  mov     rbp, [r11+40h]
0x1800040ca  mov     rsp, r11
0x1800040cd  pop     r15
0x1800040cf  pop     r14
0x1800040d1  pop     r12
0x1800040d3  pop     rdi
0x1800040d4  pop     rsi
0x1800040d5  retn
0x1800040d6  mov     rcx, [rsp+278h]; this
0x1800040de  mov     edx, 0A0Bh; void *
0x1800040e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040e9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800040ef  mov     rcx, [rsp+278h]; this
0x1800040f7  mov     edx, 0A0Bh; void *
0x1800040fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
