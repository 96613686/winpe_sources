# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004e7c`
- end: `0x1800050a6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800048d8`
- `0x180009dec`

## callees

- `0x180002240`
- `0x180004e7c`
- `0x1800058a4`
- `0x180006a14`
- `0x180007354`
- `0x180007a48`
- `0x180007a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004f40`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004fe3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004f40`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000501c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000501c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005036`

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
0x180004e7c  mov     [rsp+arg_8], rbx
0x180004e81  mov     [rsp+arg_10], rbp
0x180004e86  push    rsi
0x180004e87  push    rdi
0x180004e88  push    r12
0x180004e8a  push    r14
0x180004e8c  push    r15
0x180004e8e  sub     rsp, 250h
0x180004e95  mov     rax, cs:__security_cookie
0x180004e9c  xor     rax, rsp
0x180004e9f  mov     [rsp+278h+var_38], rax
0x180004ea7  mov     rax, 0C000000000000000h
0x180004eb1  mov     rbp, r9
0x180004eb4  mov     r8, rdx
0x180004eb7  mov     rbx, rcx
0x180004eba  test    rax, r9
0x180004ebd  jnz     loc_18000508D
0x180004ec3  xor     r12d, r12d
0x180004ec6  lea     rax, [rsp+278h+Name]
0x180004ecb  mov     ecx, 7FFFFFFEh
0x180004ed0  mov     edx, 104h
0x180004ed5  lea     esi, [r12+1]
0x180004eda  test    rcx, rcx
0x180004edd  jz      short loc_180004EFD
0x180004edf  movzx   r9d, word ptr [r8]
0x180004ee3  test    r9w, r9w
0x180004ee7  jz      short loc_180004EFD
0x180004ee9  mov     [rax], r9w
0x180004eed  add     r8, 2
0x180004ef1  add     rax, 2
0x180004ef5  sub     rcx, rsi
0x180004ef8  sub     rdx, rsi; unsigned __int64
0x180004efb  jnz     short loc_180004EDA
0x180004efd  test    rdx, rdx
0x180004f00  lea     rcx, [rax-2]
0x180004f04  lea     r8, aP0; "_p0"
0x180004f0b  cmovnz  rcx, rax
0x180004f0f  mov     [rcx], r12w
0x180004f13  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004f18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004f1d  mov     edx, ebp
0x180004f1f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004f27  and     edx, 7FFFFFFFh; lInitialCount
0x180004f2d  mov     [rsp+278h+dwFlags], r12d; int
0x180004f32  mov     r8d, esi
0x180004f35  lea     r9, [rsp+278h+Name]; lpName
0x180004f3a  cmova   r8d, edx; lMaximumCount
0x180004f3e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004f40  call    cs:__imp_CreateSemaphoreExW
0x180004f46  mov     r15, rax
0x180004f49  test    rax, rax
0x180004f4c  jnz     short loc_180004F7C
0x180004f4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004f53  mov     edi, eax
0x180004f55  test    eax, eax
0x180004f57  jns     short loc_180004FB0
0x180004f59  mov     rcx, [rsp+278h]; this
0x180004f61  lea     r8, aWil; "wil"
0x180004f68  mov     r9d, eax; char *
0x180004f6b  mov     edx, 8Bh; void *
0x180004f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f75  mov     eax, edi
0x180004f77  jmp     loc_18000504E
0x180004f7c  call    cs:__imp_GetLastError
0x180004f82  mov     rdi, [rbx]
0x180004f85  test    rdi, rdi
0x180004f88  jz      short loc_180004FAD
0x180004f8a  call    cs:__imp_GetLastError
0x180004f90  mov     rcx, rdi; hObject
0x180004f93  mov     r14d, eax
0x180004f96  call    cs:__imp_CloseHandle
0x180004f9c  test    eax, eax
0x180004f9e  jz      loc_180005093
0x180004fa4  mov     ecx, r14d; dwErrCode
0x180004fa7  call    cs:__imp_SetLastError
0x180004fad  mov     [rbx], r15
0x180004fb0  lea     r8, asc_18006CEF8; "h"
0x180004fb7  shr     rbp, 1Fh
0x180004fbb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004fc0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004fc5  test    ebp, ebp
0x180004fc7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004fcf  lea     r9, [rsp+278h+Name]; lpName
0x180004fd4  mov     [rsp+278h+dwFlags], r12d; int
0x180004fd9  cmovnz  esi, ebp
0x180004fdc  mov     edx, ebp; lInitialCount
0x180004fde  mov     r8d, esi; lMaximumCount
0x180004fe1  xor     ecx, ecx; lpSemaphoreAttributes
0x180004fe3  call    cs:__imp_CreateSemaphoreExW
0x180004fe9  mov     rsi, rax
0x180004fec  test    rax, rax
0x180004fef  jnz     short loc_18000501C
0x180004ff1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ff6  mov     ebx, eax
0x180004ff8  test    eax, eax
0x180004ffa  jns     short loc_18000504C
0x180004ffc  mov     rcx, [rsp+278h]; this
0x180005004  lea     r8, aWil; "wil"
0x18000500b  mov     r9d, eax; char *
0x18000500e  mov     edx, 90h; void *
0x180005013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005018  mov     eax, ebx
0x18000501a  jmp     short loc_18000504E
0x18000501c  call    cs:__imp_GetLastError
0x180005022  mov     rdi, [rbx+8]
0x180005026  test    rdi, rdi
0x180005029  jz      short loc_180005048
0x18000502b  call    cs:__imp_GetLastError
0x180005031  mov     rcx, rdi; hObject
0x180005034  mov     ebp, eax
0x180005036  call    cs:__imp_CloseHandle
0x18000503c  test    eax, eax
0x18000503e  jz      short loc_18000507A
0x180005040  mov     ecx, ebp; dwErrCode
0x180005042  call    cs:__imp_SetLastError
0x180005048  mov     [rbx+8], rsi
0x18000504c  xor     eax, eax
0x18000504e  mov     rcx, [rsp+278h+var_38]
0x180005056  xor     rcx, rsp; StackCookie
0x180005059  call    __security_check_cookie
0x18000505e  lea     r11, [rsp+278h+var_28]
0x180005066  mov     rbx, [r11+38h]
0x18000506a  mov     rbp, [r11+40h]
0x18000506e  mov     rsp, r11
0x180005071  pop     r15
0x180005073  pop     r14
0x180005075  pop     r12
0x180005077  pop     rdi
0x180005078  pop     rsi
0x180005079  retn
0x18000507a  mov     rcx, [rsp+278h]; this
0x180005082  mov     edx, 0A0Bh; void *
0x180005087  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000508d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005093  mov     rcx, [rsp+278h]; this
0x18000509b  mov     edx, 0A0Bh; void *
0x1800050a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
