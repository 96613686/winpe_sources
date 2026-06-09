# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000708c`
- end: `0x1800072b6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006a78`
- `0x180015244`

## callees

- `0x180003520`
- `0x18000708c`
- `0x180008088`
- `0x1800092a4`
- `0x180009be4`
- `0x18000a364`
- `0x18000a374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007150`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071f3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007150`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000718c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000723b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000718c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000723b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007246`

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
0x18000708c  mov     [rsp+arg_8], rbx
0x180007091  mov     [rsp+arg_10], rbp
0x180007096  push    rsi
0x180007097  push    rdi
0x180007098  push    r12
0x18000709a  push    r14
0x18000709c  push    r15
0x18000709e  sub     rsp, 250h
0x1800070a5  mov     rax, cs:__security_cookie
0x1800070ac  xor     rax, rsp
0x1800070af  mov     [rsp+278h+var_38], rax
0x1800070b7  mov     rax, 0C000000000000000h
0x1800070c1  mov     rbp, r9
0x1800070c4  mov     r8, rdx
0x1800070c7  mov     rbx, rcx
0x1800070ca  test    rax, r9
0x1800070cd  jnz     loc_18000729D
0x1800070d3  xor     r12d, r12d
0x1800070d6  lea     rax, [rsp+278h+Name]
0x1800070db  mov     ecx, 7FFFFFFEh
0x1800070e0  mov     edx, 104h
0x1800070e5  lea     esi, [r12+1]
0x1800070ea  test    rcx, rcx
0x1800070ed  jz      short loc_18000710D
0x1800070ef  movzx   r9d, word ptr [r8]
0x1800070f3  test    r9w, r9w
0x1800070f7  jz      short loc_18000710D
0x1800070f9  mov     [rax], r9w
0x1800070fd  add     r8, 2
0x180007101  add     rax, 2
0x180007105  sub     rcx, rsi
0x180007108  sub     rdx, rsi; unsigned __int64
0x18000710b  jnz     short loc_1800070EA
0x18000710d  test    rdx, rdx
0x180007110  lea     rcx, [rax-2]
0x180007114  lea     r8, aP0; "_p0"
0x18000711b  cmovnz  rcx, rax
0x18000711f  mov     [rcx], r12w
0x180007123  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007128  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000712d  mov     edx, ebp
0x18000712f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007137  and     edx, 7FFFFFFFh; lInitialCount
0x18000713d  mov     [rsp+278h+dwFlags], r12d; int
0x180007142  mov     r8d, esi
0x180007145  lea     r9, [rsp+278h+Name]; lpName
0x18000714a  cmova   r8d, edx; lMaximumCount
0x18000714e  xor     ecx, ecx; lpSemaphoreAttributes
0x180007150  call    cs:__imp_CreateSemaphoreExW
0x180007156  mov     r15, rax
0x180007159  test    rax, rax
0x18000715c  jnz     short loc_18000718C
0x18000715e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007163  mov     edi, eax
0x180007165  test    eax, eax
0x180007167  jns     short loc_1800071C0
0x180007169  mov     rcx, [rsp+278h]; this
0x180007171  lea     r8, aWil; "wil"
0x180007178  mov     r9d, eax; char *
0x18000717b  mov     edx, 8Bh; void *
0x180007180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007185  mov     eax, edi
0x180007187  jmp     loc_18000725E
0x18000718c  call    cs:__imp_GetLastError
0x180007192  mov     rdi, [rbx]
0x180007195  test    rdi, rdi
0x180007198  jz      short loc_1800071BD
0x18000719a  call    cs:__imp_GetLastError
0x1800071a0  mov     rcx, rdi; hObject
0x1800071a3  mov     r14d, eax
0x1800071a6  call    cs:__imp_CloseHandle
0x1800071ac  test    eax, eax
0x1800071ae  jz      loc_1800072A3
0x1800071b4  mov     ecx, r14d; dwErrCode
0x1800071b7  call    cs:__imp_SetLastError
0x1800071bd  mov     [rbx], r15
0x1800071c0  lea     r8, asc_18002CBE0; "h"
0x1800071c7  shr     rbp, 1Fh
0x1800071cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800071d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071d5  test    ebp, ebp
0x1800071d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800071df  lea     r9, [rsp+278h+Name]; lpName
0x1800071e4  mov     [rsp+278h+dwFlags], r12d; int
0x1800071e9  cmovnz  esi, ebp
0x1800071ec  mov     edx, ebp; lInitialCount
0x1800071ee  mov     r8d, esi; lMaximumCount
0x1800071f1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800071f3  call    cs:__imp_CreateSemaphoreExW
0x1800071f9  mov     rsi, rax
0x1800071fc  test    rax, rax
0x1800071ff  jnz     short loc_18000722C
0x180007201  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007206  mov     ebx, eax
0x180007208  test    eax, eax
0x18000720a  jns     short loc_18000725C
0x18000720c  mov     rcx, [rsp+278h]; this
0x180007214  lea     r8, aWil; "wil"
0x18000721b  mov     r9d, eax; char *
0x18000721e  mov     edx, 90h; void *
0x180007223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007228  mov     eax, ebx
0x18000722a  jmp     short loc_18000725E
0x18000722c  call    cs:__imp_GetLastError
0x180007232  mov     rdi, [rbx+8]
0x180007236  test    rdi, rdi
0x180007239  jz      short loc_180007258
0x18000723b  call    cs:__imp_GetLastError
0x180007241  mov     rcx, rdi; hObject
0x180007244  mov     ebp, eax
0x180007246  call    cs:__imp_CloseHandle
0x18000724c  test    eax, eax
0x18000724e  jz      short loc_18000728A
0x180007250  mov     ecx, ebp; dwErrCode
0x180007252  call    cs:__imp_SetLastError
0x180007258  mov     [rbx+8], rsi
0x18000725c  xor     eax, eax
0x18000725e  mov     rcx, [rsp+278h+var_38]
0x180007266  xor     rcx, rsp; StackCookie
0x180007269  call    __security_check_cookie
0x18000726e  lea     r11, [rsp+278h+var_28]
0x180007276  mov     rbx, [r11+38h]
0x18000727a  mov     rbp, [r11+40h]
0x18000727e  mov     rsp, r11
0x180007281  pop     r15
0x180007283  pop     r14
0x180007285  pop     r12
0x180007287  pop     rdi
0x180007288  pop     rsi
0x180007289  retn
0x18000728a  mov     rcx, [rsp+278h]; this
0x180007292  mov     edx, 0A0Bh; void *
0x180007297  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000729d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800072a3  mov     rcx, [rsp+278h]; this
0x1800072ab  mov     edx, 0A0Bh; void *
0x1800072b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
