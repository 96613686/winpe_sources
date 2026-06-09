# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800046b0`
- end: `0x1800048d3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003eb0`
- `0x180004254`

## callees

- `0x1800046b0`
- `0x180006378`
- `0x180008c84`
- `0x180009620`
- `0x18000b848`
- `0x18000b858`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004779`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004818`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004779`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000484a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000484a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004870`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004864`

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
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  __int64 v31; // r8
  const char *v32; // r9
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800046b0  mov     [rsp+arg_8], rbx
0x1800046b5  push    rbp
0x1800046b6  push    rsi
0x1800046b7  push    rdi
0x1800046b8  push    r12
0x1800046ba  push    r13
0x1800046bc  push    r14
0x1800046be  push    r15
0x1800046c0  sub     rsp, 250h
0x1800046c7  mov     rax, cs:__security_cookie
0x1800046ce  xor     rax, rsp
0x1800046d1  mov     [rsp+288h+var_48], rax
0x1800046d9  mov     rax, 0C000000000000000h
0x1800046e3  mov     rsi, r9
0x1800046e6  mov     r8, rdx
0x1800046e9  mov     rbx, rcx
0x1800046ec  test    rax, r9
0x1800046ef  jnz     loc_1800048BA
0x1800046f5  xor     r12d, r12d
0x1800046f8  lea     rax, [rsp+288h+Name]
0x1800046fd  mov     r13d, 104h
0x180004703  mov     ecx, 7FFFFFFEh
0x180004708  mov     edx, r13d
0x18000470b  lea     ebp, [r12+1]
0x180004710  test    rcx, rcx
0x180004713  jz      short loc_180004733
0x180004715  movzx   r9d, word ptr [r8]
0x180004719  test    r9w, r9w
0x18000471d  jz      short loc_180004733
0x18000471f  mov     [rax], r9w
0x180004723  add     r8, 2
0x180004727  add     rax, 2
0x18000472b  sub     rcx, rbp
0x18000472e  sub     rdx, rbp
0x180004731  jnz     short loc_180004710
0x180004733  test    rdx, rdx
0x180004736  lea     rcx, [rax-2]
0x18000473a  lea     r8, aP0; "_p0"
0x180004741  mov     rdx, r13; unsigned __int64
0x180004744  cmovnz  rcx, rax
0x180004748  mov     [rcx], r12w
0x18000474c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004751  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004756  mov     edx, esi
0x180004758  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004760  and     edx, 7FFFFFFFh; lInitialCount
0x180004766  mov     [rsp+288h+dwFlags], r12d; int
0x18000476b  mov     r8d, ebp
0x18000476e  lea     r9, [rsp+288h+Name]; lpName
0x180004773  cmova   r8d, edx; lMaximumCount
0x180004777  xor     ecx, ecx; lpSemaphoreAttributes
0x180004779  call    cs:__imp_CreateSemaphoreExW
0x18000477f  mov     r15, rax
0x180004782  test    rax, rax
0x180004785  jnz     short loc_1800047AE
0x180004787  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000478c  mov     edi, eax
0x18000478e  test    eax, eax
0x180004790  jns     short loc_1800047E2
0x180004792  mov     rcx, [rsp+288h]; this
0x18000479a  mov     r9d, eax; char *
0x18000479d  mov     edx, 8Bh; void *
0x1800047a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047a7  mov     eax, edi
0x1800047a9  jmp     loc_18000487C
0x1800047ae  call    cs:__imp_GetLastError
0x1800047b4  mov     rdi, [rbx]
0x1800047b7  test    rdi, rdi
0x1800047ba  jz      short loc_1800047DF
0x1800047bc  call    cs:__imp_GetLastError
0x1800047c2  mov     rcx, rdi; hObject
0x1800047c5  mov     r14d, eax
0x1800047c8  call    cs:__imp_CloseHandle
0x1800047ce  test    eax, eax
0x1800047d0  jz      loc_1800048C0
0x1800047d6  mov     ecx, r14d; dwErrCode
0x1800047d9  call    cs:__imp_SetLastError
0x1800047df  mov     [rbx], r15
0x1800047e2  lea     r8, asc_180015360; "h"
0x1800047e9  shr     rsi, 1Fh
0x1800047ed  mov     rdx, r13; unsigned __int64
0x1800047f0  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800047f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800047fa  test    esi, esi
0x1800047fc  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004804  lea     r9, [rsp+288h+Name]; lpName
0x180004809  mov     [rsp+288h+dwFlags], r12d; int
0x18000480e  cmovnz  ebp, esi
0x180004811  mov     edx, esi; lInitialCount
0x180004813  mov     r8d, ebp; lMaximumCount
0x180004816  xor     ecx, ecx; lpSemaphoreAttributes
0x180004818  call    cs:__imp_CreateSemaphoreExW
0x18000481e  mov     rbp, rax
0x180004821  test    rax, rax
0x180004824  jnz     short loc_18000484A
0x180004826  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000482b  mov     ebx, eax
0x18000482d  test    eax, eax
0x18000482f  jns     short loc_18000487A
0x180004831  mov     rcx, [rsp+288h]; this
0x180004839  mov     r9d, eax; char *
0x18000483c  mov     edx, 90h; void *
0x180004841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004846  mov     eax, ebx
0x180004848  jmp     short loc_18000487C
0x18000484a  call    cs:__imp_GetLastError
0x180004850  mov     rdi, [rbx+8]
0x180004854  test    rdi, rdi
0x180004857  jz      short loc_180004876
0x180004859  call    cs:__imp_GetLastError
0x18000485f  mov     rcx, rdi; hObject
0x180004862  mov     esi, eax
0x180004864  call    cs:__imp_CloseHandle
0x18000486a  test    eax, eax
0x18000486c  jz      short loc_1800048A7
0x18000486e  mov     ecx, esi; dwErrCode
0x180004870  call    cs:__imp_SetLastError
0x180004876  mov     [rbx+8], rbp
0x18000487a  xor     eax, eax
0x18000487c  mov     rcx, [rsp+288h+var_48]
0x180004884  xor     rcx, rsp; StackCookie
0x180004887  call    __security_check_cookie
0x18000488c  mov     rbx, [rsp+288h+arg_8]
0x180004894  add     rsp, 250h
0x18000489b  pop     r15
0x18000489d  pop     r14
0x18000489f  pop     r13
0x1800048a1  pop     r12
0x1800048a3  pop     rdi
0x1800048a4  pop     rsi
0x1800048a5  pop     rbp
0x1800048a6  retn
0x1800048a7  mov     rcx, [rsp+288h]; this
0x1800048af  mov     edx, 0A0Bh; void *
0x1800048b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800048c0  mov     rcx, [rsp+288h]; this
0x1800048c8  mov     edx, 0A0Bh; void *
0x1800048cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
