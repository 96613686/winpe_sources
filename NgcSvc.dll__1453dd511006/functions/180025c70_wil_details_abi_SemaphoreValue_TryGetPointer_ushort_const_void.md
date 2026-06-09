# wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)

- ea: `0x180025c70`
- end: `0x180025f78`
- name: `?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z`
- size: `776`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025aa0`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18000948c`
- `0x1800094b8`
- `0x180025c70`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025d78`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025e4f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025d78`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f12`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetPointer(WCHAR *a1, void **a2)
{
  WCHAR *v2; // rax
  __int64 v3; // r15
  unsigned __int64 v4; // r14
  __int64 v5; // r9
  __int64 v6; // r8
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  __int64 v11; // r8
  const wchar_t *v12; // r9
  __int64 v13; // rcx
  WCHAR *v14; // rdx
  __int64 v15; // rax
  WCHAR *v16; // rcx
  wil::details *v17; // rax
  wil::details *v18; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  void *v21; // rdx
  __int64 v22; // rdx
  WCHAR *v23; // rax
  __int64 v24; // r8
  WCHAR *v25; // rax
  const wchar_t *v26; // rcx
  __int64 v27; // rbx
  WCHAR *v28; // rdx
  wil::details *v29; // rax
  const char *v30; // r9
  wil::details *v31; // rbx
  int v32; // eax
  void *v33; // rdx
  void *v34; // rdx
  void *v35; // rdx
  void *v37; // rdx
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h] BYREF
  int v40[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v2 = Name;
  v3 = 2147483646;
  *a2 = 0;
  v4 = 0;
  v5 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*a1 )
      break;
    *v2++ = *a1++;
    --v5;
    --v6;
  }
  while ( v6 );
  v8 = v2 - 1;
  v9 = 260;
  if ( v6 )
    v8 = v2;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = (260 - v9) & -(__int64)(v9 != 0);
  if ( v9 )
  {
    v12 = L"_p0";
    v13 = 2147483646;
    v14 = &Name[v11];
    v15 = 260 - v11;
    if ( v11 != 260 )
    {
      do
      {
        if ( !v13 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v13;
        --v15;
      }
      while ( v15 );
    }
    v16 = v14 - 1;
    if ( v15 )
      v16 = v14;
    *v16 = 0;
  }
  v17 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v17;
  if ( !v17 )
  {
    if ( GetLastError() == 2 )
      goto LABEL_37;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v38);
    goto LABEL_41;
  }
  v40[0] = 0;
  v39 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, v40);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore >= 0 )
  {
    v22 = 260;
    v23 = Name;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    v24 = (260 - v22) & -(__int64)(v22 != 0);
    if ( v22 )
    {
      v25 = &Name[v24];
      v26 = L"h";
      v27 = 260 - v24;
      if ( 260 != v24 )
      {
        do
        {
          if ( !v3 )
            break;
          if ( !*v26 )
            break;
          *v25++ = *v26++;
          --v3;
          --v27;
        }
        while ( v27 );
      }
      v28 = v25 - 1;
      if ( v27 )
        v28 = v25;
      *v28 = 0;
    }
    v29 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v31 = v29;
    if ( v29 )
    {
      v32 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v29, &v39);
      LastError = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v32,
          v39);
        wil::details::CloseHandle(v31, v34);
        goto LABEL_21;
      }
      wil::details::CloseHandle(v31, v33);
      v4 = v40[0] | (unsigned __int64)((__int64)v39 << 31);
      wil::details::CloseHandle(v18, v35);
LABEL_37:
      *a2 = (void *)(4 * v4);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v30);
    wil::details::CloseHandle(v18, v37);
LABEL_41:
    if ( (LastError & 0x80000000) != 0 )
      goto LABEL_42;
    goto LABEL_37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD6,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueFromSemaphore,
    v39);
LABEL_21:
  wil::details::CloseHandle(v18, v21);
LABEL_42:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (unsigned int)"wil", (const char *)LastError, v39);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastError, v39);
  return LastError;
}

```

## disassembly

```asm
0x180025c70  push    rbp
0x180025c72  push    rbx
0x180025c73  push    rsi
0x180025c74  push    rdi
0x180025c75  push    r12
0x180025c77  push    r13
0x180025c79  push    r14
0x180025c7b  push    r15
0x180025c7d  lea     rbp, [rsp-158h]
0x180025c85  sub     rsp, 258h
0x180025c8c  mov     rax, cs:__security_cookie
0x180025c93  xor     rax, rsp
0x180025c96  mov     [rbp+190h+var_50], rax
0x180025c9d  xor     r13d, r13d
0x180025ca0  lea     rax, [rsp+290h+Name]
0x180025ca5  mov     r15d, 7FFFFFFEh
0x180025cab  mov     [rdx], r13
0x180025cae  mov     ebx, 104h
0x180025cb3  mov     r14d, r13d
0x180025cb6  mov     r9d, r15d
0x180025cb9  mov     r8d, ebx
0x180025cbc  mov     r12, rdx
0x180025cbf  test    r9, r9
0x180025cc2  jz      short loc_180025CE0
0x180025cc4  movzx   edx, word ptr [rcx]
0x180025cc7  test    dx, dx
0x180025cca  jz      short loc_180025CE0
0x180025ccc  mov     [rax], dx
0x180025ccf  add     rcx, 2
0x180025cd3  add     rax, 2
0x180025cd7  dec     r9
0x180025cda  sub     r8, 1
0x180025cde  jnz     short loc_180025CBF
0x180025ce0  lea     rcx, [rax-2]
0x180025ce4  test    r8, r8
0x180025ce7  mov     rdx, rbx
0x180025cea  cmovnz  rcx, rax
0x180025cee  lea     rax, [rsp+290h+Name]
0x180025cf3  mov     [rcx], r13w
0x180025cf7  cmp     [rax], r13w
0x180025cfb  jz      short loc_180025D07
0x180025cfd  add     rax, 2
0x180025d01  sub     rdx, 1
0x180025d05  jnz     short loc_180025CF7
0x180025d07  mov     rcx, rbx
0x180025d0a  mov     rax, rdx
0x180025d0d  sub     rcx, rdx
0x180025d10  neg     rax
0x180025d13  sbb     r8, r8
0x180025d16  and     r8, rcx
0x180025d19  test    rdx, rdx
0x180025d1c  jz      short loc_180025D6C
0x180025d1e  mov     rax, rbx
0x180025d21  lea     rdx, [rsp+290h+Name]
0x180025d26  lea     r9, aP0; "_p0"
0x180025d2d  mov     rcx, r15
0x180025d30  lea     rdx, [rdx+r8*2]
0x180025d34  sub     rax, r8
0x180025d37  jz      short loc_180025D5D
0x180025d39  test    rcx, rcx
0x180025d3c  jz      short loc_180025D5D
0x180025d3e  movzx   r8d, word ptr [r9]
0x180025d42  test    r8w, r8w
0x180025d46  jz      short loc_180025D5D
0x180025d48  mov     [rdx], r8w
0x180025d4c  add     r9, 2
0x180025d50  add     rdx, 2
0x180025d54  dec     rcx
0x180025d57  sub     rax, 1
0x180025d5b  jnz     short loc_180025D39
0x180025d5d  test    rax, rax
0x180025d60  lea     rcx, [rdx-2]
0x180025d64  cmovnz  rcx, rdx
0x180025d68  mov     [rcx], r13w
0x180025d6c  lea     r8, [rsp+290h+Name]; lpName
0x180025d71  xor     edx, edx; bInheritHandle
0x180025d73  mov     ecx, 1F0003h; dwDesiredAccess
0x180025d78  call    cs:__imp_OpenSemaphoreW
0x180025d7e  mov     rdi, rax
0x180025d81  test    rax, rax
0x180025d84  jz      loc_180025F12
0x180025d8a  lea     rdx, [rsp+290h+var_26C]; int *
0x180025d8f  mov     [rsp+290h+var_26C], r13d
0x180025d94  mov     rcx, rax; hHandle
0x180025d97  mov     [rsp+290h+var_270], r13d; int
0x180025d9c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025da1  mov     esi, eax
0x180025da3  test    eax, eax
0x180025da5  jns     short loc_180025DCF
0x180025da7  mov     rcx, [rbp+198h]; this
0x180025dae  lea     r8, aWil; "wil"
0x180025db5  mov     r9d, eax; char *
0x180025db8  mov     edx, 0D6h; void *
0x180025dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025dc2  mov     rcx, rdi; this
0x180025dc5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025dca  jmp     loc_180025F3B
0x180025dcf  mov     rdx, rbx
0x180025dd2  lea     rax, [rsp+290h+Name]
0x180025dd7  cmp     [rax], r13w
0x180025ddb  jz      short loc_180025DE7
0x180025ddd  add     rax, 2
0x180025de1  sub     rdx, 1
0x180025de5  jnz     short loc_180025DD7
0x180025de7  mov     rcx, rbx
0x180025dea  mov     rax, rdx
0x180025ded  sub     rcx, rdx
0x180025df0  neg     rax
0x180025df3  sbb     r8, r8
0x180025df6  and     r8, rcx
0x180025df9  test    rdx, rdx
0x180025dfc  jz      short loc_180025E43
0x180025dfe  lea     rax, [rsp+290h+Name]
0x180025e03  lea     rax, [rax+r8*2]
0x180025e07  lea     rcx, asc_1800DB980; "h"
0x180025e0e  sub     rbx, r8
0x180025e11  jz      short loc_180025E34
0x180025e13  test    r15, r15
0x180025e16  jz      short loc_180025E34
0x180025e18  movzx   edx, word ptr [rcx]
0x180025e1b  test    dx, dx
0x180025e1e  jz      short loc_180025E34
0x180025e20  mov     [rax], dx
0x180025e23  add     rcx, 2
0x180025e27  add     rax, 2
0x180025e2b  dec     r15
0x180025e2e  sub     rbx, 1
0x180025e32  jnz     short loc_180025E13
0x180025e34  test    rbx, rbx
0x180025e37  lea     rdx, [rax-2]
0x180025e3b  cmovnz  rdx, rax
0x180025e3f  mov     [rdx], r13w
0x180025e43  lea     r8, [rsp+290h+Name]; lpName
0x180025e48  xor     edx, edx; bInheritHandle
0x180025e4a  mov     ecx, 1F0003h; dwDesiredAccess
0x180025e4f  call    cs:__imp_OpenSemaphoreW
0x180025e55  mov     rbx, rax
0x180025e58  test    rax, rax
0x180025e5b  jz      loc_180025EEE
0x180025e61  lea     rdx, [rsp+290h+var_270]; int *
0x180025e66  mov     rcx, rax; hHandle
0x180025e69  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025e6e  mov     esi, eax
0x180025e70  test    eax, eax
0x180025e72  jns     short loc_180025E9C
0x180025e74  mov     rcx, [rbp+198h]; this
0x180025e7b  lea     r8, aWil; "wil"
0x180025e82  mov     r9d, eax; char *
0x180025e85  mov     edx, 0DEh; void *
0x180025e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e8f  mov     rcx, rbx; this
0x180025e92  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025e97  jmp     loc_180025DC2
0x180025e9c  mov     rcx, rbx; this
0x180025e9f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025ea4  movsxd  rax, [rsp+290h+var_26C]
0x180025ea9  mov     rcx, rdi; this
0x180025eac  movsxd  r14, [rsp+290h+var_270]
0x180025eb1  shl     r14, 1Fh
0x180025eb5  or      r14, rax
0x180025eb8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025ebd  lea     rax, ds:0[r14*4]
0x180025ec5  mov     [r12], rax
0x180025ec9  xor     eax, eax
0x180025ecb  mov     rcx, [rbp+190h+var_50]
0x180025ed2  xor     rcx, rsp; StackCookie
0x180025ed5  call    __security_check_cookie
0x180025eda  add     rsp, 258h
0x180025ee1  pop     r15
0x180025ee3  pop     r14
0x180025ee5  pop     r13
0x180025ee7  pop     r12
0x180025ee9  pop     rdi
0x180025eea  pop     rsi
0x180025eeb  pop     rbx
0x180025eec  pop     rbp
0x180025eed  retn
0x180025eee  mov     rcx, [rbp+198h]; this
0x180025ef5  lea     r8, aWil; "wil"
0x180025efc  mov     edx, 0DCh; void *
0x180025f01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025f06  mov     rcx, rdi; this
0x180025f09  mov     esi, eax
0x180025f0b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025f10  jmp     short loc_180025F37
0x180025f12  call    cs:__imp_GetLastError
0x180025f18  cmp     eax, 2
0x180025f1b  jz      short loc_180025EBD
0x180025f1d  mov     rcx, [rbp+198h]; this
0x180025f24  lea     r8, aWil; "wil"
0x180025f2b  mov     edx, 0D0h; void *
0x180025f30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025f35  mov     esi, eax
0x180025f37  test    esi, esi
0x180025f39  jns     short loc_180025EBD
0x180025f3b  mov     rcx, [rbp+198h]; this
0x180025f42  lea     r8, aWil; "wil"
0x180025f49  mov     r9d, esi; char *
0x180025f4c  mov     edx, 66h ; 'f'; void *
0x180025f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f56  mov     rcx, [rbp+198h]; this
0x180025f5d  lea     r8, aWil; "wil"
0x180025f64  mov     r9d, esi; char *
0x180025f67  mov     edx, 6Fh ; 'o'; void *
0x180025f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f71  mov     eax, esi
0x180025f73  jmp     loc_180025ECB
```
