# Vpath::rename(Vstring const &,char)

- ea: `0x180094480`
- end: `0x1800947cc`
- name: `?rename@Vpath@@QEAAPEAVVstatus@@AEBVVstring@@D@Z`
- size: `844`
- prototype: `struct Vstatus *__fastcall(Vpath *__hidden this, const struct Vstring *, char)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180093f80`
- `0x1800947d0`
- `0x1800e0540`
- `0x1800e0c90`

## callees

- `0x180047c50`
- `0x18006ff20`
- `0x1800838f0`
- `0x1800903dc`
- `0x180090560`
- `0x180090df0`
- `0x180092a20`
- `0x180094480`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x180134070`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180094743`
- `KERNEL32!DeleteFileA` at `0x180094743`
- `KERNEL32!MoveFileExW` at `0x180094715`
- `KERNEL32!MoveFileExW` at `0x180094715`
- `KERNEL32!MoveFileA` at `0x18009471d`
- `KERNEL32!MoveFileA` at `0x180094757`
- `KERNEL32!MoveFileA` at `0x18009471d`
- `KERNEL32!MoveFileA` at `0x180094757`
- `KERNEL32!GetLastError` at `0x18009472c`
- `KERNEL32!GetLastError` at `0x180094764`
- `KERNEL32!GetLastError` at `0x18009472c`
- `KERNEL32!GetLastError` at `0x180094764`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800945cf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094619`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800946c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800945cf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094619`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800946c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct Vstatus *__fastcall Vpath::rename(char **this, const struct Vstring *a2, char a3)
{
  __int64 v6; // rbx
  int *v7; // rcx
  int *v8; // rcx
  char *v9; // r8
  int v10; // edx
  unsigned int v11; // ecx
  __int64 v12; // rdx
  int *v13; // rcx
  __int64 v14; // r8
  bool v15; // r14
  int v16; // ecx
  BOOL v17; // eax
  DWORD v18; // eax
  char *v19; // rbx
  DWORD LastError; // eax
  char v22; // [rsp+28h] [rbp-E0h]
  _QWORD v23[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v24[4]; // [rsp+50h] [rbp-B8h] BYREF
  _WORD v25[256]; // [rsp+78h] [rbp-90h] BYREF
  LPCWSTR lpNewFileName; // [rsp+278h] [rbp+170h]
  int v27; // [rsp+280h] [rbp+178h]
  char v28; // [rsp+284h] [rbp+17Ch]
  _WORD v29[256]; // [rsp+288h] [rbp+180h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+488h] [rbp+380h]
  int v31; // [rsp+490h] [rbp+388h]
  char v32; // [rsp+494h] [rbp+38Ch]

  v24[3] = -2;
  v22 = 0;
  lpNewFileName = v25;
  v27 = 512;
  v25[0] = 0;
  v28 = 0;
  sub_1800B7B38((VstackStrLCP *)v25);
  lpExistingFileName = v29;
  v31 = 512;
  v29[0] = 0;
  v32 = 0;
  sub_1800B7B38((VstackStrLCP *)v29);
  if ( a3 )
    goto LABEL_14;
  Vpath::Vpath((Vpath *)v23, a2);
  if ( !Vpath::exists((Vpath *)v23) || Vpath::pathsEquivalent((Vpath *)this, (const struct Vpath *)v23) )
  {
    Vpath::ClearStat((Vpath *)v23);
    v8 = (int *)(v23[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v23[0] - 12LL), 0xFFFFFFFF) == 1 && v8 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v8);
      else
        free(v8);
    }
LABEL_14:
    if ( !Vpath::exists((Vpath *)this) )
    {
      v9 = *this;
      v10 = 0;
      v11 = 131093;
LABEL_41:
      v6 = sub_180047C50(v11, v10, v9);
      goto LABEL_43;
    }
    Vpath::ClearStat((Vpath *)this);
    v15 = 1;
    if ( !isMSDosReservedName((const struct Vpath *)this) )
    {
      Vpath::Vpath((Vpath *)v24, a2);
      v22 = 1;
      if ( !isMSDosReservedName((const struct Vpath *)v24) )
        v15 = 0;
    }
    if ( (v22 & 1) != 0 )
    {
      Vpath::ClearStat((Vpath *)v24);
      v13 = (int *)(v24[0] - 12LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24[0] - 12LL), 0xFFFFFFFF) == 1
        && v13 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v13);
        else
          free(v13);
      }
    }
    if ( v15 )
    {
      v9 = *this;
      v10 = 13;
LABEL_40:
      v11 = 131092;
      goto LABEL_41;
    }
    if ( (unsigned __int8)sub_180096770(v13, v12, v14) )
      v16 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v16 = 0;
    if ( v16 == 2 )
    {
      v17 = MoveFileExW(lpExistingFileName, lpNewFileName, (a3 != 0) | 8);
    }
    else
    {
      if ( MoveFileA((LPCSTR)lpExistingFileName, (LPCSTR)lpNewFileName) )
        goto LABEL_42;
      if ( !a3 )
        goto LABEL_39;
      v18 = GetLastError() - 80;
      if ( v18 )
      {
        if ( v18 != 103 )
          goto LABEL_39;
      }
      DeleteFileA((LPCSTR)lpNewFileName);
      v17 = MoveFileA((LPCSTR)lpExistingFileName, (LPCSTR)lpNewFileName);
    }
    if ( !v17 )
    {
LABEL_39:
      v19 = *this;
      LastError = GetLastError();
      v9 = v19;
      v10 = LastError;
      goto LABEL_40;
    }
LABEL_42:
    RWCString::operator=(this, a2);
    v6 = 0;
    goto LABEL_43;
  }
  v6 = sub_1800903DC(0x20019u);
  Vpath::ClearStat((Vpath *)v23);
  v7 = (int *)(v23[0] - 12LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v23[0] - 12LL), 0xFFFFFFFF) == 1 && v7 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v7);
    else
      free(v7);
  }
LABEL_43:
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v29);
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v25);
  return (struct Vstatus *)v6;
}

```

## disassembly

```asm
0x180094480  mov     rax, rsp
0x180094483  push    rbp
0x180094484  push    rsi
0x180094485  push    r12
0x180094487  push    r14
0x180094489  push    r15
0x18009448b  lea     rbp, [rax-3C8h]
0x180094492  sub     rsp, 4A0h
0x180094499  mov     qword ptr [rsp+60h], 0FFFFFFFFFFFFFFFEh
0x1800944a2  mov     [rax+20h], rbx
0x1800944a6  mov     rax, cs:__security_cookie
0x1800944ad  xor     rax, rsp
0x1800944b0  mov     [rbp+3C0h+var_30], rax
0x1800944b7  mov     r12b, r8b
0x1800944ba  mov     r15, rdx
0x1800944bd  mov     rbx, rcx
0x1800944c0  and     dword ptr [rsp+4C0h+var_4A0], 0
0x1800944c5  lea     rax, [rsp+4C0h+var_450]
0x1800944ca  mov     [rbp+3C0h+lpNewFileName], rax
0x1800944d1  mov     [rbp+3C0h+var_248], 200h
0x1800944db  and     [rsp+4C0h+var_450], 0
0x1800944e1  mov     [rbp+3C0h+var_244], 0
0x1800944e8  lea     rcx, [rsp+4C0h+var_450]; this
0x1800944ed  call    sub_1800B7B38
0x1800944f2  nop
0x1800944f3  lea     rax, [rbp+3C0h+var_240]
0x1800944fa  mov     [rbp+3C0h+lpExistingFileName], rax
0x180094501  mov     [rbp+3C0h+var_38], 200h
0x18009450b  and     [rbp+3C0h+var_240], 0
0x180094513  mov     [rbp+3C0h+var_34], 0
0x18009451a  mov     rdx, rbx
0x18009451d  lea     rcx, [rbp+3C0h+var_240]; this
0x180094524  call    sub_1800B7B38
0x180094529  nop
0x18009452a  lea     rsi, dword_1802AFD50
0x180094531  test    r12b, r12b
0x180094534  jnz     loc_18009461F
0x18009453a  mov     rdx, r15; struct Vstring *
0x18009453d  lea     rcx, [rsp+4C0h+var_490]; this
0x180094542  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x180094547  nop
0x180094548  lea     rcx, [rsp+4C0h+var_490]; this
0x18009454d  call    ?exists@Vpath@@QEAADXZ; Vpath::exists(void)
0x180094552  test    al, al
0x180094554  jz      loc_1800945DA
0x18009455a  lea     rdx, [rsp+4C0h+var_490]; struct Vpath *
0x18009455f  mov     rcx, rbx; this
0x180094562  call    ?pathsEquivalent@Vpath@@QEBADAEBV1@@Z; Vpath::pathsEquivalent(Vpath const &)
0x180094567  test    al, al
0x180094569  jnz     short loc_1800945DA
0x18009456b  mov     r9, [r15]
0x18009456e  mov     r8, [rbx]
0x180094571  mov     ecx, 20019h
0x180094576  call    sub_1800903DC
0x18009457b  mov     rbx, rax
0x18009457e  lea     rcx, [rsp+4C0h+var_490]; this
0x180094583  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180094588  nop
0x180094589  lea     rax, [rsp+4C0h+var_490]
0x18009458e  mov     [rsp+4C0h+var_498], rax
0x180094593  mov     rcx, qword ptr [rsp+4C0h+var_490]
0x180094598  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18009459c  or      eax, 0FFFFFFFFh
0x18009459f  lock xadd [rcx], eax
0x1800945a3  cmp     eax, 1
0x1800945a6  jnz     loc_18009478B
0x1800945ac  lea     rsi, dword_1802AFD50
0x1800945b3  cmp     rcx, rsi
0x1800945b6  jz      loc_18009478B
0x1800945bc  cmp     cs:dword_1802B0018, 0
0x1800945c3  jz      short loc_1800945CF
0x1800945c5  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800945ca  jmp     loc_18009478B
0x1800945cf  call    cs:free
0x1800945d5  jmp     loc_18009478B
0x1800945da  lea     rcx, [rsp+4C0h+var_490]; this
0x1800945df  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800945e4  nop
0x1800945e5  lea     rax, [rsp+4C0h+var_490]
0x1800945ea  mov     [rsp+4C0h+var_498], rax
0x1800945ef  mov     rcx, qword ptr [rsp+4C0h+var_490]
0x1800945f4  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800945f8  or      eax, 0FFFFFFFFh
0x1800945fb  lock xadd [rcx], eax
0x1800945ff  cmp     eax, 1
0x180094602  jnz     short loc_18009461F
0x180094604  cmp     rcx, rsi
0x180094607  jz      short loc_18009461F
0x180094609  cmp     cs:dword_1802B0018, 0
0x180094610  jz      short loc_180094619
0x180094612  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180094617  jmp     short loc_18009461F
0x180094619  call    cs:free
0x18009461f  mov     rcx, rbx; this
0x180094622  call    ?exists@Vpath@@QEAADXZ; Vpath::exists(void)
0x180094627  test    al, al
0x180094629  jnz     short loc_18009463A
0x18009462b  mov     r8, [rbx]
0x18009462e  xor     edx, edx
0x180094630  mov     ecx, 20015h
0x180094635  jmp     loc_180094774
0x18009463a  mov     rcx, rbx; this
0x18009463d  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180094642  mov     rcx, rbx; struct Vpath *
0x180094645  call    ?isMSDosReservedName@@YADAEBVVpath@@@Z; isMSDosReservedName(Vpath const &)
0x18009464a  test    al, al
0x18009464c  jnz     short loc_180094677
0x18009464e  mov     rdx, r15; struct Vstring *
0x180094651  lea     rcx, [rsp+4C0h+var_478]; this
0x180094656  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x18009465b  nop
0x18009465c  mov     dword ptr [rsp+4C0h+var_4A0], 1
0x180094664  lea     rcx, [rsp+4C0h+var_478]; struct Vpath *
0x180094669  call    ?isMSDosReservedName@@YADAEBVVpath@@@Z; isMSDosReservedName(Vpath const &)
0x18009466e  test    al, al
0x180094670  jnz     short loc_180094677
0x180094672  xor     r14b, r14b
0x180094675  jmp     short loc_18009467A
0x180094677  mov     r14b, 1
0x18009467a  test    byte ptr [rsp+4C0h+var_4A0], 1
0x18009467f  jz      short loc_1800946CB
0x180094681  and     dword ptr [rsp+4C0h+var_4A0], 0FFFFFFFEh
0x180094686  lea     rcx, [rsp+4C0h+var_478]; this
0x18009468b  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180094690  nop
0x180094691  lea     rax, [rsp+4C0h+var_478]
0x180094696  mov     [rsp+4C0h+var_498], rax
0x18009469b  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x1800946a0  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800946a4  or      eax, 0FFFFFFFFh
0x1800946a7  lock xadd [rcx], eax
0x1800946ab  cmp     eax, 1
0x1800946ae  jnz     short loc_1800946CB
0x1800946b0  cmp     rcx, rsi
0x1800946b3  jz      short loc_1800946CB
0x1800946b5  cmp     cs:dword_1802B0018, 0
0x1800946bc  jz      short loc_1800946C5
0x1800946be  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800946c3  jmp     short loc_1800946CB
0x1800946c5  call    cs:free
0x1800946cb  test    r14b, r14b
0x1800946ce  jz      short loc_1800946DD
0x1800946d0  mov     r8, [rbx]
0x1800946d3  mov     edx, 0Dh
0x1800946d8  jmp     loc_18009476F
0x1800946dd  call    sub_180096770
0x1800946e2  test    al, al
0x1800946e4  jz      short loc_1800946F2
0x1800946e6  mov     rax, cs:qword_1802B00B0
0x1800946ed  mov     ecx, [rax+4]
0x1800946f0  jmp     short loc_1800946F4
0x1800946f2  xor     ecx, ecx
0x1800946f4  mov     rdx, [rbp+3C0h+lpNewFileName]; lpNewFileName
0x1800946fb  cmp     ecx, 2
0x1800946fe  mov     rcx, [rbp+3C0h+lpExistingFileName]; lpExistingFileName
0x180094705  jnz     short loc_18009471D
0x180094707  xor     r8d, r8d
0x18009470a  test    r12b, r12b
0x18009470d  setnz   r8b
0x180094711  or      r8d, 8; dwFlags
0x180094715  call    cs:MoveFileExW
0x18009471b  jmp     short loc_18009475D
0x18009471d  call    cs:MoveFileA
0x180094723  test    eax, eax
0x180094725  jnz     short loc_18009477E
0x180094727  test    r12b, r12b
0x18009472a  jz      short loc_180094761
0x18009472c  call    cs:GetLastError
0x180094732  sub     eax, 50h ; 'P'
0x180094735  jz      short loc_18009473C
0x180094737  cmp     eax, 67h ; 'g'
0x18009473a  jnz     short loc_180094761
0x18009473c  mov     rcx, [rbp+3C0h+lpNewFileName]; lpFileName
0x180094743  call    cs:DeleteFileA
0x180094749  mov     rdx, [rbp+3C0h+lpNewFileName]; lpNewFileName
0x180094750  mov     rcx, [rbp+3C0h+lpExistingFileName]; lpExistingFileName
0x180094757  call    cs:MoveFileA
0x18009475d  test    eax, eax
0x18009475f  jnz     short loc_18009477E
0x180094761  mov     rbx, [rbx]
0x180094764  call    cs:GetLastError
0x18009476a  mov     r8, rbx
0x18009476d  mov     edx, eax
0x18009476f  mov     ecx, 20014h
0x180094774  call    sub_180047C50
0x180094779  mov     rbx, rax
0x18009477c  jmp     short loc_18009478B
0x18009477e  mov     rdx, r15
0x180094781  mov     rcx, rbx
0x180094784  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x180094789  xor     ebx, ebx
0x18009478b  lea     rcx, [rbp+3C0h+var_240]; this
0x180094792  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x180094797  nop
0x180094798  lea     rcx, [rsp+4C0h+var_450]; this
0x18009479d  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800947a2  mov     rax, rbx
0x1800947a5  mov     rcx, [rbp+3C0h+var_30]
0x1800947ac  xor     rcx, rsp
0x1800947af  call    sub_1801503E0
0x1800947b4  mov     rbx, [rsp+4C0h+arg_18]
0x1800947bc  add     rsp, 4A0h
0x1800947c3  pop     r15
0x1800947c5  pop     r14
0x1800947c7  pop     r12
0x1800947c9  pop     rsi
0x1800947ca  pop     rbp
0x1800947cb  retn
```
