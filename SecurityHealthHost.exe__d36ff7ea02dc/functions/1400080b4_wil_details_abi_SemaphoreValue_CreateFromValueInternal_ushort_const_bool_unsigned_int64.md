# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400080b4`
- end: `0x1400082de`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400078ec`
- `0x140007cbc`

## callees

- `0x1400015f0`
- `0x14000674c`
- `0x1400068ec`
- `0x1400080b4`
- `0x140008b6c`
- `0x14000af18`
- `0x14000ba50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400081ce`
- `KERNEL32!CloseHandle` at `0x14000826e`
- `KERNEL32!CloseHandle` at `0x1400081ce`
- `KERNEL32!CloseHandle` at `0x14000826e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400081b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400081c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400081b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400081c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008263`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000827a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000827a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140008178`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000821b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140008178`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000821b`

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
0x1400080b4  mov     [rsp+arg_8], rbx
0x1400080b9  mov     [rsp+arg_10], rbp
0x1400080be  push    rsi
0x1400080bf  push    rdi
0x1400080c0  push    r12
0x1400080c2  push    r14
0x1400080c4  push    r15
0x1400080c6  sub     rsp, 250h
0x1400080cd  mov     rax, cs:__security_cookie
0x1400080d4  xor     rax, rsp
0x1400080d7  mov     [rsp+278h+var_38], rax
0x1400080df  mov     rax, 0C000000000000000h
0x1400080e9  mov     rbp, r9
0x1400080ec  mov     r8, rdx
0x1400080ef  mov     rbx, rcx
0x1400080f2  test    rax, r9
0x1400080f5  jnz     loc_1400082C5
0x1400080fb  xor     r12d, r12d
0x1400080fe  lea     rax, [rsp+278h+Name]
0x140008103  mov     ecx, 7FFFFFFEh
0x140008108  mov     edx, 104h
0x14000810d  lea     esi, [r12+1]
0x140008112  test    rcx, rcx
0x140008115  jz      short loc_140008135
0x140008117  movzx   r9d, word ptr [r8]
0x14000811b  test    r9w, r9w
0x14000811f  jz      short loc_140008135
0x140008121  mov     [rax], r9w
0x140008125  add     r8, 2
0x140008129  add     rax, 2
0x14000812d  sub     rcx, rsi
0x140008130  sub     rdx, rsi; unsigned __int64
0x140008133  jnz     short loc_140008112
0x140008135  test    rdx, rdx
0x140008138  lea     rcx, [rax-2]
0x14000813c  lea     r8, aP0; "_p0"
0x140008143  cmovnz  rcx, rax
0x140008147  mov     [rcx], r12w
0x14000814b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140008150  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008155  mov     edx, ebp
0x140008157  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000815f  and     edx, 7FFFFFFFh; lInitialCount
0x140008165  mov     [rsp+278h+dwFlags], r12d; int
0x14000816a  mov     r8d, esi
0x14000816d  lea     r9, [rsp+278h+Name]; lpName
0x140008172  cmova   r8d, edx; lMaximumCount
0x140008176  xor     ecx, ecx; lpSemaphoreAttributes
0x140008178  call    cs:__imp_CreateSemaphoreExW
0x14000817e  mov     r15, rax
0x140008181  test    rax, rax
0x140008184  jnz     short loc_1400081B4
0x140008186  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000818b  mov     edi, eax
0x14000818d  test    eax, eax
0x14000818f  jns     short loc_1400081E8
0x140008191  mov     rcx, [rsp+278h]; this
0x140008199  lea     r8, aWil; "wil"
0x1400081a0  mov     r9d, eax; char *
0x1400081a3  mov     edx, 8Bh; void *
0x1400081a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400081ad  mov     eax, edi
0x1400081af  jmp     loc_140008286
0x1400081b4  call    cs:__imp_GetLastError
0x1400081ba  mov     rdi, [rbx]
0x1400081bd  test    rdi, rdi
0x1400081c0  jz      short loc_1400081E5
0x1400081c2  call    cs:__imp_GetLastError
0x1400081c8  mov     rcx, rdi; hObject
0x1400081cb  mov     r14d, eax
0x1400081ce  call    cs:__imp_CloseHandle
0x1400081d4  test    eax, eax
0x1400081d6  jz      loc_1400082CB
0x1400081dc  mov     ecx, r14d; dwErrCode
0x1400081df  call    cs:__imp_SetLastError
0x1400081e5  mov     [rbx], r15
0x1400081e8  lea     r8, asc_140013580; "h"
0x1400081ef  shr     rbp, 1Fh
0x1400081f3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400081f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400081fd  test    ebp, ebp
0x1400081ff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140008207  lea     r9, [rsp+278h+Name]; lpName
0x14000820c  mov     [rsp+278h+dwFlags], r12d; int
0x140008211  cmovnz  esi, ebp
0x140008214  mov     edx, ebp; lInitialCount
0x140008216  mov     r8d, esi; lMaximumCount
0x140008219  xor     ecx, ecx; lpSemaphoreAttributes
0x14000821b  call    cs:__imp_CreateSemaphoreExW
0x140008221  mov     rsi, rax
0x140008224  test    rax, rax
0x140008227  jnz     short loc_140008254
0x140008229  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000822e  mov     ebx, eax
0x140008230  test    eax, eax
0x140008232  jns     short loc_140008284
0x140008234  mov     rcx, [rsp+278h]; this
0x14000823c  lea     r8, aWil; "wil"
0x140008243  mov     r9d, eax; char *
0x140008246  mov     edx, 90h; void *
0x14000824b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008250  mov     eax, ebx
0x140008252  jmp     short loc_140008286
0x140008254  call    cs:__imp_GetLastError
0x14000825a  mov     rdi, [rbx+8]
0x14000825e  test    rdi, rdi
0x140008261  jz      short loc_140008280
0x140008263  call    cs:__imp_GetLastError
0x140008269  mov     rcx, rdi; hObject
0x14000826c  mov     ebp, eax
0x14000826e  call    cs:__imp_CloseHandle
0x140008274  test    eax, eax
0x140008276  jz      short loc_1400082B2
0x140008278  mov     ecx, ebp; dwErrCode
0x14000827a  call    cs:__imp_SetLastError
0x140008280  mov     [rbx+8], rsi
0x140008284  xor     eax, eax
0x140008286  mov     rcx, [rsp+278h+var_38]
0x14000828e  xor     rcx, rsp; StackCookie
0x140008291  call    __security_check_cookie
0x140008296  lea     r11, [rsp+278h+var_28]
0x14000829e  mov     rbx, [r11+38h]
0x1400082a2  mov     rbp, [r11+40h]
0x1400082a6  mov     rsp, r11
0x1400082a9  pop     r15
0x1400082ab  pop     r14
0x1400082ad  pop     r12
0x1400082af  pop     rdi
0x1400082b0  pop     rsi
0x1400082b1  retn
0x1400082b2  mov     rcx, [rsp+278h]; this
0x1400082ba  mov     edx, 0A0Bh; void *
0x1400082bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400082c5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400082cb  mov     rcx, [rsp+278h]; this
0x1400082d3  mov     edx, 0A0Bh; void *
0x1400082d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
