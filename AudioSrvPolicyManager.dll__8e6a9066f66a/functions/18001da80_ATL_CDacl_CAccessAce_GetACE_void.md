# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x18001da80`
- end: `0x18001db99`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `281`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001da80`
- `0x18002bd9c`
- `0x180032736`
- `0x1800327e0`
- `0x1800327f8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001daba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001daba`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db78`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db8b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db78`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001db8b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001db08`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001db08`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rbx
  size_t v4; // rbp
  size_t v5; // rsi
  char *v6; // rax
  __int64 v7; // rax
  DWORD LengthSid; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  size_t v12; // rbp
  void *v13; // rcx
  size_t v14; // rsi

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v4 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v5 = v4;
    v6 = (char *)malloc(v4);
    v1 = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v6, 0, (unsigned int)v4);
    v1[1] = *((_BYTE *)this + 132);
    v7 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v4;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v7 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v12 = LengthSid;
    if ( !LengthSid )
      goto LABEL_9;
    v13 = v1 + 8;
    if ( v1 == (char *)-8LL )
      goto LABEL_10;
    v14 = v5 - 8;
    if ( this != (ATL::CDacl::CAccessAce *)-16LL && v14 >= LengthSid )
    {
      memcpy_0(v13, (char *)this + 16, LengthSid);
LABEL_9:
      *((_QWORD *)this + 17) = v1;
      return v1;
    }
    memset_0(v13, 0, v14);
    if ( this == (ATL::CDacl::CAccessAce *)-16LL )
    {
LABEL_10:
      *(_DWORD *)_o__errno(v13, v9, v10, v11) = 22;
    }
    else
    {
      if ( v14 >= v12 )
LABEL_12:
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)_o__errno(v13, v9, v10, v11) = 34;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
  return v1;
}

```

## disassembly

```asm
0x18001da80  push    rbx
0x18001da82  push    rbp
0x18001da83  push    rsi
0x18001da84  push    rdi
0x18001da85  push    r14
0x18001da87  sub     rsp, 20h
0x18001da8b  mov     rbx, [rcx+88h]
0x18001da92  mov     rdi, rcx
0x18001da95  test    rbx, rbx
0x18001da98  jz      short loc_18001DAA8
0x18001da9a  mov     rax, rbx
0x18001da9d  add     rsp, 20h
0x18001daa1  pop     r14
0x18001daa3  pop     rdi
0x18001daa4  pop     rsi
0x18001daa5  pop     rbp
0x18001daa6  pop     rbx
0x18001daa7  retn
0x18001daa8  mov     rax, [rcx]
0x18001daab  mov     rax, [rax+10h]
0x18001daaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dab4  mov     ecx, eax; Size
0x18001dab6  mov     ebp, eax
0x18001dab8  mov     esi, eax
0x18001daba  call    cs:__imp_malloc
0x18001dac0  mov     rbx, rax
0x18001dac3  test    rax, rax
0x18001dac6  jz      loc_18001DB5E
0x18001dacc  mov     r8d, esi; Size
0x18001dacf  xor     edx, edx; Val
0x18001dad1  mov     rcx, rax; void *
0x18001dad4  call    memset_0
0x18001dad9  movzx   eax, byte ptr [rdi+84h]
0x18001dae0  mov     rcx, rdi
0x18001dae3  mov     [rbx+1], al
0x18001dae6  mov     rax, [rdi]
0x18001dae9  mov     [rbx+2], bp
0x18001daed  mov     rax, [rax+18h]
0x18001daf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daf6  mov     [rbx], al
0x18001daf8  lea     r14, [rdi+10h]
0x18001dafc  mov     eax, [rdi+80h]
0x18001db02  mov     rcx, r14; pSid
0x18001db05  mov     [rbx+4], eax
0x18001db08  call    cs:__imp_GetLengthSid
0x18001db0e  mov     ebp, eax
0x18001db10  test    eax, eax
0x18001db12  jz      short loc_18001DB36
0x18001db14  lea     rcx, [rbx+8]; void *
0x18001db18  test    rcx, rcx
0x18001db1b  jz      short loc_18001DB42
0x18001db1d  add     rsi, 0FFFFFFFFFFFFFFF8h
0x18001db21  test    r14, r14
0x18001db24  jz      short loc_18001DB69
0x18001db26  cmp     rsi, rbp
0x18001db29  jb      short loc_18001DB69
0x18001db2b  mov     r8d, ebp; Size
0x18001db2e  mov     rdx, r14; Src
0x18001db31  call    memcpy_0
0x18001db36  mov     [rdi+88h], rbx
0x18001db3d  jmp     loc_18001DA9A
0x18001db42  call    cs:__imp__o__errno
0x18001db48  mov     dword ptr [rax], 16h
0x18001db4e  call    _invalid_parameter_noinfo
0x18001db53  mov     ecx, 80070057h; int
0x18001db58  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001db5e  mov     ecx, 8007000Eh; int
0x18001db63  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001db69  mov     r8, rsi; Size
0x18001db6c  xor     edx, edx; Val
0x18001db6e  call    memset_0
0x18001db73  test    r14, r14
0x18001db76  jnz     short loc_18001DB86
0x18001db78  call    cs:__imp__o__errno
0x18001db7e  mov     dword ptr [rax], 16h
0x18001db84  jmp     short loc_18001DB4E
0x18001db86  cmp     rsi, rbp
0x18001db89  jnb     short loc_18001DB53
0x18001db8b  call    cs:__imp__o__errno
0x18001db91  mov     dword ptr [rax], 22h ; '"'
0x18001db97  jmp     short loc_18001DB4E
```
