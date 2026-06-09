# ATL::CDacl::RemoveAce(uint)

- ea: `0x140012990`
- end: `0x140012a6a`
- name: `?RemoveAce@CDacl@ATL@@UEAAXI@Z`
- size: `218`
- prototype: `void __fastcall(ATL::CDacl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140002e74`
- `0x140012990`
- `0x140014bc6`
- `0x140014c70`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012a4d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012a4d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140012a59`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140012a59`

## pseudocode

```c
void __fastcall ATL::CDacl::RemoveAce(ATL::CDacl *this, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbp
  __int64 v6; // r14
  unsigned __int64 v7; // rbp
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  __int64 v9; // rax
  const void *v10; // rdx
  void *v11; // rcx

  v2 = a2;
  v4 = a2 + 1LL;
  if ( v4 < a2 )
    goto LABEL_13;
  if ( a2 == -1 )
    goto LABEL_13;
  v5 = *((_QWORD *)this + 4);
  if ( v4 > v5 )
    goto LABEL_13;
  _mm_lfence();
  v6 = *((_QWORD *)this + 3);
  v7 = v5 - v4;
  v8 = *(void (__fastcall ****)(_QWORD, __int64))(v6 + 8LL * a2);
  if ( v8 )
    (**v8)(v8, 1);
  *(_QWORD *)(v6 + 8 * v2) = 0;
  if ( v7 )
  {
    v9 = *((_QWORD *)this + 3);
    v10 = (const void *)(v9 + 8 * v4);
    v11 = (void *)(v9 + 8 * v2);
    if ( 8 * v7 )
    {
      if ( v11 && v10 )
      {
        _mm_lfence();
        memmove_0(v11, v10, 8 * v7);
        goto LABEL_11;
      }
      *_errno() = 22;
      _invalid_parameter_noinfo();
LABEL_13:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
LABEL_11:
  --*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x140012990  mov     rax, rsp
0x140012993  mov     [rax+8], rbx
0x140012997  mov     [rax+10h], rbp
0x14001299b  mov     [rax+18h], rsi
0x14001299f  mov     [rax+20h], rdi
0x1400129a3  push    r14
0x1400129a5  sub     rsp, 20h
0x1400129a9  mov     esi, edx
0x1400129ab  mov     rbx, rcx
0x1400129ae  lea     rdi, [rsi+1]
0x1400129b2  cmp     rdi, rsi
0x1400129b5  jb      loc_140012A5F
0x1400129bb  cmp     rdi, 1
0x1400129bf  jb      loc_140012A5F
0x1400129c5  mov     rbp, [rcx+20h]
0x1400129c9  cmp     rdi, rbp
0x1400129cc  ja      loc_140012A5F
0x1400129d2  lfence
0x1400129d5  mov     r14, [rcx+18h]
0x1400129d9  sub     rbp, rdi
0x1400129dc  mov     rcx, [r14+rsi*8]
0x1400129e0  test    rcx, rcx
0x1400129e3  jz      short loc_1400129F6
0x1400129e5  mov     rax, [rcx]
0x1400129e8  mov     edx, 1
0x1400129ed  mov     rax, [rax]
0x1400129f0  call    cs:__guard_dispatch_icall_fptr
0x1400129f6  mov     qword ptr [r14+rsi*8], 0
0x1400129fe  test    rbp, rbp
0x140012a01  jz      short loc_140012A2E
0x140012a03  mov     rax, [rbx+18h]
0x140012a07  lea     r8, ds:0[rbp*8]; Size
0x140012a0f  lea     rdx, [rax+rdi*8]; Src
0x140012a13  lea     rcx, [rax+rsi*8]; void *
0x140012a17  test    r8, r8
0x140012a1a  jz      short loc_140012A2E
0x140012a1c  test    rcx, rcx
0x140012a1f  jz      short loc_140012A4D
0x140012a21  test    rdx, rdx
0x140012a24  jz      short loc_140012A4D
0x140012a26  lfence
0x140012a29  call    memmove_0
0x140012a2e  dec     qword ptr [rbx+20h]
0x140012a32  mov     rbx, [rsp+28h+arg_0]
0x140012a37  mov     rbp, [rsp+28h+arg_8]
0x140012a3c  mov     rsi, [rsp+28h+arg_10]
0x140012a41  mov     rdi, [rsp+28h+arg_18]
0x140012a46  add     rsp, 20h
0x140012a4a  pop     r14
0x140012a4c  retn
0x140012a4d  call    cs:__imp__errno
0x140012a53  mov     dword ptr [rax], 16h
0x140012a59  call    cs:__imp__invalid_parameter_noinfo
0x140012a5f  mov     ecx, 80070057h; int
0x140012a64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
