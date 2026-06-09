# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180003f20`
- end: `0x180004256`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `822`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005aa0`

## callees

- `0x180002ca0`
- `0x180003e90`
- `0x180003ed0`
- `0x180003f10`
- `0x180003f20`
- `0x180007280`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180004078`
- `KERNEL32!CreateSemaphoreExW` at `0x180004171`
- `KERNEL32!CreateSemaphoreExW` at `0x180004078`
- `KERNEL32!CreateSemaphoreExW` at `0x180004171`
- `KERNEL32!SetLastError` at `0x1800040da`
- `KERNEL32!SetLastError` at `0x1800041cc`
- `KERNEL32!SetLastError` at `0x1800040da`
- `KERNEL32!SetLastError` at `0x1800041cc`
- `KERNEL32!GetLastError` at `0x1800040b0`
- `KERNEL32!GetLastError` at `0x1800040bf`
- `KERNEL32!GetLastError` at `0x1800041a6`
- `KERNEL32!GetLastError` at `0x1800041b5`
- `KERNEL32!GetLastError` at `0x1800040b0`
- `KERNEL32!GetLastError` at `0x1800040bf`
- `KERNEL32!GetLastError` at `0x1800041a6`
- `KERNEL32!GetLastError` at `0x1800041b5`
- `KERNEL32!CloseHandle` at `0x1800040ca`
- `KERNEL32!CloseHandle` at `0x1800041c0`
- `KERNEL32!CloseHandle` at `0x1800040ca`
- `KERNEL32!CloseHandle` at `0x1800041c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  signed __int64 v9; // r8
  WCHAR v10; // ax
  WCHAR *v11; // rax
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  char *v19; // r9
  WCHAR v20; // r8
  WCHAR *v21; // rax
  unsigned __int64 v22; // r15
  LONG v23; // r10d
  LONG v24; // r12d
  LONG v25; // r8d
  wil::details *v26; // rcx
  HANDLE Semaphore; // r14
  int LastErrorFailHr; // eax
  unsigned int v29; // r8d
  unsigned int v30; // esi
  void *v32; // rsi
  DWORD LastError; // ebp
  int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rcx
  WCHAR *v37; // rax
  __int64 v38; // rax
  WCHAR *v39; // rcx
  __int64 v40; // rbx
  char *v41; // rdx
  WCHAR v42; // ax
  WCHAR *v43; // rax
  wil::details *v44; // rcx
  HANDLE v45; // rdi
  int v46; // eax
  unsigned int v47; // r8d
  unsigned int v48; // ebx
  void *v49; // rbx
  DWORD v50; // esi
  int v51; // r8d
  const char *v52; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 260;
  v9 = (char *)a2 - (char *)Name;
  do
  {
    if ( v8 == -2147483386 )
      break;
    v10 = *(WCHAR *)((char *)v7 + v9);
    if ( !v10 )
      break;
    *v7++ = v10;
    --v8;
  }
  while ( v8 );
  v11 = v7 - 1;
  if ( v8 )
    v11 = v7;
  v12 = 260;
  *v11 = 0;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 2147483646;
  v15 = 260 - v12;
  if ( v12 )
  {
    v16 = &Name[v15];
    v17 = 260 - v15;
    if ( v15 != 260 )
    {
      v18 = 2147483646;
      v19 = (char *)((char *)L"_p0" - (char *)v16);
      do
      {
        if ( !v18 )
          break;
        v20 = *(WCHAR *)((char *)v16 + (_QWORD)v19);
        if ( !v20 )
          break;
        *v16 = v20;
        --v18;
        ++v16;
        --v17;
      }
      while ( v17 );
    }
    v21 = v16 - 1;
    if ( v17 )
      v21 = v16;
    *v21 = 0;
  }
  v22 = a4 >> 31;
  v23 = a4 & 0x7FFFFFFF;
  v24 = 1;
  v25 = 1;
  if ( v23 )
    v25 = v23;
  Semaphore = CreateSemaphoreExW(0, v23, v25, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v32 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v32) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    v30 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        v29,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v30;
    }
  }
  v36 = 260;
  v37 = Name;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  v38 = 260 - v36;
  if ( v36 )
  {
    v39 = &Name[v38];
    v40 = 260 - v38;
    if ( 260 != v38 )
    {
      v41 = (char *)((char *)L"h" - (char *)v39);
      do
      {
        if ( !v14 )
          break;
        v42 = *(WCHAR *)((char *)v39 + (_QWORD)v41);
        if ( !v42 )
          break;
        *v39 = v42;
        --v14;
        ++v39;
        --v40;
      }
      while ( v40 );
    }
    v43 = v39 - 1;
    if ( v40 )
      v43 = v39;
    *v43 = 0;
  }
  if ( (_DWORD)v22 )
    v24 = v22;
  v45 = CreateSemaphoreExW(0, v22, v24, Name, 0, 0x1F0003u);
  if ( v45 )
  {
    GetLastError();
    v49 = (void *)*((_QWORD *)this + 1);
    if ( v49 )
    {
      v50 = GetLastError();
      if ( !CloseHandle(v49) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v51, v52);
      SetLastError(v50);
    }
    *((_QWORD *)this + 1) = v45;
  }
  else
  {
    v46 = wil::details::GetLastErrorFailHr(v44);
    v48 = v46;
    if ( v46 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x8D, v47, (const char *)(unsigned int)v46, dwFlagsa);
      return v48;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003f20  mov     r11, rsp
0x180003f23  push    r13
0x180003f25  sub     rsp, 280h
0x180003f2c  mov     rax, cs:__security_cookie
0x180003f33  xor     rax, rsp
0x180003f36  mov     [rsp+288h+var_48], rax
0x180003f3e  mov     rax, 0C000000000000000h
0x180003f48  mov     r10, r9
0x180003f4b  mov     r8, rdx
0x180003f4e  mov     r13, rcx
0x180003f51  test    rax, r9
0x180003f54  jnz     loc_18000423D
0x180003f5a  mov     [r11+10h], rbx
0x180003f5e  lea     rax, [rsp+288h+Name]
0x180003f63  mov     [r11-10h], rbp
0x180003f67  lea     rcx, [rsp+288h+Name]
0x180003f6c  mov     [r11-20h], rdi
0x180003f70  mov     ebx, 104h
0x180003f75  mov     [r11-28h], r12
0x180003f79  mov     edx, ebx
0x180003f7b  mov     [r11-30h], r14
0x180003f7f  sub     r8, rax
0x180003f82  mov     [r11-38h], r15
0x180003f86  nop     word ptr [rax+rax+00000000h]
0x180003f90  lea     rax, [rdx+7FFFFEFAh]
0x180003f97  test    rax, rax
0x180003f9a  jz      short loc_180003FB3
0x180003f9c  movzx   eax, word ptr [r8+rcx]
0x180003fa1  test    ax, ax
0x180003fa4  jz      short loc_180003FB3
0x180003fa6  mov     [rcx], ax
0x180003fa9  add     rcx, 2
0x180003fad  sub     rdx, 1
0x180003fb1  jnz     short loc_180003F90
0x180003fb3  test    rdx, rdx
0x180003fb6  lea     rax, [rcx-2]
0x180003fba  cmovnz  rax, rcx
0x180003fbe  xor     ebp, ebp
0x180003fc0  mov     rcx, rbx
0x180003fc3  mov     [rax], bp
0x180003fc6  lea     rax, [rsp+288h+Name]
0x180003fcb  nop     dword ptr [rax+rax+00h]
0x180003fd0  cmp     [rax], bp
0x180003fd3  jz      short loc_180003FDF
0x180003fd5  add     rax, 2
0x180003fd9  sub     rcx, 1
0x180003fdd  jnz     short loc_180003FD0
0x180003fdf  mov     rax, rbx
0x180003fe2  mov     edi, 7FFFFFFEh
0x180003fe7  sub     rax, rcx
0x180003fea  test    rcx, rcx
0x180003fed  cmovz   rax, rbp
0x180003ff1  jz      short loc_18000403F
0x180003ff3  mov     rdx, rbx
0x180003ff6  lea     rcx, [rsp+288h+Name]
0x180003ffb  lea     rcx, [rcx+rax*2]
0x180003fff  sub     rdx, rax
0x180004002  jz      short loc_180004031
0x180004004  lea     r9, aP0; "_p0"
0x18000400b  mov     eax, edi
0x18000400d  sub     r9, rcx
0x180004010  test    rax, rax
0x180004013  jz      short loc_180004031
0x180004015  movzx   r8d, word ptr [r9+rcx]
0x18000401a  test    r8w, r8w
0x18000401e  jz      short loc_180004031
0x180004020  mov     [rcx], r8w
0x180004024  dec     rax
0x180004027  add     rcx, 2
0x18000402b  sub     rdx, 1
0x18000402f  jnz     short loc_180004010
0x180004031  test    rdx, rdx
0x180004034  lea     rax, [rcx-2]
0x180004038  cmovnz  rax, rcx
0x18000403c  mov     [rax], bp
0x18000403f  mov     r15, r10
0x180004042  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000404a  shr     r15, 1Fh
0x18000404e  lea     r9, [rsp+288h+Name]; lpName
0x180004053  and     r10d, 7FFFFFFFh
0x18000405a  mov     [rsp+288h+var_18], rsi
0x180004062  mov     r12d, 1
0x180004068  mov     [rsp+288h+dwFlags], ebp; int
0x18000406c  mov     r8d, r12d
0x18000406f  mov     edx, r10d; lInitialCount
0x180004072  cmova   r8d, r10d; lMaximumCount
0x180004076  xor     ecx, ecx; lpSemaphoreAttributes
0x180004078  call    cs:__imp_CreateSemaphoreExW
0x18000407e  mov     r14, rax
0x180004081  test    rax, rax
0x180004084  jnz     short loc_1800040B0
0x180004086  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000408b  mov     esi, eax
0x18000408d  test    eax, eax
0x18000408f  jns     short loc_1800040E6
0x180004091  lfence
0x180004094  mov     rcx, [rsp+288h]; this
0x18000409c  mov     r9d, eax; char *
0x18000409f  mov     edx, 88h; void *
0x1800040a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040a9  mov     eax, esi
0x1800040ab  jmp     loc_1800041D8
0x1800040b0  call    cs:__imp_GetLastError
0x1800040b6  mov     rsi, [r13+0]
0x1800040ba  test    rsi, rsi
0x1800040bd  jz      short loc_1800040E2
0x1800040bf  call    cs:__imp_GetLastError
0x1800040c5  mov     rcx, rsi; hObject
0x1800040c8  mov     ebp, eax
0x1800040ca  call    cs:__imp_CloseHandle
0x1800040d0  test    eax, eax
0x1800040d2  jz      loc_180004243
0x1800040d8  mov     ecx, ebp; dwErrCode
0x1800040da  call    cs:__imp_SetLastError
0x1800040e0  xor     ebp, ebp
0x1800040e2  mov     [r13+0], r14
0x1800040e6  mov     rcx, rbx
0x1800040e9  lea     rax, [rsp+288h+Name]
0x1800040ee  xchg    ax, ax
0x1800040f0  cmp     word ptr [rax], 0
0x1800040f4  jz      short loc_1800040FF
0x1800040f6  add     rax, 2
0x1800040fa  sub     rcx, r12
0x1800040fd  jnz     short loc_1800040F0
0x1800040ff  mov     rax, rbx
0x180004102  sub     rax, rcx
0x180004105  test    rcx, rcx
0x180004108  cmovz   rax, rbp
0x18000410c  jz      short loc_180004151
0x18000410e  lea     rcx, [rsp+288h+Name]
0x180004113  lea     rcx, [rcx+rax*2]
0x180004117  sub     rbx, rax
0x18000411a  jz      short loc_180004143
0x18000411c  lea     rdx, asc_18000E8A8; "h"
0x180004123  sub     rdx, rcx
0x180004126  test    rdi, rdi
0x180004129  jz      short loc_180004143
0x18000412b  movzx   eax, word ptr [rdx+rcx]
0x18000412f  test    ax, ax
0x180004132  jz      short loc_180004143
0x180004134  mov     [rcx], ax
0x180004137  dec     rdi
0x18000413a  add     rcx, 2
0x18000413e  sub     rbx, r12
0x180004141  jnz     short loc_180004126
0x180004143  test    rbx, rbx
0x180004146  lea     rax, [rcx-2]
0x18000414a  cmovnz  rax, rcx
0x18000414e  mov     [rax], bp
0x180004151  test    r15d, r15d
0x180004154  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000415c  lea     r9, [rsp+288h+Name]; lpName
0x180004161  mov     [rsp+288h+dwFlags], ebp; int
0x180004165  cmovnz  r12d, r15d
0x180004169  mov     edx, r15d; lInitialCount
0x18000416c  mov     r8d, r12d; lMaximumCount
0x18000416f  xor     ecx, ecx; lpSemaphoreAttributes
0x180004171  call    cs:__imp_CreateSemaphoreExW
0x180004177  mov     rdi, rax
0x18000417a  test    rax, rax
0x18000417d  jnz     short loc_1800041A6
0x18000417f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004184  mov     ebx, eax
0x180004186  test    eax, eax
0x180004188  jns     short loc_1800041D6
0x18000418a  lfence
0x18000418d  mov     rcx, [rsp+288h]; this
0x180004195  mov     r9d, eax; char *
0x180004198  mov     edx, 8Dh; void *
0x18000419d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041a2  mov     eax, ebx
0x1800041a4  jmp     short loc_1800041D8
0x1800041a6  call    cs:__imp_GetLastError
0x1800041ac  mov     rbx, [r13+8]
0x1800041b0  test    rbx, rbx
0x1800041b3  jz      short loc_1800041D2
0x1800041b5  call    cs:__imp_GetLastError
0x1800041bb  mov     rcx, rbx; hObject
0x1800041be  mov     esi, eax
0x1800041c0  call    cs:__imp_CloseHandle
0x1800041c6  test    eax, eax
0x1800041c8  jz      short loc_18000422A
0x1800041ca  mov     ecx, esi; dwErrCode
0x1800041cc  call    cs:__imp_SetLastError
0x1800041d2  mov     [r13+8], rdi
0x1800041d6  xor     eax, eax
0x1800041d8  mov     rsi, [rsp+288h+var_18]
0x1800041e0  mov     r12, [rsp+288h+var_28]
0x1800041e8  mov     rdi, [rsp+288h+var_20]
0x1800041f0  mov     r14, [rsp+288h+var_30]
0x1800041f8  mov     rbp, [rsp+288h+var_10]
0x180004200  mov     rbx, [rsp+288h+arg_8]
0x180004208  mov     r15, [rsp+288h+var_38]
0x180004210  mov     rcx, [rsp+288h+var_48]
0x180004218  xor     rcx, rsp; StackCookie
0x18000421b  call    __security_check_cookie
0x180004220  add     rsp, 280h
0x180004227  pop     r13
0x180004229  retn
0x18000422a  mov     rcx, [rsp+288h]; this
0x180004232  mov     edx, 9CDh; void *
0x180004237  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000423d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004243  mov     rcx, [rsp+288h]; this
0x18000424b  mov     edx, 9CDh; void *
0x180004250  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
