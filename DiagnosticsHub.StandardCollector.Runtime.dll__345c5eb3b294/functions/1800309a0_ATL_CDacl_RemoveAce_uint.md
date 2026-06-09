# ATL::CDacl::RemoveAce(uint)

- ea: `0x1800309a0`
- end: `0x180030a7b`
- name: `?RemoveAce@CDacl@ATL@@UEAAXI@Z`
- size: `219`
- prototype: `void __fastcall(ATL::CDacl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180002604`
- `0x1800309a0`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180030a39`
- `VCRUNTIME140!memmove` at `0x180030a39`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030a5e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030a5e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030a6a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030a6a`

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
        memmove(v11, v10, 8 * v7);
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
0x1800309a0  mov     rax, rsp
0x1800309a3  mov     [rax+8], rbx
0x1800309a7  mov     [rax+10h], rbp
0x1800309ab  mov     [rax+18h], rsi
0x1800309af  mov     [rax+20h], rdi
0x1800309b3  push    r14
0x1800309b5  sub     rsp, 20h
0x1800309b9  mov     esi, edx
0x1800309bb  mov     rbx, rcx
0x1800309be  lea     rdi, [rsi+1]
0x1800309c2  cmp     rdi, rsi
0x1800309c5  jb      loc_180030A70
0x1800309cb  cmp     rdi, 1
0x1800309cf  jb      loc_180030A70
0x1800309d5  mov     rbp, [rcx+20h]
0x1800309d9  cmp     rdi, rbp
0x1800309dc  ja      loc_180030A70
0x1800309e2  lfence
0x1800309e5  mov     r14, [rcx+18h]
0x1800309e9  sub     rbp, rdi
0x1800309ec  mov     rcx, [r14+rsi*8]
0x1800309f0  test    rcx, rcx
0x1800309f3  jz      short loc_180030A06
0x1800309f5  mov     rax, [rcx]
0x1800309f8  mov     edx, 1
0x1800309fd  mov     rax, [rax]
0x180030a00  call    cs:__guard_dispatch_icall_fptr
0x180030a06  mov     qword ptr [r14+rsi*8], 0
0x180030a0e  test    rbp, rbp
0x180030a11  jz      short loc_180030A3F
0x180030a13  mov     rax, [rbx+18h]
0x180030a17  lea     r8, ds:0[rbp*8]; Size
0x180030a1f  lea     rdx, [rax+rdi*8]; Src
0x180030a23  lea     rcx, [rax+rsi*8]; void *
0x180030a27  test    r8, r8
0x180030a2a  jz      short loc_180030A3F
0x180030a2c  test    rcx, rcx
0x180030a2f  jz      short loc_180030A5E
0x180030a31  test    rdx, rdx
0x180030a34  jz      short loc_180030A5E
0x180030a36  lfence
0x180030a39  call    cs:__imp_memmove
0x180030a3f  dec     qword ptr [rbx+20h]
0x180030a43  mov     rbx, [rsp+28h+arg_0]
0x180030a48  mov     rbp, [rsp+28h+arg_8]
0x180030a4d  mov     rsi, [rsp+28h+arg_10]
0x180030a52  mov     rdi, [rsp+28h+arg_18]
0x180030a57  add     rsp, 20h
0x180030a5b  pop     r14
0x180030a5d  retn
0x180030a5e  call    cs:__imp__errno
0x180030a64  mov     dword ptr [rax], 16h
0x180030a6a  call    cs:__imp__invalid_parameter_noinfo
0x180030a70  mov     ecx, 80070057h; int
0x180030a75  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
