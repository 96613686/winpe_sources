# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180019934`
- end: `0x180019b5e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001928c`

## callees

- `0x180001800`
- `0x180019934`
- `0x18001a270`
- `0x18001c4c4`
- `0x18001cdd4`
- `0x18001e14c`
- `0x18001e15c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180019a4e`
- `KERNEL32!CloseHandle` at `0x180019aee`
- `KERNEL32!CloseHandle` at `0x180019a4e`
- `KERNEL32!CloseHandle` at `0x180019aee`
- `KERNEL32!GetLastError` at `0x180019a34`
- `KERNEL32!GetLastError` at `0x180019a42`
- `KERNEL32!GetLastError` at `0x180019ad4`
- `KERNEL32!GetLastError` at `0x180019ae3`
- `KERNEL32!GetLastError` at `0x180019a34`
- `KERNEL32!GetLastError` at `0x180019a42`
- `KERNEL32!GetLastError` at `0x180019ad4`
- `KERNEL32!GetLastError` at `0x180019ae3`
- `KERNEL32!SetLastError` at `0x180019a5f`
- `KERNEL32!SetLastError` at `0x180019afa`
- `KERNEL32!SetLastError` at `0x180019a5f`
- `KERNEL32!SetLastError` at `0x180019afa`
- `KERNEL32!CreateSemaphoreExW` at `0x1800199f8`
- `KERNEL32!CreateSemaphoreExW` at `0x180019a9b`
- `KERNEL32!CreateSemaphoreExW` at `0x1800199f8`
- `KERNEL32!CreateSemaphoreExW` at `0x180019a9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180019934  mov     [rsp+arg_8], rbx
0x180019939  mov     [rsp+arg_10], rbp
0x18001993e  push    rsi
0x18001993f  push    rdi
0x180019940  push    r12
0x180019942  push    r14
0x180019944  push    r15
0x180019946  sub     rsp, 250h
0x18001994d  mov     rax, cs:__security_cookie
0x180019954  xor     rax, rsp
0x180019957  mov     [rsp+278h+var_38], rax
0x18001995f  mov     rax, 0C000000000000000h
0x180019969  mov     rbp, r9
0x18001996c  mov     r8, rdx
0x18001996f  mov     rbx, rcx
0x180019972  test    rax, r9
0x180019975  jnz     loc_180019B45
0x18001997b  xor     r12d, r12d
0x18001997e  lea     rax, [rsp+278h+Name]
0x180019983  mov     ecx, 7FFFFFFEh
0x180019988  mov     edx, 104h
0x18001998d  lea     esi, [r12+1]
0x180019992  test    rcx, rcx
0x180019995  jz      short loc_1800199B5
0x180019997  movzx   r9d, word ptr [r8]
0x18001999b  test    r9w, r9w
0x18001999f  jz      short loc_1800199B5
0x1800199a1  mov     [rax], r9w
0x1800199a5  add     r8, 2
0x1800199a9  add     rax, 2
0x1800199ad  sub     rcx, rsi
0x1800199b0  sub     rdx, rsi; unsigned __int64
0x1800199b3  jnz     short loc_180019992
0x1800199b5  test    rdx, rdx
0x1800199b8  lea     rcx, [rax-2]
0x1800199bc  lea     r8, aP0; "_p0"
0x1800199c3  cmovnz  rcx, rax
0x1800199c7  mov     [rcx], r12w
0x1800199cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800199d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800199d5  mov     edx, ebp
0x1800199d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800199df  and     edx, 7FFFFFFFh; lInitialCount
0x1800199e5  mov     [rsp+278h+dwFlags], r12d; int
0x1800199ea  mov     r8d, esi
0x1800199ed  lea     r9, [rsp+278h+Name]; lpName
0x1800199f2  cmova   r8d, edx; lMaximumCount
0x1800199f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800199f8  call    cs:__imp_CreateSemaphoreExW
0x1800199fe  mov     r15, rax
0x180019a01  test    rax, rax
0x180019a04  jnz     short loc_180019A34
0x180019a06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019a0b  mov     edi, eax
0x180019a0d  test    eax, eax
0x180019a0f  jns     short loc_180019A68
0x180019a11  mov     rcx, [rsp+278h]; this
0x180019a19  lea     r8, aWil; "wil"
0x180019a20  mov     r9d, eax; char *
0x180019a23  mov     edx, 8Bh; void *
0x180019a28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a2d  mov     eax, edi
0x180019a2f  jmp     loc_180019B06
0x180019a34  call    cs:__imp_GetLastError
0x180019a3a  mov     rdi, [rbx]
0x180019a3d  test    rdi, rdi
0x180019a40  jz      short loc_180019A65
0x180019a42  call    cs:__imp_GetLastError
0x180019a48  mov     rcx, rdi; hObject
0x180019a4b  mov     r14d, eax
0x180019a4e  call    cs:__imp_CloseHandle
0x180019a54  test    eax, eax
0x180019a56  jz      loc_180019B4B
0x180019a5c  mov     ecx, r14d; dwErrCode
0x180019a5f  call    cs:__imp_SetLastError
0x180019a65  mov     [rbx], r15
0x180019a68  lea     r8, asc_18003AD70; "h"
0x180019a6f  shr     rbp, 1Fh
0x180019a73  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180019a78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019a7d  test    ebp, ebp
0x180019a7f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180019a87  lea     r9, [rsp+278h+Name]; lpName
0x180019a8c  mov     [rsp+278h+dwFlags], r12d; int
0x180019a91  cmovnz  esi, ebp
0x180019a94  mov     edx, ebp; lInitialCount
0x180019a96  mov     r8d, esi; lMaximumCount
0x180019a99  xor     ecx, ecx; lpSemaphoreAttributes
0x180019a9b  call    cs:__imp_CreateSemaphoreExW
0x180019aa1  mov     rsi, rax
0x180019aa4  test    rax, rax
0x180019aa7  jnz     short loc_180019AD4
0x180019aa9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019aae  mov     ebx, eax
0x180019ab0  test    eax, eax
0x180019ab2  jns     short loc_180019B04
0x180019ab4  mov     rcx, [rsp+278h]; this
0x180019abc  lea     r8, aWil; "wil"
0x180019ac3  mov     r9d, eax; char *
0x180019ac6  mov     edx, 90h; void *
0x180019acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ad0  mov     eax, ebx
0x180019ad2  jmp     short loc_180019B06
0x180019ad4  call    cs:__imp_GetLastError
0x180019ada  mov     rdi, [rbx+8]
0x180019ade  test    rdi, rdi
0x180019ae1  jz      short loc_180019B00
0x180019ae3  call    cs:__imp_GetLastError
0x180019ae9  mov     rcx, rdi; hObject
0x180019aec  mov     ebp, eax
0x180019aee  call    cs:__imp_CloseHandle
0x180019af4  test    eax, eax
0x180019af6  jz      short loc_180019B32
0x180019af8  mov     ecx, ebp; dwErrCode
0x180019afa  call    cs:__imp_SetLastError
0x180019b00  mov     [rbx+8], rsi
0x180019b04  xor     eax, eax
0x180019b06  mov     rcx, [rsp+278h+var_38]
0x180019b0e  xor     rcx, rsp; StackCookie
0x180019b11  call    __security_check_cookie
0x180019b16  lea     r11, [rsp+278h+var_28]
0x180019b1e  mov     rbx, [r11+38h]
0x180019b22  mov     rbp, [r11+40h]
0x180019b26  mov     rsp, r11
0x180019b29  pop     r15
0x180019b2b  pop     r14
0x180019b2d  pop     r12
0x180019b2f  pop     rdi
0x180019b30  pop     rsi
0x180019b31  retn
0x180019b32  mov     rcx, [rsp+278h]; this
0x180019b3a  mov     edx, 0A0Bh; void *
0x180019b3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019b45  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180019b4b  mov     rcx, [rsp+278h]; this
0x180019b53  mov     edx, 0A0Bh; void *
0x180019b58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
