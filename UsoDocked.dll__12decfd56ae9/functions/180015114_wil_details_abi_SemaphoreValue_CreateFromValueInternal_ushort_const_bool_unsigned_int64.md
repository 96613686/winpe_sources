# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180015114`
- end: `0x180015345`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014938`
- `0x180014d08`

## callees

- `0x180007660`
- `0x180015114`
- `0x180016128`
- `0x1800183f4`
- `0x180018e44`
- `0x180019e38`
- `0x180019e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800151dd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015283`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800151dd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015244`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015244`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800152d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800152d6`

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
0x180015114  mov     [rsp+arg_8], rbx
0x180015119  push    rbp
0x18001511a  push    rsi
0x18001511b  push    rdi
0x18001511c  push    r12
0x18001511e  push    r13
0x180015120  push    r14
0x180015122  push    r15
0x180015124  sub     rsp, 250h
0x18001512b  mov     rax, cs:__security_cookie
0x180015132  xor     rax, rsp
0x180015135  mov     [rsp+288h+var_48], rax
0x18001513d  mov     rax, 0C000000000000000h
0x180015147  mov     rsi, r9
0x18001514a  mov     r8, rdx
0x18001514d  mov     rbx, rcx
0x180015150  test    rax, r9
0x180015153  jnz     loc_18001532C
0x180015159  xor     r12d, r12d
0x18001515c  lea     rax, [rsp+288h+Name]
0x180015161  mov     r13d, 104h
0x180015167  mov     ecx, 7FFFFFFEh
0x18001516c  mov     edx, r13d
0x18001516f  lea     ebp, [r12+1]
0x180015174  test    rcx, rcx
0x180015177  jz      short loc_180015197
0x180015179  movzx   r9d, word ptr [r8]
0x18001517d  test    r9w, r9w
0x180015181  jz      short loc_180015197
0x180015183  mov     [rax], r9w
0x180015187  add     r8, 2
0x18001518b  add     rax, 2
0x18001518f  sub     rcx, rbp
0x180015192  sub     rdx, rbp
0x180015195  jnz     short loc_180015174
0x180015197  test    rdx, rdx
0x18001519a  lea     rcx, [rax-2]
0x18001519e  lea     r8, aP0; "_p0"
0x1800151a5  mov     rdx, r13; unsigned __int64
0x1800151a8  cmovnz  rcx, rax
0x1800151ac  mov     [rcx], r12w
0x1800151b0  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800151b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800151ba  mov     edx, esi
0x1800151bc  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800151c4  and     edx, 7FFFFFFFh; lInitialCount
0x1800151ca  mov     [rsp+288h+dwFlags], r12d; int
0x1800151cf  mov     r8d, ebp
0x1800151d2  lea     r9, [rsp+288h+Name]; lpName
0x1800151d7  cmova   r8d, edx; lMaximumCount
0x1800151db  xor     ecx, ecx; lpSemaphoreAttributes
0x1800151dd  call    cs:__imp_CreateSemaphoreExW
0x1800151e3  mov     r15, rax
0x1800151e6  test    rax, rax
0x1800151e9  jnz     short loc_180015219
0x1800151eb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800151f0  mov     edi, eax
0x1800151f2  test    eax, eax
0x1800151f4  jns     short loc_18001524D
0x1800151f6  mov     rcx, [rsp+288h]; this
0x1800151fe  lea     r8, aWil; "wil"
0x180015205  mov     r9d, eax; char *
0x180015208  mov     edx, 8Bh; void *
0x18001520d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015212  mov     eax, edi
0x180015214  jmp     loc_1800152EE
0x180015219  call    cs:__imp_GetLastError
0x18001521f  mov     rdi, [rbx]
0x180015222  test    rdi, rdi
0x180015225  jz      short loc_18001524A
0x180015227  call    cs:__imp_GetLastError
0x18001522d  mov     rcx, rdi; hObject
0x180015230  mov     r14d, eax
0x180015233  call    cs:__imp_CloseHandle
0x180015239  test    eax, eax
0x18001523b  jz      loc_180015332
0x180015241  mov     ecx, r14d; dwErrCode
0x180015244  call    cs:__imp_SetLastError
0x18001524a  mov     [rbx], r15
0x18001524d  lea     r8, asc_1800788F0; "h"
0x180015254  shr     rsi, 1Fh
0x180015258  mov     rdx, r13; unsigned __int64
0x18001525b  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180015260  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015265  test    esi, esi
0x180015267  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001526f  lea     r9, [rsp+288h+Name]; lpName
0x180015274  mov     [rsp+288h+dwFlags], r12d; int
0x180015279  cmovnz  ebp, esi
0x18001527c  mov     edx, esi; lInitialCount
0x18001527e  mov     r8d, ebp; lMaximumCount
0x180015281  xor     ecx, ecx; lpSemaphoreAttributes
0x180015283  call    cs:__imp_CreateSemaphoreExW
0x180015289  mov     rbp, rax
0x18001528c  test    rax, rax
0x18001528f  jnz     short loc_1800152BC
0x180015291  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015296  mov     ebx, eax
0x180015298  test    eax, eax
0x18001529a  jns     short loc_1800152EC
0x18001529c  mov     rcx, [rsp+288h]; this
0x1800152a4  lea     r8, aWil; "wil"
0x1800152ab  mov     r9d, eax; char *
0x1800152ae  mov     edx, 90h; void *
0x1800152b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152b8  mov     eax, ebx
0x1800152ba  jmp     short loc_1800152EE
0x1800152bc  call    cs:__imp_GetLastError
0x1800152c2  mov     rdi, [rbx+8]
0x1800152c6  test    rdi, rdi
0x1800152c9  jz      short loc_1800152E8
0x1800152cb  call    cs:__imp_GetLastError
0x1800152d1  mov     rcx, rdi; hObject
0x1800152d4  mov     esi, eax
0x1800152d6  call    cs:__imp_CloseHandle
0x1800152dc  test    eax, eax
0x1800152de  jz      short loc_180015319
0x1800152e0  mov     ecx, esi; dwErrCode
0x1800152e2  call    cs:__imp_SetLastError
0x1800152e8  mov     [rbx+8], rbp
0x1800152ec  xor     eax, eax
0x1800152ee  mov     rcx, [rsp+288h+var_48]
0x1800152f6  xor     rcx, rsp; StackCookie
0x1800152f9  call    __security_check_cookie
0x1800152fe  mov     rbx, [rsp+288h+arg_8]
0x180015306  add     rsp, 250h
0x18001530d  pop     r15
0x18001530f  pop     r14
0x180015311  pop     r13
0x180015313  pop     r12
0x180015315  pop     rdi
0x180015316  pop     rsi
0x180015317  pop     rbp
0x180015318  retn
0x180015319  mov     rcx, [rsp+288h]; this
0x180015321  mov     edx, 0A0Bh; void *
0x180015326  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001532c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015332  mov     rcx, [rsp+288h]; this
0x18001533a  mov     edx, 0A0Bh; void *
0x18001533f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
