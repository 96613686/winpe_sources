# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180003280`
- end: `0x180003489`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `521`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003924`
- `0x180005b00`

## callees

- `0x1800012b4`
- `0x180001e80`
- `0x180002de0`
- `0x180002e24`
- `0x180002e94`
- `0x180003280`
- `0x180008a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000333f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800033d9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000333f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800033d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000339d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003422`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000339d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000340b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000338c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000338c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003416`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  __int64 v19; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rdi
  wil::details *v25; // rcx
  HANDLE v26; // rdi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v6 = a3 >> 2;
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
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, v6 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
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
LABEL_18:
    StringCchCatW(Name, v16, L"h");
    v24 = v6 >> 31;
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
      v18 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v19 = 144;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_18;
  v19 = 139;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v18;
}

```

## disassembly

```asm
0x180003280  mov     [rsp+arg_8], rbx
0x180003285  mov     [rsp+arg_18], rbp
0x18000328a  push    rsi
0x18000328b  push    rdi
0x18000328c  push    r12
0x18000328e  push    r14
0x180003290  push    r15
0x180003292  sub     rsp, 250h
0x180003299  mov     rax, cs:__security_cookie
0x1800032a0  xor     rax, rsp
0x1800032a3  mov     [rsp+278h+var_38], rax
0x1800032ab  mov     rdi, r8
0x1800032ae  mov     rsi, rcx
0x1800032b1  mov     r8, rdx
0x1800032b4  test    dil, 3
0x1800032b8  jnz     loc_180003470
0x1800032be  shr     rdi, 2
0x1800032c2  lea     rax, [rsp+278h+Name]
0x1800032c7  xor     r12d, r12d
0x1800032ca  mov     ecx, 7FFFFFFEh
0x1800032cf  mov     edx, 104h
0x1800032d4  lea     ebp, [r12+1]
0x1800032d9  test    rcx, rcx
0x1800032dc  jz      short loc_1800032FC
0x1800032de  movzx   r9d, word ptr [r8]
0x1800032e2  test    r9w, r9w
0x1800032e6  jz      short loc_1800032FC
0x1800032e8  mov     [rax], r9w
0x1800032ec  add     r8, 2
0x1800032f0  add     rax, 2
0x1800032f4  sub     rcx, rbp
0x1800032f7  sub     rdx, rbp; unsigned __int64
0x1800032fa  jnz     short loc_1800032D9
0x1800032fc  test    rdx, rdx
0x1800032ff  lea     rcx, [rax-2]
0x180003303  lea     r8, aP0; "_p0"
0x18000330a  cmovnz  rcx, rax
0x18000330e  mov     [rcx], r12w
0x180003312  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003317  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000331c  mov     edx, edi
0x18000331e  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003326  and     edx, 7FFFFFFFh; lInitialCount
0x18000332c  mov     [rsp+278h+dwFlags], r12d; int
0x180003331  mov     r8d, ebp
0x180003334  lea     r9, [rsp+278h+Name]; lpName
0x180003339  cmova   r8d, edx; lMaximumCount
0x18000333d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000333f  call    cs:__imp_CreateSemaphoreExW
0x180003345  mov     r15, rax
0x180003348  test    rax, rax
0x18000334b  jnz     short loc_180003372
0x18000334d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003352  mov     ebx, eax
0x180003354  test    eax, eax
0x180003356  jns     short loc_1800033A6
0x180003358  mov     edx, 8Bh; void *
0x18000335d  mov     rcx, [rsp+278h]; this
0x180003365  mov     r9d, eax; char *
0x180003368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000336d  jmp     loc_18000342F
0x180003372  call    cs:__imp_GetLastError
0x180003378  mov     rbx, [rsi]
0x18000337b  test    rbx, rbx
0x18000337e  jz      short loc_1800033A3
0x180003380  call    cs:__imp_GetLastError
0x180003386  mov     rcx, rbx; hObject
0x180003389  mov     r14d, eax
0x18000338c  call    cs:__imp_CloseHandle
0x180003392  test    eax, eax
0x180003394  jz      loc_180003476
0x18000339a  mov     ecx, r14d; dwErrCode
0x18000339d  call    cs:__imp_SetLastError
0x1800033a3  mov     [rsi], r15
0x1800033a6  lea     r8, asc_18000BC28; "h"
0x1800033ad  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800033b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800033b7  shr     rdi, 1Fh
0x1800033bb  lea     r9, [rsp+278h+Name]; lpName
0x1800033c0  test    edi, edi
0x1800033c2  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800033ca  mov     edx, edi; lInitialCount
0x1800033cc  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800033d1  cmovnz  ebp, edi
0x1800033d4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800033d6  mov     r8d, ebp; lMaximumCount
0x1800033d9  call    cs:__imp_CreateSemaphoreExW
0x1800033df  mov     rdi, rax
0x1800033e2  test    rax, rax
0x1800033e5  jnz     short loc_1800033FC
0x1800033e7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800033ec  mov     ebx, eax
0x1800033ee  test    eax, eax
0x1800033f0  jns     short loc_18000342C
0x1800033f2  mov     edx, 90h
0x1800033f7  jmp     loc_18000335D
0x1800033fc  call    cs:__imp_GetLastError
0x180003402  mov     rbx, [rsi+8]
0x180003406  test    rbx, rbx
0x180003409  jz      short loc_180003428
0x18000340b  call    cs:__imp_GetLastError
0x180003411  mov     rcx, rbx; hObject
0x180003414  mov     ebp, eax
0x180003416  call    cs:__imp_CloseHandle
0x18000341c  test    eax, eax
0x18000341e  jz      short loc_18000345D
0x180003420  mov     ecx, ebp; dwErrCode
0x180003422  call    cs:__imp_SetLastError
0x180003428  mov     [rsi+8], rdi
0x18000342c  mov     ebx, r12d
0x18000342f  mov     eax, ebx
0x180003431  mov     rcx, [rsp+278h+var_38]
0x180003439  xor     rcx, rsp; StackCookie
0x18000343c  call    __security_check_cookie
0x180003441  lea     r11, [rsp+278h+var_28]
0x180003449  mov     rbx, [r11+38h]
0x18000344d  mov     rbp, [r11+48h]
0x180003451  mov     rsp, r11
0x180003454  pop     r15
0x180003456  pop     r14
0x180003458  pop     r12
0x18000345a  pop     rdi
0x18000345b  pop     rsi
0x18000345c  retn
0x18000345d  mov     rcx, [rsp+278h]; this
0x180003465  mov     edx, 0A0Bh; void *
0x18000346a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003470  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003476  mov     rcx, [rsp+278h]; this
0x18000347e  mov     edx, 0A0Bh; void *
0x180003483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
