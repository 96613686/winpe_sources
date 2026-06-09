# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007084`
- end: `0x180007291`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800068a8`
- `0x180006c4c`

## callees

- `0x180002300`
- `0x180007084`
- `0x180008930`
- `0x18000bfb4`
- `0x18000d1e0`
- `0x18000e804`
- `0x18000e814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007148`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071e4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007148`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000717d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000718b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000717d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000718b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007221`

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
0x180007084  mov     [rsp+arg_8], rbx
0x180007089  mov     [rsp+arg_10], rbp
0x18000708e  push    rsi
0x18000708f  push    rdi
0x180007090  push    r12
0x180007092  push    r14
0x180007094  push    r15
0x180007096  sub     rsp, 250h
0x18000709d  mov     rax, cs:__security_cookie
0x1800070a4  xor     rax, rsp
0x1800070a7  mov     [rsp+278h+var_38], rax
0x1800070af  mov     rax, 0C000000000000000h
0x1800070b9  mov     rbp, r9
0x1800070bc  mov     r8, rdx
0x1800070bf  mov     rdi, rcx
0x1800070c2  test    rax, r9
0x1800070c5  jnz     loc_180007278
0x1800070cb  xor     r12d, r12d
0x1800070ce  lea     rax, [rsp+278h+Name]
0x1800070d3  mov     ecx, 7FFFFFFEh
0x1800070d8  mov     edx, 104h
0x1800070dd  lea     esi, [r12+1]
0x1800070e2  test    rcx, rcx
0x1800070e5  jz      short loc_180007105
0x1800070e7  movzx   r9d, word ptr [r8]
0x1800070eb  test    r9w, r9w
0x1800070ef  jz      short loc_180007105
0x1800070f1  mov     [rax], r9w
0x1800070f5  add     r8, 2
0x1800070f9  add     rax, 2
0x1800070fd  sub     rcx, rsi
0x180007100  sub     rdx, rsi; unsigned __int64
0x180007103  jnz     short loc_1800070E2
0x180007105  test    rdx, rdx
0x180007108  lea     rcx, [rax-2]
0x18000710c  lea     r8, aP0; "_p0"
0x180007113  cmovnz  rcx, rax
0x180007117  mov     [rcx], r12w
0x18000711b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007120  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007125  mov     edx, ebp
0x180007127  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000712f  and     edx, 7FFFFFFFh; lInitialCount
0x180007135  mov     [rsp+278h+dwFlags], r12d; int
0x18000713a  mov     r8d, esi
0x18000713d  lea     r9, [rsp+278h+Name]; lpName
0x180007142  cmova   r8d, edx; lMaximumCount
0x180007146  xor     ecx, ecx; lpSemaphoreAttributes
0x180007148  call    cs:__imp_CreateSemaphoreExW
0x18000714e  mov     r15, rax
0x180007151  test    rax, rax
0x180007154  jnz     short loc_18000717D
0x180007156  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000715b  mov     ebx, eax
0x18000715d  test    eax, eax
0x18000715f  jns     short loc_1800071B1
0x180007161  mov     edx, 8Bh; void *
0x180007166  mov     rcx, [rsp+278h]; this
0x18000716e  mov     r9d, ebx; char *
0x180007171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007176  mov     eax, ebx
0x180007178  jmp     loc_180007239
0x18000717d  call    cs:__imp_GetLastError
0x180007183  mov     rbx, [rdi]
0x180007186  test    rbx, rbx
0x180007189  jz      short loc_1800071AE
0x18000718b  call    cs:__imp_GetLastError
0x180007191  mov     rcx, rbx; hObject
0x180007194  mov     r14d, eax
0x180007197  call    cs:__imp_CloseHandle
0x18000719d  test    eax, eax
0x18000719f  jz      loc_18000727E
0x1800071a5  mov     ecx, r14d; dwErrCode
0x1800071a8  call    cs:__imp_SetLastError
0x1800071ae  mov     [rdi], r15
0x1800071b1  lea     r8, asc_180014240; "h"
0x1800071b8  shr     rbp, 1Fh
0x1800071bc  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800071c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071c6  test    ebp, ebp
0x1800071c8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800071d0  lea     r9, [rsp+278h+Name]; lpName
0x1800071d5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800071da  cmovnz  esi, ebp
0x1800071dd  mov     edx, ebp; lInitialCount
0x1800071df  mov     r8d, esi; lMaximumCount
0x1800071e2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800071e4  call    cs:__imp_CreateSemaphoreExW
0x1800071ea  mov     rsi, rax
0x1800071ed  test    rax, rax
0x1800071f0  jnz     short loc_180007207
0x1800071f2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800071f7  mov     ebx, eax
0x1800071f9  test    eax, eax
0x1800071fb  jns     short loc_180007237
0x1800071fd  mov     edx, 90h
0x180007202  jmp     loc_180007166
0x180007207  call    cs:__imp_GetLastError
0x18000720d  mov     rbx, [rdi+8]
0x180007211  test    rbx, rbx
0x180007214  jz      short loc_180007233
0x180007216  call    cs:__imp_GetLastError
0x18000721c  mov     rcx, rbx; hObject
0x18000721f  mov     ebp, eax
0x180007221  call    cs:__imp_CloseHandle
0x180007227  test    eax, eax
0x180007229  jz      short loc_180007265
0x18000722b  mov     ecx, ebp; dwErrCode
0x18000722d  call    cs:__imp_SetLastError
0x180007233  mov     [rdi+8], rsi
0x180007237  xor     eax, eax
0x180007239  mov     rcx, [rsp+278h+var_38]
0x180007241  xor     rcx, rsp; StackCookie
0x180007244  call    __security_check_cookie
0x180007249  lea     r11, [rsp+278h+var_28]
0x180007251  mov     rbx, [r11+38h]
0x180007255  mov     rbp, [r11+40h]
0x180007259  mov     rsp, r11
0x18000725c  pop     r15
0x18000725e  pop     r14
0x180007260  pop     r12
0x180007262  pop     rdi
0x180007263  pop     rsi
0x180007264  retn
0x180007265  mov     rcx, [rsp+278h]; this
0x18000726d  mov     edx, 0A0Bh; void *
0x180007272  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007278  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000727e  mov     rcx, [rsp+278h]; this
0x180007286  mov     edx, 0A0Bh; void *
0x18000728b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
