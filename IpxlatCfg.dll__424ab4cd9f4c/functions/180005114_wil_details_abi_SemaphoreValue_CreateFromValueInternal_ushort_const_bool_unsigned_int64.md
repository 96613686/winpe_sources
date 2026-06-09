# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005114`
- end: `0x180005321`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004988`
- `0x180004d38`

## callees

- `0x180001d40`
- `0x180005114`
- `0x180005f58`
- `0x1800083b4`
- `0x180008df8`
- `0x180009bbc`
- `0x180009bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000520d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000520d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052b1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800051d8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005274`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800051d8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005274`

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
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
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
0x180005114  mov     [rsp+arg_8], rbx
0x180005119  mov     [rsp+arg_10], rbp
0x18000511e  push    rsi
0x18000511f  push    rdi
0x180005120  push    r12
0x180005122  push    r14
0x180005124  push    r15
0x180005126  sub     rsp, 250h
0x18000512d  mov     rax, cs:__security_cookie
0x180005134  xor     rax, rsp
0x180005137  mov     [rsp+278h+var_38], rax
0x18000513f  mov     rax, 0C000000000000000h
0x180005149  mov     rbp, r9
0x18000514c  mov     r8, rdx
0x18000514f  mov     rdi, rcx
0x180005152  test    rax, r9
0x180005155  jnz     loc_180005308
0x18000515b  xor     r12d, r12d
0x18000515e  lea     rax, [rsp+278h+Name]
0x180005163  mov     ecx, 7FFFFFFEh
0x180005168  mov     edx, 104h
0x18000516d  lea     esi, [r12+1]
0x180005172  test    rcx, rcx
0x180005175  jz      short loc_180005195
0x180005177  movzx   r9d, word ptr [r8]
0x18000517b  test    r9w, r9w
0x18000517f  jz      short loc_180005195
0x180005181  mov     [rax], r9w
0x180005185  add     r8, 2
0x180005189  add     rax, 2
0x18000518d  sub     rcx, rsi
0x180005190  sub     rdx, rsi; unsigned __int64
0x180005193  jnz     short loc_180005172
0x180005195  test    rdx, rdx
0x180005198  lea     rcx, [rax-2]
0x18000519c  lea     r8, aP0; "_p0"
0x1800051a3  cmovnz  rcx, rax
0x1800051a7  mov     [rcx], r12w
0x1800051ab  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800051b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051b5  mov     edx, ebp
0x1800051b7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800051bf  and     edx, 7FFFFFFFh; lInitialCount
0x1800051c5  mov     [rsp+278h+dwFlags], r12d; int
0x1800051ca  mov     r8d, esi
0x1800051cd  lea     r9, [rsp+278h+Name]; lpName
0x1800051d2  cmova   r8d, edx; lMaximumCount
0x1800051d6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800051d8  call    cs:__imp_CreateSemaphoreExW
0x1800051de  mov     r15, rax
0x1800051e1  test    rax, rax
0x1800051e4  jnz     short loc_18000520D
0x1800051e6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800051eb  mov     ebx, eax
0x1800051ed  test    eax, eax
0x1800051ef  jns     short loc_180005241
0x1800051f1  mov     edx, 8Bh; void *
0x1800051f6  mov     rcx, [rsp+278h]; this
0x1800051fe  mov     r9d, ebx; char *
0x180005201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005206  mov     eax, ebx
0x180005208  jmp     loc_1800052C9
0x18000520d  call    cs:__imp_GetLastError
0x180005213  mov     rbx, [rdi]
0x180005216  test    rbx, rbx
0x180005219  jz      short loc_18000523E
0x18000521b  call    cs:__imp_GetLastError
0x180005221  mov     rcx, rbx; hObject
0x180005224  mov     r14d, eax
0x180005227  call    cs:__imp_CloseHandle
0x18000522d  test    eax, eax
0x18000522f  jz      loc_18000530E
0x180005235  mov     ecx, r14d; dwErrCode
0x180005238  call    cs:__imp_SetLastError
0x18000523e  mov     [rdi], r15
0x180005241  lea     r8, asc_18001B8A0; "h"
0x180005248  shr     rbp, 1Fh
0x18000524c  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005251  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005256  test    ebp, ebp
0x180005258  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005260  lea     r9, [rsp+278h+Name]; lpName
0x180005265  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000526a  cmovnz  esi, ebp
0x18000526d  mov     edx, ebp; lInitialCount
0x18000526f  mov     r8d, esi; lMaximumCount
0x180005272  xor     ecx, ecx; lpSemaphoreAttributes
0x180005274  call    cs:__imp_CreateSemaphoreExW
0x18000527a  mov     rsi, rax
0x18000527d  test    rax, rax
0x180005280  jnz     short loc_180005297
0x180005282  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005287  mov     ebx, eax
0x180005289  test    eax, eax
0x18000528b  jns     short loc_1800052C7
0x18000528d  mov     edx, 90h
0x180005292  jmp     loc_1800051F6
0x180005297  call    cs:__imp_GetLastError
0x18000529d  mov     rbx, [rdi+8]
0x1800052a1  test    rbx, rbx
0x1800052a4  jz      short loc_1800052C3
0x1800052a6  call    cs:__imp_GetLastError
0x1800052ac  mov     rcx, rbx; hObject
0x1800052af  mov     ebp, eax
0x1800052b1  call    cs:__imp_CloseHandle
0x1800052b7  test    eax, eax
0x1800052b9  jz      short loc_1800052F5
0x1800052bb  mov     ecx, ebp; dwErrCode
0x1800052bd  call    cs:__imp_SetLastError
0x1800052c3  mov     [rdi+8], rsi
0x1800052c7  xor     eax, eax
0x1800052c9  mov     rcx, [rsp+278h+var_38]
0x1800052d1  xor     rcx, rsp; StackCookie
0x1800052d4  call    __security_check_cookie
0x1800052d9  lea     r11, [rsp+278h+var_28]
0x1800052e1  mov     rbx, [r11+38h]
0x1800052e5  mov     rbp, [r11+40h]
0x1800052e9  mov     rsp, r11
0x1800052ec  pop     r15
0x1800052ee  pop     r14
0x1800052f0  pop     r12
0x1800052f2  pop     rdi
0x1800052f3  pop     rsi
0x1800052f4  retn
0x1800052f5  mov     rcx, [rsp+278h]; this
0x1800052fd  mov     edx, 0A0Bh; void *
0x180005302  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005308  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000530e  mov     rcx, [rsp+278h]; this
0x180005316  mov     edx, 0A0Bh; void *
0x18000531b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
