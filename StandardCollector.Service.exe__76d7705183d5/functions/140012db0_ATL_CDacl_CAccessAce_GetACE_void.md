# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x140012db0`
- end: `0x140012edf`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `303`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140002e74`
- `0x140012db0`
- `0x14001473e`
- `0x140014bc0`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140012e3d`
- `ADVAPI32!GetLengthSid` at `0x140012e3d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012e56`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012ec2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012e56`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012ec2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140012ece`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140012ece`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140012def`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140012def`

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
    memset_0(v4, 0, (unsigned int)v3);
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
        memset_0(v9, 0, v7);
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
      memcpy_0(v9, (char *)this + 16, LengthSid);
    }
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x140012db0  mov     rax, rsp
0x140012db3  mov     [rax+8], rbx
0x140012db7  mov     [rax+10h], rbp
0x140012dbb  mov     [rax+18h], rsi
0x140012dbf  mov     [rax+20h], rdi
0x140012dc3  push    r14
0x140012dc5  sub     rsp, 20h
0x140012dc9  mov     rbx, [rcx+88h]
0x140012dd0  mov     rdi, rcx
0x140012dd3  test    rbx, rbx
0x140012dd6  jnz     loc_140012E83
0x140012ddc  mov     rax, [rcx]
0x140012ddf  mov     rax, [rax+10h]
0x140012de3  call    cs:__guard_dispatch_icall_fptr
0x140012de9  mov     ecx, eax; Size
0x140012deb  mov     esi, eax
0x140012ded  mov     ebp, eax
0x140012def  call    cs:__imp_malloc
0x140012df5  mov     rbx, rax
0x140012df8  test    rax, rax
0x140012dfb  jz      loc_140012EB2
0x140012e01  mov     r8d, ebp; Size
0x140012e04  xor     edx, edx; Val
0x140012e06  mov     rcx, rax; void *
0x140012e09  call    memset_0
0x140012e0e  mov     al, [rdi+84h]
0x140012e14  mov     rcx, rdi
0x140012e17  mov     [rbx+1], al
0x140012e1a  mov     rax, [rdi]
0x140012e1d  mov     [rbx+2], si
0x140012e21  mov     rax, [rax+18h]
0x140012e25  call    cs:__guard_dispatch_icall_fptr
0x140012e2b  mov     [rbx], al
0x140012e2d  lea     r14, [rdi+10h]
0x140012e31  mov     eax, [rdi+80h]
0x140012e37  mov     rcx, r14; pSid
0x140012e3a  mov     [rbx+4], eax
0x140012e3d  call    cs:__imp_GetLengthSid
0x140012e43  add     rbp, 0FFFFFFFFFFFFFFF8h
0x140012e47  mov     esi, eax
0x140012e49  lea     rcx, [rbx+8]; void *
0x140012e4d  test    eax, eax
0x140012e4f  jz      short loc_140012E7C
0x140012e51  test    rcx, rcx
0x140012e54  jnz     short loc_140012E64
0x140012e56  call    cs:__imp__errno
0x140012e5c  mov     dword ptr [rax], 16h
0x140012e62  jmp     short loc_140012ECE
0x140012e64  test    r14, r14
0x140012e67  jz      short loc_140012EA1
0x140012e69  cmp     rbp, rsi
0x140012e6c  jb      short loc_140012EA1
0x140012e6e  lfence
0x140012e71  mov     r8, rsi; Size
0x140012e74  mov     rdx, r14; Src
0x140012e77  call    memcpy_0
0x140012e7c  mov     [rdi+88h], rbx
0x140012e83  mov     rbp, [rsp+28h+arg_8]
0x140012e88  mov     rax, rbx
0x140012e8b  mov     rbx, [rsp+28h+arg_0]
0x140012e90  mov     rsi, [rsp+28h+arg_10]
0x140012e95  mov     rdi, [rsp+28h+arg_18]
0x140012e9a  add     rsp, 20h
0x140012e9e  pop     r14
0x140012ea0  retn
0x140012ea1  mov     r8, rbp; Size
0x140012ea4  xor     edx, edx; Val
0x140012ea6  call    memset_0
0x140012eab  test    r14, r14
0x140012eae  jnz     short loc_140012EBD
0x140012eb0  jmp     short loc_140012E56
0x140012eb2  mov     ecx, 8007000Eh; int
0x140012eb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012ebd  cmp     rbp, rsi
0x140012ec0  jnb     short loc_140012ED4
0x140012ec2  call    cs:__imp__errno
0x140012ec8  mov     dword ptr [rax], 22h ; '"'
0x140012ece  call    cs:__imp__invalid_parameter_noinfo
0x140012ed4  mov     ecx, 80070057h; int
0x140012ed9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
