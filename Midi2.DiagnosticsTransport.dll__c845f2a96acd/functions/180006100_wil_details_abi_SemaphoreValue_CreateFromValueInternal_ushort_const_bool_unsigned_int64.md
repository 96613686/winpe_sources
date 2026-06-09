# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006100`
- end: `0x18000632a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005198`

## callees

- `0x1800033d0`
- `0x180006100`
- `0x180006dd8`
- `0x180008f64`
- `0x1800098f4`
- `0x18000a104`
- `0x18000a114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800061c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006267`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800061c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006267`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000622b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000622b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000620e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000620e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000621a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000621a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062ba`

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
0x180006100  mov     [rsp+arg_8], rbx
0x180006105  mov     [rsp+arg_10], rbp
0x18000610a  push    rsi
0x18000610b  push    rdi
0x18000610c  push    r12
0x18000610e  push    r14
0x180006110  push    r15
0x180006112  sub     rsp, 250h
0x180006119  mov     rax, cs:__security_cookie
0x180006120  xor     rax, rsp
0x180006123  mov     [rsp+278h+var_38], rax
0x18000612b  mov     rax, 0C000000000000000h
0x180006135  mov     rbp, r9
0x180006138  mov     r8, rdx
0x18000613b  mov     rbx, rcx
0x18000613e  test    rax, r9
0x180006141  jnz     loc_180006311
0x180006147  xor     r12d, r12d
0x18000614a  lea     rax, [rsp+278h+Name]
0x18000614f  mov     ecx, 7FFFFFFEh
0x180006154  mov     edx, 104h
0x180006159  lea     esi, [r12+1]
0x18000615e  test    rcx, rcx
0x180006161  jz      short loc_180006181
0x180006163  movzx   r9d, word ptr [r8]
0x180006167  test    r9w, r9w
0x18000616b  jz      short loc_180006181
0x18000616d  mov     [rax], r9w
0x180006171  add     r8, 2
0x180006175  add     rax, 2
0x180006179  sub     rcx, rsi
0x18000617c  sub     rdx, rsi; unsigned __int64
0x18000617f  jnz     short loc_18000615E
0x180006181  test    rdx, rdx
0x180006184  lea     rcx, [rax-2]
0x180006188  lea     r8, aP0; "_p0"
0x18000618f  cmovnz  rcx, rax
0x180006193  mov     [rcx], r12w
0x180006197  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000619c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800061a1  mov     edx, ebp
0x1800061a3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800061ab  and     edx, 7FFFFFFFh; lInitialCount
0x1800061b1  mov     [rsp+278h+dwFlags], r12d; int
0x1800061b6  mov     r8d, esi
0x1800061b9  lea     r9, [rsp+278h+Name]; lpName
0x1800061be  cmova   r8d, edx; lMaximumCount
0x1800061c2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800061c4  call    cs:__imp_CreateSemaphoreExW
0x1800061ca  mov     r15, rax
0x1800061cd  test    rax, rax
0x1800061d0  jnz     short loc_180006200
0x1800061d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800061d7  mov     edi, eax
0x1800061d9  test    eax, eax
0x1800061db  jns     short loc_180006234
0x1800061dd  mov     rcx, [rsp+278h]; this
0x1800061e5  lea     r8, aWil; "wil"
0x1800061ec  mov     r9d, eax; char *
0x1800061ef  mov     edx, 8Bh; void *
0x1800061f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061f9  mov     eax, edi
0x1800061fb  jmp     loc_1800062D2
0x180006200  call    cs:__imp_GetLastError
0x180006206  mov     rdi, [rbx]
0x180006209  test    rdi, rdi
0x18000620c  jz      short loc_180006231
0x18000620e  call    cs:__imp_GetLastError
0x180006214  mov     rcx, rdi; hObject
0x180006217  mov     r14d, eax
0x18000621a  call    cs:__imp_CloseHandle
0x180006220  test    eax, eax
0x180006222  jz      loc_180006317
0x180006228  mov     ecx, r14d; dwErrCode
0x18000622b  call    cs:__imp_SetLastError
0x180006231  mov     [rbx], r15
0x180006234  lea     r8, asc_180015440; "h"
0x18000623b  shr     rbp, 1Fh
0x18000623f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006244  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006249  test    ebp, ebp
0x18000624b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006253  lea     r9, [rsp+278h+Name]; lpName
0x180006258  mov     [rsp+278h+dwFlags], r12d; int
0x18000625d  cmovnz  esi, ebp
0x180006260  mov     edx, ebp; lInitialCount
0x180006262  mov     r8d, esi; lMaximumCount
0x180006265  xor     ecx, ecx; lpSemaphoreAttributes
0x180006267  call    cs:__imp_CreateSemaphoreExW
0x18000626d  mov     rsi, rax
0x180006270  test    rax, rax
0x180006273  jnz     short loc_1800062A0
0x180006275  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000627a  mov     ebx, eax
0x18000627c  test    eax, eax
0x18000627e  jns     short loc_1800062D0
0x180006280  mov     rcx, [rsp+278h]; this
0x180006288  lea     r8, aWil; "wil"
0x18000628f  mov     r9d, eax; char *
0x180006292  mov     edx, 90h; void *
0x180006297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000629c  mov     eax, ebx
0x18000629e  jmp     short loc_1800062D2
0x1800062a0  call    cs:__imp_GetLastError
0x1800062a6  mov     rdi, [rbx+8]
0x1800062aa  test    rdi, rdi
0x1800062ad  jz      short loc_1800062CC
0x1800062af  call    cs:__imp_GetLastError
0x1800062b5  mov     rcx, rdi; hObject
0x1800062b8  mov     ebp, eax
0x1800062ba  call    cs:__imp_CloseHandle
0x1800062c0  test    eax, eax
0x1800062c2  jz      short loc_1800062FE
0x1800062c4  mov     ecx, ebp; dwErrCode
0x1800062c6  call    cs:__imp_SetLastError
0x1800062cc  mov     [rbx+8], rsi
0x1800062d0  xor     eax, eax
0x1800062d2  mov     rcx, [rsp+278h+var_38]
0x1800062da  xor     rcx, rsp; StackCookie
0x1800062dd  call    __security_check_cookie
0x1800062e2  lea     r11, [rsp+278h+var_28]
0x1800062ea  mov     rbx, [r11+38h]
0x1800062ee  mov     rbp, [r11+40h]
0x1800062f2  mov     rsp, r11
0x1800062f5  pop     r15
0x1800062f7  pop     r14
0x1800062f9  pop     r12
0x1800062fb  pop     rdi
0x1800062fc  pop     rsi
0x1800062fd  retn
0x1800062fe  mov     rcx, [rsp+278h]; this
0x180006306  mov     edx, 0A0Bh; void *
0x18000630b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006311  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006317  mov     rcx, [rsp+278h]; this
0x18000631f  mov     edx, 0A0Bh; void *
0x180006324  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
