# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x180030dc0`
- end: `0x180030ef2`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `306`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180002604`
- `0x180030dc0`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180030e88`
- `VCRUNTIME140!memcpy` at `0x180030e88`
- `VCRUNTIME140!memset` at `0x180030e19`
- `VCRUNTIME140!memset` at `0x180030eb8`
- `VCRUNTIME140!memset` at `0x180030e19`
- `VCRUNTIME140!memset` at `0x180030eb8`
- `ADVAPI32!GetLengthSid` at `0x180030e4e`
- `ADVAPI32!GetLengthSid` at `0x180030e4e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030e67`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030ed5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030e67`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030ed5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030ee1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030ee1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180030dff`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180030dff`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rbx
  size_t v3; // rsi
  char *v4; // rax
  __int64 v5; // rax
  DWORD LengthSid; // eax
  size_t v7; // rbp
  size_t v8; // rsi
  void *v9; // rcx

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset(v4, 0, (unsigned int)v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v5 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v7 = v3 - 8;
    v8 = LengthSid;
    v9 = v1 + 8;
    if ( LengthSid )
    {
      if ( v1 == (char *)-8LL )
        goto LABEL_5;
      if ( this == (ATL::CDacl::CAccessAce *)-16LL || v7 < LengthSid )
      {
        memset(v9, 0, v7);
        if ( this != (ATL::CDacl::CAccessAce *)-16LL )
        {
          if ( v7 >= v8 )
            goto LABEL_17;
          *_errno() = 34;
LABEL_16:
          _invalid_parameter_noinfo();
LABEL_17:
          ATL::AtlThrowImpl(-2147024809);
        }
LABEL_5:
        *_errno() = 22;
        goto LABEL_16;
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
0x180030dc0  mov     rax, rsp
0x180030dc3  mov     [rax+8], rbx
0x180030dc7  mov     [rax+10h], rbp
0x180030dcb  mov     [rax+18h], rsi
0x180030dcf  mov     [rax+20h], rdi
0x180030dd3  push    r14
0x180030dd5  sub     rsp, 20h
0x180030dd9  mov     rbx, [rcx+88h]
0x180030de0  mov     rdi, rcx
0x180030de3  test    rbx, rbx
0x180030de6  jnz     loc_180030E95
0x180030dec  mov     rax, [rcx]
0x180030def  mov     rax, [rax+10h]
0x180030df3  call    cs:__guard_dispatch_icall_fptr
0x180030df9  mov     ecx, eax; Size
0x180030dfb  mov     esi, eax
0x180030dfd  mov     ebp, eax
0x180030dff  call    cs:__imp_malloc
0x180030e05  mov     rbx, rax
0x180030e08  test    rax, rax
0x180030e0b  jz      loc_180030EC5
0x180030e11  mov     r8d, ebp; Size
0x180030e14  xor     edx, edx; Val
0x180030e16  mov     rcx, rax; void *
0x180030e19  call    cs:__imp_memset
0x180030e1f  mov     al, [rdi+84h]
0x180030e25  mov     rcx, rdi
0x180030e28  mov     [rbx+1], al
0x180030e2b  mov     rax, [rdi]
0x180030e2e  mov     [rbx+2], si
0x180030e32  mov     rax, [rax+18h]
0x180030e36  call    cs:__guard_dispatch_icall_fptr
0x180030e3c  mov     [rbx], al
0x180030e3e  lea     r14, [rdi+10h]
0x180030e42  mov     eax, [rdi+80h]
0x180030e48  mov     rcx, r14; pSid
0x180030e4b  mov     [rbx+4], eax
0x180030e4e  call    cs:__imp_GetLengthSid
0x180030e54  add     rbp, 0FFFFFFFFFFFFFFF8h
0x180030e58  mov     esi, eax
0x180030e5a  lea     rcx, [rbx+8]; void *
0x180030e5e  test    eax, eax
0x180030e60  jz      short loc_180030E8E
0x180030e62  test    rcx, rcx
0x180030e65  jnz     short loc_180030E75
0x180030e67  call    cs:__imp__errno
0x180030e6d  mov     dword ptr [rax], 16h
0x180030e73  jmp     short loc_180030EE1
0x180030e75  test    r14, r14
0x180030e78  jz      short loc_180030EB3
0x180030e7a  cmp     rbp, rsi
0x180030e7d  jb      short loc_180030EB3
0x180030e7f  lfence
0x180030e82  mov     r8, rsi; Size
0x180030e85  mov     rdx, r14; Src
0x180030e88  call    cs:__imp_memcpy
0x180030e8e  mov     [rdi+88h], rbx
0x180030e95  mov     rbp, [rsp+28h+arg_8]
0x180030e9a  mov     rax, rbx
0x180030e9d  mov     rbx, [rsp+28h+arg_0]
0x180030ea2  mov     rsi, [rsp+28h+arg_10]
0x180030ea7  mov     rdi, [rsp+28h+arg_18]
0x180030eac  add     rsp, 20h
0x180030eb0  pop     r14
0x180030eb2  retn
0x180030eb3  mov     r8, rbp; Size
0x180030eb6  xor     edx, edx; Val
0x180030eb8  call    cs:__imp_memset
0x180030ebe  test    r14, r14
0x180030ec1  jnz     short loc_180030ED0
0x180030ec3  jmp     short loc_180030E67
0x180030ec5  mov     ecx, 8007000Eh; int
0x180030eca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180030ed0  cmp     rbp, rsi
0x180030ed3  jnb     short loc_180030EE7
0x180030ed5  call    cs:__imp__errno
0x180030edb  mov     dword ptr [rax], 22h ; '"'
0x180030ee1  call    cs:__imp__invalid_parameter_noinfo
0x180030ee7  mov     ecx, 80070057h; int
0x180030eec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
