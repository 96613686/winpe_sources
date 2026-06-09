# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800030bc`
- end: `0x1800032c9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002d18`

## callees

- `0x180001590`
- `0x1800030bc`
- `0x180003928`
- `0x1800046d4`
- `0x180004fb0`
- `0x1800054ec`
- `0x1800054fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003180`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000321c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003180`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000321c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000323f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000324e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000323f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000324e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003259`

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
0x1800030bc  mov     [rsp+arg_8], rbx
0x1800030c1  mov     [rsp+arg_10], rbp
0x1800030c6  push    rsi
0x1800030c7  push    rdi
0x1800030c8  push    r12
0x1800030ca  push    r14
0x1800030cc  push    r15
0x1800030ce  sub     rsp, 250h
0x1800030d5  mov     rax, cs:__security_cookie
0x1800030dc  xor     rax, rsp
0x1800030df  mov     [rsp+278h+var_38], rax
0x1800030e7  mov     rax, 0C000000000000000h
0x1800030f1  mov     rbp, r9
0x1800030f4  mov     r8, rdx
0x1800030f7  mov     rdi, rcx
0x1800030fa  test    rax, r9
0x1800030fd  jnz     loc_1800032B0
0x180003103  xor     r12d, r12d
0x180003106  lea     rax, [rsp+278h+Name]
0x18000310b  mov     ecx, 7FFFFFFEh
0x180003110  mov     edx, 104h
0x180003115  lea     esi, [r12+1]
0x18000311a  test    rcx, rcx
0x18000311d  jz      short loc_18000313D
0x18000311f  movzx   r9d, word ptr [r8]
0x180003123  test    r9w, r9w
0x180003127  jz      short loc_18000313D
0x180003129  mov     [rax], r9w
0x18000312d  add     r8, 2
0x180003131  add     rax, 2
0x180003135  sub     rcx, rsi
0x180003138  sub     rdx, rsi; unsigned __int64
0x18000313b  jnz     short loc_18000311A
0x18000313d  test    rdx, rdx
0x180003140  lea     rcx, [rax-2]
0x180003144  lea     r8, aP0; "_p0"
0x18000314b  cmovnz  rcx, rax
0x18000314f  mov     [rcx], r12w
0x180003153  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003158  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000315d  mov     edx, ebp
0x18000315f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003167  and     edx, 7FFFFFFFh; lInitialCount
0x18000316d  mov     [rsp+278h+dwFlags], r12d; int
0x180003172  mov     r8d, esi
0x180003175  lea     r9, [rsp+278h+Name]; lpName
0x18000317a  cmova   r8d, edx; lMaximumCount
0x18000317e  xor     ecx, ecx; lpSemaphoreAttributes
0x180003180  call    cs:__imp_CreateSemaphoreExW
0x180003186  mov     r15, rax
0x180003189  test    rax, rax
0x18000318c  jnz     short loc_1800031B5
0x18000318e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003193  mov     ebx, eax
0x180003195  test    eax, eax
0x180003197  jns     short loc_1800031E9
0x180003199  mov     edx, 8Bh; void *
0x18000319e  mov     rcx, [rsp+278h]; this
0x1800031a6  mov     r9d, ebx; char *
0x1800031a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031ae  mov     eax, ebx
0x1800031b0  jmp     loc_180003271
0x1800031b5  call    cs:__imp_GetLastError
0x1800031bb  mov     rbx, [rdi]
0x1800031be  test    rbx, rbx
0x1800031c1  jz      short loc_1800031E6
0x1800031c3  call    cs:__imp_GetLastError
0x1800031c9  mov     rcx, rbx; hObject
0x1800031cc  mov     r14d, eax
0x1800031cf  call    cs:__imp_CloseHandle
0x1800031d5  test    eax, eax
0x1800031d7  jz      loc_1800032B6
0x1800031dd  mov     ecx, r14d; dwErrCode
0x1800031e0  call    cs:__imp_SetLastError
0x1800031e6  mov     [rdi], r15
0x1800031e9  lea     r8, asc_1800088B0; "h"
0x1800031f0  shr     rbp, 1Fh
0x1800031f4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800031f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800031fe  test    ebp, ebp
0x180003200  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003208  lea     r9, [rsp+278h+Name]; lpName
0x18000320d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003212  cmovnz  esi, ebp
0x180003215  mov     edx, ebp; lInitialCount
0x180003217  mov     r8d, esi; lMaximumCount
0x18000321a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000321c  call    cs:__imp_CreateSemaphoreExW
0x180003222  mov     rsi, rax
0x180003225  test    rax, rax
0x180003228  jnz     short loc_18000323F
0x18000322a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000322f  mov     ebx, eax
0x180003231  test    eax, eax
0x180003233  jns     short loc_18000326F
0x180003235  mov     edx, 90h
0x18000323a  jmp     loc_18000319E
0x18000323f  call    cs:__imp_GetLastError
0x180003245  mov     rbx, [rdi+8]
0x180003249  test    rbx, rbx
0x18000324c  jz      short loc_18000326B
0x18000324e  call    cs:__imp_GetLastError
0x180003254  mov     rcx, rbx; hObject
0x180003257  mov     ebp, eax
0x180003259  call    cs:__imp_CloseHandle
0x18000325f  test    eax, eax
0x180003261  jz      short loc_18000329D
0x180003263  mov     ecx, ebp; dwErrCode
0x180003265  call    cs:__imp_SetLastError
0x18000326b  mov     [rdi+8], rsi
0x18000326f  xor     eax, eax
0x180003271  mov     rcx, [rsp+278h+var_38]
0x180003279  xor     rcx, rsp; StackCookie
0x18000327c  call    __security_check_cookie
0x180003281  lea     r11, [rsp+278h+var_28]
0x180003289  mov     rbx, [r11+38h]
0x18000328d  mov     rbp, [r11+40h]
0x180003291  mov     rsp, r11
0x180003294  pop     r15
0x180003296  pop     r14
0x180003298  pop     r12
0x18000329a  pop     rdi
0x18000329b  pop     rsi
0x18000329c  retn
0x18000329d  mov     rcx, [rsp+278h]; this
0x1800032a5  mov     edx, 0A0Bh; void *
0x1800032aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800032b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800032b6  mov     rcx, [rsp+278h]; this
0x1800032be  mov     edx, 0A0Bh; void *
0x1800032c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
