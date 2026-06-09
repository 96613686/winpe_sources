# ATL::CRegParser::PreProcessBuffer(char *,char * *)

- ea: `0x180004a4c`
- end: `0x180004cdd`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEADPEAPEAD@Z`
- size: `657`
- prototype: `int(ATL::CRegParser *__hidden this, char *, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004f3c`

## callees

- `0x180002cc8`
- `0x18000352c`
- `0x1800037f4`
- `0x180004a4c`
- `0x18000701c`
- `0x18000b640`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180004bb1`
- `msvcrt!strncpy_s` at `0x180004bb1`
- `KERNEL32!lstrcmpiA` at `0x180004c04`
- `KERNEL32!lstrcmpiA` at `0x180004c04`
- `KERNEL32!LeaveCriticalSection` at `0x180004c1b`
- `KERNEL32!LeaveCriticalSection` at `0x180004c1b`
- `KERNEL32!EnterCriticalSection` at `0x180004be7`
- `KERNEL32!EnterCriticalSection` at `0x180004be7`
- `USER32!CharNextA` at `0x180004af1`
- `USER32!CharNextA` at `0x180004b06`
- `USER32!CharNextA` at `0x180004b29`
- `USER32!CharNextA` at `0x180004b70`
- `USER32!CharNextA` at `0x180004c5a`
- `USER32!CharNextA` at `0x180004af1`
- `USER32!CharNextA` at `0x180004b06`
- `USER32!CharNextA` at `0x180004b29`
- `USER32!CharNextA` at `0x180004b70`
- `USER32!CharNextA` at `0x180004c5a`
- `ole32!CoTaskMemAlloc` at `0x180004ab5`
- `ole32!CoTaskMemAlloc` at `0x180004ab5`
- `ole32!CoTaskMemFree` at `0x180004ad0`
- `ole32!CoTaskMemFree` at `0x180004b4f`
- `ole32!CoTaskMemFree` at `0x180004ad0`
- `ole32!CoTaskMemFree` at `0x180004b4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCSTR *this, char *a2, char **a3)
{
  LPSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  _BYTE *v8; // rax
  CHAR v10; // cl
  bool v11; // zf
  const CHAR *v12; // rcx
  CHAR v13; // al
  unsigned int v14; // eax
  unsigned int v15; // ebx
  const CHAR *v16; // rdi
  errno_t v17; // eax
  LPCSTR v18; // rbp
  int v19; // ebx
  unsigned int v20; // edx
  const WCHAR *v21; // rbx
  const CHAR *i; // rax
  _DWORD v23[2]; // [rsp+20h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-60h]
  char Destination[32]; // [rsp+30h] [rbp-58h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v23[0] = 0;
  v23[1] = v7;
  v8 = CoTaskMemAlloc((unsigned int)v7);
  pv = v8;
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *v8 = 0;
  *this = v4;
  v10 = *v4;
  if ( !*v4 )
  {
LABEL_17:
    v15 = 0;
    pv = 0;
    *a3 = v8;
    goto LABEL_18;
  }
  while ( 1 )
  {
    v11 = v10 == 37;
    v12 = v4;
    if ( !v11 )
      goto LABEL_14;
    v4 = CharNextA(v4);
    *this = v4;
    v13 = *v4;
    if ( *v4 != 37 )
      break;
    v12 = v4;
LABEL_14:
    v14 = (unsigned int)CharNextA(v12);
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v23, v4, v14 - (_DWORD)v4) )
      goto LABEL_49;
LABEL_15:
    v4 = CharNextA(*this);
    *this = v4;
    v10 = *v4;
    if ( !*v4 )
    {
      v8 = pv;
      goto LABEL_17;
    }
  }
  if ( !v4 )
    goto LABEL_48;
  v16 = 0;
  while ( v13 )
  {
    if ( v13 == 37 )
    {
      v16 = v4;
      break;
    }
    v4 = CharNextA(v4);
    v13 = *v4;
  }
  if ( !v16 )
    goto LABEL_48;
  if ( v16 - *this > 31 )
  {
    v15 = -2147467259;
    goto LABEL_18;
  }
  v17 = strncpy_s(Destination, 0x20u, *this, (int)v16 - *(_DWORD *)this);
  if ( v17 )
  {
    if ( v17 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v17 == 22 || v17 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v17 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v18 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
  v19 = 0;
  if ( *((int *)v18 + 6) <= 0 )
    goto LABEL_36;
  while ( lstrcmpiA(*(LPCSTR *)(*((_QWORD *)v18 + 1) + 8LL * v19), Destination) )
  {
    if ( ++v19 >= *((_DWORD *)v18 + 6) )
      goto LABEL_36;
  }
  if ( v19 == -1 )
  {
LABEL_36:
    v21 = 0;
  }
  else
  {
    if ( v19 < 0 || v19 >= *((_DWORD *)v18 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v20);
      __debugbreak();
    }
    v21 = *(const WCHAR **)(*((_QWORD *)v18 + 2) + 8LL * v19);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
  if ( !v21 )
  {
LABEL_48:
    v15 = -2147352567;
    goto LABEL_18;
  }
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::AddString((ATL::CRegParser::CParseBuffer *)v23, v21) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextA(i);
    goto LABEL_15;
  }
LABEL_49:
  v15 = -2147024882;
LABEL_18:
  CoTaskMemFree(pv);
  return v15;
}

```

## disassembly

```asm
0x180004a4c  mov     [rsp+arg_8], rbx
0x180004a51  push    rbp
0x180004a52  push    rsi
0x180004a53  push    rdi
0x180004a54  push    r14
0x180004a56  push    r15
0x180004a58  sub     rsp, 60h
0x180004a5c  mov     rax, cs:__security_cookie
0x180004a63  xor     rax, rsp
0x180004a66  mov     [rsp+88h+var_38], rax
0x180004a6b  mov     r15, r8
0x180004a6e  mov     rbx, rdx
0x180004a71  mov     rsi, rcx
0x180004a74  test    rdx, rdx
0x180004a77  jz      loc_180004C8B
0x180004a7d  test    r8, r8
0x180004a80  jz      loc_180004C8B
0x180004a86  mov     qword ptr [r8], 0
0x180004a8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a91  inc     rax
0x180004a94  cmp     byte ptr [rdx+rax], 0
0x180004a98  jnz     short loc_180004A91
0x180004a9a  add     eax, eax
0x180004a9c  mov     ecx, 3E8h
0x180004aa1  cmp     eax, 64h ; 'd'
0x180004aa4  cmovl   eax, ecx
0x180004aa7  mov     [rsp+88h+var_68], 0
0x180004aaf  mov     [rsp+88h+var_64], eax
0x180004ab3  mov     ecx, eax; cb
0x180004ab5  call    cs:__imp_CoTaskMemAlloc
0x180004abb  mov     [rsp+88h+pv], rax
0x180004ac0  test    rax, rax
0x180004ac3  jz      short loc_180004AC8
0x180004ac5  mov     byte ptr [rax], 0
0x180004ac8  test    rax, rax
0x180004acb  jnz     short loc_180004AE0
0x180004acd  mov     rcx, rax; pv
0x180004ad0  call    cs:__imp_CoTaskMemFree
0x180004ad6  mov     eax, 8007000Eh
0x180004adb  jmp     loc_180004C90
0x180004ae0  mov     [rsi], rbx
0x180004ae3  mov     cl, [rbx]
0x180004ae5  test    cl, cl
0x180004ae7  jz      short loc_180004B40
0x180004ae9  cmp     cl, 25h ; '%'
0x180004aec  mov     rcx, rbx; lpsz
0x180004aef  jnz     short loc_180004B06
0x180004af1  call    cs:__imp_CharNextA
0x180004af7  mov     rbx, rax
0x180004afa  mov     [rsi], rax
0x180004afd  mov     al, [rax]
0x180004aff  cmp     al, 25h ; '%'
0x180004b01  jnz     short loc_180004B5C
0x180004b03  mov     rcx, rbx; lpsz
0x180004b06  call    cs:__imp_CharNextA
0x180004b0c  sub     eax, ebx
0x180004b0e  mov     r8d, eax; int
0x180004b11  mov     rdx, rbx; char *
0x180004b14  lea     rcx, [rsp+88h+var_68]; this
0x180004b19  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBDH@Z; ATL::CRegParser::CParseBuffer::Append(char const *,int)
0x180004b1e  test    eax, eax
0x180004b20  jz      loc_180004C81
0x180004b26  mov     rcx, [rsi]; lpsz
0x180004b29  call    cs:__imp_CharNextA
0x180004b2f  mov     rbx, rax
0x180004b32  mov     [rsi], rax
0x180004b35  mov     cl, [rax]
0x180004b37  test    cl, cl
0x180004b39  jnz     short loc_180004AE9
0x180004b3b  mov     rax, [rsp+88h+pv]
0x180004b40  xor     ebx, ebx
0x180004b42  mov     [rsp+88h+pv], rbx
0x180004b47  mov     [r15], rax
0x180004b4a  mov     rcx, [rsp+88h+pv]; pv
0x180004b4f  call    cs:__imp_CoTaskMemFree
0x180004b55  mov     eax, ebx
0x180004b57  jmp     loc_180004C90
0x180004b5c  test    rbx, rbx
0x180004b5f  jz      loc_180004C77
0x180004b65  xor     edi, edi
0x180004b67  jmp     short loc_180004B7B
0x180004b69  cmp     al, 25h ; '%'
0x180004b6b  jz      short loc_180004B81
0x180004b6d  mov     rcx, rbx; lpsz
0x180004b70  call    cs:__imp_CharNextA
0x180004b76  mov     rbx, rax
0x180004b79  mov     al, [rax]
0x180004b7b  test    al, al
0x180004b7d  jnz     short loc_180004B69
0x180004b7f  jmp     short loc_180004B84
0x180004b81  mov     rdi, rbx
0x180004b84  test    rdi, rdi
0x180004b87  jz      loc_180004C77
0x180004b8d  mov     rax, rdi
0x180004b90  sub     rax, [rsi]
0x180004b93  cmp     rax, 1Fh
0x180004b97  jg      loc_180004C6D
0x180004b9d  mov     eax, edi
0x180004b9f  sub     eax, [rsi]
0x180004ba1  movsxd  r9, eax; MaxCount
0x180004ba4  mov     r8, [rsi]; Source
0x180004ba7  mov     edx, 20h ; ' '; SizeInBytes
0x180004bac  lea     rcx, [rsp+88h+Destination]; Destination
0x180004bb1  call    cs:__imp_strncpy_s
0x180004bb7  test    eax, eax
0x180004bb9  jz      short loc_180004BDF
0x180004bbb  cmp     eax, 0Ch
0x180004bbe  jz      loc_180004CD2
0x180004bc4  cmp     eax, 16h
0x180004bc7  jz      loc_180004CC7
0x180004bcd  cmp     eax, 22h ; '"'
0x180004bd0  jz      loc_180004CC7
0x180004bd6  cmp     eax, 50h ; 'P'
0x180004bd9  jnz     loc_180004CBC
0x180004bdf  mov     rbp, [rsi+8]
0x180004be3  lea     rcx, [rbp+20h]; lpCriticalSection
0x180004be7  call    cs:__imp_EnterCriticalSection
0x180004bed  xor     ebx, ebx
0x180004bef  cmp     [rbp+18h], ebx
0x180004bf2  jle     short loc_180004C15
0x180004bf4  movsxd  rax, ebx
0x180004bf7  mov     rcx, [rbp+8]
0x180004bfb  lea     rdx, [rsp+88h+Destination]; lpString2
0x180004c00  mov     rcx, [rcx+rax*8]; lpString1
0x180004c04  call    cs:__imp_lstrcmpiA
0x180004c0a  test    eax, eax
0x180004c0c  jz      short loc_180004C3C
0x180004c0e  inc     ebx
0x180004c10  cmp     ebx, [rbp+18h]
0x180004c13  jl      short loc_180004BF4
0x180004c15  xor     ebx, ebx
0x180004c17  lea     rcx, [rbp+20h]; lpCriticalSection
0x180004c1b  call    cs:__imp_LeaveCriticalSection
0x180004c21  test    rbx, rbx
0x180004c24  jz      short loc_180004C77
0x180004c26  mov     rdx, rbx; lpWideCharStr
0x180004c29  lea     rcx, [rsp+88h+var_68]; this
0x180004c2e  call    ?AddString@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddString(ushort const *)
0x180004c33  test    eax, eax
0x180004c35  jz      short loc_180004C81
0x180004c37  mov     rax, [rsi]
0x180004c3a  jmp     short loc_180004C63
0x180004c3c  cmp     ebx, 0FFFFFFFFh
0x180004c3f  jz      short loc_180004C15
0x180004c41  test    ebx, ebx
0x180004c43  js      short loc_180004CB1
0x180004c45  cmp     ebx, [rbp+18h]
0x180004c48  jge     short loc_180004CB1
0x180004c4a  movsxd  rcx, ebx
0x180004c4d  mov     rax, [rbp+10h]
0x180004c51  mov     rbx, [rax+rcx*8]
0x180004c55  jmp     short loc_180004C17
0x180004c57  mov     rcx, rax; lpsz
0x180004c5a  call    cs:__imp_CharNextA
0x180004c60  mov     [rsi], rax
0x180004c63  cmp     rax, rdi
0x180004c66  jnz     short loc_180004C57
0x180004c68  jmp     loc_180004B26
0x180004c6d  mov     ebx, 80004005h
0x180004c72  jmp     loc_180004B4A
0x180004c77  mov     ebx, 80020009h
0x180004c7c  jmp     loc_180004B4A
0x180004c81  mov     ebx, 8007000Eh
0x180004c86  jmp     loc_180004B4A
0x180004c8b  mov     eax, 80004003h
0x180004c90  mov     rcx, [rsp+88h+var_38]
0x180004c95  xor     rcx, rsp; StackCookie
0x180004c98  call    __security_check_cookie
0x180004c9d  mov     rbx, [rsp+88h+arg_8]
0x180004ca5  add     rsp, 60h
0x180004ca9  pop     r15
0x180004cab  pop     r14
0x180004cad  pop     rdi
0x180004cae  pop     rsi
0x180004caf  pop     rbp
0x180004cb0  retn
0x180004cb1  mov     ecx, 0C000008Ch; unsigned int
0x180004cb6  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004cbb  int     3; Trap to Debugger
0x180004cbc  mov     ecx, 80004005h; int
0x180004cc1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004cc7  mov     ecx, 80070057h; int
0x180004ccc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004cd2  mov     ecx, 8007000Eh; int
0x180004cd7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
