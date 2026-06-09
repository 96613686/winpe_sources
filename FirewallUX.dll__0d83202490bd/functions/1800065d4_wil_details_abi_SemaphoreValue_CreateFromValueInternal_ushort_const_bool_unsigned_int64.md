# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800065d4`
- end: `0x1800067fe`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006128`
- `0x180023de4`

## callees

- `0x1800021c0`
- `0x1800065d4`
- `0x1800076b8`
- `0x180009544`
- `0x18000a2b8`
- `0x18000a938`
- `0x18000a948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006698`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000673b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006698`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000673b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000679a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000679a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000678e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000678e`

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
0x1800065d4  mov     [rsp+arg_8], rbx
0x1800065d9  mov     [rsp+arg_10], rbp
0x1800065de  push    rsi
0x1800065df  push    rdi
0x1800065e0  push    r12
0x1800065e2  push    r14
0x1800065e4  push    r15
0x1800065e6  sub     rsp, 250h
0x1800065ed  mov     rax, cs:__security_cookie
0x1800065f4  xor     rax, rsp
0x1800065f7  mov     [rsp+278h+var_38], rax
0x1800065ff  mov     rax, 0C000000000000000h
0x180006609  mov     rbp, r9
0x18000660c  mov     r8, rdx
0x18000660f  mov     rbx, rcx
0x180006612  test    rax, r9
0x180006615  jnz     loc_1800067E5
0x18000661b  xor     r12d, r12d
0x18000661e  lea     rax, [rsp+278h+Name]
0x180006623  mov     ecx, 7FFFFFFEh
0x180006628  mov     edx, 104h
0x18000662d  lea     esi, [r12+1]
0x180006632  test    rcx, rcx
0x180006635  jz      short loc_180006655
0x180006637  movzx   r9d, word ptr [r8]
0x18000663b  test    r9w, r9w
0x18000663f  jz      short loc_180006655
0x180006641  mov     [rax], r9w
0x180006645  add     r8, 2
0x180006649  add     rax, 2
0x18000664d  sub     rcx, rsi
0x180006650  sub     rdx, rsi; unsigned __int64
0x180006653  jnz     short loc_180006632
0x180006655  test    rdx, rdx
0x180006658  lea     rcx, [rax-2]
0x18000665c  lea     r8, aP0; "_p0"
0x180006663  cmovnz  rcx, rax
0x180006667  mov     [rcx], r12w
0x18000666b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006670  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006675  mov     edx, ebp
0x180006677  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000667f  and     edx, 7FFFFFFFh; lInitialCount
0x180006685  mov     [rsp+278h+dwFlags], r12d; int
0x18000668a  mov     r8d, esi
0x18000668d  lea     r9, [rsp+278h+Name]; lpName
0x180006692  cmova   r8d, edx; lMaximumCount
0x180006696  xor     ecx, ecx; lpSemaphoreAttributes
0x180006698  call    cs:__imp_CreateSemaphoreExW
0x18000669e  mov     r15, rax
0x1800066a1  test    rax, rax
0x1800066a4  jnz     short loc_1800066D4
0x1800066a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800066ab  mov     edi, eax
0x1800066ad  test    eax, eax
0x1800066af  jns     short loc_180006708
0x1800066b1  mov     rcx, [rsp+278h]; this
0x1800066b9  lea     r8, aWil; "wil"
0x1800066c0  mov     r9d, eax; char *
0x1800066c3  mov     edx, 8Bh; void *
0x1800066c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066cd  mov     eax, edi
0x1800066cf  jmp     loc_1800067A6
0x1800066d4  call    cs:__imp_GetLastError
0x1800066da  mov     rdi, [rbx]
0x1800066dd  test    rdi, rdi
0x1800066e0  jz      short loc_180006705
0x1800066e2  call    cs:__imp_GetLastError
0x1800066e8  mov     rcx, rdi; hObject
0x1800066eb  mov     r14d, eax
0x1800066ee  call    cs:__imp_CloseHandle
0x1800066f4  test    eax, eax
0x1800066f6  jz      loc_1800067EB
0x1800066fc  mov     ecx, r14d; dwErrCode
0x1800066ff  call    cs:__imp_SetLastError
0x180006705  mov     [rbx], r15
0x180006708  lea     r8, asc_1800300B0; "h"
0x18000670f  shr     rbp, 1Fh
0x180006713  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006718  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000671d  test    ebp, ebp
0x18000671f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006727  lea     r9, [rsp+278h+Name]; lpName
0x18000672c  mov     [rsp+278h+dwFlags], r12d; int
0x180006731  cmovnz  esi, ebp
0x180006734  mov     edx, ebp; lInitialCount
0x180006736  mov     r8d, esi; lMaximumCount
0x180006739  xor     ecx, ecx; lpSemaphoreAttributes
0x18000673b  call    cs:__imp_CreateSemaphoreExW
0x180006741  mov     rsi, rax
0x180006744  test    rax, rax
0x180006747  jnz     short loc_180006774
0x180006749  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000674e  mov     ebx, eax
0x180006750  test    eax, eax
0x180006752  jns     short loc_1800067A4
0x180006754  mov     rcx, [rsp+278h]; this
0x18000675c  lea     r8, aWil; "wil"
0x180006763  mov     r9d, eax; char *
0x180006766  mov     edx, 90h; void *
0x18000676b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006770  mov     eax, ebx
0x180006772  jmp     short loc_1800067A6
0x180006774  call    cs:__imp_GetLastError
0x18000677a  mov     rdi, [rbx+8]
0x18000677e  test    rdi, rdi
0x180006781  jz      short loc_1800067A0
0x180006783  call    cs:__imp_GetLastError
0x180006789  mov     rcx, rdi; hObject
0x18000678c  mov     ebp, eax
0x18000678e  call    cs:__imp_CloseHandle
0x180006794  test    eax, eax
0x180006796  jz      short loc_1800067D2
0x180006798  mov     ecx, ebp; dwErrCode
0x18000679a  call    cs:__imp_SetLastError
0x1800067a0  mov     [rbx+8], rsi
0x1800067a4  xor     eax, eax
0x1800067a6  mov     rcx, [rsp+278h+var_38]
0x1800067ae  xor     rcx, rsp; StackCookie
0x1800067b1  call    __security_check_cookie
0x1800067b6  lea     r11, [rsp+278h+var_28]
0x1800067be  mov     rbx, [r11+38h]
0x1800067c2  mov     rbp, [r11+40h]
0x1800067c6  mov     rsp, r11
0x1800067c9  pop     r15
0x1800067cb  pop     r14
0x1800067cd  pop     r12
0x1800067cf  pop     rdi
0x1800067d0  pop     rsi
0x1800067d1  retn
0x1800067d2  mov     rcx, [rsp+278h]; this
0x1800067da  mov     edx, 0A0Bh; void *
0x1800067df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067e5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800067eb  mov     rcx, [rsp+278h]; this
0x1800067f3  mov     edx, 0A0Bh; void *
0x1800067f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
