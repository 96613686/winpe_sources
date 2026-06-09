# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007620`
- end: `0x18000784a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800066b8`

## callees

- `0x180004410`
- `0x180007620`
- `0x1800083cc`
- `0x18000a814`
- `0x18000b1a4`
- `0x18000baf4`
- `0x18000bb04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800076e4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007787`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800076e4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000774b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800077e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000774b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800077e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000773a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000773a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077da`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x180007620  mov     [rsp+arg_8], rbx
0x180007625  mov     [rsp+arg_10], rbp
0x18000762a  push    rsi
0x18000762b  push    rdi
0x18000762c  push    r12
0x18000762e  push    r14
0x180007630  push    r15
0x180007632  sub     rsp, 250h
0x180007639  mov     rax, cs:__security_cookie
0x180007640  xor     rax, rsp
0x180007643  mov     [rsp+278h+var_38], rax
0x18000764b  mov     rax, 0C000000000000000h
0x180007655  mov     rbp, r9
0x180007658  mov     r8, rdx
0x18000765b  mov     rbx, rcx
0x18000765e  test    rax, r9
0x180007661  jnz     loc_180007831
0x180007667  xor     r12d, r12d
0x18000766a  lea     rax, [rsp+278h+Name]
0x18000766f  mov     ecx, 7FFFFFFEh
0x180007674  mov     edx, 104h
0x180007679  lea     esi, [r12+1]
0x18000767e  test    rcx, rcx
0x180007681  jz      short loc_1800076A1
0x180007683  movzx   r9d, word ptr [r8]
0x180007687  test    r9w, r9w
0x18000768b  jz      short loc_1800076A1
0x18000768d  mov     [rax], r9w
0x180007691  add     r8, 2
0x180007695  add     rax, 2
0x180007699  sub     rcx, rsi
0x18000769c  sub     rdx, rsi; unsigned __int64
0x18000769f  jnz     short loc_18000767E
0x1800076a1  test    rdx, rdx
0x1800076a4  lea     rcx, [rax-2]
0x1800076a8  lea     r8, aP0; "_p0"
0x1800076af  cmovnz  rcx, rax
0x1800076b3  mov     [rcx], r12w
0x1800076b7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800076bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800076c1  mov     edx, ebp
0x1800076c3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800076cb  and     edx, 7FFFFFFFh; lInitialCount
0x1800076d1  mov     [rsp+278h+dwFlags], r12d; int
0x1800076d6  mov     r8d, esi
0x1800076d9  lea     r9, [rsp+278h+Name]; lpName
0x1800076de  cmova   r8d, edx; lMaximumCount
0x1800076e2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800076e4  call    cs:__imp_CreateSemaphoreExW
0x1800076ea  mov     r15, rax
0x1800076ed  test    rax, rax
0x1800076f0  jnz     short loc_180007720
0x1800076f2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800076f7  mov     edi, eax
0x1800076f9  test    eax, eax
0x1800076fb  jns     short loc_180007754
0x1800076fd  mov     rcx, [rsp+278h]; this
0x180007705  lea     r8, aWil; "wil"
0x18000770c  mov     r9d, eax; char *
0x18000770f  mov     edx, 8Bh; void *
0x180007714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007719  mov     eax, edi
0x18000771b  jmp     loc_1800077F2
0x180007720  call    cs:__imp_GetLastError
0x180007726  mov     rdi, [rbx]
0x180007729  test    rdi, rdi
0x18000772c  jz      short loc_180007751
0x18000772e  call    cs:__imp_GetLastError
0x180007734  mov     rcx, rdi; hObject
0x180007737  mov     r14d, eax
0x18000773a  call    cs:__imp_CloseHandle
0x180007740  test    eax, eax
0x180007742  jz      loc_180007837
0x180007748  mov     ecx, r14d; dwErrCode
0x18000774b  call    cs:__imp_SetLastError
0x180007751  mov     [rbx], r15
0x180007754  lea     r8, asc_1800610F0; "h"
0x18000775b  shr     rbp, 1Fh
0x18000775f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007764  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007769  test    ebp, ebp
0x18000776b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007773  lea     r9, [rsp+278h+Name]; lpName
0x180007778  mov     [rsp+278h+dwFlags], r12d; int
0x18000777d  cmovnz  esi, ebp
0x180007780  mov     edx, ebp; lInitialCount
0x180007782  mov     r8d, esi; lMaximumCount
0x180007785  xor     ecx, ecx; lpSemaphoreAttributes
0x180007787  call    cs:__imp_CreateSemaphoreExW
0x18000778d  mov     rsi, rax
0x180007790  test    rax, rax
0x180007793  jnz     short loc_1800077C0
0x180007795  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000779a  mov     ebx, eax
0x18000779c  test    eax, eax
0x18000779e  jns     short loc_1800077F0
0x1800077a0  mov     rcx, [rsp+278h]; this
0x1800077a8  lea     r8, aWil; "wil"
0x1800077af  mov     r9d, eax; char *
0x1800077b2  mov     edx, 90h; void *
0x1800077b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077bc  mov     eax, ebx
0x1800077be  jmp     short loc_1800077F2
0x1800077c0  call    cs:__imp_GetLastError
0x1800077c6  mov     rdi, [rbx+8]
0x1800077ca  test    rdi, rdi
0x1800077cd  jz      short loc_1800077EC
0x1800077cf  call    cs:__imp_GetLastError
0x1800077d5  mov     rcx, rdi; hObject
0x1800077d8  mov     ebp, eax
0x1800077da  call    cs:__imp_CloseHandle
0x1800077e0  test    eax, eax
0x1800077e2  jz      short loc_18000781E
0x1800077e4  mov     ecx, ebp; dwErrCode
0x1800077e6  call    cs:__imp_SetLastError
0x1800077ec  mov     [rbx+8], rsi
0x1800077f0  xor     eax, eax
0x1800077f2  mov     rcx, [rsp+278h+var_38]
0x1800077fa  xor     rcx, rsp; StackCookie
0x1800077fd  call    __security_check_cookie
0x180007802  lea     r11, [rsp+278h+var_28]
0x18000780a  mov     rbx, [r11+38h]
0x18000780e  mov     rbp, [r11+40h]
0x180007812  mov     rsp, r11
0x180007815  pop     r15
0x180007817  pop     r14
0x180007819  pop     r12
0x18000781b  pop     rdi
0x18000781c  pop     rsi
0x18000781d  retn
0x18000781e  mov     rcx, [rsp+278h]; this
0x180007826  mov     edx, 0A0Bh; void *
0x18000782b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007831  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007837  mov     rcx, [rsp+278h]; this
0x18000783f  mov     edx, 0A0Bh; void *
0x180007844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
