# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180014440`
- end: `0x180014776`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `822`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180015db0`

## callees

- `0x180002b50`
- `0x180013850`
- `0x180013f70`
- `0x180013fb0`
- `0x180014440`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800145d0`
- `KERNEL32!GetLastError` at `0x1800145df`
- `KERNEL32!GetLastError` at `0x1800146c6`
- `KERNEL32!GetLastError` at `0x1800146d5`
- `KERNEL32!GetLastError` at `0x1800145d0`
- `KERNEL32!GetLastError` at `0x1800145df`
- `KERNEL32!GetLastError` at `0x1800146c6`
- `KERNEL32!GetLastError` at `0x1800146d5`
- `KERNEL32!SetLastError` at `0x1800145fa`
- `KERNEL32!SetLastError` at `0x1800146ec`
- `KERNEL32!SetLastError` at `0x1800145fa`
- `KERNEL32!SetLastError` at `0x1800146ec`
- `KERNEL32!CreateSemaphoreExW` at `0x180014598`
- `KERNEL32!CreateSemaphoreExW` at `0x180014691`
- `KERNEL32!CreateSemaphoreExW` at `0x180014598`
- `KERNEL32!CreateSemaphoreExW` at `0x180014691`
- `KERNEL32!CloseHandle` at `0x1800145ea`
- `KERNEL32!CloseHandle` at `0x1800146e0`
- `KERNEL32!CloseHandle` at `0x1800145ea`
- `KERNEL32!CloseHandle` at `0x1800146e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v34; // r8d
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
  unsigned int v51; // r8d
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
0x180014440  mov     r11, rsp
0x180014443  push    r13
0x180014445  sub     rsp, 280h
0x18001444c  mov     rax, cs:__security_cookie
0x180014453  xor     rax, rsp
0x180014456  mov     [rsp+288h+var_48], rax
0x18001445e  mov     rax, 0C000000000000000h
0x180014468  mov     r10, r9
0x18001446b  mov     r8, rdx
0x18001446e  mov     r13, rcx
0x180014471  test    rax, r9
0x180014474  jnz     loc_18001475D
0x18001447a  mov     [r11+10h], rbx
0x18001447e  lea     rax, [rsp+288h+Name]
0x180014483  mov     [r11-10h], rbp
0x180014487  lea     rcx, [rsp+288h+Name]
0x18001448c  mov     [r11-20h], rdi
0x180014490  mov     ebx, 104h
0x180014495  mov     [r11-28h], r12
0x180014499  mov     edx, ebx
0x18001449b  mov     [r11-30h], r14
0x18001449f  sub     r8, rax
0x1800144a2  mov     [r11-38h], r15
0x1800144a6  nop     word ptr [rax+rax+00000000h]
0x1800144b0  lea     rax, [rdx+7FFFFEFAh]
0x1800144b7  test    rax, rax
0x1800144ba  jz      short loc_1800144D3
0x1800144bc  movzx   eax, word ptr [r8+rcx]
0x1800144c1  test    ax, ax
0x1800144c4  jz      short loc_1800144D3
0x1800144c6  mov     [rcx], ax
0x1800144c9  add     rcx, 2
0x1800144cd  sub     rdx, 1
0x1800144d1  jnz     short loc_1800144B0
0x1800144d3  test    rdx, rdx
0x1800144d6  lea     rax, [rcx-2]
0x1800144da  cmovnz  rax, rcx
0x1800144de  xor     ebp, ebp
0x1800144e0  mov     rcx, rbx
0x1800144e3  mov     [rax], bp
0x1800144e6  lea     rax, [rsp+288h+Name]
0x1800144eb  nop     dword ptr [rax+rax+00h]
0x1800144f0  cmp     [rax], bp
0x1800144f3  jz      short loc_1800144FF
0x1800144f5  add     rax, 2
0x1800144f9  sub     rcx, 1
0x1800144fd  jnz     short loc_1800144F0
0x1800144ff  mov     rax, rbx
0x180014502  mov     edi, 7FFFFFFEh
0x180014507  sub     rax, rcx
0x18001450a  test    rcx, rcx
0x18001450d  cmovz   rax, rbp
0x180014511  jz      short loc_18001455F
0x180014513  mov     rdx, rbx
0x180014516  lea     rcx, [rsp+288h+Name]
0x18001451b  lea     rcx, [rcx+rax*2]
0x18001451f  sub     rdx, rax
0x180014522  jz      short loc_180014551
0x180014524  lea     r9, aP0; "_p0"
0x18001452b  mov     eax, edi
0x18001452d  sub     r9, rcx
0x180014530  test    rax, rax
0x180014533  jz      short loc_180014551
0x180014535  movzx   r8d, word ptr [r9+rcx]
0x18001453a  test    r8w, r8w
0x18001453e  jz      short loc_180014551
0x180014540  mov     [rcx], r8w
0x180014544  dec     rax
0x180014547  add     rcx, 2
0x18001454b  sub     rdx, 1
0x18001454f  jnz     short loc_180014530
0x180014551  test    rdx, rdx
0x180014554  lea     rax, [rcx-2]
0x180014558  cmovnz  rax, rcx
0x18001455c  mov     [rax], bp
0x18001455f  mov     r15, r10
0x180014562  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001456a  shr     r15, 1Fh
0x18001456e  lea     r9, [rsp+288h+Name]; lpName
0x180014573  and     r10d, 7FFFFFFFh
0x18001457a  mov     [rsp+288h+var_18], rsi
0x180014582  mov     r12d, 1
0x180014588  mov     [rsp+288h+dwFlags], ebp; int
0x18001458c  mov     r8d, r12d
0x18001458f  mov     edx, r10d; lInitialCount
0x180014592  cmova   r8d, r10d; lMaximumCount
0x180014596  xor     ecx, ecx; lpSemaphoreAttributes
0x180014598  call    cs:__imp_CreateSemaphoreExW
0x18001459e  mov     r14, rax
0x1800145a1  test    rax, rax
0x1800145a4  jnz     short loc_1800145D0
0x1800145a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800145ab  mov     esi, eax
0x1800145ad  test    eax, eax
0x1800145af  jns     short loc_180014606
0x1800145b1  lfence
0x1800145b4  mov     rcx, [rsp+288h]; this
0x1800145bc  mov     r9d, eax; char *
0x1800145bf  mov     edx, 88h; void *
0x1800145c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145c9  mov     eax, esi
0x1800145cb  jmp     loc_1800146F8
0x1800145d0  call    cs:__imp_GetLastError
0x1800145d6  mov     rsi, [r13+0]
0x1800145da  test    rsi, rsi
0x1800145dd  jz      short loc_180014602
0x1800145df  call    cs:__imp_GetLastError
0x1800145e5  mov     rcx, rsi; hObject
0x1800145e8  mov     ebp, eax
0x1800145ea  call    cs:__imp_CloseHandle
0x1800145f0  test    eax, eax
0x1800145f2  jz      loc_180014763
0x1800145f8  mov     ecx, ebp; dwErrCode
0x1800145fa  call    cs:__imp_SetLastError
0x180014600  xor     ebp, ebp
0x180014602  mov     [r13+0], r14
0x180014606  mov     rcx, rbx
0x180014609  lea     rax, [rsp+288h+Name]
0x18001460e  xchg    ax, ax
0x180014610  cmp     word ptr [rax], 0
0x180014614  jz      short loc_18001461F
0x180014616  add     rax, 2
0x18001461a  sub     rcx, r12
0x18001461d  jnz     short loc_180014610
0x18001461f  mov     rax, rbx
0x180014622  sub     rax, rcx
0x180014625  test    rcx, rcx
0x180014628  cmovz   rax, rbp
0x18001462c  jz      short loc_180014671
0x18001462e  lea     rcx, [rsp+288h+Name]
0x180014633  lea     rcx, [rcx+rax*2]
0x180014637  sub     rbx, rax
0x18001463a  jz      short loc_180014663
0x18001463c  lea     rdx, asc_180026148; "h"
0x180014643  sub     rdx, rcx
0x180014646  test    rdi, rdi
0x180014649  jz      short loc_180014663
0x18001464b  movzx   eax, word ptr [rdx+rcx]
0x18001464f  test    ax, ax
0x180014652  jz      short loc_180014663
0x180014654  mov     [rcx], ax
0x180014657  dec     rdi
0x18001465a  add     rcx, 2
0x18001465e  sub     rbx, r12
0x180014661  jnz     short loc_180014646
0x180014663  test    rbx, rbx
0x180014666  lea     rax, [rcx-2]
0x18001466a  cmovnz  rax, rcx
0x18001466e  mov     [rax], bp
0x180014671  test    r15d, r15d
0x180014674  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001467c  lea     r9, [rsp+288h+Name]; lpName
0x180014681  mov     [rsp+288h+dwFlags], ebp; int
0x180014685  cmovnz  r12d, r15d
0x180014689  mov     edx, r15d; lInitialCount
0x18001468c  mov     r8d, r12d; lMaximumCount
0x18001468f  xor     ecx, ecx; lpSemaphoreAttributes
0x180014691  call    cs:__imp_CreateSemaphoreExW
0x180014697  mov     rdi, rax
0x18001469a  test    rax, rax
0x18001469d  jnz     short loc_1800146C6
0x18001469f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800146a4  mov     ebx, eax
0x1800146a6  test    eax, eax
0x1800146a8  jns     short loc_1800146F6
0x1800146aa  lfence
0x1800146ad  mov     rcx, [rsp+288h]; this
0x1800146b5  mov     r9d, eax; char *
0x1800146b8  mov     edx, 8Dh; void *
0x1800146bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146c2  mov     eax, ebx
0x1800146c4  jmp     short loc_1800146F8
0x1800146c6  call    cs:__imp_GetLastError
0x1800146cc  mov     rbx, [r13+8]
0x1800146d0  test    rbx, rbx
0x1800146d3  jz      short loc_1800146F2
0x1800146d5  call    cs:__imp_GetLastError
0x1800146db  mov     rcx, rbx; hObject
0x1800146de  mov     esi, eax
0x1800146e0  call    cs:__imp_CloseHandle
0x1800146e6  test    eax, eax
0x1800146e8  jz      short loc_18001474A
0x1800146ea  mov     ecx, esi; dwErrCode
0x1800146ec  call    cs:__imp_SetLastError
0x1800146f2  mov     [r13+8], rdi
0x1800146f6  xor     eax, eax
0x1800146f8  mov     rsi, [rsp+288h+var_18]
0x180014700  mov     r12, [rsp+288h+var_28]
0x180014708  mov     rdi, [rsp+288h+var_20]
0x180014710  mov     r14, [rsp+288h+var_30]
0x180014718  mov     rbp, [rsp+288h+var_10]
0x180014720  mov     rbx, [rsp+288h+arg_8]
0x180014728  mov     r15, [rsp+288h+var_38]
0x180014730  mov     rcx, [rsp+288h+var_48]
0x180014738  xor     rcx, rsp; StackCookie
0x18001473b  call    __security_check_cookie
0x180014740  add     rsp, 280h
0x180014747  pop     r13
0x180014749  retn
0x18001474a  mov     rcx, [rsp+288h]; this
0x180014752  mov     edx, 9CDh; void *
0x180014757  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001475d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180014763  mov     rcx, [rsp+288h]; this
0x18001476b  mov     edx, 9CDh; void *
0x180014770  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
