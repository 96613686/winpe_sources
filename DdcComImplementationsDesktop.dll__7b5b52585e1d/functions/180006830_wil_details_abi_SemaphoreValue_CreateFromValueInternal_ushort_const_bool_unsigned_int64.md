# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006830`
- end: `0x180006a3d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800060bc`
- `0x180006460`

## callees

- `0x1800016b0`
- `0x180006830`
- `0x1800075b8`
- `0x1800094d4`
- `0x180009f18`
- `0x18000aafc`
- `0x18000ab0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069d9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800068f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006990`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800068f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069cd`

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
0x180006830  mov     [rsp+arg_8], rbx
0x180006835  mov     [rsp+arg_10], rbp
0x18000683a  push    rsi
0x18000683b  push    rdi
0x18000683c  push    r12
0x18000683e  push    r14
0x180006840  push    r15
0x180006842  sub     rsp, 250h
0x180006849  mov     rax, cs:__security_cookie
0x180006850  xor     rax, rsp
0x180006853  mov     [rsp+278h+var_38], rax
0x18000685b  mov     rax, 0C000000000000000h
0x180006865  mov     rbp, r9
0x180006868  mov     r8, rdx
0x18000686b  mov     rdi, rcx
0x18000686e  test    rax, r9
0x180006871  jnz     loc_180006A24
0x180006877  xor     r12d, r12d
0x18000687a  lea     rax, [rsp+278h+Name]
0x18000687f  mov     ecx, 7FFFFFFEh
0x180006884  mov     edx, 104h
0x180006889  lea     esi, [r12+1]
0x18000688e  test    rcx, rcx
0x180006891  jz      short loc_1800068B1
0x180006893  movzx   r9d, word ptr [r8]
0x180006897  test    r9w, r9w
0x18000689b  jz      short loc_1800068B1
0x18000689d  mov     [rax], r9w
0x1800068a1  add     r8, 2
0x1800068a5  add     rax, 2
0x1800068a9  sub     rcx, rsi
0x1800068ac  sub     rdx, rsi; unsigned __int64
0x1800068af  jnz     short loc_18000688E
0x1800068b1  test    rdx, rdx
0x1800068b4  lea     rcx, [rax-2]
0x1800068b8  lea     r8, aP0; "_p0"
0x1800068bf  cmovnz  rcx, rax
0x1800068c3  mov     [rcx], r12w
0x1800068c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800068cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068d1  mov     edx, ebp
0x1800068d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800068db  and     edx, 7FFFFFFFh; lInitialCount
0x1800068e1  mov     [rsp+278h+dwFlags], r12d; int
0x1800068e6  mov     r8d, esi
0x1800068e9  lea     r9, [rsp+278h+Name]; lpName
0x1800068ee  cmova   r8d, edx; lMaximumCount
0x1800068f2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800068f4  call    cs:__imp_CreateSemaphoreExW
0x1800068fa  mov     r15, rax
0x1800068fd  test    rax, rax
0x180006900  jnz     short loc_180006929
0x180006902  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006907  mov     ebx, eax
0x180006909  test    eax, eax
0x18000690b  jns     short loc_18000695D
0x18000690d  mov     edx, 8Bh; void *
0x180006912  mov     rcx, [rsp+278h]; this
0x18000691a  mov     r9d, ebx; char *
0x18000691d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006922  mov     eax, ebx
0x180006924  jmp     loc_1800069E5
0x180006929  call    cs:__imp_GetLastError
0x18000692f  mov     rbx, [rdi]
0x180006932  test    rbx, rbx
0x180006935  jz      short loc_18000695A
0x180006937  call    cs:__imp_GetLastError
0x18000693d  mov     rcx, rbx; hObject
0x180006940  mov     r14d, eax
0x180006943  call    cs:__imp_CloseHandle
0x180006949  test    eax, eax
0x18000694b  jz      loc_180006A2A
0x180006951  mov     ecx, r14d; dwErrCode
0x180006954  call    cs:__imp_SetLastError
0x18000695a  mov     [rdi], r15
0x18000695d  lea     r8, asc_18000F4E8; "h"
0x180006964  shr     rbp, 1Fh
0x180006968  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000696d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006972  test    ebp, ebp
0x180006974  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000697c  lea     r9, [rsp+278h+Name]; lpName
0x180006981  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180006986  cmovnz  esi, ebp
0x180006989  mov     edx, ebp; lInitialCount
0x18000698b  mov     r8d, esi; lMaximumCount
0x18000698e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006990  call    cs:__imp_CreateSemaphoreExW
0x180006996  mov     rsi, rax
0x180006999  test    rax, rax
0x18000699c  jnz     short loc_1800069B3
0x18000699e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800069a3  mov     ebx, eax
0x1800069a5  test    eax, eax
0x1800069a7  jns     short loc_1800069E3
0x1800069a9  mov     edx, 90h
0x1800069ae  jmp     loc_180006912
0x1800069b3  call    cs:__imp_GetLastError
0x1800069b9  mov     rbx, [rdi+8]
0x1800069bd  test    rbx, rbx
0x1800069c0  jz      short loc_1800069DF
0x1800069c2  call    cs:__imp_GetLastError
0x1800069c8  mov     rcx, rbx; hObject
0x1800069cb  mov     ebp, eax
0x1800069cd  call    cs:__imp_CloseHandle
0x1800069d3  test    eax, eax
0x1800069d5  jz      short loc_180006A11
0x1800069d7  mov     ecx, ebp; dwErrCode
0x1800069d9  call    cs:__imp_SetLastError
0x1800069df  mov     [rdi+8], rsi
0x1800069e3  xor     eax, eax
0x1800069e5  mov     rcx, [rsp+278h+var_38]
0x1800069ed  xor     rcx, rsp; StackCookie
0x1800069f0  call    __security_check_cookie
0x1800069f5  lea     r11, [rsp+278h+var_28]
0x1800069fd  mov     rbx, [r11+38h]
0x180006a01  mov     rbp, [r11+40h]
0x180006a05  mov     rsp, r11
0x180006a08  pop     r15
0x180006a0a  pop     r14
0x180006a0c  pop     r12
0x180006a0e  pop     rdi
0x180006a0f  pop     rsi
0x180006a10  retn
0x180006a11  mov     rcx, [rsp+278h]; this
0x180006a19  mov     edx, 0A0Bh; void *
0x180006a1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006a2a  mov     rcx, [rsp+278h]; this
0x180006a32  mov     edx, 0A0Bh; void *
0x180006a37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
