# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x180030020`
- end: `0x1800301c0`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `416`
- prototype: `void *__fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180002604`
- `0x180030020`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180030155`
- `VCRUNTIME140!memcpy` at `0x180030155`
- `VCRUNTIME140!memset` at `0x180030079`
- `VCRUNTIME140!memset` at `0x180030186`
- `VCRUNTIME140!memset` at `0x180030079`
- `VCRUNTIME140!memset` at `0x180030186`
- `ADVAPI32!GetLengthSid` at `0x18003011f`
- `ADVAPI32!GetLengthSid` at `0x18003011f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030131`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800301a3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030131`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800301a3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800301af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800301af`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18003005f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18003005f`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessObjectAce::GetACE(ATL::CDacl::CAccessObjectAce *this)
{
  char *v1; // rbx
  size_t v3; // rdi
  size_t v4; // r14
  char *v5; // rax
  __int64 v6; // rax
  char v7; // al
  __int128 *v8; // r8
  char *v9; // rdi
  int v10; // edx
  __int128 v11; // xmm0
  __int128 *v12; // rax
  __int128 v13; // xmm0
  size_t v14; // rbp
  DWORD LengthSid; // eax
  size_t v16; // r14

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = v3;
    v5 = (char *)malloc(v3);
    v1 = v5;
    if ( !v5 )
      ATL::AtlThrowImpl(-2147024882);
    memset(v5, 0, (unsigned int)v3);
    v1[1] = *((_BYTE *)this + 132);
    v6 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    v7 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(v6 + 24))(this);
    v8 = (__int128 *)*((_QWORD *)this + 19);
    v9 = v1 + 44;
    *v1 = v7;
    *(_QWORD *)(v1 + 4) = *((unsigned int *)this + 32);
    if ( v8 )
    {
      v11 = *v8;
      *((_DWORD *)v1 + 2) = 1;
      v10 = 3;
      *(_OWORD *)(v1 + 12) = v11;
    }
    else
    {
      v9 = v1 + 28;
      v10 = 2;
    }
    v12 = (__int128 *)*((_QWORD *)this + 20);
    if ( v12 )
    {
      v13 = *v12;
      if ( v8 )
        *(_OWORD *)(v1 + 28) = v13;
      else
        *(_OWORD *)(v1 + 12) = v13;
      *((_DWORD *)v1 + 2) = v10;
    }
    else
    {
      v9 -= 16;
    }
    v14 = 0;
    if ( (unsigned __int64)&v1[v4 - (_QWORD)v9] <= v4 )
      v14 = (size_t)&v1[v4 - (_QWORD)v9];
    LengthSid = GetLengthSid((char *)this + 16);
    v16 = LengthSid;
    if ( LengthSid )
    {
      if ( !v9 )
        goto LABEL_16;
      if ( this == (ATL::CDacl::CAccessObjectAce *)-16LL || v14 < LengthSid )
      {
        memset(v9, 0, v14);
        if ( this != (ATL::CDacl::CAccessObjectAce *)-16LL )
        {
          if ( v14 >= v16 )
            goto LABEL_28;
          *_errno() = 34;
LABEL_27:
          _invalid_parameter_noinfo();
LABEL_28:
          ATL::AtlThrowImpl(-2147024809);
        }
LABEL_16:
        *_errno() = 22;
        goto LABEL_27;
      }
      _mm_lfence();
      memcpy(v9, (char *)this + 16, LengthSid);
    }
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x180030020  mov     [rsp+arg_0], rbx
0x180030025  mov     [rsp+arg_8], rbp
0x18003002a  mov     [rsp+arg_10], rsi
0x18003002f  push    rdi
0x180030030  push    r14
0x180030032  push    r15
0x180030034  sub     rsp, 20h
0x180030038  mov     rbx, [rcx+88h]
0x18003003f  mov     rsi, rcx
0x180030042  test    rbx, rbx
0x180030045  jnz     loc_180030162
0x18003004b  mov     rax, [rcx]
0x18003004e  mov     rax, [rax+10h]
0x180030052  call    cs:__guard_dispatch_icall_fptr
0x180030058  mov     ecx, eax; Size
0x18003005a  mov     edi, eax
0x18003005c  mov     r14d, eax
0x18003005f  call    cs:__imp_malloc
0x180030065  mov     rbx, rax
0x180030068  test    rax, rax
0x18003006b  jz      loc_180030193
0x180030071  mov     r8d, r14d; Size
0x180030074  xor     edx, edx; Val
0x180030076  mov     rcx, rax; void *
0x180030079  call    cs:__imp_memset
0x18003007f  mov     al, [rsi+84h]
0x180030085  mov     rcx, rsi
0x180030088  mov     [rbx+1], al
0x18003008b  mov     rax, [rsi]
0x18003008e  mov     [rbx+2], di
0x180030092  mov     rax, [rax+18h]
0x180030096  call    cs:__guard_dispatch_icall_fptr
0x18003009c  mov     r8, [rsi+98h]
0x1800300a3  lea     rdi, [rbx+2Ch]
0x1800300a7  mov     [rbx], al
0x1800300a9  mov     eax, [rsi+80h]
0x1800300af  mov     [rbx+4], eax
0x1800300b2  mov     dword ptr [rbx+8], 0
0x1800300b9  test    r8, r8
0x1800300bc  jnz     short loc_1800300C8
0x1800300be  sub     rdi, 10h
0x1800300c2  lea     edx, [r8+2]
0x1800300c6  jmp     short loc_1800300DD
0x1800300c8  movups  xmm0, xmmword ptr [r8]
0x1800300cc  mov     dword ptr [rbx+8], 1
0x1800300d3  mov     edx, 3
0x1800300d8  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800300dd  mov     rax, [rsi+0A0h]
0x1800300e4  test    rax, rax
0x1800300e7  jnz     short loc_1800300EF
0x1800300e9  sub     rdi, 10h
0x1800300ed  jmp     short loc_180030106
0x1800300ef  movups  xmm0, xmmword ptr [rax]
0x1800300f2  test    r8, r8
0x1800300f5  jz      short loc_1800300FE
0x1800300f7  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x1800300fc  jmp     short loc_180030103
0x1800300fe  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180030103  mov     [rbx+8], edx
0x180030106  xor     ebp, ebp
0x180030108  lea     r15, [rsi+10h]
0x18003010c  mov     rcx, r14
0x18003010f  sub     rcx, rdi
0x180030112  add     rcx, rbx
0x180030115  cmp     rcx, r14
0x180030118  cmovbe  rbp, rcx
0x18003011c  mov     rcx, r15; pSid
0x18003011f  call    cs:__imp_GetLengthSid
0x180030125  mov     r14d, eax
0x180030128  test    eax, eax
0x18003012a  jz      short loc_18003015B
0x18003012c  test    rdi, rdi
0x18003012f  jnz     short loc_18003013F
0x180030131  call    cs:__imp__errno
0x180030137  mov     dword ptr [rax], 16h
0x18003013d  jmp     short loc_1800301AF
0x18003013f  test    r15, r15
0x180030142  jz      short loc_18003017E
0x180030144  cmp     rbp, r14
0x180030147  jb      short loc_18003017E
0x180030149  lfence
0x18003014c  mov     r8, r14; Size
0x18003014f  mov     rdx, r15; Src
0x180030152  mov     rcx, rdi; void *
0x180030155  call    cs:__imp_memcpy
0x18003015b  mov     [rsi+88h], rbx
0x180030162  mov     rbp, [rsp+38h+arg_8]
0x180030167  mov     rax, rbx
0x18003016a  mov     rbx, [rsp+38h+arg_0]
0x18003016f  mov     rsi, [rsp+38h+arg_10]
0x180030174  add     rsp, 20h
0x180030178  pop     r15
0x18003017a  pop     r14
0x18003017c  pop     rdi
0x18003017d  retn
0x18003017e  mov     r8, rbp; Size
0x180030181  xor     edx, edx; Val
0x180030183  mov     rcx, rdi; void *
0x180030186  call    cs:__imp_memset
0x18003018c  test    r15, r15
0x18003018f  jnz     short loc_18003019E
0x180030191  jmp     short loc_180030131
0x180030193  mov     ecx, 8007000Eh; int
0x180030198  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003019e  cmp     rbp, r14
0x1800301a1  jnb     short loc_1800301B5
0x1800301a3  call    cs:__imp__errno
0x1800301a9  mov     dword ptr [rax], 22h ; '"'
0x1800301af  call    cs:__imp__invalid_parameter_noinfo
0x1800301b5  mov     ecx, 80070057h; int
0x1800301ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
