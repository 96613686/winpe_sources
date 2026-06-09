# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x18002c900`
- end: `0x18002c9b1`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `177`
- prototype: `char *__fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017f50`
- `0x180019e00`
- `0x18001c684`
- `0x18002c334`
- `0x18002c900`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c92c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c92c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c97d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c97d`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  DWORD LengthSid; // eax
  errno_t v7; // eax

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v5 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v7 = memcpy_s(v1 + 8, v3 - 8, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v7);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18002c900  push    rbx
0x18002c902  push    rbp
0x18002c903  push    rsi
0x18002c904  push    rdi
0x18002c905  sub     rsp, 28h
0x18002c909  mov     rdi, [rcx+88h]
0x18002c910  mov     rsi, rcx
0x18002c913  test    rdi, rdi
0x18002c916  jnz     loc_18002C9A5
0x18002c91c  mov     rax, [rcx]
0x18002c91f  mov     rax, [rax+10h]
0x18002c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c928  mov     ecx, eax; Size
0x18002c92a  mov     ebx, eax
0x18002c92c  call    cs:__imp_malloc
0x18002c932  mov     rdi, rax
0x18002c935  test    rax, rax
0x18002c938  jnz     short loc_18002C945
0x18002c93a  mov     ecx, 8007000Eh; int
0x18002c93f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c945  mov     r8, rbx; Size
0x18002c948  xor     edx, edx; Val
0x18002c94a  mov     rcx, rdi; void *
0x18002c94d  call    memset_0
0x18002c952  mov     al, [rsi+84h]
0x18002c958  mov     rcx, rsi
0x18002c95b  mov     [rdi+1], al
0x18002c95e  mov     rax, [rsi]
0x18002c961  mov     [rdi+2], bx
0x18002c965  mov     rax, [rax+18h]
0x18002c969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c96e  mov     [rdi], al
0x18002c970  lea     rcx, [rsi+10h]; pSid
0x18002c974  mov     eax, [rsi+80h]
0x18002c97a  mov     [rdi+4], eax
0x18002c97d  call    cs:__imp_GetLengthSid
0x18002c983  mov     r9d, eax; SourceSize
0x18002c986  lea     rdx, [rbx-8]; DestinationSize
0x18002c98a  lea     rcx, [rdi+8]; Destination
0x18002c98e  lea     r8, [rsi+10h]; Source
0x18002c992  call    memcpy_s
0x18002c997  mov     ecx, eax; int
0x18002c999  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002c99e  mov     [rsi+88h], rdi
0x18002c9a5  mov     rax, rdi
0x18002c9a8  add     rsp, 28h
0x18002c9ac  pop     rdi
0x18002c9ad  pop     rsi
0x18002c9ae  pop     rbp
0x18002c9af  pop     rbx
0x18002c9b0  retn
```
