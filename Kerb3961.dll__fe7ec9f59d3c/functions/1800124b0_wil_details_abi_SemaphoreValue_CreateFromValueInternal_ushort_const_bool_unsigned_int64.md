# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800124b0`
- end: `0x1800126bd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800109f4`
- `0x18001c7b4`

## callees

- `0x180001d40`
- `0x18000a074`
- `0x1800124b0`
- `0x180014214`
- `0x1800165e8`
- `0x180016d24`
- `0x180017f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012574`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012610`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012574`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012610`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001264d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001264d`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x1800124b0  mov     [rsp+arg_8], rbx
0x1800124b5  mov     [rsp+arg_10], rbp
0x1800124ba  push    rsi
0x1800124bb  push    rdi
0x1800124bc  push    r12
0x1800124be  push    r14
0x1800124c0  push    r15
0x1800124c2  sub     rsp, 250h
0x1800124c9  mov     rax, cs:__security_cookie
0x1800124d0  xor     rax, rsp
0x1800124d3  mov     [rsp+278h+var_38], rax
0x1800124db  mov     rax, 0C000000000000000h
0x1800124e5  mov     rbp, r9
0x1800124e8  mov     r8, rdx
0x1800124eb  mov     rdi, rcx
0x1800124ee  test    rax, r9
0x1800124f1  jnz     loc_1800126A4
0x1800124f7  xor     r12d, r12d
0x1800124fa  lea     rax, [rsp+278h+Name]
0x1800124ff  mov     ecx, 7FFFFFFEh
0x180012504  mov     edx, 104h
0x180012509  lea     esi, [r12+1]
0x18001250e  test    rcx, rcx
0x180012511  jz      short loc_180012531
0x180012513  movzx   r9d, word ptr [r8]
0x180012517  test    r9w, r9w
0x18001251b  jz      short loc_180012531
0x18001251d  mov     [rax], r9w
0x180012521  add     r8, 2
0x180012525  add     rax, 2
0x180012529  sub     rcx, rsi
0x18001252c  sub     rdx, rsi; unsigned __int64
0x18001252f  jnz     short loc_18001250E
0x180012531  test    rdx, rdx
0x180012534  lea     rcx, [rax-2]
0x180012538  lea     r8, aP0; "_p0"
0x18001253f  cmovnz  rcx, rax
0x180012543  mov     [rcx], r12w
0x180012547  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001254c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012551  mov     edx, ebp
0x180012553  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001255b  and     edx, 7FFFFFFFh; lInitialCount
0x180012561  mov     [rsp+278h+dwFlags], r12d; int
0x180012566  mov     r8d, esi
0x180012569  lea     r9, [rsp+278h+Name]; lpName
0x18001256e  cmova   r8d, edx; lMaximumCount
0x180012572  xor     ecx, ecx; lpSemaphoreAttributes
0x180012574  call    cs:__imp_CreateSemaphoreExW
0x18001257a  mov     r15, rax
0x18001257d  test    rax, rax
0x180012580  jnz     short loc_1800125A9
0x180012582  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012587  mov     ebx, eax
0x180012589  test    eax, eax
0x18001258b  jns     short loc_1800125DD
0x18001258d  mov     edx, 8Bh; void *
0x180012592  mov     rcx, [rsp+278h]; this
0x18001259a  mov     r9d, ebx; char *
0x18001259d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125a2  mov     eax, ebx
0x1800125a4  jmp     loc_180012665
0x1800125a9  call    cs:__imp_GetLastError
0x1800125af  mov     rbx, [rdi]
0x1800125b2  test    rbx, rbx
0x1800125b5  jz      short loc_1800125DA
0x1800125b7  call    cs:__imp_GetLastError
0x1800125bd  mov     rcx, rbx; hObject
0x1800125c0  mov     r14d, eax
0x1800125c3  call    cs:__imp_CloseHandle
0x1800125c9  test    eax, eax
0x1800125cb  jz      loc_1800126AA
0x1800125d1  mov     ecx, r14d; dwErrCode
0x1800125d4  call    cs:__imp_SetLastError
0x1800125da  mov     [rdi], r15
0x1800125dd  lea     r8, asc_180025128; "h"
0x1800125e4  shr     rbp, 1Fh
0x1800125e8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800125ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800125f2  test    ebp, ebp
0x1800125f4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800125fc  lea     r9, [rsp+278h+Name]; lpName
0x180012601  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180012606  cmovnz  esi, ebp
0x180012609  mov     edx, ebp; lInitialCount
0x18001260b  mov     r8d, esi; lMaximumCount
0x18001260e  xor     ecx, ecx; lpSemaphoreAttributes
0x180012610  call    cs:__imp_CreateSemaphoreExW
0x180012616  mov     rsi, rax
0x180012619  test    rax, rax
0x18001261c  jnz     short loc_180012633
0x18001261e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012623  mov     ebx, eax
0x180012625  test    eax, eax
0x180012627  jns     short loc_180012663
0x180012629  mov     edx, 90h
0x18001262e  jmp     loc_180012592
0x180012633  call    cs:__imp_GetLastError
0x180012639  mov     rbx, [rdi+8]
0x18001263d  test    rbx, rbx
0x180012640  jz      short loc_18001265F
0x180012642  call    cs:__imp_GetLastError
0x180012648  mov     rcx, rbx; hObject
0x18001264b  mov     ebp, eax
0x18001264d  call    cs:__imp_CloseHandle
0x180012653  test    eax, eax
0x180012655  jz      short loc_180012691
0x180012657  mov     ecx, ebp; dwErrCode
0x180012659  call    cs:__imp_SetLastError
0x18001265f  mov     [rdi+8], rsi
0x180012663  xor     eax, eax
0x180012665  mov     rcx, [rsp+278h+var_38]
0x18001266d  xor     rcx, rsp; StackCookie
0x180012670  call    __security_check_cookie
0x180012675  lea     r11, [rsp+278h+var_28]
0x18001267d  mov     rbx, [r11+38h]
0x180012681  mov     rbp, [r11+40h]
0x180012685  mov     rsp, r11
0x180012688  pop     r15
0x18001268a  pop     r14
0x18001268c  pop     r12
0x18001268e  pop     rdi
0x18001268f  pop     rsi
0x180012690  retn
0x180012691  mov     rcx, [rsp+278h]; this
0x180012699  mov     edx, 0A0Bh; void *
0x18001269e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800126a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800126aa  mov     rcx, [rsp+278h]; this
0x1800126b2  mov     edx, 0A0Bh; void *
0x1800126b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
