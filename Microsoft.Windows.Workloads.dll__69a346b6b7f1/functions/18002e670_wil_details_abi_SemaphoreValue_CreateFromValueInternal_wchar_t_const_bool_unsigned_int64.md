# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18002e670`
- end: `0x18002e9b7`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `839`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180030560`

## callees

- `0x180002e40`
- `0x180010a50`
- `0x18002d300`
- `0x18002e1e0`
- `0x18002e670`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e831`
- `KERNEL32!SetLastError` at `0x18002e92d`
- `KERNEL32!SetLastError` at `0x18002e831`
- `KERNEL32!SetLastError` at `0x18002e92d`
- `KERNEL32!GetLastError` at `0x18002e807`
- `KERNEL32!GetLastError` at `0x18002e816`
- `KERNEL32!GetLastError` at `0x18002e907`
- `KERNEL32!GetLastError` at `0x18002e916`
- `KERNEL32!GetLastError` at `0x18002e807`
- `KERNEL32!GetLastError` at `0x18002e816`
- `KERNEL32!GetLastError` at `0x18002e907`
- `KERNEL32!GetLastError` at `0x18002e916`
- `KERNEL32!CloseHandle` at `0x18002e821`
- `KERNEL32!CloseHandle` at `0x18002e921`
- `KERNEL32!CloseHandle` at `0x18002e821`
- `KERNEL32!CloseHandle` at `0x18002e921`
- `KERNEL32!CreateSemaphoreExW` at `0x18002e7c8`
- `KERNEL32!CreateSemaphoreExW` at `0x18002e8cb`
- `KERNEL32!CreateSemaphoreExW` at `0x18002e7c8`
- `KERNEL32!CreateSemaphoreExW` at `0x18002e8cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned int v29; // esi
  void *v31; // rsi
  DWORD LastError; // ebp
  unsigned int v33; // r8d
  const char *v34; // r9
  __int64 v35; // rcx
  WCHAR *v36; // rax
  __int64 v37; // rax
  WCHAR *v38; // rcx
  __int64 v39; // rbx
  char *v40; // rdx
  WCHAR v41; // ax
  WCHAR *v42; // rax
  wil::details *v43; // rcx
  HANDLE v44; // rdi
  int v45; // eax
  unsigned int v46; // ebx
  void *v47; // rbx
  DWORD v48; // esi
  unsigned int v49; // r8d
  const char *v50; // r9
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
    v31 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v31) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v33, v34);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    v29 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v29;
    }
  }
  v35 = 260;
  v36 = Name;
  do
  {
    if ( !*v36 )
      break;
    ++v36;
    --v35;
  }
  while ( v35 );
  v37 = 260 - v35;
  if ( v35 )
  {
    v38 = &Name[v37];
    v39 = 260 - v37;
    if ( 260 != v37 )
    {
      v40 = (char *)((char *)L"h" - (char *)v38);
      do
      {
        if ( !v14 )
          break;
        v41 = *(WCHAR *)((char *)v38 + (_QWORD)v40);
        if ( !v41 )
          break;
        *v38 = v41;
        --v14;
        ++v38;
        --v39;
      }
      while ( v39 );
    }
    v42 = v38 - 1;
    if ( v39 )
      v42 = v38;
    *v42 = 0;
  }
  if ( (_DWORD)v22 )
    v24 = v22;
  v44 = CreateSemaphoreExW(0, v22, v24, Name, 0, 0x1F0003u);
  if ( v44 )
  {
    GetLastError();
    v47 = (void *)*((_QWORD *)this + 1);
    if ( v47 )
    {
      v48 = GetLastError();
      if ( !CloseHandle(v47) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v49, v50);
      SetLastError(v48);
    }
    *((_QWORD *)this + 1) = v44;
  }
  else
  {
    v45 = wil::details::GetLastErrorFailHr(v43);
    v46 = v45;
    if ( v45 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"wil",
        (const char *)(unsigned int)v45,
        dwFlagsa);
      return v46;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002e670  mov     r11, rsp
0x18002e673  push    r13
0x18002e675  sub     rsp, 280h
0x18002e67c  mov     rax, cs:__security_cookie
0x18002e683  xor     rax, rsp
0x18002e686  mov     [rsp+288h+var_48], rax
0x18002e68e  mov     rax, 0C000000000000000h
0x18002e698  mov     r10, r9
0x18002e69b  mov     r8, rdx
0x18002e69e  mov     r13, rcx
0x18002e6a1  test    rax, r9
0x18002e6a4  jnz     loc_18002E99E
0x18002e6aa  mov     [r11+10h], rbx
0x18002e6ae  lea     rax, [rsp+288h+Name]
0x18002e6b3  mov     [r11-10h], rbp
0x18002e6b7  lea     rcx, [rsp+288h+Name]
0x18002e6bc  mov     [r11-20h], rdi
0x18002e6c0  mov     ebx, 104h
0x18002e6c5  mov     [r11-28h], r12
0x18002e6c9  mov     edx, ebx
0x18002e6cb  mov     [r11-30h], r14
0x18002e6cf  sub     r8, rax
0x18002e6d2  mov     [r11-38h], r15
0x18002e6d6  nop     word ptr [rax+rax+00000000h]
0x18002e6e0  lea     rax, [rdx+7FFFFEFAh]
0x18002e6e7  test    rax, rax
0x18002e6ea  jz      short loc_18002E703
0x18002e6ec  movzx   eax, word ptr [r8+rcx]
0x18002e6f1  test    ax, ax
0x18002e6f4  jz      short loc_18002E703
0x18002e6f6  mov     [rcx], ax
0x18002e6f9  add     rcx, 2
0x18002e6fd  sub     rdx, 1
0x18002e701  jnz     short loc_18002E6E0
0x18002e703  test    rdx, rdx
0x18002e706  lea     rax, [rcx-2]
0x18002e70a  cmovnz  rax, rcx
0x18002e70e  xor     ebp, ebp
0x18002e710  mov     rcx, rbx
0x18002e713  mov     [rax], bp
0x18002e716  lea     rax, [rsp+288h+Name]
0x18002e71b  nop     dword ptr [rax+rax+00h]
0x18002e720  cmp     [rax], bp
0x18002e723  jz      short loc_18002E72F
0x18002e725  add     rax, 2
0x18002e729  sub     rcx, 1
0x18002e72d  jnz     short loc_18002E720
0x18002e72f  mov     rax, rbx
0x18002e732  mov     edi, 7FFFFFFEh
0x18002e737  sub     rax, rcx
0x18002e73a  test    rcx, rcx
0x18002e73d  cmovz   rax, rbp
0x18002e741  jz      short loc_18002E78F
0x18002e743  mov     rdx, rbx
0x18002e746  lea     rcx, [rsp+288h+Name]
0x18002e74b  lea     rcx, [rcx+rax*2]
0x18002e74f  sub     rdx, rax
0x18002e752  jz      short loc_18002E781
0x18002e754  lea     r9, aP0; "_p0"
0x18002e75b  mov     eax, edi
0x18002e75d  sub     r9, rcx
0x18002e760  test    rax, rax
0x18002e763  jz      short loc_18002E781
0x18002e765  movzx   r8d, word ptr [r9+rcx]
0x18002e76a  test    r8w, r8w
0x18002e76e  jz      short loc_18002E781
0x18002e770  mov     [rcx], r8w
0x18002e774  dec     rax
0x18002e777  add     rcx, 2
0x18002e77b  sub     rdx, 1
0x18002e77f  jnz     short loc_18002E760
0x18002e781  test    rdx, rdx
0x18002e784  lea     rax, [rcx-2]
0x18002e788  cmovnz  rax, rcx
0x18002e78c  mov     [rax], bp
0x18002e78f  mov     r15, r10
0x18002e792  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002e79a  shr     r15, 1Fh
0x18002e79e  lea     r9, [rsp+288h+Name]; lpName
0x18002e7a3  and     r10d, 7FFFFFFFh
0x18002e7aa  mov     [rsp+288h+var_18], rsi
0x18002e7b2  mov     r12d, 1
0x18002e7b8  mov     [rsp+288h+dwFlags], ebp; int
0x18002e7bc  mov     r8d, r12d
0x18002e7bf  mov     edx, r10d; lInitialCount
0x18002e7c2  cmova   r8d, r10d; lMaximumCount
0x18002e7c6  xor     ecx, ecx; lpSemaphoreAttributes
0x18002e7c8  call    cs:__imp_CreateSemaphoreExW
0x18002e7ce  mov     r14, rax
0x18002e7d1  test    rax, rax
0x18002e7d4  jnz     short loc_18002E807
0x18002e7d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002e7db  mov     esi, eax
0x18002e7dd  test    eax, eax
0x18002e7df  jns     short loc_18002E83D
0x18002e7e1  lfence
0x18002e7e4  mov     rcx, [rsp+288h]; this
0x18002e7ec  lea     r8, aWil; "wil"
0x18002e7f3  mov     r9d, eax; char *
0x18002e7f6  mov     edx, 88h; void *
0x18002e7fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e800  mov     eax, esi
0x18002e802  jmp     loc_18002E939
0x18002e807  call    cs:__imp_GetLastError
0x18002e80d  mov     rsi, [r13+0]
0x18002e811  test    rsi, rsi
0x18002e814  jz      short loc_18002E839
0x18002e816  call    cs:__imp_GetLastError
0x18002e81c  mov     rcx, rsi; hObject
0x18002e81f  mov     ebp, eax
0x18002e821  call    cs:__imp_CloseHandle
0x18002e827  test    eax, eax
0x18002e829  jz      loc_18002E9A4
0x18002e82f  mov     ecx, ebp; dwErrCode
0x18002e831  call    cs:__imp_SetLastError
0x18002e837  xor     ebp, ebp
0x18002e839  mov     [r13+0], r14
0x18002e83d  mov     rcx, rbx
0x18002e840  lea     rax, [rsp+288h+Name]
0x18002e845  cmp     word ptr [rax], 0
0x18002e849  jz      short loc_18002E854
0x18002e84b  add     rax, 2
0x18002e84f  sub     rcx, r12
0x18002e852  jnz     short loc_18002E845
0x18002e854  mov     rax, rbx
0x18002e857  sub     rax, rcx
0x18002e85a  test    rcx, rcx
0x18002e85d  cmovz   rax, rbp
0x18002e861  jz      short loc_18002E8AB
0x18002e863  lea     rcx, [rsp+288h+Name]
0x18002e868  lea     rcx, [rcx+rax*2]
0x18002e86c  sub     rbx, rax
0x18002e86f  jz      short loc_18002E89D
0x18002e871  lea     rdx, asc_18004BBE8; "h"
0x18002e878  sub     rdx, rcx
0x18002e87b  nop     dword ptr [rax+rax+00h]
0x18002e880  test    rdi, rdi
0x18002e883  jz      short loc_18002E89D
0x18002e885  movzx   eax, word ptr [rdx+rcx]
0x18002e889  test    ax, ax
0x18002e88c  jz      short loc_18002E89D
0x18002e88e  mov     [rcx], ax
0x18002e891  dec     rdi
0x18002e894  add     rcx, 2
0x18002e898  sub     rbx, r12
0x18002e89b  jnz     short loc_18002E880
0x18002e89d  test    rbx, rbx
0x18002e8a0  lea     rax, [rcx-2]
0x18002e8a4  cmovnz  rax, rcx
0x18002e8a8  mov     [rax], bp
0x18002e8ab  test    r15d, r15d
0x18002e8ae  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002e8b6  lea     r9, [rsp+288h+Name]; lpName
0x18002e8bb  mov     [rsp+288h+dwFlags], ebp; int
0x18002e8bf  cmovnz  r12d, r15d
0x18002e8c3  mov     edx, r15d; lInitialCount
0x18002e8c6  mov     r8d, r12d; lMaximumCount
0x18002e8c9  xor     ecx, ecx; lpSemaphoreAttributes
0x18002e8cb  call    cs:__imp_CreateSemaphoreExW
0x18002e8d1  mov     rdi, rax
0x18002e8d4  test    rax, rax
0x18002e8d7  jnz     short loc_18002E907
0x18002e8d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002e8de  mov     ebx, eax
0x18002e8e0  test    eax, eax
0x18002e8e2  jns     short loc_18002E937
0x18002e8e4  lfence
0x18002e8e7  mov     rcx, [rsp+288h]; this
0x18002e8ef  lea     r8, aWil; "wil"
0x18002e8f6  mov     r9d, eax; char *
0x18002e8f9  mov     edx, 8Dh; void *
0x18002e8fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e903  mov     eax, ebx
0x18002e905  jmp     short loc_18002E939
0x18002e907  call    cs:__imp_GetLastError
0x18002e90d  mov     rbx, [r13+8]
0x18002e911  test    rbx, rbx
0x18002e914  jz      short loc_18002E933
0x18002e916  call    cs:__imp_GetLastError
0x18002e91c  mov     rcx, rbx; hObject
0x18002e91f  mov     esi, eax
0x18002e921  call    cs:__imp_CloseHandle
0x18002e927  test    eax, eax
0x18002e929  jz      short loc_18002E98B
0x18002e92b  mov     ecx, esi; dwErrCode
0x18002e92d  call    cs:__imp_SetLastError
0x18002e933  mov     [r13+8], rdi
0x18002e937  xor     eax, eax
0x18002e939  mov     rsi, [rsp+288h+var_18]
0x18002e941  mov     r12, [rsp+288h+var_28]
0x18002e949  mov     rdi, [rsp+288h+var_20]
0x18002e951  mov     r14, [rsp+288h+var_30]
0x18002e959  mov     rbp, [rsp+288h+var_10]
0x18002e961  mov     rbx, [rsp+288h+arg_8]
0x18002e969  mov     r15, [rsp+288h+var_38]
0x18002e971  mov     rcx, [rsp+288h+var_48]
0x18002e979  xor     rcx, rsp; StackCookie
0x18002e97c  call    __security_check_cookie
0x18002e981  add     rsp, 280h
0x18002e988  pop     r13
0x18002e98a  retn
0x18002e98b  mov     rcx, [rsp+288h]; this
0x18002e993  mov     edx, 9CDh; void *
0x18002e998  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e99e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002e9a4  mov     rcx, [rsp+288h]; this
0x18002e9ac  mov     edx, 9CDh; void *
0x18002e9b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
