# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002b10`
- end: `0x180002cc2`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `434`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000672c`
- `0x180006b14`

## callees

- `0x18000276c`
- `0x180002b10`
- `0x1800037f4`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!free` at `0x180002c62`
- `msvcrt!free` at `0x180002c83`
- `msvcrt!free` at `0x180002c62`
- `msvcrt!free` at `0x180002c83`
- `msvcrt!malloc` at `0x180002be4`
- `msvcrt!malloc` at `0x180002be4`
- `KERNEL32!WideCharToMultiByte` at `0x180002c29`
- `KERNEL32!WideCharToMultiByte` at `0x180002c29`
- `KERNEL32!LeaveCriticalSection` at `0x180002c47`
- `KERNEL32!LeaveCriticalSection` at `0x180002c74`
- `KERNEL32!LeaveCriticalSection` at `0x180002c47`
- `KERNEL32!LeaveCriticalSection` at `0x180002c74`
- `KERNEL32!EnterCriticalSection` at `0x180002b56`
- `KERNEL32!EnterCriticalSection` at `0x180002b56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  _QWORD *v7; // rbx
  __int64 v8; // rax
  __int64 cbMultiByte; // rsi
  unsigned __int64 v10; // rax
  void *v11; // rsp
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v13; // rax
  int v14; // edi
  unsigned int v15; // edi
  void *v16; // rcx
  void *v18; // rcx
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v7 = 0;
  *(_QWORD *)MultiByteStr = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  cbMultiByte = 2LL * ((int)v8 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_21;
  if ( (int)cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte, 0) )
  {
    v10 = (int)cbMultiByte + 15LL;
    if ( v10 < (int)cbMultiByte )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v13 = malloc((int)cbMultiByte + 16LL);
    if ( v13 )
    {
      *v13 = 0;
      v7 = v13;
      *(_QWORD *)MultiByteStr = v13;
      lpMultiByteStr = (CHAR *)(v13 + 2);
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( lpMultiByteStr && (*lpMultiByteStr = 0, WideCharToMultiByte(3u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0)) )
  {
    v14 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), lpMultiByteStr, a3);
    LeaveCriticalSection(v6);
    v15 = v14 == 0 ? 0x8007000E : 0;
    while ( v7 )
    {
      v16 = v7;
      v7 = (_QWORD *)*v7;
      free(v16);
    }
    return v15;
  }
  else
  {
LABEL_21:
    LeaveCriticalSection(v6);
    while ( v7 )
    {
      v18 = v7;
      v7 = (_QWORD *)*v7;
      free(v18);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180002b10  push    rbp
0x180002b12  push    rbx
0x180002b13  push    rsi
0x180002b14  push    rdi
0x180002b15  push    r12
0x180002b17  push    r13
0x180002b19  push    r14
0x180002b1b  push    r15
0x180002b1d  sub     rsp, 58h
0x180002b21  lea     rbp, [rsp+40h]
0x180002b26  mov     rax, cs:__security_cookie
0x180002b2d  xor     rax, rbp
0x180002b30  mov     [rbp+50h+var_48], rax
0x180002b34  mov     r12, r8
0x180002b37  mov     r14, rdx
0x180002b3a  mov     r13, rcx
0x180002b3d  test    rdx, rdx
0x180002b40  jz      loc_180002C95
0x180002b46  test    r8, r8
0x180002b49  jz      loc_180002C95
0x180002b4f  lea     r15, [rcx+20h]
0x180002b53  mov     rcx, r15; lpCriticalSection
0x180002b56  call    cs:__imp_EnterCriticalSection
0x180002b5c  xor     edx, edx; unsigned __int64
0x180002b5e  mov     ebx, edx
0x180002b60  mov     qword ptr [rbp+50h+MultiByteStr], rdx
0x180002b64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002b68  inc     rax
0x180002b6b  cmp     [r14+rax*2], dx
0x180002b70  jnz     short loc_180002B68
0x180002b72  inc     eax
0x180002b74  movsxd  rcx, eax
0x180002b77  lea     rsi, [rcx+rcx]
0x180002b7b  mov     eax, 80000000h
0x180002b80  add     rax, rsi
0x180002b83  mov     ecx, 0FFFFFFFFh
0x180002b88  cmp     rax, rcx
0x180002b8b  ja      loc_180002C71
0x180002b91  movsxd  rdi, esi
0x180002b94  cmp     esi, 400h
0x180002b9a  jg      short loc_180002BD0
0x180002b9c  mov     rcx, rdi; this
0x180002b9f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180002ba4  xor     edx, edx
0x180002ba6  test    al, al
0x180002ba8  jz      short loc_180002BD0
0x180002baa  lea     rax, [rdi+0Fh]
0x180002bae  cmp     rax, rdi
0x180002bb1  ja      short loc_180002BBD
0x180002bb3  mov     rax, 0FFFFFFFFFFFFFF0h
0x180002bbd  and     rax, 0FFFFFFFFFFFFFFF0h
0x180002bc1  call    _alloca_probe
0x180002bc6  sub     rsp, rax
0x180002bc9  lea     rdi, [rsp+90h+MultiByteStr]
0x180002bce  jmp     short loc_180002C03
0x180002bd0  mov     rax, rdi
0x180002bd3  not     rax
0x180002bd6  cmp     rax, 10h
0x180002bda  jb      loc_180002CB7
0x180002be0  lea     rcx, [rdi+10h]; Size
0x180002be4  call    cs:__imp_malloc
0x180002bea  xor     edx, edx
0x180002bec  test    rax, rax
0x180002bef  jnz     short loc_180002BF5
0x180002bf1  mov     edi, edx
0x180002bf3  jmp     short loc_180002C03
0x180002bf5  mov     [rax], rdx
0x180002bf8  mov     rbx, rax
0x180002bfb  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180002bff  lea     rdi, [rax+10h]
0x180002c03  test    rdi, rdi
0x180002c06  jz      short loc_180002C71
0x180002c08  mov     [rdi], dl
0x180002c0a  mov     [rsp+90h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180002c0f  mov     [rsp+90h+lpDefaultChar], rdx; lpDefaultChar
0x180002c14  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x180002c18  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x180002c1d  or      r9d, 0FFFFFFFFh; cchWideChar
0x180002c21  mov     r8, r14; lpWideCharStr
0x180002c24  xor     edx, edx; dwFlags
0x180002c26  lea     ecx, [rdx+3]; CodePage
0x180002c29  call    cs:__imp_WideCharToMultiByte
0x180002c2f  test    eax, eax
0x180002c31  jz      short loc_180002C71
0x180002c33  lea     rcx, [r13+8]; this
0x180002c37  mov     r8, r12; unsigned __int16 *
0x180002c3a  mov     rdx, rdi; char *
0x180002c3d  call    ?Add@CExpansionVector@ATL@@QEAAHPEBDPEBG@Z; ATL::CExpansionVector::Add(char const *,ushort const *)
0x180002c42  mov     edi, eax
0x180002c44  mov     rcx, r15; lpCriticalSection
0x180002c47  call    cs:__imp_LeaveCriticalSection
0x180002c4d  nop
0x180002c4e  neg     edi
0x180002c50  sbb     edi, edi
0x180002c52  not     edi
0x180002c54  and     edi, 8007000Eh
0x180002c5a  jmp     short loc_180002C68
0x180002c5c  mov     rcx, rbx; Block
0x180002c5f  mov     rbx, [rbx]
0x180002c62  call    cs:__imp_free
0x180002c68  test    rbx, rbx
0x180002c6b  jnz     short loc_180002C5C
0x180002c6d  mov     eax, edi
0x180002c6f  jmp     short loc_180002C9A
0x180002c71  mov     rcx, r15; lpCriticalSection
0x180002c74  call    cs:__imp_LeaveCriticalSection
0x180002c7a  nop
0x180002c7b  jmp     short loc_180002C89
0x180002c7d  mov     rcx, rbx; Block
0x180002c80  mov     rbx, [rbx]
0x180002c83  call    cs:__imp_free
0x180002c89  test    rbx, rbx
0x180002c8c  jnz     short loc_180002C7D
0x180002c8e  mov     eax, 8007000Eh
0x180002c93  jmp     short loc_180002C9A
0x180002c95  mov     eax, 80070057h
0x180002c9a  mov     rcx, [rbp+50h+var_48]
0x180002c9e  xor     rcx, rbp; StackCookie
0x180002ca1  call    __security_check_cookie
0x180002ca6  lea     rsp, [rbp+18h]
0x180002caa  pop     r15
0x180002cac  pop     r14
0x180002cae  pop     r13
0x180002cb0  pop     r12
0x180002cb2  pop     rdi
0x180002cb3  pop     rsi
0x180002cb4  pop     rbx
0x180002cb5  pop     rbp
0x180002cb6  retn
0x180002cb7  mov     ecx, 80070057h; int
0x180002cbc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
