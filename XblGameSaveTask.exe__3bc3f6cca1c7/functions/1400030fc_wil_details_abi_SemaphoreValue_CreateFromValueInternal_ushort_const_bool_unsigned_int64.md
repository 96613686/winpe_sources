# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400030fc`
- end: `0x140003309`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d58`

## callees

- `0x140001480`
- `0x1400030fc`
- `0x140003968`
- `0x140004724`
- `0x140005000`
- `0x14000553c`
- `0x14000554c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400031c0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000325c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400031c0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000325c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003220`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003220`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000327f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000328e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000327f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000328e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000320f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000320f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003299`

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
0x1400030fc  mov     [rsp+arg_8], rbx
0x140003101  mov     [rsp+arg_10], rbp
0x140003106  push    rsi
0x140003107  push    rdi
0x140003108  push    r12
0x14000310a  push    r14
0x14000310c  push    r15
0x14000310e  sub     rsp, 250h
0x140003115  mov     rax, cs:__security_cookie
0x14000311c  xor     rax, rsp
0x14000311f  mov     [rsp+278h+var_38], rax
0x140003127  mov     rax, 0C000000000000000h
0x140003131  mov     rbp, r9
0x140003134  mov     r8, rdx
0x140003137  mov     rdi, rcx
0x14000313a  test    rax, r9
0x14000313d  jnz     loc_1400032F0
0x140003143  xor     r12d, r12d
0x140003146  lea     rax, [rsp+278h+Name]
0x14000314b  mov     ecx, 7FFFFFFEh
0x140003150  mov     edx, 104h
0x140003155  lea     esi, [r12+1]
0x14000315a  test    rcx, rcx
0x14000315d  jz      short loc_14000317D
0x14000315f  movzx   r9d, word ptr [r8]
0x140003163  test    r9w, r9w
0x140003167  jz      short loc_14000317D
0x140003169  mov     [rax], r9w
0x14000316d  add     r8, 2
0x140003171  add     rax, 2
0x140003175  sub     rcx, rsi
0x140003178  sub     rdx, rsi; unsigned __int64
0x14000317b  jnz     short loc_14000315A
0x14000317d  test    rdx, rdx
0x140003180  lea     rcx, [rax-2]
0x140003184  lea     r8, aP0; "_p0"
0x14000318b  cmovnz  rcx, rax
0x14000318f  mov     [rcx], r12w
0x140003193  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003198  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000319d  mov     edx, ebp
0x14000319f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400031a7  and     edx, 7FFFFFFFh; lInitialCount
0x1400031ad  mov     [rsp+278h+dwFlags], r12d; int
0x1400031b2  mov     r8d, esi
0x1400031b5  lea     r9, [rsp+278h+Name]; lpName
0x1400031ba  cmova   r8d, edx; lMaximumCount
0x1400031be  xor     ecx, ecx; lpSemaphoreAttributes
0x1400031c0  call    cs:__imp_CreateSemaphoreExW
0x1400031c6  mov     r15, rax
0x1400031c9  test    rax, rax
0x1400031cc  jnz     short loc_1400031F5
0x1400031ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400031d3  mov     ebx, eax
0x1400031d5  test    eax, eax
0x1400031d7  jns     short loc_140003229
0x1400031d9  mov     edx, 8Bh; void *
0x1400031de  mov     rcx, [rsp+278h]; this
0x1400031e6  mov     r9d, ebx; char *
0x1400031e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031ee  mov     eax, ebx
0x1400031f0  jmp     loc_1400032B1
0x1400031f5  call    cs:__imp_GetLastError
0x1400031fb  mov     rbx, [rdi]
0x1400031fe  test    rbx, rbx
0x140003201  jz      short loc_140003226
0x140003203  call    cs:__imp_GetLastError
0x140003209  mov     rcx, rbx; hObject
0x14000320c  mov     r14d, eax
0x14000320f  call    cs:__imp_CloseHandle
0x140003215  test    eax, eax
0x140003217  jz      loc_1400032F6
0x14000321d  mov     ecx, r14d; dwErrCode
0x140003220  call    cs:__imp_SetLastError
0x140003226  mov     [rdi], r15
0x140003229  lea     r8, asc_140008B38; "h"
0x140003230  shr     rbp, 1Fh
0x140003234  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003239  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000323e  test    ebp, ebp
0x140003240  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003248  lea     r9, [rsp+278h+Name]; lpName
0x14000324d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003252  cmovnz  esi, ebp
0x140003255  mov     edx, ebp; lInitialCount
0x140003257  mov     r8d, esi; lMaximumCount
0x14000325a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000325c  call    cs:__imp_CreateSemaphoreExW
0x140003262  mov     rsi, rax
0x140003265  test    rax, rax
0x140003268  jnz     short loc_14000327F
0x14000326a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000326f  mov     ebx, eax
0x140003271  test    eax, eax
0x140003273  jns     short loc_1400032AF
0x140003275  mov     edx, 90h
0x14000327a  jmp     loc_1400031DE
0x14000327f  call    cs:__imp_GetLastError
0x140003285  mov     rbx, [rdi+8]
0x140003289  test    rbx, rbx
0x14000328c  jz      short loc_1400032AB
0x14000328e  call    cs:__imp_GetLastError
0x140003294  mov     rcx, rbx; hObject
0x140003297  mov     ebp, eax
0x140003299  call    cs:__imp_CloseHandle
0x14000329f  test    eax, eax
0x1400032a1  jz      short loc_1400032DD
0x1400032a3  mov     ecx, ebp; dwErrCode
0x1400032a5  call    cs:__imp_SetLastError
0x1400032ab  mov     [rdi+8], rsi
0x1400032af  xor     eax, eax
0x1400032b1  mov     rcx, [rsp+278h+var_38]
0x1400032b9  xor     rcx, rsp; StackCookie
0x1400032bc  call    __security_check_cookie
0x1400032c1  lea     r11, [rsp+278h+var_28]
0x1400032c9  mov     rbx, [r11+38h]
0x1400032cd  mov     rbp, [r11+40h]
0x1400032d1  mov     rsp, r11
0x1400032d4  pop     r15
0x1400032d6  pop     r14
0x1400032d8  pop     r12
0x1400032da  pop     rdi
0x1400032db  pop     rsi
0x1400032dc  retn
0x1400032dd  mov     rcx, [rsp+278h]; this
0x1400032e5  mov     edx, 0A0Bh; void *
0x1400032ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400032f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400032f6  mov     rcx, [rsp+278h]; this
0x1400032fe  mov     edx, 0A0Bh; void *
0x140003303  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
