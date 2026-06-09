# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000568c`
- end: `0x1800058c4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004e58`
- `0x18000522c`

## callees

- `0x180002350`
- `0x18000568c`
- `0x180006628`
- `0x180008c24`
- `0x180009668`
- `0x18000a48c`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005750`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800057f3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005750`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800057f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800057b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800057b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000578c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000579a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000583b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000578c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000579a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000583b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005846`

## string_xrefs

- `0x180005892`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800058b2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000568c  mov     [rsp+arg_8], rbx
0x180005691  mov     [rsp+arg_10], rbp
0x180005696  push    rsi
0x180005697  push    rdi
0x180005698  push    r12
0x18000569a  push    r14
0x18000569c  push    r15
0x18000569e  sub     rsp, 250h
0x1800056a5  mov     rax, cs:__security_cookie
0x1800056ac  xor     rax, rsp
0x1800056af  mov     [rsp+278h+var_38], rax
0x1800056b7  mov     rax, 0C000000000000000h
0x1800056c1  mov     rbp, r9
0x1800056c4  mov     r8, rdx
0x1800056c7  mov     rbx, rcx
0x1800056ca  test    rax, r9
0x1800056cd  jnz     loc_1800058A4
0x1800056d3  xor     r12d, r12d
0x1800056d6  lea     rax, [rsp+278h+Name]
0x1800056db  mov     ecx, 7FFFFFFEh
0x1800056e0  mov     edx, 104h
0x1800056e5  lea     esi, [r12+1]
0x1800056ea  test    rcx, rcx
0x1800056ed  jz      short loc_18000570D
0x1800056ef  movzx   r9d, word ptr [r8]
0x1800056f3  test    r9w, r9w
0x1800056f7  jz      short loc_18000570D
0x1800056f9  mov     [rax], r9w
0x1800056fd  add     r8, 2
0x180005701  add     rax, 2
0x180005705  sub     rcx, rsi
0x180005708  sub     rdx, rsi; unsigned __int64
0x18000570b  jnz     short loc_1800056EA
0x18000570d  test    rdx, rdx
0x180005710  lea     rcx, [rax-2]
0x180005714  lea     r8, aP0; "_p0"
0x18000571b  cmovnz  rcx, rax
0x18000571f  mov     [rcx], r12w
0x180005723  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005728  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000572d  mov     edx, ebp
0x18000572f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005737  and     edx, 7FFFFFFFh; lInitialCount
0x18000573d  mov     [rsp+278h+dwFlags], r12d; int
0x180005742  mov     r8d, esi
0x180005745  lea     r9, [rsp+278h+Name]; lpName
0x18000574a  cmova   r8d, edx; lMaximumCount
0x18000574e  xor     ecx, ecx; lpSemaphoreAttributes
0x180005750  call    cs:__imp_CreateSemaphoreExW
0x180005756  mov     r15, rax
0x180005759  test    rax, rax
0x18000575c  jnz     short loc_18000578C
0x18000575e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005763  mov     edi, eax
0x180005765  test    eax, eax
0x180005767  jns     short loc_1800057C0
0x180005769  mov     rcx, [rsp+278h]; this
0x180005771  lea     r8, aWil; "wil"
0x180005778  mov     r9d, eax; char *
0x18000577b  mov     edx, 8Bh; void *
0x180005780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005785  mov     eax, edi
0x180005787  jmp     loc_18000585E
0x18000578c  call    cs:__imp_GetLastError
0x180005792  mov     rdi, [rbx]
0x180005795  test    rdi, rdi
0x180005798  jz      short loc_1800057BD
0x18000579a  call    cs:__imp_GetLastError
0x1800057a0  mov     rcx, rdi; hObject
0x1800057a3  mov     r14d, eax
0x1800057a6  call    cs:__imp_CloseHandle
0x1800057ac  test    eax, eax
0x1800057ae  jz      loc_1800058AA
0x1800057b4  mov     ecx, r14d; dwErrCode
0x1800057b7  call    cs:__imp_SetLastError
0x1800057bd  mov     [rbx], r15
0x1800057c0  lea     r8, asc_180032668; "h"
0x1800057c7  shr     rbp, 1Fh
0x1800057cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800057d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800057d5  test    ebp, ebp
0x1800057d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800057df  lea     r9, [rsp+278h+Name]; lpName
0x1800057e4  mov     [rsp+278h+dwFlags], r12d; int
0x1800057e9  cmovnz  esi, ebp
0x1800057ec  mov     edx, ebp; lInitialCount
0x1800057ee  mov     r8d, esi; lMaximumCount
0x1800057f1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800057f3  call    cs:__imp_CreateSemaphoreExW
0x1800057f9  mov     rsi, rax
0x1800057fc  test    rax, rax
0x1800057ff  jnz     short loc_18000582C
0x180005801  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005806  mov     ebx, eax
0x180005808  test    eax, eax
0x18000580a  jns     short loc_18000585C
0x18000580c  mov     rcx, [rsp+278h]; this
0x180005814  lea     r8, aWil; "wil"
0x18000581b  mov     r9d, eax; char *
0x18000581e  mov     edx, 90h; void *
0x180005823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005828  mov     eax, ebx
0x18000582a  jmp     short loc_18000585E
0x18000582c  call    cs:__imp_GetLastError
0x180005832  mov     rdi, [rbx+8]
0x180005836  test    rdi, rdi
0x180005839  jz      short loc_180005858
0x18000583b  call    cs:__imp_GetLastError
0x180005841  mov     rcx, rdi; hObject
0x180005844  mov     ebp, eax
0x180005846  call    cs:__imp_CloseHandle
0x18000584c  test    eax, eax
0x18000584e  jz      short loc_18000588A
0x180005850  mov     ecx, ebp; dwErrCode
0x180005852  call    cs:__imp_SetLastError
0x180005858  mov     [rbx+8], rsi
0x18000585c  xor     eax, eax
0x18000585e  mov     rcx, [rsp+278h+var_38]
0x180005866  xor     rcx, rsp; StackCookie
0x180005869  call    __security_check_cookie
0x18000586e  lea     r11, [rsp+278h+var_28]
0x180005876  mov     rbx, [r11+38h]
0x18000587a  mov     rbp, [r11+40h]
0x18000587e  mov     rsp, r11
0x180005881  pop     r15
0x180005883  pop     r14
0x180005885  pop     r12
0x180005887  pop     rdi
0x180005888  pop     rsi
0x180005889  retn
0x18000588a  mov     rcx, [rsp+278h]; this
0x180005892  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005899  mov     edx, 0A0Bh; void *
0x18000589e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800058aa  mov     rcx, [rsp+278h]; this
0x1800058b2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800058b9  mov     edx, 0A0Bh; void *
0x1800058be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
